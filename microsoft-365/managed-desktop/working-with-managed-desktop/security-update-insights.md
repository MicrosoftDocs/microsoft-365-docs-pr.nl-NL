---
title: Inzichten in Windows-beveiligingsupdates
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3b1f43217b3be285f20925065bf9710a38f9606
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739795"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="87907-103">Inzichten in Windows-beveiligingsupdates</span><span class="sxs-lookup"><span data-stu-id="87907-103">Windows security update insights</span></span>
<span data-ttu-id="87907-104">Deze weergave bevat een overzicht van de status van beveiligingsupdates voor uw Microsoft Managed Desktop apparaten.</span><span class="sxs-lookup"><span data-stu-id="87907-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="87907-105">Als u gebruiksgegevens wilt weergeven, selecteert <strong>u Windows tabblad Beveiligingsupdates.</strong></span><span class="sxs-lookup"><span data-stu-id="87907-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Windows beveiligingsupdatesvenster: staafdiagrammen van de apparaatstatus en updateversie in de linkerkolom, de voortgang van de implementatie bijwerken in de middelste kolom en het percentage actieve apparaten per implementatiegroep, evenals het aantal dagen dat nodig is om het implementatiedoel van 95% in de rechterkolom te bereiken.](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="87907-107">Apparaatstatus</span><span class="sxs-lookup"><span data-stu-id="87907-107">Device status</span></span>

<span data-ttu-id="87907-108">Als apparaten worden bijgewerkt door Windows Update, moeten ze zijn verbonden met internet en niet gedurende minimaal zes uur in de slaapstand blijven staan, waarvan er twee doorlopend moeten zijn.</span><span class="sxs-lookup"><span data-stu-id="87907-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="87907-109">Hoewel het mogelijk is dat een apparaat dat niet aan deze vereisten voldoet, wordt bijgewerkt, hebben apparaten die aan deze apparaten voldoen de grootste kans dat ze worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="87907-109">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="87907-110">We categoriseren apparaatactiviteit in de context van Windows Bijwerken met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="87907-110">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="87907-111"><strong>Actief:</strong> Apparaten die voldoen aan de minimumactiviteitscriteria (zes uur, twee doorlopend) voor de meest recente release van beveiligingsupdates en die zich ten minste om de vijf dagen met Microsoft Intune hebben ingecheckt</span><span class="sxs-lookup"><span data-stu-id="87907-111"><strong>Active:</strong> Devices that have met the minimum activity criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="87907-112"><strong>Gesynchroniseerd:</strong> Apparaten die in de afgelopen 28 dagen met Intune zijn ingecheckt</span><span class="sxs-lookup"><span data-stu-id="87907-112"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="87907-113"><strong>Niet gesynchroniseerd:</strong> Apparaten die de <i>afgelopen</i> 28 dagen niet zijn ingecheckt met Intune</span><span class="sxs-lookup"><span data-stu-id="87907-113"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="87907-114">Versiestatus bijwerken</span><span class="sxs-lookup"><span data-stu-id="87907-114">Update version status</span></span>

<span data-ttu-id="87907-115">Microsoft brengt elke tweede dinsdag van de maand beveiligingsupdates uit.</span><span class="sxs-lookup"><span data-stu-id="87907-115">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="87907-116">Elke release voegt belangrijke updates toe voor bekende beveiligingsproblemen.</span><span class="sxs-lookup"><span data-stu-id="87907-116">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="87907-117">Microsoft Managed Desktop zorgt ervoor dat 95% van de beheerde apparaten elke maand wordt bijgewerkt met de meest recente beveiligingsupdate.</span><span class="sxs-lookup"><span data-stu-id="87907-117">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="87907-118">Beveiligingsupdates worden soms op andere momenten uitgebracht om nieuwe bedreigingen dringend aan te pakken.</span><span class="sxs-lookup"><span data-stu-id="87907-118">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="87907-119">Microsoft Managed Desktop worden deze updates op een vergelijkbare manier geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="87907-119">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="87907-120">We categoriseren de status van beveiligingsupdateversies met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="87907-120">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="87907-121"><strong>Huidige:</strong> Apparaten met de update die in de huidige maand is uitgebracht</span><span class="sxs-lookup"><span data-stu-id="87907-121"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="87907-122"><strong>Vorige:</strong> Apparaten met de update die in de vorige maand is uitgebracht</span><span class="sxs-lookup"><span data-stu-id="87907-122"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="87907-123"><strong>Ouder:</strong> Apparaten met een beveiligingsupdate die vóór de vorige maand is uitgebracht</span><span class="sxs-lookup"><span data-stu-id="87907-123"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="87907-124">U ziet weinig apparaten <strong></strong> in de categorie Ouder. Een grote of groeiende populatie geeft waarschijnlijk een systeemprobleem aan dat u moet rapporteren aan Microsoft Managed Desktop zodat we dit kunnen onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="87907-124">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="87907-125">Implementatie-voortgang</span><span class="sxs-lookup"><span data-stu-id="87907-125">Deployment progress</span></span>

<span data-ttu-id="87907-126">Aan het begin van elke releasecyclus voor beveiligingsupdates maakt Microsoft Managed Desktop momentopname van de apparaatpopulatie en stelt u het implementatiedoel in op 95% van die populatie.</span><span class="sxs-lookup"><span data-stu-id="87907-126">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="87907-127">Het <strong>gebied Implementatie-voortgang</strong> toont een historische trend die dagelijks wordt bijgewerkt en die bij houdt hoe nauw de update-implementatie aan dit doel voor elke release voldoet.</span><span class="sxs-lookup"><span data-stu-id="87907-127">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="87907-128">In deze grafiek ziet u alleen apparaten met de actieve status.</span><span class="sxs-lookup"><span data-stu-id="87907-128">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="87907-129">U kunt deze gegevens voor eerdere updatecyclussen bekijken met behulp van de vervolgkeuzelijst in de rechterbovenhoek.</span><span class="sxs-lookup"><span data-stu-id="87907-129">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="87907-130">De periode die u in dit menu selecteert, is van toepassing op alle informatie op de hele pagina.</span><span class="sxs-lookup"><span data-stu-id="87907-130">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="87907-131">Het <strong>gebied Bijgewerkte actieve apparaten per</strong> implementatiegroep biedt een andere weergave door de voortgang van de update-installatie weer te geven voor elk van de Microsoft Managed Desktop implementatiegroepen.</span><span class="sxs-lookup"><span data-stu-id="87907-131">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="87907-132">In <strong>het doelgebied</strong> Dagen wordt weergegeven hoe lang het duurde voordat 95% van het totale aantal apparaten werd bijgewerkt met de huidige beveiligingsupdate.</span><span class="sxs-lookup"><span data-stu-id="87907-132">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="87907-133">Terwijl de implementatie aan de gang is, wordt in dit gebied <strong>Nog steeds</strong> bijgewerkt weergegeven totdat het doel van 95% is bereikt voor de geselecteerde update.</span><span class="sxs-lookup"><span data-stu-id="87907-133">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="87907-134">Gebied met apparaatdetails</span><span class="sxs-lookup"><span data-stu-id="87907-134">Device details area</span></span>

<span data-ttu-id="87907-135">De onderkant van het dashboard is een tabel met gedetailleerde informatie voor uw apparaten, waaronder de [apparaatstatus](#device-status) en de [versiestatus Bijwerken.](#update-version-status)</span><span class="sxs-lookup"><span data-stu-id="87907-135">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="87907-136">U kunt in deze lijst zoeken of filteren op elke weergegeven waarde.</span><span class="sxs-lookup"><span data-stu-id="87907-136">You can search this list or filter it by any listed value.</span></span>


![Tabel apparaatdetails met kolommen voor de naam van het apparaat, de toegewezen gebruiker, de apparaatstatus, de updateversie, de versie van het besturingssysteem en de datum waarop het apparaat het laatst is gesynchroniseerd.](../../media/security-update-insights-device-table-sterile.png)
