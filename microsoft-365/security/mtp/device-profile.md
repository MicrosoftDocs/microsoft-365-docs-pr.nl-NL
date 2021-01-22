---
title: Apparaatprofiel in Microsoft 365-beveiligingsportal
description: Bekijk de risico's en blootstellingsniveaus voor een apparaat in uw organisatie. Analyseer eerdere en huidige bedreigingen en bescherm het apparaat met de nieuwste updates.
keywords: beveiliging, malware, Microsoft 365, M365, Microsoft Threat Protection, MTP, beveiligingscentrum, Microsoft Defender ATP, Office 365 ATP, Azure ATP, apparaatpagina, apparaatprofiel, computerpagina, machineprofiel
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 40897185ab885ee2b6880ecd5f25d95fbe3d771e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929572"
---
# <a name="device-profile-page"></a><span data-ttu-id="d7600-105">Apparaatprofielpagina</span><span class="sxs-lookup"><span data-stu-id="d7600-105">Device profile page</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d7600-106">De Microsoft 365-beveiligingsportal biedt u apparaatprofielpagina's, zodat u snel de status en status van apparaten in uw netwerk kunt beoordelen.</span><span class="sxs-lookup"><span data-stu-id="d7600-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d7600-107">De profielpagina van het apparaat kan er iets anders uit zien, afhankelijk van of het apparaat is ingeschreven bij Microsoft Defender for Endpoint, Microsoft Defender for Identity of beide.</span><span class="sxs-lookup"><span data-stu-id="d7600-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender for Endpoint, Microsoft Defender for Identity, or both.</span></span>

<span data-ttu-id="d7600-108">Als het apparaat is geregistreerd bij Microsoft Defender for Endpoint, kunt u ook de profielpagina van het apparaat gebruiken om enkele veelvoorkomende beveiligingstaken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="d7600-108">If the device is enrolled in Microsoft Defender for Endpoint, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="d7600-109">Navigeren op de apparaatprofielpagina</span><span class="sxs-lookup"><span data-stu-id="d7600-109">Navigating the device profile page</span></span>

<span data-ttu-id="d7600-110">De profielpagina is onderverdeeld in diverse algemene secties.</span><span class="sxs-lookup"><span data-stu-id="d7600-110">The profile page is broken up into several broad sections.</span></span>

![Afbeelding van apparaatprofielpagina met (1) Tabbladgebied (2) Zijbalk en (3) Acties gemarkeerd met rood](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="d7600-112">De zijbalk (1) bevat basisgegevens over het apparaat.</span><span class="sxs-lookup"><span data-stu-id="d7600-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="d7600-113">Het gebied met de hoofdinhoud (2) bevat tabbladen waar u doorheen kunt schakelen om verschillende soorten informatie over het apparaat te bekijken.</span><span class="sxs-lookup"><span data-stu-id="d7600-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="d7600-114">Als het apparaat is geregistreerd bij Microsoft Defender for Endpoint, ziet u ook een lijst met antwoordacties (3).</span><span class="sxs-lookup"><span data-stu-id="d7600-114">If the device is enrolled in Microsoft Defender for Endpoint, you will also see a list of response actions (3).</span></span> <span data-ttu-id="d7600-115">Met antwoordacties kunt u veelvoorkomende beveiligingstaken uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="d7600-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="d7600-116">Zijbalk</span><span class="sxs-lookup"><span data-stu-id="d7600-116">Sidebar</span></span>

<span data-ttu-id="d7600-117">Naast het gebied met de hoofdinhoud van de profielpagina van het apparaat, staat de zijbalk.</span><span class="sxs-lookup"><span data-stu-id="d7600-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![Afbeelding van tabblad Zijbalk voor apparaatprofiel](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="d7600-119">De zijbalk bevat de volledige naam en het blootstellingsniveau van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="d7600-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="d7600-120">Daarnaast vindt u hier belangrijke basisinformatie in kleine subsecties die u kunt openen of sluiten, zoals:</span><span class="sxs-lookup"><span data-stu-id="d7600-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="d7600-121">**Tags:** Alle Microsoft Defender voor eindpunten, Microsoft Defender voor identiteiten of aangepaste tags die aan het apparaat zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="d7600-121">**Tags** - Any Microsoft Defender for Endpoint, Microsoft Defender for Identity, or custom tags associated with the device.</span></span> <span data-ttu-id="d7600-122">Labels van Microsoft Defender voor identiteit kunnen niet worden bewerkt.</span><span class="sxs-lookup"><span data-stu-id="d7600-122">Tags from Microsoft Defender for Identity are not editable.</span></span>
* <span data-ttu-id="d7600-123">**Beveiligingsgegevens:** open incidenten en actieve waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="d7600-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="d7600-124">Apparaten die zijn ingeschreven in Microsoft Defender for Endpoint, geven ook het blootstellingsniveau en het risiconiveau weer.</span><span class="sxs-lookup"><span data-stu-id="d7600-124">Devices enrolled in Microsoft Defender for Endpoint will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="d7600-125">Blootstellingsniveau heeft betrekking op hoeveel het apparaat voldoet aan beveiligingsaanbevelingen, terwijl het risiconiveau wordt berekend op basis van een aantal factoren, waaronder de typen en ernst van actieve waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="d7600-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="d7600-126">**Apparaatgegevens:** domein, besturingssysteem, tijdstempel voor wanneer het apparaat voor het eerst werd gezien, IP-adressen, bronnen.</span><span class="sxs-lookup"><span data-stu-id="d7600-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="d7600-127">Apparaten die zijn ingeschreven in Microsoft Defender voor eindpunten geven ook de status van de status weer.</span><span class="sxs-lookup"><span data-stu-id="d7600-127">Devices enrolled in Microsoft Defender for Endpoint also display health state.</span></span> <span data-ttu-id="d7600-128">Apparaten die zijn geregistreerd met Microsoft Defender for Identity, geven de SAM-naam en een tijdstempel weer voor wanneer het apparaat voor het eerst werd gemaakt.</span><span class="sxs-lookup"><span data-stu-id="d7600-128">Devices enrolled in Microsoft Defender for Identity will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="d7600-129">**Netwerkactiviteit:** tijdstempels voor de eerste keer en de laatste keer dat het apparaat in het netwerk is gezien.</span><span class="sxs-lookup"><span data-stu-id="d7600-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="d7600-130">**Adreslijstgegevens** (alleen voor apparaten die zijn geregistreerd *voor Microsoft Defender voor identiteit)*- [UAC-vlaggen,](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) [SPN's](https://docs.microsoft.com/windows/win32/ad/service-principal-names)en groepslidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="d7600-130">**Directory data** (*only for devices enrolled in Microsoft Defender for Identity*) - [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="d7600-131">Antwoordacties</span><span class="sxs-lookup"><span data-stu-id="d7600-131">Response actions</span></span>

<span data-ttu-id="d7600-132">Reactieacties bieden een snelle manier om je te beschermen tegen bedreigingen en om bedreigingen te analyseren.</span><span class="sxs-lookup"><span data-stu-id="d7600-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Afbeelding van actiebalk voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="d7600-134">[Antwoordacties](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) zijn alleen beschikbaar als het apparaat is ingeschreven bij Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="d7600-134">[Response actions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender for Endpoint.</span></span>
> * <span data-ttu-id="d7600-135">Apparaten die zijn ingeschreven in Microsoft Defender for Endpoint kunnen verschillende aantallen antwoordacties weergeven, op basis van het besturingssysteem en versienummer van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="d7600-135">Devices that are enrolled in Microsoft Defender for Endpoint may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="d7600-136">Acties die beschikbaar zijn op de profielpagina van het apparaat zijn:</span><span class="sxs-lookup"><span data-stu-id="d7600-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="d7600-137">**Tags beheren:** updates van aangepaste tags die u op dit apparaat hebt toegepast.</span><span class="sxs-lookup"><span data-stu-id="d7600-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="d7600-138">**Isoleert apparaat:** isoleert het apparaat van het netwerk van uw organisatie terwijl het verbonden blijft met Microsoft Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="d7600-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="d7600-139">U kunt Outlook, Teams en Skype voor Bedrijven laten uitvoeren terwijl het apparaat geïsoleerd is, voor communicatiedoeleinden.</span><span class="sxs-lookup"><span data-stu-id="d7600-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="d7600-140">**Actiecentrum** - Bekijk de status van verzonden acties.</span><span class="sxs-lookup"><span data-stu-id="d7600-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="d7600-141">Alleen beschikbaar als er al een andere actie is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="d7600-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="d7600-142">**Het uitvoeren van apps** beperken: voorkomt dat toepassingen die niet door Microsoft zijn ondertekend, worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="d7600-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="d7600-143">**Voer antivirusscan uit** - Windows Defender Antivirus-definities worden bijgewerkt en er wordt meteen een antivirusscan uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="d7600-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="d7600-144">Kiezen tussen Snelle scan of Volledige scan.</span><span class="sxs-lookup"><span data-stu-id="d7600-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="d7600-145">**Pakket voor onderzoek verzamelen:** verzamelt informatie over het apparaat.</span><span class="sxs-lookup"><span data-stu-id="d7600-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="d7600-146">Wanneer het onderzoek is voltooid, kunt u het downloaden.</span><span class="sxs-lookup"><span data-stu-id="d7600-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="d7600-147">**Live Response-sessie starten:** er wordt een externe shell op het apparaat geladen voor uitgebreide [beveiligingsonderzoeken.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)</span><span class="sxs-lookup"><span data-stu-id="d7600-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="d7600-148">**Automatisch onderzoek starten:** automatisch [bedreigingen onderzoeken en herstellen.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</span><span class="sxs-lookup"><span data-stu-id="d7600-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="d7600-149">Hoewel u vanaf deze pagina handmatig kunt activeren dat geautomatiseerde onderzoeken worden [uitgevoerd,](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) worden met bepaalde waarschuwingsbeleidsregels automatische onderzoeken automatisch uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="d7600-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="d7600-150">**Actiecentrum:** hier wordt informatie weergegeven over alle antwoordacties die momenteel worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="d7600-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="d7600-151">Sectie Tabbladen</span><span class="sxs-lookup"><span data-stu-id="d7600-151">Tabs section</span></span>

<span data-ttu-id="d7600-152">Met de profieltabbladen van het apparaat kunt u door een overzicht van beveiligingsdetails over het apparaat schakelen en door tabellen met een lijst met waarschuwingen schakelen.</span><span class="sxs-lookup"><span data-stu-id="d7600-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="d7600-153">Apparaten die zijn geregistreerd in Microsoft Defender for Endpoint, bevatten ook tabbladen met een tijdlijn, een lijst met beveiligingsaanbevelingen, een softwarevoorraad, een lijst met gevonden beveiligingsproblemen en ontbrekende KB's (beveiligingsupdates).</span><span class="sxs-lookup"><span data-stu-id="d7600-153">Devices enrolled in Microsoft Defender for Endpoint will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="d7600-154">Tabblad Overzicht</span><span class="sxs-lookup"><span data-stu-id="d7600-154">Overview tab</span></span>

<span data-ttu-id="d7600-155">Het standaardtabblad is **Overzicht.**</span><span class="sxs-lookup"><span data-stu-id="d7600-155">The default tab is **Overview**.</span></span> <span data-ttu-id="d7600-156">In dit artikel vindt u een beknopt overzicht van de belangrijkste beveiligingsrisico's van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="d7600-156">It provides a quick look at the most important security fact about the device.</span></span>

![Afbeelding van tabblad Overzicht voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="d7600-158">Hier kunt u een kort overzicht krijgen van de actieve waarschuwingen op het apparaat en eventuele gebruikers die op dat moment zijn aangemeld.</span><span class="sxs-lookup"><span data-stu-id="d7600-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="d7600-159">Als het apparaat is geregistreerd bij Microsoft Defender for Endpoint, ziet u ook het risiconiveau van het apparaat en alle beschikbare gegevens over beveiligingsbeoordelingen.</span><span class="sxs-lookup"><span data-stu-id="d7600-159">If the device is enrolled in Microsoft Defender for Endpoint, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="d7600-160">In de beveiligingsbeoordelingen wordt het blootstellingsniveau van het apparaat beschreven, worden beveiligingsaanbevelingen gegeven, wordt de betrokken software vermeld en worden beveiligingsproblemen ontdekt.</span><span class="sxs-lookup"><span data-stu-id="d7600-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="d7600-161">Tabblad Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="d7600-161">Alerts tab</span></span>

<span data-ttu-id="d7600-162">Het **tabblad** Waarschuwingen bevat een lijst met waarschuwingen die zijn verhoogd op het apparaat, van zowel Microsoft Defender for Identity als Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="d7600-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span>

![Afbeelding van tabblad Waarschuwingen voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="d7600-164">U kunt het aantal weergegeven items aanpassen en voor elk item welke kolommen worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d7600-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="d7600-165">Het standaardgedrag is om dertig items per pagina weer te geven.</span><span class="sxs-lookup"><span data-stu-id="d7600-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="d7600-166">De kolommen op dit tabblad bevatten informatie over de ernst van de bedreiging die de waarschuwing heeft geactiveerd, evenals de status, de onderzoeksstatus en aan wie de waarschuwing is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="d7600-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="d7600-167">De *kolom met beïnvloede entiteiten* verwijst naar het apparaat (de entiteit) waarvan u het profiel momenteel bekijkt, plus alle andere apparaten in uw netwerk die worden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="d7600-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="d7600-168">Als u een item in deze lijst selecteert, wordt een flyout geopend met nog meer informatie over de geselecteerde waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="d7600-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="d7600-169">Deze lijst kan worden gefilterd op ernst, status of aan wie de waarschuwing is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="d7600-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="d7600-170">Tabblad Tijdlijn</span><span class="sxs-lookup"><span data-stu-id="d7600-170">Timeline tab</span></span>

<span data-ttu-id="d7600-171">Het **tabblad** Tijdlijn bevat een interactief chronologisch diagram van alle gebeurtenissen die op het apparaat zijn geplaatst.</span><span class="sxs-lookup"><span data-stu-id="d7600-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="d7600-172">Door het gemarkeerde gebied van de grafiek naar links of rechts te verplaatsen, kunt u gebeurtenissen over verschillende perioden weergeven.</span><span class="sxs-lookup"><span data-stu-id="d7600-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="d7600-173">U kunt ook een aangepast datumbereik kiezen in de vervolgkeuzelijst tussen de interactieve grafiek en de lijst met gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="d7600-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="d7600-174">Onder de grafiek staat een lijst met gebeurtenissen voor het geselecteerde datumbereik.</span><span class="sxs-lookup"><span data-stu-id="d7600-174">Below the chart is a list of events for the selected range of dates.</span></span>

![Afbeelding van tijdlijntabblad voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="d7600-176">Het aantal weergegeven items en de kolommen in de lijst kunnen beide worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="d7600-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="d7600-177">De standaardkolommen bevatten de gebeurtenistijd, de actieve gebruiker, het actietype, entiteiten (processen) en aanvullende informatie over de gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="d7600-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="d7600-178">Als u een item in deze lijst selecteert, wordt er een flyout geopend waarin een grafiek met gebeurtenis-entiteiten wordt weergegeven, waarin de bovenliggende en onderliggende processen voor de gebeurtenis worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d7600-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="d7600-179">De lijst kan worden gefilterd op het specifieke type gebeurtenis; Bijvoorbeeld registergebeurtenissen of slimme schermgebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="d7600-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="d7600-180">De lijst kan ook worden geëxporteerd naar een CSV-bestand om te downloaden.</span><span class="sxs-lookup"><span data-stu-id="d7600-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="d7600-181">Hoewel het bestand niet wordt beperkt door het aantal gebeurtenissen, is de maximumtijd die u kunt kiezen om te exporteren zeven dagen.</span><span class="sxs-lookup"><span data-stu-id="d7600-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="d7600-182">Tabblad Beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="d7600-182">Security recommendations tab</span></span>

<span data-ttu-id="d7600-183">Op **het tabblad Beveiligingsaanbevelingen** worden de acties weergegeven die u kunt uitvoeren om het apparaat te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="d7600-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="d7600-184">Als u een item in deze lijst selecteert, wordt een flyout geopend waarin u instructies kunt krijgen voor het toepassen van de aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="d7600-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Afbeelding van tabblad Met beveiligingsaanbevelingen voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="d7600-186">Net als bij de vorige tabbladen, kan het aantal items dat per pagina wordt weergegeven en welke kolommen zichtbaar zijn, worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="d7600-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="d7600-187">De standaardweergave bevat kolommen met een overzicht van de beveiligingsrisico's die worden aangepakt, de bijbehorende bedreiging, het gerelateerde onderdeel of de software die door de bedreiging wordt beïnvloed, en meer.</span><span class="sxs-lookup"><span data-stu-id="d7600-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="d7600-188">Items kunnen worden gefilterd op de status van de aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="d7600-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="d7600-189">Softwarevoorraad</span><span class="sxs-lookup"><span data-stu-id="d7600-189">Software inventory</span></span>

<span data-ttu-id="d7600-190">Op **het tabblad Softwarevoorraad** wordt software vermeld die op het apparaat is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="d7600-190">The **Software inventory** tab lists software installed on the device.</span></span>

![Afbeelding van tabblad Softwarevoorraad voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="d7600-192">In de standaardweergave ziet u de softwareleverancier, het geïnstalleerde versienummer, het aantal bekende software zwakke punten, bedreigingsinzichten, productcode en labels.</span><span class="sxs-lookup"><span data-stu-id="d7600-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="d7600-193">Het aantal weergegeven items en welke kolommen kunnen beide worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="d7600-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="d7600-194">Als u een item in deze lijst selecteert, wordt een flyout geopend met meer informatie over de geselecteerde software en het pad en de tijdstempel voor de laatste keer dat de software is gevonden.</span><span class="sxs-lookup"><span data-stu-id="d7600-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="d7600-195">Deze lijst kan worden gefilterd op productcode.</span><span class="sxs-lookup"><span data-stu-id="d7600-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="d7600-196">Tabblad Voor ontdekte beveiligingsproblemen</span><span class="sxs-lookup"><span data-stu-id="d7600-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="d7600-197">Op **het tabblad Gevonden** beveiligingsproblemen worden veelvoorkomende beveiligingslekken en misbruiken (CVEs) vermeld die van invloed kunnen zijn op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="d7600-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Afbeelding van het tabblad Met beveiligingsproblemen ontdekt voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="d7600-199">In de standaardweergave worden de ernst van het CVE, de CVS (Common Vulnerability Score), de software die is gerelateerd aan het CVE, vermeld wanneer de CVE is gepubliceerd, wanneer de CVE voor het laatst werd bijgewerkt, en de bedreigingen die aan het CVE zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="d7600-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="d7600-200">Net als bij de vorige tabbladen, kan het aantal weergegeven items en welke kolommen worden weergegeven, worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="d7600-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="d7600-201">Als u een item in deze lijst selecteert, wordt een flyout geopend met een beschrijving van het CVE.</span><span class="sxs-lookup"><span data-stu-id="d7600-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="d7600-202">Ontbrekende KB's</span><span class="sxs-lookup"><span data-stu-id="d7600-202">Missing KBs</span></span>

<span data-ttu-id="d7600-203">Op **het tabblad Ontbrekende KB's** worden alle Microsoft-updates vermeld die nog niet op het apparaat zijn toegepast.</span><span class="sxs-lookup"><span data-stu-id="d7600-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="d7600-204">De KB's in kwestie zijn [Knowledge Base-artikelen](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) waarin deze updates worden beschreven. bijvoorbeeld [KB4551762.](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762)</span><span class="sxs-lookup"><span data-stu-id="d7600-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Afbeelding van het ontbrekende tabblad Kbs voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="d7600-206">In de standaardweergave wordt het bulletin weergegeven met updates, versie van het besturingssysteem, betrokken producten, geadresseerde CV's, het KB-nummer en labels.</span><span class="sxs-lookup"><span data-stu-id="d7600-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="d7600-207">Het aantal weergegeven items per pagina en welke kolommen kunnen worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="d7600-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="d7600-208">Als u een item selecteert, wordt een flyout geopend die is koppelingen naar de update.</span><span class="sxs-lookup"><span data-stu-id="d7600-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d7600-209">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d7600-209">Related topics</span></span>

* [<span data-ttu-id="d7600-210">Overzicht van Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7600-210">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="d7600-211">Microsoft 365 Defender in te zetten</span><span class="sxs-lookup"><span data-stu-id="d7600-211">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
* [<span data-ttu-id="d7600-212">Entiteiten op apparaten onderzoeken met behulp van live-antwoorden</span><span class="sxs-lookup"><span data-stu-id="d7600-212">Investigate entities on devices, using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="d7600-213">Automatisch onderzoek en automatisch onderzoek (AIR) in Office 365</span><span class="sxs-lookup"><span data-stu-id="d7600-213">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
