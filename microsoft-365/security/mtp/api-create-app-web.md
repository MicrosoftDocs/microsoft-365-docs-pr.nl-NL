---
title: Een app maken om toegang te krijgen tot Microsoft 365 Defender zonder een gebruiker
description: Meer informatie over het maken van een app voor toegang tot Microsoft 365 Defender zonder een gebruiker.
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
ms.openlocfilehash: de925fa52056a051592fe5024c0abd40b51ad57b
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719354"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a><span data-ttu-id="d8a0d-104">Een app maken om toegang te krijgen tot Microsoft 365 Defender zonder een gebruiker</span><span class="sxs-lookup"><span data-stu-id="d8a0d-104">Create an app to access Microsoft 365 Defender without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d8a0d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d8a0d-105">**Applies to:**</span></span>

- <span data-ttu-id="d8a0d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8a0d-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8a0d-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d8a0d-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="d8a0d-109">Op deze pagina wordt beschreven hoe u een toepassing maakt om via een programma toegang te krijgen tot Microsoft 365 Defender zonder een gedefinieerde gebruiker, bijvoorbeeld als u een demon of een achtergrondservice maakt.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender without a defined user—for example, if you're creating a daemon or background service.</span></span>

<span data-ttu-id="d8a0d-110">Als u voor een of meer gebruikers via een programma toegang wilt hebben tot Microsoft 365 Defender, raadpleegt u [een app maken om toegang te krijgen tot Microsoft 365-api's namens een gebruiker](api-create-app-user-context.md) en [een app te maken met partner toegang tot Microsoft 365](api-partner-access.md)</span><span class="sxs-lookup"><span data-stu-id="d8a0d-110">If you need programmatic access to Microsoft 365 Defender on behalf of one or more users, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md) and [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).</span></span> <span data-ttu-id="d8a0d-111">Als u niet zeker weet welk type toegang u nodig hebt, raadpleegt u [aan de slag](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="d8a0d-111">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="d8a0d-112">Microsoft 365 Defender geeft veel van zijn gegevens en acties getoond via een set programmeer Api's.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="d8a0d-113">Met deze Api's kunt u werkstromen automatiseren en gebruikmaken van de mogelijkheden van Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="d8a0d-114">Voor deze API-toegang is OAuth 2.0 Authentication vereist.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="d8a0d-115">Voor meer informatie raadpleegt u [OAuth 2,0 Authorization code flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="d8a0d-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="d8a0d-116">In het algemeen dient u de volgende stappen uit te voeren om deze Api's te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="d8a0d-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="d8a0d-117">Maak een Azure AD-toepassing (Azure Active Directory).</span><span class="sxs-lookup"><span data-stu-id="d8a0d-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="d8a0d-118">U krijgt een toegangstoken met deze toepassing.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-118">Get an access token using this application.</span></span>
- <span data-ttu-id="d8a0d-119">Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="d8a0d-120">In dit artikel wordt uitgelegd hoe u dit kunt doen:</span><span class="sxs-lookup"><span data-stu-id="d8a0d-120">This article explains how to:</span></span>

- <span data-ttu-id="d8a0d-121">Een Azure AD-toepassing maken</span><span class="sxs-lookup"><span data-stu-id="d8a0d-121">Create an Azure AD application</span></span>
- <span data-ttu-id="d8a0d-122">Een toegangstoken verkrijgen bij Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8a0d-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="d8a0d-123">Valideer het token.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-123">Validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="d8a0d-124">Een app maken</span><span class="sxs-lookup"><span data-stu-id="d8a0d-124">Create an app</span></span>

1. <span data-ttu-id="d8a0d-125">Meld u aan bij [Azure](https://portal.azure.com) als een gebruiker met de rol van **globale beheerder** .</span><span class="sxs-lookup"><span data-stu-id="d8a0d-125">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="d8a0d-126">Ga naar de **Azure Active Directory**-  >  **app registraties**  >  **nieuwe registratie**.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-126">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Afbeelding van Microsoft Azure en navigatie naar toepassing registreren](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="d8a0d-128">Kies in het formulier een naam voor de toepassing en selecteer vervolgens **registreren**.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-128">In the form, choose a name for your application, then select **Register**.</span></span>

4. <span data-ttu-id="d8a0d-129">Selecteer op de pagina toepassingen de optie **API-machtigingen**  >  **toevoegen**  >  **Mijn organisatie gebruikt** >, typ **Microsoft Threat Protection** en selecteer **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-129">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="d8a0d-130">Uw app heeft nu toegang tot Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-130">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="d8a0d-131">*Microsoft Threat Protection* is een voormalig naam voor microsoft 365 Defender en wordt niet weergegeven in de oorspronkelijke lijst.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-131">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="d8a0d-132">U moet de naam ervan beginnen te schrijven in het tekstvak om de naam weer te geven.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-132">You need to start writing its name in the text box to see it appear.</span></span>

   ![Afbeelding van selectie van API-machtigingen](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="d8a0d-134">Selecteer **Toepassingsmachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-134">Select **Application permissions**.</span></span> <span data-ttu-id="d8a0d-135">Kies de relevante machtigingen voor uw scenario (bijvoorbeeld **incident. Read. all**) en selecteer vervolgens **machtigingen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-135">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![Afbeelding van API-toegang en API-selectie](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="d8a0d-137">U moet de relevante machtigingen voor uw scenario selecteren.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-137">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="d8a0d-138">*Alle incidenten lezen* is slechts een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-138">*Read all incidents* is just an example.</span></span> <span data-ttu-id="d8a0d-139">Om te bepalen welke machtigingen u nodig hebt, raadpleegt u de sectie **machtigingen** in de API die u wilt bellen.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-139">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="d8a0d-140">Als u een [geavanceerde zoek](api-advanced-hunting.md)opdracht wilt uitvoeren, selecteert u de machtiging Geavanceerd query's uitvoeren. Als u [een apparaat wilt isoleren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), selecteert u de machtiging computer isoleren.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-140">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="d8a0d-141">Selecteer **beheerder toestemming verlenen**.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-141">Select **Grant admin consent**.</span></span> <span data-ttu-id="d8a0d-142">Telkens wanneer u een machtiging toevoegt, moet u de machtiging **beheerder toestemming verlenen** selecteren om de machtiging van kracht te laten worden.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-142">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Afbeelding van machtiging verlenen](../../media/grant-consent.PNG)

7. <span data-ttu-id="d8a0d-144">Als u een geheim wilt toevoegen aan de toepassing, selecteert u **certificaten & geheimen**, voegt u een beschrijving toe aan het geheim en selecteert u vervolgens **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-144">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="d8a0d-145">Wanneer u **toevoegen** hebt geselecteerd, selecteert u **de gegenereerde geheime waarde kopiëren**.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-145">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="d8a0d-146">U kunt de geheime waarde niet meer ophalen wanneer u niets hebt.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-146">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Afbeelding van de sleutel app maken](../../media/webapp-create-key2.png)

8. <span data-ttu-id="d8a0d-148">Registreer uw toepassings-ID en uw Tenant-ID ergens veilig.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-148">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="d8a0d-149">Ze worden weergegeven onder **overzicht** op de pagina toepassing.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-149">They're listed under **Overview** on your application page.</span></span>

   ![Afbeelding van gemaakte app-id](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="d8a0d-151">**Voor alleen Microsoft 365, alleen voor Microsoft-partners**: [Volg deze instructies](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access) voor het openen van partners via de Microsoft 365 Defender-api's, stel uw app in op multi-tenant, zodat deze beschikbaar is in alle tenants wanneer u beheerders toestemming ontvangt.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-151">**For Microsoft 365 Defender Partners only**: [Follow these instructions](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access) for partner access through the Microsoft 365 Defender APIs, set your app to be multi-tenant, so it can be available in all tenants once you receive admin consent.</span></span> <span data-ttu-id="d8a0d-152">Partner toegang is **vereist** voor apps van derden, bijvoorbeeld als u een app maakt die bedoeld is om te worden uitgevoerd in de tenants van meerdere klanten.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-152">Partner access is **required** for third-party apps—for example, if you create an app that is intended to run in multiple customers' tenants.</span></span> <span data-ttu-id="d8a0d-153">U hoeft **niet te doen** als u een service maakt die u alleen in uw Tenant wilt uitvoeren, zoals een toepassing voor uw eigen gebruik dat alleen werkt met uw eigen gegevens.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-153">It is **not required** if you create a service that you want to run in your tenant only, such as an application for your own usage that will only interact with your own data.</span></span> <span data-ttu-id="d8a0d-154">Uw app instellen voor meervoudige Tenant:</span><span class="sxs-lookup"><span data-stu-id="d8a0d-154">To set your app to be multi-tenant:</span></span>

    - <span data-ttu-id="d8a0d-155">Ga naar **verificatie** en voeg toe https://portal.azure.com als de **omleidings-URL**.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-155">Go to **Authentication**, and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="d8a0d-156">Onder aan de pagina, onder **ondersteunde accounttypen**, selecteert u de **accounts in een** toepassing voor de organisatie van de toepassing voor uw app met meerdere tenants.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-156">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="d8a0d-157">Aangezien de toepassing interactie maakt met Microsoft 365 Defender in naam van uw gebruikers, moet deze zijn goedgekeurd voor elke Tenant waarop u de toepassing wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-157">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

    <span data-ttu-id="d8a0d-158">De globale beheerder van Active Directory voor elke Tenant moet de instemming-koppeling selecteren en de app goedkeuren.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-158">The Active Directory global admin for each tenant needs to select the consent link and approve your app.</span></span>

    <span data-ttu-id="d8a0d-159">De koppeling toestemming heeft de volgende structuur:</span><span class="sxs-lookup"><span data-stu-id="d8a0d-159">The consent link has the following structure:</span></span>

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="d8a0d-160">De cijfers `00000000-0000-0000-0000-000000000000` worden vervangen door uw toepassings-id.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-160">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>  

<span data-ttu-id="d8a0d-161">**Klaar!**</span><span class="sxs-lookup"><span data-stu-id="d8a0d-161">**Done!**</span></span> <span data-ttu-id="d8a0d-162">U hebt een toepassing geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-162">You've successfully registered an application!</span></span> <span data-ttu-id="d8a0d-163">Zie voorbeelden hieronder voor het verwerving van tokens en validatie.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-163">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="d8a0d-164">Een toegangstoken verkrijgen</span><span class="sxs-lookup"><span data-stu-id="d8a0d-164">Get an access token</span></span>

<span data-ttu-id="d8a0d-165">Zie voor meer informatie over Azure Active Directory-tokens de [zelfstudie voor Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="d8a0d-165">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8a0d-166">Hoewel in de voorbeelden in deze sectie wordt voor testdoeleinden geen geheime waarden kunnen worden geplakt, moet u **nooit hardcodee geheimen** verleggen in een toepassing die wordt uitgevoerd in de productie.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-166">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="d8a0d-167">Een derde partij kon uw geheim gebruiken om toegang te krijgen tot bronnen.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-167">A third party could use your secret to access resources.</span></span> <span data-ttu-id="d8a0d-168">U kunt de geheimen van uw apps veilig houden met behulp van [Azure Key-kluis](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span><span class="sxs-lookup"><span data-stu-id="d8a0d-168">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="d8a0d-169">Zie [geheimen in uw server-apps beheren met Azure-sleutel](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)beveiliging voor een praktisch voorbeeld van de manier waarop u uw app kunt beschermen.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-169">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="d8a0d-170">Een toegangstoken verkrijgen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8a0d-170">Get an access token using PowerShell</span></span>

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

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

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="d8a0d-171">Een toegangstoken verkrijgen met C\#</span><span class="sxs-lookup"><span data-stu-id="d8a0d-171">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="d8a0d-172">De volgende code is getest met Nuget Microsoft. Identity model. clients. ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-172">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="d8a0d-173">Maak een nieuwe consoletoepassing.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-173">Create a new console application.</span></span>

1. <span data-ttu-id="d8a0d-174">Installeer NuGet [Microsoft. Identity model. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="d8a0d-174">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>

1. <span data-ttu-id="d8a0d-175">Voeg de volgende regel toe:</span><span class="sxs-lookup"><span data-stu-id="d8a0d-175">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="d8a0d-176">Kopieer en plak de volgende code in uw app (Vergeet niet de drie variabelen bij te werken: `tenantId` , `clientId` , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="d8a0d-176">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

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

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="d8a0d-177">Een toegangstoken verkrijgen met python</span><span class="sxs-lookup"><span data-stu-id="d8a0d-177">Get an access token using Python</span></span>

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

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="d8a0d-178">Een toegangstoken verkrijgen met krul</span><span class="sxs-lookup"><span data-stu-id="d8a0d-178">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="d8a0d-179">Krul is vooraf geïnstalleerd op Windows 10, versies 1803 en hoger.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-179">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="d8a0d-180">Download en installeer het hulpprogramma rechtstreeks vanaf de website van de [officiële krul](https://curl.haxx.se/windows/)voor andere versies van Windows.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-180">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="d8a0d-181">Open een opdrachtprompt en stel CLIENT_ID in op de ID van uw Azure-toepassing.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-181">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>

1. <span data-ttu-id="d8a0d-182">Stel CLIENT_SECRET in op uw Azure-toepassing Secret.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-182">Set CLIENT_SECRET to your Azure application secret.</span></span>

1. <span data-ttu-id="d8a0d-183">Stel TENANT_ID in op de Azure-TENANT-ID van de klant die de app wil gebruiken voor toegang tot Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-183">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft 365 Defender.</span></span>

1. <span data-ttu-id="d8a0d-184">Voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="d8a0d-184">Run the following command:</span></span>

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   <span data-ttu-id="d8a0d-185">Een succesvolle reactie ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="d8a0d-185">A successful response will look like this:</span></span>

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a><span data-ttu-id="d8a0d-186">Het token valideren</span><span class="sxs-lookup"><span data-stu-id="d8a0d-186">Validate the token</span></span>

1. <span data-ttu-id="d8a0d-187">Kopieer de token en plak deze in de [JSON Web token validator-website,](https://jwt.ms) om deze te decoderen.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-187">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>

1. <span data-ttu-id="d8a0d-188">Zorg ervoor dat de *claim claim* binnen het genummerde token de gewenste machtigingen bevat.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-188">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

   <span data-ttu-id="d8a0d-189">In de volgende afbeelding ziet u een versleuteld token dat u hebt verkregen uit een app, met `Incidents.Read.All` , `Incidents.ReadWrite.All` en `AdvancedHunting.Read.All` machtigingen:</span><span class="sxs-lookup"><span data-stu-id="d8a0d-189">In the following image, you can see a decoded token acquired from an app, with `Incidents.Read.All`, `Incidents.ReadWrite.All`, and `AdvancedHunting.Read.All` permissions:</span></span>

   ![Afbeelding van validatie van tokens](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="d8a0d-191">Het token gebruiken voor toegang tot de Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="d8a0d-191">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="d8a0d-192">Kies de API die u wilt gebruiken (incidenten of geavanceerde jacht).</span><span class="sxs-lookup"><span data-stu-id="d8a0d-192">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="d8a0d-193">Zie [ondersteunde Microsoft 365 Defender-api's](api-supported.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-193">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>

2. <span data-ttu-id="d8a0d-194">In het HTTP-verzoek dat u gaat verzenden, stelt u de autorisatie header in op `"Bearer" <token>` het autorisatieschema en *token* dat uw gevalideerde token is. </span><span class="sxs-lookup"><span data-stu-id="d8a0d-194">In the http request you are about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>

3. <span data-ttu-id="d8a0d-195">Het token vervalt binnen één uur.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-195">The token will expire within one hour.</span></span> <span data-ttu-id="d8a0d-196">U kunt meer dan één verzoek verzenden vanaf dit tijdstip met hetzelfde token.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-196">You can send more than one request during this time with the same token.</span></span>

<span data-ttu-id="d8a0d-197">In het volgende voorbeeld ziet u hoe u een aanvraag verzendt voor het aanvragen van een lijst met incidenten **met C#**.</span><span class="sxs-lookup"><span data-stu-id="d8a0d-197">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="d8a0d-198">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="d8a0d-198">Related articles</span></span>

- [<span data-ttu-id="d8a0d-199">Overzicht van Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="d8a0d-199">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="d8a0d-200">Toegang tot de Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="d8a0d-200">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="d8a0d-201">Een ' Hallo wereld '-toepassing maken</span><span class="sxs-lookup"><span data-stu-id="d8a0d-201">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="d8a0d-202">Een app maken om toegang te krijgen tot Microsoft 365 Defender-Api's namens een gebruiker</span><span class="sxs-lookup"><span data-stu-id="d8a0d-202">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="d8a0d-203">Een app maken met toegang met meerdere tenants voor partners van Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8a0d-203">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="d8a0d-204">Meer informatie over API-limieten en licenties</span><span class="sxs-lookup"><span data-stu-id="d8a0d-204">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="d8a0d-205">Meer informatie over foutcodes</span><span class="sxs-lookup"><span data-stu-id="d8a0d-205">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="d8a0d-206">Geheimen in uw server-apps beheren met Azure-sleutel kluis</span><span class="sxs-lookup"><span data-stu-id="d8a0d-206">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="d8a0d-207">OAuth 2,0-autorisatie voor gebruikersaanmelding en API-toegang</span><span class="sxs-lookup"><span data-stu-id="d8a0d-207">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
