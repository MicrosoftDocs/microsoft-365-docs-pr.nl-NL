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
description: Meer informatie over Microsoft Defender Office 365 voor bestanden in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7aa375020ce05ca1d484bb7ed18b8cf7a6e7d04e
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/15/2021
ms.locfileid: "52932840"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="d5663-103">Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d5663-103">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d5663-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="d5663-104">**Applies to**</span></span>
- [<span data-ttu-id="d5663-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="d5663-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d5663-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5663-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="d5663-107">Safe Bijlagen voor SharePoint, OneDrive en Microsoft Teams in [Microsoft Defender](whats-new-in-defender-for-office-365.md) voor Office 365 bieden een extra beveiligingslaag voor bestanden die al zijn gescand tijdens het uploaden door de algemene [virusdetectie-engine in Microsoft 365.](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="d5663-107">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="d5663-108">Safe Bijlagen voor SharePoint, OneDrive en Microsoft Teams helpt bij het opsporen en blokkeren van bestaande bestanden die zijn geïdentificeerd als schadelijk in teamsites en documentbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="d5663-108">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="d5663-109">Safe Bijlagen voor SharePoint, OneDrive en Microsoft Teams is standaard niet ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d5663-109">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="d5663-110">Zie Safe Bijlagen in SharePoint, OneDrive en [Microsoft Teams.](turn-on-mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="d5663-110">To turn it on, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="d5663-111">Hoe Safe bijlagen voor SharePoint, OneDrive en Microsoft Teams werken</span><span class="sxs-lookup"><span data-stu-id="d5663-111">How Safe Attachments for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="d5663-112">Wanneer Safe bijlagen voor SharePoint, OneDrive en Microsoft Teams is ingeschakeld en een bestand als schadelijk wordt geïdentificeerd, wordt het bestand vergrendeld met behulp van directe integratie met de bestandsopslag.</span><span class="sxs-lookup"><span data-stu-id="d5663-112">When Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="d5663-113">In de volgende afbeelding ziet u een voorbeeld van een schadelijk bestand dat is gedetecteerd in een bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="d5663-113">The following image shows an example of a malicious file detected in a library.</span></span>

![Bestanden in OneDrive voor Bedrijven met een gedetecteerd als schadelijk](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="d5663-115">Hoewel het geblokkeerde bestand nog steeds wordt weergegeven in de documentbibliotheek en in web-, mobiele of desktoptoepassingen, kunnen personen het bestand niet openen, kopiëren, verplaatsen of delen.</span><span class="sxs-lookup"><span data-stu-id="d5663-115">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="d5663-116">Maar ze kunnen het geblokkeerde bestand verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d5663-116">But they can delete the blocked file.</span></span>

<span data-ttu-id="d5663-117">Hier ziet u een voorbeeld van hoe een geblokkeerd bestand eruitziet op een mobiel apparaat:</span><span class="sxs-lookup"><span data-stu-id="d5663-117">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![Een geblokkeerd bestand verwijderen uit OneDrive voor Bedrijven mobiele OneDrive app](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="d5663-119">Standaard kunnen personen een geblokkeerd bestand downloaden.</span><span class="sxs-lookup"><span data-stu-id="d5663-119">By default, people can download a blocked file.</span></span> <span data-ttu-id="d5663-120">Zo ziet het downloaden van een geblokkeerd bestand eruit op een mobiel apparaat:</span><span class="sxs-lookup"><span data-stu-id="d5663-120">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![Een geblokkeerd bestand downloaden in OneDrive voor Bedrijven](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="d5663-122">SharePoint Onlinebeheerders kunnen voorkomen dat personen schadelijke bestanden downloaden.</span><span class="sxs-lookup"><span data-stu-id="d5663-122">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="d5663-123">Zie Gebruik SharePoint [Online PowerShell](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)om te voorkomen dat gebruikers schadelijke bestanden downloaden voor instructies.</span><span class="sxs-lookup"><span data-stu-id="d5663-123">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="d5663-124">Zie Wat u moet doen wanneer een schadelijk bestand wordt gevonden [in SharePoint Online, OneDrive](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)of Microsoft Teams voor meer informatie over de gebruikerservaring wanneer een bestand is gedetecteerd als schadelijk.</span><span class="sxs-lookup"><span data-stu-id="d5663-124">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="d5663-125">Informatie weergeven over schadelijke bestanden die zijn gedetecteerd door Safe Bijlagen voor SharePoint, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d5663-125">View information about malicious files detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="d5663-126">Bestanden die zijn geïdentificeerd als schadelijk door Safe Bijlagen voor SharePoint, OneDrive en Microsoft Teams worden weergegeven in rapporten voor [Microsoft Defender](view-reports-for-mdo.md) voor Office 365 en in [Explorer (en realtime detecties)](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="d5663-126">Files that are identified as malicious by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams will show up in [reports for Microsoft Defender for Office 365](view-reports-for-mdo.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="d5663-127">Vanaf mei 2018, wanneer een bestand wordt geïdentificeerd als schadelijk door Safe Bijlagen voor SharePoint, OneDrive en Microsoft Teams, is het bestand ook beschikbaar in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="d5663-127">As of May 2018, when a file is identified as malicious by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, the file is also available in quarantine.</span></span> <span data-ttu-id="d5663-128">Zie In Quarantaine geplaatste bestanden beheren in Defender voor [Office 365.](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="d5663-128">For more information, see [Manage quarantined files in Defender for Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="d5663-129">Houd rekening met deze punten</span><span class="sxs-lookup"><span data-stu-id="d5663-129">Keep these points in mind</span></span>

- <span data-ttu-id="d5663-130">Defender voor Office 365 scant niet elk bestand in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d5663-130">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="d5663-131">Dit is inherent aan het ontwerp van het product.</span><span class="sxs-lookup"><span data-stu-id="d5663-131">This is by design.</span></span> <span data-ttu-id="d5663-132">Bestanden worden asynchroon gescand.</span><span class="sxs-lookup"><span data-stu-id="d5663-132">Files are scanned asynchronously.</span></span> <span data-ttu-id="d5663-133">In het proces worden gebeurtenissen voor delen en gastactiviteit gebruikt, samen met slimme heuristische en bedreigingssignalen om schadelijke bestanden te identificeren.</span><span class="sxs-lookup"><span data-stu-id="d5663-133">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="d5663-134">Zorg ervoor dat SharePoint sites zijn geconfigureerd voor gebruik van [de moderne ervaring.](/sharepoint/guide-to-sharepoint-modern-experience)</span><span class="sxs-lookup"><span data-stu-id="d5663-134">Make sure your SharePoint sites are configured to use the [Modern experience](/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="d5663-135">Defender for Office 365 protection is van toepassing of de moderne ervaring of de klassieke weergave wordt gebruikt. Visuele indicatoren dat een bestand is geblokkeerd, zijn echter alleen beschikbaar in de moderne ervaring.</span><span class="sxs-lookup"><span data-stu-id="d5663-135">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="d5663-136">Safe Bijlagen voor SharePoint, OneDrive en Microsoft Teams maken deel uit van de algemene strategie voor bedreigingsbeveiliging van uw organisatie, waaronder antispam- en anti-malwarebeveiliging in Exchange Online Protection (EOP), evenals Safe Koppelingen en Safe Bijlagen in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="d5663-136">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="d5663-137">Zie Beschermen tegen bedreigingen [in](protect-against-threats.md)Office 365.</span><span class="sxs-lookup"><span data-stu-id="d5663-137">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
