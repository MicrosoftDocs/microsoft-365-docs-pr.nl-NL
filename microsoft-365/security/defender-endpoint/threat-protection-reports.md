---
title: Rapport bedreigingsbeveiliging in MICROSOFT Defender ATP
description: Waarschuwingsdetecties, categorieën en ernst bijhouden met behulp van het rapport bedreigingsbeveiliging
keywords: waarschuwingsdetectie, bron, waarschuwing per categorie, ernst van waarschuwing, waarschuwingsclassificatie, bepaling
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4ecd2df31e1e03da5134d3d4180dcba75d3cee26
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183835"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="c321d-104">Rapport bedreigingsbeveiliging in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="c321d-104">Threat protection report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c321d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c321d-105">**Applies to:**</span></span>
- [<span data-ttu-id="c321d-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="c321d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c321d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c321d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="c321d-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="c321d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c321d-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="c321d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="c321d-110">Het rapport bedreigingsbeveiliging bevat informatie op hoog niveau over waarschuwingen die in uw organisatie worden gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="c321d-110">The threat protection report provides high-level information about alerts generated in your organization.</span></span> <span data-ttu-id="c321d-111">Het rapport bevat trendgegevens met de detectiebronnen, categorieën, ernst, statussen, classificaties en de bepaling van waarschuwingen in de tijd.</span><span class="sxs-lookup"><span data-stu-id="c321d-111">The report includes trending information showing the detection sources, categories, severities, statuses, classifications, and determinations of alerts across time.</span></span>

<span data-ttu-id="c321d-112">Het dashboard is gestructureerd in twee secties:</span><span class="sxs-lookup"><span data-stu-id="c321d-112">The dashboard is structured into two sections:</span></span>

![Afbeelding van het rapport bedreigingsbeveiliging](images/threat-protection-reports.png)

<span data-ttu-id="c321d-114">Sectie</span><span class="sxs-lookup"><span data-stu-id="c321d-114">Section</span></span> | <span data-ttu-id="c321d-115">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="c321d-115">Description</span></span> 
:---|:---
<span data-ttu-id="c321d-116">1</span><span class="sxs-lookup"><span data-stu-id="c321d-116">1</span></span> | <span data-ttu-id="c321d-117">Trends in waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="c321d-117">Alerts trends</span></span>
<span data-ttu-id="c321d-118">2</span><span class="sxs-lookup"><span data-stu-id="c321d-118">2</span></span> | <span data-ttu-id="c321d-119">Overzicht van waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="c321d-119">Alert summary</span></span>

## <a name="alert-trends"></a><span data-ttu-id="c321d-120">Waarschuwingstrends</span><span class="sxs-lookup"><span data-stu-id="c321d-120">Alert trends</span></span>
<span data-ttu-id="c321d-121">Standaard worden in de waarschuwingstrends waarschuwingsgegevens weergegeven uit de periode van 30 dagen die eindigt op de laatste volledige dag.</span><span class="sxs-lookup"><span data-stu-id="c321d-121">By default, the alert trends display alert information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="c321d-122">Als u meer inzicht wilt krijgen in trends in uw organisatie, kunt u de rapportageperiode aanpassen door de weergegeven periode aan te passen.</span><span class="sxs-lookup"><span data-stu-id="c321d-122">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="c321d-123">Als u de periode wilt aanpassen, selecteert u een tijdsbereik in de vervolgkeuzeopties:</span><span class="sxs-lookup"><span data-stu-id="c321d-123">To adjust the time period, select a time range from the drop-down options:</span></span>

- <span data-ttu-id="c321d-124">30 dagen</span><span class="sxs-lookup"><span data-stu-id="c321d-124">30 days</span></span>
- <span data-ttu-id="c321d-125">3 maanden</span><span class="sxs-lookup"><span data-stu-id="c321d-125">3 months</span></span>
- <span data-ttu-id="c321d-126">6 maanden</span><span class="sxs-lookup"><span data-stu-id="c321d-126">6 months</span></span>
- <span data-ttu-id="c321d-127">Aangepast</span><span class="sxs-lookup"><span data-stu-id="c321d-127">Custom</span></span>

>[!NOTE]
><span data-ttu-id="c321d-128">Deze filters worden alleen toegepast op de sectie waarschuwingstrends.</span><span class="sxs-lookup"><span data-stu-id="c321d-128">These filters are only applied on the alert trends section.</span></span> <span data-ttu-id="c321d-129">Dit heeft geen invloed op de sectie Overzicht van waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="c321d-129">It doesn't affect the alert summary section.</span></span>


## <a name="alert-summary"></a><span data-ttu-id="c321d-130">Overzicht van waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="c321d-130">Alert summary</span></span>
<span data-ttu-id="c321d-131">Terwijl de waarschuwingstrends trending waarschuwingsgegevens laten zien, worden in de overzichtsoverzicht van waarschuwingen waarschuwingsinformatie voor de huidige dag gegeven.</span><span class="sxs-lookup"><span data-stu-id="c321d-131">While the alert trends shows trending alert information, the alert summary shows alert information scoped to the current day.</span></span>

 <span data-ttu-id="c321d-132">Met het overzicht van waarschuwingen kunt u inzoomen op een bepaalde waarschuwingswachtrij waarbij het bijbehorende filter erop is toegepast.</span><span class="sxs-lookup"><span data-stu-id="c321d-132">The alert summary allows you to drill down to a particular alert queue with the corresponding filter applied to it.</span></span> <span data-ttu-id="c321d-133">Als u bijvoorbeeld op de EDR-balk in de kaart Detectiebronnen klikt, wordt de wachtrij voor waarschuwingen weergegeven met alleen waarschuwingen die zijn gegenereerd op basis van EDR-detecties.</span><span class="sxs-lookup"><span data-stu-id="c321d-133">For example, clicking on the EDR bar in the Detection sources card will bring you the alerts queue with results showing only alerts generated from EDR detections.</span></span> 

>[!NOTE]
><span data-ttu-id="c321d-134">De gegevens die in de samenvattingssectie worden weergegeven, hebben een bereik van 180 dagen vóór de huidige datum.</span><span class="sxs-lookup"><span data-stu-id="c321d-134">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="c321d-135">Als de datum van vandaag bijvoorbeeld 5 november 2019 is, worden in de gegevens in de samenvattingssectie getallen weergegeven die beginnen van 5 mei 2019 tot en met 5 november 2019.</span><span class="sxs-lookup"><span data-stu-id="c321d-135">For example if today's date is November 5, 2019, the data on the summary section will reflect numbers starting from May 5, 2019 to November 5, 2019.</span></span><br>
> <span data-ttu-id="c321d-136">Het filter dat is toegepast op de sectie Trends, wordt niet toegepast op de samenvattingssectie.</span><span class="sxs-lookup"><span data-stu-id="c321d-136">The filter applied on the trends section is not applied on the summary section.</span></span> 

## <a name="alert-attributes"></a><span data-ttu-id="c321d-137">Waarschuwingskenmerken</span><span class="sxs-lookup"><span data-stu-id="c321d-137">Alert attributes</span></span>
<span data-ttu-id="c321d-138">Het rapport bestaat uit kaarten met de volgende waarschuwingskenmerken:</span><span class="sxs-lookup"><span data-stu-id="c321d-138">The report is made up of cards that display the following alert attributes:</span></span>

- <span data-ttu-id="c321d-139">**Detectiebronnen:** geeft informatie weer over de sensoren en detectietechnologieën die de gegevens bevatten die door Microsoft Defender voor Eindpunt worden gebruikt om waarschuwingen te activeren.</span><span class="sxs-lookup"><span data-stu-id="c321d-139">**Detection sources**: shows information about the sensors and detection technologies that provide the data used by Microsoft Defender for Endpoint to trigger alerts.</span></span>

- <span data-ttu-id="c321d-140">**Bedreigingscategorieën:** geeft de typen bedreigings- of aanvalsactiviteiten weer die waarschuwingen hebben geactiveerd, waarmee mogelijke focusgebieden voor uw beveiligingsbewerkingen worden aangegeven.</span><span class="sxs-lookup"><span data-stu-id="c321d-140">**Threat categories**: shows the types of threat or attack activity that triggered alerts, indicating possible focus areas for your security operations.</span></span>

- <span data-ttu-id="c321d-141">**Ernst:** geeft het ernstniveau van waarschuwingen weer, wat aangeeft wat de mogelijke gevolgen zijn van bedreigingen voor uw organisatie en het antwoordniveau dat nodig is om deze aan te pakken.</span><span class="sxs-lookup"><span data-stu-id="c321d-141">**Severity**: shows the severity level of alerts, indicating the collective potential impact of threats to your organization and the level of response needed to address them.</span></span>

- <span data-ttu-id="c321d-142">**Status:** geeft de resolutiestatus van waarschuwingen weer, waarmee de efficiëntie van uw handmatige waarschuwingsreacties en van geautomatiseerde herstel (indien ingeschakeld) wordt aangegeven.</span><span class="sxs-lookup"><span data-stu-id="c321d-142">**Status**: shows the resolution status of alerts, indicating the efficiency of your manual alert responses and of automated remediation (if enabled).</span></span> 

- <span data-ttu-id="c321d-143">**Classificatie &** bepaling: laat zien hoe u waarschuwingen hebt geclassificeerd bij resolutie, of u deze hebt geclassificeerd als werkelijke bedreigingen (echte waarschuwingen) of als onjuiste detecties (onwaar waarschuwingen).</span><span class="sxs-lookup"><span data-stu-id="c321d-143">**Classification & determination**: shows how you have classified alerts upon resolution, whether you have classified them as actual threats (true alerts) or as incorrect detections (false alerts).</span></span> <span data-ttu-id="c321d-144">Deze kaarten geven ook de bepaling van opgeloste waarschuwingen weer, wat extra inzicht geeft, zoals de typen werkelijke bedreigingen die zijn gevonden of de legitieme activiteiten die ten onrechte zijn gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="c321d-144">These cards also show the determination of resolved alerts, providing additional insight like the types of actual threats found or the legitimate activities that were incorrectly detected.</span></span>


 

## <a name="filter-data"></a><span data-ttu-id="c321d-145">Gegevens filteren</span><span class="sxs-lookup"><span data-stu-id="c321d-145">Filter data</span></span>

<span data-ttu-id="c321d-146">Gebruik de meegeleverde filters om waarschuwingen met bepaalde kenmerken op te nemen of uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="c321d-146">Use the provided filters to include or exclude alerts with certain attributes.</span></span>

>[!NOTE]
><span data-ttu-id="c321d-147">Deze filters zijn van **toepassing op alle** kaarten in het rapport.</span><span class="sxs-lookup"><span data-stu-id="c321d-147">These filters apply to **all** the cards in the report.</span></span>

<span data-ttu-id="c321d-148">Als u bijvoorbeeld alleen gegevens wilt weergeven over waarschuwingen met hoge ernst:</span><span class="sxs-lookup"><span data-stu-id="c321d-148">For example, to show data about high-severity alerts only:</span></span>

1. <span data-ttu-id="c321d-149">Selecteer **onder Filters > Ernst** de optie **Hoog**</span><span class="sxs-lookup"><span data-stu-id="c321d-149">Under **Filters > Severity**, select **High**</span></span>
2. <span data-ttu-id="c321d-150">Zorg ervoor dat alle andere opties onder **Ernst** worden uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c321d-150">Ensure that all other options under **Severity** are deselected.</span></span>
3. <span data-ttu-id="c321d-151">Selecteer **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="c321d-151">Select **Apply**.</span></span> 

## <a name="related-topic"></a><span data-ttu-id="c321d-152">Verwant onderwerp</span><span class="sxs-lookup"><span data-stu-id="c321d-152">Related topic</span></span>
- [<span data-ttu-id="c321d-153">Rapport apparaattoestand en naleving</span><span class="sxs-lookup"><span data-stu-id="c321d-153">Device health and compliance report</span></span>](machine-reports.md)
