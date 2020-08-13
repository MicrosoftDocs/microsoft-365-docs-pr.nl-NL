---
title: Virusdetectie in SharePoint Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: In dit artikel leest u hoe u met SharePoint Online virussen kunt herkennen aan bestanden die gebruikers uploaden en voorkomen dat gebruikers de bestanden downloaden of synchroniseren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0e58fa8dc8b30c5bc6ff5db1508d8b7f9189b73a
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653507"
---
# <a name="virus-detection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="b95d8-103">Virus detectie in SharePoint Online, OneDrive en Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="b95d8-103">Virus detection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="b95d8-104">Microsoft 365 kan u helpen uw omgeving te beschermen tegen malware door virussen te detecteren in bestanden die gebruikers uploaden naar SharePoint Online, OneDrive en Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="b95d8-104">Microsoft 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="b95d8-105">Het kan zijn dat bestanden worden gecontroleerd op virussen nadat ze zijn geüpload.</span><span class="sxs-lookup"><span data-stu-id="b95d8-105">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="b95d8-106">Als een bestand is geïnfecteerd met infectie, wordt er een eigenschap ingesteld, zodat gebruikers het bestand niet kunnen downloaden of synchroniseren.</span><span class="sxs-lookup"><span data-stu-id="b95d8-106">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b95d8-107">Deze antivirusfuncties in SharePoint Online zijn een manier om virussen te bevatten.</span><span class="sxs-lookup"><span data-stu-id="b95d8-107">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="b95d8-108">Ze zijn niet bedoeld als één verdedigings punt tegen malware van uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="b95d8-108">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="b95d8-109">We raden u aan alle klanten te beschermen tegen antimalware-beveiliging op verschillende lagen en best practices toe te passen om uw bedrijfsinfrastructuur te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="b95d8-109">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="b95d8-110">Zie voor meer informatie over strategieën en best practices voor [beveiliging](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="b95d8-110">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="b95d8-111">Wat gebeurt er wanneer een geïnfecteerd bestand wordt geüpload naar SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="b95d8-111">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="b95d8-112">Microsoft 365 gebruikt een gangbare virusdetectie-engine.</span><span class="sxs-lookup"><span data-stu-id="b95d8-112">Microsoft 365 uses a common virus detection engine.</span></span> <span data-ttu-id="b95d8-113">De engine wordt asynchroon uitgevoerd in SharePoint Online en scant sommige bestanden nadat deze zijn geüpload.</span><span class="sxs-lookup"><span data-stu-id="b95d8-113">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="b95d8-114">Heuristiek wordt gebruikt om te bepalen welke bestanden worden gescand.</span><span class="sxs-lookup"><span data-stu-id="b95d8-114">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="b95d8-115">Wanneer een bestand een virus bevat, is dit gemarkeerd zodat het niet meer kan worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="b95d8-115">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="b95d8-116">In april 2018 is de limiet van 25 MB voor gescande bestanden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b95d8-116">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="b95d8-117">Dit is wat er gebeurt:</span><span class="sxs-lookup"><span data-stu-id="b95d8-117">Here's what happens:</span></span>

1. <span data-ttu-id="b95d8-118">Een gebruiker uploadt een bestand naar SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b95d8-118">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="b95d8-119">In SharePoint Online wordt bepaald of het bestand voldoet aan de criteria voor een scan.</span><span class="sxs-lookup"><span data-stu-id="b95d8-119">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="b95d8-120">De virusdetectie-engine scant het bestand.</span><span class="sxs-lookup"><span data-stu-id="b95d8-120">The virus detection engine scans the file.</span></span>

4. <span data-ttu-id="b95d8-121">Als er een virus wordt gevonden, stelt de virus engine een eigenschap in op het bestand om aan te geven dat het geïnfecteerd is.</span><span class="sxs-lookup"><span data-stu-id="b95d8-121">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="b95d8-122">Wat gebeurt er wanneer een gebruiker een geïnfecteerd bestand probeert te downloaden met de browser?</span><span class="sxs-lookup"><span data-stu-id="b95d8-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="b95d8-123">Als een bestand is geïnfecteerd, kunnen gebruikers het niet downloaden van SharePoint Online met behulp van de browser.</span><span class="sxs-lookup"><span data-stu-id="b95d8-123">If a file is infected, users can't download the file from SharePoint Online by using the browser.</span></span>

<span data-ttu-id="b95d8-124">Dit is wat er gebeurt:</span><span class="sxs-lookup"><span data-stu-id="b95d8-124">Here's what happens:</span></span>

1. <span data-ttu-id="b95d8-125">Een gebruiker opent een webbrowser en probeert een geïnfecteerd bestand te downloaden van SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b95d8-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>

2. <span data-ttu-id="b95d8-126">De gebruiker krijgt een waarschuwing dat er een virus is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="b95d8-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="b95d8-127">De gebruiker krijgt de mogelijkheid om het bestand te downloaden en te proberen te wissen met behulp van hun eigen antivirussoftware.</span><span class="sxs-lookup"><span data-stu-id="b95d8-127">The user is given the option to download the file and attempt to clean it using their own antivirus software.</span></span>

> [!NOTE]
>
> <span data-ttu-id="b95d8-128">U kunt de parameter *DisallowInfectedFileDownload* van de cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online PowerShell gebruiken om te voorkomen dat gebruikers een geïnfecteerd bestand downloaden, zelfs in het waarschuwingsvenster van antivirusprogramma's.</span><span class="sxs-lookup"><span data-stu-id="b95d8-128">You can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading an infected file, even in the anti-virus warning window.</span></span>
>
> <span data-ttu-id="b95d8-129">Houd er ook rekening mee dat zodra u de parameter *DisallowInfectedFileDownload* inschakelt, de toegang tot de gedetecteerde/geblokkeerde bestanden volledig wordt geblokkeerd voor gebruikers en beheerders.</span><span class="sxs-lookup"><span data-stu-id="b95d8-129">Also keep in mind, that as soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completly blocked for users and administrators.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="b95d8-130">Wat gebeurt er wanneer de OneDrive-synchronisatieclient een geïnfecteerd bestand probeert te synchroniseren?</span><span class="sxs-lookup"><span data-stu-id="b95d8-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="b95d8-131">Of gebruikers bestanden synchroniseren met de nieuwe OneDrive-synchronisatieclient (OneDrive.exe) of de vorige synchronisatieclient van OneDrive voor bedrijven (Groove.exe), als een bestand een virus bevat, kan de synchronisatieclient dit niet downloaden.</span><span class="sxs-lookup"><span data-stu-id="b95d8-131">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="b95d8-132">Met de synchronisatieclient wordt een melding weergegeven dat het bestand niet kan worden gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="b95d8-132">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-office-365-atp"></a><span data-ttu-id="b95d8-133">Uitgebreide mogelijkheden met Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="b95d8-133">Extended capabilities with Office 365 ATP</span></span>

<span data-ttu-id="b95d8-134">Voor klanten die Office 365 ATP voor SharePoint, OneDrive en Microsoft teams hebben ingeschakeld, kunt u de beschikbaarheid [voor SharePoint, onedrive en micro](turn-on-atp-for-spo-odb-and-teams.md) Soft teams gebruiken om het beveiligings & voor het beheren van gequarantinee bestanden voor AV-en ATP-detecties te beheren.</span><span class="sxs-lookup"><span data-stu-id="b95d8-134">Customers who enabled Office 365 ATP for Sharepoint, OneDrive, and Microsoft Teams [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) are able to use the Security & Compliance Center to manage quarantined files for AV and ATP detections.</span></span> <span data-ttu-id="b95d8-135">[Alleen ATP: gebruik de beveiligings & voor nalevings centrum voor het beheren van bestanden die in quarantaine zijn geplaatst](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span><span class="sxs-lookup"><span data-stu-id="b95d8-135">[ATP Only: Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="more-information"></a><span data-ttu-id="b95d8-136">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="b95d8-136">More information</span></span>

<span data-ttu-id="b95d8-137">Zie [beschermen tegen bedreigingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) en [Schakel ATP in voor SharePoint, OneDrive en Microsoft teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) voor meer informatie over het configureren van SharePoint Online-antivirusprogramma.</span><span class="sxs-lookup"><span data-stu-id="b95d8-137">See [Protect against threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) for more information on how to configure SharePoint Online antivirus.</span></span>


