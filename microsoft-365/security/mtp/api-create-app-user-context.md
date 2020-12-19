---
title: Een app maken om toegang te krijgen tot Microsoft 365 Defender-Api's namens een gebruiker
description: Meer informatie over het openen van Microsoft 365 Defender-Api's namens een gebruiker.
keywords: toegang, in naam van gebruiker, API, toepassing, gebruiker, toegangstoken, token,
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
ms.openlocfilehash: f1c0caea9ff7810f79026c789241a4f250ec5303
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719414"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a>Een app maken om toegang te krijgen tot Microsoft 365 Defender-Api's namens een gebruiker

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.

Op deze pagina wordt beschreven hoe u een toepassing maakt om via een programma toegang te krijgen tot Microsoft 365 Defender namens één gebruiker.

Zie [een app maken om toegang te krijgen tot Microsoft 365 Defender zonder een gebruiker](api-create-app-web.md)als u via programma toegang wilt hebben tot microsoft 365 Defender zonder een gedefinieerde gebruiker (bijvoorbeeld als u een achtergrond-app of een demon schrijft). Zie [een app met partner toegang maken voor Microsoft 365-apps](api-partner-access.md)voor meer informatie over het maken van toegang voor meerdere tenants, bijvoorbeeld als u een grote organisatie of een groep klanten ter beschikking hebt. Als u niet zeker weet welk type toegang u nodig hebt, raadpleegt u [aan de slag](api-access.md).

Microsoft 365 Defender geeft veel van zijn gegevens en acties getoond via een set programmeer Api's. Met deze Api's kunt u werkstromen automatiseren en gebruikmaken van de mogelijkheden van Microsoft 365 Defender. Voor deze API-toegang is OAuth 2.0 Authentication vereist. Voor meer informatie raadpleegt u [OAuth 2,0 Authorization code flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

In het algemeen dient u de volgende stappen uit te voeren om deze Api's te gebruiken:

- Maak een Azure AD-toepassing (Azure Active Directory).
- U krijgt een toegangstoken met deze toepassing.
- Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender API.

In dit artikel wordt uitgelegd hoe u dit kunt doen:

- Een Azure AD-toepassing maken
- Een toegangstoken verkrijgen bij Microsoft 365 Defender
- Het token valideren

> [!NOTE]
> Wanneer u de Microsoft 365-API-API opent namens een gebruiker, hebt u de juiste toepassingsmachtigingen en gebruikersmachtigingen nodig.

> [!TIP]
> Als u gemachtigd bent om een actie uit te voeren in de portal, hebt u de machtiging om de actie uit te voeren in de API.

## <a name="create-an-app"></a>Een app maken

1. Meld u aan bij [Azure](https://portal.azure.com) als een gebruiker met de rol van **globale beheerder** .

2. Ga naar de **Azure Active Directory**-  >  **app registraties**  >  **nieuwe registratie**.

   ![Afbeelding van Microsoft Azure en navigatie naar toepassing registreren](../../media/atp-azure-new-app2.png)

3. Kies in het formulier een naam voor de toepassing en voer de volgende gegevens voor de omleidings-URL in en selecteer vervolgens **registreren**.

   ![Afbeelding van het venster toepassing maken](../../media/nativeapp-create2.PNG)

   - **Type toepassing:** Openbare client
   - **URI omleiden:**https://portal.azure.com

4. Selecteer op de pagina toepassingen de optie **API-machtigingen**  >  **toevoegen**  >  **Mijn organisatie gebruikt** >, typ **Microsoft Threat Protection** en selecteer **Microsoft Threat Protection**. Uw app heeft nu toegang tot Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection* is een voormalig naam voor microsoft 365 Defender en wordt niet weergegeven in de oorspronkelijke lijst. U moet de naam ervan beginnen te schrijven in het tekstvak om de naam weer te geven.

   ![Afbeelding van selectie van API-machtigingen](../../media/apis-in-my-org-tab.PNG)

   - Kies **gedelegeerde machtigingen**. Kies de relevante machtigingen voor uw scenario (bijvoorbeeld **incident. Read**) en selecteer vervolgens **machtigingen toevoegen**.

   ![Afbeelding van API-toegang en API-selectie](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > U moet de relevante machtigingen voor uw scenario selecteren. *Alle incidenten lezen* is slechts een voorbeeld. Om te bepalen welke machtigingen u nodig hebt, raadpleegt u de sectie **machtigingen** in de API die u wilt bellen.
    >
    > Als u een [geavanceerde zoek](api-advanced-hunting.md)opdracht wilt uitvoeren, selecteert u de machtiging Geavanceerd query's uitvoeren. Als u [een apparaat wilt isoleren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), selecteert u de machtiging computer isoleren.

5. Selecteer **beheerder toestemming verlenen**. Telkens wanneer u een machtiging toevoegt, moet u de machtiging **beheerder toestemming verlenen** selecteren om de machtiging van kracht te laten worden.

   ![Afbeelding van machtiging verlenen](../../media/grant-consent-delegated.PNG)

6. Registreer uw toepassings-ID en uw Tenant-ID ergens veilig. Ze worden weergegeven onder **overzicht** op de pagina toepassing.

   ![Afbeelding van gemaakte app-id](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a>Een toegangstoken verkrijgen

Zie voor meer informatie over Azure Active Directory-tokens de [zelfstudie voor Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

### <a name="get-an-access-token-using-powershell"></a>Een toegangstoken verkrijgen met PowerShell

```PowerShell
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps } # Install the ADAL.PS package in case it's not already present

$tenantId = '' # Paste your directory (tenant) ID here.
$clientId = '' # Paste your application (client) ID here.
$redirectUri = '' # Paste your app's redirection URI

$authority = "https://login.windows.net/$tenantId"
$resourceUrl = 'https://api.security.microsoft.com'

$response = Get-ADALToken -Resource $resourceUrl -ClientId $cleintId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip

$response.AccessToken
```

## <a name="validate-the-token"></a>Het token valideren

1. Kopieer en plak de token in [JWT](https://jwt.ms) om deze te decoderen.
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
- [Een ' Hallo wereld '-app maken](api-hello-world.md)
- [Een app maken om toegang te krijgen tot Microsoft 365 Defender zonder een gebruiker](api-create-app-web.md)
- [Een app maken met toegang met meerdere tenants voor partners van Microsoft 365 Defender](api-partner-access.md)
- [Meer informatie over API-limieten en licenties](api-terms.md)
- [Meer informatie over foutcodes](api-error-codes.md)
- [OAuth 2,0-autorisatie voor gebruikersaanmelding en API-toegang](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
