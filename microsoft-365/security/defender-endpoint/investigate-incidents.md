---
title: Incidenten in Microsoft Defender ATP onderzoeken
description: Zie bijbehorende waarschuwingen, beheer het incident en zie metagegevens voor waarschuwingen om een incident te onderzoeken
keywords: onderzoeken, incident, waarschuwingen, metagegevens, risico, detectiebron, beïnvloede apparaten, patronen, correlatie
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5a74da55d733d690cb218c78b87b67d6eba6b9d2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186051"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="b31fa-104">Incidenten in Microsoft Defender voor Eindpunt onderzoeken</span><span class="sxs-lookup"><span data-stu-id="b31fa-104">Investigate incidents in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b31fa-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b31fa-105">**Applies to:**</span></span>
- [<span data-ttu-id="b31fa-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="b31fa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b31fa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b31fa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="b31fa-108">Onderzoeken van incidenten die van invloed zijn op uw netwerk, begrijpen wat ze betekenen en bewijs verzamelen om deze op te lossen.</span><span class="sxs-lookup"><span data-stu-id="b31fa-108">Investigate incidents that affect your network, understand what they mean, and collate evidence to resolve them.</span></span> 

<span data-ttu-id="b31fa-109">Wanneer u een incident onderzoekt, ziet u:</span><span class="sxs-lookup"><span data-stu-id="b31fa-109">When you investigate an incident, you'll see:</span></span>
- <span data-ttu-id="b31fa-110">Details van incidenten</span><span class="sxs-lookup"><span data-stu-id="b31fa-110">Incident details</span></span>
- <span data-ttu-id="b31fa-111">Opmerkingen en acties bij incidenten</span><span class="sxs-lookup"><span data-stu-id="b31fa-111">Incident comments and actions</span></span>
- <span data-ttu-id="b31fa-112">Tabbladen (waarschuwingen, apparaten, onderzoeken, bewijs, grafiek)</span><span class="sxs-lookup"><span data-stu-id="b31fa-112">Tabs (alerts, devices, investigations, evidence, graph)</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUV]


## <a name="analyze-incident-details"></a><span data-ttu-id="b31fa-113">Details van incidenten analyseren</span><span class="sxs-lookup"><span data-stu-id="b31fa-113">Analyze incident details</span></span> 
<span data-ttu-id="b31fa-114">Klik op een incident om het **deelvenster Incident te bekijken.**</span><span class="sxs-lookup"><span data-stu-id="b31fa-114">Click an incident to see the **Incident pane**.</span></span> <span data-ttu-id="b31fa-115">Selecteer **De pagina Incident openen** om de incidentdetails en gerelateerde informatie (waarschuwingen, apparaten, onderzoeken, bewijs, grafiek) te bekijken.</span><span class="sxs-lookup"><span data-stu-id="b31fa-115">Select **Open incident page** to see the incident details and related information (alerts, devices, investigations, evidence, graph).</span></span> 

![Afbeelding van incidentdetails1](images/atp-incident-details.png)

### <a name="alerts"></a><span data-ttu-id="b31fa-117">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="b31fa-117">Alerts</span></span>
<span data-ttu-id="b31fa-118">U kunt de waarschuwingen onderzoeken en zien hoe ze zijn gekoppeld in een incident.</span><span class="sxs-lookup"><span data-stu-id="b31fa-118">You can investigate the alerts and see how they were linked together in an incident.</span></span> <span data-ttu-id="b31fa-119">Waarschuwingen worden gegroepeerd in incidenten op basis van de volgende redenen:</span><span class="sxs-lookup"><span data-stu-id="b31fa-119">Alerts are grouped into incidents based on the following reasons:</span></span>
- <span data-ttu-id="b31fa-120">Geautomatiseerd onderzoek: het geautomatiseerde onderzoek heeft de gekoppelde waarschuwing geactiveerd tijdens het onderzoeken van de oorspronkelijke waarschuwing</span><span class="sxs-lookup"><span data-stu-id="b31fa-120">Automated investigation - The automated investigation triggered the linked alert while investigating the original alert</span></span> 
- <span data-ttu-id="b31fa-121">Bestandskenmerken: de bestanden die aan de waarschuwing zijn gekoppeld, hebben vergelijkbare kenmerken</span><span class="sxs-lookup"><span data-stu-id="b31fa-121">File characteristics - The files associated with the alert have similar characteristics</span></span>
- <span data-ttu-id="b31fa-122">Handmatig koppelen : een gebruiker heeft de waarschuwingen handmatig gekoppeld</span><span class="sxs-lookup"><span data-stu-id="b31fa-122">Manual association - A user manually linked the alerts</span></span>
- <span data-ttu-id="b31fa-123">Tijd proximate - De waarschuwingen zijn binnen een bepaalde periode op hetzelfde apparaat geactiveerd</span><span class="sxs-lookup"><span data-stu-id="b31fa-123">Proximate time - The alerts were triggered on the same device within a certain timeframe</span></span>
- <span data-ttu-id="b31fa-124">Hetzelfde bestand: de bestanden die aan de waarschuwing zijn gekoppeld, zijn exact hetzelfde</span><span class="sxs-lookup"><span data-stu-id="b31fa-124">Same file - The files associated with the alert are exactly the same</span></span>
- <span data-ttu-id="b31fa-125">Dezelfde URL: de URL die de waarschuwing heeft geactiveerd, is exact hetzelfde</span><span class="sxs-lookup"><span data-stu-id="b31fa-125">Same URL - The URL that triggered the alert is exactly the same</span></span>

![Afbeelding van het tabblad Waarschuwingen met de pagina incidentdetails met de redenen waarom de waarschuwingen in dat incident aan elkaar zijn gekoppeld](images/atp-incidents-alerts-reason.png)

<span data-ttu-id="b31fa-127">U kunt ook een waarschuwing beheren en metagegevens voor waarschuwingen bekijken, samen met andere informatie.</span><span class="sxs-lookup"><span data-stu-id="b31fa-127">You can also manage an alert and see alert metadata along with other information.</span></span> <span data-ttu-id="b31fa-128">Zie Waarschuwingen [onderzoeken voor meer informatie.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="b31fa-128">For more information, see [Investigate alerts](investigate-alerts.md).</span></span> 

### <a name="devices"></a><span data-ttu-id="b31fa-129">Apparaten</span><span class="sxs-lookup"><span data-stu-id="b31fa-129">Devices</span></span>
<span data-ttu-id="b31fa-130">U kunt ook de apparaten onderzoeken die deel uitmaken van of gerelateerd zijn aan een bepaald incident.</span><span class="sxs-lookup"><span data-stu-id="b31fa-130">You can also investigate the devices that are part of, or related to, a given incident.</span></span> <span data-ttu-id="b31fa-131">Zie Apparaten [onderzoeken voor meer informatie.](investigate-machines.md)</span><span class="sxs-lookup"><span data-stu-id="b31fa-131">For more information, see [Investigate devices](investigate-machines.md).</span></span>

![Afbeelding van het tabblad Apparaten op pagina met details van incidenten](images/atp-incident-device-tab.png)

### <a name="investigations"></a><span data-ttu-id="b31fa-133">Onderzoeken</span><span class="sxs-lookup"><span data-stu-id="b31fa-133">Investigations</span></span>
<span data-ttu-id="b31fa-134">Selecteer **Onderzoeken om** alle automatische onderzoeken te bekijken die door het systeem zijn gestart in reactie op de incidentenwaarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="b31fa-134">Select **Investigations** to see all the automatic investigations launched by the system in response to the incident alerts.</span></span>

![Afbeelding van het tabblad Onderzoeken in de pagina incidentdetails](images/atp-incident-investigations-tab.png)

## <a name="going-through-the-evidence"></a><span data-ttu-id="b31fa-136">Door het bewijs heen gaan</span><span class="sxs-lookup"><span data-stu-id="b31fa-136">Going through the evidence</span></span>
<span data-ttu-id="b31fa-137">Microsoft Defender voor Eindpunt onderzoekt automatisch alle door incidenten ondersteunde gebeurtenissen en verdachte entiteiten in de waarschuwingen, zodat u automatisch kunt reageren en informatie krijgt over de belangrijke bestanden, processen, services en meer.</span><span class="sxs-lookup"><span data-stu-id="b31fa-137">Microsoft Defender for Endpoint automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, and more.</span></span> 

<span data-ttu-id="b31fa-138">Elk van de geanalyseerde entiteiten wordt gemarkeerd als geïnfecteerd, gesaneerd of verdacht.</span><span class="sxs-lookup"><span data-stu-id="b31fa-138">Each of the analyzed entities will be marked as infected, remediated, or suspicious.</span></span> 

![Afbeelding van het tabblad Bewijs in de pagina incidentdetails](images/atp-incident-evidence-tab.png)

## <a name="visualizing-associated-cybersecurity-threats"></a><span data-ttu-id="b31fa-140">Bijbehorende cyberbeveiligingsdreigingen visualiseren</span><span class="sxs-lookup"><span data-stu-id="b31fa-140">Visualizing associated cybersecurity threats</span></span> 
<span data-ttu-id="b31fa-141">Met Microsoft Defender voor Eindpunt worden de bedreigingsgegevens samengevoegd tot een incident, zodat u de patronen en correlaties kunt zien die afkomstig zijn van verschillende gegevenspunten.</span><span class="sxs-lookup"><span data-stu-id="b31fa-141">Microsoft Defender for Endpoint aggregates the threat information into an incident so you can see the patterns and correlations coming in from various data points.</span></span> <span data-ttu-id="b31fa-142">U kunt een dergelijke correlatie bekijken via de incidentgrafiek.</span><span class="sxs-lookup"><span data-stu-id="b31fa-142">You can view such correlation through the incident graph.</span></span>

### <a name="incident-graph"></a><span data-ttu-id="b31fa-143">Incidentgrafiek</span><span class="sxs-lookup"><span data-stu-id="b31fa-143">Incident graph</span></span>
<span data-ttu-id="b31fa-144">The **Graph** vertelt het verhaal van de cyberbeveiligingsaanval.</span><span class="sxs-lookup"><span data-stu-id="b31fa-144">The **Graph** tells the story of the cybersecurity attack.</span></span> <span data-ttu-id="b31fa-145">U ziet bijvoorbeeld wat het invoerpunt was, welke indicator voor compromissen of activiteit is waargenomen op welk apparaat.</span><span class="sxs-lookup"><span data-stu-id="b31fa-145">For example, it shows you what was the entry point, which indicator of compromise or activity was observed on which device.</span></span> <span data-ttu-id="b31fa-146">etc.</span><span class="sxs-lookup"><span data-stu-id="b31fa-146">etc.</span></span>

![Afbeelding van de incidentgrafiek](images/atp-incident-graph-tab.png)

<span data-ttu-id="b31fa-148">U kunt op de cirkels in de incidentgrafiek klikken om de details van de schadelijke bestanden, bijbehorende bestandsdetecties, hoeveel exemplaren er wereldwijd zijn geweest, of deze zijn waargenomen in uw organisatie, zo ja, hoeveel exemplaren.</span><span class="sxs-lookup"><span data-stu-id="b31fa-148">You can click the circles on the incident graph to view the details of the malicious files, associated file detections, how many instances have there been worldwide, whether it’s been observed in your organization, if so, how many instances.</span></span>

![Afbeelding van incidentdetails](images/atp-incident-graph-details.png)

## <a name="related-topics"></a><span data-ttu-id="b31fa-150">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b31fa-150">Related topics</span></span>
- [<span data-ttu-id="b31fa-151">Wachtrij incidenten</span><span class="sxs-lookup"><span data-stu-id="b31fa-151">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="b31fa-152">Incidenten in Microsoft Defender voor Eindpunt onderzoeken</span><span class="sxs-lookup"><span data-stu-id="b31fa-152">Investigate incidents in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-incidents)
- [<span data-ttu-id="b31fa-153">Microsoft Defender voor eindpuntincidenten beheren</span><span class="sxs-lookup"><span data-stu-id="b31fa-153">Manage Microsoft Defender for Endpoint incidents</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-incidents)
