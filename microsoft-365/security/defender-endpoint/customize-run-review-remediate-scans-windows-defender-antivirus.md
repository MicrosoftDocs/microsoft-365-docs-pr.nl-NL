---
title: Geplande en on-demand scans uitvoeren en aanpassen
description: Microsoft Defender Antivirus scans aanpassen en starten op eindpunten in uw netwerk.
keywords: scannen, plannen, aanpassen, uitsluitingen, bestanden uitsluiten, herstellen, resultaten scannen, quarantaine, bedreiging verwijderen, quick scan, volledige scan, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5f8e5606b01186e31a58f6d506b5898f20b63511
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690025"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans--remediation"></a><span data-ttu-id="c5b1b-104">De resultaten van Microsoft Defender Antivirus scans aanpassen, starten en controleren & herstel</span><span class="sxs-lookup"><span data-stu-id="c5b1b-104">Customize, initiate, and review the results of Microsoft Defender Antivirus scans & remediation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c5b1b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c5b1b-105">**Applies to:**</span></span>

- [<span data-ttu-id="c5b1b-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="c5b1b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c5b1b-107">U kunt Group Policy, PowerShell en Windows Management Instrumentation (WMI) gebruiken om Microsoft Defender Antivirus scans te configureren.</span><span class="sxs-lookup"><span data-stu-id="c5b1b-107">You can use Group Policy, PowerShell, and Windows Management Instrumentation (WMI) to configure Microsoft Defender Antivirus scans.</span></span> 

## <a name="in-this-section"></a><span data-ttu-id="c5b1b-108">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="c5b1b-108">In this section</span></span>

| <span data-ttu-id="c5b1b-109">Artikel</span><span class="sxs-lookup"><span data-stu-id="c5b1b-109">Article</span></span> | <span data-ttu-id="c5b1b-110">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="c5b1b-110">Description</span></span> |
|:---|:---|
|[<span data-ttu-id="c5b1b-111">Bestands-, map- en proces-geopende bestandsuitsluitingen configureren en valideren in Microsoft Defender Antivirus scans</span><span class="sxs-lookup"><span data-stu-id="c5b1b-111">Configure and validate file, folder, and process-opened file exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md) | <span data-ttu-id="c5b1b-112">U kunt bestanden (inclusief bestanden die zijn gewijzigd door opgegeven processen) en mappen uitsluiten van scans op aanvraag, geplande scans en altijd in realtime beveiligingscontrole en scannen</span><span class="sxs-lookup"><span data-stu-id="c5b1b-112">You can exclude files (including files modified by specified processes) and folders from on-demand scans, scheduled scans, and always-on real-time protection monitoring and scanning</span></span> |
|[<span data-ttu-id="c5b1b-113">Scanopties voor Microsoft Defender Antivirus configureren</span><span class="sxs-lookup"><span data-stu-id="c5b1b-113">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md) | <span data-ttu-id="c5b1b-114">U kunt Microsoft Defender Antivirus zo configureren dat bepaalde typen e-mailopslagbestanden, back-up- of herstelpunten en gearchiveerde bestanden (zoals ZIP-bestanden) in scans worden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="c5b1b-114">You can configure Microsoft Defender Antivirus to include certain types of email storage files, back-up or reparse points, and archived files (such as .zip files) in scans.</span></span> <span data-ttu-id="c5b1b-115">U kunt ook netwerkbestandsscans inschakelen</span><span class="sxs-lookup"><span data-stu-id="c5b1b-115">You can also enable network file scanning</span></span> |
|[<span data-ttu-id="c5b1b-116">Herstel configureren voor scans</span><span class="sxs-lookup"><span data-stu-id="c5b1b-116">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md) | <span data-ttu-id="c5b1b-117">Configureren wat Microsoft Defender Antivirus moet doen wanneer een bedreiging wordt gedetecteerd en hoe lang in quarantaine geplaatste bestanden moeten worden bewaard in de quarantainemap</span><span class="sxs-lookup"><span data-stu-id="c5b1b-117">Configure what Microsoft Defender Antivirus should do when it detects a threat, and how long quarantined files should be retained in the quarantine folder</span></span> |
|[<span data-ttu-id="c5b1b-118">Geplande scans configureren</span><span class="sxs-lookup"><span data-stu-id="c5b1b-118">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | <span data-ttu-id="c5b1b-119">Terugkerende (geplande) scans instellen, inclusief wanneer ze moeten worden uitgevoerd en of ze als volledige of snelle scans moeten worden uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="c5b1b-119">Set up recurring (scheduled) scans, including when they should run and whether they run as full or quick scans</span></span> |
|[<span data-ttu-id="c5b1b-120">Scans configureren en uitvoeren</span><span class="sxs-lookup"><span data-stu-id="c5b1b-120">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md) | <span data-ttu-id="c5b1b-121">On-demand scans uitvoeren en configureren met PowerShell, Windows Management Instrumentation of afzonderlijk op eindpunten met de Windows Security-app</span><span class="sxs-lookup"><span data-stu-id="c5b1b-121">Run and configure on-demand scans using PowerShell, Windows Management Instrumentation, or individually on endpoints with the Windows Security app</span></span> |
|[<span data-ttu-id="c5b1b-122">Scanresultaten controleren</span><span class="sxs-lookup"><span data-stu-id="c5b1b-122">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md) | <span data-ttu-id="c5b1b-123">Bekijk de resultaten van scans met Microsoft Endpoint Configuration Manager, Microsoft Intune of de Windows Security-app</span><span class="sxs-lookup"><span data-stu-id="c5b1b-123">Review the results of scans using  Microsoft Endpoint Configuration Manager, Microsoft Intune, or the Windows Security app</span></span> |