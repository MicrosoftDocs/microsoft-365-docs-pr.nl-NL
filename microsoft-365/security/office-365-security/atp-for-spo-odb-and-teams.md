---
title: ATP voor SharePoint, OneDrive en Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 03/19/2019
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Meer informatie over Office 365 Advanced Threat Protection voor bestanden in SharePoint Online, OneDrive voor bedrijven en Microsoft teams.
ms.openlocfilehash: 9831b61fafc7cb4696fbad3d569f061612f85fe1
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199037"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="ce99b-103">ATP voor SharePoint, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ce99b-103">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="ce99b-104">Overzicht van Office 365 ATP voor SharePoint, OneDrive en Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="ce99b-104">Overview of Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="ce99b-105">Gebruikers delen vaak bestanden en werken met SharePoint, OneDrive en Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="ce99b-105">People regularly share files and collaborate using SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="ce99b-106">Met [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan uw organisatie op een veiligere manier samenwerken.</span><span class="sxs-lookup"><span data-stu-id="ce99b-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can collaborate in a safer manner.</span></span> <span data-ttu-id="ce99b-107">Met ATP kunt u bestanden detecteren en blokkeren die als schadelijk zijn aangeduid in team sites en documentbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="ce99b-107">ATP helps detect and block files that are identified as malicious in team sites and document libraries.</span></span>

## <a name="how-office-365-atp-operates"></a><span data-ttu-id="ce99b-108">De werking van Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="ce99b-108">How Office 365 ATP operates</span></span>

<span data-ttu-id="ce99b-109">Wanneer een bestand in SharePoint Online, OneDrive voor bedrijven en Microsoft teams als schadelijk is geïdentificeerd, wordt de ATP rechtstreeks geïntegreerd met de bestandsarchieven om dit bestand te vergrendelen.</span><span class="sxs-lookup"><span data-stu-id="ce99b-109">When a file in SharePoint Online, OneDrive for Business, and Microsoft Teams has been identified as malicious, ATP directly integrates with the file stores to lock that file.</span></span> <span data-ttu-id="ce99b-110">In de volgende afbeelding ziet u een voorbeeld van een schadelijk bestand dat is gevonden in een bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="ce99b-110">The following image shows an example of a malicious file detected in a library.</span></span>

![Bestanden in OneDrive voor bedrijven met een gedetecteerde schadelijke versie](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="ce99b-112">Hoewel het geblokkeerde bestand nog steeds wordt weergegeven in de documentbibliotheek en Web-, mobiele en bureaubladtoepassingen, kunt u het geblokkeerde bestand niet openen, kopiëren, verplaatsen of delen.</span><span class="sxs-lookup"><span data-stu-id="ce99b-112">Although the blocked file is still listed in the document library and web, mobile, or desktop applications, the blocked file cannot be opened, copied, moved, or shared.</span></span> <span data-ttu-id="ce99b-113">Personen kunnen echter wel een geblokkeerd bestand verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ce99b-113">People can, however, delete a blocked file.</span></span> <span data-ttu-id="ce99b-114">Hier ziet u een voorbeeld van wat u ziet op het mobiele apparaat van een gebruiker:</span><span class="sxs-lookup"><span data-stu-id="ce99b-114">Here's an example of what that looks like on a user's mobile device:</span></span>

![Een geblokkeerd bestand verwijderen uit OneDrive voor bedrijven uit de mobiele OneDrive-app](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="ce99b-116">Afhankelijk van de manier waarop Microsoft 365 is geconfigureerd, kunnen personen een geblokkeerd bestand misschien wel of mogelijk niet downloaden.</span><span class="sxs-lookup"><span data-stu-id="ce99b-116">Depending on how Microsoft 365 is configured, people might or might not have the ability to download a blocked file.</span></span> <span data-ttu-id="ce99b-117">Het downloaden van een geblokkeerd bestand ziet er als volgt uit op het mobiele apparaat van een gebruiker:</span><span class="sxs-lookup"><span data-stu-id="ce99b-117">Here's what downloading a blocked file looks like on a user's mobile device:</span></span>

![Een geblokkeerd bestand downloaden in OneDrive voor bedrijven](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="ce99b-119">Zie [Office 365 ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ce99b-119">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="ce99b-120">Let op de volgende punten</span><span class="sxs-lookup"><span data-stu-id="ce99b-120">Keep these points in mind</span></span>

- <span data-ttu-id="ce99b-121">Met ATP kunt u niet elk afzonderlijk bestand in SharePoint Online, OneDrive voor bedrijven of Microsoft teams scannen.</span><span class="sxs-lookup"><span data-stu-id="ce99b-121">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="ce99b-122">Dit is inherent aan het ontwerp van het product.</span><span class="sxs-lookup"><span data-stu-id="ce99b-122">This is by design.</span></span> <span data-ttu-id="ce99b-123">Bestanden worden asynchroon gescand, via een proces waarbij gebeurtenissen voordelen en gebeurtenissen met gebeurtenissen worden gebruikt in combinatie met slimme heuristiek en bedreigings signalen om kwaadaardige bestanden te identificeren.</span><span class="sxs-lookup"><span data-stu-id="ce99b-123">Files are scanned asynchronously, through a process that uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="ce99b-124">Zorg ervoor dat de SharePoint-sites zijn geconfigureerd voor gebruik van de [moderne ervaring](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span><span class="sxs-lookup"><span data-stu-id="ce99b-124">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="ce99b-125">Wanneer een bestand wordt geïdentificeerd als schadelijk en geblokkeerd, kunnen personen zien dat dit is gebeurd in de moderne ervaring, maar niet in de klassieke weergave.</span><span class="sxs-lookup"><span data-stu-id="ce99b-125">When a file is identified as malicious and blocked, people can see that this has occurred in the Modern experience, but not the Classic view.</span></span> <span data-ttu-id="ce99b-126">ATP-beveiliging is van toepassing op de meest recente ervaring of de klassieke weergave. bestaande visuele indicatoren die een bestand blokkeert, worden echter alleen weergegeven in de moderne ervaring.</span><span class="sxs-lookup"><span data-stu-id="ce99b-126">ATP protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are present only in the Modern experience.</span></span>

- <span data-ttu-id="ce99b-127">Bestanden die worden geïdentificeerd als schadelijk in SharePoint Online, OneDrive voor bedrijven of Microsoft teams, worden weergegeven in [rapporten voor Office 365 Advanced Threat Protection](view-reports-for-atp.md) en in [Verkenner (en realtime-detectie)](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="ce99b-127">Files that are identified as malicious in SharePoint Online, OneDrive for Business, or Microsoft Teams will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

- <span data-ttu-id="ce99b-128">ATP maakt deel uit van de algemene strategie voor risico beveiliging van uw organisatie, waaronder antispam en bescherming tegen malware, en veilige koppelingen en veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="ce99b-128">ATP is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection, as well as Safe Links and Safe Attachments.</span></span> <span data-ttu-id="ce99b-129">Voor meer informatie raadpleegt u [bescherming tegen bedreigingen in Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="ce99b-129">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>

- <span data-ttu-id="ce99b-130">Een SharePoint Online-beheerder kan bepalen of personen bestanden kunnen downloaden die als schadelijk zijn gevonden.</span><span class="sxs-lookup"><span data-stu-id="ce99b-130">A SharePoint Online administrator can determine whether to enable people to download files that are detected as malicious.</span></span> <span data-ttu-id="ce99b-131">Dit doet u door de PowerShell-cmdlet Set-SPOTenant uit te voeren met behulp van een parameter DisallowInfectedFileDownload (Zie [Office 365 ATP inschakelen voor SharePoint, OneDrive en Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md)).</span><span class="sxs-lookup"><span data-stu-id="ce99b-131">This is done by running the Set-SPOTenant PowerShell cmdlet using a DisallowInfectedFileDownload parameter (see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).</span></span>

## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="ce99b-132">Quarantaine in ATP voor SharePoint Online, OneDrive voor bedrijven en Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="ce99b-132">Quarantine in ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams</span></span>

 <span data-ttu-id="ce99b-133">Vanaf te laat mei 2018 worden [quarantaine](quarantine-email-messages.md) functies in het beveiligings &amp; compliance-centrum uitgebreid met ATP voor SharePoint Online, OneDrive voor bedrijven en Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="ce99b-133">Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="ce99b-134">Wanneer een bestand in SharePoint Online, OneDrive voor bedrijven, OneDrive voor bedrijven of Microsoft teams als schadelijk wordt geïdentificeerd, wordt dat bestand toegevoegd aan een lijst met items in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="ce99b-134">When a file in SharePoint Online, OneDrive for Business, or Microsoft Teams is identified as malicious, in addition to ATP blocking the file from being opened or shared, that file is included in a list of quarantined items.</span></span> <span data-ttu-id="ce99b-135">(In de beveiliging &amp; Compliance Center, ga naar **risicobeheer** , ga naar Quarantine, \> **Evalueer** \> **Quarantine** en filter voor **bestanden**.)</span><span class="sxs-lookup"><span data-stu-id="ce99b-135">(In the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Quarantine** and filter for **Files**.)</span></span>

<span data-ttu-id="ce99b-136">Als u deel uitmaakt van het beveiligingsteam van Microsoft 365 voor bedrijven en de benodigde [machtigingen voor het beveiligings &amp; centrum hebt toegewezen](permissions-in-the-security-and-compliance-center.md), kunt u bestanden downloaden, vrijgeven, melden en verwijderen die als schadelijk zijn gedetecteerd in de quarantaine.</span><span class="sxs-lookup"><span data-stu-id="ce99b-136">If you're part of your organization's Microsoft 365 for business security team and have the necessary [permissions assigned in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can download, release, report, and delete files that are detected as malicious by ATP from quarantine.</span></span>

- <span data-ttu-id="ce99b-137">Het uitdelen **en rapporteren** van een bestand: Hiermee verwijdert u het ATP-blok voor het bestand in de desbetreffende team site of documentbibliotheek voor SharePoint, OneDrive of Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="ce99b-137">**Releasing and reporting** a file removes the ATP block on the file in the respective team site or document library for SharePoint, OneDrive, or Microsoft Teams.</span></span> <span data-ttu-id="ce99b-138">Gebruikers kunnen vervolgens het bestand openen, delen en downloaden.</span><span class="sxs-lookup"><span data-stu-id="ce99b-138">Users are then able to open, share, and download the file.</span></span> <span data-ttu-id="ce99b-139">Wanneer de optie **rapport verzenden naar Microsoft** is geselecteerd, wordt het bestand als een fout positief naar Microsoft gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="ce99b-139">And, when the **Send report to Microsoft** option is selected, the file is reported as a false positive to Microsoft.</span></span>

- <span data-ttu-id="ce99b-140">**Als u een bestand verwijdert** , verwijdert u het bestand in quarantaine. het bestand is echter nog steeds geblokkeerd om te worden geopend of gedeeld.</span><span class="sxs-lookup"><span data-stu-id="ce99b-140">**Deleting a file** removes the file from quarantine; however, the file is still blocked from being opened or shared.</span></span> <span data-ttu-id="ce99b-141">Het bestand moet ook worden verwijderd uit de bijbehorende documentbibliotheek of team site (SharePoint Online, OneDrive voor bedrijven of Microsoft teams).</span><span class="sxs-lookup"><span data-stu-id="ce99b-141">The file must also be deleted in its respective document library or team site (SharePoint Online, OneDrive for Business, or Microsoft Teams).</span></span>

- <span data-ttu-id="ce99b-142">Als u **een bestand downloadt** , kunt u het bestand downloaden en analyseren voor willekeurige onwaar positief.</span><span class="sxs-lookup"><span data-stu-id="ce99b-142">**Downloading a file** enables you to download and analyze the file for any false positives.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ce99b-143">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="ce99b-143">Next steps</span></span>

 - [<span data-ttu-id="ce99b-144">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ce99b-144">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-atp-for-spo-odb-and-teams.md)

 - [<span data-ttu-id="ce99b-145">Informatie over schadelijke bestanden weergeven die zijn gevonden in SharePoint, OneDrive of Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="ce99b-145">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

