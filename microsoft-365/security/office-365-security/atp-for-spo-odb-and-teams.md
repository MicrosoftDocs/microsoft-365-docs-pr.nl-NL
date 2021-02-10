---
title: Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
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
description: Meer informatie over Microsoft Defender voor Office 365 voor bestanden in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 640867cb38dab650bca990fe36c0b7cea7f6a0d8
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175725"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="bada0-103">Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bada0-103">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bada0-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="bada0-104">**Applies to**</span></span>
- [<span data-ttu-id="bada0-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="bada0-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="bada0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bada0-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="bada0-107">Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams in Microsoft Defender voor [Office 365](office-365-atp.md) bieden een extra beveiligingslaag voor bestanden die al tijdens het uploaden zijn gescand met de algemene [virusdetectie-engine in Microsoft 365.](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="bada0-107">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](office-365-atp.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="bada0-108">Met veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams kunt u bestaande bestanden opsporen en blokkeren die in teamsites en documentbibliotheken als schadelijk zijn aangemerkt.</span><span class="sxs-lookup"><span data-stu-id="bada0-108">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="bada0-109">Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams zijn standaard niet ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="bada0-109">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="bada0-110">Zie Veilige bijlagen in schakel je in voor [SharePoint, OneDrive en Microsoft Teams.](turn-on-atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="bada0-110">To turn it on, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="bada0-111">Hoe veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams werken</span><span class="sxs-lookup"><span data-stu-id="bada0-111">How Safe Attachments for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="bada0-112">Als veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams zijn ingeschakeld en een bestand als schadelijk wordt geïdentificeerd, wordt het bestand vergrendeld met rechtstreekse integratie met de bestandsopslag.</span><span class="sxs-lookup"><span data-stu-id="bada0-112">When Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="bada0-113">In de volgende afbeelding ziet u een voorbeeld van een schadelijk bestand dat in een bibliotheek is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="bada0-113">The following image shows an example of a malicious file detected in a library.</span></span>

![Bestanden in OneDrive voor Bedrijven met een gedetecteerd als schadelijk](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="bada0-115">Hoewel het geblokkeerde bestand nog steeds wordt vermeld in de documentbibliotheek en in web-, mobiele of bureaubladtoepassingen, kunnen personen het bestand niet openen, kopiëren, verplaatsen of delen.</span><span class="sxs-lookup"><span data-stu-id="bada0-115">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="bada0-116">Maar ze kunnen het geblokkeerde bestand verwijderen.</span><span class="sxs-lookup"><span data-stu-id="bada0-116">But they can delete the blocked file.</span></span>

<span data-ttu-id="bada0-117">Hier ziet u een voorbeeld van hoe een geblokkeerd bestand eruitziet op een mobiel apparaat:</span><span class="sxs-lookup"><span data-stu-id="bada0-117">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![Een geblokkeerd bestand verwijderen uit OneDrive voor Bedrijven vanuit de mobiele OneDrive-app](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="bada0-119">Standaard kunnen mensen een geblokkeerd bestand downloaden.</span><span class="sxs-lookup"><span data-stu-id="bada0-119">By default, people can download a blocked file.</span></span> <span data-ttu-id="bada0-120">Zo ziet het downloaden van een geblokkeerd bestand er op een mobiel apparaat uit:</span><span class="sxs-lookup"><span data-stu-id="bada0-120">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![Een geblokkeerd bestand downloaden in OneDrive voor Bedrijven](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="bada0-122">SharePoint Online-beheerders kunnen voorkomen dat personen schadelijke bestanden downloaden.</span><span class="sxs-lookup"><span data-stu-id="bada0-122">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="bada0-123">Zie [SharePoint Online PowerShell gebruiken om te](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)voorkomen dat gebruikers schadelijke bestanden downloaden.</span><span class="sxs-lookup"><span data-stu-id="bada0-123">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="bada0-124">Als u meer wilt weten over de gebruikerservaring wanneer een bestand als schadelijk is gedetecteerd, bekijkt u Wat u moet doen als er een schadelijk bestand wordt gevonden [in SharePoint Online, OneDrive of Microsoft Teams.](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="bada0-124">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="bada0-125">Informatie weergeven over schadelijke bestanden die worden gedetecteerd door veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bada0-125">View information about malicious files detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="bada0-126">Bestanden die worden geïdentificeerd als schadelijk door Microsoft Defender voor Office 365, worden weergegeven in rapporten voor Microsoft Defender voor [Office 365](view-reports-for-atp.md) en in [Verkenner (en realtime detecties).](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="bada0-126">Files that are identified as malicious by Microsoft Defender for Office 365 will show up in [reports for Microsoft Defender for Office 365](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="bada0-127">Vanaf mei 2018, wanneer een bestand wordt geïdentificeerd als schadelijk door Microsoft Defender voor Office 365, is het bestand ook in quarantaine beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="bada0-127">As of May 2018, when a file is identified as malicious by Microsoft Defender for Office 365, the file is also available in quarantine.</span></span> <span data-ttu-id="bada0-128">Zie het beveiligingscentrum voor & voor meer informatie [over het beheren van bestanden in quarantaine.](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)</span><span class="sxs-lookup"><span data-stu-id="bada0-128">For more information, see [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="bada0-129">Houd rekening met deze punten</span><span class="sxs-lookup"><span data-stu-id="bada0-129">Keep these points in mind</span></span>

- <span data-ttu-id="bada0-130">Defender voor Office 365 scant niet elk bestand in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bada0-130">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="bada0-131">Dit is inherent aan het ontwerp van het product.</span><span class="sxs-lookup"><span data-stu-id="bada0-131">This is by design.</span></span> <span data-ttu-id="bada0-132">Bestanden worden asynchroon gescand.</span><span class="sxs-lookup"><span data-stu-id="bada0-132">Files are scanned asynchronously.</span></span> <span data-ttu-id="bada0-133">Het proces maakt gebruik van gebeurtenissen voor delen en gastactiviteiten, samen met slimme heuristics- en bedreigingssignalen om schadelijke bestanden te identificeren.</span><span class="sxs-lookup"><span data-stu-id="bada0-133">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="bada0-134">Zorg ervoor dat uw SharePoint-sites zijn geconfigureerd voor gebruik met de [moderne ervaring.](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)</span><span class="sxs-lookup"><span data-stu-id="bada0-134">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="bada0-135">De beveiliging van Defender voor Office 365 is van toepassing, ongeacht of de moderne of klassieke weergave wordt gebruikt. Visuele indicatoren die echter zeggen dat een bestand is geblokkeerd, zijn alleen beschikbaar in de moderne ervaring.</span><span class="sxs-lookup"><span data-stu-id="bada0-135">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="bada0-136">Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams maken deel uit van de algemene strategie voor risicobeveiliging van uw organisatie, waaronder bescherming tegen ongewenste e-mail en malware in Exchange Online Protection (EOP), evenals veilige koppelingen en veilige bijlagen in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="bada0-136">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="bada0-137">Zie Beveiligen tegen bedreigingen [in Office 365 voor meer informatie.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="bada0-137">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
