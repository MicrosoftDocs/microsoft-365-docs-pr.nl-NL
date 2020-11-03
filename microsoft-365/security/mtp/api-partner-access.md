---
title: Partner toegang via Microsoft 365 Defender-Api's
description: Meer informatie over het maken van een AAD-toepassing voor het verkrijgen van toegang via een programma voor Microsoft 365 Defender namens uw klanten
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
ms.openlocfilehash: eb40d5d2d82f57be225515ad0aa566038397bbbd
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844982"
---
# <a name="partner-access-through-microsoft-365-defender-apis"></a>Partner toegang via Microsoft 365 Defender-Api's

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

>[!IMPORTANT] 
>Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.


Op deze pagina wordt beschreven hoe u een AAD-toepassing maakt om toegang te krijgen tot Microsoft 365 Defender namens uw klanten via programmering.

Microsoft 365 Defender geeft veel van zijn gegevens en acties getoond via een set programmeer Api's. Met deze Api's wordt u geholpen bij het automatiseren van werkstromen en innoveren op basis van de mogelijkheden van Microsoft 365 Defender. Voor API-toegang is OAuth 2.0-authenticatie vereist. Voor meer informatie raadpleegt u [OAuth 2,0 Authorization code flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

In het algemeen dient u de volgende stappen uit te voeren om de Api's te gebruiken:
- Maak een Aad-toepassing van **meerdere tenants** .
- Neem geautoriseerd (instemming) door de beheerder van uw klant voor uw toepassing om toegang te krijgen tot de informatie die nodig is voor Microsoft 365.
- U krijgt een toegangstoken met deze toepassing.
- Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender API.

De volgende stappen uit de handleiding voor het maken van een AAD-toepassing: krijg een toegangstoken aan Microsoft 365 Defender en valideer het token.

## <a name="create-the-multi-tenant-app"></a>De app meerdere tenants maken

1. Meld u aan bij uw [Azure-Tenant](https://portal.azure.com) met een gebruiker met een **globale beheerdersrol** .

2. Ga naar de **Azure Active Directory** -  >  **app registraties**  >  **nieuwe registratie**. 

   ![Afbeelding van Microsoft Azure en navigatie naar toepassing registreren](../../media/atp-azure-new-app2.png)

3. In het registratieformulier:

    - Kies een naam voor uw toepassing.

    - Ondersteunde accounttypen: accounts in een willekeurige organisatie Directory.

    - URI-type omleiden: Web, URI: https://portal.azure.com

    ![Afbeelding van registratie van Microsoft Azure-partner toepassing](../../media/atp-api-new-app-partner.png)


4. Zorg dat uw toepassing toegang heeft tot Microsoft 365 Defender en wijs dit toe aan de minimaal vereiste machtigingen om de integratie te voltooien.

   - Klik op de pagina van de toepassing op **API-machtigingen** voor het toevoegen van een  >  **machtiging** voor  >  **Mijn organisatie** > type **Microsoft 365 Defender** en klik op **Microsoft 365 Defender**.

   >[!NOTE]
   >Microsoft 365 Defender wordt niet weergegeven in de oorspronkelijke lijst. U moet de naam ervan beginnen te schrijven in het tekstvak om de naam weer te geven.

   ![Afbeelding van API-toegang en API-selectie](../../media/apis-in-my-org-tab.PNG)
   
   ### <a name="request-api-permissions"></a>API-machtigingen aanvragen

   Om te bepalen welke machtigingen u nodig hebt, raadpleegt u de sectie **machtigingen** in de API die u wilt bellen. 

   In het volgende voorbeeld gebruiken we de machtiging **alle incidenten lezen** :

   Kies **Application permissions**  >  **incidenten. als... lezen. alle** > Klik op **machtigingen toevoegen**

   ![Afbeelding van API-toegang en API-selectie](../../media/request-api-permissions.PNG)


5. Klik op **toestemming verlenen**

    >[!NOTE]
    >Telkens wanneer u toestemming toevoegt, moet u op **toestemming verlenen** om de nieuwe machtiging van kracht te laten worden.

    ![Afbeelding van machtiging verlenen](../../media/grant-consent.PNG)

6. Voeg een geheim toe aan de toepassing.

    - Klik op **certificaten & geheimen** , voeg een beschrijving toe aan het geheim en klik op **toevoegen**.

    >[!IMPORTANT]
    > Nadat u **toevoegen** hebt geselecteerd, **kopieert u de gegenereerde geheime waarde**. Wanneer u niets kunt terughalen.

    ![Afbeelding van de sleutel app maken](../../media/webapp-create-key2.png)

7. Noteer de toepassings-ID:

   - Ga op de pagina toepassing naar **overzicht** en kopieer de volgende opties:

   ![Afbeelding van gemaakte app-id](../../media/app-id.png)

8. Voeg de toepassing toe aan de Tenant van uw klant.

    U moet uw aanvraag in elke Tenant van de klant goedkeuren, waarbij u deze wilt gebruiken. Dit komt doordat de toepassing wordt uitgevoerd met de Microsoft 365-app voor uw klant namens de klant.

    Een gebruiker met een **globale beheerder** van de Tenant van uw klant moet op de koppeling naar de toestemming klikken en de toepassing goedkeuren.

    Toestemming koppeling is van het formulier:

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    Wanneer 00000000-0000-0000-0000-000000000000 moet worden vervangen door uw toepassings-ID

    Nadat u op de koppeling toestemming hebt geklikt, meldt u zich aan met de hoofdbeheerder van de Tenant van de klant en gaat u akkoord met de toepassing.

    ![Afbeelding van instemming](../../media/app-consent-partner.png)

    Daarnaast moet u uw klant vragen voor hun Tenant-ID en deze opslaan voor toekomstig gebruik tijdens het verkrijgen van het token.

- **Klaar!** U hebt een toepassing geregistreerd. 
- Zie voorbeelden hieronder voor het verwerving van tokens en validatie.

## <a name="get-an-access-token-examples"></a>Een voorbeeld van een toegangstoken verkrijgen:

>[!NOTE]
> Als u namens de klant toegangstoken wilt verkrijgen, gebruikt u de Tenant-ID van de klant bij de volgende token verwervingen.

<br>Raadpleeg voor meer informatie over AAD-tokens [zelfstudie](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="using-powershell"></a>PowerShell gebruiken

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

### <a name="using-c"></a>Met C#:

>De onderstaande code is getest met Nuget Microsoft. Identity model. clients. ActiveDirectory

- Een nieuwe console toepassing maken
- Nuget [Microsoft. Identity model. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) installeren
- Onderstaande invoegtoepassing gebruiken

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

- Kopieer en plak de onderstaande code in de toepassing (Vergeet niet de drie variabelen bij te werken: ```tenantId, appId, appSecret``` )

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string mtpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(mtpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```



### <a name="using-curl"></a>Werken met krul

> [!NOTE]
> De onderstaande procedure, krul voor Windows is al geïnstalleerd op de computer

- Een opdrachtvenster openen
- CLIENT_ID instellen op uw Azure-toepassings-ID
- CLIENT_SECRET instellen op uw Azure-toepassing Secret
- TENANT_ID instellen voor de Azure-TENANT-ID van de klant die de toepassing wil gebruiken voor toegang tot de Microsoft 365-app
- Voer de onderstaande opdracht uit:

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

U krijgt het volgende antwoord van het formulier:

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Het token valideren

Sanity Controleer of u het juiste token hebt:

- Kopiëren/ [plakken het token](https://jwt.ms) dat u in de vorige stap ontvangt om dit te decoderen
- Valideren dat u de claim ' roles ' ontvangt met de gewenste machtigingen
- In de onderstaande schermafbeelding ziet u een versleuteld token dat u hebt verkregen van een toepassing met meerdere rechten voor Microsoft 365 Defender:
- De ' TID ' claim is de Tenant-ID waarvan het token deel uitmaakt.

![Afbeelding van validatie van tokens](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-365-defender-api"></a>Het token gebruiken om toegang te krijgen tot de Microsoft 365 Defender API

- Kies de API die u wilt gebruiken voor meer informatie. [ondersteunde Microsoft 365 Defender-api's](api-supported.md)
- Stel de autorisatie header in op de HTTP-aanvraag die u verstuurt naar ' Bearer {token} ' (Bearer is het autorisatieschema).
- De verlooptijd van het token is 1 uur (u kunt meer dan één aanvraag met hetzelfde token verzenden)

- Voorbeeld van het verzenden van een aanvraag voor het opvragen van een lijst met incidenten **met C#** 
    ```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="related-topics"></a>Verwante onderwerpen 

- [Toegang tot de Microsoft 365 Defender-Api's](api-access.md)
- [Toegang tot Microsoft 365 Defender met toepassingscontext](api-create-app-web.md)
- [Toegang tot Microsoft 365 Defender met gebruikerscontext](api-create-app-user-context.md)
