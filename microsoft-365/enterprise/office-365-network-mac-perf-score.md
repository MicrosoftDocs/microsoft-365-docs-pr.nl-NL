---
title: Microsoft 365-netwerk beoordeling (preview)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365-netwerk beoordeling (preview)
ms.openlocfilehash: aacbdf73da9552a12bde250e51544f1de533637c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695738"
---
# <a name="microsoft-365-network-assessment-preview"></a><span data-ttu-id="35fa1-103">Microsoft 365-netwerk beoordeling (preview)</span><span class="sxs-lookup"><span data-stu-id="35fa1-103">Microsoft 365 network assessment (preview)</span></span>

<span data-ttu-id="35fa1-104">In het Microsoft 365-Beheercentrum 365 kunt u met de **netwerk beoordelingen** een samenvatting van tal van de prestaties van de netwerkprestaties in een momentopname van uw Enterprise-netwerkstatus weergeven die wordt weergegeven door een punten waarde van 1-100.</span><span class="sxs-lookup"><span data-stu-id="35fa1-104">In the Microsoft 365 Admin Center's Connectivity to Microsoft 365 page, **network assessments** distill an aggregate of many network performance metrics into a snapshot of your enterprise network health, represented by a points value from 1 - 100.</span></span> <span data-ttu-id="35fa1-105">Netwerk beoordelingen zijn beperkt tot de gehele Tenant en voor elke geografische locatie van de gebruikers die verbinding maken met uw Tenant, zodat Microsoft 365-beheerders een eenvoudige manier is om een Gestalt van de netwerkstatus van de onderneming te begrijpt en snel een uitzoomen op een gedetailleerd overzicht van een wereldwijd kantoor.</span><span class="sxs-lookup"><span data-stu-id="35fa1-105">Network assessments are scoped to both the entire tenant and for each geographic location from which users connect to your tenant, providing Microsoft 365 administrators with an easy way to instantly grasp a gestalt of the enterprise's network health and quickly drill down into a detailed report for any global office location.</span></span>

<span data-ttu-id="35fa1-106">De waarde van het netwerkbeoordelings punt is een gemiddelde tijdsinstelling voor latentie, bandbreedte, downloadsnelheid en hoeveelheid verbindingskwaliteit, gecompileerd Live op het moment dat ze worden bekeken.</span><span class="sxs-lookup"><span data-stu-id="35fa1-106">The network assessment points value is an average measurement of latency, bandwidth, download speed and connection quality metrics compiled live at the time they are viewed.</span></span> <span data-ttu-id="35fa1-107">Prestatiegegevens voor Microsoft-netwerken zijn uitgesloten van deze waarden, om ervoor te zorgen dat de beoordelings resultaten ondubbelzinnig en specifiek zijn voor het bedrijfsnetwerk.</span><span class="sxs-lookup"><span data-stu-id="35fa1-107">Performance metrics for Microsoft-owned networks are excluded from these measurements to ensure that assessment results are unambiguous and specific to the corporate network.</span></span>

![Waarde van netwerk beoordeling](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

<span data-ttu-id="35fa1-109">Een zeer lage waarde voor de beoordeling van een netwerk adviseert dat Microsoft 365-clients grote problemen hebben met de Tenant of de gebruikerservaring van een reactie houdt, terwijl een hoge waarde een correct geconfigureerd netwerk aangeeft met enkele voortdurende prestatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="35fa1-109">A very low network assessment value suggests that Microsoft 365 clients will have significant problems connecting to the tenant or maintaining a responsive user experience, while a high value indicates a properly configured network with few ongoing performance issues.</span></span> <span data-ttu-id="35fa1-110">Een waarde van 80% vertegenwoordigt een gezonde basislijn waarbij u geen normale klachten over de Microsoft 365-verbinding of-antwoord moet ontvangen vanwege de netwerkprestaties.</span><span class="sxs-lookup"><span data-stu-id="35fa1-110">A value of 80% represents a healthy baseline where you should not expect to receive regular user complaints about Microsoft 365 connectivity or responsiveness due to network performance.</span></span> <span data-ttu-id="35fa1-111">Aangezien er steeds meer verbeteringen in de netwerkverbinding worden aangebracht, zal deze waarde toenemen samen met de gebruikerservaring.</span><span class="sxs-lookup"><span data-stu-id="35fa1-111">As iterative network connectivity improvements are made, this value will increase along with user experience.</span></span>

>[!IMPORTANT]
><span data-ttu-id="35fa1-112">Netwerk inzichten, prestatie aanbevelingen en beoordelingen in het Microsoft 365-Beheercentrum is momenteel in de preview-versie en is alleen beschikbaar voor Microsoft 365-tenants die zijn geregistreerd in het functie voorbeeldprogramma.</span><span class="sxs-lookup"><span data-stu-id="35fa1-112">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="network-assessment-panel"></a><span data-ttu-id="35fa1-113">Deelvenster netwerk beoordeling</span><span class="sxs-lookup"><span data-stu-id="35fa1-113">Network assessment panel</span></span>

<span data-ttu-id="35fa1-114">Elke beoordeling van een netwerk, of het bereik van de Tenant of een specifieke kantoorlocatie, een deelvenster toont met details over de beoordeling.</span><span class="sxs-lookup"><span data-stu-id="35fa1-114">Each network assessment, whether scoped to the tenant or to a specific office location, shows a panel with details about the assessment.</span></span> <span data-ttu-id="35fa1-115">Dit deelvenster toont een staafdiagram van de beoordeling, zowel als een percentage, als het totaal aantal punten voor elk onderdeel dat de hoeveelheid werkbelasting omvat, waaronder alleen werkbelastingen waarop meetgegevens zijn ontvangen.</span><span class="sxs-lookup"><span data-stu-id="35fa1-115">This panel shows a bar chart of the assessment both as a percentage and as the total points for each component workload including only workloads where measurement data was received.</span></span> <span data-ttu-id="35fa1-116">Voor een netwerklocatie netwerk beoordeling wordt ook een bench type weergegeven dat de mediaan is van alle Microsoft 365-clients die gegevens hebben gerapporteerd in dezelfde plaats als uw kantoorlocatie.</span><span class="sxs-lookup"><span data-stu-id="35fa1-116">For an office location network assessment, we also show a benchmark which is the median of all Microsoft 365 clients that reported data in the same city as your office location.</span></span>

![Voorbeeld van netwerk beoordeling](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

<span data-ttu-id="35fa1-118">In **het deelvenster analyse wordt** de beoordeling voor elk van de onderdelen van het onderdeel weergegeven.</span><span class="sxs-lookup"><span data-stu-id="35fa1-118">The **Assessment breakdown** in the panel shows the assessment for each of the component workloads.</span></span>

<span data-ttu-id="35fa1-119">De **beoordelings geschiedenis** toont de afgelopen 30 dagen van de beoordeling en de benchte.</span><span class="sxs-lookup"><span data-stu-id="35fa1-119">The **Assessment history** shows the past 30 days of the assessment and the benchmark.</span></span>

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a><span data-ttu-id="35fa1-120">Inspecties van Tenant netwerkbeoordelingen en netwerk beoordelingen van Office-locaties</span><span class="sxs-lookup"><span data-stu-id="35fa1-120">Tenant network assessments and office location network assessments</span></span>

<span data-ttu-id="35fa1-121">Een netwerkbeoordeling meet de opzet van de netwerkverbinding van een kantoorlocatie naar het netwerk van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="35fa1-121">A network assessment measures the design of the network perimeter of an office location to Microsoft's network.</span></span> <span data-ttu-id="35fa1-122">De verbeteringen aan de netwerkverbinding kunt u het beste uitvoeren op elke kantoorlocatie, of als de netwerkverbinding is geaggregeerd, zijn er mogelijk verbeteringen die van invloed zijn op meerdere locaties.</span><span class="sxs-lookup"><span data-stu-id="35fa1-122">Improvements to the network perimeter is best done at each office location, or where network connectivity is aggregated there may be improvements that impact multiple locations.</span></span>

<span data-ttu-id="35fa1-123">We tonen een netwerkassessmentwaarde voor de gehele Microsoft 365-Tenant op de pagina netwerkprestaties en een specifieke waarde voor elke gedetecteerde Office-locatie op de samenvattings pagina van die locatie.</span><span class="sxs-lookup"><span data-stu-id="35fa1-123">We show a network assessment value for the whole Microsoft 365 tenant on the network performance overview page and a specific value for each detected office location on that location's summary page.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="35fa1-124">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="35fa1-124">Exchange Online</span></span>

<span data-ttu-id="35fa1-125">Voor Exchange Online wordt de TCP-latentie van de clientcomputer naar de front-end-server van Exchange gemeten.</span><span class="sxs-lookup"><span data-stu-id="35fa1-125">For Exchange Online the TCP latency from the client machine to the Exchange front end server is measured.</span></span> <span data-ttu-id="35fa1-126">Dit kan van invloed zijn op de afstand tussen het netwerk en het LAN en WAN van klanten.</span><span class="sxs-lookup"><span data-stu-id="35fa1-126">This can be impacted by the distance the network travels over the customers LAN and WAN.</span></span> <span data-ttu-id="35fa1-127">Het kan ook worden beïnvloed door de netwerk-of bewerkings apparatuur of de service die de verbinding vertraagt of dat pakketten worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="35fa1-127">It can also be impacted by network intermediary devices or services which delay the connectivity or cause packets to be resent.</span></span>

## <a name="sharepoint-online"></a><span data-ttu-id="35fa1-128">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="35fa1-128">SharePoint Online</span></span>

<span data-ttu-id="35fa1-129">Voor SharePoint Online is de beschikbare downloadsnelheid voor een gebruiker voor toegang tot een document gemeten.</span><span class="sxs-lookup"><span data-stu-id="35fa1-129">For SharePoint Online the download speed available for a user to access a document is measured.</span></span> <span data-ttu-id="35fa1-130">Dit kan van invloed zijn op de bandbreedte voor netwerk circuits van de clientcomputer en van het Microsoft-netwerk.</span><span class="sxs-lookup"><span data-stu-id="35fa1-130">This can be impacted by the bandwidth available on network circuits between the client machine and Microsoft's network.</span></span> <span data-ttu-id="35fa1-131">Dit wordt vaak beïnvloed door netwerkcongestie die zich bevindt bij knelpunten in ingewikkelde netwerkapparaten of in de WiFi-gebieden met weinig behoefte.</span><span class="sxs-lookup"><span data-stu-id="35fa1-131">It is also often impacted by network congestion that exists in bottlenecks in complex network devices or in poor coverage Wi-Fi areas.</span></span>

## <a name="microsoft-teams"></a><span data-ttu-id="35fa1-132">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="35fa1-132">Microsoft Teams</span></span>

<span data-ttu-id="35fa1-133">De netwerkkwaliteit voor Microsoft teams wordt gemeten als UDP-latentie, UDP-jitter en UDP-pakketverlies.</span><span class="sxs-lookup"><span data-stu-id="35fa1-133">For Microsoft Teams the Network quality is measured as UDP latency, UDP jitter, and UDP packet loss.</span></span> <span data-ttu-id="35fa1-134">UDP wordt gebruikt voor bellen en vergaderen via audio-en videoverbinding voor Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="35fa1-134">UDP is used for call and conferencing audio and video media connectivity for Microsoft Teams.</span></span> <span data-ttu-id="35fa1-135">Dit kan van invloed zijn op het moment dat de latentie en de downloadsnelheid van invloed zijn op de latentie en de downloadsnelheid, aangezien UDP voor de ondersteuning van de UDP apart is geconfigureerd voor het meer gangbare TCP-protocol.</span><span class="sxs-lookup"><span data-stu-id="35fa1-135">This can be impacted by the same factors as for latency and download speed in addition to connectivity gaps in a network's UDP support since UDP is configured separately to the more common TCP protocol.</span></span>

## <a name="related-topics"></a><span data-ttu-id="35fa1-136">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="35fa1-136">Related topics</span></span>

[<span data-ttu-id="35fa1-137">Aanbevelingen voor netwerkprestaties in het Microsoft 365-Beheercentrum (preview)</span><span class="sxs-lookup"><span data-stu-id="35fa1-137">Network performance recommendations in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="35fa1-138">Microsoft 365 Network Performance Insights (preview)</span><span class="sxs-lookup"><span data-stu-id="35fa1-138">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="35fa1-139">Microsoft 365 connectiviteitstest in het M365-Beheercentrum (preview)</span><span class="sxs-lookup"><span data-stu-id="35fa1-139">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="35fa1-140">Locatie Services voor Microsoft 365-netwerkconnectiviteit</span><span class="sxs-lookup"><span data-stu-id="35fa1-140">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
