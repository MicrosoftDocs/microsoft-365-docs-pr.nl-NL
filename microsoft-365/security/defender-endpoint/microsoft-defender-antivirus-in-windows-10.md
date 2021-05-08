---
title: Beveiliging van de volgende generatie
description: Informatie over het beheren, configureren en gebruiken van Microsoft Defender Antivirus, ingebouwde antimalware- en antivirusbeveiliging.
keywords: Microsoft Defender Antivirus, Windows Defender, antimalware, scep, system center endpoint protection, system center configuration manager, virus, malware, bedreiging, detectie, beveiliging, bescherming
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: c4a0e40f3f6e6728af3d8c7a6da29485f1fad3fd
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269598"
---
# <a name="next-generation-protection"></a><span data-ttu-id="0980c-104">Beveiliging van de volgende generatie</span><span class="sxs-lookup"><span data-stu-id="0980c-104">Next-generation protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0980c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="0980c-105">**Applies to:**</span></span>

- [<span data-ttu-id="0980c-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="0980c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

## <a name="microsoft-defender-antivirus-your-next-generation-protection"></a><span data-ttu-id="0980c-107">Microsoft Defender Antivirus: vernieuwde beveiliging</span><span class="sxs-lookup"><span data-stu-id="0980c-107">Microsoft Defender Antivirus: Your next-generation protection</span></span>

<span data-ttu-id="0980c-108">Microsoft Defender Antivirus is het nieuwe beveiligingsonderdeel van Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="0980c-108">Microsoft Defender Antivirus is the next-generation protection component of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="0980c-109">Deze beveiliging brengt machine learning, big data-analyse, diepgaand onderzoek naar dreigingsweerstand en de Microsoft-cloudinfrastructuur samen om apparaten in uw organisatie te beschermen.</span><span class="sxs-lookup"><span data-stu-id="0980c-109">This protection brings together machine learning, big-data analysis, in-depth threat resistance research, and the Microsoft cloud infrastructure to protect devices in your enterprise organization.</span></span> <span data-ttu-id="0980c-110">De nieuwe beveiligingsservices bieden de volgende mogelijkheden:</span><span class="sxs-lookup"><span data-stu-id="0980c-110">Your next-generation protection services include the following capabilities:</span></span>

- <span data-ttu-id="0980c-111">[Heuristische en realtime antivirusbeveiliging op basis gedrag](configure-protection-features-microsoft-defender-antivirus.md), inclusief continu scannen van bestanden en processen en andere heuristische analyses (ook wel *realtime bescherming*) genoemd.</span><span class="sxs-lookup"><span data-stu-id="0980c-111">[Behavior-based, heuristic, and real-time antivirus protection](configure-protection-features-microsoft-defender-antivirus.md), which includes always-on scanning using file and process behavior monitoring and other heuristics (also known as *real-time protection*).</span></span> <span data-ttu-id="0980c-112">Dit omvat ook het opsporen en blokkeren van apps die onveilig worden geacht, maar mogelijk niet worden gedetecteerd als malware.</span><span class="sxs-lookup"><span data-stu-id="0980c-112">It also includes detecting and blocking apps that are deemed unsafe, but might not be detected as malware.</span></span>
- <span data-ttu-id="0980c-113">[Door de cloud geleverde bescherming](cloud-protection-microsoft-defender-antivirus.md), waaronder snelle detectie en blokkering van nieuwe dreigingen.</span><span class="sxs-lookup"><span data-stu-id="0980c-113">[Cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md), which includes near-instant detection and blocking of new and emerging threats.</span></span>
- <span data-ttu-id="0980c-114">[Speciale beveiliging en productupdates](manage-updates-baselines-microsoft-defender-antivirus.md), waaronder updates om Microsoft Defender Antivirus up-to-date te houden.</span><span class="sxs-lookup"><span data-stu-id="0980c-114">[Dedicated protection and product updates](manage-updates-baselines-microsoft-defender-antivirus.md), which includes updates related to keeping Microsoft Defender Antivirus up to date.</span></span>

## <a name="try-a-demo"></a><span data-ttu-id="0980c-115">Probeer het uit!</span><span class="sxs-lookup"><span data-stu-id="0980c-115">Try a demo!</span></span>

<span data-ttu-id="0980c-116">Ga naar de [demowebsite van Microsoft Defender voor Eindpunt](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) om te controleren of de volgende beveiligingsfuncties werken en verken ze via demoscenario's:</span><span class="sxs-lookup"><span data-stu-id="0980c-116">Visit the [Microsoft Defender for Endpoint demo website](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following protection features are working and explore them using demo scenarios:</span></span>
- <span data-ttu-id="0980c-117">Cloudbeveiliging</span><span class="sxs-lookup"><span data-stu-id="0980c-117">Cloud-delivered protection</span></span>
- <span data-ttu-id="0980c-118">Blokkeren op het eerste gezicht (BAFS)</span><span class="sxs-lookup"><span data-stu-id="0980c-118">Block at first sight (BAFS) protection</span></span>
- <span data-ttu-id="0980c-119">Bescherming tegen potentieel ongewenste toepassingen (PUA)</span><span class="sxs-lookup"><span data-stu-id="0980c-119">Potentially unwanted applications (PUA) protection</span></span>

## <a name="minimum-system-requirements"></a><span data-ttu-id="0980c-120">Minimale systeemvereisten</span><span class="sxs-lookup"><span data-stu-id="0980c-120">Minimum system requirements</span></span>

<span data-ttu-id="0980c-121">Voor Microsoft Defender Antivirus gelden dezelfde hardwarevereisten als voor Windows 10.</span><span class="sxs-lookup"><span data-stu-id="0980c-121">Microsoft Defender Antivirus has the same hardware requirements as of Windows 10.</span></span> <span data-ttu-id="0980c-122">Voor meer informatie kunt u de volgende bronnen raadplegen:</span><span class="sxs-lookup"><span data-stu-id="0980c-122">For more information, see the following resources:</span></span>

- [<span data-ttu-id="0980c-123">Minimale hardwarevereisten</span><span class="sxs-lookup"><span data-stu-id="0980c-123">Minimum hardware requirements</span></span>](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)
- [<span data-ttu-id="0980c-124">Richtlijnen voor hardwarecomponenten</span><span class="sxs-lookup"><span data-stu-id="0980c-124">Hardware component guidelines</span></span>](/windows-hardware/design/component-guidelines/components)

## <a name="configure-next-generation-protection-services"></a><span data-ttu-id="0980c-125">Configureren nieuwe beveiligingsservices</span><span class="sxs-lookup"><span data-stu-id="0980c-125">Configure next-generation protection services</span></span>

<span data-ttu-id="0980c-126">Zie [Microsoft Defender Antivirusfuncties configureren](configure-microsoft-defender-antivirus-features.md) voor informatie over het configureren van de volgende generatie beveiligingsservices.</span><span class="sxs-lookup"><span data-stu-id="0980c-126">For information on how to configure next-generation protection services, see [Configure Microsoft Defender Antivirus features](configure-microsoft-defender-antivirus-features.md).</span></span>

> [!Note]  
> <span data-ttu-id="0980c-127">Als Microsoft Defender Antivirus wordt uitgevoerd zijn configuratie en beheer grotendeels hetzelfde in Windows Server 2016 en Windows Server 2019; er zijn echter wel enkele verschillen.</span><span class="sxs-lookup"><span data-stu-id="0980c-127">Configuration and management is largely the same in Windows Server 2016 and Windows Server 2019, while running Microsoft Defender Antivirus; however, there are some differences.</span></span> <span data-ttu-id="0980c-128">Zie voor meer informatie [Microsoft Defender Antivirus op Windows Server 2016 en 2019](microsoft-defender-antivirus-on-windows-server.md).</span><span class="sxs-lookup"><span data-stu-id="0980c-128">To learn more, see [Microsoft Defender Antivirus on Windows Server 2016 and 2019](microsoft-defender-antivirus-on-windows-server.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0980c-129">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0980c-129">See also</span></span>

- [<span data-ttu-id="0980c-130">Microsoft Defender Antivirus op Windows Server 2016 en 2019</span><span class="sxs-lookup"><span data-stu-id="0980c-130">Microsoft Defender Antivirus on Windows Server 2016 and 2019</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="0980c-131">Beheer en configuratie van Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="0980c-131">Microsoft Defender Antivirus management and configuration</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0980c-132">Microsoft Defender Antivirusbeveiliging evalueren</span><span class="sxs-lookup"><span data-stu-id="0980c-132">Evaluate Microsoft Defender Antivirus protection</span></span>](evaluate-microsoft-defender-antivirus.md)
