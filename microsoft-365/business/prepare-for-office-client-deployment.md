---
title: Bereid u voor op de implementatie van de Office-client door Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Informatie over het automatisch installeren van de 32-bits Office-toepassingen op computers met Windows 10 en up-to-date te houden.
ms.openlocfilehash: c8e93746b89925d6b6a928a474fe5736e2834987
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286641"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a><span data-ttu-id="ffdf3-103">Bereid u voor op de implementatie van de Office-client door Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="ffdf3-103">Prepare for Office client deployment by Microsoft 365 Business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="ffdf3-104">De automatische installatie van Office-apps op clientcomputers voorbereiden</span><span class="sxs-lookup"><span data-stu-id="ffdf3-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="ffdf3-105">U kunt met Microsoft 365 Business automatisch de 32-bits Office-apps installeren op computers met Windows 10 en ze bijwerken met updates.</span><span class="sxs-lookup"><span data-stu-id="ffdf3-105">You can use Microsoft 365 Business to automatically install the 32-bit Office apps to Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="ffdf3-106">Dit werkt het beste als de computer van de eindgebruiker Windows 10 Business uitvoert en:</span><span class="sxs-lookup"><span data-stu-id="ffdf3-106">This works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="ffdf3-107">geen bestaande Office-desktop-apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access en OneDrive) heeft.</span><span class="sxs-lookup"><span data-stu-id="ffdf3-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="ffdf3-108">of</span><span class="sxs-lookup"><span data-stu-id="ffdf3-108">or</span></span>
    
- <span data-ttu-id="ffdf3-109">er een bestaande versie van Office Klik-en-klaar is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="ffdf3-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="ffdf3-p101">Om te bepalen of u de Klik-en-klaar-versie van Office hebt, gaat u in een Office-app naar **Bestand** \> **Account** ( **Office-Account** in Outlook). Als u Office-updates kunt zien zoals in de volgende afbeelding wordt weergegeven, is de installatie gedaan met behulp van Klik-en-klaar.</span><span class="sxs-lookup"><span data-stu-id="ffdf3-p101">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook). If you see Office Updates as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="ffdf3-113">**Wie heeft er voordeel van deze functie?**</span><span class="sxs-lookup"><span data-stu-id="ffdf3-113">**Who will benefit from having this feature**</span></span>
  
<span data-ttu-id="ffdf3-114">De eindgebruiker waarvan de pc:</span><span class="sxs-lookup"><span data-stu-id="ffdf3-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="ffdf3-115">**een** gebruikerslicentie voor Windows 10 Business, een actieve Microsoft 365 Business-licentie, Windows 10 Creators-update heeft en is verbonden met Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ffdf3-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="ffdf3-p102">**geen** 64-bits Office-apps heeft (bijvoorbeeld: Word, Excel, PowerPoint). Als de 64-bits Office-apps vereist zijn, sluit deze functie niet goed aan, omdat er geen ondersteuning is voor het genereren van een 64-bits 2016 Klik-en-klaar-versie van Office vanaf de Microsoft 365 Business-beheerconsole.</span><span class="sxs-lookup"><span data-stu-id="ffdf3-p102">**Doesn't have** 64-bit Office apps (example: Word, Excel, Powerpoint). If 64-bit Office apps are required, then this feature is not a good fit because there is no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 Business admin console.</span></span> 
    
- <span data-ttu-id="ffdf3-p103">**geen** 2016 Windows Installer (MSI) zelfstandige apps (zoals Visio of Project) heeft. Microsoft 365 Business upgradet Office naar de Klik-en-klaar-versie van Office 2016 en die werkt niet met zelfstandige apps van Office 2016 MSI.</span><span class="sxs-lookup"><span data-stu-id="ffdf3-p103">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project). Microsoft 365 Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="ffdf3-120">In de volgende tabel ziet u de actie die de eindgebruikers/beheerders mogelijk uit moeten voeren, afhankelijk van hun beginstatus, om een succesvolle 32-bits Klik-en-klaar-versie van Office te implementeren vanaf de Microsoft 365 Business-beheerconsole.</span><span class="sxs-lookup"><span data-stu-id="ffdf3-120">The following table details what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 Business admin console.</span></span>
  
|<span data-ttu-id="ffdf3-121">**Beginstatus van de Office-installatie**</span><span class="sxs-lookup"><span data-stu-id="ffdf3-121">**Starting Office install status**</span></span>|<span data-ttu-id="ffdf3-122">**Actie die moet worden uitgevoerd voor de Microsoft 365 Business-installatie van Office**</span><span class="sxs-lookup"><span data-stu-id="ffdf3-122">**Action to take before Microsoft 365 Business Office install**</span></span>|<span data-ttu-id="ffdf3-123">**Eindstatus**</span><span class="sxs-lookup"><span data-stu-id="ffdf3-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ffdf3-124">Geen Office-suite geïnstalleerd</span><span class="sxs-lookup"><span data-stu-id="ffdf3-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="ffdf3-125">Geen</span><span class="sxs-lookup"><span data-stu-id="ffdf3-125">None</span></span>  <br/> |<span data-ttu-id="ffdf3-126">32-bits Office 2016 is geïnstalleerd met behulp van klik-en-klaar</span><span class="sxs-lookup"><span data-stu-id="ffdf3-126">Office 2016 32-bit is installed by using click-to-run</span></span>  <br/> |
|<span data-ttu-id="ffdf3-127">Bestaande 32-bits Klik-en-klaar-versie van Office (2016 of lager) en geen zelfstandige apps</span><span class="sxs-lookup"><span data-stu-id="ffdf3-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="ffdf3-128">Geen</span><span class="sxs-lookup"><span data-stu-id="ffdf3-128">None</span></span>  <br/> |<span data-ttu-id="ffdf3-129">Er is, zo nodig **\***, een upgrade uitgevoerd naar de meest recente 32-bits Klik-en-klaar-versie van Office 2016</span><span class="sxs-lookup"><span data-stu-id="ffdf3-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="ffdf3-130">Bestaande 32-bits Klik-en-klaar-versie van Office en 32-bits of 64-bits Klik-en-klaar zelfstandige Office-apps (bijvoorbeeld, Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="ffdf3-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32- or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="ffdf3-131">Geen</span><span class="sxs-lookup"><span data-stu-id="ffdf3-131">None</span></span>  <br/> |<span data-ttu-id="ffdf3-p104">Zelfstandige apps worden niet beïnvloed. Suite is bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016</span><span class="sxs-lookup"><span data-stu-id="ffdf3-p104">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="ffdf3-134">Bestaande 32-bits Klik-en-klaar-versie van Office en 32-bits of 64-bits (behalve 2016) MSI zelfstandige Office-apps</span><span class="sxs-lookup"><span data-stu-id="ffdf3-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="ffdf3-135">Geen</span><span class="sxs-lookup"><span data-stu-id="ffdf3-135">None</span></span>  <br/> |<span data-ttu-id="ffdf3-p105">Zelfstandige apps worden niet beïnvloed. Suite is bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016</span><span class="sxs-lookup"><span data-stu-id="ffdf3-p105">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="ffdf3-138">Een bestaande 64-bits Klik-en-klaar-versie van Office</span><span class="sxs-lookup"><span data-stu-id="ffdf3-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="ffdf3-139">Verwijder de 64-bits Office-apps als deze vervangen kunnen worden door 32-bits Office-apps</span><span class="sxs-lookup"><span data-stu-id="ffdf3-139">Uninstall the 64-bit Office apps, if it is OK to replace it with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="ffdf3-140">Als 64-bits Office-apps worden verwijderd, wordt de 32-bits Klik-en-klaar-versie van Office 2016 geïnstalleerd</span><span class="sxs-lookup"><span data-stu-id="ffdf3-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="ffdf3-141">Een bestaande MSI-installatie van Office 2016 met of zonder zelfstandige apps</span><span class="sxs-lookup"><span data-stu-id="ffdf3-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="ffdf3-142">Verwijder MSI Office 2016.</span><span class="sxs-lookup"><span data-stu-id="ffdf3-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="ffdf3-p106">32-bits Klik-en-klaar-versie van Office 2016 is geïnstalleerd. Geen wijziging van zelfstandige apps</span><span class="sxs-lookup"><span data-stu-id="ffdf3-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="ffdf3-145">Bestaande MSI-installatie van Office 2013 (of eerder) en/of zelfstandige Office-apps</span><span class="sxs-lookup"><span data-stu-id="ffdf3-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="ffdf3-146">Geen</span><span class="sxs-lookup"><span data-stu-id="ffdf3-146">None</span></span>  <br/> |<span data-ttu-id="ffdf3-147">32-bits Klik-en-klaar-versie van Office 2016 met de bestaande MSI-Office-installatie (en zelfstandige apps) bestaan naast elkaar</span><span class="sxs-lookup"><span data-stu-id="ffdf3-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="ffdf3-p107">**(\*) Opmerking:** Wordt niet bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016 vanwege een bekende fout. Er wordt aan de oplossing gewerkt.</span><span class="sxs-lookup"><span data-stu-id="ffdf3-p107">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug. Fix is in progress.</span></span> 
  


