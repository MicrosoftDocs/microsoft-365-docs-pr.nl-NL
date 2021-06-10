---
title: Apparaatprofiel in Microsoft 365 beveiligingsportal
description: Bekijk de risico- en blootstellingsniveaus voor een apparaat in uw organisatie. Analyseer eerdere en huidige bedreigingen en bescherm het apparaat met de meest recente updates.
keywords: beveiliging, malware, Microsoft 365, M365, Microsoft 365 Defender, beveiligingscentrum, Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365, Microsoft Defender voor identiteit, apparaatpagina, apparaatprofiel, machinepagina, machineprofiel
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 8e2788fd9163a27b41bd3788facf5fc9623b0543
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935663"
---
# <a name="device-profile-page"></a><span data-ttu-id="af8db-105">Pagina Apparaatprofiel</span><span class="sxs-lookup"><span data-stu-id="af8db-105">Device profile page</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="af8db-106">De Microsoft 365 beveiligingsportal biedt u apparaatprofielpagina's, zodat u snel de status en status van apparaten in uw netwerk kunt beoordelen.</span><span class="sxs-lookup"><span data-stu-id="af8db-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af8db-107">De pagina apparaatprofiel ziet er mogelijk iets anders uit, afhankelijk van of het apparaat is geregistreerd bij Microsoft Defender voor Eindpunt, Microsoft Defender voor identiteit of beide.</span><span class="sxs-lookup"><span data-stu-id="af8db-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender for Endpoint, Microsoft Defender for Identity, or both.</span></span>

<span data-ttu-id="af8db-108">Als het apparaat is geregistreerd bij Microsoft Defender voor Eindpunt, kunt u ook de profielpagina van het apparaat gebruiken om enkele algemene beveiligingstaken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="af8db-108">If the device is enrolled in Microsoft Defender for Endpoint, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="af8db-109">Navigeren op de pagina apparaatprofiel</span><span class="sxs-lookup"><span data-stu-id="af8db-109">Navigating the device profile page</span></span>

<span data-ttu-id="af8db-110">De profielpagina is onderverdeeld in verschillende brede secties.</span><span class="sxs-lookup"><span data-stu-id="af8db-110">The profile page is broken up into several broad sections.</span></span>

![Afbeelding van de pagina apparaatprofiel met (1) Tabbladgebied (2) Zijbalk en (3) Acties gemarkeerd in rood](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="af8db-112">De zijbalk (1) bevat basisgegevens over het apparaat.</span><span class="sxs-lookup"><span data-stu-id="af8db-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="af8db-113">Het gebied met de hoofdinhoud (2) bevat tabbladen waar u doorheen kunt schakelen om verschillende soorten informatie over het apparaat weer te geven.</span><span class="sxs-lookup"><span data-stu-id="af8db-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="af8db-114">Als het apparaat is geregistreerd bij Microsoft Defender voor Eindpunt, ziet u ook een lijst met antwoordacties (3).</span><span class="sxs-lookup"><span data-stu-id="af8db-114">If the device is enrolled in Microsoft Defender for Endpoint, you will also see a list of response actions (3).</span></span> <span data-ttu-id="af8db-115">Met antwoordacties kunt u algemene beveiligingstaken uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="af8db-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="af8db-116">Zijbalk</span><span class="sxs-lookup"><span data-stu-id="af8db-116">Sidebar</span></span>

<span data-ttu-id="af8db-117">Naast het hoofdinhoudsgebied van de pagina apparaatprofiel staat de zijbalk.</span><span class="sxs-lookup"><span data-stu-id="af8db-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![Afbeelding van zijbalktabblad voor apparaatprofiel](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="af8db-119">De zijbalk bevat de volledige naam en het blootstellingsniveau van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="af8db-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="af8db-120">Het bevat ook enkele belangrijke basisinformatie in kleine subsecties die u kunt openen of sluiten, zoals:</span><span class="sxs-lookup"><span data-stu-id="af8db-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="af8db-121">**Tags:** alle Microsoft Defender voor eindpunten, Microsoft Defender voor identiteit of aangepaste tags die aan het apparaat zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="af8db-121">**Tags** - Any Microsoft Defender for Endpoint, Microsoft Defender for Identity, or custom tags associated with the device.</span></span> <span data-ttu-id="af8db-122">Tags van Microsoft Defender voor identiteit kunnen niet worden bewerkt.</span><span class="sxs-lookup"><span data-stu-id="af8db-122">Tags from Microsoft Defender for Identity are not editable.</span></span>
* <span data-ttu-id="af8db-123">**Beveiligingsgegevens:** open incidenten en actieve waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="af8db-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="af8db-124">Apparaten die zijn geregistreerd in Microsoft Defender voor Eindpunt, worden ook blootstellingsniveau en risiconiveau weergegeven.</span><span class="sxs-lookup"><span data-stu-id="af8db-124">Devices enrolled in Microsoft Defender for Endpoint will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="af8db-125">Blootstellingsniveau heeft betrekking op hoeveel het apparaat voldoet aan beveiligingsaanbevelingen, terwijl het risiconiveau wordt berekend op basis van een aantal factoren, waaronder de typen en ernst van actieve waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="af8db-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="af8db-126">**Apparaatgegevens:** domein, besturingssysteem, tijdstempel voor wanneer het apparaat voor het eerst werd gezien, IP-adressen, resources.</span><span class="sxs-lookup"><span data-stu-id="af8db-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="af8db-127">Apparaten die zijn geregistreerd in Microsoft Defender voor Eindpunt, geven ook de status status weer.</span><span class="sxs-lookup"><span data-stu-id="af8db-127">Devices enrolled in Microsoft Defender for Endpoint also display health state.</span></span> <span data-ttu-id="af8db-128">Apparaten die zijn geregistreerd bij Microsoft Defender voor identiteit, geven de SAM-naam en een tijdstempel weer voor wanneer het apparaat voor het eerst is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="af8db-128">Devices enrolled in Microsoft Defender for Identity will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="af8db-129">**Netwerkactiviteit:** timestamps voor de eerste keer en de laatste keer dat het apparaat op het netwerk is gezien.</span><span class="sxs-lookup"><span data-stu-id="af8db-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="af8db-130">**Adreslijstgegevens** ( alleen voor apparaten die zijn geregistreerd *bij Microsoft Defender voor* identiteit) - [UAC-vlaggen,](/windows/security/identity-protection/user-account-control/user-account-control-overview) [SPN's](/windows/win32/ad/service-principal-names)en groepslidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="af8db-130">**Directory data** (*only for devices enrolled in Microsoft Defender for Identity*) - [UAC](/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="af8db-131">Reactieacties</span><span class="sxs-lookup"><span data-stu-id="af8db-131">Response actions</span></span>

<span data-ttu-id="af8db-132">Reactieacties bieden een snelle manier om bedreigingen te beschermen en te analyseren.</span><span class="sxs-lookup"><span data-stu-id="af8db-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Afbeelding van actiebalk voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="af8db-134">[Antwoordacties](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) zijn alleen beschikbaar als het apparaat is geregistreerd bij Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="af8db-134">[Response actions](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender for Endpoint.</span></span>
> * <span data-ttu-id="af8db-135">Apparaten die zijn geregistreerd in Microsoft Defender voor Eindpunt, kunnen verschillende aantallen antwoordacties weergeven, op basis van het besturingssysteem en versienummer van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="af8db-135">Devices that are enrolled in Microsoft Defender for Endpoint may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="af8db-136">Acties die beschikbaar zijn op de pagina apparaatprofiel zijn:</span><span class="sxs-lookup"><span data-stu-id="af8db-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="af8db-137">**Tags beheren:** hiermee worden aangepaste tags bijgewerkt die u op dit apparaat hebt toegepast.</span><span class="sxs-lookup"><span data-stu-id="af8db-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="af8db-138">**Apparaat isoleren:** isoleert het apparaat van het netwerk van uw organisatie terwijl het verbonden blijft met Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="af8db-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="af8db-139">U kunt ervoor kiezen om Outlook, Teams en Skype voor Bedrijven te laten uitvoeren terwijl het apparaat is geïsoleerd, voor communicatiedoeleinden.</span><span class="sxs-lookup"><span data-stu-id="af8db-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="af8db-140">**Actiecentrum:** de status van ingediende acties weergeven.</span><span class="sxs-lookup"><span data-stu-id="af8db-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="af8db-141">Alleen beschikbaar als er al een andere actie is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="af8db-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="af8db-142">**De uitvoering van apps beperken:** voorkomt dat toepassingen die niet door Microsoft zijn ondertekend, worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="af8db-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="af8db-143">**Antivirusscan uitvoeren:** updates Windows Defender Antivirus definities en voert onmiddellijk een antivirusscan uit.</span><span class="sxs-lookup"><span data-stu-id="af8db-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="af8db-144">Kies tussen Snel scannen of Volledige scan.</span><span class="sxs-lookup"><span data-stu-id="af8db-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="af8db-145">**Onderzoekspakket verzamelen:** verzamelt informatie over het apparaat.</span><span class="sxs-lookup"><span data-stu-id="af8db-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="af8db-146">Wanneer het onderzoek is voltooid, kunt u het downloaden.</span><span class="sxs-lookup"><span data-stu-id="af8db-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="af8db-147">**Live-antwoordsessie starten:** laadt een externe shell op het apparaat voor [uitgebreide beveiligingsonderzoeken.](/microsoft-365/security/defender-endpoint/live-response)</span><span class="sxs-lookup"><span data-stu-id="af8db-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](/microsoft-365/security/defender-endpoint/live-response).</span></span>
* <span data-ttu-id="af8db-148">**Automatisch onderzoek starten:** automatisch bedreigingen onderzoeken en [corrigeren.](../office-365-security/office-365-air.md)</span><span class="sxs-lookup"><span data-stu-id="af8db-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](../office-365-security/office-365-air.md).</span></span> <span data-ttu-id="af8db-149">Hoewel u handmatig automatische onderzoeken kunt activeren om vanaf deze pagina uit te [voeren,](../../compliance/alert-policies.md?view=o365-worldwide#default-alert-policies) worden bepaalde waarschuwingsbeleidsregels automatisch uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="af8db-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](../../compliance/alert-policies.md?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="af8db-150">**Actiecentrum:** geeft informatie weer over alle antwoordacties die momenteel worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="af8db-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="af8db-151">Sectie Tabbladen</span><span class="sxs-lookup"><span data-stu-id="af8db-151">Tabs section</span></span>

<span data-ttu-id="af8db-152">Met de tabbladen van het apparaatprofiel kunt u door een overzicht schakelen van beveiligingsdetails over het apparaat en tabellen met een lijst met waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="af8db-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="af8db-153">Apparaten die zijn geregistreerd in Microsoft Defender voor Eindpunt, bevatten ook tabbladen met een tijdlijn, een lijst met beveiligingsaanbevelingen, een softwarevoorraad, een lijst met gevonden beveiligingsproblemen en ontbrekende KBs (beveiligingsupdates).</span><span class="sxs-lookup"><span data-stu-id="af8db-153">Devices enrolled in Microsoft Defender for Endpoint will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="af8db-154">Tabblad Overzicht</span><span class="sxs-lookup"><span data-stu-id="af8db-154">Overview tab</span></span>

<span data-ttu-id="af8db-155">Het standaardtabblad is **Overzicht.**</span><span class="sxs-lookup"><span data-stu-id="af8db-155">The default tab is **Overview**.</span></span> <span data-ttu-id="af8db-156">Het biedt een beknopt overzicht van het belangrijkste beveiligings feit over het apparaat.</span><span class="sxs-lookup"><span data-stu-id="af8db-156">It provides a quick look at the most important security fact about the device.</span></span>

![Afbeelding van overzichtstabblad voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="af8db-158">Hier kunt u de actieve waarschuwingen van het apparaat en alle gebruikers die momenteel zijn aangemeld, snel bekijken.</span><span class="sxs-lookup"><span data-stu-id="af8db-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="af8db-159">Als het apparaat is geregistreerd bij Microsoft Defender voor Eindpunt, ziet u ook het risiconiveau van het apparaat en alle beschikbare gegevens over beveiligingsbeoordelingen.</span><span class="sxs-lookup"><span data-stu-id="af8db-159">If the device is enrolled in Microsoft Defender for Endpoint, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="af8db-160">In de beveiligingsbeoordelingen wordt het blootstellingsniveau van het apparaat beschreven, worden beveiligingsaanbevelingen gegeven en worden getroffen software vermeld en zijn beveiligingsproblemen ontdekt.</span><span class="sxs-lookup"><span data-stu-id="af8db-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="af8db-161">Tabblad Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="af8db-161">Alerts tab</span></span>

<span data-ttu-id="af8db-162">Het **tabblad** Waarschuwingen bevat een lijst met waarschuwingen die zijn opgeheven op het apparaat, van zowel Microsoft Defender voor identiteit als Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="af8db-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span>

![Afbeelding van het tabblad Waarschuwingen voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="af8db-164">U kunt het aantal weergegeven items aanpassen, evenals welke kolommen voor elk item worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="af8db-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="af8db-165">Het standaardgedrag is om dertig items per pagina op te geven.</span><span class="sxs-lookup"><span data-stu-id="af8db-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="af8db-166">De kolommen op dit tabblad bevatten informatie over de ernst van de bedreiging die de waarschuwing heeft geactiveerd, evenals de status, de onderzoeksstatus en aan wie de waarschuwing is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="af8db-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="af8db-167">De *kolom beïnvloede entiteiten* verwijst naar het apparaat (entiteit) waarvan u momenteel het profiel bekijkt, plus alle andere apparaten in uw netwerk die van invloed zijn.</span><span class="sxs-lookup"><span data-stu-id="af8db-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="af8db-168">Als u een item selecteert in deze lijst, wordt er een flyout geopend met nog meer informatie over de geselecteerde waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="af8db-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="af8db-169">Deze lijst kan worden gefilterd op ernst, status of aan wie de waarschuwing is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="af8db-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="af8db-170">Tabblad Tijdlijn</span><span class="sxs-lookup"><span data-stu-id="af8db-170">Timeline tab</span></span>

<span data-ttu-id="af8db-171">Het **tabblad** Tijdlijn bevat een interactief, chronologisch diagram met alle gebeurtenissen die op het apparaat worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="af8db-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="af8db-172">Door het gemarkeerde gebied van de grafiek naar links of rechts te verplaatsen, kunt u gebeurtenissen over verschillende perioden bekijken.</span><span class="sxs-lookup"><span data-stu-id="af8db-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="af8db-173">U kunt ook een aangepast datumbereik kiezen in de vervolgkeuzelijst tussen de interactieve grafiek en de lijst met gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="af8db-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="af8db-174">Onder de grafiek staat een lijst met gebeurtenissen voor het geselecteerde datumbereik.</span><span class="sxs-lookup"><span data-stu-id="af8db-174">Below the chart is a list of events for the selected range of dates.</span></span>

![Afbeelding van het tabblad Tijdlijn voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="af8db-176">Het aantal weergegeven items en de kolommen in de lijst kunnen beide worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="af8db-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="af8db-177">De standaardkolommen bevatten de gebeurtenistijd, actieve gebruiker, actietype, entiteiten (processen) en aanvullende informatie over de gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="af8db-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="af8db-178">Als u een item selecteert in deze lijst, wordt een flyout geopend waarin een grafiek met gebeurtenis-entiteiten wordt weergegeven, met de bovenliggende en onderliggende processen die betrokken zijn bij de gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="af8db-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="af8db-179">De lijst kan worden gefilterd op het specifieke type gebeurtenis. bijvoorbeeld registergebeurtenissen of Smart Screen-gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="af8db-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="af8db-180">De lijst kan ook worden geëxporteerd naar een CSV-bestand, om deze te downloaden.</span><span class="sxs-lookup"><span data-stu-id="af8db-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="af8db-181">Hoewel het bestand niet wordt beperkt door het aantal gebeurtenissen, is het maximale tijdsbereik dat u kunt kiezen om te exporteren zeven dagen.</span><span class="sxs-lookup"><span data-stu-id="af8db-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="af8db-182">Tabblad Beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="af8db-182">Security recommendations tab</span></span>

<span data-ttu-id="af8db-183">Het **tabblad Beveiligingsaanbevelingen** bevat acties die u kunt uitvoeren om het apparaat te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="af8db-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="af8db-184">Als u een item in deze lijst selecteert, wordt een flyout geopend waarin u instructies kunt krijgen over het toepassen van de aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="af8db-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Afbeelding van het tabblad Beveiligingsaanbevelingen voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="af8db-186">Net als bij de vorige tabbladen kan het aantal items dat per pagina wordt weergegeven en welke kolommen zichtbaar zijn, worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="af8db-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="af8db-187">De standaardweergave bevat kolommen met details over de beveiligingszwakheden die zijn aangepakt, de bijbehorende bedreiging, het gerelateerde onderdeel of de software die door de bedreiging wordt beïnvloed, en meer.</span><span class="sxs-lookup"><span data-stu-id="af8db-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="af8db-188">Items kunnen worden gefilterd op de status van de aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="af8db-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="af8db-189">Software-inventaris</span><span class="sxs-lookup"><span data-stu-id="af8db-189">Software inventory</span></span>

<span data-ttu-id="af8db-190">Op **het tabblad Softwarevoorraad** wordt software weergegeven die op het apparaat is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="af8db-190">The **Software inventory** tab lists software installed on the device.</span></span>

![Afbeelding van het tabblad Softwarevoorraad voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="af8db-192">In de standaardweergave worden de softwareleverancier, het geïnstalleerde versienummer, het aantal bekende softwarezwaktes, bedreigingsinzichten, productcode en tags weergegeven.</span><span class="sxs-lookup"><span data-stu-id="af8db-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="af8db-193">Het aantal weergegeven items en welke kolommen worden weergegeven, kunnen beide worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="af8db-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="af8db-194">Als u een item selecteert in deze lijst, wordt een flyout geopend met meer informatie over de geselecteerde software, evenals het pad en de tijdstempel voor de laatste keer dat de software is gevonden.</span><span class="sxs-lookup"><span data-stu-id="af8db-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="af8db-195">Deze lijst kan worden gefilterd op productcode.</span><span class="sxs-lookup"><span data-stu-id="af8db-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="af8db-196">Tabblad Gevonden beveiligingslekken</span><span class="sxs-lookup"><span data-stu-id="af8db-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="af8db-197">Het **tabblad Gevonden beveiligingslekken** bevat algemene beveiligingslekken en exploits (CVE's) die van invloed kunnen zijn op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="af8db-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Afbeelding van het tabblad Gevonden beveiligingslekken voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="af8db-199">De standaardweergave bevat de ernst van de CVE, de Common Vulnerability Score (CVS), de software die betrekking heeft op de CVE, wanneer de CVE is gepubliceerd, wanneer de CVE voor het laatst is bijgewerkt, en bedreigingen die zijn gekoppeld aan de CVE.</span><span class="sxs-lookup"><span data-stu-id="af8db-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="af8db-200">Net als bij de vorige tabbladen kan het aantal items dat wordt weergegeven en welke kolommen zichtbaar zijn, worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="af8db-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="af8db-201">Als u een item selecteert in deze lijst, wordt een fly-out geopend met een beschrijving van de CVE.</span><span class="sxs-lookup"><span data-stu-id="af8db-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="af8db-202">Ontbrekende KBs</span><span class="sxs-lookup"><span data-stu-id="af8db-202">Missing KBs</span></span>

<span data-ttu-id="af8db-203">Het **tabblad Ontbrekende KBs** bevat alle Microsoft-updates die nog moeten worden toegepast op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="af8db-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="af8db-204">De KBs in kwestie zijn [Knowledge Base-artikelen](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) waarin deze updates worden beschreven. bijvoorbeeld [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="af8db-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Afbeelding van ontbrekende kbs-tabblad voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="af8db-206">In de standaardweergave wordt het bulletin weergegeven met de updates, de besturingssysteemversie, de betreffende producten, de geadresseerde CVE's, het KB-nummer en de tags.</span><span class="sxs-lookup"><span data-stu-id="af8db-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="af8db-207">Het aantal items dat per pagina wordt weergegeven en welke kolommen worden weergegeven, kan worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="af8db-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="af8db-208">Als u een item selecteert, wordt een flyout geopend die naar de update wordt koppelingen.</span><span class="sxs-lookup"><span data-stu-id="af8db-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="af8db-209">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="af8db-209">Related topics</span></span>

* [<span data-ttu-id="af8db-210">Microsoft 365 Overzicht van Defender</span><span class="sxs-lookup"><span data-stu-id="af8db-210">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
* [<span data-ttu-id="af8db-211">Microsoft 365 Defender inschakelen</span><span class="sxs-lookup"><span data-stu-id="af8db-211">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
* [<span data-ttu-id="af8db-212">Entiteiten op apparaten onderzoeken met livereactie</span><span class="sxs-lookup"><span data-stu-id="af8db-212">Investigate entities on devices, using live response</span></span>](../defender-endpoint/live-response.md)
* [<span data-ttu-id="af8db-213">Automatisch onderzoek en antwoord (AIR) in Office 365</span><span class="sxs-lookup"><span data-stu-id="af8db-213">Automated investigation and response (AIR) in Office 365</span></span>](../office-365-security/office-365-air.md)
