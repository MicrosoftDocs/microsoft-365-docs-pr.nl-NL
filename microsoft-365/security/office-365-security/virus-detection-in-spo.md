---
title: Ingebouwde virusbeveiliging in SharePoint Online, OneDrive en Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Meer informatie over hoe SharePoint online virussen detecteert in bestanden die gebruikers uploaden en voorkomt dat gebruikers de bestanden downloaden of synchroniseren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dd38b196c106a36fb1a1bfc0a441620b1c5b8ba5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204158"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="d7c0e-103">Ingebouwde virusbeveiliging in SharePoint Online, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d7c0e-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d7c0e-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="d7c0e-104">**Applies to**</span></span>
- [<span data-ttu-id="d7c0e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d7c0e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d7c0e-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="d7c0e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="d7c0e-107">Microsoft 365 maakt gebruik van een veelgebruikte virusdetectieprogramma voor het scannen van bestanden die gebruikers uploaden naar SharePoint Online, OneDrive en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-107">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="d7c0e-108">Deze beveiliging is inbegrepen bij alle abonnementen die SharePoint Online, OneDrive en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-108">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d7c0e-109">De ingebouwde anti-virusmogelijkheden zijn een manier om virussen te helpen bevatten.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-109">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="d7c0e-110">Ze zijn niet bedoeld als één verdedigingspunt tegen malware voor uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="d7c0e-111">We raden alle klanten aan om anti-malwarebeveiliging op verschillende lagen te onderzoeken en te implementeren en best practices toe te passen voor het beveiligen van hun bedrijfsinfrastructuur.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-111">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="d7c0e-112">Zie Routekaart voor beveiliging voor meer informatie over strategieën [en](security-roadmap.md)best practices.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="d7c0e-113">Wat gebeurt er als een geïnfecteerd bestand wordt geüpload naar SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="d7c0e-113">What happens if an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="d7c0e-114">De Microsoft 365 virusdetectieprogramma wordt asynchroon uitgevoerd (onafhankelijk van bestands uploads) binnen SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-114">The Microsoft 365 virus detection engine runs asynchronously (independent from file uploads) within SharePoint Online.</span></span> <span data-ttu-id="d7c0e-115">**Alle bestanden worden niet automatisch gescand.**</span><span class="sxs-lookup"><span data-stu-id="d7c0e-115">**All files are not automatically scanned**.</span></span> <span data-ttu-id="d7c0e-116">Heuristische gegevens bepalen de bestanden die moeten worden gescand.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-116">Heuristics determine the files to scan.</span></span> <span data-ttu-id="d7c0e-117">Wanneer een bestand een virus bevat, wordt het bestand gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-117">When a file is found to contain a virus, the file is flagged.</span></span> <span data-ttu-id="d7c0e-118">In april 2018 hebben we de limiet van 25 MB voor gescande bestanden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="d7c0e-119">Dit is wat er gebeurt:</span><span class="sxs-lookup"><span data-stu-id="d7c0e-119">Here's what happens:</span></span>

1. <span data-ttu-id="d7c0e-120">Een gebruiker uploadt een bestand naar SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-120">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="d7c0e-121">SharePoint Online, als onderdeel van de virusscanprocessen, bepaalt u later of het bestand voldoet aan de criteria voor een scan.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-121">SharePoint Online, as part of its virus scanning processes, later determines if the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="d7c0e-122">Als het bestand voldoet aan de criteria voor een scan, scant de virusdetectie-engine het bestand.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-122">If the file meets the criteria for a scan, the virus detection engine scans the file.</span></span>
4. <span data-ttu-id="d7c0e-123">Als er een virus wordt gevonden in het gescande bestand, stelt de virusprogramma een eigenschap in op het bestand waarmee wordt aangegeven dat het is geïnfecteerd.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-123">If a virus is found within the scanned file, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="d7c0e-124">Wat gebeurt er wanneer een gebruiker een geïnfecteerd bestand probeert te downloaden met behulp van de browser?</span><span class="sxs-lookup"><span data-stu-id="d7c0e-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="d7c0e-125">Als een bestand is geïnfecteerd, kunnen gebruikers het bestand niet downloaden van SharePoint Online met behulp van een browser.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-125">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="d7c0e-126">Dit is wat er gebeurt:</span><span class="sxs-lookup"><span data-stu-id="d7c0e-126">Here's what happens:</span></span>

1. <span data-ttu-id="d7c0e-127">Een gebruiker opent een webbrowser en probeert een geïnfecteerd bestand te downloaden van SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="d7c0e-128">De gebruiker krijgt een waarschuwing dat er een virus is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="d7c0e-129">Standaard krijgt de gebruiker de optie om het bestand te downloaden en te proberen het op te schonen met de antivirussoftware op zijn eigen apparaat.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-129">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="d7c0e-130">Beheerders kunnen de parameter *DisallowInfectedFileDownload* gebruiken op de cmdlet [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online PowerShell om te voorkomen dat gebruikers geïnfecteerde bestanden downloaden, zelfs in het waarschuwingsvenster voor virussen.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-130">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="d7c0e-131">Zie Gebruik SharePoint [Online PowerShell](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)om te voorkomen dat gebruikers schadelijke bestanden downloaden voor instructies.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-131">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="d7c0e-132">Zodra u de parameter *DisallowInfectedFileDownload* inschakelen, wordt de toegang tot de gedetecteerde/geblokkeerde bestanden volledig geblokkeerd voor gebruikers en beheerders.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-132">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="d7c0e-133">Wat gebeurt er wanneer de OneDrive synchronisatieclient een geïnfecteerd bestand probeert te synchroniseren?</span><span class="sxs-lookup"><span data-stu-id="d7c0e-133">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="d7c0e-134">OneDrive synchronisatiecl clients worden geen bestanden gedownload die virussen bevatten.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-134">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="d7c0e-135">De synchronisatieclient geeft een melding weer dat het bestand niet kan worden gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-135">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a><span data-ttu-id="d7c0e-136">Uitgebreide mogelijkheden met Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="d7c0e-136">Extended capabilities with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="d7c0e-137">Microsoft 365 organisaties die Microsoft [Defender](defender-for-office-365.md) voor Office 365 hebben opgenomen in hun abonnement of die zijn gekocht als invoegabonnement, kunnen Safe Bijlagen voor SharePoint, OneDrive en Microsoft Teams inschakelen voor verbeterde rapportage en beveiliging.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-137">Microsoft 365 organizations that have [Microsoft Defender for Office 365](defender-for-office-365.md) included in their subscription or purchased as an add-on can enable Safe Attachments for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="d7c0e-138">Zie Bijlagen voor Safe bijlagen voor [SharePoint, OneDrive en Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="d7c0e-138">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="d7c0e-139">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="d7c0e-139">Related Articles</span></span>

[<span data-ttu-id="d7c0e-140">Beveiliging tegen malware en ransomware in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d7c0e-140">Malware and ransomware protection in Microsoft 365</span></span>](/compliance/assurance/assurance-malware-and-ransomware-protection)

<span data-ttu-id="d7c0e-141">Zie Beschermen tegen bedreigingen en [Safe-bijlagen](turn-on-mdo-for-spo-odb-and-teams.md)in SharePoint, OneDrive en Microsoft Teams [](protect-against-threats.md) voor meer informatie over antivirusprogramma's in SharePoint SharePoint Online, OneDrive en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d7c0e-141">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>
