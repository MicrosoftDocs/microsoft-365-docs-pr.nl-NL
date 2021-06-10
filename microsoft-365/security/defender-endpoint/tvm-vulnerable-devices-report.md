---
title: Rapport Kwetsbare apparaten - Threat and Vulnerability Management
description: Een rapport met zwakke apparaattrends en huidige statistieken. Het doel is dat u de adem en het bereik van de blootstelling van uw apparaat begrijpt.
keywords: Microsoft Defender for Endpoint-tvm vulnerable devices, Microsoft Defender for Endpoint, tvm, reduce threat & vulnerability exposure, reduce threat and vulnerability, monitor security configuration
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 355561936642b1fa38228bfa07ad59269c48d817
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245478"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a><span data-ttu-id="51377-105">Rapport Kwetsbare apparaten - Threat and Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="51377-105">Vulnerable devices report - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="51377-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="51377-106">**Applies to:**</span></span>

- [<span data-ttu-id="51377-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="51377-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="51377-108">Bedreiging en vulnerability management</span><span class="sxs-lookup"><span data-stu-id="51377-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="51377-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51377-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="51377-110">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="51377-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="51377-111">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="51377-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="51377-112">Het rapport bevat grafieken en staafdiagrammen met kwetsbare apparaattrends en huidige statistieken.</span><span class="sxs-lookup"><span data-stu-id="51377-112">The report shows graphs and bar charts with vulnerable device trends and current statistics.</span></span> <span data-ttu-id="51377-113">Het doel is dat u de adem en het bereik van de blootstelling van uw apparaat begrijpt.</span><span class="sxs-lookup"><span data-stu-id="51377-113">The goal is for you to understand the breath and scope of your device exposure.</span></span>

<span data-ttu-id="51377-114">Toegang tot het rapport in de Microsoft Defender-beveiligingscentrum door naar **Rapporten > Kwetsbare apparaten**</span><span class="sxs-lookup"><span data-stu-id="51377-114">Access the report in the Microsoft Defender Security Center by going to **Reports > Vulnerable devices**</span></span>

<span data-ttu-id="51377-115">Er zijn twee kolommen:</span><span class="sxs-lookup"><span data-stu-id="51377-115">There are two columns:</span></span>

- <span data-ttu-id="51377-116">Trends (in de tijd).</span><span class="sxs-lookup"><span data-stu-id="51377-116">Trends (over time).</span></span> <span data-ttu-id="51377-117">Kan de afgelopen 30 dagen, 3 maanden, 6 maanden of een aangepast datumbereik laten zien.</span><span class="sxs-lookup"><span data-stu-id="51377-117">Can show the past 30 days, 3 months, 6 months, or a custom date range.</span></span>
- <span data-ttu-id="51377-118">Vandaag (huidige informatie)</span><span class="sxs-lookup"><span data-stu-id="51377-118">Today (current information)</span></span>

<span data-ttu-id="51377-119">**Filter:** U kunt de gegevens filteren op ernst van de kwetsbaarheid, misbruik maken van beschikbaarheid, leeftijd van kwetsbaarheid, besturingssysteemplatform, Windows 10 versie of apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="51377-119">**Filter**: You can filter the data by vulnerability severity levels, exploit availability, vulnerability age, operating system platform, Windows 10 version, or device group.</span></span>

<span data-ttu-id="51377-120">**Inzoomen:** Als er een inzicht is dat u verder wilt verkennen, selecteert u het relevante staafdiagram om een gefilterde lijst met apparaten weer te geven op de pagina Apparaatvoorraad.</span><span class="sxs-lookup"><span data-stu-id="51377-120">**Drill down**: If there is an insight you want to explore further, select the relevant bar chart to view a filtered list of devices in the Device inventory page.</span></span> <span data-ttu-id="51377-121">Van hieruit kunt u de lijst exporteren.</span><span class="sxs-lookup"><span data-stu-id="51377-121">From there, you can export the list.</span></span>

## <a name="severity-level-graphs"></a><span data-ttu-id="51377-122">Ernstniveaugrafieken</span><span class="sxs-lookup"><span data-stu-id="51377-122">Severity level graphs</span></span>

<span data-ttu-id="51377-123">Elk apparaat wordt slechts eenmaal geteld op basis van het ernstigste beveiligingsprobleem dat op dat apparaat is gevonden.</span><span class="sxs-lookup"><span data-stu-id="51377-123">Each device is counted only once according to the most severe vulnerability found on that device.</span></span>

![Eén grafiek met de ernst van de kwetsbaarheid van het huidige apparaat en één grafiek met niveaus in de tijd.](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a><span data-ttu-id="51377-125">Beschikbaarheidsgrafieken benutten</span><span class="sxs-lookup"><span data-stu-id="51377-125">Exploit availability graphs</span></span>

<span data-ttu-id="51377-126">Elk apparaat wordt slechts eenmaal geteld op basis van het hoogste niveau van bekende exploit.</span><span class="sxs-lookup"><span data-stu-id="51377-126">Each device is counted only once based on the highest level of known exploit.</span></span>

![Eén grafiek met de beschikbaarheid van het huidige apparaat en één grafiek met beschikbaarheid in de tijd.](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a><span data-ttu-id="51377-128">Leeftijdsgrafieken van kwetsbaarheid</span><span class="sxs-lookup"><span data-stu-id="51377-128">Vulnerability age graphs</span></span>

<span data-ttu-id="51377-129">Elk apparaat wordt slechts eenmaal geteld onder de oudste publicatiedatum van het beveiligingsprobleem.</span><span class="sxs-lookup"><span data-stu-id="51377-129">Each device is counted only once under the oldest vulnerability publication date.</span></span> <span data-ttu-id="51377-130">Oudere beveiligingslekken hebben een grotere kans op misbruik.</span><span class="sxs-lookup"><span data-stu-id="51377-130">Older vulnerabilities have a higher chance of being exploited.</span></span>

![Eén grafiek van de huidige leeftijd van de kwetsbaarheid van het apparaat en één grafiek met de leeftijd in de tijd.](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a><span data-ttu-id="51377-132">Kwetsbare apparaten per besturingssysteemplatformgrafieken</span><span class="sxs-lookup"><span data-stu-id="51377-132">Vulnerable devices by operating system platform graphs</span></span>

<span data-ttu-id="51377-133">Het aantal apparaten op elk besturingssysteem dat wordt blootgesteld als gevolg van softwareproblemen.</span><span class="sxs-lookup"><span data-stu-id="51377-133">The number of devices on each operating system that are exposed due to software vulnerabilities.</span></span>

![Eén grafiek van huidige, kwetsbare apparaten per besturingssysteemplatform en één grafiek met kwetsbare apparaten van besturingssysteemplatforms in de tijd.](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a><span data-ttu-id="51377-135">Kwetsbare apparaten op Windows 10 versiegrafieken</span><span class="sxs-lookup"><span data-stu-id="51377-135">Vulnerable devices by Windows 10 version graphs</span></span>

<span data-ttu-id="51377-136">Het aantal apparaten op elke Windows 10 versie die worden blootgesteld aan kwetsbare toepassingen of besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="51377-136">The number of devices on each Windows 10 version that are exposed due to vulnerable applications or OS.</span></span>

![Eén grafiek van huidige, kwetsbare apparaten per Windows 10 versie en één grafiek met kwetsbare apparaten per Windows 10 in de tijd.](images/tvm-report-version.png)

## <a name="related-topics"></a><span data-ttu-id="51377-138">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="51377-138">Related topics</span></span>

- [<span data-ttu-id="51377-139">Overzicht van bedreigingen en vulnerability management</span><span class="sxs-lookup"><span data-stu-id="51377-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="51377-140">Beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="51377-140">Security recommendations</span></span>](tvm-security-recommendation.md)
