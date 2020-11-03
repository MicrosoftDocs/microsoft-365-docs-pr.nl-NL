---
title: Ingebouwde antivirusbeveiliging in SharePoint Online, OneDrive en Microsoft teams
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
ms.openlocfilehash: f774c9afd0988c504d6207b0e71ee9561312e6b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844234"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="c5fbf-103">Ingebouwde antivirusbeveiliging in SharePoint Online, OneDrive en Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="c5fbf-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c5fbf-104">Microsoft 365 gebruikt een gangbare virusdetectie-engine voor het scannen van bestanden die gebruikers uploaden naar SharePoint Online, OneDrive en Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-104">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="c5fbf-105">Deze bescherming is inbegrepen in alle abonnementen, waaronder SharePoint Online, OneDrive en Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-105">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5fbf-106">De ingebouwde anti-virus functies vormen een manier om virussen te kunnen bevatten.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-106">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="c5fbf-107">Ze zijn niet bedoeld als één verdedigings punt tegen malware van uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-107">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="c5fbf-108">We raden u aan alle klanten te beschermen tegen beveiliging tegen malware tegen verschillende lagen en best practices op te zetten voor de beveiliging van hun bedrijfsinfrastructuur.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-108">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="c5fbf-109">Zie voor meer informatie over strategieën en best practices voor [beveiliging](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="c5fbf-109">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="c5fbf-110">Wat gebeurt er wanneer een geïnfecteerd bestand wordt geüpload naar SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="c5fbf-110">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="c5fbf-111">De Microsoft 365-virusdetectie-engine wordt asynchroon uitgevoerd in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-111">The Microsoft 365 virus detection engine runs asynchronously within SharePoint Online.</span></span> <span data-ttu-id="c5fbf-112">**Alle bestanden worden niet automatisch gescand tijdens het uploaden**.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-112">**All files are not automatically scanned on upload**.</span></span> <span data-ttu-id="c5fbf-113">Heuristiek bepaalt welke bestanden moeten worden gescand.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-113">Heuristics determine the files to scan.</span></span> <span data-ttu-id="c5fbf-114">Wanneer een bestand een virus bevat, wordt het bestand gemarkeerd zodat het niet opnieuw kan worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-114">When a file is found to contain a virus, the file is flagged so it can't be downloaded again.</span></span> <span data-ttu-id="c5fbf-115">In april 2018 is de limiet van 25 MB voor gescande bestanden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-115">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="c5fbf-116">Dit is wat er gebeurt:</span><span class="sxs-lookup"><span data-stu-id="c5fbf-116">Here's what happens:</span></span>

1. <span data-ttu-id="c5fbf-117">Een gebruiker uploadt een bestand naar SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-117">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="c5fbf-118">In SharePoint Online wordt bepaald of het bestand voldoet aan de criteria voor een scan.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-118">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="c5fbf-119">De virusdetectie-engine scant het bestand.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-119">The virus detection engine scans the file.</span></span>
4. <span data-ttu-id="c5fbf-120">Als er een virus wordt gevonden, stelt de virus engine een eigenschap in op het bestand om aan te geven dat het geïnfecteerd is.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-120">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="c5fbf-121">Wat gebeurt er wanneer een gebruiker een geïnfecteerd bestand probeert te downloaden met de browser?</span><span class="sxs-lookup"><span data-stu-id="c5fbf-121">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="c5fbf-122">Als een bestand is geïnfecteerd, kunnen gebruikers het niet downloaden van SharePoint Online met behulp van een browser.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-122">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="c5fbf-123">Dit is wat er gebeurt:</span><span class="sxs-lookup"><span data-stu-id="c5fbf-123">Here's what happens:</span></span>

1. <span data-ttu-id="c5fbf-124">Een gebruiker opent een webbrowser en probeert een geïnfecteerd bestand te downloaden van SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-124">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="c5fbf-125">De gebruiker krijgt een waarschuwing dat er een virus is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-125">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="c5fbf-126">Standaard krijgt de gebruiker de mogelijkheid om het bestand te downloaden en proberen het te wissen met de antivirussoftware op hun eigen apparaat.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-126">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="c5fbf-127">Beheerders kunnen de parameter *DisallowInfectedFileDownload* van de cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) van SharePoint Online PowerShell gebruiken om te voorkomen dat gebruikers geïnfecteerde bestanden downloaden, ook in het waarschuwingsvenster van antivirusprogramma's.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-127">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="c5fbf-128">Zie [SharePoint Online PowerShell gebruiken om te voorkomen dat gebruikers schadelijke bestanden downloaden](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-128">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="c5fbf-129">Zodra u de parameter *DisallowInfectedFileDownload* inschakelt, wordt de toegang tot de gedetecteerde/geblokkeerde bestanden volledig geblokkeerd voor gebruikers en beheerders.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-129">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="c5fbf-130">Wat gebeurt er wanneer de OneDrive-synchronisatieclient een geïnfecteerd bestand probeert te synchroniseren?</span><span class="sxs-lookup"><span data-stu-id="c5fbf-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="c5fbf-131">OneDrive-synchronisatieclient downloaden geen bestanden die virussen bevatten.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-131">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="c5fbf-132">Met de synchronisatieclient wordt een melding weergegeven dat het bestand niet kan worden gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-132">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a><span data-ttu-id="c5fbf-133">Uitgebreide mogelijkheden met Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="c5fbf-133">Extended capabilities with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="c5fbf-134">Microsoft 365-organisaties waarop [Microsoft Defender for Office 365](office-365-atp.md) in hun abonnement is opgenomen of als een invoegtoepassing zijn gekocht, kunnen ATP voor SharePoint, OneDrive en Microsoft teams gebruiken voor uitgebreide rapportage en bescherming.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-134">Microsoft 365 organizations that have [Microsoft Defender for Office 365](office-365-atp.md) included in their subscription or purchased as an add-on can enable ATP for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="c5fbf-135">Zie [ATP voor SharePoint, OneDrive en Microsoft teams](atp-for-spo-odb-and-teams.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c5fbf-135">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

## <a name="more-information"></a><span data-ttu-id="c5fbf-136">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="c5fbf-136">More information</span></span>

<span data-ttu-id="c5fbf-137">Zie voor meer informatie over anti-virus in SharePoint Online, OneDrive en Microsoft teams voor meer informatie over [bedreigingen](protect-against-threats.md) [voor SharePoint, Onedrive en Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="c5fbf-137">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
