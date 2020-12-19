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
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a><span data-ttu-id="8322f-104">Een app met partner toegang maken voor Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="8322f-104">Create an app with partner access to Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8322f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8322f-105">**Applies to:**</span></span>

- <span data-ttu-id="8322f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8322f-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8322f-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="8322f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8322f-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="8322f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="8322f-109">Op deze pagina wordt beschreven hoe u een Azure Active Directory-app maakt met programmatische toegang tot Microsoft 365 Defender, namens gebruikers in meerdere tenants.</span><span class="sxs-lookup"><span data-stu-id="8322f-109">This page describes how to create an Azure Active Directory app that has programmatic access to Microsoft 365 Defender, on behalf of users across multiple tenants.</span></span> <span data-ttu-id="8322f-110">Apps met meerdere tenants zijn handig voor het fungeren van grote groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="8322f-110">Multi-tenant apps are useful for serving large groups of users.</span></span>

<span data-ttu-id="8322f-111">Zie [een app maken om toegang te krijgen tot Microsoft 365 Defender-api's namens een gebruiker](api-create-app-user-context.md)als u via programma toegang wilt hebben tot microsoft 365 Defender namens één gebruiker.</span><span class="sxs-lookup"><span data-stu-id="8322f-111">If you need programmatic access to Microsoft 365 Defender on behalf of a single user, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md).</span></span> <span data-ttu-id="8322f-112">Zie [een app maken om toegang te krijgen tot Microsoft 365 Defender zonder een gebruiker](api-create-app-web.md)als u Access wilt gebruiken zonder dat dit expliciet is gedefinieerd (als u bijvoorbeeld een achtergrond-app of-demon schrijft).</span><span class="sxs-lookup"><span data-stu-id="8322f-112">If you need access without a user explicitly defined (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="8322f-113">Als u niet zeker weet welk type toegang u nodig hebt, raadpleegt u [aan de slag](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="8322f-113">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="8322f-114">Microsoft 365 Defender geeft veel van zijn gegevens en acties getoond via een set programmeer Api's.</span><span class="sxs-lookup"><span data-stu-id="8322f-114">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="8322f-115">Met deze Api's kunt u werkstromen automatiseren en gebruikmaken van de mogelijkheden van Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8322f-115">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="8322f-116">Voor deze API-toegang is OAuth 2.0 Authentication vereist.</span><span class="sxs-lookup"><span data-stu-id="8322f-116">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="8322f-117">Voor meer informatie raadpleegt u [OAuth 2,0 Authorization code flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="8322f-117">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="8322f-118">In het algemeen dient u de volgende stappen uit te voeren om deze Api's te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="8322f-118">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="8322f-119">Maak een Azure AD-toepassing (Azure Active Directory).</span><span class="sxs-lookup"><span data-stu-id="8322f-119">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="8322f-120">U krijgt een toegangstoken met deze toepassing.</span><span class="sxs-lookup"><span data-stu-id="8322f-120">Get an access token using this application.</span></span>
- <span data-ttu-id="8322f-121">Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="8322f-121">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="8322f-122">Aangezien deze app een meervoudige Tenant is, moet u ook [beheerders toestemming](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) verlenen voor elke Tenant namens de gebruikers.</span><span class="sxs-lookup"><span data-stu-id="8322f-122">Since this app is multi-tenant, you'll also need [admin consent](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) from each tenant on behalf of its users.</span></span>

<span data-ttu-id="8322f-123">In dit artikel wordt uitgelegd hoe u dit kunt doen:</span><span class="sxs-lookup"><span data-stu-id="8322f-123">This article explains how to:</span></span>

- <span data-ttu-id="8322f-124">Een Azure AD-toepassing voor **meerdere tenants** maken</span><span class="sxs-lookup"><span data-stu-id="8322f-124">Create a **multi-tenant** Azure AD application</span></span>
- <span data-ttu-id="8322f-125">U kunt toestemming verlenen aan uw gebruikersbeheerder voor uw toepassing om toegang te krijgen tot de Microsoft 365-app die u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="8322f-125">Get authorized consent from your user administrator for your application to access the Microsoft 365 Defender that resources it needs.</span></span>
- <span data-ttu-id="8322f-126">Een toegangstoken verkrijgen bij Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8322f-126">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="8322f-127">Het token valideren</span><span class="sxs-lookup"><span data-stu-id="8322f-127">Validate the token</span></span>

<span data-ttu-id="8322f-128">Microsoft 365 Defender geeft veel van zijn gegevens en acties getoond via een set programmeer Api's.</span><span class="sxs-lookup"><span data-stu-id="8322f-128">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="8322f-129">Met deze Api's wordt u geholpen bij het automatiseren van werkstromen en innoveren op basis van de mogelijkheden van Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8322f-129">Those APIs will help you automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="8322f-130">Voor API-toegang is OAuth 2.0-authenticatie vereist.</span><span class="sxs-lookup"><span data-stu-id="8322f-130">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="8322f-131">Voor meer informatie raadpleegt u [OAuth 2,0 Authorization code flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="8322f-131">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="8322f-132">In het algemeen dient u de volgende stappen uit te voeren om de Api's te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="8322f-132">In general, you’ll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="8322f-133">Maak een Azure AD-toepassing voor **meerdere tenants** .</span><span class="sxs-lookup"><span data-stu-id="8322f-133">Create a **multi-tenant** Azure AD application.</span></span>
- <span data-ttu-id="8322f-134">Zorg dat de gebruikersbeheerder van uw toepassing bevoegd is om toegang te krijgen tot de informatie die nodig is voor Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8322f-134">Get authorized (consent) by your user administrator for your application to access Microsoft 365 Defender resources it needs.</span></span>
- <span data-ttu-id="8322f-135">U krijgt een toegangstoken met deze toepassing.</span><span class="sxs-lookup"><span data-stu-id="8322f-135">Get an access token using this application.</span></span>
- <span data-ttu-id="8322f-136">Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="8322f-136">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="8322f-137">De volgende stappen uit de handleiding voor het maken van een Azure AD-toepassing voor meerdere tenants: krijg een toegangstoken voor Microsoft 365 Defender en valideer het token.</span><span class="sxs-lookup"><span data-stu-id="8322f-137">The following steps with guide you how to create a multi-tenant Azure AD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="8322f-138">De app meerdere tenants maken</span><span class="sxs-lookup"><span data-stu-id="8322f-138">Create the multi-tenant app</span></span>

1. <span data-ttu-id="8322f-139">Meld u aan bij [Azure](https://portal.azure.com) als een gebruiker met de rol van **globale beheerder** .</span><span class="sxs-lookup"><span data-stu-id="8322f-139">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="8322f-140">Ga naar de **Azure Active Directory**-  >  **app registraties**  >  **nieuwe registratie**.</span><span class="sxs-lookup"><span data-stu-id="8322f-140">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Afbeelding van Microsoft Azure en navigatie naar toepassing registreren](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="8322f-142">In het registratieformulier:</span><span class="sxs-lookup"><span data-stu-id="8322f-142">In the registration form:</span></span>

   - <span data-ttu-id="8322f-143">Kies een naam voor uw toepassing.</span><span class="sxs-lookup"><span data-stu-id="8322f-143">Choose a name for your application.</span></span>
   - <span data-ttu-id="8322f-144">Selecteer voor **ondersteunde accounttypen** **accounts in een willekeurige organisatie Directory (willekeurige Azure AD-Directory): multitenant**.</span><span class="sxs-lookup"><span data-stu-id="8322f-144">From **Supported account types**, select **Accounts in any organizational directory (Any Azure AD directory) - Multitenant**.</span></span>
   - <span data-ttu-id="8322f-145">Vul de sectie **omleiding van URI** in.</span><span class="sxs-lookup"><span data-stu-id="8322f-145">Fill out the **Redirect URI** section.</span></span> <span data-ttu-id="8322f-146">Selecteer **Web** type en geef de omleidings-URL op als **https://portal.azure.com** .</span><span class="sxs-lookup"><span data-stu-id="8322f-146">Select type **Web** and give the redirect URI as **https://portal.azure.com**.</span></span>

   <span data-ttu-id="8322f-147">Wanneer u klaar bent met het invullen van het formulier, selecteert u **registreren**.</span><span class="sxs-lookup"><span data-stu-id="8322f-147">After you're done filling out the form, select **Register**.</span></span>

   ![Afbeelding van het toepassingsformulier registreren](../..//media/atp-api-new-app-partner.png)

4. <span data-ttu-id="8322f-149">Selecteer op de pagina toepassingen de optie **API-machtigingen**  >  **toevoegen**  >  **Mijn organisatie gebruikt** >, typ **Microsoft Threat Protection** en selecteer **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="8322f-149">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="8322f-150">Uw app heeft nu toegang tot Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8322f-150">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="8322f-151">*Microsoft Threat Protection* is een voormalig naam voor microsoft 365 Defender en wordt niet weergegeven in de oorspronkelijke lijst.</span><span class="sxs-lookup"><span data-stu-id="8322f-151">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="8322f-152">U moet de naam ervan beginnen te schrijven in het tekstvak om de naam weer te geven.</span><span class="sxs-lookup"><span data-stu-id="8322f-152">You need to start writing its name in the text box to see it appear.</span></span>

   ![Afbeelding van selectie van API-machtigingen](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="8322f-154">Selecteer **Toepassingsmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="8322f-154">Select **Application permissions**.</span></span> <span data-ttu-id="8322f-155">Kies de relevante machtigingen voor uw scenario (bijvoorbeeld **incident. Read. all**) en selecteer vervolgens **machtigingen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8322f-155">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![Afbeelding van API-toegang en API-selectie](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="8322f-157">U moet de relevante machtigingen voor uw scenario selecteren.</span><span class="sxs-lookup"><span data-stu-id="8322f-157">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="8322f-158">*Alle incidenten lezen* is slechts een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="8322f-158">*Read all incidents* is just an example.</span></span> <span data-ttu-id="8322f-159">Om te bepalen welke machtigingen u nodig hebt, raadpleegt u de sectie **machtigingen** in de API die u wilt bellen.</span><span class="sxs-lookup"><span data-stu-id="8322f-159">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="8322f-160">Als u een [geavanceerde zoek](api-advanced-hunting.md)opdracht wilt uitvoeren, selecteert u de machtiging Geavanceerd query's uitvoeren. Als u [een apparaat wilt isoleren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), selecteert u de machtiging computer isoleren.</span><span class="sxs-lookup"><span data-stu-id="8322f-160">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="8322f-161">Selecteer **beheerder toestemming verlenen**.</span><span class="sxs-lookup"><span data-stu-id="8322f-161">Select **Grant admin consent**.</span></span> <span data-ttu-id="8322f-162">Telkens wanneer u een machtiging toevoegt, moet u de machtiging **beheerder toestemming verlenen** selecteren om de machtiging van kracht te laten worden.</span><span class="sxs-lookup"><span data-stu-id="8322f-162">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Afbeelding van machtiging verlenen](../../media/grant-consent.PNG)

7. <span data-ttu-id="8322f-164">Als u een geheim wilt toevoegen aan de toepassing, selecteert u **certificaten & geheimen**, voegt u een beschrijving toe aan het geheim en selecteert u vervolgens **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8322f-164">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="8322f-165">Wanneer u **toevoegen** hebt geselecteerd, selecteert u **de gegenereerde geheime waarde kopiëren**.</span><span class="sxs-lookup"><span data-stu-id="8322f-165">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="8322f-166">U kunt de geheime waarde niet meer ophalen wanneer u niets hebt.</span><span class="sxs-lookup"><span data-stu-id="8322f-166">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Afbeelding van de sleutel app maken](../../media/webapp-create-key2.png)

8. <span data-ttu-id="8322f-168">Registreer uw toepassings-ID en uw Tenant-ID ergens veilig.</span><span class="sxs-lookup"><span data-stu-id="8322f-168">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="8322f-169">Ze worden weergegeven onder **overzicht** op de pagina toepassing.</span><span class="sxs-lookup"><span data-stu-id="8322f-169">They're listed under **Overview** on your application page.</span></span>

   ![Afbeelding van gemaakte app-id](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="8322f-171">Voeg de toepassing toe aan de Tenant van uw gebruiker.</span><span class="sxs-lookup"><span data-stu-id="8322f-171">Add the application to your user's tenant.</span></span>

   <span data-ttu-id="8322f-172">Aangezien de toepassing interactie maakt met Microsoft 365 Defender in naam van uw gebruikers, moet deze zijn goedgekeurd voor elke Tenant waarop u de toepassing wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8322f-172">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

   <span data-ttu-id="8322f-173">Een **globale beheerder** van de Tenant van uw gebruiker moet de instemming-koppeling bekijken en de toepassing goedkeuren.</span><span class="sxs-lookup"><span data-stu-id="8322f-173">A **Global Administrator** from your user's tenant needs to view the consent link and approve your application.</span></span>

   <span data-ttu-id="8322f-174">Toestemming koppeling is van het formulier:</span><span class="sxs-lookup"><span data-stu-id="8322f-174">Consent link is of the form:</span></span>

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   <span data-ttu-id="8322f-175">De cijfers `00000000-0000-0000-0000-000000000000` worden vervangen door uw toepassings-id.</span><span class="sxs-lookup"><span data-stu-id="8322f-175">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>

   <span data-ttu-id="8322f-176">Nadat u op de koppeling toestemming hebt geklikt, meldt u zich aan met de globale beheerder van de Tenant van de gebruiker en gaat u akkoord met de toepassing.</span><span class="sxs-lookup"><span data-stu-id="8322f-176">After clicking on the consent link, sign in with the Global Administrator of the user's tenant and consent the application.</span></span>

   ![Afbeelding van instemming](../../media/app-consent-partner.png)

   <span data-ttu-id="8322f-178">U moet uw gebruiker ook om een Tenant-ID vragen.</span><span class="sxs-lookup"><span data-stu-id="8322f-178">You'll also need to ask your user for their tenant ID.</span></span> <span data-ttu-id="8322f-179">De Tenant-ID is een van de id's die worden gebruikt voor het verkrijgen van toegangstokens.</span><span class="sxs-lookup"><span data-stu-id="8322f-179">The tenant ID is one of the identifiers used to acquire access tokens.</span></span>

- <span data-ttu-id="8322f-180">**Klaar!**</span><span class="sxs-lookup"><span data-stu-id="8322f-180">**Done!**</span></span> <span data-ttu-id="8322f-181">U hebt een toepassing geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="8322f-181">You've successfully registered an application!</span></span>
- <span data-ttu-id="8322f-182">Zie voorbeelden hieronder voor het verwerving van tokens en validatie.</span><span class="sxs-lookup"><span data-stu-id="8322f-182">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="8322f-183">Een toegangstoken verkrijgen</span><span class="sxs-lookup"><span data-stu-id="8322f-183">Get an access token</span></span>

<span data-ttu-id="8322f-184">Zie voor meer informatie over Azure AD-tokens de [zelfstudie voor Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="8322f-184">For more information on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8322f-185">Hoewel in de voorbeelden in deze sectie wordt voor testdoeleinden geen geheime waarden kunnen worden geplakt, moet u **nooit hardcodee geheimen** verleggen in een toepassing die wordt uitgevoerd in de productie.</span><span class="sxs-lookup"><span data-stu-id="8322f-185">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="8322f-186">Een derde partij kon uw geheim gebruiken om toegang te krijgen tot bronnen.</span><span class="sxs-lookup"><span data-stu-id="8322f-186">A third party could use your secret to access resources.</span></span> <span data-ttu-id="8322f-187">U kunt de geheimen van uw apps veilig houden met behulp van [Azure Key-kluis](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span><span class="sxs-lookup"><span data-stu-id="8322f-187">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="8322f-188">Zie [geheimen in uw server-apps beheren met Azure-sleutel](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)beveiliging voor een praktisch voorbeeld van de manier waarop u uw app kunt beschermen.</span><span class="sxs-lookup"><span data-stu-id="8322f-188">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

> [!TIP]
> <span data-ttu-id="8322f-189">In de volgende voorbeelden kunt u de Tenant-ID van een gebruiker gebruiken om te testen of het script werkt.</span><span class="sxs-lookup"><span data-stu-id="8322f-189">In the following examples, use a user's tenant ID to test that the script is working.</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="8322f-190">Een toegangstoken verkrijgen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="8322f-190">Get an access token using PowerShell</span></span>

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

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="8322f-191">Een toegangstoken verkrijgen met C\#</span><span class="sxs-lookup"><span data-stu-id="8322f-191">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="8322f-192">De volgende code is getest met Nuget Microsoft. Identity model. clients. ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="8322f-192">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="8322f-193">Maak een nieuwe consoletoepassing.</span><span class="sxs-lookup"><span data-stu-id="8322f-193">Create a new console application.</span></span>
1. <span data-ttu-id="8322f-194">Installeer NuGet [Microsoft. Identity model. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="8322f-194">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="8322f-195">Voeg de volgende regel toe:</span><span class="sxs-lookup"><span data-stu-id="8322f-195">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="8322f-196">Kopieer en plak de volgende code in uw app (Vergeet niet de drie variabelen bij te werken: `tenantId` , `clientId` , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="8322f-196">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

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

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="8322f-197">Een toegangstoken verkrijgen met python</span><span class="sxs-lookup"><span data-stu-id="8322f-197">Get an access token using Python</span></span>

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

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="8322f-198">Een toegangstoken verkrijgen met krul</span><span class="sxs-lookup"><span data-stu-id="8322f-198">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="8322f-199">Krul is vooraf geïnstalleerd op Windows 10, versies 1803 en hoger.</span><span class="sxs-lookup"><span data-stu-id="8322f-199">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="8322f-200">Download en installeer het hulpprogramma rechtstreeks vanaf de website van de [officiële krul](https://curl.haxx.se/windows/)voor andere versies van Windows.</span><span class="sxs-lookup"><span data-stu-id="8322f-200">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="8322f-201">Open een opdrachtprompt en stel CLIENT_ID in op de ID van uw Azure-toepassing.</span><span class="sxs-lookup"><span data-stu-id="8322f-201">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="8322f-202">Stel CLIENT_SECRET in op uw Azure-toepassing Secret.</span><span class="sxs-lookup"><span data-stu-id="8322f-202">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="8322f-203">Stel TENANT_ID in op de Azure-TENANT-ID van de gebruiker die de app wil gebruiken voor toegang tot Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8322f-203">Set TENANT_ID to the Azure tenant ID of the user that wants to use your app to access Microsoft 365 Defender.</span></span>
1. <span data-ttu-id="8322f-204">Voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="8322f-204">Run the following command:</span></span>

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="8322f-205">Een succesvolle reactie ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="8322f-205">A successful response will look like this:</span></span>

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="8322f-206">Het token valideren</span><span class="sxs-lookup"><span data-stu-id="8322f-206">Validate the token</span></span>

1. <span data-ttu-id="8322f-207">Kopieer de token en plak deze in de [JSON Web token validator-website,](https://jwt.ms) om deze te decoderen.</span><span class="sxs-lookup"><span data-stu-id="8322f-207">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="8322f-208">Zorg ervoor dat de *claim claim* binnen het genummerde token de gewenste machtigingen bevat.</span><span class="sxs-lookup"><span data-stu-id="8322f-208">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="8322f-209">In de volgende afbeelding ziet u een versleuteld token dat u hebt verkregen uit een app, met ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` en ```AdvancedHunting.Read.All``` machtigingen:</span><span class="sxs-lookup"><span data-stu-id="8322f-209">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Afbeelding van validatie van tokens](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="8322f-211">Het token gebruiken voor toegang tot de Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="8322f-211">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="8322f-212">Kies de API die u wilt gebruiken (incidenten of geavanceerde jacht).</span><span class="sxs-lookup"><span data-stu-id="8322f-212">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="8322f-213">Zie [ondersteunde Microsoft 365 Defender-api's](api-supported.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8322f-213">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="8322f-214">In het HTTP-verzoek dat u gaat verzenden, stelt u de autorisatie header in op `"Bearer" <token>` het autorisatieschema en *token* dat uw gevalideerde token is. </span><span class="sxs-lookup"><span data-stu-id="8322f-214">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="8322f-215">Het token vervalt binnen één uur.</span><span class="sxs-lookup"><span data-stu-id="8322f-215">The token will expire within one hour.</span></span> <span data-ttu-id="8322f-216">U kunt meer dan één verzoek verzenden vanaf dit tijdstip met hetzelfde token.</span><span class="sxs-lookup"><span data-stu-id="8322f-216">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="8322f-217">In het volgende voorbeeld ziet u hoe u een aanvraag verzendt voor het aanvragen van een lijst met incidenten **met C#**.</span><span class="sxs-lookup"><span data-stu-id="8322f-217">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="8322f-218">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="8322f-218">Related articles</span></span>

- [<span data-ttu-id="8322f-219">Overzicht van Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="8322f-219">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="8322f-220">Toegang tot de Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="8322f-220">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="8322f-221">Een ' Hallo wereld '-toepassing maken</span><span class="sxs-lookup"><span data-stu-id="8322f-221">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="8322f-222">Een app maken om toegang te krijgen tot Microsoft 365 Defender zonder een gebruiker</span><span class="sxs-lookup"><span data-stu-id="8322f-222">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="8322f-223">Een app maken om toegang te krijgen tot Microsoft 365 Defender-Api's namens een gebruiker</span><span class="sxs-lookup"><span data-stu-id="8322f-223">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="8322f-224">Meer informatie over API-limieten en licenties</span><span class="sxs-lookup"><span data-stu-id="8322f-224">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="8322f-225">Meer informatie over foutcodes</span><span class="sxs-lookup"><span data-stu-id="8322f-225">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="8322f-226">Geheimen in uw server-apps beheren met Azure-sleutel kluis</span><span class="sxs-lookup"><span data-stu-id="8322f-226">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="8322f-227">OAuth 2,0-autorisatie voor gebruikersaanmelding en API-toegang</span><span class="sxs-lookup"><span data-stu-id="8322f-227">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
