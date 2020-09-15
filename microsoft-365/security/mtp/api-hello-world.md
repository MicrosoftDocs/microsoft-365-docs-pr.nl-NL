---
title: Hallo wereld voor Microsoft Threat Protection REST API
description: Leer hoe u een app maakt en een token gebruikt om toegang te krijgen tot de Microsoft Threat Protection-Api's
keywords: app, token, toegang, Aad, app, toepassing registreren, powershell, script, globale beheerder, machtiging
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
ms.openlocfilehash: d9aafc43fb08d9e8b3a427805ba58490afee6297
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650247"
---
# <a name="hello-world-for-microsoft-threat-protection-rest-api"></a><span data-ttu-id="9befe-104">Hallo wereld voor Microsoft Threat Protection REST API</span><span class="sxs-lookup"><span data-stu-id="9befe-104">Hello World for Microsoft Threat Protection REST API</span></span> 

<span data-ttu-id="9befe-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="9befe-105">**Applies to:**</span></span>
- <span data-ttu-id="9befe-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="9befe-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="9befe-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="9befe-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="9befe-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="9befe-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="9befe-109">Incidenten aanvragen met behulp van een eenvoudig PowerShell-script</span><span class="sxs-lookup"><span data-stu-id="9befe-109">Get incidents using a simple PowerShell script</span></span>

### <a name="how-long-it-takes-to-go-through-this-example"></a><span data-ttu-id="9befe-110">Hoe lang duurt het om het volgende voorbeeld te passeren?</span><span class="sxs-lookup"><span data-stu-id="9befe-110">How long it takes to go through this example?</span></span>
<span data-ttu-id="9befe-111">U duurt slechts 5 minuten in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="9befe-111">It only takes 5 minutes done in two steps:</span></span>
- <span data-ttu-id="9befe-112">Sollicitatie registratie</span><span class="sxs-lookup"><span data-stu-id="9befe-112">Application registration</span></span>
- <span data-ttu-id="9befe-113">Voorbeelden gebruiken: alleen kopiëren en plakken van een korte PowerShell-script vereist</span><span class="sxs-lookup"><span data-stu-id="9befe-113">Use examples: only requires copy/paste of a short PowerShell script</span></span>

### <a name="do-i-need-a-permission-to-connect"></a><span data-ttu-id="9befe-114">Heb ik een machtiging nodig om verbinding te maken?</span><span class="sxs-lookup"><span data-stu-id="9befe-114">Do I need a permission to connect?</span></span>
<span data-ttu-id="9befe-115">Voor de registratie fase van de toepassing moet u een **globale** beheerdersrol hebben in uw Azure Active Directory (Azure AD)-Tenant.</span><span class="sxs-lookup"><span data-stu-id="9befe-115">For the Application registration stage, you must have a **Global administrator** role in your Azure Active Directory (Azure AD) tenant.</span></span>

### <a name="step-1---create-an-app-in-azure-active-directory"></a><span data-ttu-id="9befe-116">Stap 1: een app maken in azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9befe-116">Step 1 - Create an App in Azure Active Directory</span></span>

1. <span data-ttu-id="9befe-117">Meld u aan bij [Azure](https://portal.azure.com) met de gebruikers van uw **globale beheerder** .</span><span class="sxs-lookup"><span data-stu-id="9befe-117">Log on to [Azure](https://portal.azure.com) with your **Global administrator** user.</span></span>

2. <span data-ttu-id="9befe-118">Ga naar de **Azure Active Directory**-  >  **app registraties**  >  **nieuwe registratie**.</span><span class="sxs-lookup"><span data-stu-id="9befe-118">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Afbeelding van Microsoft Azure en navigatie naar toepassing registreren](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="9befe-120">Kies in het registratieformulier een naam voor de toepassing en selecteer vervolgens **registreren**.</span><span class="sxs-lookup"><span data-stu-id="9befe-120">In the registration form, choose a name for your application and then select **Register**.</span></span>

4. <span data-ttu-id="9befe-121">Zorg dat uw toepassing toegang heeft tot Microsoft Defender ATP en wijs de machtiging **alle incidenten lezen** toe:</span><span class="sxs-lookup"><span data-stu-id="9befe-121">Allow your Application to access Microsoft Defender ATP and assign it **Read all incidents** permission:</span></span>

   - <span data-ttu-id="9befe-122">Selecteer op de pagina toepassingen de optie **API-machtigingen**  >  **toevoegen**voor  >  **Mijn organisatie** > type **Microsoft Threat Protection** en selecteer **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="9befe-122">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** > type **Microsoft Threat Protection** and select on **Microsoft Threat Protection**.</span></span>

   >[!NOTE]
   ><span data-ttu-id="9befe-123">Microsoft Threat Protection wordt niet weergegeven in de oorspronkelijke lijst.</span><span class="sxs-lookup"><span data-stu-id="9befe-123">Microsoft Threat Protection does not appear in the original list.</span></span> <span data-ttu-id="9befe-124">U moet de naam ervan beginnen te schrijven in het tekstvak om de naam weer te geven.</span><span class="sxs-lookup"><span data-stu-id="9befe-124">You need to start writing its name in the text box to see it appear.</span></span>

   ![Afbeelding van API-toegang en API-selectie](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="9befe-126">Kies **Toepassingsmachtigingen**  >  **incident. Read. alle** > Selecteer **machtigingen toevoegen**</span><span class="sxs-lookup"><span data-stu-id="9befe-126">Choose **Application permissions** > **Incident.Read.All** > Select on **Add permissions**</span></span>

   ![Afbeelding van API-toegang en API-selectie](../../media/request-api-permissions.PNG)

   >[!IMPORTANT]
   ><span data-ttu-id="9befe-128">U moet de relevante machtigingen selecteren.</span><span class="sxs-lookup"><span data-stu-id="9befe-128">You need to select the relevant permissions.</span></span> 

     <span data-ttu-id="9befe-129">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="9befe-129">For instance,</span></span>

     - <span data-ttu-id="9befe-130">Om te bepalen welke machtigingen u nodig hebt, raadpleegt u de sectie **machtigingen** in de API die u wilt bellen.</span><span class="sxs-lookup"><span data-stu-id="9befe-130">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="9befe-131">Selecteer **beheerder toestemming verlenen**</span><span class="sxs-lookup"><span data-stu-id="9befe-131">Select **Grant admin consent**</span></span>

    - >[!NOTE]
      > <span data-ttu-id="9befe-132">Telkens wanneer u toestemming toevoegt, moet u op **toestemming verlenen** om de nieuwe machtiging van kracht te laten worden.</span><span class="sxs-lookup"><span data-stu-id="9befe-132">Every time you add permission you must select on **Grant consent** for the new permission to take effect.</span></span>

    ![Afbeelding van machtiging verlenen](../../media/grant-consent.PNG)

6. <span data-ttu-id="9befe-134">Voeg een geheim toe aan de toepassing.</span><span class="sxs-lookup"><span data-stu-id="9befe-134">Add a secret to the application.</span></span>

    - <span data-ttu-id="9befe-135">Selecteer **certificaten & geheimen**, voeg een beschrijving toe aan het geheim en selecteer **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="9befe-135">Select **Certificates & secrets**, add description to the secret and select **Add**.</span></span>

    >[!IMPORTANT]
    > <span data-ttu-id="9befe-136">Nadat u **toevoegen**hebt geselecteerd, **kopieert u de gegenereerde geheime waarde**.</span><span class="sxs-lookup"><span data-stu-id="9befe-136">After selecting **Add**, **copy the generated secret value**.</span></span> <span data-ttu-id="9befe-137">Wanneer u niets kunt terughalen.</span><span class="sxs-lookup"><span data-stu-id="9befe-137">You won't be able to retrieve after you leave!</span></span>

    ![Afbeelding van de sleutel app maken](../../media/webapp-create-key2.png)

7. <span data-ttu-id="9befe-139">Noteer de toepassings-ID en uw Tenant-ID:</span><span class="sxs-lookup"><span data-stu-id="9befe-139">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="9befe-140">Ga op de pagina toepassing naar **overzicht** en kopieer de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="9befe-140">On your application page, go to **Overview** and copy the following:</span></span>

   ![Afbeelding van gemaakte app-id](../../media/app-and-tenant-ids.png)


<span data-ttu-id="9befe-142">Klaar!</span><span class="sxs-lookup"><span data-stu-id="9befe-142">Done!</span></span> <span data-ttu-id="9befe-143">U hebt een toepassing geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="9befe-143">You have successfully registered an application.</span></span>

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a><span data-ttu-id="9befe-144">Stap 2: een token verkrijgen met behulp van de app en dit token gebruiken om toegang te krijgen tot de API.</span><span class="sxs-lookup"><span data-stu-id="9befe-144">Step 2 - Get a token using the App and use this token to access the API.</span></span>

-   <span data-ttu-id="9befe-145">Kopieer het volgende script naar PowerShell ISE of naar een teksteditor en sla het bestand op als '**Get-Token.ps1**'.</span><span class="sxs-lookup"><span data-stu-id="9befe-145">Copy the script below to PowerShell ISE or to a text editor, and save it as "**Get-Token.ps1**"</span></span>
-   <span data-ttu-id="9befe-146">Als u dit script uitvoert, wordt een token gegenereerd en wordt dit opgeslagen in de werkmap onder de naam '**Latest-token.txt**'.</span><span class="sxs-lookup"><span data-stu-id="9befe-146">Running this script will generate a token and will save it in the working folder under the name "**Latest-token.txt**".</span></span>

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

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

-   <span data-ttu-id="9befe-147">Sanity controleren:</span><span class="sxs-lookup"><span data-stu-id="9befe-147">Sanity Check:</span></span><br>
<span data-ttu-id="9befe-148">Voer het script uit.</span><span class="sxs-lookup"><span data-stu-id="9befe-148">Run the script.</span></span><br>
<span data-ttu-id="9befe-149">Ga in uw browser naar: https://jwt.ms/</span><span class="sxs-lookup"><span data-stu-id="9befe-149">In your browser go to: https://jwt.ms/</span></span> <br>
<span data-ttu-id="9befe-150">Kopieer de token (de inhoud van het Latest-token.txt bestand).</span><span class="sxs-lookup"><span data-stu-id="9befe-150">Copy the token (the content of the Latest-token.txt file).</span></span><br>
<span data-ttu-id="9befe-151">Plakken in het bovenste vak.</span><span class="sxs-lookup"><span data-stu-id="9befe-151">Paste in the top box.</span></span><br>
<span data-ttu-id="9befe-152">Zoek naar de sectie rollen.</span><span class="sxs-lookup"><span data-stu-id="9befe-152">Look for the "roles" section.</span></span> <span data-ttu-id="9befe-153">De ```Incidents.Read.All``` rol zoeken.</span><span class="sxs-lookup"><span data-stu-id="9befe-153">Find the ```Incidents.Read.All``` role.</span></span><br>
<span data-ttu-id="9befe-154">In het onderstaande voorbeeld bevindt zich een app met de ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` machtiging en machtigingen.</span><span class="sxs-lookup"><span data-stu-id="9befe-154">The below example is from an app that has ```Incidents.Read.All```, ```Incidents.ReadWrite.All``` and ```AdvancedHunting.Read.All``` permissions.</span></span>

![Afbeelding van jwt.ms](../../media/api-jwt-ms.png)

### <a name="lets-get-the-incidents"></a><span data-ttu-id="9befe-156">Hiermee kunt u de incidenten vinden.</span><span class="sxs-lookup"><span data-stu-id="9befe-156">Lets get the Incidents!</span></span>

-   <span data-ttu-id="9befe-157">In het onderstaande script wordt **Get-Token.ps1** gebruikt voor toegang tot de API en worden de meest recent bijgewerkte aanvragen weergegeven in de afgelopen 48 uur.</span><span class="sxs-lookup"><span data-stu-id="9befe-157">The script below will use **Get-Token.ps1** to access the API and will get the incidents last updated in past 48 hours.</span></span>
-   <span data-ttu-id="9befe-158">Sla dit script op in de map waarin u het vorige script hebt opgeslagen **Get-Token.ps1**.</span><span class="sxs-lookup"><span data-stu-id="9befe-158">Save this script in the same folder you saved the previous script **Get-Token.ps1**.</span></span> 
-   <span data-ttu-id="9befe-159">Het script een JSON-bestand met de gegevens in dezelfde map als de scripts.</span><span class="sxs-lookup"><span data-stu-id="9befe-159">The script a json file with the data in the same folder as the scripts.</span></span>

```
# Returns Incidents last updated in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Incidents from the last 48 hours. Make sure you have incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# The URL contains the type of query and the time filter we created above
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results. 
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"     

Out-File -FilePath $outputJsonPath -InputObject $incidents 
```

<span data-ttu-id="9befe-160">U bent klaar!</span><span class="sxs-lookup"><span data-stu-id="9befe-160">You're all done!</span></span> <span data-ttu-id="9befe-161">U hebt zojuist de volgende handelingen uitgevoerd:</span><span class="sxs-lookup"><span data-stu-id="9befe-161">You have just successfully:</span></span>
-   <span data-ttu-id="9befe-162">Gemaakt en geregistreerd en Application</span><span class="sxs-lookup"><span data-stu-id="9befe-162">Created and registered and application</span></span>
-   <span data-ttu-id="9befe-163">Toestemming voor de toepassing van waarschuwingen heeft gekregen</span><span class="sxs-lookup"><span data-stu-id="9befe-163">Granted permission for that application to read alerts</span></span>
-   <span data-ttu-id="9befe-164">Verbonden met de API</span><span class="sxs-lookup"><span data-stu-id="9befe-164">Connected the API</span></span>
-   <span data-ttu-id="9befe-165">Gebruik een PowerShell-script om incidenten te retourneren die in de afgelopen 48 uur zijn gemaakt</span><span class="sxs-lookup"><span data-stu-id="9befe-165">Used a PowerShell script to return incidents created in the past 48 hours</span></span>



## <a name="related-topic"></a><span data-ttu-id="9befe-166">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="9befe-166">Related topic</span></span>
- [<span data-ttu-id="9befe-167">Toegang tot de Microsoft Threat Protection-Api's</span><span class="sxs-lookup"><span data-stu-id="9befe-167">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="9befe-168">Toegang tot Microsoft Threat Protection met toepassingscontext</span><span class="sxs-lookup"><span data-stu-id="9befe-168">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="9befe-169">Microsoft Threat Protection met gebruikerscontext openen</span><span class="sxs-lookup"><span data-stu-id="9befe-169">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
