---
title: ATP voor SharePoint, OneDrive en Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Meer informatie over Office 365 Advanced Threat Protection voor bestanden in SharePoint Online, OneDrive voor bedrijven en Microsoft teams.
ms.openlocfilehash: e536809c74abbe87e1250acda3f3922180cfae97
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446261"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="3e672-103">ATP voor SharePoint, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3e672-103">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3e672-104">ATP voor SharePoint, OneDrive en Microsoft teams in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) biedt een extra beveiligingslaag voor bestanden die al zijn gecontroleerd op het moment dat ze worden geüpload via de [algemene virusdetectie-engine in Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="3e672-104">ATP for SharePoint, OneDrive, and Microsoft Teams in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="3e672-105">Met ATP voor SharePoint, OneDrive en Microsoft teams kunt u bestaande bestanden die zijn geïdentificeerd als schadelijk op team sites en documentbibliotheken detecteren en blokkeren.</span><span class="sxs-lookup"><span data-stu-id="3e672-105">ATP for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="3e672-106">ATP voor SharePoint, OneDrive en Microsoft teams is standaard niet ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="3e672-106">ATP for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="3e672-107">Als u dit wilt inschakelen, raadpleegt u [ATP voor SharePoint, OneDrive en Microsoft teams inschakelen](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="3e672-107">To turn it on, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="3e672-108">De werking van ATP voor SharePoint, OneDrive en Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="3e672-108">How ATP for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="3e672-109">Wanneer ATP voor SharePoint, OneDrive en Microsoft teams is ingeschakeld en een bestand als schadelijk wordt geïdentificeerd, wordt het bestand vergrendeld via rechtstreekse integratie met de bestandsarchieven.</span><span class="sxs-lookup"><span data-stu-id="3e672-109">When ATP for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="3e672-110">In de volgende afbeelding ziet u een voorbeeld van een schadelijk bestand dat is gevonden in een bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="3e672-110">The following image shows an example of a malicious file detected in a library.</span></span>

![Bestanden in OneDrive voor bedrijven met een gedetecteerde schadelijke versie](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="3e672-112">Hoewel het geblokkeerde bestand nog steeds wordt weergegeven in de documentbibliotheek en in Internet-, mobiele en bureaubladtoepassingen, kunnen personen het bestand niet openen, kopiëren, verplaatsen of delen.</span><span class="sxs-lookup"><span data-stu-id="3e672-112">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="3e672-113">Maar ze kunnen het geblokkeerde bestand wel verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3e672-113">But they can delete the blocked file.</span></span>

<span data-ttu-id="3e672-114">Hier ziet u een voorbeeld van hoe een geblokkeerd bestand eruit ziet op een mobiel apparaat:</span><span class="sxs-lookup"><span data-stu-id="3e672-114">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![Een geblokkeerd bestand verwijderen uit OneDrive voor bedrijven uit de mobiele OneDrive-app](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="3e672-116">Standaard kunnen personen een geblokkeerd bestand downloaden.</span><span class="sxs-lookup"><span data-stu-id="3e672-116">By default, people can download a blocked file.</span></span> <span data-ttu-id="3e672-117">Het downloaden van een geblokkeerd bestand ziet er als volgt uit op een mobiel apparaat:</span><span class="sxs-lookup"><span data-stu-id="3e672-117">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![Een geblokkeerd bestand downloaden in OneDrive voor bedrijven](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="3e672-119">SharePoint Online-beheerders kunnen voorkomen dat mensen schadelijke bestanden downloaden.</span><span class="sxs-lookup"><span data-stu-id="3e672-119">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="3e672-120">Zie [SharePoint Online PowerShell gebruiken om te voorkomen dat gebruikers schadelijke bestanden downloaden](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="3e672-120">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="3e672-121">Zie [wat u moet doen als er een schadelijk bestand wordt gevonden in SharePoint Online, OneDrive of Microsoft teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)voor meer informatie over de gebruikerservaring wanneer een bestand als schadelijk is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="3e672-121">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="3e672-122">Informatie weergeven over schadelijke bestanden die zijn gedetecteerd door ATP voor SharePoint, OneDrive en Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="3e672-122">View information about malicious files detected by ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="3e672-123">Bestanden die worden geïdentificeerd als schadelijk voor ATP, worden weergegeven in [rapporten voor Office 365 Advanced Threat Protection](view-reports-for-atp.md) en in [Explorer (en realtime-detectie)](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="3e672-123">Files that are identified as malicious by ATP will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="3e672-124">Vanaf mei 2018 wordt het bestand ook in quarantaine geplaatst wanneer een bestand wordt geïdentificeerd als schadelijk voor ATP.</span><span class="sxs-lookup"><span data-stu-id="3e672-124">As of May 2018, when a file is identified as malicious by ATP, the file is also available in quarantine.</span></span> <span data-ttu-id="3e672-125">Zie voor meer informatie het artikel over [beveiligings & voor nalevings centrum voor het beheren van gequarantinee bestanden](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span><span class="sxs-lookup"><span data-stu-id="3e672-125">For more information, see [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="3e672-126">Let op de volgende punten</span><span class="sxs-lookup"><span data-stu-id="3e672-126">Keep these points in mind</span></span>

- <span data-ttu-id="3e672-127">Met ATP kunt u niet elk afzonderlijk bestand in SharePoint Online, OneDrive voor bedrijven of Microsoft teams scannen.</span><span class="sxs-lookup"><span data-stu-id="3e672-127">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="3e672-128">Dit is inherent aan het ontwerp van het product.</span><span class="sxs-lookup"><span data-stu-id="3e672-128">This is by design.</span></span> <span data-ttu-id="3e672-129">Bestanden worden asynchroon gescand.</span><span class="sxs-lookup"><span data-stu-id="3e672-129">Files are scanned asynchronously.</span></span> <span data-ttu-id="3e672-130">Met de functie voor het delen van gebeurtenissen en gebeurtenissen in een gast activiteit worden kwaadwillende bestanden aangegeven met behulp van slimme heuristisch en bedreigings signalen.</span><span class="sxs-lookup"><span data-stu-id="3e672-130">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="3e672-131">Zorg ervoor dat de SharePoint-sites zijn geconfigureerd voor gebruik van de [moderne ervaring](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span><span class="sxs-lookup"><span data-stu-id="3e672-131">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="3e672-132">ATP-beveiliging is van toepassing op de meest recente ervaring of de klassieke weergave. de visuele indicatoren die een bestand blokkeert, zijn echter alleen beschikbaar in de moderne ervaring.</span><span class="sxs-lookup"><span data-stu-id="3e672-132">ATP protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="3e672-133">ATP voor SharePoint, OneDrive en Microsoft teams maakt deel uit van de algemene strategie voor risico beveiliging van uw organisatie, waaronder antispam en bescherming tegen malware in Exchange Online Protection (EOP), en veilige koppelingen en veilige bijlagen in Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="3e672-133">ATP for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Office 365 ATP.</span></span> <span data-ttu-id="3e672-134">Voor meer informatie raadpleegt u [bescherming tegen bedreigingen in Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="3e672-134">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
