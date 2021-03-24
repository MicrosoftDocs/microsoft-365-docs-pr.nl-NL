---
title: Een app maken voor toegang tot Microsoft 365 Defender-API's namens een gebruiker
description: Meer informatie over het openen van Microsoft 365 Defender-API's namens een gebruiker.
keywords: toegang, namens gebruiker, api, toepassing, gebruiker, toegangs token, token,
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
ms.openlocfilehash: bffe38ff5dc4c11ed25519c86081e24ff1191e94
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060594"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a><span data-ttu-id="74415-104">Een app maken voor toegang tot Microsoft 365 Defender-API's namens een gebruiker</span><span class="sxs-lookup"><span data-stu-id="74415-104">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="74415-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="74415-105">**Applies to:**</span></span>

- <span data-ttu-id="74415-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74415-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74415-107">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="74415-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="74415-108">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="74415-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="74415-109">Op deze pagina wordt beschreven hoe u een toepassing maakt voor programmatische toegang tot Microsoft 365 Defender namens één gebruiker.</span><span class="sxs-lookup"><span data-stu-id="74415-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a single user.</span></span>

<span data-ttu-id="74415-110">Als u programmatische toegang nodig hebt tot Microsoft 365 Defender zonder een gedefinieerde gebruiker (bijvoorbeeld als u een achtergrond-app of daemon schrijft), zie Een app maken voor toegang tot [Microsoft 365 Defender](api-create-app-web.md)zonder een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="74415-110">If you need programmatic access to Microsoft 365 Defender without a defined user (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="74415-111">Zie Een app maken met partnertoegang tot [Microsoft 365 Defender API's](api-partner-access.md)als u toegang wilt bieden voor meerdere tenants, bijvoorbeeld als u een grote organisatie of een groep klanten dient. Zie Aan de slag als u niet zeker weet welk type toegang u nodig [hebt.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="74415-111">If you need to provide access for multiple tenants—for example, if you're serving a large organization or a group of customers—see [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="74415-112">Microsoft 365 Defender toont een groot deel van de gegevens en acties via een set programmatische API's.</span><span class="sxs-lookup"><span data-stu-id="74415-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="74415-113">Met deze API's kunt u werkstromen automatiseren en gebruikmaken van de mogelijkheden van Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="74415-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="74415-114">Voor deze API-toegang is OAuth2.0-verificatie vereist.</span><span class="sxs-lookup"><span data-stu-id="74415-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="74415-115">Zie [OAuth 2.0 Autorisatiecodestroom](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="74415-115">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="74415-116">Over het algemeen moet u de volgende stappen nemen om deze API's te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="74415-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="74415-117">Een Azure Active Directory-toepassing (Azure AD) maken.</span><span class="sxs-lookup"><span data-stu-id="74415-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="74415-118">Een toegangs token krijgen met deze toepassing.</span><span class="sxs-lookup"><span data-stu-id="74415-118">Get an access token using this application.</span></span>
- <span data-ttu-id="74415-119">Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender-API.</span><span class="sxs-lookup"><span data-stu-id="74415-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="74415-120">In dit artikel wordt uitgelegd hoe u:</span><span class="sxs-lookup"><span data-stu-id="74415-120">This article explains how to:</span></span>

- <span data-ttu-id="74415-121">Een Azure AD-toepassing maken</span><span class="sxs-lookup"><span data-stu-id="74415-121">Create an Azure AD application</span></span>
- <span data-ttu-id="74415-122">Een toegangs token voor Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74415-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="74415-123">Het token valideren</span><span class="sxs-lookup"><span data-stu-id="74415-123">Validate the token</span></span>

> [!NOTE]
> <span data-ttu-id="74415-124">Wanneer u namens een gebruiker toegang hebt tot de Microsoft 365 Defender-API, hebt u de juiste machtigingen en gebruikersmachtigingen nodig.</span><span class="sxs-lookup"><span data-stu-id="74415-124">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct application permissions and user permissions.</span></span>

> [!TIP]
> <span data-ttu-id="74415-125">Als u de machtiging hebt om een actie uit te voeren in de portal, hebt u de machtiging om de actie uit te voeren in de API.</span><span class="sxs-lookup"><span data-stu-id="74415-125">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="74415-126">Een app maken</span><span class="sxs-lookup"><span data-stu-id="74415-126">Create an app</span></span>

1. <span data-ttu-id="74415-127">Meld u aan [bij Azure](https://portal.azure.com) als gebruiker met de **rol Globale** beheerder.</span><span class="sxs-lookup"><span data-stu-id="74415-127">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="74415-128">**Navigeer naar Azure Active Directory**  >  **App-registraties** Nieuwe  >  **registratie**.</span><span class="sxs-lookup"><span data-stu-id="74415-128">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Afbeelding van Microsoft Azure en navigatie naar toepassingsregistratie](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="74415-130">Kies in het formulier een naam voor uw toepassing en voer de volgende gegevens in voor de omleidings-URI en selecteer **register.**</span><span class="sxs-lookup"><span data-stu-id="74415-130">In the form, choose a name for your application and enter the following information for the redirect URI, then select **Register**.</span></span>

   ![Afbeelding van toepassingsvenster maken](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="74415-132">**Toepassingstype:** Openbare client</span><span class="sxs-lookup"><span data-stu-id="74415-132">**Application type:** Public client</span></span>
   - <span data-ttu-id="74415-133">**Redirect URI:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="74415-133">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="74415-134">Selecteer op uw **toepassingspagina API-machtigingen** Machtigingen toevoegen Machtiging-API's die mijn organisatie gebruikt  >    >   >, typ **Microsoft Threat Protection** en selecteer Microsoft **Threat Protection.**</span><span class="sxs-lookup"><span data-stu-id="74415-134">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="74415-135">Uw app heeft nu toegang tot Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="74415-135">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="74415-136">*Microsoft Threat Protection* is een voormalige naam voor Microsoft 365 Defender en wordt niet weergegeven in de oorspronkelijke lijst.</span><span class="sxs-lookup"><span data-stu-id="74415-136">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="74415-137">U moet beginnen met het schrijven van de naam in het tekstvak om deze weer te geven.</span><span class="sxs-lookup"><span data-stu-id="74415-137">You need to start writing its name in the text box to see it appear.</span></span>

   ![Afbeelding van API-machtigingsselectie](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="74415-139">Kies **Gedelegeerde machtigingen.**</span><span class="sxs-lookup"><span data-stu-id="74415-139">Choose **Delegated permissions**.</span></span> <span data-ttu-id="74415-140">Kies de relevante machtigingen voor uw scenario (bijvoorbeeld **Incident.Read)** en selecteer **vervolgens Machtigingen toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="74415-140">Choose the relevant permissions for your scenario (for example **Incident.Read**), and then select **Add permissions**.</span></span>

   ![Afbeelding van API-toegang en API-selectie](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > <span data-ttu-id="74415-142">U moet de relevante machtigingen voor uw scenario selecteren.</span><span class="sxs-lookup"><span data-stu-id="74415-142">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="74415-143">*Alle incidenten lezen* is slechts een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="74415-143">*Read all incidents* is just an example.</span></span> <span data-ttu-id="74415-144">Als u wilt bepalen welke machtiging u nodig hebt, kijkt u naar **de sectie** Machtigingen in de API die u wilt bellen.</span><span class="sxs-lookup"><span data-stu-id="74415-144">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="74415-145">Als u bijvoorbeeld geavanceerde [query's wilt uitvoeren,](api-advanced-hunting.md)selecteert u de machtiging Geavanceerde query's uitvoeren. als [u een apparaat wilt isoleren,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)selecteert u de machtiging 'Machine isoleren'.</span><span class="sxs-lookup"><span data-stu-id="74415-145">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

5. <span data-ttu-id="74415-146">Selecteer **Beheerdersmachtiging verlenen.**</span><span class="sxs-lookup"><span data-stu-id="74415-146">Select **Grant admin consent**.</span></span> <span data-ttu-id="74415-147">Telkens wanneer u een machtiging toevoegt, moet u Toestemming van beheerder **verlenen selecteren** om deze van kracht te laten worden.</span><span class="sxs-lookup"><span data-stu-id="74415-147">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

   ![Afbeelding van machtigingen verlenen](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="74415-149">Neem uw toepassings-id en uw tenant-id op een veilige plaats op.</span><span class="sxs-lookup"><span data-stu-id="74415-149">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="74415-150">Ze worden weergegeven onder **Overzicht** op uw toepassingspagina.</span><span class="sxs-lookup"><span data-stu-id="74415-150">They're listed under **Overview** on your application page.</span></span>

   ![Afbeelding van gemaakte app-id](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a><span data-ttu-id="74415-152">Een toegangs token krijgen</span><span class="sxs-lookup"><span data-stu-id="74415-152">Get an access token</span></span>

<span data-ttu-id="74415-153">Zie de [zelfstudie Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)voor meer informatie over Azure Active Directory-tokens.</span><span class="sxs-lookup"><span data-stu-id="74415-153">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="74415-154">Toegangs token krijgen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="74415-154">Get an access token using PowerShell</span></span>

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

## <a name="validate-the-token"></a><span data-ttu-id="74415-155">Het token valideren</span><span class="sxs-lookup"><span data-stu-id="74415-155">Validate the token</span></span>

1. <span data-ttu-id="74415-156">Kopieer en plak het token in [JWT om](https://jwt.ms) het te decoderen.</span><span class="sxs-lookup"><span data-stu-id="74415-156">Copy and paste the token into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="74415-157">Zorg ervoor dat de *claim rollen* in het gedecodeerde token de gewenste machtigingen bevat.</span><span class="sxs-lookup"><span data-stu-id="74415-157">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="74415-158">In de volgende afbeelding ziet u een gedecodeerd token dat is verkregen van een app, met ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` , en ```AdvancedHunting.Read.All``` machtigingen:</span><span class="sxs-lookup"><span data-stu-id="74415-158">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Afbeelding van tokenvalidatie](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="74415-160">Het token gebruiken om toegang te krijgen tot de Microsoft 365 Defender-API</span><span class="sxs-lookup"><span data-stu-id="74415-160">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="74415-161">Kies de API die u wilt gebruiken (incidenten of geavanceerd zoeken).</span><span class="sxs-lookup"><span data-stu-id="74415-161">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="74415-162">Zie Ondersteunde [Microsoft 365 Defender-API's](api-supported.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="74415-162">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="74415-163">Stel in de http-aanvraag die u gaat verzenden de autorisatiekop in op , Bearer is het autorisatieschema en het `"Bearer" <token>` *token*  dat uw gevalideerde token is.</span><span class="sxs-lookup"><span data-stu-id="74415-163">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="74415-164">Het token verloopt binnen een uur.</span><span class="sxs-lookup"><span data-stu-id="74415-164">The token will expire within one hour.</span></span> <span data-ttu-id="74415-165">U kunt in deze periode meerdere aanvragen met hetzelfde token verzenden.</span><span class="sxs-lookup"><span data-stu-id="74415-165">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="74415-166">In het volgende voorbeeld ziet u hoe u een aanvraag verzendt om een lijst met incidenten te krijgen **met C#**.</span><span class="sxs-lookup"><span data-stu-id="74415-166">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="74415-167">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="74415-167">Related articles</span></span>

- [<span data-ttu-id="74415-168">Overzicht van Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="74415-168">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="74415-169">De Microsoft 365 Defender-API's openen</span><span class="sxs-lookup"><span data-stu-id="74415-169">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="74415-170">Een 'Hello world' app maken</span><span class="sxs-lookup"><span data-stu-id="74415-170">Create a 'Hello world' app</span></span>](api-hello-world.md)
- [<span data-ttu-id="74415-171">Een app maken voor toegang tot Microsoft 365 Defender zonder een gebruiker</span><span class="sxs-lookup"><span data-stu-id="74415-171">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="74415-172">Een app maken met partnertoegang voor meerdere tenants tot Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="74415-172">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="74415-173">Meer informatie over API-limieten en -licenties</span><span class="sxs-lookup"><span data-stu-id="74415-173">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="74415-174">Foutcodes begrijpen</span><span class="sxs-lookup"><span data-stu-id="74415-174">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="74415-175">OAuth 2.0-autorisatie voor gebruikers aanmelden en API-toegang</span><span class="sxs-lookup"><span data-stu-id="74415-175">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)