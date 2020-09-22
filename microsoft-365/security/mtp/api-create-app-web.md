---
title: Een app maken om toegang te krijgen tot Microsoft Threat Protection zonder een gebruiker
description: Meer informatie over het maken van een app voor toegang tot Microsoft Threat Protection zonder een gebruiker
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
ms.openlocfilehash: 57ba0eb77ccb855cc0c0224b5321f11809e21ae8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201417"
---
# <a name="create-an-app-to-access-microsoft-threat-protection-without-a-user"></a><span data-ttu-id="46e28-104">Een app maken om toegang te krijgen tot Microsoft Threat Protection zonder een gebruiker</span><span class="sxs-lookup"><span data-stu-id="46e28-104">Create an app to access Microsoft Threat Protection without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="46e28-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="46e28-105">**Applies to:**</span></span>
- <span data-ttu-id="46e28-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="46e28-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="46e28-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="46e28-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="46e28-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="46e28-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="46e28-109">Op deze pagina wordt beschreven hoe u een toepassing maakt om via een programma toegang te krijgen tot Microsoft Threat Protection zonder een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="46e28-109">This page describes how to create an application to get programmatic access to Microsoft Threat Protection without a user.</span></span> <span data-ttu-id="46e28-110">Als u toegang tot Microsoft Threat Protection voornaam van een gebruiker nodig hebt, raadpleegt u [toegang krijgen met gebruikerscontext](api-create-app-user-context.md).</span><span class="sxs-lookup"><span data-stu-id="46e28-110">If you need programmatic access to Microsoft Threat Protection on behalf of a user, see [Get access with user context](api-create-app-user-context.md).</span></span> <span data-ttu-id="46e28-111">Als u niet zeker weet welke toegang u nodig hebt, raadpleegt u [aan de slag](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="46e28-111">If you are not sure which access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="46e28-112">Microsoft Threat Protection geeft veel van zijn gegevens en acties getoond via een set programmeer Api's.</span><span class="sxs-lookup"><span data-stu-id="46e28-112">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="46e28-113">Met deze Api's wordt u geholpen bij het automatiseren van werkstromen en innoveren op basis van de mogelijkheden van Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="46e28-113">Those APIs will help you automate work flows and innovate based on Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="46e28-114">Voor API-toegang is OAuth 2.0-authenticatie vereist.</span><span class="sxs-lookup"><span data-stu-id="46e28-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="46e28-115">Voor meer informatie raadpleegt u [OAuth 2,0 Authorization code flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="46e28-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="46e28-116">In het algemeen dient u de volgende stappen uit te voeren om de Api's te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="46e28-116">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="46e28-117">Maak een Azure AD-toepassing (Azure Active Directory).</span><span class="sxs-lookup"><span data-stu-id="46e28-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="46e28-118">U krijgt een toegangstoken met deze toepassing.</span><span class="sxs-lookup"><span data-stu-id="46e28-118">Get an access token using this application.</span></span>
- <span data-ttu-id="46e28-119">Gebruik het token om toegang te krijgen tot de Microsoft Threat Protection API.</span><span class="sxs-lookup"><span data-stu-id="46e28-119">Use the token to access Microsoft Threat Protection API.</span></span>

<span data-ttu-id="46e28-120">In dit artikel wordt uitgelegd hoe u een Azure AD-toepassing maakt, een toegangstoken krijgt voor Microsoft Threat Protection en het token valideert.</span><span class="sxs-lookup"><span data-stu-id="46e28-120">This article explains how to create an Azure AD application, get an access token to Microsoft Threat Protection, and validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="46e28-121">Een app maken</span><span class="sxs-lookup"><span data-stu-id="46e28-121">Create an app</span></span>

1. <span data-ttu-id="46e28-122">Meld u aan bij [Azure](https://portal.azure.com) met een gebruiker die de rol **globale beheerder** heeft.</span><span class="sxs-lookup"><span data-stu-id="46e28-122">Log on to [Azure](https://portal.azure.com) with a user that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="46e28-123">Ga naar de **Azure Active Directory**-  >  **app registraties**  >  **nieuwe registratie**.</span><span class="sxs-lookup"><span data-stu-id="46e28-123">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Afbeelding van Microsoft Azure en navigatie naar toepassing registreren](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="46e28-125">Kies in het registratieformulier een naam voor de toepassing en selecteer vervolgens **registreren**.</span><span class="sxs-lookup"><span data-stu-id="46e28-125">In the registration form, choose a name for your application, and then select **Register**.</span></span>

4. <span data-ttu-id="46e28-126">Als u de app wilt gebruiken voor toegang tot Microsoft Threat Protection en de machtigingen voor deze persoon wilt toewijzen, selecteert u op de Toepassingspagina **API-machtigingen**de optie API-  >  api's**toevoegen**  >  **Mijn organisatie gebruikt** >, typt u **Microsoft Threat Protection**en selecteert u vervolgens **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="46e28-126">To enable your app to access Microsoft Threat Protection and assign it permissions, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and then select **Microsoft Threat Protection**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="46e28-127">Microsoft Threat Protection wordt niet weergegeven in de oorspronkelijke lijst.</span><span class="sxs-lookup"><span data-stu-id="46e28-127">Microsoft Threat Protection does not appear in the original list.</span></span> <span data-ttu-id="46e28-128">U moet de naam ervan beginnen te schrijven in het tekstvak om de naam weer te geven.</span><span class="sxs-lookup"><span data-stu-id="46e28-128">You need to start writing its name in the text box to see it appear.</span></span>

   ![Afbeelding van API-toegang en API-selectie](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="46e28-130">Selecteer **Toepassingsmachtigingen** > Kies de relevante machtigingen voor uw scenario, bijvoorbeeld **incident. Read. all**, en selecteer vervolgens **add machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="46e28-130">Select **Application permissions** > Choose the relevant permissions for your scenario, e.g. **Incident.Read.All**, and then select **Add permissions**.</span></span>

   ![Afbeelding van API-toegang en API-selectie](../../media/request-api-permissions.PNG)

    >[!NOTE]
    ><span data-ttu-id="46e28-132">U moet de relevante machtigingen voor uw scenario selecteren, **' alle incidenten lezen '** is slechts een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="46e28-132">You need to select the relevant permissions for your scenario, **'Read all incidents'** is just an example.</span></span> <span data-ttu-id="46e28-133">Om te bepalen welke machtigingen u nodig hebt, raadpleegt u de sectie **machtigingen** in de API die u wilt bellen.</span><span class="sxs-lookup"><span data-stu-id="46e28-133">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="46e28-134">Selecteer **toestemming verlenen**.</span><span class="sxs-lookup"><span data-stu-id="46e28-134">Select **Grant consent**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="46e28-135">Telkens wanneer u een machtiging toevoegt, moet u **toestemming verlenen** om de nieuwe machtiging te activeren.</span><span class="sxs-lookup"><span data-stu-id="46e28-135">Every time you add a permission, you must select **Grant consent** for the new permission to take effect.</span></span>

    ![Afbeelding van machtiging verlenen](../../media/grant-consent.PNG)

6. <span data-ttu-id="46e28-137">Als u een geheim wilt toevoegen aan de toepassing, selecteert u **certificaten & geheimen**, voegt u een beschrijving toe aan het geheim en selecteert u vervolgens **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="46e28-137">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, and then select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="46e28-138">Wanneer u **toevoegen**hebt geselecteerd, selecteert u **de gegenereerde geheime waarde kopiëren**.</span><span class="sxs-lookup"><span data-stu-id="46e28-138">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="46e28-139">U kunt deze waarde niet meer ophalen wanneer u niets hebt.</span><span class="sxs-lookup"><span data-stu-id="46e28-139">You won't be able to retrieve this value after you leave.</span></span>

    ![Afbeelding van de sleutel app maken](../../media/webapp-create-key2.png)

7. <span data-ttu-id="46e28-141">Noteer de toepassings-ID en uw Tenant-ID.</span><span class="sxs-lookup"><span data-stu-id="46e28-141">Write down your application ID and your tenant ID.</span></span> <span data-ttu-id="46e28-142">Ga op de pagina toepassing naar **overzicht** en kopieer de volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="46e28-142">On your application page, go to **Overview** and copy the following.</span></span>

   ![Afbeelding van gemaakte app-id](../../media/app-and-tenant-ids.png)

8. <span data-ttu-id="46e28-144">**Alleen voor Microsoft Threat Protection-partners**.</span><span class="sxs-lookup"><span data-stu-id="46e28-144">**For Microsoft Threat Protection Partners only**.</span></span> <span data-ttu-id="46e28-145">[Volg de instructies hier](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access).</span><span class="sxs-lookup"><span data-stu-id="46e28-145">[Follow the instructions here](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access).</span></span> <span data-ttu-id="46e28-146">U kunt instellen dat uw app meerdere tenants (beschikbaar na instemming) moet zijn.</span><span class="sxs-lookup"><span data-stu-id="46e28-146">Set your app to be multi-tenanted (available in all tenants after consent).</span></span> <span data-ttu-id="46e28-147">Dit is **vereist** voor apps van derden (bijvoorbeeld als u een app maakt die bedoeld is om te worden uitgevoerd in de Tenant van meerdere klanten).</span><span class="sxs-lookup"><span data-stu-id="46e28-147">This is **required** for third-party apps (for example, if you create an app that is intended to run in multiple customers' tenant).</span></span> <span data-ttu-id="46e28-148">U **hoeft dit niet te doen** als u een service maakt die u alleen in uw Tenant wilt uitvoeren (als u bijvoorbeeld een toepassing maakt voor uw eigen gebruik, zodat u alleen uw eigen gegevens kunt gebruiken).</span><span class="sxs-lookup"><span data-stu-id="46e28-148">This is **not required** if you create a service that you want to run in your tenant only (for example, if you create an application for your own usage that will only interact with your own data).</span></span> <span data-ttu-id="46e28-149">Uw app instellen voor meerdere tenants:</span><span class="sxs-lookup"><span data-stu-id="46e28-149">To set your app to be multi-tenanted:</span></span>

    - <span data-ttu-id="46e28-150">Ga naar **verificatie**en voeg toe https://portal.azure.com als de **omleidings-URL**.</span><span class="sxs-lookup"><span data-stu-id="46e28-150">Go to **Authentication**, and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="46e28-151">Onder aan de pagina, onder **ondersteunde accounttypen**, selecteert u de **accounts in een** toepassing voor de organisatie van de toepassing voor uw app met meerdere tenants.</span><span class="sxs-lookup"><span data-stu-id="46e28-151">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="46e28-152">U moet uw toepassing in elke Tenant goedgekeurd hebben, waar u deze wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="46e28-152">You need your application to be approved in each tenant where you intend to use it.</span></span> <span data-ttu-id="46e28-153">Dit komt doordat de toepassing Microsoft Threat Protection bijdraagt namens de klant.</span><span class="sxs-lookup"><span data-stu-id="46e28-153">This is because your application interacts Microsoft Threat Protection on behalf of your customer.</span></span>

    <span data-ttu-id="46e28-154">U (of de klant als u een app van derden schrijft), moet u de instemming koppeling selecteren en uw app goedkeuren.</span><span class="sxs-lookup"><span data-stu-id="46e28-154">You (or your customer if you are writing a third-party app) need to select the consent link and approve your app.</span></span> <span data-ttu-id="46e28-155">De toestemming moet worden uitgevoerd met een gebruiker die beheerdersrechten heeft in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="46e28-155">The consent should be done with a user who has administrative privileges in Active Directory.</span></span>

    <span data-ttu-id="46e28-156">De koppeling toestemming wordt als volgt gevormd:</span><span class="sxs-lookup"><span data-stu-id="46e28-156">The consent link is formed as follows:</span></span> 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="46e28-157">Waarbij 00000000-0000-0000-0000-000000000000 wordt vervangen door uw toepassings-ID.</span><span class="sxs-lookup"><span data-stu-id="46e28-157">Where 00000000-0000-0000-0000-000000000000 is replaced with your application ID.</span></span>


<span data-ttu-id="46e28-158">**Klaar!**</span><span class="sxs-lookup"><span data-stu-id="46e28-158">**Done!**</span></span> <span data-ttu-id="46e28-159">U hebt een toepassing geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="46e28-159">You have successfully registered an application!</span></span> <span data-ttu-id="46e28-160">Zie voorbeelden hieronder voor het verwerving van tokens en validatie.</span><span class="sxs-lookup"><span data-stu-id="46e28-160">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="46e28-161">Een toegangstoken verkrijgen</span><span class="sxs-lookup"><span data-stu-id="46e28-161">Get an access token</span></span>

<span data-ttu-id="46e28-162">Zie voor meer informatie over Azure AD-tokens de [zelfstudie voor Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="46e28-162">For more details on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="use-powershell"></a><span data-ttu-id="46e28-163">PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="46e28-163">Use PowerShell</span></span>

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

### <a name="use-c"></a><span data-ttu-id="46e28-164">Gebruik C#:</span><span class="sxs-lookup"><span data-stu-id="46e28-164">Use C#:</span></span>

<span data-ttu-id="46e28-165">De volgende code is getest met Nuget Microsoft. Identity model. clients. ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="46e28-165">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="46e28-166">Maak een nieuwe consoletoepassing.</span><span class="sxs-lookup"><span data-stu-id="46e28-166">Create a new console application.</span></span>
1. <span data-ttu-id="46e28-167">Installeer Nuget [Microsoft. Identity model. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="46e28-167">Install Nuget [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="46e28-168">Voegt u het volgende toe:</span><span class="sxs-lookup"><span data-stu-id="46e28-168">Add the following:</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="46e28-169">Kopieer en plak de volgende code in uw app (Vergeet niet de drie variabelen bij te werken: ```tenantId, appId, appSecret``` ):</span><span class="sxs-lookup"><span data-stu-id="46e28-169">Copy and paste the following code in your app (don't forget to update the three variables: ```tenantId, appId, appSecret```):</span></span>

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a><span data-ttu-id="46e28-170">Python gebruiken</span><span class="sxs-lookup"><span data-stu-id="46e28-170">Use Python</span></span> 

```
import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```
### <a name="use-curl"></a><span data-ttu-id="46e28-171">Krul gebruiken</span><span class="sxs-lookup"><span data-stu-id="46e28-171">Use Curl</span></span>

> [!NOTE]
> <span data-ttu-id="46e28-172">In de volgende procedure wordt ervan uitgegaan dat krul voor Windows al op uw computer is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="46e28-172">The following procedure assumes that Curl for Windows is already installed on your computer.</span></span>

1. <span data-ttu-id="46e28-173">Open een opdrachtprompt en stel CLIENT_ID in op de ID van uw Azure-toepassing.</span><span class="sxs-lookup"><span data-stu-id="46e28-173">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="46e28-174">Stel CLIENT_SECRET in op uw Azure-toepassing Secret.</span><span class="sxs-lookup"><span data-stu-id="46e28-174">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="46e28-175">Stel TENANT_ID in op de Azure-TENANT-ID van de klant die uw app wil gebruiken om toegang te krijgen tot Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="46e28-175">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft Threat Protection.</span></span>
1. <span data-ttu-id="46e28-176">Voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="46e28-176">Run the following command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="46e28-177">U krijgt een antwoord in de volgende vorm:</span><span class="sxs-lookup"><span data-stu-id="46e28-177">You will get an answer in the following form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="46e28-178">Het token valideren</span><span class="sxs-lookup"><span data-stu-id="46e28-178">Validate the token</span></span>

<span data-ttu-id="46e28-179">Zorg ervoor dat u het juiste token hebt:</span><span class="sxs-lookup"><span data-stu-id="46e28-179">Ensure that you got the correct token:</span></span>

1. <span data-ttu-id="46e28-180">Kopieer en plak het token dat u in de vorige stap hebt [JWT](https://jwt.ms) ontvangen, om dit te decoderen.</span><span class="sxs-lookup"><span data-stu-id="46e28-180">Copy and paste the token you got in the previous step into [JWT](https://jwt.ms) in order to decode it.</span></span>
1. <span data-ttu-id="46e28-181">Controleren of u een claim ontvangt met de gewenste machtigingen</span><span class="sxs-lookup"><span data-stu-id="46e28-181">Validate that you get a 'roles' claim with the desired permissions</span></span>
1. <span data-ttu-id="46e28-182">In de volgende afbeelding ziet u een versleuteld token dat u hebt verkregen uit een app met ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` en ```AdvancedHunting.Read.All``` machtigingen:</span><span class="sxs-lookup"><span data-stu-id="46e28-182">In the following image, you can see a decoded token acquired from an app with ```Incidents.Read.All```, ```Incidents.ReadWrite.All``` and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Afbeelding van validatie van tokens](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-threat-protection-api"></a><span data-ttu-id="46e28-184">Het token gebruiken om toegang te krijgen tot de Microsoft Threat Protection API</span><span class="sxs-lookup"><span data-stu-id="46e28-184">Use the token to access Microsoft Threat Protection API</span></span>

1. <span data-ttu-id="46e28-185">Kies de API die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="46e28-185">Choose the API you want to use.</span></span> <span data-ttu-id="46e28-186">Zie voor meer informatie [ondersteunde api's voor Microsoft Threat Protection](api-supported.md).</span><span class="sxs-lookup"><span data-stu-id="46e28-186">For more information, see [Supported Microsoft Threat Protection APIs](api-supported.md).</span></span>

2. <span data-ttu-id="46e28-187">Stel de autorisatie header in voor de HTTP-aanvraag die u verstuurt naar ' Bearer {token} ' (Bearer is het autorisatieschema).</span><span class="sxs-lookup"><span data-stu-id="46e28-187">Set the authorization header in the http request you send to "Bearer {token}" (Bearer is the authorization scheme).</span></span>

3. <span data-ttu-id="46e28-188">De verlooptijd van het token is één uur.</span><span class="sxs-lookup"><span data-stu-id="46e28-188">The expiration time of the token is one hour.</span></span> <span data-ttu-id="46e28-189">U kunt meer dan één aanvraag met hetzelfde token verzenden.</span><span class="sxs-lookup"><span data-stu-id="46e28-189">You can send more then one request with the same token.</span></span>

<span data-ttu-id="46e28-190">Hieronder ziet u een voorbeeld van het verzenden van een aanvraag voor het aanvragen van een lijst met incidenten **met C#**:</span><span class="sxs-lookup"><span data-stu-id="46e28-190">The following is an example of sending a request to get a list of incidents **using C#**:</span></span> 

```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="related-topics"></a><span data-ttu-id="46e28-191">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="46e28-191">Related topics</span></span>
- [<span data-ttu-id="46e28-192">Toegang tot de Microsoft Threat Protection-Api's</span><span class="sxs-lookup"><span data-stu-id="46e28-192">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="46e28-193">Toegang tot Microsoft Threat Protection met toepassingscontext</span><span class="sxs-lookup"><span data-stu-id="46e28-193">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="46e28-194">Microsoft Threat Protection met gebruikerscontext openen</span><span class="sxs-lookup"><span data-stu-id="46e28-194">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
