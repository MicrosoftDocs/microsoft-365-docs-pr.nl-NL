---
title: Een app maken voor toegang Microsoft 365 Defender zonder een gebruiker
description: Meer informatie over het maken van een app voor toegang Microsoft 365 Defender zonder een gebruiker.
keywords: app, access, api, create
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
ms.openlocfilehash: 8ffa04492f42f7e1ee5f3fc7fadad963e6bb7fbe
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059641"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a><span data-ttu-id="1fc73-104">Een app maken voor toegang Microsoft 365 Defender zonder een gebruiker</span><span class="sxs-lookup"><span data-stu-id="1fc73-104">Create an app to access Microsoft 365 Defender without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1fc73-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="1fc73-105">**Applies to:**</span></span>

- <span data-ttu-id="1fc73-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1fc73-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1fc73-107">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="1fc73-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1fc73-108">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="1fc73-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="1fc73-109">Op deze pagina wordt beschreven hoe u een toepassing maakt om programmatische toegang te krijgen tot Microsoft 365 Defender zonder een gedefinieerde gebruiker, bijvoorbeeld als u een daemon- of achtergrondservice maakt.</span><span class="sxs-lookup"><span data-stu-id="1fc73-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender without a defined user—for example, if you're creating a daemon or background service.</span></span>

<span data-ttu-id="1fc73-110">Als u programmatische toegang nodig hebt tot Microsoft 365 Defender namens een of meer gebruikers, zie Een app maken voor toegang tot Microsoft 365 Defender-API's namens een gebruiker en Een app maken met partnertoegang tot [Microsoft 365 Defender-API's.](api-partner-access.md) [](api-create-app-user-context.md)</span><span class="sxs-lookup"><span data-stu-id="1fc73-110">If you need programmatic access to Microsoft 365 Defender on behalf of one or more users, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md) and [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).</span></span> <span data-ttu-id="1fc73-111">Zie Aan de slag als u niet zeker weet welk type toegang u nodig [hebt.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="1fc73-111">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="1fc73-112">Microsoft 365 In Defender worden veel van de gegevens en acties via een set programmatische API's openbaar.</span><span class="sxs-lookup"><span data-stu-id="1fc73-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="1fc73-113">Met deze API's kunt u werkstromen automatiseren en gebruikmaken van Microsoft 365 de mogelijkheden van Defender.</span><span class="sxs-lookup"><span data-stu-id="1fc73-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="1fc73-114">Voor deze API-toegang is OAuth2.0-verificatie vereist.</span><span class="sxs-lookup"><span data-stu-id="1fc73-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="1fc73-115">Zie [OAuth 2.0 Autorisatiecode](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)voor Flow.</span><span class="sxs-lookup"><span data-stu-id="1fc73-115">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="1fc73-116">Over het algemeen moet u de volgende stappen nemen om deze API's te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="1fc73-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="1fc73-117">Maak een Azure Active Directory (Azure AD)-toepassing.</span><span class="sxs-lookup"><span data-stu-id="1fc73-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="1fc73-118">Een toegangs token krijgen met deze toepassing.</span><span class="sxs-lookup"><span data-stu-id="1fc73-118">Get an access token using this application.</span></span>
- <span data-ttu-id="1fc73-119">Gebruik het token om toegang te krijgen Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="1fc73-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="1fc73-120">In dit artikel wordt uitgelegd hoe u:</span><span class="sxs-lookup"><span data-stu-id="1fc73-120">This article explains how to:</span></span>

- <span data-ttu-id="1fc73-121">Een Azure AD-toepassing maken</span><span class="sxs-lookup"><span data-stu-id="1fc73-121">Create an Azure AD application</span></span>
- <span data-ttu-id="1fc73-122">Een toegangs token voor Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1fc73-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="1fc73-123">Valideer het token.</span><span class="sxs-lookup"><span data-stu-id="1fc73-123">Validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="1fc73-124">Een app maken</span><span class="sxs-lookup"><span data-stu-id="1fc73-124">Create an app</span></span>

1. <span data-ttu-id="1fc73-125">Meld u aan [bij Azure](https://portal.azure.com) als gebruiker met de **rol Globale** beheerder.</span><span class="sxs-lookup"><span data-stu-id="1fc73-125">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="1fc73-126">Navigeer **naar Azure Active Directory**  >  **app-registraties Nieuwe**  >  **registratie**.</span><span class="sxs-lookup"><span data-stu-id="1fc73-126">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Afbeelding van Microsoft Azure en navigatie naar toepassingsregistratie](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="1fc73-128">Kies in het formulier een naam voor uw toepassing en selecteer vervolgens **Registreren.**</span><span class="sxs-lookup"><span data-stu-id="1fc73-128">In the form, choose a name for your application, then select **Register**.</span></span>

4. <span data-ttu-id="1fc73-129">Selecteer op uw **toepassingspagina API-machtigingen** Machtigingen toevoegen Api's die mijn organisatie gebruikt, > gebruiken, typ Microsoft Threat Protection  >    >   en selecteer **Microsoft Threat Protection.** </span><span class="sxs-lookup"><span data-stu-id="1fc73-129">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="1fc73-130">Uw app heeft nu toegang tot Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="1fc73-130">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="1fc73-131">*Microsoft Threat Protection* is een voormalige naam voor Microsoft 365 Defender en wordt niet weergegeven in de oorspronkelijke lijst.</span><span class="sxs-lookup"><span data-stu-id="1fc73-131">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="1fc73-132">U moet beginnen met het schrijven van de naam in het tekstvak om deze weer te geven.</span><span class="sxs-lookup"><span data-stu-id="1fc73-132">You need to start writing its name in the text box to see it appear.</span></span>

   ![Afbeelding van API-machtigingsselectie](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="1fc73-134">Selecteer **Toepassingsmachtigingen.**</span><span class="sxs-lookup"><span data-stu-id="1fc73-134">Select **Application permissions**.</span></span> <span data-ttu-id="1fc73-135">Kies de relevante machtigingen voor uw scenario (bijvoorbeeld **Incident.Read.All)** en selecteer **vervolgens Machtigingen toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="1fc73-135">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![Afbeelding van API-toegang en API-selectie](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="1fc73-137">U moet de relevante machtigingen voor uw scenario selecteren.</span><span class="sxs-lookup"><span data-stu-id="1fc73-137">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="1fc73-138">*Alle incidenten lezen* is slechts een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="1fc73-138">*Read all incidents* is just an example.</span></span> <span data-ttu-id="1fc73-139">Als u wilt bepalen welke machtiging u nodig hebt, kijkt u naar **de sectie** Machtigingen in de API die u wilt bellen.</span><span class="sxs-lookup"><span data-stu-id="1fc73-139">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="1fc73-140">Als u bijvoorbeeld geavanceerde [query's wilt uitvoeren,](api-advanced-hunting.md)selecteert u de machtiging Geavanceerde query's uitvoeren. als [u een apparaat wilt isoleren,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)selecteert u de machtiging 'Machine isoleren'.</span><span class="sxs-lookup"><span data-stu-id="1fc73-140">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="1fc73-141">Selecteer **Beheerdersmachtiging verlenen.**</span><span class="sxs-lookup"><span data-stu-id="1fc73-141">Select **Grant admin consent**.</span></span> <span data-ttu-id="1fc73-142">Telkens wanneer u een machtiging toevoegt, moet u Toestemming van beheerder **verlenen selecteren** om deze van kracht te laten worden.</span><span class="sxs-lookup"><span data-stu-id="1fc73-142">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Afbeelding van machtigingen verlenen](../../media/grant-consent.PNG)

7. <span data-ttu-id="1fc73-144">Als u een geheim aan de toepassing wilt toevoegen, selecteert u Certificaten **& geheimen,** voegt u een beschrijving toe aan het geheim en selecteert u **Vervolgens Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="1fc73-144">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="1fc73-145">Nadat u Toevoegen **hebt geselecteerd,** **selecteert u de gegenereerde geheime waarde kopiëren.**</span><span class="sxs-lookup"><span data-stu-id="1fc73-145">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="1fc73-146">U kunt de geheime waarde niet meer ophalen nadat u bent weggehaald.</span><span class="sxs-lookup"><span data-stu-id="1fc73-146">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Afbeelding van app-sleutel maken](../../media/webapp-create-key2.png)

8. <span data-ttu-id="1fc73-148">Neem uw toepassings-id en uw tenant-id op een veilige plaats op.</span><span class="sxs-lookup"><span data-stu-id="1fc73-148">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="1fc73-149">Ze worden weergegeven onder **Overzicht** op uw toepassingspagina.</span><span class="sxs-lookup"><span data-stu-id="1fc73-149">They're listed under **Overview** on your application page.</span></span>

   ![Afbeelding van gemaakte app-id](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="1fc73-151">Alleen **voor Microsoft 365 Defender Partners:** Volg deze instructies voor partnertoegang via de api's van Microsoft 365 Defender, stel uw app in op multiten tenant, zodat deze beschikbaar is in alle tenants zodra u toestemming van de beheerder hebt ontvangen. [](./api-partner-access.md)</span><span class="sxs-lookup"><span data-stu-id="1fc73-151">**For Microsoft 365 Defender Partners only**: [Follow these instructions](./api-partner-access.md) for partner access through the Microsoft 365 Defender APIs, set your app to be multi-tenant, so it can be available in all tenants once you receive admin consent.</span></span> <span data-ttu-id="1fc73-152">Partnertoegang is **vereist** voor apps van derden, bijvoorbeeld als u een app maakt die is bedoeld voor gebruik in tenants van meerdere klanten.</span><span class="sxs-lookup"><span data-stu-id="1fc73-152">Partner access is **required** for third-party apps—for example, if you create an app that is intended to run in multiple customers' tenants.</span></span> <span data-ttu-id="1fc73-153">Dit is **niet vereist** als u een service maakt die u alleen in uw tenant wilt uitvoeren, zoals een toepassing voor eigen gebruik die alleen met uw eigen gegevens werkt.</span><span class="sxs-lookup"><span data-stu-id="1fc73-153">It is **not required** if you create a service that you want to run in your tenant only, such as an application for your own usage that will only interact with your own data.</span></span> <span data-ttu-id="1fc73-154">De app instellen op multi-tenant:</span><span class="sxs-lookup"><span data-stu-id="1fc73-154">To set your app to be multi-tenant:</span></span>

    - <span data-ttu-id="1fc73-155">Ga naar **Verificatie** en voeg deze toe https://portal.azure.com als **omleidings-URI.**</span><span class="sxs-lookup"><span data-stu-id="1fc73-155">Go to **Authentication**, and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="1fc73-156">Selecteer onder aan de pagina, onder **Ondersteunde accounttypen,** de **accounts in** een organisatiemaptoepassing voor uw multi-tenant-app.</span><span class="sxs-lookup"><span data-stu-id="1fc73-156">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="1fc73-157">Aangezien uw toepassing samenwerkt met Microsoft 365 Defender namens uw gebruikers, moet deze worden goedgekeurd voor elke tenant waarvoor u deze wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1fc73-157">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

    <span data-ttu-id="1fc73-158">De globale beheerder van Active Directory voor elke tenant moet de toestemmingskoppeling selecteren en uw app goedkeuren.</span><span class="sxs-lookup"><span data-stu-id="1fc73-158">The Active Directory global admin for each tenant needs to select the consent link and approve your app.</span></span>

    <span data-ttu-id="1fc73-159">De toestemmingskoppeling heeft de volgende structuur:</span><span class="sxs-lookup"><span data-stu-id="1fc73-159">The consent link has the following structure:</span></span>

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="1fc73-160">De cijfers moeten `00000000-0000-0000-0000-000000000000` worden vervangen door uw toepassings-id.</span><span class="sxs-lookup"><span data-stu-id="1fc73-160">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>  

<span data-ttu-id="1fc73-161">**Klaar!**</span><span class="sxs-lookup"><span data-stu-id="1fc73-161">**Done!**</span></span> <span data-ttu-id="1fc73-162">U hebt een toepassing geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="1fc73-162">You've successfully registered an application!</span></span> <span data-ttu-id="1fc73-163">Zie hieronder voorbeelden voor het verkrijgen en valideren van tokens.</span><span class="sxs-lookup"><span data-stu-id="1fc73-163">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="1fc73-164">Een toegangs token krijgen</span><span class="sxs-lookup"><span data-stu-id="1fc73-164">Get an access token</span></span>

<span data-ttu-id="1fc73-165">Zie de Azure AD-zelfstudie voor meer Azure Active Directory over uw [tokens.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="1fc73-165">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1fc73-166">Hoewel de voorbeelden in deze sectie u aanmoedigen om geheime waarden te plakken voor testdoeleinden, moet u nooit geheimen **hardcoderen** in een toepassing die in productie wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="1fc73-166">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="1fc73-167">Een derde partij kan uw geheim gebruiken om toegang te krijgen tot bronnen.</span><span class="sxs-lookup"><span data-stu-id="1fc73-167">A third party could use your secret to access resources.</span></span> <span data-ttu-id="1fc73-168">U kunt de geheimen van uw app beveiligen met Behulp van [Azure Key Vault.](/azure/key-vault/general/about-keys-secrets-certificates)</span><span class="sxs-lookup"><span data-stu-id="1fc73-168">You can help keep your app's secrets secure by using [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="1fc73-169">Zie Geheimen beheren in uw server-apps met Azure Key Vault voor een praktisch voorbeeld van hoe u uw app [kunt beveiligen.](/learn/modules/manage-secrets-with-azure-key-vault/)</span><span class="sxs-lookup"><span data-stu-id="1fc73-169">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="1fc73-170">Toegangs token krijgen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="1fc73-170">Get an access token using PowerShell</span></span>

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

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="1fc73-171">Toegangs token krijgen met C\#</span><span class="sxs-lookup"><span data-stu-id="1fc73-171">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="1fc73-172">De volgende code is getest met Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="1fc73-172">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="1fc73-173">Een nieuwe consoletoepassing maken.</span><span class="sxs-lookup"><span data-stu-id="1fc73-173">Create a new console application.</span></span>

1. <span data-ttu-id="1fc73-174">Installeer NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="1fc73-174">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>

1. <span data-ttu-id="1fc73-175">Voeg de volgende regel toe:</span><span class="sxs-lookup"><span data-stu-id="1fc73-175">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="1fc73-176">Kopieer en plak de volgende code in uw app (vergeet niet om de drie variabelen bij te werken: `tenantId` , `clientId` , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="1fc73-176">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

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

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="1fc73-177">Toegangs token krijgen met Python</span><span class="sxs-lookup"><span data-stu-id="1fc73-177">Get an access token using Python</span></span>

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.security.microsoft.com'

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

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="1fc73-178">Een toegangs token krijgen met behulp van krul</span><span class="sxs-lookup"><span data-stu-id="1fc73-178">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="1fc73-179">Curl is vooraf geïnstalleerd op Windows 10 versie 1803 en hoger.</span><span class="sxs-lookup"><span data-stu-id="1fc73-179">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="1fc73-180">Voor andere versies van Windows kunt u het hulpprogramma rechtstreeks downloaden en installeren vanaf de [officiële krullenwebsite.](https://curl.haxx.se/windows/)</span><span class="sxs-lookup"><span data-stu-id="1fc73-180">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="1fc73-181">Open een opdrachtprompt en stel CLIENT_ID in op uw Azure-toepassings-id.</span><span class="sxs-lookup"><span data-stu-id="1fc73-181">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>

1. <span data-ttu-id="1fc73-182">Stel CLIENT_SECRET in op uw Azure-toepassingsgeheim.</span><span class="sxs-lookup"><span data-stu-id="1fc73-182">Set CLIENT_SECRET to your Azure application secret.</span></span>

1. <span data-ttu-id="1fc73-183">Stel TENANT_ID azure tenant-id in van de klant die uw app wil gebruiken om toegang te krijgen tot Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="1fc73-183">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft 365 Defender.</span></span>

1. <span data-ttu-id="1fc73-184">Voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="1fc73-184">Run the following command:</span></span>

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   <span data-ttu-id="1fc73-185">Een succesvol antwoord ziet er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="1fc73-185">A successful response will look like this:</span></span>

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a><span data-ttu-id="1fc73-186">Het token valideren</span><span class="sxs-lookup"><span data-stu-id="1fc73-186">Validate the token</span></span>

1. <span data-ttu-id="1fc73-187">Kopieer en plak het token in [de JSON web token validator-website, JWT,](https://jwt.ms) om het te decoderen.</span><span class="sxs-lookup"><span data-stu-id="1fc73-187">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>

1. <span data-ttu-id="1fc73-188">Zorg ervoor dat de *claim rollen* in het gedecodeerde token de gewenste machtigingen bevat.</span><span class="sxs-lookup"><span data-stu-id="1fc73-188">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

   <span data-ttu-id="1fc73-189">In de volgende afbeelding ziet u een gedecodeerd token dat is verkregen van een app, met `Incidents.Read.All` `Incidents.ReadWrite.All` , en `AdvancedHunting.Read.All` machtigingen:</span><span class="sxs-lookup"><span data-stu-id="1fc73-189">In the following image, you can see a decoded token acquired from an app, with `Incidents.Read.All`, `Incidents.ReadWrite.All`, and `AdvancedHunting.Read.All` permissions:</span></span>

   ![Afbeelding van tokenvalidatie](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="1fc73-191">Het token gebruiken om toegang te krijgen tot Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="1fc73-191">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="1fc73-192">Kies de API die u wilt gebruiken (incidenten of geavanceerd zoeken).</span><span class="sxs-lookup"><span data-stu-id="1fc73-192">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="1fc73-193">Zie Ondersteunde [api's Microsoft 365 Defender voor meer informatie.](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="1fc73-193">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>

2. <span data-ttu-id="1fc73-194">In de http-aanvraag die u wilt verzenden, stelt u de autorisatiekop in op , Bearer is het autorisatieschema en het `"Bearer" <token>` *token*  dat uw gevalideerde token is.</span><span class="sxs-lookup"><span data-stu-id="1fc73-194">In the http request you are about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>

3. <span data-ttu-id="1fc73-195">Het token verloopt binnen een uur.</span><span class="sxs-lookup"><span data-stu-id="1fc73-195">The token will expire within one hour.</span></span> <span data-ttu-id="1fc73-196">U kunt in deze periode meerdere aanvragen met hetzelfde token verzenden.</span><span class="sxs-lookup"><span data-stu-id="1fc73-196">You can send more than one request during this time with the same token.</span></span>

<span data-ttu-id="1fc73-197">In het volgende voorbeeld ziet u hoe u een aanvraag verzendt om een lijst met incidenten te krijgen **met C#**.</span><span class="sxs-lookup"><span data-stu-id="1fc73-197">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="1fc73-198">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="1fc73-198">Related articles</span></span>

- [<span data-ttu-id="1fc73-199">Microsoft 365 Overzicht van DEFENDER-API's</span><span class="sxs-lookup"><span data-stu-id="1fc73-199">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="1fc73-200">Toegang tot Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="1fc73-200">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="1fc73-201">Een 'Hello world'-toepassing maken</span><span class="sxs-lookup"><span data-stu-id="1fc73-201">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="1fc73-202">Een app maken voor toegang Microsoft 365 Defender-API's namens een gebruiker</span><span class="sxs-lookup"><span data-stu-id="1fc73-202">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="1fc73-203">Een app maken met partnertoegang voor meerdere tenants Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="1fc73-203">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="1fc73-204">Meer informatie over API-limieten en -licenties</span><span class="sxs-lookup"><span data-stu-id="1fc73-204">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="1fc73-205">Foutcodes begrijpen</span><span class="sxs-lookup"><span data-stu-id="1fc73-205">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="1fc73-206">Geheimen beheren in uw server-apps met Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="1fc73-206">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="1fc73-207">OAuth 2.0-autorisatie voor gebruikers aanmelden en API-toegang</span><span class="sxs-lookup"><span data-stu-id="1fc73-207">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)