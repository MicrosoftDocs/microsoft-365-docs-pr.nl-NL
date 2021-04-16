---
title: Overzicht van de mogelijkheden voor eindpuntdetectie en -antwoorden
ms.reviewer: ''
description: Meer informatie over de mogelijkheden voor het detecteren en reageren van eindpunten in Microsoft Defender voor Eindpunt
keywords: Microsoft Defender voor eindpunten, eindpuntdetectie en -antwoord, antwoord, detectie, cyberbeveiliging, beveiliging
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
ms.openlocfilehash: 138a6afde9e8c601fd41811928580644b85bf2e2
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861717"
---
# <a name="overview-of-endpoint-detection-and-response"></a><span data-ttu-id="d9b5f-104">Overzicht van eindpuntdetectie en -antwoord</span><span class="sxs-lookup"><span data-stu-id="d9b5f-104">Overview of endpoint detection and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d9b5f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d9b5f-105">**Applies to:**</span></span>
- [<span data-ttu-id="d9b5f-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="d9b5f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d9b5f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9b5f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d9b5f-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="d9b5f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d9b5f-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="d9b5f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="d9b5f-110">De detectie- en antwoordmogelijkheden van Defender voor eindpunten bieden geavanceerde aanvalsdetecties die bijna realtime zijn en actie kunnen worden ondernomen.</span><span class="sxs-lookup"><span data-stu-id="d9b5f-110">Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="d9b5f-111">Beveiligingsanalisten kunnen waarschuwingen effectief prioriteit geven, zichtbaarheid krijgen in het volledige bereik van een beveiligingsschending en reactieacties ondernemen om bedreigingen te herstellen.</span><span class="sxs-lookup"><span data-stu-id="d9b5f-111">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span>

<span data-ttu-id="d9b5f-112">Wanneer een bedreiging wordt gedetecteerd, worden waarschuwingen gemaakt in het systeem die een analist kan onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="d9b5f-112">When a threat is detected, alerts are created in the system for an analyst to investigate.</span></span> <span data-ttu-id="d9b5f-113">Waarschuwingen met dezelfde aanvalstechnieken of die worden toegeschreven aan dezelfde aanvaller, worden samengevoegd tot een entiteit die een _incident wordt genoemd._</span><span class="sxs-lookup"><span data-stu-id="d9b5f-113">Alerts with the same attack techniques or attributed to the same attacker are aggregated into an entity called an _incident_.</span></span> <span data-ttu-id="d9b5f-114">Door waarschuwingen op deze manier te aggregeren, kunnen analisten gemakkelijk gezamenlijk bedreigingen onderzoeken en beantwoorden.</span><span class="sxs-lookup"><span data-stu-id="d9b5f-114">Aggregating alerts in this manner makes it easy for analysts to collectively investigate and respond to threats.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

<span data-ttu-id="d9b5f-115">Geïnspireerd door de 'assume breach'-denkrichting verzamelt Defender for Endpoint voortdurend gedragsmatige cyber telemetrie.</span><span class="sxs-lookup"><span data-stu-id="d9b5f-115">Inspired by the "assume breach" mindset, Defender for Endpoint continuously collects behavioral cyber telemetry.</span></span> <span data-ttu-id="d9b5f-116">Dit omvat procesgegevens, netwerkactiviteiten, deep optics in de kernel en memory manager, aanmeldingsactiviteiten van gebruikers, wijzigingen in het register en bestandssysteem, en andere.</span><span class="sxs-lookup"><span data-stu-id="d9b5f-116">This includes process information, network activities, deep optics into the kernel and memory manager, user login activities, registry and file system changes, and others.</span></span> <span data-ttu-id="d9b5f-117">De gegevens worden zes maanden opgeslagen, zodat een analist terug in de tijd kan reizen naar het begin van een aanval.</span><span class="sxs-lookup"><span data-stu-id="d9b5f-117">The information is stored for six months, enabling an analyst to travel back in time to the start of an attack.</span></span> <span data-ttu-id="d9b5f-118">De analist kan vervolgens in verschillende weergaven draaien en een onderzoek benaderen via meerdere vectoren.</span><span class="sxs-lookup"><span data-stu-id="d9b5f-118">The analyst can then pivot in various views and approach an investigation through multiple vectors.</span></span>

<span data-ttu-id="d9b5f-119">De antwoordmogelijkheden bieden u de macht om snel bedreigingen te corrigeren door op de betreffende entiteiten te reageren.</span><span class="sxs-lookup"><span data-stu-id="d9b5f-119">The response capabilities give you the power to promptly remediate threats by acting on the affected entities.</span></span>


## <a name="related-topics"></a><span data-ttu-id="d9b5f-120">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d9b5f-120">Related topics</span></span>
- [<span data-ttu-id="d9b5f-121">Dashboard beveiligingsbewerkingen</span><span class="sxs-lookup"><span data-stu-id="d9b5f-121">Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="d9b5f-122">Incidentenwachtrij</span><span class="sxs-lookup"><span data-stu-id="d9b5f-122">Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="d9b5f-123">Waarschuwingenwachtrij</span><span class="sxs-lookup"><span data-stu-id="d9b5f-123">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="d9b5f-124">Lijst met apparaten</span><span class="sxs-lookup"><span data-stu-id="d9b5f-124">Devices list</span></span>](machines-view-overview.md)

