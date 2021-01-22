---
title: Hallo wereld voor Microsoft 365 Defender REST API
description: Informatie over het maken van een app en het gebruik van een token voor toegang tot de Microsoft 365 Defender-API's
keywords: app, token, access, aad, app, application registration, powershell, script, global administrator, permission, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 66afa27d0fa7a092d3f9e9ed6c3b6abc6020cb8d
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928376"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Hallo wereld voor Microsoft 365 Defender REST API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie heeft betrekking op vooraf uitgebracht product dat aanzienlijk kan worden gewijzigd voordat het in de handel wordt gebracht. Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt be gegeven.

## <a name="get-incidents-using-a-simple-powershell-script"></a>Incidenten krijgen met een eenvoudig PowerShell-script

Het duurt 5 tot 10 minuten om dit project te voltooien. Deze tijdschatting omvat het registreren van de toepassing en het toepassen van de code uit het PowerShell-voorbeeldscript.

### <a name="register-an-app-in-azure-active-directory"></a>Een app registreren in Azure Active Directory

1. Meld u aan [bij Azure](https://portal.azure.com) als gebruiker met de rol **van globale** beheerder.

2. Navigeer **naar de nieuwe registratie** van Azure Active Directory  >  **App-registraties.**  >  

   ![Afbeelding van Microsoft Azure en navigatie naar toepassingsregistratie](../../media/atp-azure-new-app2.png)

3. Kies in het registratieformulier een naam voor uw toepassing en selecteer **Register.** Het selecteren van een omleidings-URI is optioneel. U hebt er geen nodig om dit voorbeeld te voltooien.

4. Selecteer op uw **toepassingspagina** API-machtigingen Toevoegen machtiging-API's die door mijn organisatie >, typ Microsoft Threat Protection en selecteer  >    >   Microsoft **Threat Protection.**  Uw app heeft nu toegang tot Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection* is een voormalige naam voor Microsoft 365 Defender en wordt niet weergegeven in de oorspronkelijke lijst. U moet beginnen met het schrijven van de naam in het tekstvak om deze weer te geven.
   ![Afbeelding van api-machtigingenselectie](../../media/apis-in-my-org-tab.PNG)

   - Kies **Toepassingsmachtigingen**  >  **Incident.Read.All** en selecteer **Machtigingen toevoegen.**

   ![Afbeelding van API-toegang en API-selectie](../../media/request-api-permissions.PNG)

5. Selecteer **Beheerdersmachtiging verlenen.** Telkens wanneer u een machtiging toevoegt, moet u Toestemming **van een beheerder verlenen** selecteren om deze van kracht te laten worden.

    ![Afbeelding van Machtigingen verlenen](../../media/grant-consent.PNG)

6. Voeg een geheim toe aan de toepassing. Selecteer **Certificaten & geheimen,** voeg een beschrijving toe aan het geheim en selecteer Vervolgens **Toevoegen.**

    > [!TIP]
    > Nadat u Toevoegen **hebt geselecteerd,** **selecteert u de gegenereerde geheime waarde kopiëren.** Nadat u de geheime waarde hebt verlaten, kunt u deze niet meer ophalen.

    ![Afbeelding van app-sleutel maken](../../media/webapp-create-key2.png)

7. Neem uw toepassings-id en tenant-id op in een veilige plaats. Ze worden weergegeven onder Overzicht op **uw** toepassingspagina.

   ![Afbeelding van gemaakte app-id](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>Een token downloaden met behulp van de app en het token gebruiken voor toegang tot de API

Zie de Azure AD-zelfstudie [](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)voor meer informatie over Azure Active Directory-tokens.

> [!IMPORTANT]
> Hoewel het voorbeeld in deze demo-app u aanmoedigt om  uw geheime waarde voor testdoeleinden te plakken, moet u nooit geheimen coderen in een toepassing die wordt uitgevoerd in productie. Een derde partij kan uw geheim gebruiken om toegang te krijgen tot bronnen. U kunt de geheimen van uw app veilig houden met behulp van [Azure Key Vault.](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates) Zie Geheimen in uw [server-apps](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)beheren met Azure Key Vault voor een praktisch voorbeeld van hoe u uw app kunt beschermen.

1. Kopieer het onderstaande script en plak dit in uw favoriete teksteditor. Opslaan als **Get-Token.ps1.** U kunt de code ook in PowerShell ISE uitvoeren, maar u moet deze opslaan omdat deze opnieuw moet worden uitgevoerd wanneer we het script voor het ophalen van incidenten in de volgende sectie gebruiken.

    Met dit script wordt een token gegenereerd en opgeslagen in de werkmap onder de *naam,Latest-token.txt.*

    ```PowerShell
    # This script gets the app context token and saves it to a file named "Latest-token.txt" under the current directory.
    # Paste in your tenant ID, client ID and app secret (App key).

    $tenantId = '' # Paste your directory (tenant) ID here
    $clientId = '' # Paste your application (client) ID here
    $appSecret = '' # # Paste your own app secret here to test, then store it in a safe place!

    $resourceAppIdUri = 'https://api.security.microsoft.com'
    $oAuthUri = "https://login.windows.net/$tenantId/oauth2/token"
    $authBody = [Ordered] @{
      resource = $resourceAppIdUri
      client_id = $clientId
      client_secret = $appSecret
      grant_type = 'client_credentials'
    }
    $authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
    $token = $authResponse.access_token
    Out-File -FilePath "./Latest-token.txt" -InputObject $token
    return $token
    ```

#### <a name="validate-the-token"></a>Het token valideren

1. Kopieer en plak het token dat u hebt ontvangen in [JWT om](https://jwt.ms) het te decoderen.
1. *JWT* staat voor *JSON Web Token.* Het gedecodeerde token bevat een aantal in JSON opgemaakte items of claims. Zorg ervoor dat de *rollen die* binnen het gedecodeerde token worden gebruikt, de gewenste machtigingen bevatten.

    In de volgende afbeelding ziet u een gedecodeerd token dat is verkregen van een app, met ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` en ```AdvancedHunting.Read.All``` machtigingen:

    ![Afbeelding jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a>Een lijst met recente incidenten

Het onderstaande script gebruikt **Get-Token.ps1** om toegang te krijgen tot de API. Vervolgens wordt een lijst opgehaald met incidenten die het laatst binnen de afgelopen 48 uur zijn bijgewerkt en wordt de lijst opgeslagen als een JSON-bestand.

> [!IMPORTANT]
> Sla dit script op in de map die u hebt **opgeslagenGet-Token.ps1.**

```PowerShell
# This script returns incidents last updated within the past 48 hours.

$token = ./Get-Token.ps1

# Get incidents from the past 48 hours.
# The script may appear to fail if you don't have any incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# This URL contains the type of query and the time filter we created above.
# Note that `$filter` does not refer to a local variable in our script --
# it's actually an OData operator and part of the API's syntax.
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the webrequest headers
$headers = @{
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the request and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results.
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get a string containing the execution time. We concatenate that string to the name 
# of the output file to avoid overwriting the file on consecutive runs of the script.
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"

Out-File -FilePath $outputJsonPath -InputObject $incidents
```

U bent klaar. U hebt het volgende gedaan:

- Er is een toepassing gemaakt en geregistreerd.
- Deze toepassing heeft toestemming verleend om waarschuwingen te lezen.
- Verbonden met de API.
- Een PowerShell-script gebruikt om incidenten te retourneren die in de afgelopen 48 uur zijn bijgewerkt.

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van Microsoft 365 Defender API's](api-overview.md)
- [Toegang tot de Microsoft 365 Defender-API's](api-access.md)
- [Een app maken voor toegang tot Microsoft 365 Defender zonder een gebruiker](api-create-app-web.md)
- [Een app maken voor toegang tot Microsoft 365 Defender API's namens een gebruiker](api-create-app-user-context.md)
- [Een app maken met partnertoegang met meerdere tenants tot Microsoft 365 Defender-API's](api-partner-access.md)
- [Geheimen in uw server-apps beheren met Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2.0 Authorization for user sign in and API access](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
