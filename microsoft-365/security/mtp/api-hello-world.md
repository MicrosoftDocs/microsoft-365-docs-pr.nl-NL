---
title: Hallo wereld voor Microsoft 365 Defender REST API
description: Leer hoe u een app maakt en een token gebruikt om toegang te krijgen tot de Microsoft 365 Defender-Api's
keywords: app, token, toegang, Aad, app, toepassing registreren, powershell, script, globale beheerder, machtiging, Microsoft 365 Defender
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
ms.openlocfilehash: b36a6acca5880a455a66b03b5355cdf1fb85b29b
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719308"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="2833e-104">Hallo wereld voor Microsoft 365 Defender REST API</span><span class="sxs-lookup"><span data-stu-id="2833e-104">Hello World for Microsoft 365 Defender REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2833e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2833e-105">**Applies to:**</span></span>

- <span data-ttu-id="2833e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2833e-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2833e-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="2833e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2833e-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="2833e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="2833e-109">Incidenten aanvragen met behulp van een eenvoudig PowerShell-script</span><span class="sxs-lookup"><span data-stu-id="2833e-109">Get incidents using a simple PowerShell script</span></span>

<span data-ttu-id="2833e-110">Het duurt 5 tot 10 minuten voordat het project is voltooid.</span><span class="sxs-lookup"><span data-stu-id="2833e-110">It should take 5 to 10 minutes to complete this project.</span></span> <span data-ttu-id="2833e-111">Deze tijds raming omvat het registreren van de toepassing en het toepassen van de code van het PowerShell-voorbeeldscript.</span><span class="sxs-lookup"><span data-stu-id="2833e-111">This time estimate includes registering the application, and applying the code from the PowerShell sample script.</span></span>

### <a name="register-an-app-in-azure-active-directory"></a><span data-ttu-id="2833e-112">Een app registreren in azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2833e-112">Register an app in Azure Active Directory</span></span>

1. <span data-ttu-id="2833e-113">Meld u aan bij [Azure](https://portal.azure.com) als een gebruiker met de rol van **globale beheerder** .</span><span class="sxs-lookup"><span data-stu-id="2833e-113">Sign in to [Azure](https://portal.azure.com) as a user with the **Global administrator** role.</span></span>

2. <span data-ttu-id="2833e-114">Ga naar de **Azure Active Directory**-  >  **app registraties**  >  **nieuwe registratie**.</span><span class="sxs-lookup"><span data-stu-id="2833e-114">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Afbeelding van Microsoft Azure en navigatie naar toepassing registreren](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="2833e-116">Kies in het registratieformulier een naam voor de toepassing en selecteer vervolgens **registreren**.</span><span class="sxs-lookup"><span data-stu-id="2833e-116">In the registration form, choose a name for your application, then select **Register**.</span></span> <span data-ttu-id="2833e-117">U moet een omleidings-URI selecteren optioneel.</span><span class="sxs-lookup"><span data-stu-id="2833e-117">Selecting a redirect URI is optional.</span></span> <span data-ttu-id="2833e-118">Dit voorbeeld is niet nodig.</span><span class="sxs-lookup"><span data-stu-id="2833e-118">You won't need one to complete this example.</span></span>

4. <span data-ttu-id="2833e-119">Selecteer op de pagina toepassingen de optie **API-machtigingen**  >  **toevoegen**  >  **Mijn organisatie gebruikt** >, typ **Microsoft Threat Protection** en selecteer **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="2833e-119">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="2833e-120">Uw app heeft nu toegang tot Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="2833e-120">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="2833e-121">*Microsoft Threat Protection* is een voormalig naam voor microsoft 365 Defender en wordt niet weergegeven in de oorspronkelijke lijst.</span><span class="sxs-lookup"><span data-stu-id="2833e-121">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="2833e-122">U moet de naam ervan beginnen te schrijven in het tekstvak om de naam weer te geven.</span><span class="sxs-lookup"><span data-stu-id="2833e-122">You need to start writing its name in the text box to see it appear.</span></span>
   <span data-ttu-id="2833e-123">![Afbeelding van selectie van API-machtigingen](../../media/apis-in-my-org-tab.PNG)</span><span class="sxs-lookup"><span data-stu-id="2833e-123">![Image of API permission selection](../../media/apis-in-my-org-tab.PNG)</span></span>

   - <span data-ttu-id="2833e-124">Kies **Application permissions**  >  **. Read. all** en selecteer **add machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="2833e-124">Choose **Application permissions** > **Incident.Read.All** and select **Add permissions**.</span></span>

   ![Afbeelding van API-toegang en API-selectie](../../media/request-api-permissions.PNG)

5. <span data-ttu-id="2833e-126">Selecteer **beheerder toestemming verlenen**.</span><span class="sxs-lookup"><span data-stu-id="2833e-126">Select **Grant admin consent**.</span></span> <span data-ttu-id="2833e-127">Telkens wanneer u een machtiging toevoegt, moet u de machtiging **beheerder toestemming verlenen** selecteren om de machtiging van kracht te laten worden.</span><span class="sxs-lookup"><span data-stu-id="2833e-127">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Afbeelding van machtiging verlenen](../../media/grant-consent.PNG)

6. <span data-ttu-id="2833e-129">Voeg een geheim toe aan de toepassing.</span><span class="sxs-lookup"><span data-stu-id="2833e-129">Add a secret to the application.</span></span> <span data-ttu-id="2833e-130">Selecteer **certificaten & geheimen**, voeg een beschrijving toe aan het geheim en selecteer vervolgens **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="2833e-130">Select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="2833e-131">Wanneer u **toevoegen** hebt geselecteerd, selecteert u **de gegenereerde geheime waarde kopiëren**.</span><span class="sxs-lookup"><span data-stu-id="2833e-131">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="2833e-132">U kunt de geheime waarde niet meer ophalen wanneer u niets hebt.</span><span class="sxs-lookup"><span data-stu-id="2833e-132">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Afbeelding van de sleutel app maken](../../media/webapp-create-key2.png)

7. <span data-ttu-id="2833e-134">Registreer uw toepassings-ID en uw Tenant-ID ergens veilig.</span><span class="sxs-lookup"><span data-stu-id="2833e-134">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="2833e-135">Ze worden weergegeven onder **overzicht** op de pagina toepassing.</span><span class="sxs-lookup"><span data-stu-id="2833e-135">They're listed under **Overview** on your application page.</span></span>

   ![Afbeelding van gemaakte app-id](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a><span data-ttu-id="2833e-137">Een token verkrijgen met behulp van de app en de token gebruiken om toegang te krijgen tot de API</span><span class="sxs-lookup"><span data-stu-id="2833e-137">Get a token using the app and use the token to access the API</span></span>

<span data-ttu-id="2833e-138">Zie voor meer informatie over Azure Active Directory-tokens de [zelfstudie voor Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="2833e-138">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2833e-139">Hoewel het voorbeeld in deze demo-app u adviseert om te plakken in uw geheime waarde voor testdoeleinden, moet u **nooit hardcodee geheimen** verleggen in een toepassing die wordt uitgevoerd in de productie.</span><span class="sxs-lookup"><span data-stu-id="2833e-139">Although the example in this demo app encourage you to paste in your secret value for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="2833e-140">Een derde partij kon uw geheim gebruiken om toegang te krijgen tot bronnen.</span><span class="sxs-lookup"><span data-stu-id="2833e-140">A third party could use your secret to access resources.</span></span> <span data-ttu-id="2833e-141">U kunt de geheimen van uw apps veilig houden met behulp van [Azure Key-kluis](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span><span class="sxs-lookup"><span data-stu-id="2833e-141">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="2833e-142">Zie [geheimen in uw server-apps beheren met Azure-sleutel](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)beveiliging voor een praktisch voorbeeld van de manier waarop u uw app kunt beschermen.</span><span class="sxs-lookup"><span data-stu-id="2833e-142">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

1. <span data-ttu-id="2833e-143">Kopieer het onderstaande script en plak dit in uw favoriete teksteditor.</span><span class="sxs-lookup"><span data-stu-id="2833e-143">Copy the script below and paste it into your favorite text editor.</span></span> <span data-ttu-id="2833e-144">Opslaan als **Get-Token.ps1**.</span><span class="sxs-lookup"><span data-stu-id="2833e-144">Save as **Get-Token.ps1**.</span></span> <span data-ttu-id="2833e-145">U kunt de code ook uitvoeren als-is in PowerShell ISE, maar u moet deze opslaan, omdat we de code opnieuw moeten uitvoeren wanneer we het script voor het aanvullen van incidenten gebruiken in de volgende sectie.</span><span class="sxs-lookup"><span data-stu-id="2833e-145">You can also run the code as-is in PowerShell ISE, but you should save it, because we'll need to run it again when we use the incident-fetching script in the next section.</span></span>

    <span data-ttu-id="2833e-146">Met dit script wordt een token gegenereerd en opgeslagen in de werkmap onder de naam *Latest-token.txt*.</span><span class="sxs-lookup"><span data-stu-id="2833e-146">This script will generate a token and save it in the working folder under the name, *Latest-token.txt*.</span></span>

    ```PowerShell
    # This script gets the app context token and saves it to a file named "Latest-token.txt" under the current directory.
    # Paste in your tenant ID, client ID and app secret (App key).

    $tenantId = '' # Paste your directory (tenant) ID here
    $clientId = '' # Paste your application (client) ID here
    $appSecret = '' # # Paste your own app secret here to test, then store it in a safe place!

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

#### <a name="validate-the-token"></a><span data-ttu-id="2833e-147">Het token valideren</span><span class="sxs-lookup"><span data-stu-id="2833e-147">Validate the token</span></span>

1. <span data-ttu-id="2833e-148">Kopieer en plak het token dat u hebt ontvangen in [JWT](https://jwt.ms) om dit te decoderen.</span><span class="sxs-lookup"><span data-stu-id="2833e-148">Copy and paste the token you received into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="2833e-149">*JWT* staat voor *JSON Web token*.</span><span class="sxs-lookup"><span data-stu-id="2833e-149">*JWT* stands for *JSON Web Token*.</span></span> <span data-ttu-id="2833e-150">Het met een cijfer genummerde token bevat een aantal met JSON opgemaakte items of claims.</span><span class="sxs-lookup"><span data-stu-id="2833e-150">The decoded token will contain a number of JSON-formatted items or claims.</span></span> <span data-ttu-id="2833e-151">Zorg ervoor dat de *claim claim* binnen het genummerde token de gewenste machtigingen bevat.</span><span class="sxs-lookup"><span data-stu-id="2833e-151">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

    <span data-ttu-id="2833e-152">In de volgende afbeelding ziet u een versleuteld token dat u hebt verkregen uit een app, met ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` en ```AdvancedHunting.Read.All``` machtigingen:</span><span class="sxs-lookup"><span data-stu-id="2833e-152">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

    ![Afbeelding van jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a><span data-ttu-id="2833e-154">Een lijst met recente incidenten weergeven</span><span class="sxs-lookup"><span data-stu-id="2833e-154">Get a list of recent incidents</span></span>

<span data-ttu-id="2833e-155">In het onderstaande script wordt **Get-Token.ps1** gebruikt voor toegang tot de API.</span><span class="sxs-lookup"><span data-stu-id="2833e-155">The script below will use **Get-Token.ps1** to access the API.</span></span> <span data-ttu-id="2833e-156">Vervolgens wordt een lijst met incidenten opgehaald die zijn bijgewerkt in de afgelopen 48 uur en wordt de lijst opgeslagen als een JSON-bestand.</span><span class="sxs-lookup"><span data-stu-id="2833e-156">It then retrieves a list of incidents that were last updated within the past 48 hours, and saves the list as a JSON file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2833e-157">Sla dit script op in de map waarin u **Get-Token.ps1** hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="2833e-157">Save this script in the same folder you saved **Get-Token.ps1**.</span></span>

```PowerShell
# This script returns incidents last updated within the past 48 hours.

$token = ./Get-Token.ps1

# Get incidents from the past 48 hours.
# The script may appear to fail if you don't have any incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# This URL contains the type of query and the time filter we created above.
# Note that `$filter` does not refer to a local variable in our script --
# it's actually an OData operator and part of the API's syntax.
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the webrequest headers
$headers = @{
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the request and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results.
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get a string containing the execution time. We concatenate that string to the name 
# of the output file to avoid overwriting the file on consecutive runs of the script.
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"

Out-File -FilePath $outputJsonPath -InputObject $incidents
```

<span data-ttu-id="2833e-158">U bent klaar!</span><span class="sxs-lookup"><span data-stu-id="2833e-158">You're all done!</span></span> <span data-ttu-id="2833e-159">U hebt de volgende handelingen uitgevoerd:</span><span class="sxs-lookup"><span data-stu-id="2833e-159">You've successfully:</span></span>

- <span data-ttu-id="2833e-160">Het maken en registreren van een toepassing.</span><span class="sxs-lookup"><span data-stu-id="2833e-160">Created and registered an application.</span></span>
- <span data-ttu-id="2833e-161">Toestemming verleend voor de toepassing van waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="2833e-161">Granted permission for that application to read alerts.</span></span>
- <span data-ttu-id="2833e-162">Verbonden met de API.</span><span class="sxs-lookup"><span data-stu-id="2833e-162">Connected to the API.</span></span>
- <span data-ttu-id="2833e-163">Gebruik een PowerShell-script om in de afgelopen 48 uur bijgewerkte incidenties te retourneren.</span><span class="sxs-lookup"><span data-stu-id="2833e-163">Used a PowerShell script to return incidents updated in the past 48 hours.</span></span>

## <a name="related-articles"></a><span data-ttu-id="2833e-164">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="2833e-164">Related articles</span></span>

- [<span data-ttu-id="2833e-165">Overzicht van Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="2833e-165">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="2833e-166">Toegang tot de Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="2833e-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="2833e-167">Een app maken om toegang te krijgen tot Microsoft 365 Defender zonder een gebruiker</span><span class="sxs-lookup"><span data-stu-id="2833e-167">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="2833e-168">Een app maken om toegang te krijgen tot Microsoft 365 Defender-Api's namens een gebruiker</span><span class="sxs-lookup"><span data-stu-id="2833e-168">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="2833e-169">Een app maken met toegang met meerdere tenants voor partners van Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2833e-169">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="2833e-170">Geheimen in uw server-apps beheren met Azure-sleutel kluis</span><span class="sxs-lookup"><span data-stu-id="2833e-170">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="2833e-171">OAuth 2,0-autorisatie voor gebruikersaanmelding en API-toegang</span><span class="sxs-lookup"><span data-stu-id="2833e-171">OAuth 2.0 Authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
