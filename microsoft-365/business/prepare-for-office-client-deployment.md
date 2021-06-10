---
title: Voorbereiden op Office clientimplementatie per Microsoft 365 voor bedrijven
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Meer informatie over het automatisch installeren van de 32-bits Office apps op Windows 10 computers en deze bijgewerkt houden.
ms.openlocfilehash: 868d06fadfef0f55b41131b7fdfbb368b9128405
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580049"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a><span data-ttu-id="c9ffb-103">Voorbereiden op Office clientimplementatie per Microsoft 365 voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="c9ffb-103">Prepare for Office client deployment by Microsoft 365 for business</span></span>

<span data-ttu-id="c9ffb-104">Dit artikel is van toepassing op Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="c9ffb-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="c9ffb-105">De automatische installatie van Office-apps op clientcomputers voorbereiden</span><span class="sxs-lookup"><span data-stu-id="c9ffb-105">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="c9ffb-106">U kunt Microsoft 365 Business Premium gebruiken om de 32-bits apps Office op Windows 10 computers te installeren en deze op de hoogte te houden van updates.</span><span class="sxs-lookup"><span data-stu-id="c9ffb-106">You can use Microsoft 365 Business Premium to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="c9ffb-107">Automatische installatie werkt het beste als de computer van de eindgebruiker is Windows 10 Business en:</span><span class="sxs-lookup"><span data-stu-id="c9ffb-107">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="c9ffb-108">geen bestaande Office-desktop-apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access en OneDrive) heeft.</span><span class="sxs-lookup"><span data-stu-id="c9ffb-108">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="c9ffb-109">of</span><span class="sxs-lookup"><span data-stu-id="c9ffb-109">or</span></span>
    
- <span data-ttu-id="c9ffb-110">er een bestaande versie van Office Klik-en-klaar is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="c9ffb-110">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="c9ffb-111">Om te bepalen of u de Klik-en-klaar-versie van Office hebt, gaat u in een Office-app naar **Bestand** \> **Account** ( **Office-Account** in Outlook).</span><span class="sxs-lookup"><span data-stu-id="c9ffb-111">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="c9ffb-112">Als u Office **in** de volgende afbeelding ziet, is de installatie uitgevoerd met Klik-en-Klaar.</span><span class="sxs-lookup"><span data-stu-id="c9ffb-112">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="c9ffb-114">**Wie voordeel van deze functie**</span><span class="sxs-lookup"><span data-stu-id="c9ffb-114">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="c9ffb-115">De eindgebruiker waarvan de pc:</span><span class="sxs-lookup"><span data-stu-id="c9ffb-115">The end user whose PC:</span></span>
  
- <span data-ttu-id="c9ffb-116">**Heeft** een Windows 10 Business gebruikerslicentie, een actieve licentie Microsoft 365 voor bedrijven, Windows 10 Creators Update en is lid van Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c9ffb-116">**Has**  a Windows 10 Business user license, an active Microsoft 365 for business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="c9ffb-117">**Heeft geen** 64-bits Office apps (bijvoorbeeld: Word, Excel, PowerPoint).</span><span class="sxs-lookup"><span data-stu-id="c9ffb-117">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="c9ffb-118">Als 64-bits Office-apps vereist zijn, is deze functie niet geschikt omdat er geen ondersteuning is voor het activeren van een 64-bits 2016 Klik-en-Werk-versie van Office vanaf de Microsoft 365 voor bedrijven-beheerconsole.</span><span class="sxs-lookup"><span data-stu-id="c9ffb-118">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 for business admin console.</span></span> 
    
- <span data-ttu-id="c9ffb-119">**geen** 2016 Windows Installer (MSI) zelfstandige apps (zoals Visio of Project) heeft.</span><span class="sxs-lookup"><span data-stu-id="c9ffb-119">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="c9ffb-120">Microsoft 365 voor bedrijven upgrades Office de Klik-en-Klaar-versie van Office 2016 en dat werkt niet met zelfstandige Office 2016 MSI.</span><span class="sxs-lookup"><span data-stu-id="c9ffb-120">Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="c9ffb-121">In de volgende tabel ziet u welke actie de eindgebruikers/beheerders mogelijk moeten ondernemen, afhankelijk van hun begintoestand, om een succesvolle 32-bits Klik-en-Werk-versie van Office-implementatie te hebben vanaf de Microsoft 365 voor zakelijke beheerconsole.</span><span class="sxs-lookup"><span data-stu-id="c9ffb-121">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 for business admin console.</span></span>
  
|<span data-ttu-id="c9ffb-122">**Beginstatus van de Office-installatie**</span><span class="sxs-lookup"><span data-stu-id="c9ffb-122">**Starting Office install status**</span></span>|<span data-ttu-id="c9ffb-123">**Actie die moet worden ondernomen voordat Microsoft 365 voor bedrijven Office installeren**</span><span class="sxs-lookup"><span data-stu-id="c9ffb-123">**Action to take before Microsoft 365 for business Office install**</span></span>|<span data-ttu-id="c9ffb-124">**Eindstatus**</span><span class="sxs-lookup"><span data-stu-id="c9ffb-124">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c9ffb-125">Geen Office-suite geïnstalleerd</span><span class="sxs-lookup"><span data-stu-id="c9ffb-125">No Office suite installed</span></span>  <br/> |<span data-ttu-id="c9ffb-126">Geen</span><span class="sxs-lookup"><span data-stu-id="c9ffb-126">None</span></span>  <br/> |<span data-ttu-id="c9ffb-127">Office 32-bits 2016 is geïnstalleerd met behulp van Klik-en-Werk</span><span class="sxs-lookup"><span data-stu-id="c9ffb-127">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="c9ffb-128">Bestaande 32-bits Klik-en-klaar-versie van Office (2016 of lager) en geen zelfstandige apps</span><span class="sxs-lookup"><span data-stu-id="c9ffb-128">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="c9ffb-129">Geen</span><span class="sxs-lookup"><span data-stu-id="c9ffb-129">None</span></span>  <br/> |<span data-ttu-id="c9ffb-130">Er is, zo nodig **\***, een upgrade uitgevoerd naar de meest recente 32-bits Klik-en-klaar-versie van Office 2016</span><span class="sxs-lookup"><span data-stu-id="c9ffb-130">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="c9ffb-131">Bestaande 32-bits 32-bits versie van Office en 32 bits- of 64-bits zelfstandige Office-apps (bijvoorbeeld Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="c9ffb-131">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="c9ffb-132">Geen</span><span class="sxs-lookup"><span data-stu-id="c9ffb-132">None</span></span>  <br/> |<span data-ttu-id="c9ffb-133">Zelfstandige apps worden niet beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="c9ffb-133">Standalone apps aren't affected.</span></span> <span data-ttu-id="c9ffb-134">Suite is bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016</span><span class="sxs-lookup"><span data-stu-id="c9ffb-134">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="c9ffb-135">Bestaande 32-bits Klik-en-klaar-versie van Office en 32-bits of 64-bits (behalve 2016) MSI zelfstandige Office-apps</span><span class="sxs-lookup"><span data-stu-id="c9ffb-135">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="c9ffb-136">Geen</span><span class="sxs-lookup"><span data-stu-id="c9ffb-136">None</span></span>  <br/> |<span data-ttu-id="c9ffb-137">Zelfstandige apps worden niet beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="c9ffb-137">Standalone apps aren't affected.</span></span> <span data-ttu-id="c9ffb-138">Suite is bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016</span><span class="sxs-lookup"><span data-stu-id="c9ffb-138">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="c9ffb-139">Een bestaande 64-bits Klik-en-klaar-versie van Office</span><span class="sxs-lookup"><span data-stu-id="c9ffb-139">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="c9ffb-140">Verwijder de 64-bits Office apps, als u deze kunt vervangen door 32-bits Office apps</span><span class="sxs-lookup"><span data-stu-id="c9ffb-140">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="c9ffb-141">Als 64-bits Office-apps worden verwijderd, wordt de 32-bits Klik-en-klaar-versie van Office 2016 geïnstalleerd</span><span class="sxs-lookup"><span data-stu-id="c9ffb-141">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="c9ffb-142">Een bestaande MSI-installatie van Office 2016 met of zonder zelfstandige apps</span><span class="sxs-lookup"><span data-stu-id="c9ffb-142">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="c9ffb-143">Verwijder MSI Office 2016.</span><span class="sxs-lookup"><span data-stu-id="c9ffb-143">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="c9ffb-p106">32-bits Klik-en-klaar-versie van Office 2016 is geïnstalleerd. Geen wijziging van zelfstandige apps</span><span class="sxs-lookup"><span data-stu-id="c9ffb-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="c9ffb-146">Bestaande MSI-installatie van Office 2013 (of eerder) en/of zelfstandige Office-apps</span><span class="sxs-lookup"><span data-stu-id="c9ffb-146">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="c9ffb-147">Geen</span><span class="sxs-lookup"><span data-stu-id="c9ffb-147">None</span></span>  <br/> |<span data-ttu-id="c9ffb-148">32-bits Klik-en-klaar-versie van Office 2016 met de bestaande MSI-Office-installatie (en zelfstandige apps) bestaan naast elkaar</span><span class="sxs-lookup"><span data-stu-id="c9ffb-148">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="c9ffb-149">**(\*) Opmerking:** Wordt niet bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016 vanwege een bekende fout.</span><span class="sxs-lookup"><span data-stu-id="c9ffb-149">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="c9ffb-150">Er wordt een oplossing uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="c9ffb-150">A fix is in progress.</span></span> 
  
