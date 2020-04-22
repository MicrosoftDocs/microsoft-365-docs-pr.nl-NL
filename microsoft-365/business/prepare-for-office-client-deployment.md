---
title: Voorbereiden op de implementatie van Office-client door Microsoft 365 voor Bedrijven
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
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Lees hoe u de 32-bits Office-apps automatisch op Windows 10-computers installeert en deze up-to-date houdt.
ms.openlocfilehash: b5f01bc9bb10765929f3c6bdd5908e8b48a51a11
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633094"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a><span data-ttu-id="45b93-103">Voorbereiden op de implementatie van Office-client door Microsoft 365 voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="45b93-103">Prepare for Office client deployment by Microsoft 365 for business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="45b93-104">De automatische installatie van Office-apps op clientcomputers voorbereiden</span><span class="sxs-lookup"><span data-stu-id="45b93-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="45b93-105">U Microsoft 365 voor Bedrijven gebruiken om de 32-bits Office-apps automatisch op Windows 10-computers te installeren en actueel te houden met updates.</span><span class="sxs-lookup"><span data-stu-id="45b93-105">You can use Microsoft 365 for business to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="45b93-106">Automatische installatie werkt het beste als de computer van de eindgebruiker zich op Windows 10 Business bevindt en:</span><span class="sxs-lookup"><span data-stu-id="45b93-106">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="45b93-107">geen bestaande Office-desktop-apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access en OneDrive) heeft.</span><span class="sxs-lookup"><span data-stu-id="45b93-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="45b93-108">of</span><span class="sxs-lookup"><span data-stu-id="45b93-108">or</span></span>
    
- <span data-ttu-id="45b93-109">er een bestaande versie van Office Klik-en-klaar is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="45b93-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="45b93-110">Om te bepalen of u de Klik-en-klaar-versie van Office hebt, gaat u in een Office-app naar **Bestand** \> **Account** ( **Office-Account** in Outlook).</span><span class="sxs-lookup"><span data-stu-id="45b93-110">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="45b93-111">Als u **Office-updates** ziet zoals weergegeven in de volgende afbeelding, is de installatie uitgevoerd met Klik-en-Klaar.</span><span class="sxs-lookup"><span data-stu-id="45b93-111">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="45b93-113">**Wie profiteert van deze functie**</span><span class="sxs-lookup"><span data-stu-id="45b93-113">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="45b93-114">De eindgebruiker waarvan de pc:</span><span class="sxs-lookup"><span data-stu-id="45b93-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="45b93-115">**Heeft** een Windows 10 Business-gebruikerslicentie, een actieve Microsoft 365 voor bedrijvenlicentie, Windows 10 Creators Update en is verbonden met Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="45b93-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 for business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="45b93-116">**Heeft geen** 64-bits Office-apps (bijvoorbeeld Word, Excel, PowerPoint).</span><span class="sxs-lookup"><span data-stu-id="45b93-116">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="45b93-117">Als 64-bits Office-apps vereist zijn, past deze functie niet goed omdat er geen ondersteuning is voor het activeren van een 64-bits 2016 Click-to-Run-versie van Office vanuit de Microsoft 365 voor zakelijke beheerconsole.</span><span class="sxs-lookup"><span data-stu-id="45b93-117">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 for business admin console.</span></span> 
    
- <span data-ttu-id="45b93-118">**geen** 2016 Windows Installer (MSI) zelfstandige apps (zoals Visio of Project) heeft.</span><span class="sxs-lookup"><span data-stu-id="45b93-118">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="45b93-119">Microsoft 365 voor Bedrijven upgradet Office naar de Click-to-Run-versie van Office 2016 en dat werkt niet met zelfstandige apps van Office 2016 MSI.</span><span class="sxs-lookup"><span data-stu-id="45b93-119">Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="45b93-120">In de volgende tabel ziet u welke actie de eindgebruikers/beheerders mogelijk moeten ondernemen, afhankelijk van hun beginstatus, om een succesvolle 32-bits Click-to-Run-versie van Office-implementatie van de Microsoft 365 voor zakelijke beheerconsole te hebben.</span><span class="sxs-lookup"><span data-stu-id="45b93-120">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 for business admin console.</span></span>
  
|<span data-ttu-id="45b93-121">**Beginstatus van de Office-installatie**</span><span class="sxs-lookup"><span data-stu-id="45b93-121">**Starting Office install status**</span></span>|<span data-ttu-id="45b93-122">**Actie die moet worden ondernomen voordat Microsoft 365 voor Bedrijven Office wordt geïnstalleerd**</span><span class="sxs-lookup"><span data-stu-id="45b93-122">**Action to take before Microsoft 365 for business Office install**</span></span>|<span data-ttu-id="45b93-123">**Eindstatus**</span><span class="sxs-lookup"><span data-stu-id="45b93-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="45b93-124">Geen Office-suite geïnstalleerd</span><span class="sxs-lookup"><span data-stu-id="45b93-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="45b93-125">Geen</span><span class="sxs-lookup"><span data-stu-id="45b93-125">None</span></span>  <br/> |<span data-ttu-id="45b93-126">Office 2016 32-bits is geïnstalleerd met Klik-en-Uit</span><span class="sxs-lookup"><span data-stu-id="45b93-126">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="45b93-127">Bestaande 32-bits Klik-en-klaar-versie van Office (2016 of lager) en geen zelfstandige apps</span><span class="sxs-lookup"><span data-stu-id="45b93-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="45b93-128">Geen</span><span class="sxs-lookup"><span data-stu-id="45b93-128">None</span></span>  <br/> |<span data-ttu-id="45b93-129">Er is, zo nodig **\***, een upgrade uitgevoerd naar de meest recente 32-bits Klik-en-klaar-versie van Office 2016</span><span class="sxs-lookup"><span data-stu-id="45b93-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="45b93-130">Bestaande Click-to-Run 32-bits versie van Office en Click-to-Run 32-bits of 64-bits standalone Office-apps (bijvoorbeeld Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="45b93-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="45b93-131">Geen</span><span class="sxs-lookup"><span data-stu-id="45b93-131">None</span></span>  <br/> |<span data-ttu-id="45b93-132">Zelfstandige apps worden niet beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="45b93-132">Standalone apps aren't affected.</span></span> <span data-ttu-id="45b93-133">Suite is bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016</span><span class="sxs-lookup"><span data-stu-id="45b93-133">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="45b93-134">Bestaande 32-bits Klik-en-klaar-versie van Office en 32-bits of 64-bits (behalve 2016) MSI zelfstandige Office-apps</span><span class="sxs-lookup"><span data-stu-id="45b93-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="45b93-135">Geen</span><span class="sxs-lookup"><span data-stu-id="45b93-135">None</span></span>  <br/> |<span data-ttu-id="45b93-136">Zelfstandige apps worden niet beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="45b93-136">Standalone apps aren't affected.</span></span> <span data-ttu-id="45b93-137">Suite is bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016</span><span class="sxs-lookup"><span data-stu-id="45b93-137">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="45b93-138">Een bestaande 64-bits Klik-en-klaar-versie van Office</span><span class="sxs-lookup"><span data-stu-id="45b93-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="45b93-139">Verwijder de 64-bits Office-apps als het ok is om ze te vervangen door 32-bits Office-apps</span><span class="sxs-lookup"><span data-stu-id="45b93-139">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="45b93-140">Als 64-bits Office-apps worden verwijderd, wordt de 32-bits Klik-en-klaar-versie van Office 2016 geïnstalleerd</span><span class="sxs-lookup"><span data-stu-id="45b93-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="45b93-141">Een bestaande MSI-installatie van Office 2016 met of zonder zelfstandige apps</span><span class="sxs-lookup"><span data-stu-id="45b93-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="45b93-142">Verwijder MSI Office 2016.</span><span class="sxs-lookup"><span data-stu-id="45b93-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="45b93-p106">32-bits Klik-en-klaar-versie van Office 2016 is geïnstalleerd. Geen wijziging van zelfstandige apps</span><span class="sxs-lookup"><span data-stu-id="45b93-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="45b93-145">Bestaande MSI-installatie van Office 2013 (of eerder) en/of zelfstandige Office-apps</span><span class="sxs-lookup"><span data-stu-id="45b93-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="45b93-146">Geen</span><span class="sxs-lookup"><span data-stu-id="45b93-146">None</span></span>  <br/> |<span data-ttu-id="45b93-147">32-bits Klik-en-klaar-versie van Office 2016 met de bestaande MSI-Office-installatie (en zelfstandige apps) bestaan naast elkaar</span><span class="sxs-lookup"><span data-stu-id="45b93-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="45b93-148">**(\*) Opmerking:** Wordt niet bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016 vanwege een bekende fout.</span><span class="sxs-lookup"><span data-stu-id="45b93-148">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="45b93-149">Er wordt gewerkt aan een oplossing.</span><span class="sxs-lookup"><span data-stu-id="45b93-149">A fix is in progress.</span></span> 
  
