---
title: Rapport over apparaattoestand en naleving in MICROSOFT Defender ATP
description: Detectie van apparaatstatussen, antivirusstatus, besturingssysteemplatform en Windows 10-versies bijhouden met behulp van het rapport Apparaatstatus en naleving
keywords: status, antivirus, besturingssysteemplatform, windows 10-versie, versie, status, naleving, status
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
ms.openlocfilehash: 9d41071fc5849f3a11061437af2bb88b117ec4a8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058290"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="9d881-104">Rapport over apparaattoestand en naleving in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="9d881-104">Device health and compliance report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9d881-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="9d881-105">**Applies to:**</span></span>
- [<span data-ttu-id="9d881-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="9d881-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="9d881-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9d881-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="9d881-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="9d881-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9d881-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="9d881-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="9d881-110">Het statusrapport apparaten bevat informatie op hoog niveau over de apparaten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="9d881-110">The devices status report provides high-level information about the devices in your organization.</span></span> <span data-ttu-id="9d881-111">Het rapport bevat trending-informatie over de status van de sensorstatus, antivirusstatus, besturingssysteemplatforms en Windows 10-versies.</span><span class="sxs-lookup"><span data-stu-id="9d881-111">The report includes trending information showing the sensor health state, antivirus status, OS platforms, and Windows 10 versions.</span></span>

<span data-ttu-id="9d881-112">Het dashboard is gestructureerd in twee secties: ![ Afbeelding van het apparaatrapport](images/device-reports.png)</span><span class="sxs-lookup"><span data-stu-id="9d881-112">The dashboard is structured into two sections: ![Image of the device report](images/device-reports.png)</span></span>
 
<span data-ttu-id="9d881-113">Sectie</span><span class="sxs-lookup"><span data-stu-id="9d881-113">Section</span></span> | <span data-ttu-id="9d881-114">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="9d881-114">Description</span></span>
:---|:---
<span data-ttu-id="9d881-115">1</span><span class="sxs-lookup"><span data-stu-id="9d881-115">1</span></span> | <span data-ttu-id="9d881-116">Apparaattrends</span><span class="sxs-lookup"><span data-stu-id="9d881-116">Device trends</span></span>
<span data-ttu-id="9d881-117">2</span><span class="sxs-lookup"><span data-stu-id="9d881-117">2</span></span> | <span data-ttu-id="9d881-118">Apparaatoverzicht (huidige dag)</span><span class="sxs-lookup"><span data-stu-id="9d881-118">Device summary (current day)</span></span>
 
 
## <a name="device-trends"></a><span data-ttu-id="9d881-119">Apparaattrends</span><span class="sxs-lookup"><span data-stu-id="9d881-119">Device trends</span></span> 
<span data-ttu-id="9d881-120">De apparaattrends geven standaard apparaatgegevens weer uit de periode van 30 dagen die eindigt op de laatste volledige dag.</span><span class="sxs-lookup"><span data-stu-id="9d881-120">By default, the device trends displays device information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="9d881-121">Als u meer inzicht wilt krijgen in trends in uw organisatie, kunt u de rapportageperiode aanpassen door de weergegeven periode aan te passen.</span><span class="sxs-lookup"><span data-stu-id="9d881-121">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="9d881-122">Als u de periode wilt aanpassen, selecteert u een tijdsbereik in de vervolgkeuzeopties:</span><span class="sxs-lookup"><span data-stu-id="9d881-122">To adjust the time period, select a time range from the drop-down options:</span></span>
 
- <span data-ttu-id="9d881-123">30 dagen</span><span class="sxs-lookup"><span data-stu-id="9d881-123">30 days</span></span>
- <span data-ttu-id="9d881-124">3 maanden</span><span class="sxs-lookup"><span data-stu-id="9d881-124">3 months</span></span>
- <span data-ttu-id="9d881-125">6 maanden</span><span class="sxs-lookup"><span data-stu-id="9d881-125">6 months</span></span>
- <span data-ttu-id="9d881-126">Aangepast</span><span class="sxs-lookup"><span data-stu-id="9d881-126">Custom</span></span>

>[!NOTE]
><span data-ttu-id="9d881-127">Deze filters worden alleen toegepast op de sectie Apparaattrends.</span><span class="sxs-lookup"><span data-stu-id="9d881-127">These filters are only applied on the device trends section.</span></span> <span data-ttu-id="9d881-128">Dit heeft geen invloed op de sectie Apparaatoverzicht.</span><span class="sxs-lookup"><span data-stu-id="9d881-128">It doesn't affect the device summary section.</span></span>

## <a name="device-summary"></a><span data-ttu-id="9d881-129">Apparaatoverzicht</span><span class="sxs-lookup"><span data-stu-id="9d881-129">Device summary</span></span> 
<span data-ttu-id="9d881-130">Terwijl de apparatentrends trending apparaatgegevens laten zien, wordt in het apparaatoverzicht de apparaatgegevens tot op de huidige dag gebruikt.</span><span class="sxs-lookup"><span data-stu-id="9d881-130">While the devices trends shows trending device information, the device summary shows device information scoped to the current day.</span></span> 

>[!NOTE]
><span data-ttu-id="9d881-131">De gegevens die in de samenvattingssectie worden weergegeven, hebben een bereik van 180 dagen vóór de huidige datum.</span><span class="sxs-lookup"><span data-stu-id="9d881-131">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="9d881-132">Als de datum van vandaag bijvoorbeeld 27 maart 2019 is, worden de gegevens in de samenvattingssectie weergegeven met getallen die beginnen van 28 september 2018 tot en met 27 maart 2019.</span><span class="sxs-lookup"><span data-stu-id="9d881-132">For example if today's date is March 27, 2019, the data on the summary section will reflect numbers starting from September 28, 2018 to March 27, 2019.</span></span><br>
> <span data-ttu-id="9d881-133">Het filter dat is toegepast op de sectie Trends, wordt niet toegepast op de samenvattingssectie.</span><span class="sxs-lookup"><span data-stu-id="9d881-133">The filter applied on the trends section is not applied on the summary section.</span></span> 
 
<span data-ttu-id="9d881-134">In de sectie Apparaattrends kunt u inzoomen op de lijst met apparaten met het bijbehorende filter dat op het apparaat is toegepast.</span><span class="sxs-lookup"><span data-stu-id="9d881-134">The device trends section allows you to drill down to the devices list with the corresponding filter applied to it.</span></span> <span data-ttu-id="9d881-135">Als u bijvoorbeeld op de inactieve balk in de statuskaart voor sensorstatus klikt, wordt de lijst met apparaten weergegeven met alleen apparaten waarvan de sensorstatus inactief is.</span><span class="sxs-lookup"><span data-stu-id="9d881-135">For example, clicking on the Inactive bar in the Sensor health state card will bring you the devices list with results showing only devices whose sensor status is inactive.</span></span> 
 
 
 
## <a name="device-attributes"></a><span data-ttu-id="9d881-136">Apparaatkenmerken</span><span class="sxs-lookup"><span data-stu-id="9d881-136">Device attributes</span></span>
<span data-ttu-id="9d881-137">Het rapport bestaat uit kaarten met de volgende apparaatkenmerken:</span><span class="sxs-lookup"><span data-stu-id="9d881-137">The report is made up of cards that display the following device attributes:</span></span>
 
- <span data-ttu-id="9d881-138">**Gezondheidstoestand:** geeft informatie weer over de sensortoestand op apparaten, met een samengevoegde weergave van apparaten die actief zijn, communicatiesproblemen ondervinden, inactief zijn of waar geen sensorgegevens worden gezien.</span><span class="sxs-lookup"><span data-stu-id="9d881-138">**Health state**: shows information about the sensor state on devices, providing an aggregated view of devices that are active, experiencing impaired communications, inactive, or where no sensor data is seen.</span></span>
  
- <span data-ttu-id="9d881-139">**Antivirusstatus voor actieve Windows 10-apparaten:** toont het aantal apparaten en de status van Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="9d881-139">**Antivirus status for active Windows 10 devices**: shows the number of devices and status of Microsoft Defender Antivirus.</span></span>
    
- <span data-ttu-id="9d881-140">**BESTURINGSSYSTEEM-platforms:** toont de distributie van besturingssysteemplatforms die binnen uw organisatie aanwezig zijn.</span><span class="sxs-lookup"><span data-stu-id="9d881-140">**OS platforms**: shows the distribution of OS platforms that exists within your organization.</span></span> 
 
- <span data-ttu-id="9d881-141">**Windows 10-versies:** toont de distributie van Windows 10-apparaten en hun versies in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="9d881-141">**Windows 10 versions**: shows the distribution of Windows 10 devices and their versions in your organization.</span></span>
 
 
 
## <a name="filter-data"></a><span data-ttu-id="9d881-142">Gegevens filteren</span><span class="sxs-lookup"><span data-stu-id="9d881-142">Filter data</span></span>
 
<span data-ttu-id="9d881-143">Gebruik de meegeleverde filters om apparaten met bepaalde kenmerken op te nemen of uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="9d881-143">Use the provided filters to include or exclude devices with certain attributes.</span></span>

<span data-ttu-id="9d881-144">U kunt meerdere filters selecteren die u wilt toepassen op de apparaatkenmerken.</span><span class="sxs-lookup"><span data-stu-id="9d881-144">You can select multiple filters to apply from the device attributes.</span></span> 
 
>[!NOTE]
><span data-ttu-id="9d881-145">Deze filters zijn van **toepassing op alle** kaarten in het rapport.</span><span class="sxs-lookup"><span data-stu-id="9d881-145">These filters apply to **all** the cards in the report.</span></span>
 
<span data-ttu-id="9d881-146">Als u bijvoorbeeld gegevens wilt tonen over Windows 10-apparaten met de status actieve sensor:</span><span class="sxs-lookup"><span data-stu-id="9d881-146">For example, to show data about Windows 10 devices with Active sensor health state:</span></span>
 
1. <span data-ttu-id="9d881-147">Onder **Filters > status van de sensor > Actief**.</span><span class="sxs-lookup"><span data-stu-id="9d881-147">Under **Filters > Sensor health state > Active**.</span></span>
2. <span data-ttu-id="9d881-148">Selecteer vervolgens **BE-platforms > Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="9d881-148">Then select **OS platforms > Windows 10**.</span></span>
3. <span data-ttu-id="9d881-149">Selecteer **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="9d881-149">Select **Apply**.</span></span>


## <a name="related-topic"></a><span data-ttu-id="9d881-150">Gerelateerd onderwerp</span><span class="sxs-lookup"><span data-stu-id="9d881-150">Related topic</span></span>
- [<span data-ttu-id="9d881-151">Rapport over bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="9d881-151">Threat protection report</span></span>](threat-protection-reports.md)
