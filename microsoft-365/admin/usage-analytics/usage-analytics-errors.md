---
title: Problemen oplossen voor Microsoft 365 Gebruiksanalyse
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Meer informatie over het oplossen van problemen met de Microsoft 365 De sjabloon-app Gebruiksanalyse.
ms.openlocfilehash: 74ee32ae015421a2352474daefa0eaa0a53fbbc9
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52293733"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="984fd-103">Problemen oplossen voor Microsoft 365 Gebruiksanalyse</span><span class="sxs-lookup"><span data-stu-id="984fd-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="984fd-104">Raadpleeg de volgende lijst met foutmeldingen voor hulp bij de meest voorkomende problemen met het Microsoft 365 Gebruiksanalyse.</span><span class="sxs-lookup"><span data-stu-id="984fd-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="984fd-105">De aanvraag kan niet worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="984fd-105">We are unable to process your request.</span></span> <span data-ttu-id="984fd-106">U moet zich eerst abonneren op deze gegevens vanuit het Microsoft 365 beheercentrum</span><span class="sxs-lookup"><span data-stu-id="984fd-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="984fd-107">**Foutcode:** 422</span><span class="sxs-lookup"><span data-stu-id="984fd-107">**Error Code:** 422</span></span> 
  
 <span data-ttu-id="984fd-108">**Waar ziet u dit bericht:** In Power BI wanneer u verbinding maakt met de Microsoft 365 De sjabloon-app Gebruiksanalyse of wanneer u rechtstreeks de Microsoft 365 Api's voor rapportage.</span><span class="sxs-lookup"><span data-stu-id="984fd-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="984fd-109">**Oorzaak:** Voordat u verbinding kunt maken met de app, moet u zich abonneren op de gegevens van het Microsoft 365 beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="984fd-109">**Cause:** Before you can connect to the app, you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="984fd-110">Als deze stap niet eerst wordt uitgevoerd, kunt u geen verbinding maken met de sjabloon-app, zelfs niet als u uw tenant-id Microsoft 365 toevoegen.</span><span class="sxs-lookup"><span data-stu-id="984fd-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant ID.</span></span> 
  
 <span data-ttu-id="984fd-111">**Deze fout oplossen:** Als u zich wilt abonneren op de gegevens, gaat u naar het beheercentrum Rapportengebruik en zoekt u de Microsoft 365 de tegel Gebruiksanalyse \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> op de pagina met het hoofddashboard.</span><span class="sxs-lookup"><span data-stu-id="984fd-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="984fd-112">Selecteer de **knop Aan** de  slag en schakel in het deelvenster Rapporten dat wordt geopend de optie Gegevens beschikbaar maken voor Microsoft 365 **gebruiksanalyse** voor Power BI instelling in en **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="984fd-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="984fd-113">Uw gegevens worden verwerkt</span><span class="sxs-lookup"><span data-stu-id="984fd-113">We are processing your data</span></span>

 <span data-ttu-id="984fd-114">**Waar ziet u dit bericht:** In de **Microsoft 365 de tegel Gebruiksanalyse** op het dashboard **Gebruik** in het Microsoft 365 beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="984fd-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="984fd-115">**Oorzaak:** Wanneer u [ervoor kiest om](enable-usage-analytics.md) gegevens in de sjabloon-app te zien vanuit het Microsoft 365-beheercentrum, begint het Microsoft 365 met het genereren van historische gebruiksgegevens voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="984fd-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="984fd-116">Afhankelijk van de grootte van uw tenant kan dit 2 tot 48 uur duren.</span><span class="sxs-lookup"><span data-stu-id="984fd-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="984fd-117">**U kunt dit als volgende oplossen:** Wees geduldig, maar als het bericht  na 3 dagen nog niet is gewijzigd in Uw gegevens, neemt u [contact op met Microsoft 365 ondersteuning voor bedrijven.](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="984fd-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../../business-video/get-help-support.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="984fd-p105">De aanvraag kan momenteel niet worden verwerkt. De gegevens voor uw organisatie worden nog voorbereid</span><span class="sxs-lookup"><span data-stu-id="984fd-p105">We are unable to process your request at this time. We are still preparing the data for your organization</span></span>

 <span data-ttu-id="984fd-120">**Foutcode:** 423</span><span class="sxs-lookup"><span data-stu-id="984fd-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="984fd-121">**Waar ziet u dit bericht:** In Power BI, wanneer u verbinding maakt met de Microsoft 365 De sjabloon-app Gebruiksanalyse of wanneer u rechtstreeks de app Reporting API's Microsoft 365 bellen.</span><span class="sxs-lookup"><span data-stu-id="984fd-121">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="984fd-122">**Oorzaak:** Wanneer u [ervoor kiest om](enable-usage-analytics.md) gegevens in de sjabloon-app te zien vanuit het beheercentrum, begint het Microsoft 365 met het genereren van historische gebruiksgegevens voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="984fd-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="984fd-123">Afhankelijk van de grootte van uw tenant, kan deze stap tussen twee uur en 48 uur duren.</span><span class="sxs-lookup"><span data-stu-id="984fd-123">Depending on the size of your tenant, this step could take anywhere between two hours to 48 hours.</span></span> 
  
 <span data-ttu-id="984fd-124">**U kunt dit als volgende oplossen:** Wees geduldig, maar als het bericht niet wordt gewijzigd in Uw gegevens **is** zelfs 3 dagen na de initiatie gereed, neemt u [contact op met Microsoft 365 voor zakelijke ondersteuning.](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="984fd-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../../business-video/get-help-support.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="984fd-125">De opgegeven tenant-id heeft niet de juiste indeling</span><span class="sxs-lookup"><span data-stu-id="984fd-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="984fd-126">**Foutcode:** 400</span><span class="sxs-lookup"><span data-stu-id="984fd-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="984fd-127">**Waar ziet u dit bericht:** In Power BI, wanneer u verbinding maakt met de Microsoft 365 De sjabloon-app Gebruiksanalyse of wanneer u rechtstreeks de app Reporting API's Microsoft 365 bellen.</span><span class="sxs-lookup"><span data-stu-id="984fd-127">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="984fd-128">**Oorzaak:** De tenant-id is een guid en moet de indeling xxxxxxxx-xxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx hebben.</span><span class="sxs-lookup"><span data-stu-id="984fd-128">**Cause:** The tenant ID is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span></span> <span data-ttu-id="984fd-129">Als u een andere tekenreeks in het invoervak van de tenant invoert, krijgt u deze foutmelding.</span><span class="sxs-lookup"><span data-stu-id="984fd-129">If you enter any other string in the tenant input box, you will get this error.</span></span> 
  
 <span data-ttu-id="984fd-130">**Deze fout oplossen:** Ga naar het beheercentrum Rapportengebruik en zoek de Microsoft 365 de tegel \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Gebruiksanalyse op de pagina met het hoofddashboard.</span><span class="sxs-lookup"><span data-stu-id="984fd-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="984fd-131">De tenant-id wordt weergegeven op de tegel.</span><span class="sxs-lookup"><span data-stu-id="984fd-131">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="984fd-132">U kunt het hier kopiëren en plakken in het dialoogvenster om verbinding te maken met de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="984fd-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="984fd-133">De opgegeven tenant-id wordt niet herkend door het systeem</span><span class="sxs-lookup"><span data-stu-id="984fd-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="984fd-134">**Foutcode:** 404</span><span class="sxs-lookup"><span data-stu-id="984fd-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="984fd-135">**Waar ziet u dit bericht:** In Power BI wanneer u verbinding maakt met de Microsoft 365 De sjabloon-app Gebruiksanalyse of wanneer u rechtstreeks de Microsoft 365 Api's voor rapportage.</span><span class="sxs-lookup"><span data-stu-id="984fd-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="984fd-136">**Oorzaak:** De tenant-id die u hebt opgegeven, is niet geldig of bestaat niet.</span><span class="sxs-lookup"><span data-stu-id="984fd-136">**Cause:** The tenant ID you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="984fd-137">**Deze fout oplossen:** Ga naar het beheercentrum Rapportengebruik en zoek de Microsoft 365 de tegel \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Gebruiksanalyse op de pagina met het hoofddashboard.</span><span class="sxs-lookup"><span data-stu-id="984fd-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="984fd-138">De tenant-id wordt weergegeven op de tegel.</span><span class="sxs-lookup"><span data-stu-id="984fd-138">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="984fd-139">U kunt het hier kopiëren en plakken in het dialoogvenster om verbinding te maken met de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="984fd-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="984fd-140">Voer uw referenties nogmaals in om u opnieuw aan te melden bij Power BI</span><span class="sxs-lookup"><span data-stu-id="984fd-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="984fd-141">Foutcode: 302</span><span class="sxs-lookup"><span data-stu-id="984fd-141">Error Code: 302</span></span>
  
 <span data-ttu-id="984fd-142">**Waar ziet u dit bericht:** In Power BI wanneer u verbinding maakt met de Microsoft 365 De sjabloon-app Gebruiksanalyse of wanneer u rechtstreeks de Microsoft 365 Api's voor rapportage.</span><span class="sxs-lookup"><span data-stu-id="984fd-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="984fd-143">**Oorzaak:** De autorisatie is mislukt en u moet uw referenties mogelijk opnieuw invoeren.</span><span class="sxs-lookup"><span data-stu-id="984fd-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="984fd-144">**Oplossing:** Meld u af en weer aan bij Power BI.</span><span class="sxs-lookup"><span data-stu-id="984fd-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="984fd-p110">U bent niet gemachtigd voor toegang tot deze gegevens. Om toegang te krijgen tot de gegevens van deze service moet u een globale beheerder of een van de productbeheerders zijn</span><span class="sxs-lookup"><span data-stu-id="984fd-p110">You do not have the right authorization to access to this data. To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="984fd-147">**Foutcode:** 403</span><span class="sxs-lookup"><span data-stu-id="984fd-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="984fd-148">**Waar ziet u dit bericht:** In Power BI wanneer u verbinding maakt met de Microsoft 365 De sjabloon-app Gebruiksanalyse of wanneer u rechtstreeks de Microsoft 365 Api's voor rapportage.</span><span class="sxs-lookup"><span data-stu-id="984fd-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="984fd-149">**Oorzaak:** De autorisatiecode is mislukt omdat de gebruiker die verbinding heeft gemaakt met de sjabloon-app niet over het juiste machtigingsniveau voor toegang tot deze gegevens heeft.</span><span class="sxs-lookup"><span data-stu-id="984fd-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="984fd-150">**Deze fout oplossen:** Geef de referenties op van een gebruiker die een globale **beheerder, Exchange-beheerder,**  **Skype voor Bedrijven-beheerder,** **SharePoint-beheerder,** **globale** lezer of rapportlezer is om verbinding te maken met de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="984fd-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="984fd-151">Zie [Beheerdersrollen voor](../add-users/about-admin-roles.md) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="984fd-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="984fd-152">Vernieuwen mislukt</span><span class="sxs-lookup"><span data-stu-id="984fd-152">Refresh failed</span></span>

 <span data-ttu-id="984fd-153">**Waar wordt dit bericht weergegeven:** E-mail van Power BI of de status mislukt in de vernieuwingsgeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="984fd-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="984fd-154">**Oorzaak:** Soms worden de referenties van de gebruiker die verbinding heeft gemaakt met de sjabloon-app opnieuw ingesteld en niet bijgewerkt in de verbindingsinstellingen van de sjabloon-app, waardoor de gebruiker foutfouten bij vernieuwen ziet.</span><span class="sxs-lookup"><span data-stu-id="984fd-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="984fd-155">**Deze fout oplossen:** Zoek Power BI gegevensset die overeenkomt met de Microsoft 365 app Gebruiksanalyse, selecteer vernieuwen plannen en geef uw beheerdersreferenties op. </span><span class="sxs-lookup"><span data-stu-id="984fd-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="984fd-156">Als dat niet werkt, moet u de cache wissen en de sjabloon-app opnieuw maken.</span><span class="sxs-lookup"><span data-stu-id="984fd-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
