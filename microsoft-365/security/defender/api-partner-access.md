---
title: Partnertoegang via Api's voor Microsoft 365 Defender
description: Meer informatie over het maken van een app om namens uw gebruikers programmatische toegang te krijgen tot Microsoft 365 Defender.
keywords: partner, access, api, multi tenant, consent, access token, app
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 46876fef8a0279ee350d57fdc85aeced82696656
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057281"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a>Een app maken met partnertoegang tot Microsoft 365 Defender-API's

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden. Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.

Op deze pagina wordt beschreven hoe u een Azure Active Directory-app maakt die programmatische toegang heeft tot Microsoft 365 Defender, namens gebruikers in meerdere tenants. Multi-tenant-apps zijn handig voor het bedienen van grote groepen gebruikers.

Zie Een app maken voor toegang tot Microsoft 365 Defender-API's namens een gebruiker als u programmatische toegang nodig hebt tot [Microsoft 365](api-create-app-user-context.md)Defender. Als u toegang nodig hebt zonder een gebruiker die expliciet is gedefinieerd (bijvoorbeeld als u een achtergrond-app of daemon schrijft), zie Een app maken voor toegang tot [Microsoft 365 Defender](api-create-app-web.md)zonder een gebruiker. Zie Aan de slag als u niet zeker weet welk type toegang u nodig [hebt.](api-access.md)

Microsoft 365 Defender toont een groot deel van de gegevens en acties via een set programmatische API's. Met deze API's kunt u werkstromen automatiseren en gebruikmaken van de mogelijkheden van Microsoft 365 Defender. Voor deze API-toegang is OAuth2.0-verificatie vereist. Zie [OAuth 2.0 Autorisatiecodestroom](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)voor meer informatie.

Over het algemeen moet u de volgende stappen nemen om deze API's te gebruiken:

- Een Azure Active Directory-toepassing (Azure AD) maken.
- Een toegangs token krijgen met deze toepassing.
- Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender-API.

Aangezien deze app multi-tenant is, [](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) hebt u ook beheerdersmachtiging nodig van elke tenant namens de gebruikers.

In dit artikel wordt uitgelegd hoe u:

- Een **Azure AD-toepassing met meerdere tenants** maken
- Krijg geautoriseerde toestemming van uw gebruikerbeheerder voor uw toepassing om toegang te krijgen tot de Microsoft 365 Defender die deze resources nodig heeft.
- Een toegangs token voor Microsoft 365 Defender
- Het token valideren

Microsoft 365 Defender toont een groot deel van de gegevens en acties via een set programmatische API's. Met deze API's kunt u werkstromen automatiseren en innoveren op basis van microsoft 365 Defender-mogelijkheden. Voor de API-toegang is OAuth2.0-verificatie vereist. Zie [OAuth 2.0 Autorisatiecodestroom](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)voor meer informatie.

Over het algemeen moet u de volgende stappen nemen om de API's te gebruiken:

- Maak een **Azure AD-toepassing met** meerdere tenants.
- Ontvang geautoriseerde (toestemming) van uw gebruikerbeheerder voor uw toepassing om toegang te krijgen tot Microsoft 365 Defender-bronnen die nodig zijn.
- Een toegangs token krijgen met deze toepassing.
- Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender-API.

In de volgende stappen vindt u informatie over het maken van een Azure AD-toepassing met meerdere tenants, het openen van een token voor Microsoft 365 Defender en het valideren van het token.

## <a name="create-the-multi-tenant-app"></a>De multi-tenant-app maken

1. Meld u aan [bij Azure](https://portal.azure.com) als gebruiker met de **rol Globale** beheerder.

2. **Navigeer naar Azure Active Directory**  >  **App-registraties** Nieuwe  >  **registratie**.

   ![Afbeelding van Microsoft Azure en navigatie naar toepassingsregistratie](../../media/atp-azure-new-app2.png)

3. In het registratieformulier:

   - Kies een naam voor uw toepassing.
   - Selecteer accounts in **een organisatiemap** **(een Azure AD-adreslijst) - Multitenant in ondersteunde accounttypen.**
   - Vul de sectie **Redirect URI** in. Selecteer Type **Web** en geef de omleidings-URI als **https://portal.azure.com** .

   Nadat u klaar bent met het invullen van het formulier, selecteert u **Registreren.**

   ![Afbeelding van het toepassingsformulier Registreren](../..//media/atp-api-new-app-partner.png)

4. Selecteer op uw **toepassingspagina API-machtigingen** Machtigingen toevoegen Machtiging-API's die mijn organisatie gebruikt  >    >   >, typ **Microsoft Threat Protection** en selecteer Microsoft **Threat Protection.** Uw app heeft nu toegang tot Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection* is een voormalige naam voor Microsoft 365 Defender en wordt niet weergegeven in de oorspronkelijke lijst. U moet beginnen met het schrijven van de naam in het tekstvak om deze weer te geven.

   ![Afbeelding van API-machtigingsselectie](../../media/apis-in-my-org-tab.PNG)

5. Selecteer **Toepassingsmachtigingen.** Kies de relevante machtigingen voor uw scenario (bijvoorbeeld **Incident.Read.All)** en selecteer **vervolgens Machtigingen toevoegen.**

   ![Afbeelding van API-toegang en API-selectie](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > U moet de relevante machtigingen voor uw scenario selecteren. *Alle incidenten lezen* is slechts een voorbeeld. Als u wilt bepalen welke machtiging u nodig hebt, kijkt u naar **de sectie** Machtigingen in de API die u wilt bellen.
    >
    > Als u bijvoorbeeld geavanceerde [query's wilt uitvoeren,](api-advanced-hunting.md)selecteert u de machtiging Geavanceerde query's uitvoeren. als [u een apparaat wilt isoleren,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)selecteert u de machtiging 'Machine isoleren'.

6. Selecteer **Beheerdersmachtiging verlenen.** Telkens wanneer u een machtiging toevoegt, moet u Toestemming van beheerder **verlenen selecteren** om deze van kracht te laten worden.

    ![Afbeelding van machtigingen verlenen](../../media/grant-consent.PNG)

7. Als u een geheim aan de toepassing wilt toevoegen, selecteert u Certificaten **& geheimen,** voegt u een beschrijving toe aan het geheim en selecteert u **Vervolgens Toevoegen**.

    > [!TIP]
    > Nadat u Toevoegen **hebt geselecteerd,** **selecteert u de gegenereerde geheime waarde kopiëren.** U kunt de geheime waarde niet meer ophalen nadat u bent weggehaald.

    ![Afbeelding van app-sleutel maken](../../media/webapp-create-key2.png)

8. Neem uw toepassings-id en uw tenant-id op een veilige plaats op. Ze worden weergegeven onder **Overzicht** op uw toepassingspagina.

   ![Afbeelding van gemaakte app-id](../../media/app-and-tenant-ids.png)

9. Voeg de toepassing toe aan de tenant van uw gebruiker.

   Aangezien uw toepassing namens uw gebruikers samenwerkt met Microsoft 365 Defender, moet deze worden goedgekeurd voor elke tenant waarvoor u deze wilt gebruiken.

   Een **globale beheerder** van de tenant van uw gebruiker moet de toestemmingskoppeling bekijken en uw toepassing goedkeuren.

   De koppeling Toestemming is van het formulier:

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   De cijfers moeten `00000000-0000-0000-0000-000000000000` worden vervangen door uw toepassings-id.

   Nadat u op de toestemmingskoppeling hebt geklikt, meldt u zich aan bij de globale beheerder van de tenant van de gebruiker en stemt u in met de toepassing.

   ![Afbeelding van toestemming](../../media/app-consent-partner.png)

   U moet ook uw gebruiker om zijn of haar tenant-id vragen. De tenant-id is een van de id's die worden gebruikt om toegangstokens te verkrijgen.

- **Klaar!** U hebt een toepassing geregistreerd.
- Zie hieronder voorbeelden voor het verkrijgen en valideren van tokens.

## <a name="get-an-access-token"></a>Een toegangs token krijgen

Zie de [zelfstudie Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)voor meer informatie over Azure AD-tokens.

> [!IMPORTANT]
> Hoewel de voorbeelden in deze sectie u aanmoedigen om geheime waarden te plakken voor testdoeleinden, moet u nooit geheimen **hardcoderen** in een toepassing die in productie wordt uitgevoerd. Een derde partij kan uw geheim gebruiken om toegang te krijgen tot bronnen. U kunt de geheimen van uw app beveiligen met Behulp van [Azure Key Vault.](/azure/key-vault/general/about-keys-secrets-certificates) Zie Geheimen beheren in uw server-apps met Azure Key Vault voor een praktisch voorbeeld van hoe u uw app [kunt beveiligen.](/learn/modules/manage-secrets-with-azure-key-vault/)

> [!TIP]
> Gebruik in de volgende voorbeelden de tenant-id van een gebruiker om te testen of het script werkt.

### <a name="get-an-access-token-using-powershell"></a>Toegangs token krijgen met PowerShell

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

### <a name="get-an-access-token-using-c"></a>Toegangs token krijgen met C\#

> [!NOTE]
> De volgende code is getest met Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.

1. Een nieuwe consoletoepassing maken.
1. Installeer NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).
1. Voeg de volgende regel toe:

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Kopieer en plak de volgende code in uw app (vergeet niet om de drie variabelen bij te werken: `tenantId` , `clientId` , `appSecret` ):

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

### <a name="get-an-access-token-using-python"></a>Toegangs token krijgen met Python

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

### <a name="get-an-access-token-using-curl"></a>Een toegangs token krijgen met behulp van krul

> [!NOTE]
> Curl is vooraf geïnstalleerd op Windows 10, versie 1803 en hoger. Voor andere versies van Windows downloadt en installeert u het hulpprogramma rechtstreeks vanaf de [officiële curl-website.](https://curl.haxx.se/windows/)

1. Open een opdrachtprompt en stel CLIENT_ID in op uw Azure-toepassings-id.
1. Stel CLIENT_SECRET in op uw Azure-toepassingsgeheim.
1. Stel TENANT_ID azure tenant-id in van de gebruiker die uw app wil gebruiken om toegang te krijgen tot Microsoft 365 Defender.
1. Voer de volgende opdracht uit:

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Een succesvol antwoord ziet er als volgende uit:

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Het token valideren

1. Kopieer en plak het token in [de JSON web token validator-website, JWT,](https://jwt.ms) om het te decoderen.
1. Zorg ervoor dat de *claim rollen* in het gedecodeerde token de gewenste machtigingen bevat.

In de volgende afbeelding ziet u een gedecodeerd token dat is verkregen van een app, met ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` , en ```AdvancedHunting.Read.All``` machtigingen:

![Afbeelding van tokenvalidatie](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Het token gebruiken om toegang te krijgen tot de Microsoft 365 Defender-API

1. Kies de API die u wilt gebruiken (incidenten of geavanceerd zoeken). Zie Ondersteunde [Microsoft 365 Defender-API's](api-supported.md)voor meer informatie.
2. Stel in de http-aanvraag die u gaat verzenden de autorisatiekop in op , Bearer is het autorisatieschema en het `"Bearer" <token>` *token*  dat uw gevalideerde token is.
3. Het token verloopt binnen een uur. U kunt in deze periode meerdere aanvragen met hetzelfde token verzenden.

In het volgende voorbeeld ziet u hoe u een aanvraag verzendt om een lijst met incidenten te krijgen **met C#**.

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van Microsoft 365 Defender-API's](api-overview.md)
- [De Microsoft 365 Defender-API's openen](api-access.md)
- [Een 'Hello world'-toepassing maken](api-hello-world.md)
- [Een app maken voor toegang tot Microsoft 365 Defender zonder een gebruiker](api-create-app-web.md)
- [Een app maken voor toegang tot Microsoft 365 Defender-API's namens een gebruiker](api-create-app-user-context.md)
- [Meer informatie over API-limieten en -licenties](api-terms.md)
- [Foutcodes begrijpen](api-error-codes.md)
- [Geheimen beheren in uw server-apps met Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2.0-autorisatie voor gebruikers aanmelden en API-toegang](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)