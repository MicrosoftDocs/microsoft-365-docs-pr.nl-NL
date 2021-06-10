---
title: Blootstellingsscore in Threat and Vulnerability Management
description: De Threat and Vulnerability Management blootstellingsscore geeft aan hoe kwetsbaar uw organisatie is voor cyberbeveiligingsdreigingen.
keywords: exposure score, Microsoft Defender for Endpoint exposure score, Microsoft Defender for Endpoint tvm exposure score, organization exposure score, tvm organization exposure score, Threat and Vulnerability Management, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fcea240fe1dc0ce97a2800391320b04c39c84336
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934103"
---
# <a name="exposure-score---threat-and-vulnerability-management"></a><span data-ttu-id="19238-104">Blootstellingsscore - Threat and Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="19238-104">Exposure score - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="19238-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="19238-105">**Applies to:**</span></span>

- [<span data-ttu-id="19238-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="19238-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="19238-107">Bedreiging en vulnerability management</span><span class="sxs-lookup"><span data-stu-id="19238-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="19238-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19238-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="19238-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="19238-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="19238-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="19238-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="19238-111">Uw blootstellingsscore is zichtbaar in het [dashboard Bedreiging en vulnerability management van](tvm-dashboard-insights.md) de Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="19238-111">Your exposure score is visible in the [Threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="19238-112">Het geeft aan hoe kwetsbaar uw organisatie is voor cyberbeveiligingsdreigingen.</span><span class="sxs-lookup"><span data-stu-id="19238-112">It reflects how vulnerable your organization is to cybersecurity threats.</span></span> <span data-ttu-id="19238-113">Lage blootstellingsscore betekent dat uw apparaten minder kwetsbaar zijn voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="19238-113">Low exposure score means your devices are less vulnerable from exploitation.</span></span>

- <span data-ttu-id="19238-114">Snel inzicht krijgen in en identificeren van take-aways op hoog niveau over de staat van beveiliging in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="19238-114">Quickly understand and identify high-level takeaways about the state of security in your organization.</span></span>
- <span data-ttu-id="19238-115">Detecteer en reageer op gebieden waarvoor onderzoek of actie moet worden ondernomen om de huidige status te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="19238-115">Detect and respond to areas that require investigation or action to improve the current state.</span></span>
- <span data-ttu-id="19238-116">Communiceer met collega's en management over de impact van beveiligingsinspanningen.</span><span class="sxs-lookup"><span data-stu-id="19238-116">Communicate with peers and management about the impact of security efforts.</span></span>

<span data-ttu-id="19238-117">De kaart geeft u een hoog niveau van de trend van uw blootstellingsscore in de tijd.</span><span class="sxs-lookup"><span data-stu-id="19238-117">The card gives you a high-level view of your exposure score trend over time.</span></span> <span data-ttu-id="19238-118">Eventuele pieken in de grafiek geven een visuele indicatie van een hoge blootstelling aan cyberbeveiligingsdreiging die u verder kunt onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="19238-118">Any spikes in the chart give you a visual indication of a high cybersecurity threat exposure that you can investigate further.</span></span>

![Belichtingsscorekaart](images/tvm_exp_score.png)

## <a name="how-it-works"></a><span data-ttu-id="19238-120">Hoe het werkt</span><span class="sxs-lookup"><span data-stu-id="19238-120">How it works</span></span>

<span data-ttu-id="19238-121">De blootstellingsscore wordt onderverdeeld in de volgende niveaus:</span><span class="sxs-lookup"><span data-stu-id="19238-121">The exposure score is broken down into the following levels:</span></span>

- <span data-ttu-id="19238-122">0–29: lage blootstellingsscore</span><span class="sxs-lookup"><span data-stu-id="19238-122">0–29: low exposure score</span></span>
- <span data-ttu-id="19238-123">30–69: gemiddelde blootstellingsscore</span><span class="sxs-lookup"><span data-stu-id="19238-123">30–69: medium exposure score</span></span>
- <span data-ttu-id="19238-124">70–100: hoge blootstellingsscore</span><span class="sxs-lookup"><span data-stu-id="19238-124">70–100: high exposure score</span></span>

<span data-ttu-id="19238-125">U kunt de problemen oplossen op basis van beveiligingsaanbevelingen met prioriteit om de [blootstellingsscore](tvm-security-recommendation.md) te verlagen.</span><span class="sxs-lookup"><span data-stu-id="19238-125">You can remediate the issues based on prioritized [security recommendations](tvm-security-recommendation.md) to reduce the exposure score.</span></span> <span data-ttu-id="19238-126">Elke software heeft zwakke punten die worden omgezet in aanbevelingen en prioriteit krijgen op basis van risico's voor de organisatie.</span><span class="sxs-lookup"><span data-stu-id="19238-126">Each software has weaknesses that are transformed into recommendations and prioritized based on risk to the organization.</span></span>

## <a name="reduce-your-threat-and-vulnerability-exposure"></a><span data-ttu-id="19238-127">Uw blootstelling aan bedreigingen en kwetsbaarheid verminderen</span><span class="sxs-lookup"><span data-stu-id="19238-127">Reduce your threat and vulnerability exposure</span></span>

<span data-ttu-id="19238-128">Vererk de blootstelling aan bedreigingen en kwetsbaarheid door beveiligingsaanbevelingen [te corrigeren.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="19238-128">Lower your threat and vulnerability exposure by remediating [security recommendations](tvm-security-recommendation.md).</span></span> <span data-ttu-id="19238-129">Maak de meeste impact op uw blootstellingsscore door de belangrijkste beveiligingsaanbevelingen te corrigeren, die kunnen worden bekeken in [het Threat and Vulnerability Management dashboard.](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="19238-129">Make the most impact to your exposure score by remediating the top security recommendations, which can be viewed in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="19238-130">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="19238-130">Related topics</span></span>

- [<span data-ttu-id="19238-131">Overzicht van bedreigingen en vulnerability management</span><span class="sxs-lookup"><span data-stu-id="19238-131">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="19238-132">Microsoft Secure Score voor apparaten</span><span class="sxs-lookup"><span data-stu-id="19238-132">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="19238-133">Beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="19238-133">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="19238-134">Tijdlijn van het evenement</span><span class="sxs-lookup"><span data-stu-id="19238-134">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
