---
title: Partner toegang via Microsoft 365 Defender-Api's
description: Meer informatie over het maken van een app om via een programma toegang te krijgen tot Microsoft 365 Defender namens uw gebruikers.
keywords: partner, Access, API, multitenant, instemming, toegangstoken, app
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
ms.openlocfilehash: 5de113c8f8419b3af2a287bd7ba7e41dc06b4121
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719438"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a>Een app met partner toegang maken voor Microsoft 365 Defender-Api's

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.

Op deze pagina wordt beschreven hoe u een Azure Active Directory-app maakt met programmatische toegang tot Microsoft 365 Defender, namens gebruikers in meerdere tenants. Apps met meerdere tenants zijn handig voor het fungeren van grote groepen gebruikers.

Zie [een app maken om toegang te krijgen tot Microsoft 365 Defender-api's namens een gebruiker](api-create-app-user-context.md)als u via programma toegang wilt hebben tot microsoft 365 Defender namens één gebruiker. Zie [een app maken om toegang te krijgen tot Microsoft 365 Defender zonder een gebruiker](api-create-app-web.md)als u Access wilt gebruiken zonder dat dit expliciet is gedefinieerd (als u bijvoorbeeld een achtergrond-app of-demon schrijft). Als u niet zeker weet welk type toegang u nodig hebt, raadpleegt u [aan de slag](api-access.md).

Microsoft 365 Defender geeft veel van zijn gegevens en acties getoond via een set programmeer Api's. Met deze Api's kunt u werkstromen automatiseren en gebruikmaken van de mogelijkheden van Microsoft 365 Defender. Voor deze API-toegang is OAuth 2.0 Authentication vereist. Voor meer informatie raadpleegt u [OAuth 2,0 Authorization code flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

In het algemeen dient u de volgende stappen uit te voeren om deze Api's te gebruiken:

- Maak een Azure AD-toepassing (Azure Active Directory).
- U krijgt een toegangstoken met deze toepassing.
- Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender API.

Aangezien deze app een meervoudige Tenant is, moet u ook [beheerders toestemming](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) verlenen voor elke Tenant namens de gebruikers.

In dit artikel wordt uitgelegd hoe u dit kunt doen:

- Een Azure AD-toepassing voor **meerdere tenants** maken
- U kunt toestemming verlenen aan uw gebruikersbeheerder voor uw toepassing om toegang te krijgen tot de Microsoft 365-app die u nodig hebt.
- Een toegangstoken verkrijgen bij Microsoft 365 Defender
- Het token valideren

Microsoft 365 Defender geeft veel van zijn gegevens en acties getoond via een set programmeer Api's. Met deze Api's wordt u geholpen bij het automatiseren van werkstromen en innoveren op basis van de mogelijkheden van Microsoft 365 Defender. Voor API-toegang is OAuth 2.0-authenticatie vereist. Voor meer informatie raadpleegt u [OAuth 2,0 Authorization code flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

In het algemeen dient u de volgende stappen uit te voeren om de Api's te gebruiken:

- Maak een Azure AD-toepassing voor **meerdere tenants** .
- Zorg dat de gebruikersbeheerder van uw toepassing bevoegd is om toegang te krijgen tot de informatie die nodig is voor Microsoft 365 Defender.
- U krijgt een toegangstoken met deze toepassing.
- Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender API.

De volgende stappen uit de handleiding voor het maken van een Azure AD-toepassing voor meerdere tenants: krijg een toegangstoken voor Microsoft 365 Defender en valideer het token.

## <a name="create-the-multi-tenant-app"></a>De app meerdere tenants maken

1. Meld u aan bij [Azure](https://portal.azure.com) als een gebruiker met de rol van **globale beheerder** .

2. Ga naar de **Azure Active Directory**-  >  **app registraties**  >  **nieuwe registratie**.

   ![Afbeelding van Microsoft Azure en navigatie naar toepassing registreren](../../media/atp-azure-new-app2.png)

3. In het registratieformulier:

   - Kies een naam voor uw toepassing.
   - Selecteer voor **ondersteunde accounttypen** **accounts in een willekeurige organisatie Directory (willekeurige Azure AD-Directory): multitenant**.
   - Vul de sectie **omleiding van URI** in. Selecteer **Web** type en geef de omleidings-URL op als **https://portal.azure.com** .

   Wanneer u klaar bent met het invullen van het formulier, selecteert u **registreren**.

   ![Afbeelding van het toepassingsformulier registreren](../..//media/atp-api-new-app-partner.png)

4. Selecteer op de pagina toepassingen de optie **API-machtigingen**  >  **toevoegen**  >  **Mijn organisatie gebruikt** >, typ **Microsoft Threat Protection** en selecteer **Microsoft Threat Protection**. Uw app heeft nu toegang tot Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection* is een voormalig naam voor microsoft 365 Defender en wordt niet weergegeven in de oorspronkelijke lijst. U moet de naam ervan beginnen te schrijven in het tekstvak om de naam weer te geven.

   ![Afbeelding van selectie van API-machtigingen](../../media/apis-in-my-org-tab.PNG)

5. Selecteer **Toepassingsmachtigingen**. Kies de relevante machtigingen voor uw scenario (bijvoorbeeld **incident. Read. all**) en selecteer vervolgens **machtigingen toevoegen**.

   ![Afbeelding van API-toegang en API-selectie](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > U moet de relevante machtigingen voor uw scenario selecteren. *Alle incidenten lezen* is slechts een voorbeeld. Om te bepalen welke machtigingen u nodig hebt, raadpleegt u de sectie **machtigingen** in de API die u wilt bellen.
    >
    > Als u een [geavanceerde zoek](api-advanced-hunting.md)opdracht wilt uitvoeren, selecteert u de machtiging Geavanceerd query's uitvoeren. Als u [een apparaat wilt isoleren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), selecteert u de machtiging computer isoleren.

6. Selecteer **beheerder toestemming verlenen**. Telkens wanneer u een machtiging toevoegt, moet u de machtiging **beheerder toestemming verlenen** selecteren om de machtiging van kracht te laten worden.

    ![Afbeelding van machtiging verlenen](../../media/grant-consent.PNG)

7. Als u een geheim wilt toevoegen aan de toepassing, selecteert u **certificaten & geheimen**, voegt u een beschrijving toe aan het geheim en selecteert u vervolgens **toevoegen**.

    > [!TIP]
    > Wanneer u **toevoegen** hebt geselecteerd, selecteert u **de gegenereerde geheime waarde kopiëren**. U kunt de geheime waarde niet meer ophalen wanneer u niets hebt.

    ![Afbeelding van de sleutel app maken](../../media/webapp-create-key2.png)

8. Registreer uw toepassings-ID en uw Tenant-ID ergens veilig. Ze worden weergegeven onder **overzicht** op de pagina toepassing.

   ![Afbeelding van gemaakte app-id](../../media/app-and-tenant-ids.png)

9. Voeg de toepassing toe aan de Tenant van uw gebruiker.

   Aangezien de toepassing interactie maakt met Microsoft 365 Defender in naam van uw gebruikers, moet deze zijn goedgekeurd voor elke Tenant waarop u de toepassing wilt gebruiken.

   Een **globale beheerder** van de Tenant van uw gebruiker moet de instemming-koppeling bekijken en de toepassing goedkeuren.

   Toestemming koppeling is van het formulier:

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   De cijfers `00000000-0000-0000-0000-000000000000` worden vervangen door uw toepassings-id.

   Nadat u op de koppeling toestemming hebt geklikt, meldt u zich aan met de globale beheerder van de Tenant van de gebruiker en gaat u akkoord met de toepassing.

   ![Afbeelding van instemming](../../media/app-consent-partner.png)

   U moet uw gebruiker ook om een Tenant-ID vragen. De Tenant-ID is een van de id's die worden gebruikt voor het verkrijgen van toegangstokens.

- **Klaar!** U hebt een toepassing geregistreerd.
- Zie voorbeelden hieronder voor het verwerving van tokens en validatie.

## <a name="get-an-access-token"></a>Een toegangstoken verkrijgen

Zie voor meer informatie over Azure AD-tokens de [zelfstudie voor Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

> [!IMPORTANT]
> Hoewel in de voorbeelden in deze sectie wordt voor testdoeleinden geen geheime waarden kunnen worden geplakt, moet u **nooit hardcodee geheimen** verleggen in een toepassing die wordt uitgevoerd in de productie. Een derde partij kon uw geheim gebruiken om toegang te krijgen tot bronnen. U kunt de geheimen van uw apps veilig houden met behulp van [Azure Key-kluis](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates). Zie [geheimen in uw server-apps beheren met Azure-sleutel](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)beveiliging voor een praktisch voorbeeld van de manier waarop u uw app kunt beschermen.

> [!TIP]
> In de volgende voorbeelden kunt u de Tenant-ID van een gebruiker gebruiken om te testen of het script werkt.

### <a name="get-an-access-token-using-powershell"></a>Een toegangstoken verkrijgen met PowerShell

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place!

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

### <a name="get-an-access-token-using-c"></a>Een toegangstoken verkrijgen met C\#

> [!NOTE]
> De volgende code is getest met Nuget Microsoft. Identity model. clients. ActiveDirectory 3.19.8.

1. Maak een nieuwe consoletoepassing.
1. Installeer NuGet [Microsoft. Identity model. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).
1. Voeg de volgende regel toe:

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Kopieer en plak de volgende code in uw app (Vergeet niet de drie variabelen bij te werken: `tenantId` , `clientId` , `appSecret` ):

    ```C#
    string tenantId = ""; // Paste your directory (tenant) ID here
    string clientId = ""; // Paste your application (client) ID here
    string appSecret = ""; // Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(clientId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```

### <a name="get-an-access-token-using-python"></a>Een toegangstoken verkrijgen met python

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : clientId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```

### <a name="get-an-access-token-using-curl"></a>Een toegangstoken verkrijgen met krul

> [!NOTE]
> Krul is vooraf geïnstalleerd op Windows 10, versies 1803 en hoger. Download en installeer het hulpprogramma rechtstreeks vanaf de website van de [officiële krul](https://curl.haxx.se/windows/)voor andere versies van Windows.

1. Open een opdrachtprompt en stel CLIENT_ID in op de ID van uw Azure-toepassing.
1. Stel CLIENT_SECRET in op uw Azure-toepassing Secret.
1. Stel TENANT_ID in op de Azure-TENANT-ID van de gebruiker die de app wil gebruiken voor toegang tot Microsoft 365 Defender.
1. Voer de volgende opdracht uit:

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Een succesvolle reactie ziet er als volgt uit:

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Het token valideren

1. Kopieer de token en plak deze in de [JSON Web token validator-website,](https://jwt.ms) om deze te decoderen.
1. Zorg ervoor dat de *claim claim* binnen het genummerde token de gewenste machtigingen bevat.

In de volgende afbeelding ziet u een versleuteld token dat u hebt verkregen uit een app, met ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` en ```AdvancedHunting.Read.All``` machtigingen:

![Afbeelding van validatie van tokens](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Het token gebruiken voor toegang tot de Microsoft 365 Defender API

1. Kies de API die u wilt gebruiken (incidenten of geavanceerde jacht). Zie [ondersteunde Microsoft 365 Defender-api's](api-supported.md)voor meer informatie.
2. In het HTTP-verzoek dat u gaat verzenden, stelt u de autorisatie header in op `"Bearer" <token>` het autorisatieschema en *token* dat uw gevalideerde token is. 
3. Het token vervalt binnen één uur. U kunt meer dan één verzoek verzenden vanaf dit tijdstip met hetzelfde token.

In het volgende voorbeeld ziet u hoe u een aanvraag verzendt voor het aanvragen van een lijst met incidenten **met C#**.

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van Microsoft 365 Defender-Api's](api-overview.md)
- [Toegang tot de Microsoft 365 Defender-Api's](api-access.md)
- [Een ' Hallo wereld '-toepassing maken](api-hello-world.md)
- [Een app maken om toegang te krijgen tot Microsoft 365 Defender zonder een gebruiker](api-create-app-web.md)
- [Een app maken om toegang te krijgen tot Microsoft 365 Defender-Api's namens een gebruiker](api-create-app-user-context.md)
- [Meer informatie over API-limieten en licenties](api-terms.md)
- [Meer informatie over foutcodes](api-error-codes.md)
- [Geheimen in uw server-apps beheren met Azure-sleutel kluis](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2,0-autorisatie voor gebruikersaanmelding en API-toegang](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
