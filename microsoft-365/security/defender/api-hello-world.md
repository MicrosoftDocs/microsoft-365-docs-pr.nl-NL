---
title: Hello World voor Microsoft 365 Defender REST API
description: Meer informatie over het maken van een app en het gebruik van een token voor toegang tot de Microsoft 365 Defender-API's
keywords: app, token, access, aad, app, application registration, powershell, script, global administrator, permission, microsoft 365 defender
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
ms.openlocfilehash: ffdcf91da6b5def7d63e5fdb8ff51ddbdb1ec550
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058621"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="7878d-104">Hello World voor Microsoft 365 Defender REST API</span><span class="sxs-lookup"><span data-stu-id="7878d-104">Hello World for Microsoft 365 Defender REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7878d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7878d-105">**Applies to:**</span></span>

- <span data-ttu-id="7878d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7878d-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7878d-107">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="7878d-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="7878d-108">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="7878d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="7878d-109">Incidenten krijgen met een eenvoudig PowerShell-script</span><span class="sxs-lookup"><span data-stu-id="7878d-109">Get incidents using a simple PowerShell script</span></span>

<span data-ttu-id="7878d-110">Het duurt 5 tot 10 minuten om dit project te voltooien.</span><span class="sxs-lookup"><span data-stu-id="7878d-110">It should take 5 to 10 minutes to complete this project.</span></span> <span data-ttu-id="7878d-111">Deze tijdschatting omvat het registreren van de toepassing en het toepassen van de code uit het PowerShell-voorbeeldscript.</span><span class="sxs-lookup"><span data-stu-id="7878d-111">This time estimate includes registering the application, and applying the code from the PowerShell sample script.</span></span>

### <a name="register-an-app-in-azure-active-directory"></a><span data-ttu-id="7878d-112">Een app registreren in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7878d-112">Register an app in Azure Active Directory</span></span>

1. <span data-ttu-id="7878d-113">Meld u aan [bij Azure](https://portal.azure.com) als gebruiker met de rol **globale beheerder.**</span><span class="sxs-lookup"><span data-stu-id="7878d-113">Sign in to [Azure](https://portal.azure.com) as a user with the **Global administrator** role.</span></span>

2. <span data-ttu-id="7878d-114">**Navigeer naar Azure Active Directory**  >  **App-registraties** Nieuwe  >  **registratie**.</span><span class="sxs-lookup"><span data-stu-id="7878d-114">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Afbeelding van Microsoft Azure en navigatie naar toepassingsregistratie](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="7878d-116">Kies in het registratieformulier een naam voor uw toepassing en selecteer **vervolgens Registreren.**</span><span class="sxs-lookup"><span data-stu-id="7878d-116">In the registration form, choose a name for your application, then select **Register**.</span></span> <span data-ttu-id="7878d-117">Het selecteren van een omleidings-URI is optioneel.</span><span class="sxs-lookup"><span data-stu-id="7878d-117">Selecting a redirect URI is optional.</span></span> <span data-ttu-id="7878d-118">U hebt er geen nodig om dit voorbeeld te voltooien.</span><span class="sxs-lookup"><span data-stu-id="7878d-118">You won't need one to complete this example.</span></span>

4. <span data-ttu-id="7878d-119">Selecteer op uw **toepassingspagina API-machtigingen** Machtigingen toevoegen Machtiging-API's die mijn organisatie gebruikt  >    >   >, typ **Microsoft Threat Protection** en selecteer Microsoft **Threat Protection.**</span><span class="sxs-lookup"><span data-stu-id="7878d-119">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="7878d-120">Uw app heeft nu toegang tot Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7878d-120">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="7878d-121">*Microsoft Threat Protection* is een voormalige naam voor Microsoft 365 Defender en wordt niet weergegeven in de oorspronkelijke lijst.</span><span class="sxs-lookup"><span data-stu-id="7878d-121">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="7878d-122">U moet beginnen met het schrijven van de naam in het tekstvak om deze weer te geven.</span><span class="sxs-lookup"><span data-stu-id="7878d-122">You need to start writing its name in the text box to see it appear.</span></span>
   <span data-ttu-id="7878d-123">![Afbeelding van API-machtigingsselectie](../../media/apis-in-my-org-tab.PNG)</span><span class="sxs-lookup"><span data-stu-id="7878d-123">![Image of API permission selection](../../media/apis-in-my-org-tab.PNG)</span></span>

   - <span data-ttu-id="7878d-124">Kies **Toepassingsmachtigingen**  >  **Incident.Read.All** en selecteer **Machtigingen toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="7878d-124">Choose **Application permissions** > **Incident.Read.All** and select **Add permissions**.</span></span>

   ![Afbeelding van API-toegang en API-selectie](../../media/request-api-permissions.PNG)

5. <span data-ttu-id="7878d-126">Selecteer **Beheerdersmachtiging verlenen.**</span><span class="sxs-lookup"><span data-stu-id="7878d-126">Select **Grant admin consent**.</span></span> <span data-ttu-id="7878d-127">Telkens wanneer u een machtiging toevoegt, moet u Toestemming van beheerder **verlenen selecteren** om deze van kracht te laten worden.</span><span class="sxs-lookup"><span data-stu-id="7878d-127">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Afbeelding van machtigingen verlenen](../../media/grant-consent.PNG)

6. <span data-ttu-id="7878d-129">Voeg een geheim toe aan de toepassing.</span><span class="sxs-lookup"><span data-stu-id="7878d-129">Add a secret to the application.</span></span> <span data-ttu-id="7878d-130">Selecteer **Certificaten & geheimen,** voeg een beschrijving toe aan het geheim en selecteer **vervolgens Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="7878d-130">Select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="7878d-131">Nadat u Toevoegen **hebt geselecteerd,** **selecteert u de gegenereerde geheime waarde kopiëren.**</span><span class="sxs-lookup"><span data-stu-id="7878d-131">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="7878d-132">U kunt de geheime waarde niet meer ophalen nadat u bent weggehaald.</span><span class="sxs-lookup"><span data-stu-id="7878d-132">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Afbeelding van app-sleutel maken](../../media/webapp-create-key2.png)

7. <span data-ttu-id="7878d-134">Neem uw toepassings-id en uw tenant-id op een veilige plaats op.</span><span class="sxs-lookup"><span data-stu-id="7878d-134">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="7878d-135">Ze worden weergegeven onder **Overzicht** op uw toepassingspagina.</span><span class="sxs-lookup"><span data-stu-id="7878d-135">They're listed under **Overview** on your application page.</span></span>

   ![Afbeelding van gemaakte app-id](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a><span data-ttu-id="7878d-137">Een token downloaden met de app en het token gebruiken om toegang te krijgen tot de API</span><span class="sxs-lookup"><span data-stu-id="7878d-137">Get a token using the app and use the token to access the API</span></span>

<span data-ttu-id="7878d-138">Zie de [zelfstudie Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)voor meer informatie over Azure Active Directory-tokens.</span><span class="sxs-lookup"><span data-stu-id="7878d-138">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7878d-139">Hoewel het voorbeeld in deze demo-app u aanmoedigt om in uw geheime waarde te plakken voor testdoeleinden, moet u nooit geheimen **hardcoderen** in een toepassing die in productie wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="7878d-139">Although the example in this demo app encourage you to paste in your secret value for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="7878d-140">Een derde partij kan uw geheim gebruiken om toegang te krijgen tot bronnen.</span><span class="sxs-lookup"><span data-stu-id="7878d-140">A third party could use your secret to access resources.</span></span> <span data-ttu-id="7878d-141">U kunt de geheimen van uw app beveiligen met Behulp van [Azure Key Vault.](/azure/key-vault/general/about-keys-secrets-certificates)</span><span class="sxs-lookup"><span data-stu-id="7878d-141">You can help keep your app's secrets secure by using [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="7878d-142">Zie Geheimen beheren in uw server-apps met Azure Key Vault voor een praktisch voorbeeld van hoe u uw app [kunt beveiligen.](/learn/modules/manage-secrets-with-azure-key-vault/)</span><span class="sxs-lookup"><span data-stu-id="7878d-142">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

1. <span data-ttu-id="7878d-143">Kopieer het script hieronder en plak het in uw favoriete teksteditor.</span><span class="sxs-lookup"><span data-stu-id="7878d-143">Copy the script below and paste it into your favorite text editor.</span></span> <span data-ttu-id="7878d-144">Opslaan als **Get-Token.ps1.**</span><span class="sxs-lookup"><span data-stu-id="7878d-144">Save as **Get-Token.ps1**.</span></span> <span data-ttu-id="7878d-145">U kunt de code ook in PowerShell ISE uitvoeren, maar u moet deze opslaan, omdat we deze opnieuw moeten uitvoeren wanneer we het script voor het ophalen van incidenten gebruiken in de volgende sectie.</span><span class="sxs-lookup"><span data-stu-id="7878d-145">You can also run the code as-is in PowerShell ISE, but you should save it, because we'll need to run it again when we use the incident-fetching script in the next section.</span></span>

    <span data-ttu-id="7878d-146">Met dit script wordt een token gegenereerd en opgeslagen in de werkmap onder de naam, *Latest-token.txt.*</span><span class="sxs-lookup"><span data-stu-id="7878d-146">This script will generate a token and save it in the working folder under the name, *Latest-token.txt*.</span></span>

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

#### <a name="validate-the-token"></a><span data-ttu-id="7878d-147">Het token valideren</span><span class="sxs-lookup"><span data-stu-id="7878d-147">Validate the token</span></span>

1. <span data-ttu-id="7878d-148">Kopieer en plak het token dat u hebt ontvangen in [JWT om](https://jwt.ms) het te decoderen.</span><span class="sxs-lookup"><span data-stu-id="7878d-148">Copy and paste the token you received into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="7878d-149">*JWT* staat voor *JSON Web Token*.</span><span class="sxs-lookup"><span data-stu-id="7878d-149">*JWT* stands for *JSON Web Token*.</span></span> <span data-ttu-id="7878d-150">Het gedecodeerde token bevat een aantal JSON-opgemaakte items of claims.</span><span class="sxs-lookup"><span data-stu-id="7878d-150">The decoded token will contain a number of JSON-formatted items or claims.</span></span> <span data-ttu-id="7878d-151">Zorg ervoor dat de *claim rollen* in het gedecodeerde token de gewenste machtigingen bevat.</span><span class="sxs-lookup"><span data-stu-id="7878d-151">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

    <span data-ttu-id="7878d-152">In de volgende afbeelding ziet u een gedecodeerd token dat is verkregen van een app, met ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` , en ```AdvancedHunting.Read.All``` machtigingen:</span><span class="sxs-lookup"><span data-stu-id="7878d-152">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

    ![Afbeelding jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a><span data-ttu-id="7878d-154">Een lijst met recente incidenten krijgen</span><span class="sxs-lookup"><span data-stu-id="7878d-154">Get a list of recent incidents</span></span>

<span data-ttu-id="7878d-155">Het onderstaande script gebruikt **Get-Token.ps1** om toegang te krijgen tot de API.</span><span class="sxs-lookup"><span data-stu-id="7878d-155">The script below will use **Get-Token.ps1** to access the API.</span></span> <span data-ttu-id="7878d-156">Vervolgens wordt een lijst met incidenten opgehaald die de afgelopen 48 uur voor het laatst zijn bijgewerkt en wordt de lijst opgeslagen als een JSON-bestand.</span><span class="sxs-lookup"><span data-stu-id="7878d-156">It then retrieves a list of incidents that were last updated within the past 48 hours, and saves the list as a JSON file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7878d-157">Sla dit script op in dezelfde map die u **Get-Token.ps1.**</span><span class="sxs-lookup"><span data-stu-id="7878d-157">Save this script in the same folder you saved **Get-Token.ps1**.</span></span>

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

<span data-ttu-id="7878d-158">U bent klaar.</span><span class="sxs-lookup"><span data-stu-id="7878d-158">You're all done!</span></span> <span data-ttu-id="7878d-159">U hebt het volgende gedaan:</span><span class="sxs-lookup"><span data-stu-id="7878d-159">You've successfully:</span></span>

- <span data-ttu-id="7878d-160">Een toepassing gemaakt en geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="7878d-160">Created and registered an application.</span></span>
- <span data-ttu-id="7878d-161">Deze toepassing heeft toestemming verleend om waarschuwingen te lezen.</span><span class="sxs-lookup"><span data-stu-id="7878d-161">Granted permission for that application to read alerts.</span></span>
- <span data-ttu-id="7878d-162">Verbonden met de API.</span><span class="sxs-lookup"><span data-stu-id="7878d-162">Connected to the API.</span></span>
- <span data-ttu-id="7878d-163">Een PowerShell-script gebruikt om incidenten te retourneren die in de afgelopen 48 uur zijn bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="7878d-163">Used a PowerShell script to return incidents updated in the past 48 hours.</span></span>

## <a name="related-articles"></a><span data-ttu-id="7878d-164">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="7878d-164">Related articles</span></span>

- [<span data-ttu-id="7878d-165">Overzicht van Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="7878d-165">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="7878d-166">De Microsoft 365 Defender-API's openen</span><span class="sxs-lookup"><span data-stu-id="7878d-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="7878d-167">Een app maken voor toegang tot Microsoft 365 Defender zonder een gebruiker</span><span class="sxs-lookup"><span data-stu-id="7878d-167">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="7878d-168">Een app maken voor toegang tot Microsoft 365 Defender-API's namens een gebruiker</span><span class="sxs-lookup"><span data-stu-id="7878d-168">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="7878d-169">Een app maken met partnertoegang voor meerdere tenants tot Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="7878d-169">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="7878d-170">Geheimen beheren in uw server-apps met Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="7878d-170">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="7878d-171">OAuth 2.0 Autorisatie voor gebruikers aanmelden en API-toegang</span><span class="sxs-lookup"><span data-stu-id="7878d-171">OAuth 2.0 Authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)