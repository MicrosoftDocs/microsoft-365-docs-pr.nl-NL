---
title: Inzichten over Windows-beveiligingsupdate
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ef2d5c897709e7f7d2484d032b7471031be77d74
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/29/2020
ms.locfileid: "42805586"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="fffe2-103">Inzichten over Windows-beveiligingsupdate</span><span class="sxs-lookup"><span data-stu-id="fffe2-103">Windows security update insights</span></span>
<span data-ttu-id="fffe2-104">In deze weergave vindt u een overzicht van de status van beveiligingsupdates voor uw Microsoft Managed Desktop-apparaten.</span><span class="sxs-lookup"><span data-stu-id="fffe2-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="fffe2-105">Als u gebruiksgegevens wilt weergeven, selecteert u het tabblad <strong>Windows-beveiligingsupdates.</strong></span><span class="sxs-lookup"><span data-stu-id="fffe2-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Windows-beveiligingsupdates: weergrafieken van de apparaatstatus en updateversie in de linkerkolom, update implementatievoortgang in de loop van de tijd in middelste kolom en percentage actieve apparaten per implementatiegroep, evenals het aantal dagen dat nodig is om de implementatie van 95% te bereiken doel in de rechterkolom.](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="fffe2-107">Apparaatstatus</span><span class="sxs-lookup"><span data-stu-id="fffe2-107">Device status</span></span>

<span data-ttu-id="fffe2-108">Voor apparaten die door Windows Update moeten worden bijgewerkt, moeten ze zijn verbonden met het internet en niet gedurende minimaal zes uur in de sluimerstand zijn, waarvan er twee continu moeten zijn.</span><span class="sxs-lookup"><span data-stu-id="fffe2-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="fffe2-109">Zolang een apparaat is aangesloten en niet in de sluimerstand, wordt het beschouwd als "in gebruik."</span><span class="sxs-lookup"><span data-stu-id="fffe2-109">As long as a device is connected and not hibernating, it's considered to be "in use."</span></span> <span data-ttu-id="fffe2-110">Hoewel het mogelijk is dat een apparaat dat niet aan deze vereisten voldoet, wordt bijgewerkt, hebben apparaten die eraan voldoen de grootste kans om te worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="fffe2-110">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="fffe2-111">We categoriseren apparaatactiviteit in de context van Windows Update met de volgende termen:</span><span class="sxs-lookup"><span data-stu-id="fffe2-111">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="fffe2-112"><strong>Actief:</strong> Apparaten die hebben voldaan aan de minimale gebruikscriteria (zes uur, twee continu) voor de meest recente versie van de beveiligingsupdate en ten minste om de vijf dagen hebben ingecheckt bij Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="fffe2-112"><strong>Active:</strong> Devices that have met the minimum usage criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="fffe2-113"><strong>Gesynchroniseerd:</strong> Apparaten die in de afgelopen 28 dagen zijn ingecheckt bij Intune</span><span class="sxs-lookup"><span data-stu-id="fffe2-113"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="fffe2-114"><strong>Niet synchroon:</strong> Apparaten die de afgelopen 28 dagen <i>niet</i> zijn ingecheckt bij Intune</span><span class="sxs-lookup"><span data-stu-id="fffe2-114"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="fffe2-115">Versiestatus bijwerken</span><span class="sxs-lookup"><span data-stu-id="fffe2-115">Update version status</span></span>

<span data-ttu-id="fffe2-116">Microsoft brengt elke tweede dinsdag van de maand beveiligingsupdates uit.</span><span class="sxs-lookup"><span data-stu-id="fffe2-116">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="fffe2-117">Elke release voegt belangrijke updates toe voor bekende beveiligingsproblemen.</span><span class="sxs-lookup"><span data-stu-id="fffe2-117">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="fffe2-118">Microsoft Managed Desktop zorgt ervoor dat 95% van de beheerde apparaten elke maand wordt bijgewerkt met de nieuwste beschikbare beveiligingsupdate.</span><span class="sxs-lookup"><span data-stu-id="fffe2-118">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="fffe2-119">Beveiligingsupdates worden soms op andere momenten uitgebracht om nieuwe bedreigingen dringend aan te pakken.</span><span class="sxs-lookup"><span data-stu-id="fffe2-119">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="fffe2-120">Microsoft Managed Desktop implementeert deze updates op een vergelijkbare manier.</span><span class="sxs-lookup"><span data-stu-id="fffe2-120">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="fffe2-121">We categoriseren de status van beveiligingsupdateversies met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="fffe2-121">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="fffe2-122"><strong>Stroom:</strong> Apparaten waarop de update wordt uitgevoerd die in de huidige maand is uitgebracht</span><span class="sxs-lookup"><span data-stu-id="fffe2-122"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="fffe2-123"><strong>Vorige:</strong> Apparaten met de update die in de vorige maand is uitgebracht</span><span class="sxs-lookup"><span data-stu-id="fffe2-123"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="fffe2-124"><strong>Ouder:</strong> Apparaten met een beveiligingsupdate die vóór de vorige maand is uitgebracht</span><span class="sxs-lookup"><span data-stu-id="fffe2-124"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="fffe2-125">U ziet weinig apparaten in de <strong>oudere</strong> categorie - een grote of groeiende populatie duidt waarschijnlijk op een systemisch probleem dat u moet rapporteren aan Microsoft Managed Desktop, zodat we dit kunnen onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="fffe2-125">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="fffe2-126">Implementatievoortgang</span><span class="sxs-lookup"><span data-stu-id="fffe2-126">Deployment progress</span></span>

<span data-ttu-id="fffe2-127">Aan het begin van elke releasecyclus van elke beveiligingsupdate maakt Microsoft Managed Desktop een momentopname van de apparaatpopulatie en stelt het implementatiedoel in op 95% van die populatie.</span><span class="sxs-lookup"><span data-stu-id="fffe2-127">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="fffe2-128">Het <strong>voortgangsgebied Implementatie</strong> toont een historische trend, die dagelijks wordt bijgewerkt en bijhoudt hoe nauw de update-implementatie aan dit doel voldoet voor elke release.</span><span class="sxs-lookup"><span data-stu-id="fffe2-128">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="fffe2-129">Deze grafiek toont alleen apparaten met de actieve status.</span><span class="sxs-lookup"><span data-stu-id="fffe2-129">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="fffe2-130">U deze gegevens voor eerdere updatecycli bekijken met behulp van het vervolgkeuzemenu rechtsboven.</span><span class="sxs-lookup"><span data-stu-id="fffe2-130">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="fffe2-131">De periode die u selecteert in dit menu is van toepassing op alle informatie op de hele pagina.</span><span class="sxs-lookup"><span data-stu-id="fffe2-131">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="fffe2-132">Het gebied <strong>Actieve apparaten bijgewerkt op implementatiegroep</strong> biedt een andere weergave door de voortgang van de update-installatie voor elk van de microsoft Managed Desktop-implementatiegroepen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="fffe2-132">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="fffe2-133">De <strong>dagen om het doelgebied te bereiken,</strong> geeft aan hoe lang het duurde voordat 95% van het totale aantal apparaten werd bijgewerkt met de huidige beveiligingsupdate.</span><span class="sxs-lookup"><span data-stu-id="fffe2-133">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="fffe2-134">Terwijl de implementatie aan de gang is, wordt in dit gebied <strong>nog steeds bijgewerkt</strong> totdat de doelstelling van 95% is bereikt voor de geselecteerde update.</span><span class="sxs-lookup"><span data-stu-id="fffe2-134">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="fffe2-135">Gebied Apparaatdetails</span><span class="sxs-lookup"><span data-stu-id="fffe2-135">Device details area</span></span>

<span data-ttu-id="fffe2-136">Onder aan het dashboard vindt u een tabel met gedetailleerde informatie voor uw apparaten, waaronder de [apparaatstatus](#device-status) en de [status van de updateversie.](#update-version-status)</span><span class="sxs-lookup"><span data-stu-id="fffe2-136">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="fffe2-137">U deze lijst doorzoeken of filteren op een vermelde waarde.</span><span class="sxs-lookup"><span data-stu-id="fffe2-137">You can search this list or filter it by any listed value.</span></span>


![Tabel Met tabel met apparaatdetails met kolommen voor apparaatnaam, toegewezen gebruiker, apparaatstatus, updateversie, versie van het besturingssysteem en de datum waarop het apparaat het laatst is gesynchroniseerd.](../../media/security-update-insights-device-table-sterile.png)
