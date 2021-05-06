---
title: Een connector implementeren om Twitter-gegevens te archiveren
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Beheerders kunnen een native connector instellen om Twitter-gegevens te importeren en te archiveren Microsoft 365. Nadat deze gegevens zijn geïmporteerd in Microsoft 365, kunt u compliancefuncties zoals juridische bewaring, inhoud zoeken en bewaarbeleid gebruiken om het beheer van de Twitter-gegevens van uw organisatie te beheren.
ms.openlocfilehash: 0dd996802964b2a2fc58d26e23af57193c89ee8c
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "52161551"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="470b0-104">Een connector implementeren om Twitter-gegevens te archiveren</span><span class="sxs-lookup"><span data-stu-id="470b0-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="470b0-105">Dit artikel bevat het stapsgewijs proces voor het implementeren van een verbindingslijn die de Office 365 Import-service gebruikt om gegevens uit het Twitter-account van uw organisatie te importeren in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="470b0-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="470b0-106">Zie Een verbindingslijn instellen om Twitter-gegevens te archiveren voor een overzicht op hoog niveau van dit proces en een lijst met vereisten voor het implementeren van [een Twitter-connector. ](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="470b0-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="470b0-107">Stap 1: Een app maken in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="470b0-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="470b0-108">Ga naar <https://portal.azure.com> en meld u aan met de referenties van een globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="470b0-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

   ![Aanmelden bij Azure](../media/TCimage01.png)

2. <span data-ttu-id="470b0-110">Klik in het linkernavigatiedeelvenster op **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="470b0-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Ga naar Azure Active Directory](../media/TCimage02.png)

3. <span data-ttu-id="470b0-112">Klik in het linkernavigatiedeelvenster op **App-registraties (Voorbeeld)** en klik vervolgens op **Nieuwe registratie.**</span><span class="sxs-lookup"><span data-stu-id="470b0-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![Een nieuwe app-registratie maken](../media/TCimage03.png)

4. <span data-ttu-id="470b0-114">Registreer de toepassing.</span><span class="sxs-lookup"><span data-stu-id="470b0-114">Register the application.</span></span> <span data-ttu-id="470b0-115">Selecteer **onder Redirect URI (optioneel)** de optie **Web** in de vervolgkeuzelijst toepassingstype en typ vervolgens in het vak voor `https://portal.azure.com` de URI.</span><span class="sxs-lookup"><span data-stu-id="470b0-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="470b0-116">Typ https://portal.azure.com voor de omleidings-URI</span><span class="sxs-lookup"><span data-stu-id="470b0-116">Type https://portal.azure.com for the redirect URI</span></span> ](../media/TCimage04.png)

5. <span data-ttu-id="470b0-117">Kopieer de **toepassings-id en** **adreslijst-id (tenant)** en sla deze op in een tekstbestand of een andere veilige locatie.</span><span class="sxs-lookup"><span data-stu-id="470b0-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="470b0-118">U gebruikt deze ID's in latere stappen.</span><span class="sxs-lookup"><span data-stu-id="470b0-118">You use these IDs in later steps.</span></span>

    ![De toepassings-id en adreslijst-id kopiëren en opslaan](../media/TCimage05.png)

6. <span data-ttu-id="470b0-120">Ga naar **Certificaten & voor de nieuwe app** en klik onder **Clientgeheimen** op **Nieuwe clientgeheim.**</span><span class="sxs-lookup"><span data-stu-id="470b0-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![Een nieuw clientgeheim maken](../media/TCimage06.png)

7. <span data-ttu-id="470b0-122">Maak een nieuw geheim.</span><span class="sxs-lookup"><span data-stu-id="470b0-122">Create a new secret.</span></span> <span data-ttu-id="470b0-123">Typ het geheim in het vak Beschrijving en kies vervolgens een verloopperiode.</span><span class="sxs-lookup"><span data-stu-id="470b0-123">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![Typ het geheim en kies verloopperiode](../media/TCimage08.png)

8. <span data-ttu-id="470b0-125">Kopieer de waarde van het geheim en sla deze op in een tekstbestand of een andere opslaglocatie.</span><span class="sxs-lookup"><span data-stu-id="470b0-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="470b0-126">Dit is het AAD-toepassingsgeheim dat u in latere stappen gebruikt.</span><span class="sxs-lookup"><span data-stu-id="470b0-126">This is the AAD application secret that you use in later steps.</span></span>

   ![Het geheim kopiëren en opslaan](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="470b0-128">Stap 2: De connectorwebservice implementeren van GitHub naar uw Azure-account</span><span class="sxs-lookup"><span data-stu-id="470b0-128">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="470b0-129">Ga naar [deze GitHub en](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) klik op Implementeren naar **Azure**.</span><span class="sxs-lookup"><span data-stu-id="470b0-129">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Naar de startpagina van Azure gaan](../media/FBCimage11.png)

2. <span data-ttu-id="470b0-131">Nadat u op **Implementeren naar Azure hebt** geklikt, wordt u omgeleid naar een Azure-portal met een aangepaste sjabloonpagina.</span><span class="sxs-lookup"><span data-stu-id="470b0-131">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="470b0-132">Vul de **basisbeginselen** **en Instellingen** en klik vervolgens op **Kopen.**</span><span class="sxs-lookup"><span data-stu-id="470b0-132">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![Klik op Een resource maken en een opslagaccount typen](../media/FBCimage12.png)

    - <span data-ttu-id="470b0-134">**Abonnement:** Selecteer uw Azure-abonnement waarin u de twitter-connectorwebservice wilt implementeren.</span><span class="sxs-lookup"><span data-stu-id="470b0-134">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>
    
    - <span data-ttu-id="470b0-135">**Resourcegroep:** Kies of maak een nieuwe resourcegroep.</span><span class="sxs-lookup"><span data-stu-id="470b0-135">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="470b0-136">Een resourcegroep is een container met gerelateerde resources voor een Azure-oplossing.</span><span class="sxs-lookup"><span data-stu-id="470b0-136">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="470b0-137">**Locatie:** Kies een locatie.</span><span class="sxs-lookup"><span data-stu-id="470b0-137">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="470b0-138">**Web App-naam:** Geef een unieke naam op voor de connectorweb-app.</span><span class="sxs-lookup"><span data-stu-id="470b0-138">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="470b0-139">De naam moet tussen 3 en 18 tekens lang zijn.</span><span class="sxs-lookup"><span data-stu-id="470b0-139">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="470b0-140">Deze naam wordt gebruikt om de URL van de Azure-appservice te maken. als u bijvoorbeeld de naam van de web-app van **twitterconnector** op geeft, wordt de URL van de Azure-app-service **twitterconnector.azurewebsites.net.**</span><span class="sxs-lookup"><span data-stu-id="470b0-140">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="470b0-141">**tenantId:** De tenant-id van uw Microsoft 365 organisatie die u hebt gekopieerd na het maken van de Facebook-connector-app in Azure Active Directory in stap 1.</span><span class="sxs-lookup"><span data-stu-id="470b0-141">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="470b0-142">**APISecretKey:** U kunt elke waarde als het geheim typen.</span><span class="sxs-lookup"><span data-stu-id="470b0-142">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="470b0-143">Dit wordt gebruikt om toegang te krijgen tot de connectorweb-app in stap 5.</span><span class="sxs-lookup"><span data-stu-id="470b0-143">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="470b0-144">Nadat de implementatie is gelukt, ziet de pagina er ongeveer hetzelfde uit als de volgende schermafbeelding:</span><span class="sxs-lookup"><span data-stu-id="470b0-144">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![Klik Storage en klik vervolgens op Storage account](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="470b0-146">Stap 3: De Twitter-app maken</span><span class="sxs-lookup"><span data-stu-id="470b0-146">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="470b0-147">Ga naar , meld u aan met de referenties voor het https://developer.twitter.com ontwikkelaarsaccount voor uw organisatie en klik vervolgens op **Apps.**</span><span class="sxs-lookup"><span data-stu-id="470b0-147">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![Ga naar https://developer.twitter.com en meld u aan](../media/TCimage25-5.png)
2. <span data-ttu-id="470b0-149">Klik **op Een app maken.**</span><span class="sxs-lookup"><span data-stu-id="470b0-149">Click **Create an app**.</span></span>
   
   ![Ga naar de pagina Apps om een app te maken](../media/TCimage26.png)

3. <span data-ttu-id="470b0-151">Voeg **onder App-details** informatie over de toepassing toe.</span><span class="sxs-lookup"><span data-stu-id="470b0-151">Under **App details**, add information about the application.</span></span>

   ![Informatie over de app invoeren](../media/TCimage27.png)

4. <span data-ttu-id="470b0-153">Selecteer in het twitter-ontwikkelaarsdashboard de app die u zojuist hebt gemaakt en klik vervolgens op **Details.**</span><span class="sxs-lookup"><span data-stu-id="470b0-153">On the Twitter developer dashboard, select the app that you just created and then click **Details**.</span></span>
   
   ![De app-id kopiëren en opslaan](../media/TCimage28.png)

5. <span data-ttu-id="470b0-155">Kopieer op **het tabblad** Sleutels en tokens onder **Consumenten-API-sleutels** zowel de API-sleutel als de api-geheime sleutel en sla deze op in een tekstbestand of een andere opslaglocatie.</span><span class="sxs-lookup"><span data-stu-id="470b0-155">On the **Keys and tokens** tab, under **Consumer API keys** copy both the API Key and the API secret key and save them to a text file or other storage location.</span></span> <span data-ttu-id="470b0-156">Klik vervolgens **op Maken** om een toegangs token en toegangs tokengeheim te genereren en kopieer deze naar een tekstbestand of een andere opslaglocatie.</span><span class="sxs-lookup"><span data-stu-id="470b0-156">Then click **Create** to generate an access token and access token secret and copy these to a text file or other storage location.</span></span>
   
   ![De geheime API-sleutel kopiëren en opslaan](../media/TCimage29.png)

   <span data-ttu-id="470b0-158">Klik vervolgens **op Maken** om een toegangs-token en een toegangs tokengeheim te genereren en kopieer deze naar een tekstbestand of een andere opslaglocatie.</span><span class="sxs-lookup"><span data-stu-id="470b0-158">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="470b0-159">Klik op **het tabblad Machtigingen** en configureer de machtigingen zoals wordt weergegeven in de volgende schermafbeelding:</span><span class="sxs-lookup"><span data-stu-id="470b0-159">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![Machtigingen configureren](../media/TCimage30.png)

7. <span data-ttu-id="470b0-161">Nadat u de machtigingsinstellingen hebt op slaan, klikt u op het **tabblad App-details** en klikt u vervolgens op **Bewerken > Details bewerken.**</span><span class="sxs-lookup"><span data-stu-id="470b0-161">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![De app-details bewerken](../media/TCimage31.png)

8. <span data-ttu-id="470b0-163">Ga als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="470b0-163">Do the following tasks:</span></span>

   - <span data-ttu-id="470b0-164">Schakel het selectievakje in om de connector-app toe te staan zich aan te melden bij Twitter.</span><span class="sxs-lookup"><span data-stu-id="470b0-164">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="470b0-165">Voeg de OAuth redirect Uri toe met de volgende indeling: **\<connectorserviceuri> /Weergaven/TwitterOAuth**, waarbij de waarde van *connectorserviceuri* de URL van de Azure-app-service voor uw organisatie is, bijvoorbeeld https://twitterconnector.azurewebsites.net/Views/TwitterOAuth .</span><span class="sxs-lookup"><span data-stu-id="470b0-165">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![Verbindingslijn-app toestaan om u aan te melden bij Twitter en OAuth redirect Uri toe te voegen](../media/TCimage32.png)

<span data-ttu-id="470b0-167">De twitter-ontwikkelaars-app is nu klaar voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="470b0-167">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="470b0-168">Stap 4: De connectorweb-app configureren</span><span class="sxs-lookup"><span data-stu-id="470b0-168">Step 4: Configure the connector web app</span></span> 

1. <span data-ttu-id="470b0-169">Ga naar https:// \<AzureAppResourceName> .azurewebsites.net (waarbij **AzureAppResourceName** de naam is van uw Azure-app-resource die u hebt benoemd in stap 4).</span><span class="sxs-lookup"><span data-stu-id="470b0-169">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="470b0-170">Als de naam bijvoorbeeld **twitterconnector** is, gaat u naar https://twitterconnector.azurewebsites.net .</span><span class="sxs-lookup"><span data-stu-id="470b0-170">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="470b0-171">De startpagina van de app ziet eruit als de volgende schermafbeelding:</span><span class="sxs-lookup"><span data-stu-id="470b0-171">The home page of the app looks like the following screenshot:</span></span>

   ![Ga naar de resourcepagina van azure-apps](../media/FBCimage41.png)

2. <span data-ttu-id="470b0-173">Klik **op Configureren** om een aanmeldingspagina weer te geven.</span><span class="sxs-lookup"><span data-stu-id="470b0-173">Click **Configure** to display a sign in page.</span></span>

   ![Klik op Configureren om aanmeldingspagina weer te geven](../media/FBCimage42.png)

3. <span data-ttu-id="470b0-175">Typ of plak uw tenant-id in het vak Tenant-id (die u hebt verkregen in stap 2).</span><span class="sxs-lookup"><span data-stu-id="470b0-175">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="470b0-176">Typ of plak in het wachtwoordvak de APISecretKey (die u hebt verkregen in stap 2) en klik vervolgens op **Configuratie-Instellingen** instellen om de pagina met configuratiegegevens weer te geven.</span><span class="sxs-lookup"><span data-stu-id="470b0-176">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![Aanmelden met tenant-id en API-geheime sleutel](../media/TCimage35.png)

4. <span data-ttu-id="470b0-178">Voer de volgende configuratie-instellingen in</span><span class="sxs-lookup"><span data-stu-id="470b0-178">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="470b0-179">**Twitter Api-toets:** De API-sleutel voor de Twitter-toepassing die u in stap 3 hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="470b0-179">**Twitter Api Key:** The API key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="470b0-180">**Twitter Api Secret Key:** De API-geheime sleutel voor de Twitter-toepassing die u in stap 3 hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="470b0-180">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="470b0-181">**Twitter Access-token:** Het access-token dat u hebt gemaakt in stap 3.</span><span class="sxs-lookup"><span data-stu-id="470b0-181">**Twitter Access Token:** The access token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="470b0-182">**Twitter Access Token Secret:** Het toegangs tokengeheim dat u hebt gemaakt in stap 3.</span><span class="sxs-lookup"><span data-stu-id="470b0-182">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>
   
   - <span data-ttu-id="470b0-183">**AAD-toepassings-id:** De toepassings-id voor de Azure Active Directory app die u hebt gemaakt in stap 1</span><span class="sxs-lookup"><span data-stu-id="470b0-183">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>
   
   - <span data-ttu-id="470b0-184">**AAD Application Secret:** De waarde voor het APISecretKey-geheim dat u hebt gemaakt in stap 1.</span><span class="sxs-lookup"><span data-stu-id="470b0-184">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="470b0-185">Klik **op Opslaan** om de connectorinstellingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="470b0-185">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="470b0-186">Stap 5: Een Twitter-connector instellen in het Microsoft 365 compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="470b0-186">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="470b0-187">Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com) en klik vervolgens op **Gegevensconnectoren** in het linkernavigatievenster.</span><span class="sxs-lookup"><span data-stu-id="470b0-187">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="470b0-188">Klik op **de pagina Gegevensconnectors** onder **Twitter** op **Weergeven.**</span><span class="sxs-lookup"><span data-stu-id="470b0-188">On the **Data connectors** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="470b0-189">Klik op **de pagina Twitter** op **Verbindingslijn toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="470b0-189">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="470b0-190">Klik op **de pagina Servicevoorwaarden** op **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="470b0-190">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="470b0-191">Voer op **de pagina Referenties toevoegen voor de connector-app** de volgende gegevens in en klik vervolgens op Verbinding **valideren.**</span><span class="sxs-lookup"><span data-stu-id="470b0-191">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Referenties voor connector-apps invoeren](../media/TCimage38.png)

    - <span data-ttu-id="470b0-193">Typ in **het** vak Naam een naam voor de verbindingslijn, zoals **De Help-greep van Twitter.**</span><span class="sxs-lookup"><span data-stu-id="470b0-193">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>
    
    - <span data-ttu-id="470b0-194">Typ of plak de URL van de Azure-appservice in het **vak Connector-URL.** bijvoorbeeld `https://twitterconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="470b0-194">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="470b0-195">Typ of plak **in** het vak Wachtwoord de waarde van de APISecretKey die u in stap 2 hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="470b0-195">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>
    
    - <span data-ttu-id="470b0-196">Typ of plak in het vak **Azure App ID** de waarde van de Azure Application App Id (ook wel de *client-id* genoemd) die u hebt verkregen in stap 1.</span><span class="sxs-lookup"><span data-stu-id="470b0-196">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="470b0-197">Nadat de verbinding is gevalideerd, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="470b0-197">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="470b0-198">Typ of plak de APISecretKey **op Microsoft 365** pagina Gegevens importeren en klik vervolgens op **Aanmeldingsweb-app.**</span><span class="sxs-lookup"><span data-stu-id="470b0-198">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="470b0-199">Klik **op Aanmelden met Twitter.**</span><span class="sxs-lookup"><span data-stu-id="470b0-199">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="470b0-200">Meld u op de twitter-aanmeldingspagina aan met de referenties voor het Twitter-account van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="470b0-200">On the Twitter sign in page, sign in using the credentials for your organization's Twitter account.</span></span>

   ![Aanmelden bij Twitter-account](../media/TCimage42.png)

   <span data-ttu-id="470b0-202">Nadat u zich hebt aanmelden, wordt op de Twitter-pagina het volgende bericht weergegeven: 'Twitter Connector Job Successfully set up'.</span><span class="sxs-lookup"><span data-stu-id="470b0-202">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="470b0-203">Klik **op Doorgaan** om het instellen van de Twitter-connector te voltooien.</span><span class="sxs-lookup"><span data-stu-id="470b0-203">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="470b0-204">Op de **pagina Filters instellen** kunt u een filter toepassen om items van een bepaalde leeftijd in eerste instantie te importeren.</span><span class="sxs-lookup"><span data-stu-id="470b0-204">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="470b0-205">Selecteer een leeftijd en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="470b0-205">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="470b0-206">Typ op **de pagina** Opslaglocatie kiezen het e-mailadres van Microsoft 365 postvak waarin de Twitter-items worden geïmporteerd en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="470b0-206">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="470b0-207">Klik **op Volgende** om de connectorinstellingen te bekijken en klik vervolgens op **Voltooien** om de connectorconfiguratie te voltooien.</span><span class="sxs-lookup"><span data-stu-id="470b0-207">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="470b0-208">Ga in het compliancecentrum naar de pagina **Gegevensconnectors** en klik op het tabblad **Verbindingslijnen** om de voortgang van het importproces te zien.</span><span class="sxs-lookup"><span data-stu-id="470b0-208">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
