---
title: Microsoft Defender voor eindpuntdomeinen onderzoeken
description: Gebruik de onderzoeksopties om te zien of apparaten en servers met schadelijke domeinen hebben gecommuniceerd.
keywords: domein, domein, kwaadwillend domein, microsoft defender atp, waarschuwing, URL onderzoeken
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 7918a62c3afa2cfd97ffc77ad756339010c1d7a3
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186075"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="8fcc8-104">Een domein onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="8fcc8-104">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8fcc8-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8fcc8-105">**Applies to:**</span></span>
- [<span data-ttu-id="8fcc8-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="8fcc8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8fcc8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8fcc8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8fcc8-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="8fcc8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8fcc8-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatedomain-abovefoldlink) 

<span data-ttu-id="8fcc8-110">Onderzoek een domein om te zien of apparaten en servers in uw bedrijfsnetwerk hebben gecommuniceerd met een bekend kwaadwillend domein.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-110">Investigate a domain to see if devices and servers in your enterprise network have been communicating with a known malicious domain.</span></span>

<span data-ttu-id="8fcc8-111">U kunt een domein onderzoeken met behulp van de zoekfunctie of door te klikken op een domeinkoppeling vanuit de **apparaattijdlijn.**</span><span class="sxs-lookup"><span data-stu-id="8fcc8-111">You can investigate a domain by using the search feature or by clicking on a domain link from the **Device timeline**.</span></span>

<span data-ttu-id="8fcc8-112">In de URL-weergave ziet u informatie uit de volgende secties:</span><span class="sxs-lookup"><span data-stu-id="8fcc8-112">You can see information from the following sections in the URL view:</span></span>

- <span data-ttu-id="8fcc8-113">URL-details, Contactpersonen, Nameservers</span><span class="sxs-lookup"><span data-stu-id="8fcc8-113">URL details, Contacts, Nameservers</span></span>
- <span data-ttu-id="8fcc8-114">Waarschuwingen met betrekking tot deze URL</span><span class="sxs-lookup"><span data-stu-id="8fcc8-114">Alerts related to this URL</span></span> 
- <span data-ttu-id="8fcc8-115">URL in organisatie</span><span class="sxs-lookup"><span data-stu-id="8fcc8-115">URL in organization</span></span>
- <span data-ttu-id="8fcc8-116">Meest recente waargenomen apparaten met URL</span><span class="sxs-lookup"><span data-stu-id="8fcc8-116">Most recent observed devices with URL</span></span>

## <a name="url-worldwide"></a><span data-ttu-id="8fcc8-117">URL wereldwijd</span><span class="sxs-lookup"><span data-stu-id="8fcc8-117">URL worldwide</span></span>

<span data-ttu-id="8fcc8-118">De **sectie URL Worldwide** bevat de URL, een koppeling naar meer informatie bij Whois, het aantal gerelateerde geopende incidenten en het aantal actieve waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-118">The **URL Worldwide** section lists the URL, a link to further details at Whois, the number of related open incidents, and the number of active alerts.</span></span>

## <a name="incident"></a><span data-ttu-id="8fcc8-119">Incident</span><span class="sxs-lookup"><span data-stu-id="8fcc8-119">Incident</span></span>

<span data-ttu-id="8fcc8-120">Op **de kaart Incident** wordt een staafdiagram weergegeven met alle actieve waarschuwingen in incidenten van de afgelopen 180 dagen.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-120">The **Incident** card displays a bar chart of all active alerts in incidents over the past 180 days.</span></span>

## <a name="prevalence"></a><span data-ttu-id="8fcc8-121">Prevalentie</span><span class="sxs-lookup"><span data-stu-id="8fcc8-121">Prevalence</span></span>

<span data-ttu-id="8fcc8-122">De **kaart Prevalentie** bevat details over de prevalentie van de URL binnen de organisatie, over een bepaalde periode.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-122">The **Prevalence** card provides details on the prevalence of the URL within the organization, over a specified period of time.</span></span>

<span data-ttu-id="8fcc8-123">Hoewel de standaardperiode de afgelopen 30 dagen is, kunt u het bereik aanpassen door de pijl naar beneden in de hoek van de kaart te selecteren.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-123">Although the default time period is the past 30 days, you can customize the range by selecting the downward-pointing arrow in the corner of the card.</span></span> <span data-ttu-id="8fcc8-124">Het kortste bereik dat beschikbaar is voor de prevalentie van de afgelopen dag, terwijl het langste bereik de afgelopen 6 maanden is.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-124">The shortest range available is for prevalence over the past day, while the longest range is over the past 6 months.</span></span>

## <a name="alerts"></a><span data-ttu-id="8fcc8-125">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="8fcc8-125">Alerts</span></span>

<span data-ttu-id="8fcc8-126">Het **tabblad** Waarschuwingen bevat een lijst met waarschuwingen die zijn gekoppeld aan de URL.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-126">The **Alerts** tab provides a list of alerts that are associated with the URL.</span></span> <span data-ttu-id="8fcc8-127">De tabel die hier wordt weergegeven, is een gefilterde versie van de waarschuwingen die zichtbaar zijn in het waarschuwingswachtrijscherm, met alleen waarschuwingen die zijn gekoppeld aan het domein, de ernst, status, het bijbehorende incident, de classificatie, de onderzoeksstatus en meer.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-127">The table shown here is a filtered version of the alerts visible on the Alert queue screen, showing only alerts associated with the domain, their severity, status, the associated incident, classification, investigation state, and more.</span></span>

<span data-ttu-id="8fcc8-128">Het tabblad Waarschuwingen kan worden aangepast om meer of minder informatie weer te geven door kolommen aanpassen te **selecteren** in het actiemenu boven de kolomkoppen.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-128">The Alerts tab can be adjusted to show more or less information, by selecting **Customize columns** from the action menu above the column headers.</span></span> <span data-ttu-id="8fcc8-129">Het aantal weergegeven items kan ook worden aangepast door **items per pagina in** hetzelfde menu te selecteren.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-129">The number of items displayed can also be adjusted, by selecting **items per page** on the same menu.</span></span>

## <a name="observed-in-organization"></a><span data-ttu-id="8fcc8-130">Waargenomen in organisatie</span><span class="sxs-lookup"><span data-stu-id="8fcc8-130">Observed in organization</span></span>

<span data-ttu-id="8fcc8-131">Het **tabblad Waargenomen in organisatie** biedt een chronologische weergave van de gebeurtenissen en bijbehorende waarschuwingen die zijn waargenomen op de URL.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-131">The **Observed in organization** tab provides a chronological view on the events and associated alerts that were observed on the URL.</span></span> <span data-ttu-id="8fcc8-132">Dit tabblad bevat een tijdlijn en een aanpasbare tabel met gebeurtenisdetails, zoals de tijd, het apparaat en een korte beschrijving van wat er is gebeurd.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-132">This tab includes a timeline and a customizable table listing event details, such as the time, device, and a brief description of what happened.</span></span> 

<span data-ttu-id="8fcc8-133">U kunt gebeurtenissen uit verschillende perioden bekijken door de datums in te geven in de tekstvelden boven de tabelkoppen.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-133">You can view events from different periods of time by entering the dates into the text fields above the table headers.</span></span> <span data-ttu-id="8fcc8-134">U kunt ook het tijdbereik aanpassen door verschillende gebieden van de tijdlijn te selecteren.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-134">You can also customize the time range by selecting different areas of the timeline.</span></span>

<span data-ttu-id="8fcc8-135">**Een domein onderzoeken:**</span><span class="sxs-lookup"><span data-stu-id="8fcc8-135">**Investigate a domain:**</span></span>

1. <span data-ttu-id="8fcc8-136">Selecteer **URL** in **de** vervolgkeuzelijst Zoekbalk.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-136">Select **URL** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="8fcc8-137">Voer de URL in het **veld Zoeken** in.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-137">Enter the URL in the **Search** field.</span></span>
3. <span data-ttu-id="8fcc8-138">Klik op het zoekpictogram of druk op **Enter.**</span><span class="sxs-lookup"><span data-stu-id="8fcc8-138">Click the search icon   or press **Enter**.</span></span> <span data-ttu-id="8fcc8-139">Details over de URL worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-139">Details about the URL are displayed.</span></span> <span data-ttu-id="8fcc8-140">Opmerking: zoekresultaten worden alleen geretourneerd voor URL's die worden waargenomen in communicatie vanaf apparaten in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-140">Note: search results will only be returned for URLs observed in communications from devices in the organization.</span></span>
4. <span data-ttu-id="8fcc8-141">Gebruik de zoekfilters om de zoekcriteria te definiëren.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-141">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="8fcc8-142">U kunt ook het zoekvak voor de tijdlijn gebruiken om de weergegeven resultaten te filteren van alle apparaten in de organisatie die zijn waargenomen bij het communiceren met de URL, het bestand dat is gekoppeld aan de communicatie en de laatste waargenomen datum.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-142">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the URL, the file associated with the communication and the last date observed.</span></span>
5. <span data-ttu-id="8fcc8-143">Als u op een van de apparaatnamen klikt, gaat u naar de weergave van dat apparaat, waar u gerapporteerde waarschuwingen, gedragingen en gebeurtenissen kunt blijven onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="8fcc8-143">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8fcc8-144">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8fcc8-144">Related topics</span></span>
- [<span data-ttu-id="8fcc8-145">De wachtrij waarschuwingen voor Microsoft Defender voor eindpunten weergeven en ordenen</span><span class="sxs-lookup"><span data-stu-id="8fcc8-145">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="8fcc8-146">Waarschuwingen voor Microsoft Defender voor eindpunten beheren</span><span class="sxs-lookup"><span data-stu-id="8fcc8-146">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="8fcc8-147">Microsoft Defender onderzoeken voor eindpuntwaarschuwingen</span><span class="sxs-lookup"><span data-stu-id="8fcc8-147">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="8fcc8-148">Een bestand onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="8fcc8-148">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="8fcc8-149">Apparaten onderzoeken in de lijst Microsoft Defender voor eindpuntapparaten</span><span class="sxs-lookup"><span data-stu-id="8fcc8-149">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="8fcc8-150">Een IP-adres onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="8fcc8-150">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="8fcc8-151">Een gebruikersaccount onderzoeken in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="8fcc8-151">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
