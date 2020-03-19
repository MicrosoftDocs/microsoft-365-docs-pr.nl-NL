---
title: Problemen oplossen voor Microsoft 365 Gebruiksanalyse
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Meer informatie over het oplossen van problemen met de sjabloon-app Microsoft 365 Usage Analytics.
ms.openlocfilehash: a9da79a6d7760f7876de7a6321554545d411f6be
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42806177"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="20596-103">Problemen oplossen voor Microsoft 365 Gebruiksanalyse</span><span class="sxs-lookup"><span data-stu-id="20596-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="20596-104">Raadpleeg de volgende lijst met foutmeldingen voor hulp bij de meest voorkomende problemen met het Microsoft 365 Gebruiksanalyse.</span><span class="sxs-lookup"><span data-stu-id="20596-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="20596-105">De aanvraag kan niet worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="20596-105">We are unable to process your request.</span></span> <span data-ttu-id="20596-106">U moet zich eerst abonneren op deze gegevens van het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="20596-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="20596-107">**Foutcode :** 422</span><span class="sxs-lookup"><span data-stu-id="20596-107">**Error Code :** 422</span></span> 
  
 <span data-ttu-id="20596-108">**Waar u dit bericht te zien krijgt:** In Power BI wanneer u verbinding maakt met de microsoft 365-sjabloonapp Voor gebruiksanalyse of wanneer u rechtstreeks de Microsoft 365 Reporting API's belt.</span><span class="sxs-lookup"><span data-stu-id="20596-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="20596-109">**Oorzaak:** Voordat u verbinding maken met de app, moet u zich abonneren op de gegevens van het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="20596-109">**Cause:** Before you can connect to the app you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="20596-110">Als deze stap niet eerst wordt uitgevoerd, u geen verbinding maken met de sjabloon-app, zelfs niet als u uw Microsoft 365-tenant-id opgeeft.</span><span class="sxs-lookup"><span data-stu-id="20596-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant id.</span></span> 
  
 <span data-ttu-id="20596-111">**Ga als volgt te werk om deze fout op te lossen:** Als u zich wilt abonneren op \> de gegevens, gaat u naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">beheercentrum</a> **Rapporten** \> Gebruik en zoekt u de tegel Microsoft 365-gebruiksanalyse op de hoofdpagina van het dashboard.</span><span class="sxs-lookup"><span data-stu-id="20596-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="20596-112">Selecteer de knop **Aan de slag** en schakel vervolgens in het deelvenster **Rapporten** dat wordt geopend de **gebruiksanalyses voor Microsoft 365 beschikbaar** maken voor Power BI-instelling op en **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="20596-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="20596-113">Uw gegevens worden verwerkt</span><span class="sxs-lookup"><span data-stu-id="20596-113">We are processing your data</span></span>

 <span data-ttu-id="20596-114">**Waar u dit bericht te zien krijgt:** In de tegel **Gebruiksanalyse van Microsoft 365** op het dashboard **Gebruik** in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="20596-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="20596-115">**Oorzaak:** Wanneer u zich inschrijft voor het zien van [gegevens in de sjabloon-app](enable-usage-analytics.md) van het Microsoft 365-beheercentrum, begint het Microsoft 365-systeem historische gebruiksgegevens voor uw organisatie te genereren.</span><span class="sxs-lookup"><span data-stu-id="20596-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="20596-116">Afhankelijk van de grootte van uw tenant kan dit 2 tot 48 uur duren.</span><span class="sxs-lookup"><span data-stu-id="20596-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="20596-117">**Ga als volgt te werk:** Wees geduldig, maar als het bericht niet wordt gewijzigd in **uw gegevens is klaar** na 3 dagen, neem dan contact op met Microsoft [365 voor zakelijke ondersteuning](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="20596-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="20596-118">De aanvraag kan momenteel niet worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="20596-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="20596-119">De gegevens voor uw organisatie worden nog voorbereid</span><span class="sxs-lookup"><span data-stu-id="20596-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="20596-120">**Foutcode:** 423</span><span class="sxs-lookup"><span data-stu-id="20596-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="20596-121">**Waar u dit bericht te zien krijgt:** In Power BI wanneer u verbinding maakt met de microsoft 365-sjabloonapp Voor gebruiksanalyse of wanneer u rechtstreeks de Microsoft 365 Reporting API's belt.</span><span class="sxs-lookup"><span data-stu-id="20596-121">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="20596-122">**Oorzaak:** Wanneer u zich inschrijft voor het zien van [gegevens in de sjabloon-app](enable-usage-analytics.md) van het beheercentrum, begint het Microsoft 365-systeem historische gebruiksgegevens voor uw organisatie te genereren.</span><span class="sxs-lookup"><span data-stu-id="20596-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="20596-123">Afhankelijk van de grootte van uw tenant kan dit 2 tot 48 uur duren.</span><span class="sxs-lookup"><span data-stu-id="20596-123">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="20596-124">**Ga als volgt te werk:** Wees geduldig, maar als het bericht niet verandert in **uw gegevens is klaar,** zelfs 3 dagen sinds de initiatie, [contact opnemen met Microsoft 365 voor zakelijke ondersteuning](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="20596-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="20596-125">De opgegeven tenant-id heeft niet de juiste indeling</span><span class="sxs-lookup"><span data-stu-id="20596-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="20596-126">**Foutcode:** 400</span><span class="sxs-lookup"><span data-stu-id="20596-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="20596-127">**Waar u dit bericht te zien krijgt:** In Power BI wanneer u verbinding maakt met de microsoft 365-sjabloonapp Voor gebruiksanalyse of wanneer u rechtstreeks de Microsoft 365 Reporting API's belt.</span><span class="sxs-lookup"><span data-stu-id="20596-127">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="20596-p107">**Oorzaak:** de tenant-id is een GUID en moet de volgende indeling hebben: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. Als u een andere tekenreeks opgeeft in het invoervak, wordt deze fout weergegeven.</span><span class="sxs-lookup"><span data-stu-id="20596-p107">**Cause:** The tenant id is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. If you enter any other string in the tenant input box you will get this error.</span></span> 
  
 <span data-ttu-id="20596-130">**Ga als volgt te werk om deze fout op te lossen:** Ga naar het \> beheercentrum **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a> en zoek de Microsoft 365-gebruiksanalysetegel op de hoofdpagina van het dashboard.</span><span class="sxs-lookup"><span data-stu-id="20596-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="20596-131">De tenant-id wordt vermeld op de tegel.</span><span class="sxs-lookup"><span data-stu-id="20596-131">The tenant id is listed on the tile.</span></span> <span data-ttu-id="20596-132">U het vanaf hier kopiëren en in het dialoogvenster plakken om verbinding te maken met de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="20596-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="20596-133">De opgegeven tenant-id wordt niet herkend door het systeem</span><span class="sxs-lookup"><span data-stu-id="20596-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="20596-134">**Foutcode:** 404</span><span class="sxs-lookup"><span data-stu-id="20596-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="20596-135">**Waar u dit bericht te zien krijgt:** In Power BI wanneer u verbinding maakt met de microsoft 365-sjabloonapp Voor gebruiksanalyse of wanneer u rechtstreeks de Microsoft 365 Reporting API's belt.</span><span class="sxs-lookup"><span data-stu-id="20596-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="20596-136">**Oorzaak:** De tenant-id die u hebt opgegeven is niet geldig of bestaat niet.</span><span class="sxs-lookup"><span data-stu-id="20596-136">**Cause:** The tenant id you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="20596-137">**Ga als volgt te werk om deze fout op te lossen:** Ga naar het \> beheercentrum **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a> en zoek de Microsoft 365-gebruiksanalysetegel op de hoofdpagina van het dashboard.</span><span class="sxs-lookup"><span data-stu-id="20596-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="20596-138">De tenant-id wordt vermeld op de tegel.</span><span class="sxs-lookup"><span data-stu-id="20596-138">The tenant id is listed on the tile.</span></span> <span data-ttu-id="20596-139">U het vanaf hier kopiëren en in het dialoogvenster plakken om verbinding te maken met de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="20596-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="20596-140">Voer uw referenties nogmaals in om u opnieuw aan te melden bij Power BI</span><span class="sxs-lookup"><span data-stu-id="20596-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="20596-141">Foutcode: 302</span><span class="sxs-lookup"><span data-stu-id="20596-141">Error Code: 302</span></span>
  
 <span data-ttu-id="20596-142">**Waar u dit bericht te zien krijgt:** In Power BI wanneer u verbinding maakt met de microsoft 365-sjabloonapp Voor gebruiksanalyse of wanneer u rechtstreeks de Microsoft 365 Reporting API's belt.</span><span class="sxs-lookup"><span data-stu-id="20596-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="20596-143">**Oorzaak:** De autorisatie is mislukt en u moet uw referenties mogelijk opnieuw invoeren.</span><span class="sxs-lookup"><span data-stu-id="20596-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="20596-144">**Oplossing:** Meld u af en weer aan bij Power BI.</span><span class="sxs-lookup"><span data-stu-id="20596-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="20596-145">U bent niet gemachtigd voor toegang tot deze gegevens.</span><span class="sxs-lookup"><span data-stu-id="20596-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="20596-146">Om toegang te krijgen tot de gegevens van deze service moet u een globale beheerder of een van de productbeheerders zijn</span><span class="sxs-lookup"><span data-stu-id="20596-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="20596-147">**Foutcode:** 403</span><span class="sxs-lookup"><span data-stu-id="20596-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="20596-148">**Waar u dit bericht te zien krijgt:** In Power BI wanneer u verbinding maakt met de microsoft 365-sjabloonapp Voor gebruiksanalyse of wanneer u rechtstreeks de Microsoft 365 Reporting API's belt.</span><span class="sxs-lookup"><span data-stu-id="20596-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="20596-149">**Oorzaak:** De autorisatiecode is mislukt omdat de gebruiker die verbinding heeft gemaakt met de sjabloon-app niet het juiste niveau van autorisatie heeft om toegang te krijgen tot deze gegevens.</span><span class="sxs-lookup"><span data-stu-id="20596-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="20596-150">**Ga als volgt te werk om deze fout op te lossen:** Geef de referenties op van een gebruiker die een **globale beheerder**, **Exchange-beheerder**, **Skype voor Bedrijven-beheerder,** **SharePoint-beheerder,** **Globale lezer** of **Rapportlezer** is om verbinding te maken met de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="20596-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="20596-151">Zie [Informatie over beheerdersrollen](../add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="20596-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="20596-152">Vernieuwen mislukt</span><span class="sxs-lookup"><span data-stu-id="20596-152">Refresh failed</span></span>

 <span data-ttu-id="20596-153">**Waar wordt dit bericht weergegeven:** E-mail van Power BI of de status mislukt in de vernieuwingsgeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="20596-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="20596-154">**Oorzaak:** Soms worden de referenties van de gebruiker die verbinding heeft gemaakt met de sjabloon-app opnieuw ingesteld en niet bijgewerkt in de verbindingsinstellingen van de sjabloon-app waardoor de gebruiker vernieuwingsfouten ziet.</span><span class="sxs-lookup"><span data-stu-id="20596-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="20596-155">**Ga als volgt te werk om deze fout op te lossen:** Zoek in Power BI de gegevensset die overeenkomt met de sjabloon-app Microsoft 365 Usage Analytics, selecteer **vernieuwen plannen** en geef uw beheerdersreferenties op.</span><span class="sxs-lookup"><span data-stu-id="20596-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="20596-156">Als dat niet werkt, wist u de cache en maakt u de sjabloon-app opnieuw.</span><span class="sxs-lookup"><span data-stu-id="20596-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
