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
description: Lees hoe in SharePoint Online virussen worden gedetecteerd in bestanden die gebruikers uploaden en waardoor gebruikers de bestanden niet kunnen downloaden of synchroniseren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0eafb9e5e2f0c9d86791fe83931276e420afcd9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286499"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="e8b72-103">Ingebouwde virusbeveiliging in SharePoint Online, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e8b72-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e8b72-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="e8b72-104">**Applies to**</span></span>
- [<span data-ttu-id="e8b72-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e8b72-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e8b72-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="e8b72-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)

<span data-ttu-id="e8b72-107">Microsoft 365 gebruikt een veelgebruikte engine voor virusdetectie voor het scannen van bestanden die gebruikers uploaden naar SharePoint Online, OneDrive en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e8b72-107">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="e8b72-108">Deze beveiliging is inbegrepen bij alle abonnementen met SharePoint Online, OneDrive en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e8b72-108">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8b72-109">De ingebouwde antivirusmogelijkheden zijn een manier om virussen tegen te gaan.</span><span class="sxs-lookup"><span data-stu-id="e8b72-109">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="e8b72-110">Ze zijn niet bedoeld als bescherming tegen malware in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="e8b72-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="e8b72-111">We raden alle klanten aan om de beveiliging tegen malware op verschillende lagen te onderzoeken en te implementeren en best practices toe te passen voor het beveiligen van de bedrijfsinfrastructuur.</span><span class="sxs-lookup"><span data-stu-id="e8b72-111">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="e8b72-112">Zie de roadmap voor beveiliging voor meer informatie over strategieën [en best practices.](security-roadmap.md)</span><span class="sxs-lookup"><span data-stu-id="e8b72-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="e8b72-113">Wat gebeurt er wanneer een geïnfecteerd bestand wordt geüpload naar SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="e8b72-113">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="e8b72-114">De Microsoft 365-virusdetectie-engine wordt asynchroon binnen SharePoint Online uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e8b72-114">The Microsoft 365 virus detection engine runs asynchronously within SharePoint Online.</span></span> <span data-ttu-id="e8b72-115">**Niet alle bestanden worden automatisch gescand bij het uploaden.**</span><span class="sxs-lookup"><span data-stu-id="e8b72-115">**All files are not automatically scanned on upload**.</span></span> <span data-ttu-id="e8b72-116">Heuristics bepalen de bestanden die moeten worden gescand.</span><span class="sxs-lookup"><span data-stu-id="e8b72-116">Heuristics determine the files to scan.</span></span> <span data-ttu-id="e8b72-117">Wanneer een bestand een virus bevat, wordt er een vlag aan het bestand toegevoegd, zodat het niet opnieuw kan worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="e8b72-117">When a file is found to contain a virus, the file is flagged so it can't be downloaded again.</span></span> <span data-ttu-id="e8b72-118">In april 2018 hebben we de limiet van 25 MB voor gescande bestanden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="e8b72-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="e8b72-119">Dit is wat er gebeurt:</span><span class="sxs-lookup"><span data-stu-id="e8b72-119">Here's what happens:</span></span>

1. <span data-ttu-id="e8b72-120">Een gebruiker uploadt een bestand naar SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e8b72-120">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="e8b72-121">SharePoint Online bepaalt of het bestand voldoet aan de criteria voor een scan.</span><span class="sxs-lookup"><span data-stu-id="e8b72-121">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="e8b72-122">De virusdetectie-engine scant het bestand.</span><span class="sxs-lookup"><span data-stu-id="e8b72-122">The virus detection engine scans the file.</span></span>
4. <span data-ttu-id="e8b72-123">Als er een virus wordt gevonden, stelt de virusen engine een eigenschap in voor het bestand om aan te geven dat het geïnfecteerd is.</span><span class="sxs-lookup"><span data-stu-id="e8b72-123">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="e8b72-124">Wat gebeurt er wanneer een gebruiker een geïnfecteerd bestand probeert te downloaden met behulp van de browser?</span><span class="sxs-lookup"><span data-stu-id="e8b72-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="e8b72-125">Als een bestand is geïnfecteerd, kunnen gebruikers het niet downloaden van SharePoint Online met behulp van een browser.</span><span class="sxs-lookup"><span data-stu-id="e8b72-125">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="e8b72-126">Dit is wat er gebeurt:</span><span class="sxs-lookup"><span data-stu-id="e8b72-126">Here's what happens:</span></span>

1. <span data-ttu-id="e8b72-127">Een gebruiker opent een webbrowser en probeert een geïnfecteerd bestand van SharePoint Online te downloaden.</span><span class="sxs-lookup"><span data-stu-id="e8b72-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="e8b72-128">De gebruiker krijgt een waarschuwing dat er een virus is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="e8b72-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="e8b72-129">De gebruiker krijgt standaard de mogelijkheid om het bestand te downloaden en dit op te schonen met de antivirussoftware op zijn eigen apparaat.</span><span class="sxs-lookup"><span data-stu-id="e8b72-129">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="e8b72-130">Beheerders kunnen de parameter *DisallowInfectedFileDownload* gebruiken op de cmdlet [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online PowerShell om te voorkomen dat gebruikers geïnfecteerde bestanden downloaden, zelfs in het venster met de waarschuwing tegen virussen.</span><span class="sxs-lookup"><span data-stu-id="e8b72-130">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="e8b72-131">Zie [SharePoint Online PowerShell](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)gebruiken om te voorkomen dat gebruikers schadelijke bestanden downloaden.</span><span class="sxs-lookup"><span data-stu-id="e8b72-131">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="e8b72-132">Zodra u de parameter *DisallowInfectedFileDownload* inschakelen, wordt de toegang tot de gedetecteerde/geblokkeerde bestanden volledig geblokkeerd voor gebruikers en beheerders.</span><span class="sxs-lookup"><span data-stu-id="e8b72-132">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="e8b72-133">Wat gebeurt er wanneer de OneDrive-synchronisatieclient een geïnfecteerd bestand probeert te synchroniseren?</span><span class="sxs-lookup"><span data-stu-id="e8b72-133">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="e8b72-134">OneDrive-synchronisatiecl clients downloaden geen bestanden die virussen bevatten.</span><span class="sxs-lookup"><span data-stu-id="e8b72-134">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="e8b72-135">De synchronisatieclient geeft een melding weer dat het bestand niet kan worden gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="e8b72-135">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a><span data-ttu-id="e8b72-136">Uitgebreide mogelijkheden met Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="e8b72-136">Extended capabilities with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="e8b72-137">Microsoft 365-organisaties die Microsoft Defender voor [Office 365](office-365-atp.md) hebben opgenomen in hun abonnement of die zijn aangeschaft als een invoeglage, kunnen veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams inschakelen voor verbeterde rapportage en beveiliging.</span><span class="sxs-lookup"><span data-stu-id="e8b72-137">Microsoft 365 organizations that have [Microsoft Defender for Office 365](office-365-atp.md) included in their subscription or purchased as an add-on can enable Safe Attachments for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="e8b72-138">Zie Veilige bijlagen voor [SharePoint, OneDrive](atp-for-spo-odb-and-teams.md)en Microsoft Teams voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e8b72-138">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="e8b72-139">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="e8b72-139">Related Articles</span></span>

[<span data-ttu-id="e8b72-140">Bescherming tegen malware en ransomware in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e8b72-140">Malware and ransomware protection in Microsoft 365</span></span>](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)

<span data-ttu-id="e8b72-141">Voor meer informatie over antivirussoftware in SharePoint Online, OneDrive en Microsoft Teams, bekijk 'Protect [against threats'](protect-against-threats.md) en 'Turn [on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams'.](turn-on-atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="e8b72-141">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
