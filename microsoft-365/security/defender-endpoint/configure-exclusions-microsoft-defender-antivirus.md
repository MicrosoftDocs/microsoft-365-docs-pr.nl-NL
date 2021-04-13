---
title: Uitsluitingen instellen voor AV-scans van Microsoft Defender
description: U kunt uitsluiten dat bestanden (inclusief bestanden die zijn gewijzigd door bepaalde processen) en mappen worden gescand door Microsoft Defender AV. Valideer uw uitsluitingen met PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 47db9b4451a885c92ca4fda0f87f0150415d3338
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690731"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="9232d-104">Uitsluitingen configureren en valideren voor Antivirusscans van Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9232d-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9232d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="9232d-105">**Applies to:**</span></span>

- [<span data-ttu-id="9232d-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="9232d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9232d-107">U kunt bepaalde bestanden, mappen, processen en proces geopende bestanden uitsluiten van Microsoft Defender Antivirus-scans.</span><span class="sxs-lookup"><span data-stu-id="9232d-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="9232d-108">Dergelijke uitsluitingen zijn van toepassing [op geplande scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [scans](run-scan-microsoft-defender-antivirus.md)op aanvraag en altijd realtime bescherming [en monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="9232d-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="9232d-109">Uitsluitingen voor proces geopende bestanden zijn alleen van toepassing op realtime beveiliging.</span><span class="sxs-lookup"><span data-stu-id="9232d-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="9232d-110">Uitsluitingen configureren en valideren</span><span class="sxs-lookup"><span data-stu-id="9232d-110">Configure and validate exclusions</span></span>

<span data-ttu-id="9232d-111">Zie het volgende om uitsluitingen te configureren en te valideren:</span><span class="sxs-lookup"><span data-stu-id="9232d-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="9232d-112">[Uitsluitingen configureren en valideren op basis van bestandsnaam, extensie en maplocatie.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="9232d-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="9232d-113">Hiermee kunt u bestanden uitsluiten van Microsoft Defender Antivirus-scans op basis van de bestandsextensie, bestandsnaam of locatie.</span><span class="sxs-lookup"><span data-stu-id="9232d-113">This enables you to exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="9232d-114">[Uitsluitingen configureren en valideren voor bestanden die door processen zijn geopend.](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="9232d-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="9232d-115">Hiermee kunt u bestanden uitsluiten van scans die zijn geopend door een specifiek proces.</span><span class="sxs-lookup"><span data-stu-id="9232d-115">This enables you to exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="9232d-116">Aanbevelingen voor het definiëren van uitsluitingen</span><span class="sxs-lookup"><span data-stu-id="9232d-116">Recommendations for defining exclusions</span></span>

<span data-ttu-id="9232d-117">Als u uitsluitingen definieert, wordt de beveiliging van Microsoft Defender Antivirus verlaagd.</span><span class="sxs-lookup"><span data-stu-id="9232d-117">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="9232d-118">U moet altijd de risico's evalueren die zijn gekoppeld aan het implementeren van uitsluitingen en u moet alleen bestanden uitsluiten die u zeker weet dat ze niet schadelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="9232d-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="9232d-119">Hieronder volgt een lijst met aanbevelingen die u in gedachten moet houden bij het definiëren van uitsluitingen:</span><span class="sxs-lookup"><span data-stu-id="9232d-119">The following is a list of recommendations that you should keep in mind when defining exclusions:</span></span>  

- <span data-ttu-id="9232d-120">Uitsluitingen zijn technisch gezien een beschermingsgat. Houd altijd rekening met extra risico's bij het definiëren van uitsluitingen.</span><span class="sxs-lookup"><span data-stu-id="9232d-120">Exclusions are technically a protection gap—always consider additional mitigations when defining exclusions.</span></span> <span data-ttu-id="9232d-121">Extra risicobeperking kan net zo eenvoudig zijn als ervoor zorgen dat de uitgesloten locatie beschikt over de juiste toegangscontrolelijsten (ACL's), auditbeleid, wordt verwerkt door een up-to-date software, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="9232d-121">Additional mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="9232d-122">Controleer de uitsluitingen regelmatig.</span><span class="sxs-lookup"><span data-stu-id="9232d-122">Review the exclusions periodically.</span></span> <span data-ttu-id="9232d-123">Controleer de risico's opnieuw en dwing deze opnieuw af als onderdeel van het controleproces.</span><span class="sxs-lookup"><span data-stu-id="9232d-123">Re-check and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="9232d-124">Vermijd in het ideale ideale situaties het definiëren van proactieve uitsluitingen.</span><span class="sxs-lookup"><span data-stu-id="9232d-124">Ideally, avoid defining proactive exclusions.</span></span> <span data-ttu-id="9232d-125">Sluit bijvoorbeeld iets niet uit omdat u denkt dat het in de toekomst een probleem kan zijn.</span><span class="sxs-lookup"><span data-stu-id="9232d-125">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="9232d-126">Gebruik uitsluitingen alleen voor specifieke problemen, meestal rond prestaties, of soms rond toepassingscompatibiliteit die uitsluitingen kunnen beperken.</span><span class="sxs-lookup"><span data-stu-id="9232d-126">Use exclusions only for specific issues—mostly around performance, or sometimes around application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="9232d-127">Controleer de wijzigingen in de uitsluitingslijst.</span><span class="sxs-lookup"><span data-stu-id="9232d-127">Audit the exclusion list changes.</span></span> <span data-ttu-id="9232d-128">De beveiligingsbeheerder moet voldoende context behouden waarom een bepaalde uitsluiting is toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="9232d-128">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="9232d-129">U moet een antwoord kunnen geven met specifieke redenering waarom een bepaald pad is uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="9232d-129">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="9232d-130">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="9232d-130">Related articles</span></span>

- [<span data-ttu-id="9232d-131">Microsoft Defender Antivirus-uitsluitingen op Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="9232d-131">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9232d-132">Veelvoorkomende fouten om te voorkomen bij het definiëren van uitsluitingen</span><span class="sxs-lookup"><span data-stu-id="9232d-132">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)