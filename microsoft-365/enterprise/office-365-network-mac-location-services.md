---
title: Locatie Services voor Microsoft 365-netwerkconnectiviteit
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Locatie Services voor Microsoft 365-netwerkconnectiviteit
ms.openlocfilehash: f2ab872f67eca70ab2791d3ad6fe1396b009cc18
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200779"
---
# <a name="microsoft-365-network-connectivity-location-services-preview"></a><span data-ttu-id="b3a29-103">Locatie Services voor Microsoft 365-netwerkconnectiviteit</span><span class="sxs-lookup"><span data-stu-id="b3a29-103">Microsoft 365 Network Connectivity Location Services (preview)</span></span>

<span data-ttu-id="b3a29-104">In het Microsoft 365-Beheercentrum ziet u nu de **aanbevelingen voor netwerk inzichten en prestaties**, die metrische gegevens van een dynamische prestaties van uw microsoft 365-Tenant verzamelen en alleen kunnen worden weergegeven door beheerders gebruikers in uw Tenant.</span><span class="sxs-lookup"><span data-stu-id="b3a29-104">The Microsoft 365 Admin Center now shows **Network Insights and performance recommendations**, which are live performance metrics collected from your Microsoft 365 tenant and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="b3a29-105">De netwerkverbinding van de organisatie is ontwikkeld via een netwerklocatie op het internet.</span><span class="sxs-lookup"><span data-stu-id="b3a29-105">Organizational network connectivity is designed per office location through a network egress location to the Internet.</span></span> <span data-ttu-id="b3a29-106">Microsoft 365-clientconnectiviteit maakt gebruik van die route en vervolgens op internet naar Microsoft-server voor Microsoft-deur.</span><span class="sxs-lookup"><span data-stu-id="b3a29-106">Microsoft 365 client connectivity uses that route and then across the Internet to Microsoft service front door servers.</span></span> <span data-ttu-id="b3a29-107">Het identificeren van Office-locaties is de sleutel om deze netwerk inzichten te kunnen weergeven.</span><span class="sxs-lookup"><span data-stu-id="b3a29-107">Identifying office locations is key to being able to show these network insights.</span></span>

## <a name="location-in-network-measurements"></a><span data-ttu-id="b3a29-108">Locatie in netwerk afmetingen</span><span class="sxs-lookup"><span data-stu-id="b3a29-108">Location in network measurements</span></span>

<span data-ttu-id="b3a29-109">De beheerder van een organisatie kan zich afmelden voor de locatie die moet worden opgenomen in de netwerk metingen die door deze functie worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b3a29-109">An organization's administrator can opt in for location to be included in the network measurements used by this feature.</span></span> <span data-ttu-id="b3a29-110">Hiermee kunt u automatisch opsporen van de plaats waar u Office bevindt.</span><span class="sxs-lookup"><span data-stu-id="b3a29-110">This enables auto-discovery of the city where each office is located.</span></span> <span data-ttu-id="b3a29-111">Locatiegegevens zijn niet nauwkeurig en zijn van 300m en gecategoriseerd op plaats.</span><span class="sxs-lookup"><span data-stu-id="b3a29-111">Location information is not precise and is obfuscated to 300m and categorized by city.</span></span> <span data-ttu-id="b3a29-112">Op het moment dat de locatie wordt vastgelegd op een Windows-apparaat, wordt het pictogram voor de **locatie in het deel** venster weergegeven in het systeemvak en beheerders kunnen gebruikers hierover informeren.</span><span class="sxs-lookup"><span data-stu-id="b3a29-112">At the time when location is captured on a Windows device it will show a **Location In-Use** icon in the tool tray and administrators may want to notify users of this.</span></span> <span data-ttu-id="b3a29-113">Met deze verwerking wordt de locatie behandeld als de kantoorlocatie van de organisatie en niet de locatie van een persoon of een apparaat.</span><span class="sxs-lookup"><span data-stu-id="b3a29-113">With this processing, the location is treated as the organization office location and not the location of a person or a device.</span></span> <span data-ttu-id="b3a29-114">Netwerk inzichten kunnen worden weergegeven op deze gedetecteerde Office-locatie steden.</span><span class="sxs-lookup"><span data-stu-id="b3a29-114">Network insights can be shown at these discovered office location cities.</span></span> <span data-ttu-id="b3a29-115">Als u de aanbevelingen nauwkeuriger vindt, kunt u een beheerder bepaalde adressen van de Office-locaties invoeren en de netwerk inzichten worden geaggregeerd in plaats daarvan.</span><span class="sxs-lookup"><span data-stu-id="b3a29-115">If greater accuracy of recommendations is desired, an administrator can enter specific office location addresses and the network insights will be aggregated to those instead.</span></span> <span data-ttu-id="b3a29-116">Office-locaties kunnen niet dichter bij 300 meter worden geaggregeerd.</span><span class="sxs-lookup"><span data-stu-id="b3a29-116">Office locations cannot be aggregated more closely than 300 meters.</span></span>

## <a name="location-in-the-microsoft-365-admin-center"></a><span data-ttu-id="b3a29-117">Locatie in het Microsoft 365-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="b3a29-117">Location in the Microsoft 365 Admin Center</span></span>

<span data-ttu-id="b3a29-118">In het Microsoft 365-Beheercentrum worden Bing Maps-besturingselementen gebruikt om te laten zien waar de kantoorlocaties van de organisatie zijn en om de topologie voor netwerkverbindingen voor een geselecteerde kantoorlocatie weer te geven.</span><span class="sxs-lookup"><span data-stu-id="b3a29-118">In the Microsoft 365 Admin Center, Bing map controls are used to show where organization office locations are and to show network perimeter topology for a selected office location.</span></span> <span data-ttu-id="b3a29-119">Wanneer een beheerder specifiek adresgegevens voor Office-locaties toevoegt, worden met Bing Maps ook adressen voorgesteld voor het eenvoudiger maken van gegevensinvoer.</span><span class="sxs-lookup"><span data-stu-id="b3a29-119">When an administrator adds specific address details for office locations, Bing Maps is also used to suggest addresses to make data entry easier.</span></span>

## <a name="terms-of-use"></a><span data-ttu-id="b3a29-120">Gebruiksvoorwaarden</span><span class="sxs-lookup"><span data-stu-id="b3a29-120">Terms of Use</span></span>

<span data-ttu-id="b3a29-121">Alle inhoud die u hebt verkregen via Bing Maps, waaronder geocodes, kan alleen worden gebruikt binnen het product waarop de inhoud wordt verstrekt.</span><span class="sxs-lookup"><span data-stu-id="b3a29-121">Any content provided through Bing Maps, including geocodes, can only be used within the product through which the content is provided.</span></span> <span data-ttu-id="b3a29-122">Het gebruik van de functie Services van het Microsoft 365-Beheercentrum, dat wordt beheerd door Bing Maps, is onderworpen aan de _Gebruiksvoorwaarden voor eindgebruikers van Bing Maps_ op de <https://go.microsoft.com/?linkid=9710837> privacyverklaring en de _privacyverklaring van Microsoft_ zijn beschikbaar op <https://go.microsoft.com/fwlink/?LinkID=248686.></span><span class="sxs-lookup"><span data-stu-id="b3a29-122">Customer's use of the Microsoft 365 Admin Center Location Services feature, powered by Bing Maps, is governed by the _Bing Maps End User Terms of Use_ available at <https://go.microsoft.com/?linkid=9710837> and the _Microsoft Privacy Statement_ available at <https://go.microsoft.com/fwlink/?LinkID=248686.></span></span>

<span data-ttu-id="b3a29-123">Deze functie, geleverd via Bing Maps, wordt ook door deze **technologieën**ondersteund.</span><span class="sxs-lookup"><span data-stu-id="b3a29-123">This feature, provided through Bing Maps, is also supported by **Here Technologies**.</span></span> <span data-ttu-id="b3a29-124">De werking van Bing Maps via Bing Maps wordt bepaald door de _Service voorwaarden van de volgende technologieën_ , verkrijgbaar op <https://legal.here.com/en-gb/terms> .</span><span class="sxs-lookup"><span data-stu-id="b3a29-124">How Bing Maps leverages location services provided by Here Technologies is governed by the _Here Technologies Service Terms_ available at <https://legal.here.com/en-gb/terms>.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b3a29-125">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b3a29-125">Related topics</span></span>

[<span data-ttu-id="b3a29-126">Netwerkverbinding in het Microsoft 365-Beheercentrum (preview)</span><span class="sxs-lookup"><span data-stu-id="b3a29-126">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="b3a29-127">Microsoft 365 Network Performance Insights (preview)</span><span class="sxs-lookup"><span data-stu-id="b3a29-127">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="b3a29-128">Microsoft 365-netwerk beoordeling (preview)</span><span class="sxs-lookup"><span data-stu-id="b3a29-128">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="b3a29-129">Microsoft 365 connectiviteitstest in het M365-Beheercentrum (preview)</span><span class="sxs-lookup"><span data-stu-id="b3a29-129">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)
