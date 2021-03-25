---
title: De atp-apparatenlijst van Microsoft Defender weergeven en ordenen
description: Meer informatie over de beschikbare functies die u kunt gebruiken in de lijst Apparaten, zoals het sorteren, filteren en exporteren van de lijst om de onderzoeken te verbeteren.
keywords: sorteren, filteren, exporteren, csv, apparaatnaam, domein, laatst gezien, intern IP, status, actieve waarschuwingen, actieve malwaredetecties, bedreigingscategorie, waarschuwingen controleren, netwerk, verbinding, malware, type, wachtwoord stealer, ransomware, exploit, bedreiging, algemene malware, ongewenste software
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
ms.openlocfilehash: 9068983b5f61305b1f3da4d076e99e71974e8df4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185669"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="bca78-104">De lijst Met Microsoft Defender voor eindpuntapparaten weergeven en organiseren</span><span class="sxs-lookup"><span data-stu-id="bca78-104">View and organize the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bca78-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="bca78-105">**Applies to:**</span></span>
- [<span data-ttu-id="bca78-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="bca78-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bca78-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bca78-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bca78-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="bca78-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bca78-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="bca78-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-machinesview-abovefoldlink)


<span data-ttu-id="bca78-110">In **de lijst Apparaten** ziet u een lijst met de apparaten in uw netwerk waar waarschuwingen zijn gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="bca78-110">The **Devices list** shows a list of the devices in your network where alerts were generated.</span></span> <span data-ttu-id="bca78-111">Standaard worden in de wachtrij apparaten weergegeven die de afgelopen 30 dagen zijn weergegeven.</span><span class="sxs-lookup"><span data-stu-id="bca78-111">By default, the queue displays devices seen in the last 30 days.</span></span>  

<span data-ttu-id="bca78-112">In één oogopslag ziet u informatie zoals domein, risiconiveau, besturingssysteemplatform en andere details voor eenvoudige identificatie van apparaten die het meest risico lopen.</span><span class="sxs-lookup"><span data-stu-id="bca78-112">At a glance you'll see information such as domain, risk level, OS platform, and other details for easy identification of devices most at risk.</span></span>

<span data-ttu-id="bca78-113">Er zijn verschillende opties waar u uit kunt kiezen om de lijstweergave voor apparaten aan te passen.</span><span class="sxs-lookup"><span data-stu-id="bca78-113">There are several options you can choose from to customize the devices list view.</span></span> <span data-ttu-id="bca78-114">Op de bovenste navigatie kunt u:</span><span class="sxs-lookup"><span data-stu-id="bca78-114">On the top navigation you can:</span></span>

- <span data-ttu-id="bca78-115">Kolommen toevoegen of verwijderen</span><span class="sxs-lookup"><span data-stu-id="bca78-115">Add or remove columns</span></span>
- <span data-ttu-id="bca78-116">De hele lijst exporteren in CSV-indeling</span><span class="sxs-lookup"><span data-stu-id="bca78-116">Export the entire list in CSV format</span></span>
- <span data-ttu-id="bca78-117">Het aantal items selecteren dat per pagina moet worden weergegeven</span><span class="sxs-lookup"><span data-stu-id="bca78-117">Select the number of items to show per page</span></span>
- <span data-ttu-id="bca78-118">Filters toepassen</span><span class="sxs-lookup"><span data-stu-id="bca78-118">Apply filters</span></span>

<span data-ttu-id="bca78-119">Tijdens het onboardingproces wordt de lijst **Apparaten** geleidelijk gevuld met apparaten terwijl ze sensorgegevens beginnen te rapporteren.</span><span class="sxs-lookup"><span data-stu-id="bca78-119">During the onboarding process, the **Devices list** is gradually populated with devices as they begin to report sensor data.</span></span> <span data-ttu-id="bca78-120">Gebruik deze weergave om uw ingebouwde eindpunten bij te houden wanneer ze online komen, of download de volledige lijst met eindpunten als een CSV-bestand voor offlineanalyse.</span><span class="sxs-lookup"><span data-stu-id="bca78-120">Use this view to track your onboarded endpoints as they come online, or download the complete endpoint list as a CSV file for offline analysis.</span></span>

>[!NOTE]
> <span data-ttu-id="bca78-121">Als u de lijst met apparaten exporteert, bevat deze elk apparaat in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="bca78-121">If you export the device list, it will contain every device in your organization.</span></span> <span data-ttu-id="bca78-122">Het kan een aanzienlijke hoeveelheid tijd duren om te downloaden, afhankelijk van hoe groot uw organisatie is.</span><span class="sxs-lookup"><span data-stu-id="bca78-122">It might take a significant amount of time to download, depending on how large your organization is.</span></span> <span data-ttu-id="bca78-123">Als u de lijst exporteert in CSV-indeling, worden de gegevens op een ongefilterde manier weergegeven.</span><span class="sxs-lookup"><span data-stu-id="bca78-123">Exporting the list in CSV format displays the data in an unfiltered manner.</span></span> <span data-ttu-id="bca78-124">Het CSV-bestand bevat alle apparaten in de organisatie, ongeacht de filters die in de weergave zelf worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="bca78-124">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself.</span></span>

![Afbeelding van apparatenlijst met lijst met apparaten](images/device-list.png)

## <a name="sort-and-filter-the-device-list"></a><span data-ttu-id="bca78-126">De lijst met apparaten sorteren en filteren</span><span class="sxs-lookup"><span data-stu-id="bca78-126">Sort and filter the device list</span></span>

<span data-ttu-id="bca78-127">U kunt de volgende filters toepassen om de lijst met waarschuwingen te beperken en een meer gerichte weergave te krijgen.</span><span class="sxs-lookup"><span data-stu-id="bca78-127">You can apply the following filters to limit the list of alerts and get a more focused view.</span></span>

### <a name="risk-level"></a><span data-ttu-id="bca78-128">Risiconiveau</span><span class="sxs-lookup"><span data-stu-id="bca78-128">Risk level</span></span>

<span data-ttu-id="bca78-129">Het risiconiveau weerspiegelt de algemene risicobeoordeling van het apparaat op basis van een combinatie van factoren, waaronder het type en de ernst van actieve waarschuwingen op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="bca78-129">The risk level reflects the overall risk assessment of the device based on a combination of factors, including the types and severity of active alerts on the device.</span></span> <span data-ttu-id="bca78-130">Door actieve waarschuwingen op te lossen, herstelactiviteiten goed te keuren en volgende waarschuwingen te onderdrukken, kan het risiconiveau worden verlaagd.</span><span class="sxs-lookup"><span data-stu-id="bca78-130">Resolving active alerts, approving remediation activities, and suppressing subsequent alerts can lower the risk level.</span></span>

### <a name="exposure-level"></a><span data-ttu-id="bca78-131">Blootstellingsniveau</span><span class="sxs-lookup"><span data-stu-id="bca78-131">Exposure level</span></span>

<span data-ttu-id="bca78-132">Het blootstellingsniveau weerspiegelt de huidige blootstelling van het apparaat op basis van de cumulatieve impact van de beveiligingsaanbevelingen in behandeling.</span><span class="sxs-lookup"><span data-stu-id="bca78-132">The exposure level reflects the current exposure of the device based on the cumulative impact of its pending security recommendations.</span></span> <span data-ttu-id="bca78-133">De mogelijke niveaus zijn laag, gemiddeld en hoog.</span><span class="sxs-lookup"><span data-stu-id="bca78-133">The possible levels are low, medium, and high.</span></span> <span data-ttu-id="bca78-134">Lage blootstelling betekent dat uw apparaten minder kwetsbaar zijn voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="bca78-134">Low exposure means your devices are less vulnerable from exploitation.</span></span>

<span data-ttu-id="bca78-135">Als op het blootstellingsniveau 'Geen gegevens beschikbaar' staat, zijn er een paar redenen waarom dit het geval kan zijn:</span><span class="sxs-lookup"><span data-stu-id="bca78-135">If the exposure level says "No data available," there are a few reasons why this may be the case:</span></span>

- <span data-ttu-id="bca78-136">De rapportage van het apparaat is langer dan 30 dagen gestopt, in dat geval wordt het als inactief beschouwd en wordt de blootstelling niet berekend</span><span class="sxs-lookup"><span data-stu-id="bca78-136">Device stopped reporting for more than 30 days – in that case it is considered inactive, and the exposure isn't computed</span></span>
- <span data-ttu-id="bca78-137">Apparaat os niet ondersteund - zie [minimumvereisten voor Microsoft Defender voor Eindpunt](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="bca78-137">Device OS not supported - see [minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md)</span></span>
- <span data-ttu-id="bca78-138">Apparaat met verouderde agent (zeer onwaarschijnlijk)</span><span class="sxs-lookup"><span data-stu-id="bca78-138">Device with stale agent (very unlikely)</span></span>

### <a name="os-platform"></a><span data-ttu-id="bca78-139">Besturingssysteemplatform</span><span class="sxs-lookup"><span data-stu-id="bca78-139">OS Platform</span></span>

<span data-ttu-id="bca78-140">Selecteer alleen de besturingssysteemplatforms die u wilt onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="bca78-140">Select only the OS platforms you're interested in investigating.</span></span>

### <a name="health-state"></a><span data-ttu-id="bca78-141">Status</span><span class="sxs-lookup"><span data-stu-id="bca78-141">Health state</span></span>

<span data-ttu-id="bca78-142">Filteren op de volgende statussen van apparaten:</span><span class="sxs-lookup"><span data-stu-id="bca78-142">Filter by the following device health states:</span></span>

- <span data-ttu-id="bca78-143">**Actief:** apparaten die sensorgegevens actief aan de service rapporteren.</span><span class="sxs-lookup"><span data-stu-id="bca78-143">**Active** – Devices that are actively reporting sensor data to the service.</span></span>
- <span data-ttu-id="bca78-144">**Inactief:** apparaten die al meer dan 7 dagen geen signalen meer verzenden.</span><span class="sxs-lookup"><span data-stu-id="bca78-144">**Inactive** – Devices that have completely stopped sending signals for more than 7 days.</span></span>
- <span data-ttu-id="bca78-145">**Verkeerd geconfigureerd: apparaten** die communicatie met de service hebben beschadigd of die geen sensorgegevens kunnen verzenden.</span><span class="sxs-lookup"><span data-stu-id="bca78-145">**Misconfigured** – Devices that have impaired communications with service or are unable to send sensor data.</span></span> <span data-ttu-id="bca78-146">Verkeerd geconfigureerde apparaten kunnen verder worden geclassificeerd als:</span><span class="sxs-lookup"><span data-stu-id="bca78-146">Misconfigured devices can further be classified to:</span></span>
  - <span data-ttu-id="bca78-147">Geen sensorgegevens</span><span class="sxs-lookup"><span data-stu-id="bca78-147">No sensor data</span></span>
  - <span data-ttu-id="bca78-148">Communicatie met verminderde werking</span><span class="sxs-lookup"><span data-stu-id="bca78-148">Impaired communications</span></span>

  <span data-ttu-id="bca78-149">Zie Ongezonde sensoren oplossen voor meer informatie over het oplossen van problemen op verkeerd [geconfigureerde apparaten.](fix-unhealthy-sensors.md)</span><span class="sxs-lookup"><span data-stu-id="bca78-149">For more information on how to address issues on misconfigured devices see, [Fix unhealthy sensors](fix-unhealthy-sensors.md).</span></span>

### <a name="antivirus-status"></a><span data-ttu-id="bca78-150">Antivirusstatus</span><span class="sxs-lookup"><span data-stu-id="bca78-150">Antivirus status</span></span>

<span data-ttu-id="bca78-151">Apparaten filteren op antivirusstatus.</span><span class="sxs-lookup"><span data-stu-id="bca78-151">Filter devices by antivirus status.</span></span> <span data-ttu-id="bca78-152">Is alleen van toepassing op actieve Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="bca78-152">Applies to active Windows 10 devices only.</span></span>

- <span data-ttu-id="bca78-153">**Uitgeschakeld-** Virusbeveiliging & is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="bca78-153">**Disabled** - Virus & threat protection is turned off.</span></span>
- <span data-ttu-id="bca78-154">**Niet rapporteren:** virusbeveiliging & geen rapportage.</span><span class="sxs-lookup"><span data-stu-id="bca78-154">**Not reporting** - Virus & threat protection is not reporting.</span></span>
- <span data-ttu-id="bca78-155">**Niet bijgewerkt-** Virusbeveiliging & is niet up-to-date.</span><span class="sxs-lookup"><span data-stu-id="bca78-155">**Not updated** - Virus & threat protection is not up to date.</span></span>

<span data-ttu-id="bca78-156">Zie Het dashboard [Threat & Vulnerability Management weergeven voor meer informatie.](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="bca78-156">For more information, see [View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md).</span></span>

### <a name="threat-mitigation-status"></a><span data-ttu-id="bca78-157">Status van bedreigingsbeperking</span><span class="sxs-lookup"><span data-stu-id="bca78-157">Threat mitigation status</span></span>

<span data-ttu-id="bca78-158">Als u apparaten wilt weergeven die mogelijk worden beïnvloed door een bepaalde bedreiging, selecteert u de bedreiging in de vervolgkeuzelijst en selecteert u vervolgens welk beveiligingsaspect moet worden beperkt.</span><span class="sxs-lookup"><span data-stu-id="bca78-158">To view devices that may be affected by a certain threat, select the threat from the dropdown menu, and then select what vulnerability aspect needs to be mitigated.</span></span>

<span data-ttu-id="bca78-159">Zie Bedreigingsanalyse voor meer [informatie over bepaalde bedreigingen.](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="bca78-159">To learn more about certain threats, see [Threat analytics](threat-analytics.md).</span></span> <span data-ttu-id="bca78-160">Zie Threat [& Vulnerability Management voor](next-gen-threat-and-vuln-mgt.md)informatie over risicobeperking.</span><span class="sxs-lookup"><span data-stu-id="bca78-160">For mitigation information, see [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span>

### <a name="windows-10-version"></a><span data-ttu-id="bca78-161">Windows 10-versie</span><span class="sxs-lookup"><span data-stu-id="bca78-161">Windows 10 version</span></span>

<span data-ttu-id="bca78-162">Selecteer alleen de Windows 10-versies die u wilt onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="bca78-162">Select only the Windows 10 versions you're interested in investigating.</span></span>

### <a name="tags--groups"></a><span data-ttu-id="bca78-163">Tags & Groepen</span><span class="sxs-lookup"><span data-stu-id="bca78-163">Tags & Groups</span></span>

<span data-ttu-id="bca78-164">Filter de lijst op basis van de groepering en labeling die u aan afzonderlijke apparaten hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="bca78-164">Filter the list based on the grouping and tagging that you've added to individual devices.</span></span> <span data-ttu-id="bca78-165">Zie [Apparaatlabels maken en beheren](machine-tags.md) en [Apparaatgroepen maken en beheren.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="bca78-165">See [Create and manage device tags](machine-tags.md) and [Create and manage device groups](machine-groups.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="bca78-166">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="bca78-166">Related topics</span></span>

- [<span data-ttu-id="bca78-167">Apparaten onderzoeken in de lijst Microsoft Defender voor eindpuntapparaten</span><span class="sxs-lookup"><span data-stu-id="bca78-167">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
