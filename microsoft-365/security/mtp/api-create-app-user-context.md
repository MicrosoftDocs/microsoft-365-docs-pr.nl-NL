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
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a><span data-ttu-id="2acc4-104">Een app maken om toegang te krijgen tot Microsoft 365 Defender-Api's namens een gebruiker</span><span class="sxs-lookup"><span data-stu-id="2acc4-104">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2acc4-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2acc4-105">**Applies to:**</span></span>

- <span data-ttu-id="2acc4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2acc4-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2acc4-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="2acc4-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2acc4-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="2acc4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="2acc4-109">Op deze pagina wordt beschreven hoe u een toepassing maakt om via een programma toegang te krijgen tot Microsoft 365 Defender namens één gebruiker.</span><span class="sxs-lookup"><span data-stu-id="2acc4-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a single user.</span></span>

<span data-ttu-id="2acc4-110">Zie [een app maken om toegang te krijgen tot Microsoft 365 Defender zonder een gebruiker](api-create-app-web.md)als u via programma toegang wilt hebben tot microsoft 365 Defender zonder een gedefinieerde gebruiker (bijvoorbeeld als u een achtergrond-app of een demon schrijft).</span><span class="sxs-lookup"><span data-stu-id="2acc4-110">If you need programmatic access to Microsoft 365 Defender without a defined user (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="2acc4-111">Zie [een app met partner toegang maken voor Microsoft 365-apps](api-partner-access.md)voor meer informatie over het maken van toegang voor meerdere tenants, bijvoorbeeld als u een grote organisatie of een groep klanten ter beschikking hebt. Als u niet zeker weet welk type toegang u nodig hebt, raadpleegt u [aan de slag](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="2acc4-111">If you need to provide access for multiple tenants—for example, if you're serving a large organization or a group of customers—see [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="2acc4-112">Microsoft 365 Defender geeft veel van zijn gegevens en acties getoond via een set programmeer Api's.</span><span class="sxs-lookup"><span data-stu-id="2acc4-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="2acc4-113">Met deze Api's kunt u werkstromen automatiseren en gebruikmaken van de mogelijkheden van Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="2acc4-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="2acc4-114">Voor deze API-toegang is OAuth 2.0 Authentication vereist.</span><span class="sxs-lookup"><span data-stu-id="2acc4-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="2acc4-115">Voor meer informatie raadpleegt u [OAuth 2,0 Authorization code flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="2acc4-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="2acc4-116">In het algemeen dient u de volgende stappen uit te voeren om deze Api's te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="2acc4-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="2acc4-117">Maak een Azure AD-toepassing (Azure Active Directory).</span><span class="sxs-lookup"><span data-stu-id="2acc4-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="2acc4-118">U krijgt een toegangstoken met deze toepassing.</span><span class="sxs-lookup"><span data-stu-id="2acc4-118">Get an access token using this application.</span></span>
- <span data-ttu-id="2acc4-119">Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="2acc4-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="2acc4-120">In dit artikel wordt uitgelegd hoe u dit kunt doen:</span><span class="sxs-lookup"><span data-stu-id="2acc4-120">This article explains how to:</span></span>

- <span data-ttu-id="2acc4-121">Een Azure AD-toepassing maken</span><span class="sxs-lookup"><span data-stu-id="2acc4-121">Create an Azure AD application</span></span>
- <span data-ttu-id="2acc4-122">Een toegangstoken verkrijgen bij Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2acc4-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="2acc4-123">Het token valideren</span><span class="sxs-lookup"><span data-stu-id="2acc4-123">Validate the token</span></span>

> [!NOTE]
> <span data-ttu-id="2acc4-124">Wanneer u de Microsoft 365-API-API opent namens een gebruiker, hebt u de juiste toepassingsmachtigingen en gebruikersmachtigingen nodig.</span><span class="sxs-lookup"><span data-stu-id="2acc4-124">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct application permissions and user permissions.</span></span>

> [!TIP]
> <span data-ttu-id="2acc4-125">Als u gemachtigd bent om een actie uit te voeren in de portal, hebt u de machtiging om de actie uit te voeren in de API.</span><span class="sxs-lookup"><span data-stu-id="2acc4-125">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="2acc4-126">Een app maken</span><span class="sxs-lookup"><span data-stu-id="2acc4-126">Create an app</span></span>

1. <span data-ttu-id="2acc4-127">Meld u aan bij [Azure](https://portal.azure.com) als een gebruiker met de rol van **globale beheerder** .</span><span class="sxs-lookup"><span data-stu-id="2acc4-127">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="2acc4-128">Ga naar de **Azure Active Directory**-  >  **app registraties**  >  **nieuwe registratie**.</span><span class="sxs-lookup"><span data-stu-id="2acc4-128">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Afbeelding van Microsoft Azure en navigatie naar toepassing registreren](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="2acc4-130">Kies in het formulier een naam voor de toepassing en voer de volgende gegevens voor de omleidings-URL in en selecteer vervolgens **registreren**.</span><span class="sxs-lookup"><span data-stu-id="2acc4-130">In the form, choose a name for your application and enter the following information for the redirect URI, then select **Register**.</span></span>

   ![Afbeelding van het venster toepassing maken](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="2acc4-132">**Type toepassing:** Openbare client</span><span class="sxs-lookup"><span data-stu-id="2acc4-132">**Application type:** Public client</span></span>
   - <span data-ttu-id="2acc4-133">**URI omleiden:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="2acc4-133">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="2acc4-134">Selecteer op de pagina toepassingen de optie **API-machtigingen**  >  **toevoegen**  >  **Mijn organisatie gebruikt** >, typ **Microsoft Threat Protection** en selecteer **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="2acc4-134">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="2acc4-135">Uw app heeft nu toegang tot Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="2acc4-135">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="2acc4-136">*Microsoft Threat Protection* is een voormalig naam voor microsoft 365 Defender en wordt niet weergegeven in de oorspronkelijke lijst.</span><span class="sxs-lookup"><span data-stu-id="2acc4-136">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="2acc4-137">U moet de naam ervan beginnen te schrijven in het tekstvak om de naam weer te geven.</span><span class="sxs-lookup"><span data-stu-id="2acc4-137">You need to start writing its name in the text box to see it appear.</span></span>

   ![Afbeelding van selectie van API-machtigingen](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="2acc4-139">Kies **gedelegeerde machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="2acc4-139">Choose **Delegated permissions**.</span></span> <span data-ttu-id="2acc4-140">Kies de relevante machtigingen voor uw scenario (bijvoorbeeld **incident. Read**) en selecteer vervolgens **machtigingen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="2acc4-140">Choose the relevant permissions for your scenario (for example **Incident.Read**), and then select **Add permissions**.</span></span>

   ![Afbeelding van API-toegang en API-selectie](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > <span data-ttu-id="2acc4-142">U moet de relevante machtigingen voor uw scenario selecteren.</span><span class="sxs-lookup"><span data-stu-id="2acc4-142">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="2acc4-143">*Alle incidenten lezen* is slechts een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="2acc4-143">*Read all incidents* is just an example.</span></span> <span data-ttu-id="2acc4-144">Om te bepalen welke machtigingen u nodig hebt, raadpleegt u de sectie **machtigingen** in de API die u wilt bellen.</span><span class="sxs-lookup"><span data-stu-id="2acc4-144">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="2acc4-145">Als u een [geavanceerde zoek](api-advanced-hunting.md)opdracht wilt uitvoeren, selecteert u de machtiging Geavanceerd query's uitvoeren. Als u [een apparaat wilt isoleren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), selecteert u de machtiging computer isoleren.</span><span class="sxs-lookup"><span data-stu-id="2acc4-145">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

5. <span data-ttu-id="2acc4-146">Selecteer **beheerder toestemming verlenen**.</span><span class="sxs-lookup"><span data-stu-id="2acc4-146">Select **Grant admin consent**.</span></span> <span data-ttu-id="2acc4-147">Telkens wanneer u een machtiging toevoegt, moet u de machtiging **beheerder toestemming verlenen** selecteren om de machtiging van kracht te laten worden.</span><span class="sxs-lookup"><span data-stu-id="2acc4-147">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

   ![Afbeelding van machtiging verlenen](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="2acc4-149">Registreer uw toepassings-ID en uw Tenant-ID ergens veilig.</span><span class="sxs-lookup"><span data-stu-id="2acc4-149">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="2acc4-150">Ze worden weergegeven onder **overzicht** op de pagina toepassing.</span><span class="sxs-lookup"><span data-stu-id="2acc4-150">They're listed under **Overview** on your application page.</span></span>

   ![Afbeelding van gemaakte app-id](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a><span data-ttu-id="2acc4-152">Een toegangstoken verkrijgen</span><span class="sxs-lookup"><span data-stu-id="2acc4-152">Get an access token</span></span>

<span data-ttu-id="2acc4-153">Zie voor meer informatie over Azure Active Directory-tokens de [zelfstudie voor Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="2acc4-153">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="2acc4-154">Een toegangstoken verkrijgen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="2acc4-154">Get an access token using PowerShell</span></span>

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

## <a name="validate-the-token"></a><span data-ttu-id="2acc4-155">Het token valideren</span><span class="sxs-lookup"><span data-stu-id="2acc4-155">Validate the token</span></span>

1. <span data-ttu-id="2acc4-156">Kopieer en plak de token in [JWT](https://jwt.ms) om deze te decoderen.</span><span class="sxs-lookup"><span data-stu-id="2acc4-156">Copy and paste the token into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="2acc4-157">Zorg ervoor dat de *claim claim* binnen het genummerde token de gewenste machtigingen bevat.</span><span class="sxs-lookup"><span data-stu-id="2acc4-157">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="2acc4-158">In de volgende afbeelding ziet u een versleuteld token dat u hebt verkregen uit een app, met ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` en ```AdvancedHunting.Read.All``` machtigingen:</span><span class="sxs-lookup"><span data-stu-id="2acc4-158">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Afbeelding van validatie van tokens](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="2acc4-160">Het token gebruiken voor toegang tot de Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="2acc4-160">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="2acc4-161">Kies de API die u wilt gebruiken (incidenten of geavanceerde jacht).</span><span class="sxs-lookup"><span data-stu-id="2acc4-161">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="2acc4-162">Zie [ondersteunde Microsoft 365 Defender-api's](api-supported.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2acc4-162">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="2acc4-163">In het HTTP-verzoek dat u gaat verzenden, stelt u de autorisatie header in op `"Bearer" <token>` het autorisatieschema en *token* dat uw gevalideerde token is. </span><span class="sxs-lookup"><span data-stu-id="2acc4-163">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="2acc4-164">Het token vervalt binnen één uur.</span><span class="sxs-lookup"><span data-stu-id="2acc4-164">The token will expire within one hour.</span></span> <span data-ttu-id="2acc4-165">U kunt meer dan één verzoek verzenden vanaf dit tijdstip met hetzelfde token.</span><span class="sxs-lookup"><span data-stu-id="2acc4-165">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="2acc4-166">In het volgende voorbeeld ziet u hoe u een aanvraag verzendt voor het aanvragen van een lijst met incidenten **met C#**.</span><span class="sxs-lookup"><span data-stu-id="2acc4-166">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="2acc4-167">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="2acc4-167">Related articles</span></span>

- [<span data-ttu-id="2acc4-168">Overzicht van Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="2acc4-168">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="2acc4-169">Toegang tot de Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="2acc4-169">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="2acc4-170">Een ' Hallo wereld '-app maken</span><span class="sxs-lookup"><span data-stu-id="2acc4-170">Create a 'Hello world' app</span></span>](api-hello-world.md)
- [<span data-ttu-id="2acc4-171">Een app maken om toegang te krijgen tot Microsoft 365 Defender zonder een gebruiker</span><span class="sxs-lookup"><span data-stu-id="2acc4-171">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="2acc4-172">Een app maken met toegang met meerdere tenants voor partners van Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2acc4-172">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="2acc4-173">Meer informatie over API-limieten en licenties</span><span class="sxs-lookup"><span data-stu-id="2acc4-173">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="2acc4-174">Meer informatie over foutcodes</span><span class="sxs-lookup"><span data-stu-id="2acc4-174">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="2acc4-175">OAuth 2,0-autorisatie voor gebruikersaanmelding en API-toegang</span><span class="sxs-lookup"><span data-stu-id="2acc4-175">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
