---
title: Overzicht van de mogelijkheden voor eindpuntdetectie en -antwoorden
ms.reviewer: ''
description: Meer informatie over de mogelijkheden voor het detecteren en reageren van eindpunten in Microsoft Defender ATP
keywords: ''
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0a5a665fac1883016ac222197ba8322f78e2558f
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186171"
---
# <a name="overview-of-endpoint-detection-and-response"></a><span data-ttu-id="4109e-103">Overzicht van eindpuntdetectie en -antwoord</span><span class="sxs-lookup"><span data-stu-id="4109e-103">Overview of endpoint detection and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4109e-104">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4109e-104">**Applies to:**</span></span>
- [<span data-ttu-id="4109e-105">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="4109e-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4109e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4109e-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4109e-107">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="4109e-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4109e-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="4109e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="4109e-109">De detectie- en antwoordmogelijkheden van Defender voor eindpunten bieden geavanceerde aanvalsdetecties die bijna realtime zijn en actie kunnen worden ondernomen.</span><span class="sxs-lookup"><span data-stu-id="4109e-109">Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="4109e-110">Beveiligingsanalisten kunnen waarschuwingen effectief prioriteit geven, inzicht krijgen in het volledige bereik van een inbreuk en reactieacties uitvoeren om bedreigingen te corrigeren.</span><span class="sxs-lookup"><span data-stu-id="4109e-110">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span>

<span data-ttu-id="4109e-111">Wanneer een bedreiging wordt gedetecteerd, worden waarschuwingen gemaakt in het systeem die een analist kan onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="4109e-111">When a threat is detected, alerts are created in the system for an analyst to investigate.</span></span> <span data-ttu-id="4109e-112">Waarschuwingen met dezelfde aanvalstechnieken of die worden toegeschreven aan dezelfde aanvaller, worden samengevoegd tot een entiteit die een _incident wordt genoemd._</span><span class="sxs-lookup"><span data-stu-id="4109e-112">Alerts with the same attack techniques or attributed to the same attacker are aggregated into an entity called an _incident_.</span></span> <span data-ttu-id="4109e-113">Door waarschuwingen op deze manier te aggregeren, kunnen analisten gemakkelijk gezamenlijk bedreigingen onderzoeken en beantwoorden.</span><span class="sxs-lookup"><span data-stu-id="4109e-113">Aggregating alerts in this manner makes it easy for analysts to collectively investigate and respond to threats.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

<span data-ttu-id="4109e-114">Geïnspireerd door de 'assume breach'-denkrichting verzamelt Defender for Endpoint voortdurend gedragsmatige cyber telemetrie.</span><span class="sxs-lookup"><span data-stu-id="4109e-114">Inspired by the "assume breach" mindset, Defender for Endpoint continuously collects behavioral cyber telemetry.</span></span> <span data-ttu-id="4109e-115">Dit omvat procesgegevens, netwerkactiviteiten, deep optics in de kernel en memory manager, aanmeldingsactiviteiten van gebruikers, wijzigingen in het register en bestandssysteem, en andere.</span><span class="sxs-lookup"><span data-stu-id="4109e-115">This includes process information, network activities, deep optics into the kernel and memory manager, user login activities, registry and file system changes, and others.</span></span> <span data-ttu-id="4109e-116">De gegevens worden zes maanden opgeslagen, zodat een analist terug in de tijd kan reizen naar het begin van een aanval.</span><span class="sxs-lookup"><span data-stu-id="4109e-116">The information is stored for six months, enabling an analyst to travel back in time to the start of an attack.</span></span> <span data-ttu-id="4109e-117">De analist kan vervolgens in verschillende weergaven draaien en een onderzoek benaderen via meerdere vectoren.</span><span class="sxs-lookup"><span data-stu-id="4109e-117">The analyst can then pivot in various views and approach an investigation through multiple vectors.</span></span>

<span data-ttu-id="4109e-118">De antwoordmogelijkheden bieden u de macht om snel bedreigingen te corrigeren door op de betreffende entiteiten te reageren.</span><span class="sxs-lookup"><span data-stu-id="4109e-118">The response capabilities give you the power to promptly remediate threats by acting on the affected entities.</span></span>


## <a name="related-topics"></a><span data-ttu-id="4109e-119">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="4109e-119">Related topics</span></span>
- [<span data-ttu-id="4109e-120">Dashboard Beveiligingsbewerkingen</span><span class="sxs-lookup"><span data-stu-id="4109e-120">Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="4109e-121">Wachtrij incidenten</span><span class="sxs-lookup"><span data-stu-id="4109e-121">Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="4109e-122">Waarschuwingenwachtrij</span><span class="sxs-lookup"><span data-stu-id="4109e-122">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="4109e-123">Lijst apparaten</span><span class="sxs-lookup"><span data-stu-id="4109e-123">Devices list</span></span>](machines-view-overview.md)

