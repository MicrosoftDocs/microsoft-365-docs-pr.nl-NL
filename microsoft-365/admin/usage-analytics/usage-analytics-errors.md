---
title: Problemen oplossen voor Microsoft 365 Gebruiksanalyse
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Informatie over het oplossen van problemen met de app Microsoft 365 gebruiksanalyse.
ms.openlocfilehash: bf8e4ece7b1e310d91f418f5388cae9aa27f2aa7
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841433"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="ffb59-103">Problemen oplossen voor Microsoft 365 Gebruiksanalyse</span><span class="sxs-lookup"><span data-stu-id="ffb59-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="ffb59-104">Raadpleeg de volgende lijst met foutmeldingen voor hulp bij de meest voorkomende problemen met het Microsoft 365 Gebruiksanalyse.</span><span class="sxs-lookup"><span data-stu-id="ffb59-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="ffb59-105">De aanvraag kan niet worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="ffb59-105">We are unable to process your request.</span></span> <span data-ttu-id="ffb59-106">U moet eerst een abonnement op deze gegevens opzeggen via het Microsoft 365-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="ffb59-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="ffb59-107">**Fout code:** 422</span><span class="sxs-lookup"><span data-stu-id="ffb59-107">**Error Code:** 422</span></span> 
  
 <span data-ttu-id="ffb59-108">**Waar wordt dit bericht weergegeven:** In Power BI wanneer u verbinding maakt met de sjabloon app Microsoft 365 gebruiksanalyse of wanneer u de Microsoft 365-rapportage-Api's direct aanroept.</span><span class="sxs-lookup"><span data-stu-id="ffb59-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="ffb59-109">**Oorzaak:** Voordat u verbinding kunt maken met de app, moet u zich abonneren op de gegevens in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="ffb59-109">**Cause:** Before you can connect to the app, you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="ffb59-110">Als u deze stap niet eerst kunt voltooien, kunt u geen verbinding maken met de sjabloon-app, zelfs niet als u uw Microsoft 365-Tenant-ID opgeeft.</span><span class="sxs-lookup"><span data-stu-id="ffb59-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant ID.</span></span> 
  
 <span data-ttu-id="ffb59-111">**Oplossing voor deze fout:** Als u zich wilt abonneren op de gegevens, gaat u naar het Beheercentrum \> **rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> en zoekt u de tegel Microsoft 365 gebruiksanalyse op de hoofdpagina van het dashboard.</span><span class="sxs-lookup"><span data-stu-id="ffb59-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="ffb59-112">Selecteer de knop **aan de slag** en klik in het deelvenster **rapporten** dat wordt geopend, de optie **gegevens beschikbaar maken voor Microsoft 365 Usage Analytics voor Power bi** instellen en **Opslaan** .</span><span class="sxs-lookup"><span data-stu-id="ffb59-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save** .</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="ffb59-113">Uw gegevens worden verwerkt</span><span class="sxs-lookup"><span data-stu-id="ffb59-113">We are processing your data</span></span>

 <span data-ttu-id="ffb59-114">**Waar wordt dit bericht weergegeven:** In de tegel **Microsoft 365 gebruiksanalyse** in het dashboard **gebruik** in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="ffb59-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="ffb59-115">**Oorzaak:** Wanneer u [zich aanmeldt om gegevens te zien in de sjabloon-app](enable-usage-analytics.md) van het microsoft 365-Beheercentrum, begint het microsoft 365-systeem met het genereren van historische gebruiksgegevens voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ffb59-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="ffb59-116">Afhankelijk van de grootte van uw tenant kan dit 2 tot 48 uur duren.</span><span class="sxs-lookup"><span data-stu-id="ffb59-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="ffb59-117">**Oplossing:** Even geduld, maar als het bericht na 3 dagen nog niet **is veranderd in uw gegevens** , kunt u [contact opnemen met de ondersteuning van Microsoft 365 voor bedrijven](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="ffb59-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="ffb59-118">De aanvraag kan momenteel niet worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="ffb59-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="ffb59-119">De gegevens voor uw organisatie worden nog voorbereid</span><span class="sxs-lookup"><span data-stu-id="ffb59-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="ffb59-120">**Foutcode:** 423</span><span class="sxs-lookup"><span data-stu-id="ffb59-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="ffb59-121">**Waar wordt dit bericht weergegeven:** In Power BI, wanneer u verbinding maakt met de app Microsoft 365 gebruiksanalyse of wanneer u de Microsoft 365-rapportage-Api's direct aanroept.</span><span class="sxs-lookup"><span data-stu-id="ffb59-121">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="ffb59-122">**Oorzaak:** Wanneer u [zich aanmeldt om gegevens in de sjabloon-app te zien](enable-usage-analytics.md) vanuit het Beheercentrum, wordt 365 er begonnen met het genereren van historische gebruiksgegevens voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ffb59-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="ffb59-123">Afhankelijk van de grootte van de Tenant, kan deze stap twee uur tot 48 uur duren.</span><span class="sxs-lookup"><span data-stu-id="ffb59-123">Depending on the size of your tenant, this step could take anywhere between two hours to 48 hours.</span></span> 
  
 <span data-ttu-id="ffb59-124">**Oplossing:** Maar als het bericht nog niet is veranderd in **uw gegevens zijn gereed** , [neemt u contact op met de ondersteuning van Microsoft 365 voor bedrijven](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="ffb59-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="ffb59-125">De opgegeven tenant-id heeft niet de juiste indeling</span><span class="sxs-lookup"><span data-stu-id="ffb59-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="ffb59-126">**Foutcode:** 400</span><span class="sxs-lookup"><span data-stu-id="ffb59-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="ffb59-127">**Waar wordt dit bericht weergegeven:** In Power BI, wanneer u verbinding maakt met de app Microsoft 365 gebruiksanalyse of wanneer u de Microsoft 365-rapportage-Api's direct aanroept.</span><span class="sxs-lookup"><span data-stu-id="ffb59-127">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="ffb59-128">**Oorzaak:** De Tenant-ID is een GUID en moet de indeling XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX hebben.</span><span class="sxs-lookup"><span data-stu-id="ffb59-128">**Cause:** The tenant ID is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span></span> <span data-ttu-id="ffb59-129">Als u een andere tekenreeks opgeeft in het invoervak van de Tenant, krijgt u deze fout.</span><span class="sxs-lookup"><span data-stu-id="ffb59-129">If you enter any other string in the tenant input box, you will get this error.</span></span> 
  
 <span data-ttu-id="ffb59-130">**Oplossing voor deze fout:** Ga naar het Beheercentrum \> **rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> en zoek de tegel Microsoft 365 Usage Analytics op de hoofdpagina van het dashboard.</span><span class="sxs-lookup"><span data-stu-id="ffb59-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="ffb59-131">De Tenant-ID wordt weergegeven op de tegel.</span><span class="sxs-lookup"><span data-stu-id="ffb59-131">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="ffb59-132">U kunt het hierheen kopiëren en plakken in het dialoogvenster voor het maken van verbinding met de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="ffb59-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="ffb59-133">De opgegeven tenant-id wordt niet herkend door het systeem</span><span class="sxs-lookup"><span data-stu-id="ffb59-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="ffb59-134">**Foutcode:** 404</span><span class="sxs-lookup"><span data-stu-id="ffb59-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="ffb59-135">**Waar wordt dit bericht weergegeven:** In Power BI wanneer u verbinding maakt met de sjabloon app Microsoft 365 gebruiksanalyse of wanneer u de Microsoft 365-rapportage-Api's direct aanroept.</span><span class="sxs-lookup"><span data-stu-id="ffb59-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="ffb59-136">**Oorzaak:** De opgegeven Tenant-ID is niet geldig of bestaat niet.</span><span class="sxs-lookup"><span data-stu-id="ffb59-136">**Cause:** The tenant ID you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="ffb59-137">**Oplossing voor deze fout:** Ga naar het Beheercentrum \> **rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> en zoek de tegel Microsoft 365 Usage Analytics op de hoofdpagina van het dashboard.</span><span class="sxs-lookup"><span data-stu-id="ffb59-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="ffb59-138">De Tenant-ID wordt weergegeven op de tegel.</span><span class="sxs-lookup"><span data-stu-id="ffb59-138">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="ffb59-139">U kunt het hierheen kopiëren en plakken in het dialoogvenster voor het maken van verbinding met de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="ffb59-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="ffb59-140">Voer uw referenties nogmaals in om u opnieuw aan te melden bij Power BI</span><span class="sxs-lookup"><span data-stu-id="ffb59-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="ffb59-141">Foutcode: 302</span><span class="sxs-lookup"><span data-stu-id="ffb59-141">Error Code: 302</span></span>
  
 <span data-ttu-id="ffb59-142">**Waar wordt dit bericht weergegeven:** In Power BI wanneer u verbinding maakt met de sjabloon app Microsoft 365 gebruiksanalyse of wanneer u de Microsoft 365-rapportage-Api's direct aanroept.</span><span class="sxs-lookup"><span data-stu-id="ffb59-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="ffb59-143">**Oorzaak:** De autorisatie is mislukt en u moet uw referenties mogelijk opnieuw invoeren.</span><span class="sxs-lookup"><span data-stu-id="ffb59-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="ffb59-144">**Oplossing:** Meld u af en weer aan bij Power BI.</span><span class="sxs-lookup"><span data-stu-id="ffb59-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="ffb59-145">U bent niet gemachtigd voor toegang tot deze gegevens.</span><span class="sxs-lookup"><span data-stu-id="ffb59-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="ffb59-146">Om toegang te krijgen tot de gegevens van deze service moet u een globale beheerder of een van de productbeheerders zijn</span><span class="sxs-lookup"><span data-stu-id="ffb59-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="ffb59-147">**Foutcode:** 403</span><span class="sxs-lookup"><span data-stu-id="ffb59-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="ffb59-148">**Waar wordt dit bericht weergegeven:** In Power BI wanneer u verbinding maakt met de sjabloon app Microsoft 365 gebruiksanalyse of wanneer u de Microsoft 365-rapportage-Api's direct aanroept.</span><span class="sxs-lookup"><span data-stu-id="ffb59-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="ffb59-149">**Oorzaak:** De autorisatiecode is mislukt omdat de gebruiker die probeerde verbinding te maken met de sjabloon-app niet over het juiste machtigingsniveau beschikt voor toegang tot deze gegevens.</span><span class="sxs-lookup"><span data-stu-id="ffb59-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="ffb59-150">**Oplossing voor deze fout:** Voer de referenties in van een gebruiker die een **globale beheerder** , **Exchange-beheerder** , **Skype voor bedrijven-beheerder** , **SharePoint-beheerder** , **algemene lezer** of **rapportlezer** is om verbinding te maken met de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="ffb59-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin** , **Exchange admin** , **Skype for Business admin** , **SharePoint admin** , **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="ffb59-151">Zie [informatie over beheerdersrollen](../add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ffb59-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="ffb59-152">Vernieuwen mislukt</span><span class="sxs-lookup"><span data-stu-id="ffb59-152">Refresh failed</span></span>

 <span data-ttu-id="ffb59-153">**Waar wordt dit bericht weergegeven:** E-mail van Power BI of de status mislukt in de vernieuwingsgeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="ffb59-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="ffb59-154">**Oorzaak:** Soms worden de referenties van de gebruiker die verbonden zijn met de sjabloon-app opnieuw ingesteld en niet bijgewerkt in de verbindingsinstellingen van de sjabloon-app, zodat de gebruiker foutberichten vernieuwt.</span><span class="sxs-lookup"><span data-stu-id="ffb59-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="ffb59-155">**Oplossing voor deze fout:** Zoek in Power BI naar de gegevensset die hoort bij de app Microsoft 365 Usage Analytics-App, selecteer **vernieuwen plannen** en geef uw beheerdersreferenties op.</span><span class="sxs-lookup"><span data-stu-id="ffb59-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="ffb59-156">Als dat niet werkt, wist u de cache en maakt u de sjabloon-app opnieuw.</span><span class="sxs-lookup"><span data-stu-id="ffb59-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
