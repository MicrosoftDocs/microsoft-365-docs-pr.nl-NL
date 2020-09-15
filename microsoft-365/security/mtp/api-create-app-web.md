---
title: Een app maken om toegang te krijgen tot Microsoft Threat Protection zonder een gebruiker
description: Meer informatie over het maken van een app voor toegang tot Microsoft Threat Protection zonder een gebruiker
keywords: app, Access, API, Create
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: be637bab97083cb857e3983dd9b82290590c1302
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650250"
---
# <a name="create-an-app-to-access-microsoft-threat-protection-without-a-user"></a>Een app maken om toegang te krijgen tot Microsoft Threat Protection zonder een gebruiker

**Van toepassing op:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.

Op deze pagina wordt beschreven hoe u een toepassing maakt om via een programma toegang te krijgen tot Microsoft Threat Protection zonder een gebruiker. Als u toegang tot Microsoft Threat Protection voornaam van een gebruiker nodig hebt, raadpleegt u [toegang krijgen met gebruikerscontext](api-create-app-user-context.md). Als u niet zeker weet welke toegang u nodig hebt, raadpleegt u [aan de slag](api-access.md).

Microsoft Threat Protection geeft veel van zijn gegevens en acties getoond via een set programmeer Api's. Met deze Api's wordt u geholpen bij het automatiseren van werkstromen en innoveren op basis van de mogelijkheden van Microsoft Threat Protection. Voor API-toegang is OAuth 2.0-authenticatie vereist. Voor meer informatie raadpleegt u [OAuth 2,0 Authorization code flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

In het algemeen dient u de volgende stappen uit te voeren om de Api's te gebruiken:
- Maak een Azure AD-toepassing (Azure Active Directory).
- U krijgt een toegangstoken met deze toepassing.
- Gebruik het token om toegang te krijgen tot de Microsoft Threat Protection API.

In dit artikel wordt uitgelegd hoe u een Azure AD-toepassing maakt, een toegangstoken krijgt voor Microsoft Threat Protection en het token valideert.

## <a name="create-an-app"></a>Een app maken

1. Meld u aan bij [Azure](https://portal.azure.com) met een gebruiker die de rol **globale beheerder** heeft.

2. Ga naar de **Azure Active Directory**-  >  **app registraties**  >  **nieuwe registratie**. 

   ![Afbeelding van Microsoft Azure en navigatie naar toepassing registreren](../../media/atp-azure-new-app2.png)

3. Kies in het registratieformulier een naam voor de toepassing en selecteer vervolgens **registreren**.

4. Als u de app wilt gebruiken voor toegang tot Microsoft Threat Protection en de machtigingen voor deze persoon wilt toewijzen, selecteert u op de Toepassingspagina **API-machtigingen**de optie API-  >  api's**toevoegen**  >  **Mijn organisatie gebruikt** >, typt u **Microsoft Threat Protection**en selecteert u vervolgens **Microsoft Threat Protection**.

   > [!NOTE]
   > Microsoft Threat Protection wordt niet weergegeven in de oorspronkelijke lijst. U moet de naam ervan beginnen te schrijven in het tekstvak om de naam weer te geven.

   ![Afbeelding van API-toegang en API-selectie](../../media/apis-in-my-org-tab.PNG)

   - Selecteer **Toepassingsmachtigingen** > Kies de relevante machtigingen voor uw scenario, bijvoorbeeld **incident. Read. all**, en selecteer vervolgens **add machtigingen**.

   ![Afbeelding van API-toegang en API-selectie](../../media/request-api-permissions.PNG)

    >[!NOTE]
    >U moet de relevante machtigingen voor uw scenario selecteren, **' alle incidenten lezen '** is slechts een voorbeeld. Om te bepalen welke machtigingen u nodig hebt, raadpleegt u de sectie **machtigingen** in de API die u wilt bellen.

5. Selecteer **toestemming verlenen**.

     > [!NOTE]
     > Telkens wanneer u een machtiging toevoegt, moet u **toestemming verlenen** om de nieuwe machtiging te activeren.

    ![Afbeelding van machtiging verlenen](../../media/grant-consent.PNG)

6. Als u een geheim wilt toevoegen aan de toepassing, selecteert u **certificaten & geheimen**, voegt u een beschrijving toe aan het geheim en selecteert u vervolgens **toevoegen**.

    > [!NOTE]
    > Wanneer u **toevoegen**hebt geselecteerd, selecteert u **de gegenereerde geheime waarde kopiëren**. U kunt deze waarde niet meer ophalen wanneer u niets hebt.

    ![Afbeelding van de sleutel app maken](../../media/webapp-create-key2.png)

7. Noteer de toepassings-ID en uw Tenant-ID. Ga op de pagina toepassing naar **overzicht** en kopieer de volgende stappen.

   ![Afbeelding van gemaakte app-id](../../media/app-and-tenant-ids.png)

8. **Alleen voor Microsoft Threat Protection-partners**. [Volg de instructies hier](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access). U kunt instellen dat uw app meerdere tenants (beschikbaar na instemming) moet zijn. Dit is **vereist** voor apps van derden (bijvoorbeeld als u een app maakt die bedoeld is om te worden uitgevoerd in de Tenant van meerdere klanten). U **hoeft dit niet te doen** als u een service maakt die u alleen in uw Tenant wilt uitvoeren (als u bijvoorbeeld een toepassing maakt voor uw eigen gebruik, zodat u alleen uw eigen gegevens kunt gebruiken). Uw app instellen voor meerdere tenants:

    - Ga naar **verificatie**en voeg toe https://portal.azure.com als de **omleidings-URL**.

    - Onder aan de pagina, onder **ondersteunde accounttypen**, selecteert u de **accounts in een** toepassing voor de organisatie van de toepassing voor uw app met meerdere tenants.

    U moet uw toepassing in elke Tenant goedgekeurd hebben, waar u deze wilt gebruiken. Dit komt doordat de toepassing Microsoft Threat Protection bijdraagt namens de klant.

    U (of de klant als u een app van derden schrijft), moet u de instemming koppeling selecteren en uw app goedkeuren. De toestemming moet worden uitgevoerd met een gebruiker die beheerdersrechten heeft in Active Directory.

    De koppeling toestemming wordt als volgt gevormd: 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    Waarbij 00000000-0000-0000-0000-000000000000 wordt vervangen door uw toepassings-ID.


**Klaar!** U hebt een toepassing geregistreerd. Zie voorbeelden hieronder voor het verwerving van tokens en validatie.

## <a name="get-an-access-token"></a>Een toegangstoken verkrijgen

Zie voor meer informatie over Azure AD-tokens de [zelfstudie voor Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

### <a name="use-powershell"></a>PowerShell gebruiken

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

### <a name="use-c"></a>Gebruik C#:

De volgende code is getest met Nuget Microsoft. Identity model. clients. ActiveDirectory 3.19.8.

1. Maak een nieuwe consoletoepassing.
1. Installeer Nuget [Microsoft. Identity model. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).
1. Voegt u het volgende toe:

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Kopieer en plak de volgende code in uw app (Vergeet niet de drie variabelen bij te werken: ```tenantId, appId, appSecret``` ):

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a>Python gebruiken 

```
import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```
### <a name="use-curl"></a>Krul gebruiken

> [!NOTE]
> In de volgende procedure wordt ervan uitgegaan dat krul voor Windows al op uw computer is geïnstalleerd.

1. Open een opdrachtprompt en stel CLIENT_ID in op de ID van uw Azure-toepassing.
1. Stel CLIENT_SECRET in op uw Azure-toepassing Secret.
1. Stel TENANT_ID in op de Azure-TENANT-ID van de klant die uw app wil gebruiken om toegang te krijgen tot Microsoft Threat Protection.
1. Voer de volgende opdracht uit:

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

U krijgt een antwoord in de volgende vorm:

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Het token valideren

Zorg ervoor dat u het juiste token hebt:

1. Kopieer en plak het token dat u in de vorige stap hebt [JWT](https://jwt.ms) ontvangen, om dit te decoderen.
1. Controleren of u een claim ontvangt met de gewenste machtigingen
1. In de volgende afbeelding ziet u een versleuteld token dat u hebt verkregen uit een app met ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` en ```AdvancedHunting.Read.All``` machtigingen:

![Afbeelding van validatie van tokens](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-threat-protection-api"></a>Het token gebruiken om toegang te krijgen tot de Microsoft Threat Protection API

1. Kies de API die u wilt gebruiken. Zie voor meer informatie [ondersteunde api's voor Microsoft Threat Protection](api-supported.md).

2. Stel de autorisatie header in voor de HTTP-aanvraag die u verstuurt naar ' Bearer {token} ' (Bearer is het autorisatieschema).

3. De verlooptijd van het token is één uur. U kunt meer dan één aanvraag met hetzelfde token verzenden.

Hieronder ziet u een voorbeeld van het verzenden van een aanvraag voor het aanvragen van een lijst met incidenten **met C#**: 

```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="related-topics"></a>Verwante onderwerpen
- [Toegang tot de Microsoft Threat Protection-Api's](api-access.md)
- [Toegang tot Microsoft Threat Protection met toepassingscontext](api-create-app-web.md)
- [Microsoft Threat Protection met gebruikerscontext openen](api-create-app-user-context.md)
