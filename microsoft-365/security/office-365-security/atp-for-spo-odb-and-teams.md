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
description: Meer informatie over Geavanceerde bedreigingsbeveiliging van Office 365 voor bestanden in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.
ms.openlocfilehash: e4a711d6554ffcb8e291d5b2154120d078995e94
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815407"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="e2162-103">ATP voor SharePoint, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e2162-103">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="e2162-104">Overzicht van Office 365 ATP voor SharePoint, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e2162-104">Overview of Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="e2162-105">Mensen delen regelmatig bestanden en werken samen met SharePoint, OneDrive en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e2162-105">People regularly share files and collaborate using SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="e2162-106">Met [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan uw organisatie op een veiligere manier samenwerken.</span><span class="sxs-lookup"><span data-stu-id="e2162-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can collaborate in a safer manner.</span></span> <span data-ttu-id="e2162-107">ATP helpt bij het detecteren en blokkeren van bestanden die zijn geïdentificeerd als kwaadaardig in teamsites en documentbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="e2162-107">ATP helps detect and block files that are identified as malicious in team sites and document libraries.</span></span>

## <a name="how-office-365-atp-operates"></a><span data-ttu-id="e2162-108">Hoe Office 365 ATP werkt</span><span class="sxs-lookup"><span data-stu-id="e2162-108">How Office 365 ATP operates</span></span>

<span data-ttu-id="e2162-109">Wanneer een bestand in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams als kwaadaardig is aangemerkt, integreert ATP rechtstreeks met de bestandsopslag om dat bestand te vergrendelen.</span><span class="sxs-lookup"><span data-stu-id="e2162-109">When a file in SharePoint Online, OneDrive for Business, and Microsoft Teams has been identified as malicious, ATP directly integrates with the file stores to lock that file.</span></span> <span data-ttu-id="e2162-110">De volgende afbeelding toont een voorbeeld van een kwaadaardig bestand dat in een bibliotheek is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="e2162-110">The following image shows an example of a malicious file detected in a library.</span></span>

![Bestanden in OneDrive voor Bedrijven met een gedetecteerd als kwaadaardig](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="e2162-112">Hoewel het geblokkeerde bestand nog steeds wordt weergegeven in de documentbibliotheek en web-, mobiele of bureaubladtoepassingen, kan het geblokkeerde bestand niet worden geopend, gekopieerd, verplaatst of gedeeld.</span><span class="sxs-lookup"><span data-stu-id="e2162-112">Although the blocked file is still listed in the document library and web, mobile, or desktop applications, the blocked file cannot be opened, copied, moved, or shared.</span></span> <span data-ttu-id="e2162-113">Mensen kunnen echter een geblokkeerd bestand verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e2162-113">People can, however, delete a blocked file.</span></span> <span data-ttu-id="e2162-114">Hier volgt een voorbeeld van hoe dat eruit ziet op het mobiele apparaat van een gebruiker:</span><span class="sxs-lookup"><span data-stu-id="e2162-114">Here's an example of what that looks like on a user's mobile device:</span></span>

![Een geblokkeerd bestand verwijderen uit OneDrive voor Bedrijven uit de mobiele OneDrive-app](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="e2162-116">Afhankelijk van hoe Microsoft 365 is geconfigureerd, kunnen mensen al dan niet de mogelijkheid hebben om een geblokkeerd bestand te downloaden.</span><span class="sxs-lookup"><span data-stu-id="e2162-116">Depending on how Microsoft 365 is configured, people might or might not have the ability to download a blocked file.</span></span> <span data-ttu-id="e2162-117">Zo ziet het downloaden van een geblokkeerd bestand eruit op het mobiele apparaat van een gebruiker:</span><span class="sxs-lookup"><span data-stu-id="e2162-117">Here's what downloading a blocked file looks like on a user's mobile device:</span></span>

![Een geblokkeerd bestand downloaden in OneDrive voor Bedrijven](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="e2162-119">Zie [Office 365 ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="e2162-119">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="e2162-120">Houd deze punten in gedachten</span><span class="sxs-lookup"><span data-stu-id="e2162-120">Keep these points in mind</span></span>

- <span data-ttu-id="e2162-121">ATP scant niet elk bestand in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e2162-121">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="e2162-122">Dit is normaal.</span><span class="sxs-lookup"><span data-stu-id="e2162-122">This is by design.</span></span> <span data-ttu-id="e2162-123">Bestanden worden asynchroon gescand, via een proces dat het delen en gastactiviteitsgebeurtenissen gebruikt, samen met slimme heuristiek en bedreigingssignalen om schadelijke bestanden te identificeren.</span><span class="sxs-lookup"><span data-stu-id="e2162-123">Files are scanned asynchronously, through a process that uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="e2162-124">Controleer of uw SharePoint-sites zijn geconfigureerd om de [moderne ervaring](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e2162-124">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="e2162-125">Wanneer een bestand wordt geïdentificeerd als kwaadaardig en geblokkeerd, kunnen mensen zien dat dit is gebeurd in de moderne ervaring, maar niet in de klassieke weergave.</span><span class="sxs-lookup"><span data-stu-id="e2162-125">When a file is identified as malicious and blocked, people can see that this has occurred in the Modern experience, but not the Classic view.</span></span> <span data-ttu-id="e2162-126">ATP-bescherming is van toepassing of de moderne ervaring of de Classic-weergave wordt gebruikt; Visuele indicatoren die een bestand blokkeren, zijn echter alleen aanwezig in de moderne ervaring.</span><span class="sxs-lookup"><span data-stu-id="e2162-126">ATP protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are present only in the Modern experience.</span></span>

- <span data-ttu-id="e2162-127">Bestanden die als kwaadaardig zijn geïdentificeerd in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams worden weergegeven in [rapporten voor Geavanceerde bedreigingsbeveiliging van Office 365](view-reports-for-atp.md) en in Explorer [(en realtime detecties).](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="e2162-127">Files that are identified as malicious in SharePoint Online, OneDrive for Business, or Microsoft Teams will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

- <span data-ttu-id="e2162-128">ATP maakt deel uit van de algemene strategie voor bedreigingsbescherming van uw organisatie, die anti-spam- en anti-malwarebescherming omvat, evenals veilige links en veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="e2162-128">ATP is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection, as well as Safe Links and Safe Attachments.</span></span> <span data-ttu-id="e2162-129">Zie [Beschermen tegen bedreigingen in Office 365](protect-against-threats.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e2162-129">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>

- <span data-ttu-id="e2162-130">Een SharePoint Online-beheerder kan bepalen of mensen bestanden kunnen downloaden die als kwaadaardig worden gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="e2162-130">A SharePoint Online administrator can determine whether to enable people to download files that are detected as malicious.</span></span> <span data-ttu-id="e2162-131">Dit wordt gedaan door de PowerShell-cmdlet Set-SPOTenant uit te voeren met een parameter DisallowInfectedFileDownload (zie [Office 365 ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).</span><span class="sxs-lookup"><span data-stu-id="e2162-131">This is done by running the Set-SPOTenant PowerShell cmdlet using a DisallowInfectedFileDownload parameter (see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).</span></span>

## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="e2162-132">Quarantaine in ATP voor SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e2162-132">Quarantine in ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams</span></span>

 <span data-ttu-id="e2162-133">Vanaf eind mei 2018 worden [quarantainemogelijkheden](quarantine-email-messages.md) in het Security &amp; Compliance Center uitgebreid naar ATP voor SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e2162-133">Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="e2162-134">Wanneer een bestand in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams als kwaadaardig wordt aangemerkt, wordt dit bestand niet alleen als kwaadaardig aangemerkt, maar ook dat het bestand niet wordt geopend of gedeeld, maar ook in een lijst met in quarantaine geplaatste items wordt opgenomen.</span><span class="sxs-lookup"><span data-stu-id="e2162-134">When a file in SharePoint Online, OneDrive for Business, or Microsoft Teams is identified as malicious, in addition to ATP blocking the file from being opened or shared, that file is included in a list of quarantined items.</span></span> <span data-ttu-id="e2162-135">(In de beveiliging &amp; Compliance Center, ga naar **Quarantaine voor bedreigingsbeheercontrole** \> **Review** \> **Quarantine** en filter **op Bestanden**.)</span><span class="sxs-lookup"><span data-stu-id="e2162-135">(In the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Quarantine** and filter for **Files**.)</span></span>

<span data-ttu-id="e2162-136">Als u deel uitmaakt van het Microsoft 365 for Business Security-team van uw organisatie en de benodigde [machtigingen hebt toegewezen in het Security &amp; Compliance Center,](permissions-in-the-security-and-compliance-center.md)u bestanden downloaden, vrijgeven, rapporteren en verwijderen die door ATP als kwaadaardig worden gedetecteerd uit quarantaine.</span><span class="sxs-lookup"><span data-stu-id="e2162-136">If you're part of your organization's Microsoft 365 for business security team and have the necessary [permissions assigned in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can download, release, report, and delete files that are detected as malicious by ATP from quarantine.</span></span>

- <span data-ttu-id="e2162-137">Als u een bestand **vrijgeeft en rapporteert,** wordt het ATP-blok in het bestand in de desbetreffende teamsite of documentbibliotheek voor SharePoint, OneDrive of Microsoft Teams verwijderd.</span><span class="sxs-lookup"><span data-stu-id="e2162-137">**Releasing and reporting** a file removes the ATP block on the file in the respective team site or document library for SharePoint, OneDrive, or Microsoft Teams.</span></span> <span data-ttu-id="e2162-138">Gebruikers kunnen het bestand vervolgens openen, delen en downloaden.</span><span class="sxs-lookup"><span data-stu-id="e2162-138">Users are then able to open, share, and download the file.</span></span> <span data-ttu-id="e2162-139">En wanneer de optie **Rapport verzenden naar Microsoft** is geselecteerd, wordt het bestand gerapporteerd als een fout-positief aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e2162-139">And, when the **Send report to Microsoft** option is selected, the file is reported as a false positive to Microsoft.</span></span>

- <span data-ttu-id="e2162-140">**Als u een bestand verwijdert,** wordt het bestand uit quarantaine verwijderd. Het bestand wordt echter nog steeds geblokkeerd omdat het wordt geopend of gedeeld.</span><span class="sxs-lookup"><span data-stu-id="e2162-140">**Deleting a file** removes the file from quarantine; however, the file is still blocked from being opened or shared.</span></span> <span data-ttu-id="e2162-141">Het bestand moet ook worden verwijderd in de respectievelijke documentbibliotheek of teamsite (SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="e2162-141">The file must also be deleted in its respective document library or team site (SharePoint Online, OneDrive for Business, or Microsoft Teams).</span></span>

- <span data-ttu-id="e2162-142">Als u **een bestand downloadt,** u het bestand downloaden en analyseren op fout-positieven.</span><span class="sxs-lookup"><span data-stu-id="e2162-142">**Downloading a file** enables you to download and analyze the file for any false positives.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e2162-143">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="e2162-143">Next steps</span></span>

 - [<span data-ttu-id="e2162-144">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e2162-144">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-atp-for-spo-odb-and-teams.md)

 - [<span data-ttu-id="e2162-145">Informatie weergeven over schadelijke bestanden die zijn gedetecteerd in SharePoint, OneDrive of Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e2162-145">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

