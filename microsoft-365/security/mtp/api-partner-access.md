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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 1e8db376db4533a1d3932b488a773472e5209c5a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922196"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a><span data-ttu-id="d4c98-104">Een app maken met partnertoegang tot Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="d4c98-104">Create an app with partner access to Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d4c98-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d4c98-105">**Applies to:**</span></span>

- <span data-ttu-id="d4c98-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4c98-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4c98-107">Sommige informatie heeft betrekking op vooraf uitgebracht product dat mogelijk aanzienlijk wordt gewijzigd voordat het commercieel wordt uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="d4c98-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d4c98-108">Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt verstrekt.</span><span class="sxs-lookup"><span data-stu-id="d4c98-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="d4c98-109">Op deze pagina wordt beschreven hoe u een Azure Active Directory-app maakt die programmatische toegang heeft tot Microsoft 365 Defender, namens gebruikers in meerdere tenants.</span><span class="sxs-lookup"><span data-stu-id="d4c98-109">This page describes how to create an Azure Active Directory app that has programmatic access to Microsoft 365 Defender, on behalf of users across multiple tenants.</span></span> <span data-ttu-id="d4c98-110">Multi-tenant-apps zijn handig voor het bedienen van grote groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="d4c98-110">Multi-tenant apps are useful for serving large groups of users.</span></span>

<span data-ttu-id="d4c98-111">Zie Een app maken voor toegang tot Microsoft 365 Defender-API's namens een gebruiker als u programmatische toegang nodig hebt tot [Microsoft 365](api-create-app-user-context.md)Defender.</span><span class="sxs-lookup"><span data-stu-id="d4c98-111">If you need programmatic access to Microsoft 365 Defender on behalf of a single user, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md).</span></span> <span data-ttu-id="d4c98-112">Als u toegang nodig hebt zonder een gebruiker die expliciet is gedefinieerd (bijvoorbeeld als u een achtergrond-app of daemon schrijft), zie Een app maken voor toegang tot [Microsoft 365 Defender](api-create-app-web.md)zonder een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="d4c98-112">If you need access without a user explicitly defined (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="d4c98-113">Zie Aan de slag als u niet zeker weet welk type toegang u nodig [hebt.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="d4c98-113">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="d4c98-114">Microsoft 365 Defender toont een groot deel van de gegevens en acties via een set programmatische API's.</span><span class="sxs-lookup"><span data-stu-id="d4c98-114">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="d4c98-115">Met deze API's kunt u werkstromen automatiseren en gebruikmaken van de mogelijkheden van Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d4c98-115">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="d4c98-116">Voor deze API-toegang is OAuth2.0-verificatie vereist.</span><span class="sxs-lookup"><span data-stu-id="d4c98-116">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="d4c98-117">Zie [OAuth 2.0 Autorisatiecodestroom](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d4c98-117">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="d4c98-118">Over het algemeen moet u de volgende stappen nemen om deze API's te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="d4c98-118">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="d4c98-119">Een Azure Active Directory-toepassing (Azure AD) maken.</span><span class="sxs-lookup"><span data-stu-id="d4c98-119">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="d4c98-120">Een toegangs token krijgen met deze toepassing.</span><span class="sxs-lookup"><span data-stu-id="d4c98-120">Get an access token using this application.</span></span>
- <span data-ttu-id="d4c98-121">Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender-API.</span><span class="sxs-lookup"><span data-stu-id="d4c98-121">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="d4c98-122">Aangezien deze app multi-tenant is, [](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) hebt u ook beheerdersmachtiging nodig van elke tenant namens de gebruikers.</span><span class="sxs-lookup"><span data-stu-id="d4c98-122">Since this app is multi-tenant, you'll also need [admin consent](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) from each tenant on behalf of its users.</span></span>

<span data-ttu-id="d4c98-123">In dit artikel wordt uitgelegd hoe u:</span><span class="sxs-lookup"><span data-stu-id="d4c98-123">This article explains how to:</span></span>

- <span data-ttu-id="d4c98-124">Een **Azure AD-toepassing met meerdere tenants** maken</span><span class="sxs-lookup"><span data-stu-id="d4c98-124">Create a **multi-tenant** Azure AD application</span></span>
- <span data-ttu-id="d4c98-125">Krijg geautoriseerde toestemming van uw gebruikerbeheerder voor uw toepassing om toegang te krijgen tot de Microsoft 365 Defender die deze resources nodig heeft.</span><span class="sxs-lookup"><span data-stu-id="d4c98-125">Get authorized consent from your user administrator for your application to access the Microsoft 365 Defender that resources it needs.</span></span>
- <span data-ttu-id="d4c98-126">Een toegangs token voor Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4c98-126">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="d4c98-127">Het token valideren</span><span class="sxs-lookup"><span data-stu-id="d4c98-127">Validate the token</span></span>

<span data-ttu-id="d4c98-128">Microsoft 365 Defender toont een groot deel van de gegevens en acties via een set programmatische API's.</span><span class="sxs-lookup"><span data-stu-id="d4c98-128">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="d4c98-129">Met deze API's kunt u werkstromen automatiseren en innoveren op basis van microsoft 365 Defender-mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="d4c98-129">Those APIs will help you automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="d4c98-130">Voor de API-toegang is OAuth2.0-verificatie vereist.</span><span class="sxs-lookup"><span data-stu-id="d4c98-130">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="d4c98-131">Zie [OAuth 2.0 Autorisatiecodestroom](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d4c98-131">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="d4c98-132">Over het algemeen moet u de volgende stappen nemen om de API's te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="d4c98-132">In general, you’ll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="d4c98-133">Maak een **Azure AD-toepassing met** meerdere tenants.</span><span class="sxs-lookup"><span data-stu-id="d4c98-133">Create a **multi-tenant** Azure AD application.</span></span>
- <span data-ttu-id="d4c98-134">Ontvang geautoriseerde (toestemming) van uw gebruikerbeheerder voor uw toepassing om toegang te krijgen tot Microsoft 365 Defender-bronnen die nodig zijn.</span><span class="sxs-lookup"><span data-stu-id="d4c98-134">Get authorized (consent) by your user administrator for your application to access Microsoft 365 Defender resources it needs.</span></span>
- <span data-ttu-id="d4c98-135">Een toegangs token krijgen met deze toepassing.</span><span class="sxs-lookup"><span data-stu-id="d4c98-135">Get an access token using this application.</span></span>
- <span data-ttu-id="d4c98-136">Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender-API.</span><span class="sxs-lookup"><span data-stu-id="d4c98-136">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="d4c98-137">In de volgende stappen vindt u informatie over het maken van een Azure AD-toepassing met meerdere tenants, het openen van een token voor Microsoft 365 Defender en het valideren van het token.</span><span class="sxs-lookup"><span data-stu-id="d4c98-137">The following steps with guide you how to create a multi-tenant Azure AD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="d4c98-138">De multi-tenant-app maken</span><span class="sxs-lookup"><span data-stu-id="d4c98-138">Create the multi-tenant app</span></span>

1. <span data-ttu-id="d4c98-139">Meld u aan [bij Azure](https://portal.azure.com) als gebruiker met de **rol Globale** beheerder.</span><span class="sxs-lookup"><span data-stu-id="d4c98-139">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="d4c98-140">**Navigeer naar Azure Active Directory**  >  **App-registraties** Nieuwe  >  **registratie**.</span><span class="sxs-lookup"><span data-stu-id="d4c98-140">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Afbeelding van Microsoft Azure en navigatie naar toepassingsregistratie](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="d4c98-142">In het registratieformulier:</span><span class="sxs-lookup"><span data-stu-id="d4c98-142">In the registration form:</span></span>

   - <span data-ttu-id="d4c98-143">Kies een naam voor uw toepassing.</span><span class="sxs-lookup"><span data-stu-id="d4c98-143">Choose a name for your application.</span></span>
   - <span data-ttu-id="d4c98-144">Selecteer accounts in **een organisatiemap** **(een Azure AD-adreslijst) - Multitenant in ondersteunde accounttypen.**</span><span class="sxs-lookup"><span data-stu-id="d4c98-144">From **Supported account types**, select **Accounts in any organizational directory (Any Azure AD directory) - Multitenant**.</span></span>
   - <span data-ttu-id="d4c98-145">Vul de sectie **Redirect URI** in.</span><span class="sxs-lookup"><span data-stu-id="d4c98-145">Fill out the **Redirect URI** section.</span></span> <span data-ttu-id="d4c98-146">Selecteer Type **Web** en geef de omleidings-URI als **https://portal.azure.com** .</span><span class="sxs-lookup"><span data-stu-id="d4c98-146">Select type **Web** and give the redirect URI as **https://portal.azure.com**.</span></span>

   <span data-ttu-id="d4c98-147">Nadat u klaar bent met het invullen van het formulier, selecteert u **Registreren.**</span><span class="sxs-lookup"><span data-stu-id="d4c98-147">After you're done filling out the form, select **Register**.</span></span>

   ![Afbeelding van het toepassingsformulier Registreren](../..//media/atp-api-new-app-partner.png)

4. <span data-ttu-id="d4c98-149">Selecteer op uw **toepassingspagina API-machtigingen** Machtigingen toevoegen Machtiging-API's die mijn organisatie gebruikt  >    >   >, typ **Microsoft Threat Protection** en selecteer Microsoft **Threat Protection.**</span><span class="sxs-lookup"><span data-stu-id="d4c98-149">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="d4c98-150">Uw app heeft nu toegang tot Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d4c98-150">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="d4c98-151">*Microsoft Threat Protection* is een voormalige naam voor Microsoft 365 Defender en wordt niet weergegeven in de oorspronkelijke lijst.</span><span class="sxs-lookup"><span data-stu-id="d4c98-151">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="d4c98-152">U moet beginnen met het schrijven van de naam in het tekstvak om deze weer te geven.</span><span class="sxs-lookup"><span data-stu-id="d4c98-152">You need to start writing its name in the text box to see it appear.</span></span>

   ![Afbeelding van API-machtigingsselectie](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="d4c98-154">Selecteer **Toepassingsmachtigingen.**</span><span class="sxs-lookup"><span data-stu-id="d4c98-154">Select **Application permissions**.</span></span> <span data-ttu-id="d4c98-155">Kies de relevante machtigingen voor uw scenario (bijvoorbeeld **Incident.Read.All)** en selecteer **vervolgens Machtigingen toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="d4c98-155">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![Afbeelding van API-toegang en API-selectie](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="d4c98-157">U moet de relevante machtigingen voor uw scenario selecteren.</span><span class="sxs-lookup"><span data-stu-id="d4c98-157">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="d4c98-158">*Alle incidenten lezen* is slechts een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="d4c98-158">*Read all incidents* is just an example.</span></span> <span data-ttu-id="d4c98-159">Als u wilt bepalen welke machtiging u nodig hebt, kijkt u naar **de sectie** Machtigingen in de API die u wilt bellen.</span><span class="sxs-lookup"><span data-stu-id="d4c98-159">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="d4c98-160">Als u bijvoorbeeld geavanceerde [query's wilt uitvoeren,](api-advanced-hunting.md)selecteert u de machtiging Geavanceerde query's uitvoeren. als [u een apparaat wilt isoleren,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)selecteert u de machtiging 'Machine isoleren'.</span><span class="sxs-lookup"><span data-stu-id="d4c98-160">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="d4c98-161">Selecteer **Beheerdersmachtiging verlenen.**</span><span class="sxs-lookup"><span data-stu-id="d4c98-161">Select **Grant admin consent**.</span></span> <span data-ttu-id="d4c98-162">Telkens wanneer u een machtiging toevoegt, moet u Toestemming van beheerder **verlenen selecteren** om deze van kracht te laten worden.</span><span class="sxs-lookup"><span data-stu-id="d4c98-162">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Afbeelding van machtigingen verlenen](../../media/grant-consent.PNG)

7. <span data-ttu-id="d4c98-164">Als u een geheim aan de toepassing wilt toevoegen, selecteert u Certificaten **& geheimen,** voegt u een beschrijving toe aan het geheim en selecteert u **Vervolgens Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="d4c98-164">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="d4c98-165">Nadat u Toevoegen **hebt geselecteerd,** **selecteert u de gegenereerde geheime waarde kopiëren.**</span><span class="sxs-lookup"><span data-stu-id="d4c98-165">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="d4c98-166">U kunt de geheime waarde niet meer ophalen nadat u bent weggehaald.</span><span class="sxs-lookup"><span data-stu-id="d4c98-166">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Afbeelding van app-sleutel maken](../../media/webapp-create-key2.png)

8. <span data-ttu-id="d4c98-168">Neem uw toepassings-id en uw tenant-id op een veilige plaats op.</span><span class="sxs-lookup"><span data-stu-id="d4c98-168">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="d4c98-169">Ze worden weergegeven onder **Overzicht** op uw toepassingspagina.</span><span class="sxs-lookup"><span data-stu-id="d4c98-169">They're listed under **Overview** on your application page.</span></span>

   ![Afbeelding van gemaakte app-id](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="d4c98-171">Voeg de toepassing toe aan de tenant van uw gebruiker.</span><span class="sxs-lookup"><span data-stu-id="d4c98-171">Add the application to your user's tenant.</span></span>

   <span data-ttu-id="d4c98-172">Aangezien uw toepassing namens uw gebruikers samenwerkt met Microsoft 365 Defender, moet deze worden goedgekeurd voor elke tenant waarvoor u deze wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d4c98-172">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

   <span data-ttu-id="d4c98-173">Een **globale beheerder** van de tenant van uw gebruiker moet de toestemmingskoppeling bekijken en uw toepassing goedkeuren.</span><span class="sxs-lookup"><span data-stu-id="d4c98-173">A **Global Administrator** from your user's tenant needs to view the consent link and approve your application.</span></span>

   <span data-ttu-id="d4c98-174">De koppeling Toestemming is van het formulier:</span><span class="sxs-lookup"><span data-stu-id="d4c98-174">Consent link is of the form:</span></span>

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   <span data-ttu-id="d4c98-175">De cijfers moeten `00000000-0000-0000-0000-000000000000` worden vervangen door uw toepassings-id.</span><span class="sxs-lookup"><span data-stu-id="d4c98-175">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>

   <span data-ttu-id="d4c98-176">Nadat u op de toestemmingskoppeling hebt geklikt, meldt u zich aan bij de globale beheerder van de tenant van de gebruiker en stemt u in met de toepassing.</span><span class="sxs-lookup"><span data-stu-id="d4c98-176">After clicking on the consent link, sign in with the Global Administrator of the user's tenant and consent the application.</span></span>

   ![Afbeelding van toestemming](../../media/app-consent-partner.png)

   <span data-ttu-id="d4c98-178">U moet ook uw gebruiker om zijn of haar tenant-id vragen.</span><span class="sxs-lookup"><span data-stu-id="d4c98-178">You'll also need to ask your user for their tenant ID.</span></span> <span data-ttu-id="d4c98-179">De tenant-id is een van de id's die worden gebruikt om toegangstokens te verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="d4c98-179">The tenant ID is one of the identifiers used to acquire access tokens.</span></span>

- <span data-ttu-id="d4c98-180">**Klaar!**</span><span class="sxs-lookup"><span data-stu-id="d4c98-180">**Done!**</span></span> <span data-ttu-id="d4c98-181">U hebt een toepassing geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="d4c98-181">You've successfully registered an application!</span></span>
- <span data-ttu-id="d4c98-182">Zie hieronder voorbeelden voor het verkrijgen en valideren van tokens.</span><span class="sxs-lookup"><span data-stu-id="d4c98-182">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="d4c98-183">Een toegangs token krijgen</span><span class="sxs-lookup"><span data-stu-id="d4c98-183">Get an access token</span></span>

<span data-ttu-id="d4c98-184">Zie de [zelfstudie Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)voor meer informatie over Azure AD-tokens.</span><span class="sxs-lookup"><span data-stu-id="d4c98-184">For more information on Azure AD tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4c98-185">Hoewel de voorbeelden in deze sectie u aanmoedigen om geheime waarden te plakken voor testdoeleinden, moet u nooit geheimen **hardcoderen** in een toepassing die in productie wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="d4c98-185">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="d4c98-186">Een derde partij kan uw geheim gebruiken om toegang te krijgen tot bronnen.</span><span class="sxs-lookup"><span data-stu-id="d4c98-186">A third party could use your secret to access resources.</span></span> <span data-ttu-id="d4c98-187">U kunt de geheimen van uw app beveiligen met Behulp van [Azure Key Vault.](/azure/key-vault/general/about-keys-secrets-certificates)</span><span class="sxs-lookup"><span data-stu-id="d4c98-187">You can help keep your app's secrets secure by using [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="d4c98-188">Zie Geheimen beheren in uw server-apps met Azure Key Vault voor een praktisch voorbeeld van hoe u uw app [kunt beveiligen.](/learn/modules/manage-secrets-with-azure-key-vault/)</span><span class="sxs-lookup"><span data-stu-id="d4c98-188">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

> [!TIP]
> <span data-ttu-id="d4c98-189">Gebruik in de volgende voorbeelden de tenant-id van een gebruiker om te testen of het script werkt.</span><span class="sxs-lookup"><span data-stu-id="d4c98-189">In the following examples, use a user's tenant ID to test that the script is working.</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="d4c98-190">Toegangs token krijgen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4c98-190">Get an access token using PowerShell</span></span>

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

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="d4c98-191">Toegangs token krijgen met C\#</span><span class="sxs-lookup"><span data-stu-id="d4c98-191">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="d4c98-192">De volgende code is getest met Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="d4c98-192">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="d4c98-193">Een nieuwe consoletoepassing maken.</span><span class="sxs-lookup"><span data-stu-id="d4c98-193">Create a new console application.</span></span>
1. <span data-ttu-id="d4c98-194">Installeer NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="d4c98-194">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="d4c98-195">Voeg de volgende regel toe:</span><span class="sxs-lookup"><span data-stu-id="d4c98-195">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="d4c98-196">Kopieer en plak de volgende code in uw app (vergeet niet om de drie variabelen bij te werken: `tenantId` , `clientId` , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="d4c98-196">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

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

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="d4c98-197">Toegangs token krijgen met Python</span><span class="sxs-lookup"><span data-stu-id="d4c98-197">Get an access token using Python</span></span>

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

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="d4c98-198">Een toegangs token krijgen met behulp van krul</span><span class="sxs-lookup"><span data-stu-id="d4c98-198">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="d4c98-199">Curl is vooraf geïnstalleerd op Windows 10, versie 1803 en hoger.</span><span class="sxs-lookup"><span data-stu-id="d4c98-199">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="d4c98-200">Voor andere versies van Windows downloadt en installeert u het hulpprogramma rechtstreeks vanaf de [officiële curl-website.](https://curl.haxx.se/windows/)</span><span class="sxs-lookup"><span data-stu-id="d4c98-200">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="d4c98-201">Open een opdrachtprompt en stel CLIENT_ID in op uw Azure-toepassings-id.</span><span class="sxs-lookup"><span data-stu-id="d4c98-201">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="d4c98-202">Stel CLIENT_SECRET in op uw Azure-toepassingsgeheim.</span><span class="sxs-lookup"><span data-stu-id="d4c98-202">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="d4c98-203">Stel TENANT_ID azure tenant-id in van de gebruiker die uw app wil gebruiken om toegang te krijgen tot Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d4c98-203">Set TENANT_ID to the Azure tenant ID of the user that wants to use your app to access Microsoft 365 Defender.</span></span>
1. <span data-ttu-id="d4c98-204">Voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="d4c98-204">Run the following command:</span></span>

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="d4c98-205">Een succesvol antwoord ziet er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="d4c98-205">A successful response will look like this:</span></span>

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="d4c98-206">Het token valideren</span><span class="sxs-lookup"><span data-stu-id="d4c98-206">Validate the token</span></span>

1. <span data-ttu-id="d4c98-207">Kopieer en plak het token in [de JSON web token validator-website, JWT,](https://jwt.ms) om het te decoderen.</span><span class="sxs-lookup"><span data-stu-id="d4c98-207">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="d4c98-208">Zorg ervoor dat de *claim rollen* in het gedecodeerde token de gewenste machtigingen bevat.</span><span class="sxs-lookup"><span data-stu-id="d4c98-208">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="d4c98-209">In de volgende afbeelding ziet u een gedecodeerd token dat is verkregen van een app, met ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` , en ```AdvancedHunting.Read.All``` machtigingen:</span><span class="sxs-lookup"><span data-stu-id="d4c98-209">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Afbeelding van tokenvalidatie](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="d4c98-211">Het token gebruiken om toegang te krijgen tot de Microsoft 365 Defender-API</span><span class="sxs-lookup"><span data-stu-id="d4c98-211">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="d4c98-212">Kies de API die u wilt gebruiken (incidenten of geavanceerd zoeken).</span><span class="sxs-lookup"><span data-stu-id="d4c98-212">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="d4c98-213">Zie Ondersteunde [Microsoft 365 Defender-API's](api-supported.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d4c98-213">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="d4c98-214">Stel in de http-aanvraag die u gaat verzenden de autorisatiekop in op , Bearer is het autorisatieschema en het `"Bearer" <token>` *token*  dat uw gevalideerde token is.</span><span class="sxs-lookup"><span data-stu-id="d4c98-214">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="d4c98-215">Het token verloopt binnen een uur.</span><span class="sxs-lookup"><span data-stu-id="d4c98-215">The token will expire within one hour.</span></span> <span data-ttu-id="d4c98-216">U kunt in deze periode meerdere aanvragen met hetzelfde token verzenden.</span><span class="sxs-lookup"><span data-stu-id="d4c98-216">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="d4c98-217">In het volgende voorbeeld ziet u hoe u een aanvraag verzendt om een lijst met incidenten te krijgen **met C#**.</span><span class="sxs-lookup"><span data-stu-id="d4c98-217">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="d4c98-218">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="d4c98-218">Related articles</span></span>

- [<span data-ttu-id="d4c98-219">Overzicht van Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="d4c98-219">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="d4c98-220">De Microsoft 365 Defender-API's openen</span><span class="sxs-lookup"><span data-stu-id="d4c98-220">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="d4c98-221">Een 'Hello world'-toepassing maken</span><span class="sxs-lookup"><span data-stu-id="d4c98-221">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="d4c98-222">Een app maken voor toegang tot Microsoft 365 Defender zonder een gebruiker</span><span class="sxs-lookup"><span data-stu-id="d4c98-222">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="d4c98-223">Een app maken voor toegang tot Microsoft 365 Defender-API's namens een gebruiker</span><span class="sxs-lookup"><span data-stu-id="d4c98-223">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="d4c98-224">Meer informatie over API-limieten en -licenties</span><span class="sxs-lookup"><span data-stu-id="d4c98-224">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="d4c98-225">Foutcodes begrijpen</span><span class="sxs-lookup"><span data-stu-id="d4c98-225">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="d4c98-226">Geheimen beheren in uw server-apps met Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="d4c98-226">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="d4c98-227">OAuth 2.0-autorisatie voor gebruikers aanmelden en API-toegang</span><span class="sxs-lookup"><span data-stu-id="d4c98-227">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)