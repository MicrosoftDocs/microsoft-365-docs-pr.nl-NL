---
title: Een connector implementeren om gegevens van Facebook Business-pagina's te archiveren
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
description: Beheerders kunnen een native connector instellen om Facebook Business-pagina's te importeren en te archiveren Microsoft 365. Nadat deze gegevens zijn geïmporteerd in Microsoft 365, kunt u compliancefuncties zoals juridische bewaring, inhoud zoeken en bewaarbeleid gebruiken om het beheer van de Facebook-gegevens van uw organisatie te beheren.
ms.openlocfilehash: b771c50eb5c2eb5f99269f1f399d27043ebee6bb
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "52161552"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a><span data-ttu-id="c350b-104">Een connector implementeren om gegevens van Facebook Business-pagina's te archiveren</span><span class="sxs-lookup"><span data-stu-id="c350b-104">Deploy a connector to archive Facebook Business pages data</span></span>

<span data-ttu-id="c350b-105">Dit artikel bevat het stapsgewijs proces voor het implementeren van een verbindingslijn die gebruikmaakt van de Office 365 Service importeren om gegevens te importeren van Facebook Business-pagina's naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c350b-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="c350b-106">Zie Een verbindingslijn instellen voor het archiveren van [Facebook-gegevens](archive-facebook-data-with-sample-connector.md)voor een overzicht op hoog niveau van dit proces en een lijst met vereisten die nodig zijn voor het implementeren van een Facebook-connector.</span><span class="sxs-lookup"><span data-stu-id="c350b-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="c350b-107">Stap 1: Een app maken in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c350b-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="c350b-108">Ga naar <https://portal.azure.com> en meld u aan met de referenties van een globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="c350b-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

    ![App maken in AAD](../media/FBCimage1.png)

2. <span data-ttu-id="c350b-110">Klik in het linkernavigatiedeelvenster op **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="c350b-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![Klik Azure Active Directory](../media/FBCimage2.png)

3. <span data-ttu-id="c350b-112">Klik in het linkernavigatiedeelvenster op **App-registraties (Voorbeeld)** en klik vervolgens op **Nieuwe registratie.**</span><span class="sxs-lookup"><span data-stu-id="c350b-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![Klik op **App-registraties (Preview)** en klik vervolgens op **Nieuwe registratie**](../media/FBCimage3.png)

4. <span data-ttu-id="c350b-114">Registreer de toepassing.</span><span class="sxs-lookup"><span data-stu-id="c350b-114">Register the application.</span></span> <span data-ttu-id="c350b-115">Selecteer onder Redirect URI de optie Web in de vervolgkeuzelijst toepassingstype en typ <https://portal.azure.com> vervolgens het vak voor de URI.</span><span class="sxs-lookup"><span data-stu-id="c350b-115">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![De toepassing registreren](../media/FBCimage4.png)

5. <span data-ttu-id="c350b-117">Kopieer de **toepassings-id en** **adreslijst-id (tenant)** en sla deze op in een tekstbestand of een andere veilige locatie.</span><span class="sxs-lookup"><span data-stu-id="c350b-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="c350b-118">U gebruikt deze ID's in latere stappen.</span><span class="sxs-lookup"><span data-stu-id="c350b-118">You use these IDs in later steps.</span></span>

   ![De toepassings-id en adreslijst-id kopiëren en opslaan](../media/FBCimage5.png)

6. <span data-ttu-id="c350b-120">Ga naar **Certificaten & voor de nieuwe app.**</span><span class="sxs-lookup"><span data-stu-id="c350b-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![Ga naar Certificaten & voor de nieuwe app](../media/FBCimage6.png)

7. <span data-ttu-id="c350b-122">Klik **op Nieuw clientgeheim**</span><span class="sxs-lookup"><span data-stu-id="c350b-122">Click **New client secret**</span></span>

   ![Klik op Nieuw clientgeheim](../media/FBCimage7.png)

8. <span data-ttu-id="c350b-124">Maak een nieuw geheim.</span><span class="sxs-lookup"><span data-stu-id="c350b-124">Create a new secret.</span></span> <span data-ttu-id="c350b-125">Typ het geheim in het vak Beschrijving en kies vervolgens een verloopperiode.</span><span class="sxs-lookup"><span data-stu-id="c350b-125">In the description box, type the secret and then choose an expiration period.</span></span>

    ![Typ het geheim en kies vervolgens een verloopperiode](../media/FBCimage8.png)

9. <span data-ttu-id="c350b-127">Kopieer de waarde van het geheim en sla deze op in een tekstbestand of een andere opslaglocatie.</span><span class="sxs-lookup"><span data-stu-id="c350b-127">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="c350b-128">Dit is het AAD-toepassingsgeheim dat u in latere stappen gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c350b-128">This is the AAD application secret that you use in later steps.</span></span>

   ![De waarde van het geheim kopiëren en opslaan](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="c350b-130">Stap 2: De connectorwebservice implementeren van GitHub naar uw Azure-account</span><span class="sxs-lookup"><span data-stu-id="c350b-130">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="c350b-131">Ga naar [deze GitHub en](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) klik op Implementeren naar **Azure**.</span><span class="sxs-lookup"><span data-stu-id="c350b-131">Go to [this GitHub site](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Klik op Implementeren naar Azure](../media/FBCGithubApp.png)

2. <span data-ttu-id="c350b-133">Nadat u op **Implementeren naar Azure hebt** geklikt, wordt u omgeleid naar een Azure-portal met een aangepaste sjabloonpagina.</span><span class="sxs-lookup"><span data-stu-id="c350b-133">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="c350b-134">Vul de **basisbeginselen** **en Instellingen** en klik vervolgens op **Kopen.**</span><span class="sxs-lookup"><span data-stu-id="c350b-134">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   - <span data-ttu-id="c350b-135">**Abonnement:** Selecteer uw Azure-abonnement waar u de connectorwebservice voor Facebook Business-pagina's wilt implementeren.</span><span class="sxs-lookup"><span data-stu-id="c350b-135">**Subscription:** Select your Azure subscription that you want to deploy the Facebook Business pages connector web service to.</span></span>

   - <span data-ttu-id="c350b-136">**Resourcegroep:** Kies of maak een nieuwe resourcegroep.</span><span class="sxs-lookup"><span data-stu-id="c350b-136">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="c350b-137">Een resourcegroep is een container met gerelateerde resources voor een Azure-oplossing.</span><span class="sxs-lookup"><span data-stu-id="c350b-137">A resource group is a container that holds related resources for an Azure solution.</span></span>

   - <span data-ttu-id="c350b-138">**Locatie:** Kies een locatie.</span><span class="sxs-lookup"><span data-stu-id="c350b-138">**Location:** Choose a location.</span></span>

   - <span data-ttu-id="c350b-139">**Web App-naam:** Geef een unieke naam op voor de connectorweb-app.</span><span class="sxs-lookup"><span data-stu-id="c350b-139">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="c350b-140">De naam moet tussen 3 en 18 tekens lang zijn.</span><span class="sxs-lookup"><span data-stu-id="c350b-140">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="c350b-141">Deze naam wordt gebruikt om de URL van de Azure-appservice te maken. als u bijvoorbeeld de naam van de web-app van **fbconnector** op geeft, wordt de URL van de Azure-appservice **fbconnector.azurewebsites.net.**</span><span class="sxs-lookup"><span data-stu-id="c350b-141">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **fbconnector** then the Azure app service URL  will be **fbconnector.azurewebsites.net**.</span></span>

   - <span data-ttu-id="c350b-142">**tenantId:** De tenant-id van uw Microsoft 365 organisatie die u hebt gekopieerd na het maken van de Facebook-connector-app in Azure Active Directory stap 1.</span><span class="sxs-lookup"><span data-stu-id="c350b-142">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

   - <span data-ttu-id="c350b-143">**APISecretKey:** U kunt elke waarde als het geheim typen.</span><span class="sxs-lookup"><span data-stu-id="c350b-143">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="c350b-144">Dit wordt gebruikt om toegang te krijgen tot de connectorweb-app in stap 5.</span><span class="sxs-lookup"><span data-stu-id="c350b-144">This is used to access the connector web app in Step 5.</span></span>

     ![Klik op Een resource maken en een opslagaccount typen](../media/FBCimage12.png)

3. <span data-ttu-id="c350b-146">Nadat de implementatie is gelukt, ziet de pagina er ongeveer hetzelfde uit als de volgende schermafbeelding:</span><span class="sxs-lookup"><span data-stu-id="c350b-146">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![Klik Storage en klik vervolgens op Storage account](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a><span data-ttu-id="c350b-148">Stap 3: De Facebook-app registreren</span><span class="sxs-lookup"><span data-stu-id="c350b-148">Step 3: Register the Facebook app</span></span>

1. <span data-ttu-id="c350b-149">Ga naar , meld u aan met de referenties voor het account voor de Facebook Business-pagina's van uw organisatie <https://developers.facebook.com> en klik vervolgens op Nieuwe app **toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="c350b-149">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization's Facebook Business pages, and then click **Add New App**.</span></span>

   ![Een nieuwe app voor facebook-bedrijfspagina toevoegen](../media/FBCimage25.png)

2. <span data-ttu-id="c350b-151">Een nieuwe app-id maken.</span><span class="sxs-lookup"><span data-stu-id="c350b-151">Create a new app ID.</span></span>

   ![Een nieuwe app-id maken](../media/FBCimage26.png)

3. <span data-ttu-id="c350b-153">Klik in het linkernavigatiedeelvenster op **Producten toevoegen** en klik **vervolgens op Instellen** in de **tegel Facebook-aanmelding.**</span><span class="sxs-lookup"><span data-stu-id="c350b-153">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![Klik op Producten toevoegen](../media/FBCimage27.png)

4. <span data-ttu-id="c350b-155">Klik op de pagina Facebook-aanmelding integreren op **Web**.</span><span class="sxs-lookup"><span data-stu-id="c350b-155">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![Klik op Web op de pagina Facebook-aanmelding integreren](../media/FBCimage28.png)

5. <span data-ttu-id="c350b-157">Voeg de URL van de Azure-appservice toe; bijvoorbeeld `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="c350b-157">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![De URL van de Azure-app-service toevoegen](../media/FBCimage29.png)

6. <span data-ttu-id="c350b-159">Voltooi de sectie Snelstart van de facebook-aanmeldingsinstallatie.</span><span class="sxs-lookup"><span data-stu-id="c350b-159">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![De sectie Snelstart voltooien](../media/FBCimage30.png)

7. <span data-ttu-id="c350b-161">Klik in het linkernavigatiedeelvenster onder **Facebook Login** op Instellingen **en** voeg de OAuth redirect URI toe in het vak Valid **OAuth Redirect URIs.**</span><span class="sxs-lookup"><span data-stu-id="c350b-161">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="c350b-162">Gebruik de indeling **\<connectorserviceuri> /Weergaven/FacebookOAuth,** waarbij de waarde voor connectorserviceuri de URL van de Azure-app-service voor uw organisatie is, `https://fbconnector.azurewebsites.net` bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="c350b-162">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![De OAuth redirect URI toevoegen aan het vak Valid OAuth Redirect URIs](../media/FBCimage31.png)

8. <span data-ttu-id="c350b-164">Klik in het linkernavigatiedeelvenster op **Producten toevoegen** en klik vervolgens op **Webhooks.**</span><span class="sxs-lookup"><span data-stu-id="c350b-164">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="c350b-165">Klik in **het** snelmenu Pagina op **Pagina.**</span><span class="sxs-lookup"><span data-stu-id="c350b-165">In the **Page** pull-down menu, click **Page**.</span></span>

   ![Klik op Producten toevoegen en klik vervolgens op \*\*Webhooks](../media/FBCimage32.png)

9. <span data-ttu-id="c350b-167">Voeg Webhooks Callback-URL toe en voeg een verificatie-token toe.</span><span class="sxs-lookup"><span data-stu-id="c350b-167">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="c350b-168">Gebruik de indeling van de terugroep-URL met de notatie **<connectorserviceuri> /api/FbPageWebhook,** waarbij de waarde voor connectorserviceuri de URL van de Azure-app-service voor uw organisatie is, bijvoorbeeld `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="c350b-168">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span>

   <span data-ttu-id="c350b-169">Het verificatie-token lijkt op een sterk wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="c350b-169">The verify token should similar to a strong password.</span></span> <span data-ttu-id="c350b-170">Kopieer het verificatie-token naar een tekstbestand of een andere opslaglocatie.</span><span class="sxs-lookup"><span data-stu-id="c350b-170">Copy the verify token to a text file or other storage location.</span></span>

   ![Het verificatie-token toevoegen](../media/FBCimage33.png)

10. <span data-ttu-id="c350b-172">Test en abonneer u op het eindpunt voor feed.</span><span class="sxs-lookup"><span data-stu-id="c350b-172">Test and subscribe to the endpoint for feed.</span></span>

    ![Test en abonneer u op het eindpunt](../media/FBCimage34.png)

11. <span data-ttu-id="c350b-174">Voeg een privacy-URL, app-pictogram en zakelijk gebruik toe.</span><span class="sxs-lookup"><span data-stu-id="c350b-174">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="c350b-175">Kopieer ook de app-id en het app-geheim naar een tekstbestand of een andere opslaglocatie.</span><span class="sxs-lookup"><span data-stu-id="c350b-175">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![Een privacy-URL, app-pictogram en zakelijk gebruik toevoegen](../media/FBCimage35.png)

12. <span data-ttu-id="c350b-177">Maak de app openbaar.</span><span class="sxs-lookup"><span data-stu-id="c350b-177">Make the app public.</span></span>

    ![De app openbaar maken](../media/FBCimage36.png)

13. <span data-ttu-id="c350b-179">Gebruiker toevoegen aan de rol beheerder of tester.</span><span class="sxs-lookup"><span data-stu-id="c350b-179">Add user to the admin or tester role.</span></span>

    ![Gebruiker toevoegen aan de rol beheerder of tester](../media/FBCimage37.png)

14. <span data-ttu-id="c350b-181">Voeg de **machtiging Openbare inhoudstoegang voor pagina** toe.</span><span class="sxs-lookup"><span data-stu-id="c350b-181">Add the **Page Public Content Access** permission.</span></span>

    ![dd de machtiging Pagina openbare inhoudstoegang](../media/FBCimage38.png)

15. <span data-ttu-id="c350b-183">Machtiging Pagina's beheren toevoegen.</span><span class="sxs-lookup"><span data-stu-id="c350b-183">Add Manage Pages permission.</span></span>

    ![Machtiging Pagina's beheren toevoegen](../media/FBCimage39.png)

16. <span data-ttu-id="c350b-185">Laat de toepassing beoordeeld worden door Facebook.</span><span class="sxs-lookup"><span data-stu-id="c350b-185">Get the application reviewed by Facebook.</span></span>

    ![De toepassing laten reviewen door Facebook](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="c350b-187">Stap 4: De connectorweb-app configureren</span><span class="sxs-lookup"><span data-stu-id="c350b-187">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="c350b-188">Ga naar (waarbij AzureAppResourceName de naam is van uw `https://<AzureAppResourceName>.azurewebsites.net` Azure-app-resource die u hebt benoemd in stap 4).</span><span class="sxs-lookup"><span data-stu-id="c350b-188">Go to `https://<AzureAppResourceName>.azurewebsites.net` (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="c350b-189">Als de naam bijvoorbeeld **fbconnector** is, gaat u naar `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="c350b-189">For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="c350b-190">De startpagina van de app ziet eruit als de volgende schermafbeelding:</span><span class="sxs-lookup"><span data-stu-id="c350b-190">The home page of the app will look like the following screenshot:</span></span>

   ![Ga naar de web-app verbindingslijn](../media/FBCimage41.png)

2. <span data-ttu-id="c350b-192">Klik **op Configureren** om een aanmeldingspagina weer te geven.</span><span class="sxs-lookup"><span data-stu-id="c350b-192">Click **Configure** to display a sign in page.</span></span>

   ![Klik op Configureren om een aanmeldingspagina weer te geven](../media/FBCimage42.png)

3. <span data-ttu-id="c350b-194">Typ of plak uw tenant-id in het vak Tenant-id (die u hebt verkregen in stap 2).</span><span class="sxs-lookup"><span data-stu-id="c350b-194">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="c350b-195">Typ of plak in het wachtwoordvak de APISecretKey (die u hebt verkregen in stap 2) en klik vervolgens op **Configuratie-Instellingen** instellen om de pagina met configuratiegegevens weer te geven.</span><span class="sxs-lookup"><span data-stu-id="c350b-195">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

    ![Meld u aan met uw tenant-id en wachtwoord en ga naar de pagina configuratiegegevens](../media/FBCimage43.png)

4. <span data-ttu-id="c350b-197">Voer de volgende configuratie-instellingen in</span><span class="sxs-lookup"><span data-stu-id="c350b-197">Enter the following configuration settings</span></span>

   - <span data-ttu-id="c350b-198">**Facebook-toepassing-id:** De app-id voor de Facebook-toepassing die u hebt verkregen in stap 3.</span><span class="sxs-lookup"><span data-stu-id="c350b-198">**Facebook application ID:** The app ID for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="c350b-199">**Facebook-toepassingsgeheim:** Het app-geheim voor de Facebook-toepassing die u hebt verkregen in stap 3.</span><span class="sxs-lookup"><span data-stu-id="c350b-199">**Facebook application secret:** The app secret for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="c350b-200">**Facebook-webhaken verifiëren token:** Het token verifiëren dat u hebt gemaakt in stap 3.</span><span class="sxs-lookup"><span data-stu-id="c350b-200">**Facebook webhooks verify token:** The verify token that you created in Step 3.</span></span>

   - <span data-ttu-id="c350b-201">**AAD-toepassings-id:** De toepassings-id voor de Azure Active Directory app die u hebt gemaakt in stap 1.</span><span class="sxs-lookup"><span data-stu-id="c350b-201">**AAD application ID:** The application ID for the Azure Active Directory app that you created in Step 1.</span></span>

   - <span data-ttu-id="c350b-202">**AAD-toepassingsgeheim:** De waarde voor het APISecretKey-geheim dat u hebt gemaakt in stap 1.</span><span class="sxs-lookup"><span data-stu-id="c350b-202">**AAD application secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="c350b-203">Klik **op Opslaan** om de connectorinstellingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="c350b-203">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="c350b-204">Stap 5: Een Facebook-connector instellen in het Microsoft 365 compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="c350b-204">Step 5: Set up a Facebook connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="c350b-205">Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com) en klik vervolgens op **Gegevensconnectoren** in het linkernavigatievenster.</span><span class="sxs-lookup"><span data-stu-id="c350b-205">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="c350b-206">Klik op **de pagina Gegevensconnectors** onder **Facebook Business-pagina's** op **Weergeven.**</span><span class="sxs-lookup"><span data-stu-id="c350b-206">On the **Data connectors** page under **Facebook Business pages**, click **View**.</span></span>

3. <span data-ttu-id="c350b-207">Klik op de pagina Zakelijke Facebook-pagina's op **Verbindingslijn toevoegen.** </span><span class="sxs-lookup"><span data-stu-id="c350b-207">On the **Facebook business pages** page, click **Add connector**.</span></span>

4. <span data-ttu-id="c350b-208">Klik op **de pagina Servicevoorwaarden** op **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="c350b-208">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="c350b-209">Voer op **de pagina Referenties toevoegen voor de connector-app** de volgende gegevens in en klik vervolgens op Verbinding **valideren.**</span><span class="sxs-lookup"><span data-stu-id="c350b-209">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Referenties voor connector-apps invoeren](../media/TCimage38.png)

   - <span data-ttu-id="c350b-211">Typ in **het** vak Naam een naam voor de verbindingslijn, zoals **facebook-nieuwspagina.**</span><span class="sxs-lookup"><span data-stu-id="c350b-211">In the **Name** box, type a name for the connector, such as **Facebook news page**.</span></span>

   - <span data-ttu-id="c350b-212">Typ of plak de URL van de Azure-appservice in het vak **Verbindings-URL.** bijvoorbeeld `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="c350b-212">In the **Connection URL** box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   - <span data-ttu-id="c350b-213">Typ of plak **in het** vak Wachtwoord de waarde van de APISecretKey die u hebt toegevoegd in stap 2.</span><span class="sxs-lookup"><span data-stu-id="c350b-213">In the **Password** box, type or paste the value of the APISecretKey that you added in Step 2.</span></span>

   - <span data-ttu-id="c350b-214">Typ of plak in het vak **Azure App-id** de waarde van de toepassings-id (client-id) die u in stap 1 hebt gemaakt, ook wel AAD-toepassings-id genoemd.</span><span class="sxs-lookup"><span data-stu-id="c350b-214">In the **Azure App ID** box, type or paste the value of the Application (client) ID also called as AAD Application ID that you created in Step 1.</span></span>

6. <span data-ttu-id="c350b-215">Nadat de verbinding is gevalideerd, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="c350b-215">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="c350b-216">Typ of plak de APISecretKey **op Microsoft 365** pagina Gegevens importeren en klik vervolgens op **Aanmeldingsweb-app.**</span><span class="sxs-lookup"><span data-stu-id="c350b-216">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click **Login web app**.</span></span>

8. <span data-ttu-id="c350b-217">Klik op **de pagina Facebook Connector-app** configureren op Aanmelden met **Facebook** en meld u aan met de referenties voor het account voor de Facebook Business-pagina's van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c350b-217">On the **Configure Facebook connector app** page, click **Login with Facebook** and log in using the credentials for the account for your organization's Facebook Business pages.</span></span> <span data-ttu-id="c350b-218">Zorg ervoor dat aan het Facebook-account bij wie u zich hebt aangemeld, de beheerdersrol is toegewezen voor de Facebook Business-pagina's van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c350b-218">Make sure the Facebook account that you logged in to is assigned the admin role for your organization's Facebook Business pages.</span></span>

   ![Aanmelden met Facebook](../media/FBCimage50.png)

9. <span data-ttu-id="c350b-220">Er wordt een lijst weergegeven met de zakelijke pagina's die worden beheerd door het Facebook-account waarin u zich hebt aangemeld.</span><span class="sxs-lookup"><span data-stu-id="c350b-220">A list of the business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="c350b-221">Selecteer de pagina die u wilt archiveren en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="c350b-221">Select the page to archive and then click **Next**.</span></span>

   ![Selecteer de bedrijfspagina van de organisatie die u wilt archiveren](../media/FBCimage52.png)

10. <span data-ttu-id="c350b-223">Klik **op Doorgaan** om de installatie van de connectorservice-app af te sluiten.</span><span class="sxs-lookup"><span data-stu-id="c350b-223">Click **Continue** to exit the setup of the connector service app.</span></span>

11. <span data-ttu-id="c350b-224">Op de **pagina Filters instellen** kunt u een filter toepassen om items van een bepaalde leeftijd in eerste instantie te importeren.</span><span class="sxs-lookup"><span data-stu-id="c350b-224">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="c350b-225">Selecteer een leeftijd en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="c350b-225">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="c350b-226">Typ op **de pagina** Opslaglocatie kiezen het e-mailadres van Microsoft 365 postvak waarin de Facebook-items worden geïmporteerd en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="c350b-226">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Facebook items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="c350b-227">Klik **op Volgende** om de connectorinstellingen te bekijken en klik vervolgens op **Voltooien** om de connectorconfiguratie te voltooien.</span><span class="sxs-lookup"><span data-stu-id="c350b-227">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="c350b-228">Ga in het compliancecentrum naar de pagina **Gegevensconnectors** en klik op het tabblad **Verbindingslijnen** om de voortgang van het importproces te zien.</span><span class="sxs-lookup"><span data-stu-id="c350b-228">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
