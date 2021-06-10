---
title: Uitsluitingen instellen voor Microsoft Defender Antivirus scans
description: U kunt uitsluiten dat bestanden (inclusief bestanden die zijn gewijzigd door opgegeven processen) en mappen worden gescand door Microsoft Defender Antivirus. Valideer uw uitsluitingen met PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 7065aa7cd1975b2f5a38e79da8618ba3efdcdac5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275118"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="95cbd-104">Uitsluitingen configureren en valideren voor Microsoft Defender Antivirus scans</span><span class="sxs-lookup"><span data-stu-id="95cbd-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="95cbd-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="95cbd-105">**Applies to:**</span></span>

- [<span data-ttu-id="95cbd-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="95cbd-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="95cbd-107">U kunt bepaalde bestanden, mappen, processen en proces geopende bestanden uitsluiten van Microsoft Defender Antivirus scans.</span><span class="sxs-lookup"><span data-stu-id="95cbd-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="95cbd-108">Dergelijke uitsluitingen zijn van toepassing [op geplande scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [scans](run-scan-microsoft-defender-antivirus.md)op aanvraag en altijd realtime bescherming [en monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="95cbd-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="95cbd-109">Uitsluitingen voor proces geopende bestanden zijn alleen van toepassing op realtime beveiliging.</span><span class="sxs-lookup"><span data-stu-id="95cbd-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="95cbd-110">Uitsluitingen configureren en valideren</span><span class="sxs-lookup"><span data-stu-id="95cbd-110">Configure and validate exclusions</span></span>

<span data-ttu-id="95cbd-111">Zie het volgende om uitsluitingen te configureren en te valideren:</span><span class="sxs-lookup"><span data-stu-id="95cbd-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="95cbd-112">[Uitsluitingen configureren en valideren op basis van bestandsnaam, extensie en maplocatie.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="95cbd-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="95cbd-113">U kunt bestanden uitsluiten van Microsoft Defender Antivirus scans op basis van de bestandsextensie, bestandsnaam of locatie.</span><span class="sxs-lookup"><span data-stu-id="95cbd-113">You can exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="95cbd-114">[Uitsluitingen configureren en valideren voor bestanden die door processen zijn geopend.](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="95cbd-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="95cbd-115">U kunt bestanden uitsluiten van scans die door een bepaald proces zijn geopend.</span><span class="sxs-lookup"><span data-stu-id="95cbd-115">You can exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="95cbd-116">Aanbevelingen voor het definiëren van uitsluitingen</span><span class="sxs-lookup"><span data-stu-id="95cbd-116">Recommendations for defining exclusions</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95cbd-117">Microsoft Defender Antivirus omvat veel automatische uitsluitingen op basis van bekende gedragingen van het besturingssysteem en gebruikelijke beheerbestanden, zoals die worden gebruikt in ondernemingsbeheer, databasebeheer en andere ondernemingsscenario's en -situaties.</span><span class="sxs-lookup"><span data-stu-id="95cbd-117">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>  
> 
> <span data-ttu-id="95cbd-118">Als u uitsluitingen definieert, wordt de bescherming die door de Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="95cbd-118">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="95cbd-119">U moet altijd de risico's evalueren die zijn gekoppeld aan het implementeren van uitsluitingen en u moet alleen bestanden uitsluiten die u zeker weet dat ze niet schadelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="95cbd-119">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="95cbd-120">Houd rekening met de volgende punten wanneer u uitsluitingen definieert:</span><span class="sxs-lookup"><span data-stu-id="95cbd-120">Keep the following points in mind when you are defining exclusions:</span></span>  

- <span data-ttu-id="95cbd-121">Uitsluitingen zijn technisch gezien een beschermingsgat.</span><span class="sxs-lookup"><span data-stu-id="95cbd-121">Exclusions are technically a protection gap.</span></span> <span data-ttu-id="95cbd-122">Houd altijd rekening met risico's bij het definiëren van uitsluitingen.</span><span class="sxs-lookup"><span data-stu-id="95cbd-122">Always consider mitigations when defining exclusions.</span></span> <span data-ttu-id="95cbd-123">Andere risicobeperking kan net zo eenvoudig zijn als ervoor zorgen dat de uitgesloten locatie beschikt over de juiste toegangscontrolelijsten (ACL's), auditbeleid, wordt verwerkt door een up-to-date software, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="95cbd-123">Other mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="95cbd-124">Controleer de uitsluitingen regelmatig.</span><span class="sxs-lookup"><span data-stu-id="95cbd-124">Review the exclusions periodically.</span></span> <span data-ttu-id="95cbd-125">Controleer de risico's opnieuw en dwing deze opnieuw af als onderdeel van het controleproces.</span><span class="sxs-lookup"><span data-stu-id="95cbd-125">Recheck and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="95cbd-126">Vermijd het definiëren van uitsluitingen die proactief willen zijn.</span><span class="sxs-lookup"><span data-stu-id="95cbd-126">Ideally, avoid defining exclusions intending to be proactive.</span></span> <span data-ttu-id="95cbd-127">Sluit bijvoorbeeld iets niet uit omdat u denkt dat het in de toekomst een probleem kan zijn.</span><span class="sxs-lookup"><span data-stu-id="95cbd-127">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="95cbd-128">Gebruik uitsluitingen alleen voor specifieke problemen, zoals die met betrekking tot prestaties of toepassingscompatibiliteit die uitsluitingen kunnen beperken.</span><span class="sxs-lookup"><span data-stu-id="95cbd-128">Use exclusions only for specific issues, such as those pertaining to performance or application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="95cbd-129">Controleer de wijzigingen in de uitsluitingslijst.</span><span class="sxs-lookup"><span data-stu-id="95cbd-129">Audit the exclusion list changes.</span></span> <span data-ttu-id="95cbd-130">De beveiligingsbeheerder moet voldoende context behouden waarom een bepaalde uitsluiting is toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="95cbd-130">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="95cbd-131">U moet een antwoord kunnen geven met specifieke redenering waarom een bepaald pad is uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="95cbd-131">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="95cbd-132">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="95cbd-132">Related articles</span></span>

- [<span data-ttu-id="95cbd-133">Microsoft Defender Antivirus uitsluitingen op Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="95cbd-133">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="95cbd-134">Veelvoorkomende fouten bij het definiëren van uitsluitingen voorkomen</span><span class="sxs-lookup"><span data-stu-id="95cbd-134">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
