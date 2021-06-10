---
title: Microsoft Defender-beveiligingscentrum Dashboard Beveiligingsbewerkingen
description: Gebruik het dashboard om risicovolle apparaten te identificeren, de status van de service bij te houden en statistieken en informatie over apparaten en waarschuwingen te bekijken.
keywords: dashboard, waarschuwingen, nieuw, in uitvoering, opgelost, risico, apparaten met risico, infecties, rapportage, statistieken, grafieken, grafieken, gezondheid, actieve malwaredetecties, bedreigingscategorie, categorieën, wachtwoord stealer, ransomware, exploit, bedreiging, lage ernst, actieve malware
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
ms.openlocfilehash: bfa23138b1bab4abcdfa0b4b9d689a4a4cfc7fc1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058718"
---
# <a name="microsoft-defender-security-center-security-operations-dashboard"></a><span data-ttu-id="f9f1a-104">Microsoft Defender-beveiligingscentrum Dashboard Beveiligingsbewerkingen</span><span class="sxs-lookup"><span data-stu-id="f9f1a-104">Microsoft Defender Security Center Security operations dashboard</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f9f1a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f9f1a-105">**Applies to:**</span></span>
- [<span data-ttu-id="f9f1a-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f9f1a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="f9f1a-107">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f9f1a-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f9f1a-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 

<span data-ttu-id="f9f1a-109">In **het dashboard Beveiligingsbewerkingen** worden eindpuntdetectie en -respons functies opgedoken.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-109">The **Security operations dashboard** is where the endpoint detection and response capabilities are surfaced.</span></span> <span data-ttu-id="f9f1a-110">Het biedt een overzicht op hoog niveau van waar detecties zijn gezien en markeert waar reactieacties nodig zijn.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-110">It provides a high level overview of where detections were seen and highlights where response actions are needed.</span></span> 

<span data-ttu-id="f9f1a-111">In het dashboard ziet u een momentopname van:</span><span class="sxs-lookup"><span data-stu-id="f9f1a-111">The dashboard displays a snapshot of:</span></span>

- <span data-ttu-id="f9f1a-112">Actieve waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="f9f1a-112">Active alerts</span></span>
- <span data-ttu-id="f9f1a-113">Apparaten met risico</span><span class="sxs-lookup"><span data-stu-id="f9f1a-113">Devices at risk</span></span>
- <span data-ttu-id="f9f1a-114">Sensortoestand</span><span class="sxs-lookup"><span data-stu-id="f9f1a-114">Sensor health</span></span>
- <span data-ttu-id="f9f1a-115">Servicestatus</span><span class="sxs-lookup"><span data-stu-id="f9f1a-115">Service health</span></span>
- <span data-ttu-id="f9f1a-116">Rapportage van dagelijkse apparaten</span><span class="sxs-lookup"><span data-stu-id="f9f1a-116">Daily devices reporting</span></span>
- <span data-ttu-id="f9f1a-117">Actieve geautomatiseerde onderzoeken</span><span class="sxs-lookup"><span data-stu-id="f9f1a-117">Active automated investigations</span></span>
- <span data-ttu-id="f9f1a-118">Statistieken van geautomatiseerde onderzoeken</span><span class="sxs-lookup"><span data-stu-id="f9f1a-118">Automated investigations statistics</span></span>
- <span data-ttu-id="f9f1a-119">Gebruikers met risico</span><span class="sxs-lookup"><span data-stu-id="f9f1a-119">Users at risk</span></span>
- <span data-ttu-id="f9f1a-120">Verdachte activiteiten</span><span class="sxs-lookup"><span data-stu-id="f9f1a-120">Suspicious activities</span></span>


![Afbeelding van het dashboard Beveiligingsbewerkingen](images/atp-sec-ops-dashboard.png)

<span data-ttu-id="f9f1a-122">U kunt waarschuwingen en apparaten verkennen en onderzoeken om snel te bepalen of, waar en wanneer verdachte activiteiten hebben plaatsgevonden in uw netwerk om u te helpen de context te begrijpen waarin ze zich hebben voorgedaan.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-122">You can explore and investigate alerts and devices to quickly determine if, where, and when suspicious activities occurred in your network to help you understand the context they appeared in.</span></span>

<span data-ttu-id="f9f1a-123">In het **dashboard Beveiligingsbewerkingen** ziet u samengevoegde gebeurtenissen om belangrijke gebeurtenissen of gedragingen op een apparaat te identificeren.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-123">From the **Security operations dashboard** you will see aggregated events to facilitate the identification of significant events or behaviors on a device.</span></span> <span data-ttu-id="f9f1a-124">U kunt ook inzoomen op gedetailleerde gebeurtenissen en indicatoren op laag niveau.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-124">You can also drill down into granular events and low-level indicators.</span></span>

<span data-ttu-id="f9f1a-125">Het bevat ook klikbare tegels die visuele aanwijzingen geven over de algehele status van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-125">It also has clickable tiles that give visual cues on the overall health state of your organization.</span></span> <span data-ttu-id="f9f1a-126">Elke tegel opent een gedetailleerde weergave van het bijbehorende overzicht.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-126">Each tile opens a detailed view of the corresponding overview.</span></span>

## <a name="active-alerts"></a><span data-ttu-id="f9f1a-127">Actieve waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="f9f1a-127">Active alerts</span></span>
<span data-ttu-id="f9f1a-128">U kunt het totale aantal actieve waarschuwingen van de afgelopen 30 dagen in uw netwerk bekijken via de tegel.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-128">You can view the overall number of active alerts from the last 30 days in your network from the tile.</span></span> <span data-ttu-id="f9f1a-129">Waarschuwingen worden gegroepeerd in **Nieuw** en **In uitvoering.**</span><span class="sxs-lookup"><span data-stu-id="f9f1a-129">Alerts are grouped into **New** and **In progress**.</span></span>

![Klik op elk segment of de ernst om een lijst met waarschuwingen van de afgelopen 30 dagen weer te geven](images/active-alerts-tile.png)

<span data-ttu-id="f9f1a-131">Elke groep wordt verder gecategoriseerd in de bijbehorende ernst van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-131">Each group is further sub-categorized into their corresponding alert severity levels.</span></span> <span data-ttu-id="f9f1a-132">Klik op het aantal waarschuwingen in elke waarschuwingsring om een gesorteerde weergave van de wachtrij van die categorie te zien (**Nieuw** of **In uitvoering**).</span><span class="sxs-lookup"><span data-stu-id="f9f1a-132">Click the number of alerts inside each alert ring to see a sorted view of that category's queue (**New** or **In progress**).</span></span>

<span data-ttu-id="f9f1a-133">Zie Overzicht waarschuwingen voor [meer informatie.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="f9f1a-133">For more information see, [Alerts overview](alerts-queue.md).</span></span>

<span data-ttu-id="f9f1a-134">Elke rij bevat een waarschuwingscategorie en een korte beschrijving van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-134">Each row includes an alert severity category and a short description of the alert.</span></span> <span data-ttu-id="f9f1a-135">U kunt op een waarschuwing klikken om de gedetailleerde weergave te bekijken.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-135">You can click an alert to see its detailed view.</span></span> <span data-ttu-id="f9f1a-136">Zie Microsoft [Defender onderzoeken voor](investigate-alerts.md) eindpuntwaarschuwingen en waarschuwingenoverzicht voor meer [informatie.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="f9f1a-136">For more information see,  [Investigate Microsoft Defender for Endpoint alerts](investigate-alerts.md) and [Alerts overview](alerts-queue.md).</span></span>


## <a name="devices-at-risk"></a><span data-ttu-id="f9f1a-137">Apparaten met risico</span><span class="sxs-lookup"><span data-stu-id="f9f1a-137">Devices at risk</span></span>
<span data-ttu-id="f9f1a-138">Deze tegel toont een lijst met apparaten met het hoogste aantal actieve waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-138">This tile shows you a list of devices with the highest number of active alerts.</span></span> <span data-ttu-id="f9f1a-139">Het totale aantal waarschuwingen voor elk apparaat wordt weergegeven in een cirkel naast de naam van het apparaat en vervolgens verder gecategoriseerd op ernstsniveaus aan het einde van de tegel (plaats de muisaanwijzer op elke ernstbalk om het label te zien).</span><span class="sxs-lookup"><span data-stu-id="f9f1a-139">The total number of alerts for each device is shown in a circle next to the device name, and then further categorized by severity levels at the far end of the tile (hover over each severity bar to see its label).</span></span>

![De tegel Apparaten met risico toont een lijst met apparaten met het hoogste aantal waarschuwingen en een uitsplitsing van de ernst van de waarschuwingen](images/devices-at-risk-tile.png)

<span data-ttu-id="f9f1a-141">Klik op de naam van het apparaat om details over dat apparaat te zien.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-141">Click the name of the device to see details about that device.</span></span> <span data-ttu-id="f9f1a-142">Zie Apparaten onderzoeken in de lijst [Microsoft Defender voor eindpuntapparaten](investigate-machines.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-142">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

<span data-ttu-id="f9f1a-143">U kunt ook **boven** aan de tegel op De lijst Apparaten klikken om rechtstreeks naar de lijst Apparaten te **gaan,** gesorteerd op het aantal actieve waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-143">You can also click **Devices list** at the top of the tile to go directly to the **Devices list**, sorted by the number of active alerts.</span></span> <span data-ttu-id="f9f1a-144">Zie Apparaten onderzoeken in de lijst [Microsoft Defender voor eindpuntapparaten](investigate-machines.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-144">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

## <a name="devices-with-sensor-issues"></a><span data-ttu-id="f9f1a-145">Apparaten met sensorproblemen</span><span class="sxs-lookup"><span data-stu-id="f9f1a-145">Devices with sensor issues</span></span>
<span data-ttu-id="f9f1a-146">De **tegel Apparaten met sensorproblemen** bevat informatie over de mogelijkheid van het afzonderlijke apparaat om sensorgegevens te verstrekken aan de Microsoft Defender voor Eindpunt-service.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-146">The **Devices with sensor issues** tile provides information on the individual device’s ability to provide sensor data to the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="f9f1a-147">Het rapport geeft aan hoeveel apparaten aandacht nodig hebben en helpt u bij het identificeren van problematische apparaten.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-147">It reports how many devices require attention and helps you identify problematic devices.</span></span>

![Apparaten met sensorproblemen tegel](images/atp-tile-sensor-health.png)

<span data-ttu-id="f9f1a-149">Er zijn twee statusindicatoren die informatie geven over het aantal apparaten dat niet correct rapporteert aan de service:</span><span class="sxs-lookup"><span data-stu-id="f9f1a-149">There are two status indicators that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="f9f1a-150">**Verkeerd geconfigureerd:** deze apparaten rapporteren mogelijk gedeeltelijk sensorgegevens aan de Microsoft Defender voor Eindpunt-service en hebben mogelijk configuratiefouten die moeten worden gecorrigeerd.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-150">**Misconfigured** – These devices might partially be reporting sensor data to the Microsoft Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="f9f1a-151">**Inactief:** apparaten die de afgelopen maand meer dan zeven dagen zijn gestopt met rapporteren aan de Microsoft Defender for Endpoint-service.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-151">**Inactive** - Devices that have stopped reporting to the Microsoft Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="f9f1a-152">Wanneer u op een van de groepen klikt, wordt u doorgestuurd naar de lijst met apparaten, gefilterd op basis van uw keuze.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-152">When you click any of the groups, you’ll be directed to devices list, filtered according to your choice.</span></span> <span data-ttu-id="f9f1a-153">Zie Sensortoestand controleren [en](check-sensor-status.md) Apparaten onderzoeken voor meer [informatie.](investigate-machines.md)</span><span class="sxs-lookup"><span data-stu-id="f9f1a-153">For more information, see [Check sensor state](check-sensor-status.md) and [Investigate devices](investigate-machines.md).</span></span>

## <a name="service-health"></a><span data-ttu-id="f9f1a-154">Servicestatus</span><span class="sxs-lookup"><span data-stu-id="f9f1a-154">Service health</span></span>
<span data-ttu-id="f9f1a-155">De **tegel Service** status informeert u of de service actief is of als er problemen zijn.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-155">The **Service health** tile informs you if the service is active or if there are issues.</span></span>

![De tegel Servicestatus geeft een algemene indicator van de service weer](images/status-tile.png)

<span data-ttu-id="f9f1a-157">Zie De service health van Microsoft Defender voor eindpunten controleren voor meer informatie over [de service-status.](service-status.md)</span><span class="sxs-lookup"><span data-stu-id="f9f1a-157">For more information on the service health, see [Check the Microsoft Defender for Endpoint service health](service-status.md).</span></span>


## <a name="daily-devices-reporting"></a><span data-ttu-id="f9f1a-158">Rapportage van dagelijkse apparaten</span><span class="sxs-lookup"><span data-stu-id="f9f1a-158">Daily devices reporting</span></span>
<span data-ttu-id="f9f1a-159">De **rapportagetegel Dagelijkse** apparaten toont een staafdiagram dat het aantal apparaten vertegenwoordigt dat dagelijks rapporteert in de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-159">The **Daily devices reporting** tile shows a bar graph that represents the number of devices reporting daily in the last 30 days.</span></span> <span data-ttu-id="f9f1a-160">Plaats de muisaanwijzer op afzonderlijke balken in de grafiek om het exacte aantal apparaten te zien dat elke dag wordt gemeld.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-160">Hover over individual bars on the graph to see the exact number of devices reporting in each day.</span></span>

![Afbeelding van de tegel rapportage van dagelijkse apparaten](images/atp-daily-devices-reporting.png)


## <a name="active-automated-investigations"></a><span data-ttu-id="f9f1a-162">Actieve geautomatiseerde onderzoeken</span><span class="sxs-lookup"><span data-stu-id="f9f1a-162">Active automated investigations</span></span>
<span data-ttu-id="f9f1a-163">U kunt het totale aantal automatische onderzoeken van de afgelopen 30 dagen in uw netwerk bekijken via de tegel **Actieve automatische onderzoeken.**</span><span class="sxs-lookup"><span data-stu-id="f9f1a-163">You can view the overall number of automated investigations from the last 30 days in your network from the **Active automated investigations** tile.</span></span> <span data-ttu-id="f9f1a-164">Onderzoeken worden gegroepeerd in actie in **behandeling,** **wachten op apparaat** en **Uitvoeren.**</span><span class="sxs-lookup"><span data-stu-id="f9f1a-164">Investigations are grouped into **Pending action**, **Waiting for device**, and **Running**.</span></span>

![Inmage van actieve geautomatiseerde onderzoeken](images/atp-active-investigations-tile.png)


## <a name="automated-investigations-statistics"></a><span data-ttu-id="f9f1a-166">Statistieken van geautomatiseerde onderzoeken</span><span class="sxs-lookup"><span data-stu-id="f9f1a-166">Automated investigations statistics</span></span>
<span data-ttu-id="f9f1a-167">Deze tegel bevat statistieken over geautomatiseerde onderzoeken in de afgelopen zeven dagen.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-167">This tile shows statistics related to automated investigations in the last seven days.</span></span> <span data-ttu-id="f9f1a-168">Het toont het aantal voltooide onderzoeken, het aantal opgeloste onderzoeken, de gemiddelde in behandeling zijnde tijd die nodig is voor het starten van een onderzoek, de gemiddelde tijd die nodig is om een waarschuwing te corrigeren, het aantal onderzochte waarschuwingen en het aantal uren automatisering dat is opgeslagen in een normaal handmatig onderzoek.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-168">It shows the number of investigations completed, the number of successfully remediated investigations, the average pending time it takes for an investigation to be initiated, the average time it takes to remediate an alert, the number of alerts investigated, and the number of hours of automation saved from a typical manual investigation.</span></span> 

![Afbeelding van geautomatiseerde onderzoeksstatistieken](images/atp-automated-investigations-statistics.png)

<span data-ttu-id="f9f1a-170">U kunt klikken op Automatische **onderzoeken,** **opgeloste** onderzoeken en waarschuwingen  die zijn onderzocht om naar de pagina Onderzoeken te gaan, gefilterd op de juiste categorie. </span><span class="sxs-lookup"><span data-stu-id="f9f1a-170">You can click on **Automated investigations**, **Remediated investigations**, and **Alerts investigated** to navigate to the **Investigations** page, filtered by the appropriate category.</span></span> <span data-ttu-id="f9f1a-171">Op deze manier kunt u een gedetailleerde uitsplitsing van onderzoeken in de context zien.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-171">This lets you see a detailed breakdown of investigations in context.</span></span>

## <a name="users-at-risk"></a><span data-ttu-id="f9f1a-172">Gebruikers met risico</span><span class="sxs-lookup"><span data-stu-id="f9f1a-172">Users at risk</span></span>
<span data-ttu-id="f9f1a-173">De tegel toont een lijst met gebruikersaccounts met de meest actieve waarschuwingen en het aantal waarschuwingen dat wordt weergegeven op hoge, gemiddelde of lage waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-173">The tile shows you a list of user accounts with the most active alerts and the number of alerts seen on high, medium, or low alerts.</span></span> 

![Tegel Gebruikersaccounts met risico toont een lijst met gebruikersaccounts met het hoogste aantal waarschuwingen en een uitsplitsing van de ernst van de waarschuwingen](images/atp-users-at-risk.png)

<span data-ttu-id="f9f1a-175">Klik op het gebruikersaccount voor meer informatie over het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-175">Click the user account to see details about the user account.</span></span> <span data-ttu-id="f9f1a-176">Zie Een gebruikersaccount [onderzoeken voor meer informatie.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="f9f1a-176">For more information see [Investigate a user account](investigate-user.md).</span></span>

><span data-ttu-id="f9f1a-177">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f9f1a-177">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f9f1a-178">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="f9f1a-178">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="f9f1a-179">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f9f1a-179">Related topics</span></span>
- [<span data-ttu-id="f9f1a-180">De Microsoft Defender for Endpoint-portal begrijpen</span><span class="sxs-lookup"><span data-stu-id="f9f1a-180">Understand the Microsoft Defender for Endpoint portal</span></span>](use.md)
- [<span data-ttu-id="f9f1a-181">Portaloverzicht</span><span class="sxs-lookup"><span data-stu-id="f9f1a-181">Portal overview</span></span>](portal-overview.md)
- [<span data-ttu-id="f9f1a-182">Het dashboard Threat & Vulnerability Management weergeven</span><span class="sxs-lookup"><span data-stu-id="f9f1a-182">View the Threat & Vulnerability Management dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="f9f1a-183">Het dashboard Bedreigingsanalyse bekijken en aanbevolen mitigatieacties uitvoeren</span><span class="sxs-lookup"><span data-stu-id="f9f1a-183">View the Threat analytics dashboard and take recommended mitigation actions</span></span>](threat-analytics.md)
