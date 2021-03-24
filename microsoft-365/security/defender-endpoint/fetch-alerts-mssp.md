---
title: Waarschuwingen ophalen van MSSP-klant tenant
description: Informatie over het ophalen van waarschuwingen van een klant tenant
keywords: managed security service provider, mssp, configure, integration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ee2a5e1815dd552753ac7f3dee30df11ac4332e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060546"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a>Waarschuwingen ophalen van MSSP-klant tenant

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!NOTE]
>Deze actie wordt ondernomen door de MSSP.


Er zijn twee manieren waarop u waarschuwingen kunt ophalen:
- De SIEM-methode gebruiken
- API's gebruiken

## <a name="fetch-alerts-into-your-siem"></a>Waarschuwingen ophalen in uw SIEM

Als u waarschuwingen wilt ophalen in uw SIEM-systeem, moet u de volgende stappen ondernemen:

Stap 1: Een toepassing van derden maken

Stap 2: Toegang krijgen en tokens vernieuwen van de tenant van uw klant
 
Stap 3: uw toepassing toestaan in het Microsoft Defender-beveiligingscentrum
 
### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a>Stap 1: Een toepassing maken in Azure Active Directory (Azure AD)
 
U moet een toepassing maken en deze machtigingen verlenen om waarschuwingen op te halen bij de Microsoft Defender voor Eindpunt-tenant van uw klant.

1. Meld u aan bij de [Azure AD-portal.](https://aad.portal.azure.com/)

2. Selecteer **Azure Active Directory**  >  **App-registraties**.
 
3. Klik **op Nieuwe registratie.**

4. Geef de volgende waarden op:

    - Naam: \<Tenant_name\> SIEM MSSP Connector (vervangen door Tenant_name tenantweergavenaam)
 
    - Ondersteunde accounttypen: Alleen account in deze organisatiemap 
    - Redirect URI: Web selecteren en typen `https://<domain_name>/SiemMsspConnector` (<domain_name> vervangen door de tenantnaam)

5. Klik **op Registreren.** De toepassing wordt weergegeven in de lijst met toepassingen die u bezit.

6. Selecteer de toepassing en klik vervolgens op **Overzicht.**

7. Kopieer de waarde van het **veld Toepassings-id (client-id)** naar een veilige plaats, u hebt deze in de volgende stap nodig.

8. Selecteer **Certificaat & in** het nieuwe toepassingsvenster.

9. Klik **op Nieuw clientgeheim.**

    - Beschrijving: Voer een beschrijving voor de sleutel in.
    - Verloopt: Selecteren **in 1 jaar**

 
10. Klik **op Toevoegen,** kopieer de waarde van het clientgeheim naar een veilige plaats, u hebt dit nodig in de volgende stap.
 

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a>Stap 2: Toegang krijgen en tokens vernieuwen van de tenant van uw klant
In deze sectie vindt u informatie over het gebruik van een PowerShell-script om de tokens van de tenant van uw klant op te halen. In dit script wordt de toepassing uit de vorige stap gebruikt om de toegangs- en vernieuwingstokens te verkrijgen met behulp van de OAuth Authorization Code Flow.

Nadat u uw referenties hebt ingediend, moet u toestemming verlenen voor de toepassing, zodat de toepassing is ingericht in de tenant van de klant.


1. Een nieuwe map maken en deze een naam geven: `MsspTokensAcquisition` .

2. Download de [module LoginBrowser.psm1](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) en sla deze op in de `MsspTokensAcquisition` map.

    >[!NOTE]
    >Vervang in regel 30 `authorzationUrl` door `authorizationUrl` .

3. Maak een bestand met de volgende inhoud en sla het op met de naam `MsspTokensAcquisition.ps1` in de map:
    ```
    param (
        [Parameter(Mandatory=$true)][string]$clientId,
        [Parameter(Mandatory=$true)][string]$secret,
        [Parameter(Mandatory=$true)][string]$tenantId
    )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

    # Load our Login Browser Function
    Import-Module .\LoginBrowser.psm1

    # Configuration parameters
    $login = "https://login.microsoftonline.com"
    $redirectUri = "https://SiemMsspConnector"
    $resourceId = "https://graph.windows.net"

    Write-Host 'Prompt the user for his credentials, to get an authorization code'
    $authorizationUrl = ("{0}/{1}/oauth2/authorize?prompt=select_account&response_type=code&client_id={2}&redirect_uri={3}&resource={4}" -f
                        $login, $tenantId, $clientId, $redirectUri, $resourceId)
    Write-Host "authorzationUrl: $authorizationUrl"

    # Fake a proper endpoint for the Redirect URI
    $code = LoginBrowser $authorizationUrl $redirectUri

    # Acquire token using the authorization code

    $Body = @{
        grant_type = 'authorization_code'
        client_id = $clientId
        code = $code
        redirect_uri = $redirectUri
        resource = $resourceId
        client_secret = $secret
    }

    $tokenEndpoint = "$login/$tenantId/oauth2/token?"
    $Response = Invoke-RestMethod -Method Post -Uri $tokenEndpoint -Body $Body
    $token = $Response.access_token
    $refreshToken= $Response.refresh_token

    Write-Host " -----------------------------------  TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " -----------------------------------  REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken 
    ```
4. Open een verhoogde PowerShell-opdrachtprompt in de `MsspTokensAcquisition` map.

5. Voer de volgende opdracht uit: `Set-ExecutionPolicy -ExecutionPolicy Bypass`

6. Voer de volgende opdrachten in: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`
 
    - Vervang \<client_id\> de **toepassings-id (client-id)** die u hebt van de vorige stap.
    - Vervang \<app_key\> het **clientgeheim dat** u hebt gemaakt op de vorige stap.
    - Vervangen \<customer_tenant_id\> door de **tenant-id van uw klant.** 
 

7. U wordt gevraagd uw referenties en toestemming te geven. Negeer de omleiding van de pagina.

8. In het PowerShell-venster ontvangt u een toegangs-token en een vernieuwings-token. Sla het vernieuwingsken op om de SIEM-connector te configureren. 
 
### <a name="step-3-allow-your-application-on-microsoft-defender-security-center"></a>Stap 3: Uw toepassing toestaan in het Microsoft Defender-beveiligingscentrum
U moet de toepassing toestaan die u hebt gemaakt in het Microsoft Defender-beveiligingscentrum.
 
U moet de machtiging Portalsysteeminstellingen **beheren** hebben om de toepassing toe te staan. Anders moet u uw klant vragen om de toepassing voor u toe te staan.

1. Ga naar `https://securitycenter.windows.com?tid=<customer_tenant_id>` (vervangen \<customer_tenant_id\> door de tenant-id van de klant.

2. Klik **op Instellingen**  >  **SIEM**. 

3. Selecteer het **tabblad MSSP.**

4. Voer de **toepassings-id** in van de eerste stap en uw **tenant-id.**

5. Klik **op Toepassing autoreren.** 

 
U kunt nu het relevante configuratiebestand voor uw SIEM downloaden en verbinding maken met de Defender for Endpoint API. Zie Waarschuwingen naar uw [SIEM-hulpprogramma's trekken voor meer informatie.](configure-siem.md)
 

- Schrijf de toepassingssleutel handmatig in het configuratiebestand ArcSight / Splunk Authentication Properties door de geheime waarde in te stellen.
- In plaats van een vernieuwingsken in de portal te kopen, gebruikt u het script uit de vorige stap om een vernieuwings-token te verkrijgen (of op een andere manier te verkrijgen).

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a>Waarschuwingen ophalen bij de tenant van MSSP-klanten met API's
 
Zie Waarschuwingen ophalen met REST API voor informatie over het ophalen van waarschuwingen met BEHULP van [REST API.](pull-alerts-using-rest-api.md)


## <a name="see-also"></a>Zie ook
- [MSSP-toegang verlenen tot de portal](grant-mssp-access.md)
- [Toegang tot de MSSP-klantportal](access-mssp-portal.md)
- [Waarschuwingsmeldingen configureren](configure-mssp-notifications.md)
