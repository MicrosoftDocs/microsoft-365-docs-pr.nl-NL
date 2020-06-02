---
title: Voorbereiden op implementatie van Office-clients door Microsoft 365 voor Bedrijven
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Lees hoe u de 32-bits Office-apps automatisch installeert op Windows 10-computers en deze up-to-date houdt.
ms.openlocfilehash: 2de492914edbde2afe593aac290c4a634b801443
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470942"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a><span data-ttu-id="1a6f3-103">Voorbereiden op implementatie van Office-clients door Microsoft 365 voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="1a6f3-103">Prepare for Office client deployment by Microsoft 365 for business</span></span>

<span data-ttu-id="1a6f3-104">Dit artikel is van toepassing op Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="1a6f3-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="1a6f3-105">De automatische installatie van Office-apps op clientcomputers voorbereiden</span><span class="sxs-lookup"><span data-stu-id="1a6f3-105">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="1a6f3-106">U Microsoft 365 Business Premium gebruiken om de 32-bits Office-apps automatisch op Windows 10-computers te installeren en ze actueel te houden met updates.</span><span class="sxs-lookup"><span data-stu-id="1a6f3-106">You can use Microsoft 365 Business Premium to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="1a6f3-107">Automatische installatie werkt het beste als de computer van de eindgebruiker op Windows 10 Business staat en:</span><span class="sxs-lookup"><span data-stu-id="1a6f3-107">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="1a6f3-108">geen bestaande Office-desktop-apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access en OneDrive) heeft.</span><span class="sxs-lookup"><span data-stu-id="1a6f3-108">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="1a6f3-109">of</span><span class="sxs-lookup"><span data-stu-id="1a6f3-109">or</span></span>
    
- <span data-ttu-id="1a6f3-110">er een bestaande versie van Office Klik-en-klaar is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="1a6f3-110">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="1a6f3-111">Om te bepalen of u de Klik-en-klaar-versie van Office hebt, gaat u in een Office-app naar **Bestand** \> **Account** ( **Office-Account** in Outlook).</span><span class="sxs-lookup"><span data-stu-id="1a6f3-111">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="1a6f3-112">Als u **Office-updates** ziet zoals weergegeven in de volgende afbeelding, is de installatie uitgevoerd met Klik-en-Klaar.</span><span class="sxs-lookup"><span data-stu-id="1a6f3-112">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="1a6f3-114">**Wie profiteert van het hebben van deze functie**</span><span class="sxs-lookup"><span data-stu-id="1a6f3-114">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="1a6f3-115">De eindgebruiker waarvan de pc:</span><span class="sxs-lookup"><span data-stu-id="1a6f3-115">The end user whose PC:</span></span>
  
- <span data-ttu-id="1a6f3-116">**Heeft** een Windows 10 Business-gebruikerslicentie, een actieve Microsoft 365 voor zakelijke licentie, Windows 10 Creators Update en is verbonden met Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1a6f3-116">**Has**  a Windows 10 Business user license, an active Microsoft 365 for business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="1a6f3-117">**Heeft geen** 64-bits Office-apps (bijvoorbeeld: Word, Excel, PowerPoint).</span><span class="sxs-lookup"><span data-stu-id="1a6f3-117">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="1a6f3-118">Als 64-bits Office-apps vereist zijn, past deze functie niet goed omdat er geen ondersteuning is voor het activeren van een 64-bits 2016 Click-to-Run-versie van Office vanuit de Microsoft 365 voor zakelijke beheerconsole.</span><span class="sxs-lookup"><span data-stu-id="1a6f3-118">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 for business admin console.</span></span> 
    
- <span data-ttu-id="1a6f3-119">**geen** 2016 Windows Installer (MSI) zelfstandige apps (zoals Visio of Project) heeft.</span><span class="sxs-lookup"><span data-stu-id="1a6f3-119">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="1a6f3-120">Microsoft 365 voor bedrijven upgradet Office naar de Klik-en-Klaar-versie van Office 2016 en dat werkt niet met zelfstandige Office 2016 MSI-apps.</span><span class="sxs-lookup"><span data-stu-id="1a6f3-120">Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="1a6f3-121">In de volgende tabel ziet u welke actie de eindgebruikers/beheerders moeten ondernemen, afhankelijk van hun beginstatus, om een succesvolle 32-bits Click-to-Run-versie van Office-implementatie te hebben vanuit de Microsoft 365 voor zakelijke beheerconsole.</span><span class="sxs-lookup"><span data-stu-id="1a6f3-121">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 for business admin console.</span></span>
  
|<span data-ttu-id="1a6f3-122">**Beginstatus van de Office-installatie**</span><span class="sxs-lookup"><span data-stu-id="1a6f3-122">**Starting Office install status**</span></span>|<span data-ttu-id="1a6f3-123">**Actie voor de installatie van Microsoft 365 voor Bedrijven**</span><span class="sxs-lookup"><span data-stu-id="1a6f3-123">**Action to take before Microsoft 365 for business Office install**</span></span>|<span data-ttu-id="1a6f3-124">**Eindstatus**</span><span class="sxs-lookup"><span data-stu-id="1a6f3-124">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1a6f3-125">Geen Office-suite geïnstalleerd</span><span class="sxs-lookup"><span data-stu-id="1a6f3-125">No Office suite installed</span></span>  <br/> |<span data-ttu-id="1a6f3-126">Geen</span><span class="sxs-lookup"><span data-stu-id="1a6f3-126">None</span></span>  <br/> |<span data-ttu-id="1a6f3-127">Office 2016 32-bits is geïnstalleerd met Klik-en-Werkscherm</span><span class="sxs-lookup"><span data-stu-id="1a6f3-127">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="1a6f3-128">Bestaande 32-bits Klik-en-klaar-versie van Office (2016 of lager) en geen zelfstandige apps</span><span class="sxs-lookup"><span data-stu-id="1a6f3-128">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="1a6f3-129">Geen</span><span class="sxs-lookup"><span data-stu-id="1a6f3-129">None</span></span>  <br/> |<span data-ttu-id="1a6f3-130">Er is, zo nodig **\***, een upgrade uitgevoerd naar de meest recente 32-bits Klik-en-klaar-versie van Office 2016</span><span class="sxs-lookup"><span data-stu-id="1a6f3-130">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="1a6f3-131">Bestaande Click-to-Run 32-bits versie van Office en Click-to-Run 32-bits of 64-bits zelfstandige Office-apps (bijvoorbeeld Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="1a6f3-131">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="1a6f3-132">Geen</span><span class="sxs-lookup"><span data-stu-id="1a6f3-132">None</span></span>  <br/> |<span data-ttu-id="1a6f3-133">Zelfstandige apps worden niet beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="1a6f3-133">Standalone apps aren't affected.</span></span> <span data-ttu-id="1a6f3-134">Suite is bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016</span><span class="sxs-lookup"><span data-stu-id="1a6f3-134">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="1a6f3-135">Bestaande 32-bits Klik-en-klaar-versie van Office en 32-bits of 64-bits (behalve 2016) MSI zelfstandige Office-apps</span><span class="sxs-lookup"><span data-stu-id="1a6f3-135">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="1a6f3-136">Geen</span><span class="sxs-lookup"><span data-stu-id="1a6f3-136">None</span></span>  <br/> |<span data-ttu-id="1a6f3-137">Zelfstandige apps worden niet beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="1a6f3-137">Standalone apps aren't affected.</span></span> <span data-ttu-id="1a6f3-138">Suite is bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016</span><span class="sxs-lookup"><span data-stu-id="1a6f3-138">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="1a6f3-139">Een bestaande 64-bits Klik-en-klaar-versie van Office</span><span class="sxs-lookup"><span data-stu-id="1a6f3-139">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="1a6f3-140">De 64-bits Office-apps verwijderen als deze in het ok zijn om deze te vervangen door 32-bits Office-apps</span><span class="sxs-lookup"><span data-stu-id="1a6f3-140">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="1a6f3-141">Als 64-bits Office-apps worden verwijderd, wordt de 32-bits Klik-en-klaar-versie van Office 2016 geïnstalleerd</span><span class="sxs-lookup"><span data-stu-id="1a6f3-141">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="1a6f3-142">Een bestaande MSI-installatie van Office 2016 met of zonder zelfstandige apps</span><span class="sxs-lookup"><span data-stu-id="1a6f3-142">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="1a6f3-143">Verwijder MSI Office 2016.</span><span class="sxs-lookup"><span data-stu-id="1a6f3-143">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="1a6f3-p106">32-bits Klik-en-klaar-versie van Office 2016 is geïnstalleerd. Geen wijziging van zelfstandige apps</span><span class="sxs-lookup"><span data-stu-id="1a6f3-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="1a6f3-146">Bestaande MSI-installatie van Office 2013 (of eerder) en/of zelfstandige Office-apps</span><span class="sxs-lookup"><span data-stu-id="1a6f3-146">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="1a6f3-147">Geen</span><span class="sxs-lookup"><span data-stu-id="1a6f3-147">None</span></span>  <br/> |<span data-ttu-id="1a6f3-148">32-bits Klik-en-klaar-versie van Office 2016 met de bestaande MSI-Office-installatie (en zelfstandige apps) bestaan naast elkaar</span><span class="sxs-lookup"><span data-stu-id="1a6f3-148">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="1a6f3-149">**(\*) Opmerking:** Wordt niet bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016 vanwege een bekende fout.</span><span class="sxs-lookup"><span data-stu-id="1a6f3-149">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="1a6f3-150">Er is een oplossing aan de gang.</span><span class="sxs-lookup"><span data-stu-id="1a6f3-150">A fix is in progress.</span></span> 
  
