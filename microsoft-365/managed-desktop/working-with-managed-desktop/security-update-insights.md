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
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941439"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="0d83a-103">Inzichten in Windows-beveiligingsupdates</span><span class="sxs-lookup"><span data-stu-id="0d83a-103">Windows security update insights</span></span>
<span data-ttu-id="0d83a-104">Deze weergave bevat een overzicht van de status van beveiligingsupdates voor uw beheerde bureaublad apparaten van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0d83a-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="0d83a-105">Als u gebruiksgegevens wilt weergeven, selecteert u het tabblad <strong>Windows-beveiligingsupdates</strong> .</span><span class="sxs-lookup"><span data-stu-id="0d83a-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Deelvenster Windows-beveiligingsupdates: staafgrafieken van de apparaatstatus en de versie bijwerken in de linkerkolom, de voortgang van de implementatie in de kolom gecentreerd bijwerken en het percentage actieve apparaten per implementatiegroep, en het aantal dagen dat het implementatie doel voor 95% in de rechterkolom is bereikt.](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="0d83a-107">Apparaatstatus</span><span class="sxs-lookup"><span data-stu-id="0d83a-107">Device status</span></span>

<span data-ttu-id="0d83a-108">Voor apparaten die moeten worden bijgewerkt door Windows Update, moeten ze verbinding hebben met internet en niet in de slaapstand gedurende minimaal zes uur, waarvan de slaapstand niet lang moet zijn.</span><span class="sxs-lookup"><span data-stu-id="0d83a-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="0d83a-109">Hoewel het mogelijk is dat een apparaat dat niet aan deze vereisten voldoet, wordt bijgewerkt, zijn de apparaten die aan hen voldoen de beste kans om te worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="0d83a-109">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="0d83a-110">De hardware-activiteit wordt in de context van Windows Update met deze voorwaarden gecategoriseerd:</span><span class="sxs-lookup"><span data-stu-id="0d83a-110">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="0d83a-111"><strong>Actief:</strong> Apparaten die voldoen aan de minimale activiteiten criteria (zes uur, twee continu) voor de meest recente update van beveiligingsupdates en met Microsoft intune minstens elke vijf dagen zijn ingecheckt</span><span class="sxs-lookup"><span data-stu-id="0d83a-111"><strong>Active:</strong> Devices that have met the minimum activity criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="0d83a-112"><strong>Gesynchroniseerd:</strong> Apparaten die zijn ingecheckt met intune in de afgelopen 28 dagen</span><span class="sxs-lookup"><span data-stu-id="0d83a-112"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="0d83a-113"><strong>Niet gesynchroniseerd:</strong> Apparaten die <i>niet</i> zijn ingecheckt met intune in de afgelopen 30 dagen</span><span class="sxs-lookup"><span data-stu-id="0d83a-113"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="0d83a-114">Versie status bijwerken</span><span class="sxs-lookup"><span data-stu-id="0d83a-114">Update version status</span></span>

<span data-ttu-id="0d83a-115">Microsoft brengt beveiligingsupdates elk de tweede dinsdag van de maand uit.</span><span class="sxs-lookup"><span data-stu-id="0d83a-115">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="0d83a-116">Met elke release worden belangrijke updates voor bekende beveiligingsproblemen opgeteld.</span><span class="sxs-lookup"><span data-stu-id="0d83a-116">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="0d83a-117">Microsoft Managed Desktop zorgt ervoor dat 95% van de beheerde apparaten wordt bijgewerkt met de nieuwste beschikbare beveiligingsupdate per maand.</span><span class="sxs-lookup"><span data-stu-id="0d83a-117">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="0d83a-118">Beveiligingsupdates worden soms op andere momenten uitgebracht om nieuwe bedreigingen dringend te verhelpen.</span><span class="sxs-lookup"><span data-stu-id="0d83a-118">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="0d83a-119">Microsoft Managed Desktop implementeert deze updates op een soortgelijke manier.</span><span class="sxs-lookup"><span data-stu-id="0d83a-119">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="0d83a-120">De status van de versies van beveiligingsupdate wordt met deze voorwaarden gecategoriseerd:</span><span class="sxs-lookup"><span data-stu-id="0d83a-120">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="0d83a-121"><strong>Huidig:</strong> Apparaten waarop de update is uitgebracht in de huidige maand</span><span class="sxs-lookup"><span data-stu-id="0d83a-121"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="0d83a-122"><strong>Vorige:</strong> Apparaten waarop de update wordt uitgevoerd die in de vorige maand werd uitgebracht</span><span class="sxs-lookup"><span data-stu-id="0d83a-122"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="0d83a-123"><strong>Ouder:</strong> Apparaten met een of meer beveiligingsupdates die zijn uitgebracht vóór de vorige maand</span><span class="sxs-lookup"><span data-stu-id="0d83a-123"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="0d83a-124">U ziet slechts enkele apparaten in de <strong>oudere</strong> categorie: een grote of groeiende populatie duidt waarschijnlijk op een probleem met het systeem aan dat u moet rapporteren voor Microsoft Managed Desktop, zodat we kunnen onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="0d83a-124">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="0d83a-125">Voortgang van implementatie</span><span class="sxs-lookup"><span data-stu-id="0d83a-125">Deployment progress</span></span>

<span data-ttu-id="0d83a-126">Aan het begin van elke release cyclus van beveiligingsupdates, wordt door Microsoft beheerde bureaubladtoepassing een momentopname van de bevolking van het apparaat gehouden en wordt het implementatie doel ingesteld op 95% van die populatie.</span><span class="sxs-lookup"><span data-stu-id="0d83a-126">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="0d83a-127">Het gebied voortgang van de <strong>implementatie</strong> toont een historische trend, bijgewerkt op dag, waarop u kunt nagaan hoe nauw de update-implementatie voor elke release aan deze doel voldoet.</span><span class="sxs-lookup"><span data-stu-id="0d83a-127">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="0d83a-128">Deze grafiek toont alleen apparaten met de actieve status.</span><span class="sxs-lookup"><span data-stu-id="0d83a-128">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="0d83a-129">U kunt deze gegevens voor eerdere update cycli weergeven met behulp van de vervolgkeuzelijst in de rechterbovenhoek.</span><span class="sxs-lookup"><span data-stu-id="0d83a-129">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="0d83a-130">De periode die u in dit menu hebt geselecteerd, is van toepassing op alle gegevens op de hele pagina.</span><span class="sxs-lookup"><span data-stu-id="0d83a-130">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="0d83a-131">Het gebied <strong>met bijgewerkte actieve apparaten per distributiegroep</strong> biedt een andere weergave door de voortgang van de installatie van de update te tonen voor elk van de beheerde groepen Microsoft Managed Desktop Deployment.</span><span class="sxs-lookup"><span data-stu-id="0d83a-131">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="0d83a-132">In het <strong>doelgebied dagen voor bereiken</strong> wordt de duur van 95% van het totale aantal apparaten dat wordt bijgewerkt met de huidige beveiligingsupdate weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0d83a-132">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="0d83a-133">Tijdens de implementatie wordt dit gebied <strong>nog steeds bijgewerkt</strong> totdat het 95% target voor de geselecteerde update is bereikt.</span><span class="sxs-lookup"><span data-stu-id="0d83a-133">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="0d83a-134">Gebied Details van apparaat</span><span class="sxs-lookup"><span data-stu-id="0d83a-134">Device details area</span></span>

<span data-ttu-id="0d83a-135">De onderkant van het dashboard is een tabel met gedetailleerde informatie voor uw apparaten, waaronder de status van het [apparaat](#device-status) en de [status van update versies](#update-version-status).</span><span class="sxs-lookup"><span data-stu-id="0d83a-135">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="0d83a-136">U kunt deze lijst doorzoeken of filteren op een waarde in de lijst.</span><span class="sxs-lookup"><span data-stu-id="0d83a-136">You can search this list or filter it by any listed value.</span></span>


![De tabel apparaatgegevens met de kolommen voor de naam van het apparaat, de toegewezen gebruiker, de apparaatstatus, de versie van het besturingssysteem, de versie van het besturingssysteem en de datum waarop het apparaat de laatste keer is gesynchroniseerd.](../../media/security-update-insights-device-table-sterile.png)
