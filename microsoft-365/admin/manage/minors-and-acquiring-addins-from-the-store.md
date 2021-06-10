---
title: Minderjarigen en het verkrijgen van invoegtoepassingen uit de Store
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Meer informatie over de Algemene verordening gegevensbescherming (AVG) die van toepassing is op de persoonlijke gegevens van minderjarigen.
ms.openlocfilehash: e7f53a5a6b64f29f5029f0080fef44439c926edb
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580916"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="e1b49-103">Minderjarigen en het verkrijgen van invoegtoepassingen uit de Store</span><span class="sxs-lookup"><span data-stu-id="e1b49-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="e1b49-p101">De Algemene Verordening Gegevensbescherming (AVG) is een Europese verordening die in werking treedt op 25 mei 2018. De AVG biedt gebruikers rechten en beveiliging van hun gegevens. Eén van de aspecten van de AVG is dat persoonsgegevens van minderjarigen niet kunnen worden verzonden naar partijen die niet zijn goedgekeurd door de ouders of voogd. Wat de specifieke leeftijd is om iemand als minderjarig aan te merken, hangt af van het gebied waar de persoon zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="e1b49-p101">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018. It gives users rights to and protection of their data. One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved. The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="e1b49-p102">In de Verenigde Staten, Zuid-Korea, het Verenigd Koninkrijk en de Europese Unie zijn er bijvoorbeeld wettelijke voorschriften voor ouderlijke toestemming. In deze gebieden wordt een minderjarige geblokkeerd (via Azure Active Directory) om nieuwe Office-invoegtoepassingen in de Store te verkrijgen en eerder aangeschafte invoegtoepassingen uit te voeren. In landen zonder wettelijke voorschriften zijn er geen downloadbeperkingen.</span><span class="sxs-lookup"><span data-stu-id="e1b49-p102">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union. For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired. For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="e1b49-111">Een gebruiker wordt als minderjarige aangemerkt op basis van gegevens die zijn opgegeven in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e1b49-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="e1b49-112">De organisatiebeheerder is verantwoordelijk voor het declareren van de wettelijke leeftijdsgroep en de ouderlijke toestemming voor die gebruiker.</span><span class="sxs-lookup"><span data-stu-id="e1b49-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="e1b49-113">Als de ouder/voogd toestemming geeft voor een minderjarige met een specifieke invoegvoeging, kan de organisatiebeheerder gecentraliseerde implementatie gebruiken om die invoegvoeging te implementeren voor alle minderjarigen die toestemming hebben.</span><span class="sxs-lookup"><span data-stu-id="e1b49-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="e1b49-114">Als u wilt dat uw school of organisatie voldoet aan de AVG-vereisten voor minderjarigen, moet een van de volgende versies van Office zijn geïmplementeerd in uw school/organisatie.</span><span class="sxs-lookup"><span data-stu-id="e1b49-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="e1b49-115">**Voor Word, Excel, PowerPoint en Project**:</span><span class="sxs-lookup"><span data-stu-id="e1b49-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="e1b49-116">**Platform**</span><span class="sxs-lookup"><span data-stu-id="e1b49-116">**Platform**</span></span> <br/> |<span data-ttu-id="e1b49-117">**Buildnummer**</span><span class="sxs-lookup"><span data-stu-id="e1b49-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="e1b49-118">Microsoft 365-apps voor ondernemingen (huidig kanaal)</span><span class="sxs-lookup"><span data-stu-id="e1b49-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="e1b49-119">9001.2138</span><span class="sxs-lookup"><span data-stu-id="e1b49-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="e1b49-120">Microsoft 365-apps voor ondernemingen (Semi-Annual Enterprise Channel)</span><span class="sxs-lookup"><span data-stu-id="e1b49-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="e1b49-121">8431.2159</span><span class="sxs-lookup"><span data-stu-id="e1b49-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="e1b49-122">Office 2016 voor Windows</span><span class="sxs-lookup"><span data-stu-id="e1b49-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="e1b49-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="e1b49-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="e1b49-124">Office 2013 voor Windows</span><span class="sxs-lookup"><span data-stu-id="e1b49-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="e1b49-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="e1b49-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="e1b49-126">Office 2016 voor Mac</span><span class="sxs-lookup"><span data-stu-id="e1b49-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="e1b49-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="e1b49-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="e1b49-128">Webversie van Office</span><span class="sxs-lookup"><span data-stu-id="e1b49-128">Office for the web</span></span>  <br/> |<span data-ttu-id="e1b49-129">N.v.t.</span><span class="sxs-lookup"><span data-stu-id="e1b49-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="e1b49-130">**Voor Outlook**:</span><span class="sxs-lookup"><span data-stu-id="e1b49-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="e1b49-131">**Platform**</span><span class="sxs-lookup"><span data-stu-id="e1b49-131">**Platform**</span></span> <br/> |<span data-ttu-id="e1b49-132">**Buildnummer**</span><span class="sxs-lookup"><span data-stu-id="e1b49-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="e1b49-133">Outlook 2016 voor Windows (MSI)</span><span class="sxs-lookup"><span data-stu-id="e1b49-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="e1b49-134">Buildnummer n.t.b.</span><span class="sxs-lookup"><span data-stu-id="e1b49-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="e1b49-135">Outlook 2016 voor Windows (C2R)</span><span class="sxs-lookup"><span data-stu-id="e1b49-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="e1b49-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="e1b49-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="e1b49-137">Office 2016 voor Mac</span><span class="sxs-lookup"><span data-stu-id="e1b49-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="e1b49-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="e1b49-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="e1b49-139">Outlook Mobile voor iOS</span><span class="sxs-lookup"><span data-stu-id="e1b49-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="e1b49-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="e1b49-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="e1b49-141">Outlook Mobile voor Android</span><span class="sxs-lookup"><span data-stu-id="e1b49-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="e1b49-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="e1b49-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="e1b49-143">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="e1b49-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="e1b49-144">N.v.t.</span><span class="sxs-lookup"><span data-stu-id="e1b49-144">N/A</span></span>  <br/> |

 <span data-ttu-id="e1b49-145">**Vereisten voor Office 2013**</span><span class="sxs-lookup"><span data-stu-id="e1b49-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="e1b49-146">Word, Excel en PowerPoint 2013 voor Windows ondersteunen dezelfde secundaire controles als Active Directory Authentication Library (ADAL) is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e1b49-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="e1b49-147">Er zijn twee opties voor naleving, zoals hierna wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="e1b49-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="e1b49-148">**ADAL inschakelen**.</span><span class="sxs-lookup"><span data-stu-id="e1b49-148">**Enable ADAL**.</span></span> <span data-ttu-id="e1b49-149">In dit artikel wordt uitgelegd hoe u ADAL kunt inschakelen voor Office 2013: Gebruik Microsoft 365 moderne verificatie [met Office clients.](../../enterprise/modern-auth-for-office-2013-and-2016.md)</span><span class="sxs-lookup"><span data-stu-id="e1b49-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](../../enterprise/modern-auth-for-office-2013-and-2016.md).</span></span><br/><span data-ttu-id="e1b49-150">U hebt ook de registersleutels nodig om ADAL in te schakelen, zoals wordt beschreven in [Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten](../security-and-compliance/enable-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="e1b49-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="e1b49-151">Daarnaast moet u deze updates van april voor Office 2013 installeren:</span><span class="sxs-lookup"><span data-stu-id="e1b49-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="e1b49-152">Beschrijving van de beveiligingsupdate voor Outlook 2013: 10 april 2018</span><span class="sxs-lookup"><span data-stu-id="e1b49-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="e1b49-153">3 april 2018, update voor Office 2013 (KB4018333)</span><span class="sxs-lookup"><span data-stu-id="e1b49-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="e1b49-154">**Schakel ADAL niet in.**</span><span class="sxs-lookup"><span data-stu-id="e1b49-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="e1b49-155">Als u ADAL niet kunt inschakelen in Office 2013, is het onze aanbeveling om groepsbeleid te gebruiken om de Store uit te schakelen voor de Office clients.</span><span class="sxs-lookup"><span data-stu-id="e1b49-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="e1b49-156">Informatie over het uitschakelen van de app voor Office-instellingen vindt u [hier](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15)).</span><span class="sxs-lookup"><span data-stu-id="e1b49-156">Information on how to turn off the app for Office settings is located [here](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15)).</span></span>

## <a name="related-articles"></a><span data-ttu-id="e1b49-157">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="e1b49-157">Related articles</span></span>

[<span data-ttu-id="e1b49-158">Invoegtoepassingen implementeren in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="e1b49-158">Deploy add-ins in the admin center</span></span>](./manage-deployment-of-add-ins.md)

[<span data-ttu-id="e1b49-159">Invoegtoepassingen beheren in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="e1b49-159">Manage add-ins in the admin center</span></span>](./manage-addins-in-the-admin-center.md)
