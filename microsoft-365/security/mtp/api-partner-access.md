---
title: Partnertoegang via Microsoft 365 Defender API's
description: Meer informatie over het maken van een app om namens uw gebruikers toegang te krijgen via programmatische toegang tot Microsoft 365 Defender.
keywords: partner, toegang, api, meerdere tenants, toestemming, toegang token, app
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
ms.openlocfilehash: 07afb0baf5c115f2029abfe03795b081a4f253a8
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929396"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a><span data-ttu-id="53103-104">Een app maken met partnertoegang tot Microsoft 365 Defender API's</span><span class="sxs-lookup"><span data-stu-id="53103-104">Create an app with partner access to Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="53103-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="53103-105">**Applies to:**</span></span>

- <span data-ttu-id="53103-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="53103-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53103-107">Sommige informatie heeft betrekking op vooraf uitgebracht product dat aanzienlijk kan worden gewijzigd voordat het in de handel wordt gebracht.</span><span class="sxs-lookup"><span data-stu-id="53103-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="53103-108">Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt be gegeven.</span><span class="sxs-lookup"><span data-stu-id="53103-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="53103-109">Op deze pagina wordt beschreven hoe u een Azure Active Directory-app maakt met programmeertoegang tot Microsoft 365 Defender, namens gebruikers in meerdere tenants.</span><span class="sxs-lookup"><span data-stu-id="53103-109">This page describes how to create an Azure Active Directory app that has programmatic access to Microsoft 365 Defender, on behalf of users across multiple tenants.</span></span> <span data-ttu-id="53103-110">Apps met meerdere tenants zijn handig voor het bedienen van grote groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="53103-110">Multi-tenant apps are useful for serving large groups of users.</span></span>

<span data-ttu-id="53103-111">Als u namens één gebruiker programmeertoegang tot Microsoft 365 Defender nodig hebt, bekijkt u Een app maken voor toegang tot [Microsoft 365 Defender-API's namens een gebruiker.](api-create-app-user-context.md)</span><span class="sxs-lookup"><span data-stu-id="53103-111">If you need programmatic access to Microsoft 365 Defender on behalf of a single user, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md).</span></span> <span data-ttu-id="53103-112">Als u toegang nodig hebt zonder dat een gebruiker deze expliciet heeft gedefinieerd (bijvoorbeeld als u een achtergrond-app of daemon schrijft), zie Een app maken voor toegang tot [Microsoft 365 Defender](api-create-app-web.md)zonder een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="53103-112">If you need access without a user explicitly defined (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="53103-113">Zie Aan de slag als u niet zeker weet welk type toegang u [nodig hebt.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="53103-113">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="53103-114">Microsoft 365 Defender laat veel van zijn gegevens en acties zien via een set programmatische API's.</span><span class="sxs-lookup"><span data-stu-id="53103-114">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="53103-115">Met deze API's kunt u werkstromen automatiseren en gebruikmaken van de mogelijkheden van Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="53103-115">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="53103-116">Voor deze API-toegang is OAuth2.0-verificatie vereist.</span><span class="sxs-lookup"><span data-stu-id="53103-116">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="53103-117">Zie [OAuth 2.0 Authorization Code Flow voor](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="53103-117">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="53103-118">Over het algemeen moet u de volgende stappen nemen om deze API's te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="53103-118">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="53103-119">Maak een Azure Active Directory-toepassing (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="53103-119">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="53103-120">Krijg een toegangs token met deze toepassing.</span><span class="sxs-lookup"><span data-stu-id="53103-120">Get an access token using this application.</span></span>
- <span data-ttu-id="53103-121">Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender-API.</span><span class="sxs-lookup"><span data-stu-id="53103-121">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="53103-122">Omdat deze app meerdere tenants is, [](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) hebt u ook toestemming van een beheerder nodig van elke tenant namens de gebruikers.</span><span class="sxs-lookup"><span data-stu-id="53103-122">Since this app is multi-tenant, you'll also need [admin consent](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) from each tenant on behalf of its users.</span></span>

<span data-ttu-id="53103-123">In dit artikel wordt uitgelegd hoe u:</span><span class="sxs-lookup"><span data-stu-id="53103-123">This article explains how to:</span></span>

- <span data-ttu-id="53103-124">Een Azure **AD-toepassing met meerdere tenants** maken</span><span class="sxs-lookup"><span data-stu-id="53103-124">Create a **multi-tenant** Azure AD application</span></span>
- <span data-ttu-id="53103-125">Krijg toestemming van uw gebruikersbeheerder voor uw toepassing voor toegang tot Microsoft 365 Defender die bronnen beschikbaar stelt die het nodig heeft.</span><span class="sxs-lookup"><span data-stu-id="53103-125">Get authorized consent from your user administrator for your application to access the Microsoft 365 Defender that resources it needs.</span></span>
- <span data-ttu-id="53103-126">Een toegangs token voor Microsoft 365 Defender krijgen</span><span class="sxs-lookup"><span data-stu-id="53103-126">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="53103-127">Het token valideren</span><span class="sxs-lookup"><span data-stu-id="53103-127">Validate the token</span></span>

<span data-ttu-id="53103-128">Microsoft 365 Defender laat veel van zijn gegevens en acties zien via een set programmatische API's.</span><span class="sxs-lookup"><span data-stu-id="53103-128">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="53103-129">Met deze API's kunt u werkstromen automatiseren en innoveren op basis van de mogelijkheden van Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="53103-129">Those APIs will help you automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="53103-130">Voor de API-toegang is OAuth2.0-verificatie vereist.</span><span class="sxs-lookup"><span data-stu-id="53103-130">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="53103-131">Zie [OAuth 2.0 Authorization Code Flow voor](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="53103-131">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="53103-132">Over het algemeen moet u de volgende stappen nemen om de API's te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="53103-132">In general, you’ll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="53103-133">Maak een **Azure AD-toepassing met** meerdere tenants.</span><span class="sxs-lookup"><span data-stu-id="53103-133">Create a **multi-tenant** Azure AD application.</span></span>
- <span data-ttu-id="53103-134">Krijg toestemming (toestemming) van de gebruiker voor uw toepassing voor toegang tot bronnen van Microsoft 365 Defender die het nodig heeft.</span><span class="sxs-lookup"><span data-stu-id="53103-134">Get authorized (consent) by your user administrator for your application to access Microsoft 365 Defender resources it needs.</span></span>
- <span data-ttu-id="53103-135">Krijg een toegangs token met deze toepassing.</span><span class="sxs-lookup"><span data-stu-id="53103-135">Get an access token using this application.</span></span>
- <span data-ttu-id="53103-136">Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender-API.</span><span class="sxs-lookup"><span data-stu-id="53103-136">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="53103-137">De volgende stappen helpen u bij het maken van een Azure AD-toepassing met meerdere tenants, het aanvragen van een toegang-token voor Microsoft 365 Defender en het valideren van het token.</span><span class="sxs-lookup"><span data-stu-id="53103-137">The following steps with guide you how to create a multi-tenant Azure AD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="53103-138">De app met meerdere tenants maken</span><span class="sxs-lookup"><span data-stu-id="53103-138">Create the multi-tenant app</span></span>

1. <span data-ttu-id="53103-139">Meld u aan [bij Azure](https://portal.azure.com) als gebruiker met de **rol globale** beheerder.</span><span class="sxs-lookup"><span data-stu-id="53103-139">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="53103-140">Navigeer **naar de nieuwe registratie** van Azure Active Directory  >  **App-registraties.**  >  </span><span class="sxs-lookup"><span data-stu-id="53103-140">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Afbeelding van Microsoft Azure en navigatie naar toepassingsregistratie](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="53103-142">In het registratieformulier:</span><span class="sxs-lookup"><span data-stu-id="53103-142">In the registration form:</span></span>

   - <span data-ttu-id="53103-143">Kies een naam voor uw toepassing.</span><span class="sxs-lookup"><span data-stu-id="53103-143">Choose a name for your application.</span></span>
   - <span data-ttu-id="53103-144">Bij **Ondersteunde accounttypen** selecteert **u Accounts in een organisatiemap (Azure AD-adreslijst) - Multitenant.**</span><span class="sxs-lookup"><span data-stu-id="53103-144">From **Supported account types**, select **Accounts in any organizational directory (Any Azure AD directory) - Multitenant**.</span></span>
   - <span data-ttu-id="53103-145">Vul de sectie **Omleidings-URI** in.</span><span class="sxs-lookup"><span data-stu-id="53103-145">Fill out the **Redirect URI** section.</span></span> <span data-ttu-id="53103-146">Selecteer type **web** en geef de omleidings-URI als **https://portal.azure.com** .</span><span class="sxs-lookup"><span data-stu-id="53103-146">Select type **Web** and give the redirect URI as **https://portal.azure.com**.</span></span>

   <span data-ttu-id="53103-147">Nadat u het formulier hebt ingevuld, selecteert u **Registreren.**</span><span class="sxs-lookup"><span data-stu-id="53103-147">After you're done filling out the form, select **Register**.</span></span>

   ![Afbeelding van het formulier Een toepassing registreren](../..//media/atp-api-new-app-partner.png)

4. <span data-ttu-id="53103-149">Selecteer op uw **toepassingspagina** API-machtigingen Toevoegen machtiging-API's die door mijn organisatie >, typ Microsoft Threat Protection en selecteer  >    >   Microsoft **Threat Protection.** </span><span class="sxs-lookup"><span data-stu-id="53103-149">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="53103-150">Uw app heeft nu toegang tot Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="53103-150">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="53103-151">*Microsoft Threat Protection* is een voormalige naam voor Microsoft 365 Defender en wordt niet weergegeven in de oorspronkelijke lijst.</span><span class="sxs-lookup"><span data-stu-id="53103-151">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="53103-152">U moet beginnen met het schrijven van de naam in het tekstvak om deze weer te geven.</span><span class="sxs-lookup"><span data-stu-id="53103-152">You need to start writing its name in the text box to see it appear.</span></span>

   ![Afbeelding van api-machtigingenselectie](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="53103-154">Selecteer **Toepassingsmachtigingen.**</span><span class="sxs-lookup"><span data-stu-id="53103-154">Select **Application permissions**.</span></span> <span data-ttu-id="53103-155">Kies de relevante machtigingen voor uw scenario (bijvoorbeeld **Incident.Read.All)** en selecteer **Vervolgens Machtigingen toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="53103-155">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![Afbeelding van API-toegang en API-selectie](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="53103-157">U moet de relevante machtigingen voor uw scenario selecteren.</span><span class="sxs-lookup"><span data-stu-id="53103-157">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="53103-158">*Alle incidenten lezen* is slechts een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="53103-158">*Read all incidents* is just an example.</span></span> <span data-ttu-id="53103-159">Om te bepalen welke machtiging u nodig hebt, raadpleegt u de **sectie Machtigingen** in de API die u wilt bellen.</span><span class="sxs-lookup"><span data-stu-id="53103-159">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="53103-160">Als u bijvoorbeeld geavanceerde [query's wilt uitvoeren,](api-advanced-hunting.md)selecteert u de machtiging Geavanceerde query's uitvoeren. als u [een apparaat wilt isoleren,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)selecteert u de machtiging 'Isoleert computer'.</span><span class="sxs-lookup"><span data-stu-id="53103-160">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="53103-161">Selecteer **Beheerdersmachtiging verlenen.**</span><span class="sxs-lookup"><span data-stu-id="53103-161">Select **Grant admin consent**.</span></span> <span data-ttu-id="53103-162">Telkens wanneer u een machtiging toevoegt, moet u Toestemming **van een beheerder verlenen** selecteren om deze van kracht te laten worden.</span><span class="sxs-lookup"><span data-stu-id="53103-162">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Afbeelding van Machtigingen verlenen](../../media/grant-consent.PNG)

7. <span data-ttu-id="53103-164">Als u een geheim aan de toepassing wilt toevoegen, selecteert u Certificaten & **geheimen,** voegt u een beschrijving toe aan het geheim en selecteert u **Vervolgens Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="53103-164">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="53103-165">Nadat u Toevoegen **hebt geselecteerd,** **selecteert u de gegenereerde geheime waarde kopiëren.**</span><span class="sxs-lookup"><span data-stu-id="53103-165">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="53103-166">Nadat u de geheime waarde hebt verlaten, kunt u deze niet meer ophalen.</span><span class="sxs-lookup"><span data-stu-id="53103-166">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Afbeelding van app-sleutel maken](../../media/webapp-create-key2.png)

8. <span data-ttu-id="53103-168">Neem uw toepassings-id en tenant-id op in een veilige plaats.</span><span class="sxs-lookup"><span data-stu-id="53103-168">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="53103-169">Ze worden weergegeven onder Overzicht op **uw** toepassingspagina.</span><span class="sxs-lookup"><span data-stu-id="53103-169">They're listed under **Overview** on your application page.</span></span>

   ![Afbeelding van gemaakte app-id](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="53103-171">Voeg de toepassing toe aan de tenant van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="53103-171">Add the application to your user's tenant.</span></span>

   <span data-ttu-id="53103-172">Aangezien uw toepassing communiceert met Microsoft 365 Defender namens uw gebruikers, moet deze worden goedgekeurd voor elke tenant waarvoor u deze wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="53103-172">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

   <span data-ttu-id="53103-173">Een **globale beheerder** van de tenant van uw gebruiker moet de toestemmingskoppeling weergeven en uw aanvraag goedkeuren.</span><span class="sxs-lookup"><span data-stu-id="53103-173">A **Global Administrator** from your user's tenant needs to view the consent link and approve your application.</span></span>

   <span data-ttu-id="53103-174">Toestemmingskoppeling bestaat uit het formulier:</span><span class="sxs-lookup"><span data-stu-id="53103-174">Consent link is of the form:</span></span>

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   <span data-ttu-id="53103-175">De cijfers moeten `00000000-0000-0000-0000-000000000000` worden vervangen door uw toepassings-id.</span><span class="sxs-lookup"><span data-stu-id="53103-175">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>

   <span data-ttu-id="53103-176">Nadat u op de toestemmingskoppeling hebt geklikt, meldt u zich aan bij de globale beheerder van de tenant van de gebruiker en stemt u in met de toepassing.</span><span class="sxs-lookup"><span data-stu-id="53103-176">After clicking on the consent link, sign in with the Global Administrator of the user's tenant and consent the application.</span></span>

   ![Afbeelding van toestemming](../../media/app-consent-partner.png)

   <span data-ttu-id="53103-178">U moet de gebruiker ook om zijn of haar tenant-id vragen.</span><span class="sxs-lookup"><span data-stu-id="53103-178">You'll also need to ask your user for their tenant ID.</span></span> <span data-ttu-id="53103-179">De tenant-id is een van de id's die worden gebruikt om toegangstokens te verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="53103-179">The tenant ID is one of the identifiers used to acquire access tokens.</span></span>

- <span data-ttu-id="53103-180">**Klaar!**</span><span class="sxs-lookup"><span data-stu-id="53103-180">**Done!**</span></span> <span data-ttu-id="53103-181">U hebt een toepassing geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="53103-181">You've successfully registered an application!</span></span>
- <span data-ttu-id="53103-182">Zie de onderstaande voorbeelden voor het verkrijgen en valideren van token.</span><span class="sxs-lookup"><span data-stu-id="53103-182">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="53103-183">Een toegangs token krijgen</span><span class="sxs-lookup"><span data-stu-id="53103-183">Get an access token</span></span>

<span data-ttu-id="53103-184">Zie de Azure AD-zelfstudie voor meer informatie over [Azure AD-tokens.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="53103-184">For more information on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53103-185">Hoewel de voorbeelden in deze sectie u aanmoedigen om geheime  waarden te plakken voor testdoeleinden, moet u nooit geheimen coderen in een toepassing die wordt uitgevoerd in productie.</span><span class="sxs-lookup"><span data-stu-id="53103-185">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="53103-186">Een derde partij kan uw geheim gebruiken om toegang te krijgen tot bronnen.</span><span class="sxs-lookup"><span data-stu-id="53103-186">A third party could use your secret to access resources.</span></span> <span data-ttu-id="53103-187">U kunt de geheimen van uw app veilig houden met behulp van [Azure Key Vault.](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)</span><span class="sxs-lookup"><span data-stu-id="53103-187">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="53103-188">Zie Geheimen in uw [server-apps](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)beheren met Azure Key Vault voor een praktisch voorbeeld van hoe u uw app kunt beschermen.</span><span class="sxs-lookup"><span data-stu-id="53103-188">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

> [!TIP]
> <span data-ttu-id="53103-189">In de volgende voorbeelden gebruikt u de tenant-id van een gebruiker om te testen of het script werkt.</span><span class="sxs-lookup"><span data-stu-id="53103-189">In the following examples, use a user's tenant ID to test that the script is working.</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="53103-190">Een toegangs token krijgen met behulp van PowerShell</span><span class="sxs-lookup"><span data-stu-id="53103-190">Get an access token using PowerShell</span></span>

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

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="53103-191">Een toegangs token krijgen met behulp van C\#</span><span class="sxs-lookup"><span data-stu-id="53103-191">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="53103-192">De volgende code is getest met Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="53103-192">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="53103-193">Maak een nieuwe consoletoepassing.</span><span class="sxs-lookup"><span data-stu-id="53103-193">Create a new console application.</span></span>
1. <span data-ttu-id="53103-194">Installeer NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory.](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)</span><span class="sxs-lookup"><span data-stu-id="53103-194">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="53103-195">Voeg de volgende regel toe:</span><span class="sxs-lookup"><span data-stu-id="53103-195">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="53103-196">Kopieer en plak de volgende code in uw app (vergeet niet de drie variabelen bij te werken: `tenantId` , `clientId` , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="53103-196">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

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

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="53103-197">Een toegangs token krijgen met Python</span><span class="sxs-lookup"><span data-stu-id="53103-197">Get an access token using Python</span></span>

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

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="53103-198">Een toegangs token krijgen met gekruldek</span><span class="sxs-lookup"><span data-stu-id="53103-198">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="53103-199">Krullen is vooraf geïnstalleerd op Windows 10, versies 1803 en hoger.</span><span class="sxs-lookup"><span data-stu-id="53103-199">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="53103-200">Voor andere versies van Windows downloadt en installeert u het hulpprogramma rechtstreeks vanaf de [officiële gekrulde website.](https://curl.haxx.se/windows/)</span><span class="sxs-lookup"><span data-stu-id="53103-200">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="53103-201">Open een opdrachtprompt en stel een CLIENT_ID in op de id van uw Azure-toepassing.</span><span class="sxs-lookup"><span data-stu-id="53103-201">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="53103-202">Stel CLIENT_SECRET in op uw Azure-toepassingsgeheim.</span><span class="sxs-lookup"><span data-stu-id="53103-202">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="53103-203">Stel TENANT_ID in op de Azure-tenant-id van de gebruiker die uw app wil gebruiken voor toegang tot Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="53103-203">Set TENANT_ID to the Azure tenant ID of the user that wants to use your app to access Microsoft 365 Defender.</span></span>
1. <span data-ttu-id="53103-204">Voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="53103-204">Run the following command:</span></span>

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="53103-205">Een succesvol antwoord ziet er zo uit:</span><span class="sxs-lookup"><span data-stu-id="53103-205">A successful response will look like this:</span></span>

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="53103-206">Het token valideren</span><span class="sxs-lookup"><span data-stu-id="53103-206">Validate the token</span></span>

1. <span data-ttu-id="53103-207">Kopieer en plak het token in [de JSON web token validator website, JWT,](https://jwt.ms) om het te decoderen.</span><span class="sxs-lookup"><span data-stu-id="53103-207">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="53103-208">Zorg ervoor dat de *rollen die* binnen het gedecodeerde token worden gebruikt, de gewenste machtigingen bevatten.</span><span class="sxs-lookup"><span data-stu-id="53103-208">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="53103-209">In de volgende afbeelding ziet u een gedecodeerd token dat is verkregen van een app, met ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` en ```AdvancedHunting.Read.All``` machtigingen:</span><span class="sxs-lookup"><span data-stu-id="53103-209">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Afbeelding van validatie van token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="53103-211">Het token gebruiken om toegang te krijgen tot de Microsoft 365 Defender-API</span><span class="sxs-lookup"><span data-stu-id="53103-211">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="53103-212">Kies de API die u wilt gebruiken (incidenten of geavanceerd zoeken).</span><span class="sxs-lookup"><span data-stu-id="53103-212">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="53103-213">Zie Ondersteunde [Microsoft 365 Defender API's](api-supported.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="53103-213">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="53103-214">Stel in de http-aanvraag die u gaat verzenden de autorisatiekop in op, Beller is het autorisatieschema en het token dat het gevalideerde `"Bearer" <token>` token is.  </span><span class="sxs-lookup"><span data-stu-id="53103-214">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="53103-215">Het token verloopt binnen een uur.</span><span class="sxs-lookup"><span data-stu-id="53103-215">The token will expire within one hour.</span></span> <span data-ttu-id="53103-216">U kunt gedurende deze periode meer dan één aanvraag met hetzelfde token verzenden.</span><span class="sxs-lookup"><span data-stu-id="53103-216">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="53103-217">In het volgende voorbeeld ziet u hoe u een aanvraag verstuurt om een lijst met incidenten met **C# op te halen.**</span><span class="sxs-lookup"><span data-stu-id="53103-217">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="53103-218">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="53103-218">Related articles</span></span>

- [<span data-ttu-id="53103-219">Overzicht van Microsoft 365 Defender API's</span><span class="sxs-lookup"><span data-stu-id="53103-219">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="53103-220">Toegang tot de Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="53103-220">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="53103-221">Een 'Hallo wereld'-toepassing maken</span><span class="sxs-lookup"><span data-stu-id="53103-221">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="53103-222">Een app maken voor toegang tot Microsoft 365 Defender zonder een gebruiker</span><span class="sxs-lookup"><span data-stu-id="53103-222">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="53103-223">Een app maken voor toegang tot Microsoft 365 Defender API's namens een gebruiker</span><span class="sxs-lookup"><span data-stu-id="53103-223">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="53103-224">Meer informatie over API-limieten en licenties</span><span class="sxs-lookup"><span data-stu-id="53103-224">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="53103-225">Meer te weten komen over foutcodes</span><span class="sxs-lookup"><span data-stu-id="53103-225">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="53103-226">Geheimen in uw server-apps beheren met Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="53103-226">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="53103-227">OAuth 2.0 authorization for user sign in and API access</span><span class="sxs-lookup"><span data-stu-id="53103-227">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
