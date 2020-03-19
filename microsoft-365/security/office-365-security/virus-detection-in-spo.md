---
title: Virus detection in SharePoint Online
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
description: Meer informatie over antivirusbeveiliging in SharePoint Online.
ms.openlocfilehash: f22c2a3280148eb23f4ba53ff467a533186ed791
ms.sourcegitcommit: 3d17c1d6b80672719b1878e2f321f0de39595226
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/11/2020
ms.locfileid: "42806303"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="e5781-103">Virus detection in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e5781-103">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="e5781-104">Office 365 kan uw omgeving beschermen tegen malware door virussen te detecteren in bestanden die gebruikers uploaden naar SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e5781-104">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="e5781-105">Bestanden kunnen worden gescand op virussen nadat ze zijn geüpload.</span><span class="sxs-lookup"><span data-stu-id="e5781-105">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="e5781-106">Als blijkt dat een bestand geïnfecteerd is, wordt een eigenschap zo ingesteld dat gebruikers het bestand niet kunnen downloaden of synchroniseren.</span><span class="sxs-lookup"><span data-stu-id="e5781-106">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5781-107">Deze antivirusmogelijkheden in SharePoint Online zijn een manier om virussen te bevatten.</span><span class="sxs-lookup"><span data-stu-id="e5781-107">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="e5781-108">Ze zijn niet bedoeld als een enkel punt van verdediging tegen malware voor uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="e5781-108">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="e5781-109">We moedigen alle klanten aan om antimalwarebescherming op verschillende lagen te beoordelen en te implementeren en best practices toe te passen voor het beveiligen van uw bedrijfsinfrastructuur.</span><span class="sxs-lookup"><span data-stu-id="e5781-109">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="e5781-110">Zie [Beveiligingsroadmap](security-roadmap.md)voor meer informatie over strategieën en best practices.</span><span class="sxs-lookup"><span data-stu-id="e5781-110">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="e5781-111">Wat gebeurt er als een geïnfecteerd bestand wordt geüpload naar SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="e5781-111">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="e5781-112">Office 365 maakt gebruik van een veelgebruikte virusdetectie-engine.</span><span class="sxs-lookup"><span data-stu-id="e5781-112">Office 365 uses a common virus detection engine.</span></span> <span data-ttu-id="e5781-113">De engine draait asynchroon binnen SharePoint Online en scant sommige bestanden nadat ze zijn geüpload.</span><span class="sxs-lookup"><span data-stu-id="e5781-113">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="e5781-114">Heuristiek wordt gebruikt om te bepalen welke bestanden worden gescand.</span><span class="sxs-lookup"><span data-stu-id="e5781-114">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="e5781-115">Wanneer wordt vastgesteld dat een bestand een virus bevat, wordt het gemarkeerd zodat het niet opnieuw kan worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="e5781-115">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="e5781-116">In april 2018 hebben we de limiet van 25 MB voor gescande bestanden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="e5781-116">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="e5781-117">Dit is wat er gebeurt:</span><span class="sxs-lookup"><span data-stu-id="e5781-117">Here's what happens:</span></span>

1. <span data-ttu-id="e5781-118">Een gebruiker uploadt een bestand naar SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e5781-118">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="e5781-119">SharePoint Online bepaalt of het bestand voldoet aan de criteria voor een scan.</span><span class="sxs-lookup"><span data-stu-id="e5781-119">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="e5781-120">De virusdetectie-engine scant het bestand.</span><span class="sxs-lookup"><span data-stu-id="e5781-120">The virus detection engine scans the file.</span></span>

4. <span data-ttu-id="e5781-121">Als een virus wordt gevonden, stelt de virusengine een eigenschap in op het bestand die aangeeft dat het geïnfecteerd is.</span><span class="sxs-lookup"><span data-stu-id="e5781-121">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="e5781-122">Wat gebeurt er wanneer een gebruiker een geïnfecteerd bestand probeert te downloaden met behulp van de browser?</span><span class="sxs-lookup"><span data-stu-id="e5781-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="e5781-123">Als een bestand is geïnfecteerd, kunnen gebruikers het bestand niet downloaden van SharePoint Online met behulp van de browser.</span><span class="sxs-lookup"><span data-stu-id="e5781-123">If a file is infected, users can't download the file from SharePoint Online by using the browser.</span></span>

<span data-ttu-id="e5781-124">Dit is wat er gebeurt:</span><span class="sxs-lookup"><span data-stu-id="e5781-124">Here's what happens:</span></span>

1. <span data-ttu-id="e5781-125">Een gebruiker opent een webbrowser en probeert een geïnfecteerd bestand van SharePoint Online te downloaden.</span><span class="sxs-lookup"><span data-stu-id="e5781-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>

2. <span data-ttu-id="e5781-126">De gebruiker krijgt een waarschuwing dat een virus is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="e5781-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="e5781-127">De gebruiker krijgt de mogelijkheid om het bestand te downloaden en te proberen om het schoon te maken met behulp van hun eigen antivirus software.</span><span class="sxs-lookup"><span data-stu-id="e5781-127">The user is given the option to download the file and attempt to clean it using their own antivirus software.</span></span>

> [!NOTE]
> <span data-ttu-id="e5781-128">U de parameter *DisallowInfectedFileDownload* gebruiken op de cmdlet [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online PowerShell om te voorkomen dat gebruikers een geïnfecteerd bestand downloaden, zelfs in het waarschuwingsvenster voor virussen.</span><span class="sxs-lookup"><span data-stu-id="e5781-128">You can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading an infected file, even in the anti-virus warning window.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="e5781-129">Wat gebeurt er als de synchronisatieclient van OneDrive een geïnfecteerd bestand probeert te synchroniseren?</span><span class="sxs-lookup"><span data-stu-id="e5781-129">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="e5781-130">Of gebruikers bestanden synchroniseren met de nieuwe OneDrive-synchronisatieclient (OneDrive.exe) of de vorige synchronisatieclient van OneDrive voor Bedrijven (Groove.exe), als een bestand een virus bevat, wordt de synchronisatieclient niet gedownload.</span><span class="sxs-lookup"><span data-stu-id="e5781-130">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="e5781-131">De synchronisatieclient geeft een melding weer dat het bestand niet kan worden gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="e5781-131">The sync client will display a notification that the file can't be synced.</span></span>
