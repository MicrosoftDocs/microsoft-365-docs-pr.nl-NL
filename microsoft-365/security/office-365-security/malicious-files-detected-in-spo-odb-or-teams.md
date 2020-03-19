---
title: Informatie weergeven over schadelijke bestanden die zijn gedetecteerd in SharePoint, OneDrive of Microsoft Teams
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
ms.collection:
- M365-security-compliance
description: Meer informatie over waar u naartoe gaan om informatie over schadelijke bestanden te bekijken die zijn gedetecteerd in SharePoint, OneDrive of Teams en hoe u actie ondernemen voor die bestanden.
ms.openlocfilehash: 49c7e1668602a63b8b82339ad0cc7823146212a4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42805910"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="76b2e-103">Informatie weergeven over schadelijke bestanden die zijn gedetecteerd in SharePoint, OneDrive of Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="76b2e-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

<span data-ttu-id="76b2e-104">[Office 365 ATP voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md) beschermt uw organisatie tegen schadelijke bestanden in documentbibliotheken en teamsites.</span><span class="sxs-lookup"><span data-stu-id="76b2e-104">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites.</span></span> <span data-ttu-id="76b2e-105">Wanneer een kwaadaardig bestand wordt gedetecteerd, wordt dat bestand geblokkeerd, zodat niemand het kan openen, kopiëren, verplaatsen of delen totdat verdere acties zijn uitgevoerd door het beveiligingsteam van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="76b2e-105">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="76b2e-106">Lees dit artikel voor meer informatie over het weergeven van informatie over gedetecteerde bestanden en welke acties u moet uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="76b2e-106">Read this article to learn how to view information about detected files and what actions to take.</span></span> 

<span data-ttu-id="76b2e-107">Als u de in dit artikel beschreven taken wilt uitvoeren, moet u over de benodigde machtigingen beschikken [voor het Office 365 Security &amp; Compliance Center.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="76b2e-107">In order to perform the tasks described in this article, you must have the necessary [permissions for the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="76b2e-108">Rapporten weergeven met informatie over gedetecteerde bestanden</span><span class="sxs-lookup"><span data-stu-id="76b2e-108">View reports with information about detected files</span></span>

<span data-ttu-id="76b2e-109">Als u de status en gedetailleerde informatie wilt weergeven over bestanden die zijn gedetecteerd door Office 365 ATP, u het rapport Status bedreigingsbeveiliging gebruiken.</span><span class="sxs-lookup"><span data-stu-id="76b2e-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat Protection Status report.</span></span>
  
1. <span data-ttu-id="76b2e-110">Kies in het [Office &amp; 365 Security Compliance Center](https://protection.office.com)de optie Status **bedreigingsbeveiliging** **van het** \> **dashboard** \> rapporten .</span><span class="sxs-lookup"><span data-stu-id="76b2e-110">In the [Office 365 Security &amp; Compliance Center](https://protection.office.com), choose **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
    
2. <span data-ttu-id="76b2e-111">Kies **detailstabel weergeven**in de rechterbovenhoek van het rapport .</span><span class="sxs-lookup"><span data-stu-id="76b2e-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="76b2e-112">Bekijk de lijst met bestanden die in het rapport zijn gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="76b2e-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="76b2e-113">Selecteer een item in de lijst om gedetailleerde informatie weer te geven, waaronder acties, de bestandsnaam, het bestandspad en meer.</span><span class="sxs-lookup"><span data-stu-id="76b2e-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="76b2e-114">Kies het tabblad **Geavanceerde analyse** om informatie weer te geven, zoals waargenomen gedrag en analysedetails.</span><span class="sxs-lookup"><span data-stu-id="76b2e-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="76b2e-115">Bestanden in quarantaine weergeven en actie ondernemen</span><span class="sxs-lookup"><span data-stu-id="76b2e-115">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="76b2e-116">Kies in het Office &amp; 365 Security Compliance Center de optie **Quarantaine van bedreigingsbeheer.** \> **Review** \> **Quarantine**</span><span class="sxs-lookup"><span data-stu-id="76b2e-116">In the Office 365 Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span> <span data-ttu-id="76b2e-117">(U ook [https://protection.office.com/quarantine](https://protection.office.com/quarantine)rechtstreeks naar .)</span><span class="sxs-lookup"><span data-stu-id="76b2e-117">(You can also go directly to [https://protection.office.com/quarantine](https://protection.office.com/quarantine).)</span></span>
    
2. <span data-ttu-id="76b2e-118">Wijzig in de linkerbovenhoek het vervolgkeuzemenu van **E-mails** in **Bestanden.**</span><span class="sxs-lookup"><span data-stu-id="76b2e-118">In the upper left corner, change the drop-down menu from **Emails** to **Files**.</span></span> <span data-ttu-id="76b2e-119">Als de lijst met resultaten te veel items bevat, gebruikt u **de** filterfunctionaliteit om de selectie te beperken.</span><span class="sxs-lookup"><span data-stu-id="76b2e-119">If the list of results includes too many items, use the **Filter** functionality to narrow down the selection.</span></span>
    
3. <span data-ttu-id="76b2e-120">Selecteer een item in de lijst om gedetailleerde informatie weer te geven, inclusief de URL van het bestand.</span><span class="sxs-lookup"><span data-stu-id="76b2e-120">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="76b2e-121">Kies een beschikbare actie.</span><span class="sxs-lookup"><span data-stu-id="76b2e-121">Choose an available action.</span></span>
    
  - <span data-ttu-id="76b2e-122">Kies **Bestand vrijgeven** om het bestand te deblokkeren.</span><span class="sxs-lookup"><span data-stu-id="76b2e-122">Choose **Release file** to unblock the file.</span></span> 
    
    <span data-ttu-id="76b2e-123">Selecteer **Rapport verzenden naar Microsoft** om het bestand als foutpositief aan Microsoft te melden.</span><span class="sxs-lookup"><span data-stu-id="76b2e-123">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 
    
  - <span data-ttu-id="76b2e-124">Kies **Bestand downloaden** om het bestand verder te onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="76b2e-124">Choose **Download file** to investigate the file further.</span></span> 
    
  - <span data-ttu-id="76b2e-125">Kies **Verwijderen uit quarantaine** om het bestand uit de lijst met in quarantaine geplaatste items te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="76b2e-125">Choose **Remove from quarantine** to remove the file from the list of quarantined items.</span></span> <span data-ttu-id="76b2e-126">Als u deze optie kiest, moet u het bestand ook verwijderen uit de desbetreffende bibliotheek in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="76b2e-126">If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="76b2e-127">Met deze optie wordt het niet deblokkeren van het openen of delen van een bestand.</span><span class="sxs-lookup"><span data-stu-id="76b2e-127">This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="76b2e-128">Kies **Sluiten** om de details voor een geselecteerd item te sluiten.</span><span class="sxs-lookup"><span data-stu-id="76b2e-128">Choose **Close** to close the details for a selected item.</span></span> 
  
  

