---
title: Apparaatprofiel in Microsoft 365-beveiligingsportal
description: Bekijk risico- en belichtingsniveaus voor een apparaat in uw organisatie. Analyseer bedreigingen uit het verleden en heden en bescherm het apparaat met de nieuwste updates.
keywords: beveiliging, malware, Microsoft 365, M365, Microsoft Threat Protection, MTP, security center, Microsoft Defender ATP, Office 365 ATP, Azure ATP, apparaatpagina, apparaatprofiel, machinepagina, machineprofiel
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: db6109fb73f0e208ab4403e2469bc955a1a01b38
ms.sourcegitcommit: d767c288ae34431fb046f4cfe36cec485881385f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/15/2020
ms.locfileid: "43516984"
---
# <a name="device-profile-page"></a><span data-ttu-id="a945c-105">Pagina apparaatprofiel</span><span class="sxs-lookup"><span data-stu-id="a945c-105">Device profile page</span></span>

<span data-ttu-id="a945c-106">De Microsoft 365-beveiligingsportal biedt u apparaatprofielpagina's, zodat u snel de status en status van apparaten in uw netwerk beoordelen.</span><span class="sxs-lookup"><span data-stu-id="a945c-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a945c-107">De pagina met apparaatprofielen kan er iets anders uitzien, afhankelijk van of het apparaat is ingeschreven in Microsoft Defender ATP, Azure ATP of beide.</span><span class="sxs-lookup"><span data-stu-id="a945c-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender ATP, Azure ATP, or both.</span></span>

<span data-ttu-id="a945c-108">Als het apparaat is ingeschreven bij Microsoft Defender ATP, u de pagina met apparaatprofielen ook gebruiken om enkele veelvoorkomende beveiligingstaken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="a945c-108">If the device is enrolled in Microsoft Defender ATP, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="a945c-109">Navigeren op de pagina apparaatprofiel</span><span class="sxs-lookup"><span data-stu-id="a945c-109">Navigating the device profile page</span></span>

<span data-ttu-id="a945c-110">De profielpagina is opgesplitst in verschillende brede secties.</span><span class="sxs-lookup"><span data-stu-id="a945c-110">The profile page is broken up into several broad sections.</span></span>

![Afbeelding van de pagina apparaatprofiel met (1) Tabgebied (2) Zijbalk en (3) Acties gemarkeerd in het rood](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="a945c-112">De zijbalk (1) bevat basisgegevens over het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a945c-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="a945c-113">Het hoofdinhoudsgebied (2) bevat tabbladen die u inschakelen om verschillende soorten informatie over het apparaat weer te geven.</span><span class="sxs-lookup"><span data-stu-id="a945c-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="a945c-114">Als het apparaat is ingeschreven bij Microsoft Defender ATP, ziet u ook een lijst met reactieacties (3).</span><span class="sxs-lookup"><span data-stu-id="a945c-114">If the device is enrolled in Microsoft Defender ATP, you will also see a list of response actions (3).</span></span> <span data-ttu-id="a945c-115">Met responsacties u veelvoorkomende beveiligingstaken uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="a945c-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="a945c-116">Zijbalk</span><span class="sxs-lookup"><span data-stu-id="a945c-116">Sidebar</span></span>

<span data-ttu-id="a945c-117">Naast het hoofdinhoudsgebied van de profielpagina van het apparaat bevindt zich de zijbalk.</span><span class="sxs-lookup"><span data-stu-id="a945c-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![Afbeelding van het tabblad zijbalk voor apparaatprofiel](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="a945c-119">De zijbalk geeft een lijst van de volledige naam en het belichtingsniveau van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a945c-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="a945c-120">Het biedt ook een aantal belangrijke basisinformatie in kleine onderafdelingen die kunnen worden geschakeld open of gesloten, zoals:</span><span class="sxs-lookup"><span data-stu-id="a945c-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="a945c-121">**Tags** : microsoft defender ATP, Azure ATP of aangepaste tags die aan het apparaat zijn gekoppeld, zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="a945c-121">**Tags** - Any Microsoft Defender ATP, Azure ATP, or custom tags associated with the device.</span></span> <span data-ttu-id="a945c-122">Tags van Azure ATP zijn niet bewerkbaar.</span><span class="sxs-lookup"><span data-stu-id="a945c-122">Tags from Azure ATP are not editable.</span></span>
* <span data-ttu-id="a945c-123">**Beveiligingsinformatie** - Open incidenten en actieve waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="a945c-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="a945c-124">Apparaten die zijn ingeschreven bij Microsoft Defender ATP, geven ook het blootstellingsniveau en het risiconiveau weer.</span><span class="sxs-lookup"><span data-stu-id="a945c-124">Devices enrolled in Microsoft Defender ATP will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="a945c-125">Het blootstellingsniveau heeft betrekking op de mate van naleving van beveiligingsaanbevelingen, terwijl het risiconiveau wordt berekend op basis van een aantal factoren, waaronder de typen en de ernst van actieve waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="a945c-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="a945c-126">**Apparaatgegevens** - Domein, BE, tijdstempel voor wanneer het apparaat voor het eerst werd gezien, IP-adressen, bronnen.</span><span class="sxs-lookup"><span data-stu-id="a945c-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="a945c-127">Apparaten die zijn ingeschreven bij Microsoft Defender ATP, geven ook de status weer.</span><span class="sxs-lookup"><span data-stu-id="a945c-127">Devices enrolled in Microsoft Defender ATP also display health state.</span></span> <span data-ttu-id="a945c-128">Apparaten die zijn ingeschreven in Azure ATP geven de NAAM SAM en een tijdstempel weer voor wanneer het apparaat voor het eerst is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="a945c-128">Devices enrolled in Azure ATP will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="a945c-129">**Netwerkactiviteit** - Tijdstempels voor de eerste en laatste keer dat het apparaat op het netwerk werd gezien.</span><span class="sxs-lookup"><span data-stu-id="a945c-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="a945c-130">**Directorygegevens** (*alleen voor apparaten die zijn ingeschreven in Azure ATP*) - [UAC-vlaggen,](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) [SPN's](https://docs.microsoft.com/windows/win32/ad/service-principal-names)en groepslidmaatschappen.</span><span class="sxs-lookup"><span data-stu-id="a945c-130">**Directory data** (*only for devices enrolled in Azure ATP*) - [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="a945c-131">Responsacties</span><span class="sxs-lookup"><span data-stu-id="a945c-131">Response actions</span></span>

<span data-ttu-id="a945c-132">Responsacties bieden een snelle manier om bedreigingen te verdedigen en te analyseren.</span><span class="sxs-lookup"><span data-stu-id="a945c-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Afbeelding van actiebalk voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="a945c-134">[Reactieacties](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) zijn alleen beschikbaar als het apparaat is ingeschreven bij Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="a945c-134">[Response actions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender ATP.</span></span>
> * <span data-ttu-id="a945c-135">Apparaten die zijn ingeschreven bij Microsoft Defender ATP kunnen verschillende aantal responsacties weergeven op basis van het besturingssysteem en het versienummer van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a945c-135">Devices that are enrolled in Microsoft Defender ATP may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="a945c-136">Acties die beschikbaar zijn op de pagina met apparaatprofielen zijn onder andere:</span><span class="sxs-lookup"><span data-stu-id="a945c-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="a945c-137">**Tags beheren** - Werkt aangepaste tags bij die u op dit apparaat hebt toegepast.</span><span class="sxs-lookup"><span data-stu-id="a945c-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="a945c-138">**Apparaat isoleren** - Isoleer het apparaat uit het netwerk van uw organisatie en houdt het verbonden met Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="a945c-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender Advanced Threat Protection.</span></span> <span data-ttu-id="a945c-139">U ervoor kiezen om Outlook, Teams en Skype voor Bedrijven uit te laten werken terwijl het apparaat geïsoleerd is, voor communicatiedoeleinden.</span><span class="sxs-lookup"><span data-stu-id="a945c-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="a945c-140">**Actiecentrum** - Bekijk de status van ingediende acties.</span><span class="sxs-lookup"><span data-stu-id="a945c-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="a945c-141">Alleen beschikbaar als er al een andere actie is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="a945c-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="a945c-142">**App-uitvoering beperken** : hiermee voorkomt u dat toepassingen die niet door Microsoft zijn ondertekend, worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="a945c-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="a945c-143">**Antivirusscan uitvoeren** - Werkt Windows Defender Antivirus-definities bij en voert onmiddellijk een antivirusscan uit.</span><span class="sxs-lookup"><span data-stu-id="a945c-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="a945c-144">Kies tussen Quick scan of Volledige scan.</span><span class="sxs-lookup"><span data-stu-id="a945c-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="a945c-145">**Onderzoekspakket verzamelen** - Verzamelt informatie over het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a945c-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="a945c-146">Wanneer het onderzoek is voltooid, u het downloaden.</span><span class="sxs-lookup"><span data-stu-id="a945c-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="a945c-147">**Live Response Session starten** - Laadt een externe shell op het apparaat voor [diepgaande beveiligingsonderzoeken.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)</span><span class="sxs-lookup"><span data-stu-id="a945c-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="a945c-148">**Start geautomatiseerd onderzoek** - [onderzoekt en verherstelt automatisch bedreigingen.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</span><span class="sxs-lookup"><span data-stu-id="a945c-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="a945c-149">Hoewel u handmatig geautomatiseerde onderzoeken activeren om vanaf deze pagina uit te voeren, leiden [bepaalde waarschuwingsbeleidsregels](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) zelf tot automatische onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="a945c-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="a945c-150">**Actiecentrum** : geeft informatie weer over eventuele reactieacties die momenteel worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="a945c-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="a945c-151">Sectie Tabbladen</span><span class="sxs-lookup"><span data-stu-id="a945c-151">Tabs section</span></span>

<span data-ttu-id="a945c-152">Met de tabbladen apparaatprofiel u schakelen via een overzicht van beveiligingsgegevens over het apparaat en tabellen met een lijst met waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="a945c-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="a945c-153">Apparaten die zijn ingeschreven bij Microsoft Defender ATP geven ook tabbladen weer met een tijdlijn, een lijst met beveiligingsaanbevelingen, een software-inventaris, een lijst met ontdekte kwetsbaarheden en ontbrekende GB's (beveiligingsupdates).</span><span class="sxs-lookup"><span data-stu-id="a945c-153">Devices enrolled in Microsoft Defender ATP will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="a945c-154">Tabblad Overzicht</span><span class="sxs-lookup"><span data-stu-id="a945c-154">Overview tab</span></span>

<span data-ttu-id="a945c-155">Het standaardtabblad is **Overzicht**.</span><span class="sxs-lookup"><span data-stu-id="a945c-155">The default tab is **Overview**.</span></span> <span data-ttu-id="a945c-156">Het biedt een snelle blik op het belangrijkste beveiligingsfeit over het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a945c-156">It provides a quick look at the most important security fact about the device.</span></span>

![Afbeelding van het tabblad Overzicht voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="a945c-158">Hier u de actieve waarschuwingen van het apparaat en alle momenteel aangemelde gebruikers snel bekijken.</span><span class="sxs-lookup"><span data-stu-id="a945c-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="a945c-159">Als het apparaat is ingeschreven bij Microsoft Defender ATP, ziet u ook het risiconiveau van het apparaat en alle beschikbare gegevens over beveiligingsbeoordelingen.</span><span class="sxs-lookup"><span data-stu-id="a945c-159">If the device is enrolled in Microsoft Defender ATP, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="a945c-160">De beveiligingsbeoordelingen beschrijven het blootstellingsniveau van het apparaat, bieden beveiligingsaanbevelingen en vermelden getroffen software en ontdekte kwetsbaarheden.</span><span class="sxs-lookup"><span data-stu-id="a945c-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="a945c-161">Tabblad Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="a945c-161">Alerts tab</span></span>

<span data-ttu-id="a945c-162">Het tabblad **Waarschuwingen** bevat een lijst met waarschuwingen die op het apparaat zijn opgehaald, van zowel Azure ATP als Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="a945c-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Azure ATP and Microsoft Defender ATP.</span></span>

![Afbeelding van het tabblad Waarschuwingen voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="a945c-164">U het aantal weergegeven items aanpassen en welke kolommen voor elk item worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a945c-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="a945c-165">Het standaardgedrag is om dertig items per pagina weer te geven.</span><span class="sxs-lookup"><span data-stu-id="a945c-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="a945c-166">De kolommen op dit tabblad bevatten informatie over de ernst van de bedreiging die de waarschuwing heeft geactiveerd, evenals de status, de onderzoeksstatus en aan wie de waarschuwing is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="a945c-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="a945c-167">De *kolom van de getroffen entiteiten* verwijst naar het apparaat (entiteit) waarvan u momenteel het profiel bekijkt, plus alle andere apparaten in uw netwerk die worden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="a945c-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="a945c-168">Als u een item uit deze lijst selecteert, wordt een flyout geopend met nog meer informatie over de geselecteerde waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="a945c-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="a945c-169">Deze lijst kan worden gefilterd op ernst, status of aan wie de waarschuwing is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="a945c-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="a945c-170">Tabblad Tijdlijn</span><span class="sxs-lookup"><span data-stu-id="a945c-170">Timeline tab</span></span>

<span data-ttu-id="a945c-171">Het tabblad **Tijdlijn** bevat een interactieve, chronologische grafiek van alle gebeurtenissen die op het apparaat worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a945c-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="a945c-172">Door het gemarkeerde gebied van de grafiek naar links of rechts te verplaatsen, u gebeurtenissen over verschillende perioden bekijken.</span><span class="sxs-lookup"><span data-stu-id="a945c-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="a945c-173">U ook een aangepast bereik van datums kiezen in het vervolgkeuzemenu tussen de interactieve grafiek en de lijst met gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="a945c-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="a945c-174">Onder de grafiek vindt u een lijst met gebeurtenissen voor het geselecteerde bereik van datums.</span><span class="sxs-lookup"><span data-stu-id="a945c-174">Below the chart is a list of events for the selected range of dates.</span></span>

![Afbeelding van het tabblad tijdlijn voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="a945c-176">Het aantal weergegeven items en de kolommen in de lijst kunnen beide worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="a945c-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="a945c-177">De standaardkolommen bevatten de gebeurtenistijd, actieve gebruiker, actietype, entiteiten (processen) en aanvullende informatie over de gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="a945c-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="a945c-178">Als u een item uit deze lijst selecteert, wordt een flyout geopend met een grafiek voor gebeurtenisentiteiten, met de bovenliggende en onderliggende processen die bij de gebeurtenis betrokken zijn.</span><span class="sxs-lookup"><span data-stu-id="a945c-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="a945c-179">De lijst kan worden gefilterd op het specifieke soort gebeurtenis; bijvoorbeeld Registergebeurtenissen of Smart Screen-gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="a945c-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="a945c-180">De lijst kan ook worden geëxporteerd naar een CSV-bestand, om te downloaden.</span><span class="sxs-lookup"><span data-stu-id="a945c-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="a945c-181">Hoewel het bestand niet wordt beperkt door het aantal gebeurtenissen, is het maximale tijdsbereik dat u exporteren zeven dagen.</span><span class="sxs-lookup"><span data-stu-id="a945c-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="a945c-182">Tabblad Beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="a945c-182">Security recommendations tab</span></span>

<span data-ttu-id="a945c-183">Op het tabblad **Beveiligingsaanbevelingen** staan acties die u uitvoeren om het apparaat te beschermen.</span><span class="sxs-lookup"><span data-stu-id="a945c-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="a945c-184">Als u een item in deze lijst selecteert, opent u een flyout waar u instructies krijgen over het toepassen van de aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="a945c-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Afbeelding van het tabblad Beveiligingsaanbevelingen voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="a945c-186">Net als bij de vorige tabbladen kan het aantal items dat per pagina wordt weergegeven en welke kolommen zichtbaar zijn, worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="a945c-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="a945c-187">De standaardweergave bevat kolommen waarin de beveiligingszwakke punten worden beschreven die zijn verholpen, de bijbehorende bedreiging, de bijbehorende component of software die door de bedreiging wordt beïnvloed, en meer.</span><span class="sxs-lookup"><span data-stu-id="a945c-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="a945c-188">Items kunnen worden gefilterd op de status van de aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="a945c-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="a945c-189">Software-inventaris</span><span class="sxs-lookup"><span data-stu-id="a945c-189">Software inventory</span></span>

<span data-ttu-id="a945c-190">Op het tabblad **Softwareinventaris** vindt u software die op het apparaat is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="a945c-190">The **Software inventory** tab lists software installed on the device.</span></span>

![Afbeelding van het tabblad softwareinventaris voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="a945c-192">De standaardweergave toont de softwareleverancier, het geïnstalleerde versienummer, het aantal bekende softwarezwakke punten, bedreigingsinzichten, productcode en tags.</span><span class="sxs-lookup"><span data-stu-id="a945c-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="a945c-193">Het aantal weergegeven items en welke kolommen worden weergegeven, kan beide worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="a945c-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="a945c-194">Als u een item uit deze lijst selecteert, wordt een flyout geopend met meer details over de geselecteerde software, evenals het pad en de tijdstempel voor de laatste keer dat de software is gevonden.</span><span class="sxs-lookup"><span data-stu-id="a945c-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="a945c-195">Deze lijst kan worden gefilterd op productcode.</span><span class="sxs-lookup"><span data-stu-id="a945c-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="a945c-196">Tabblad Ontdekte kwetsbaarheden</span><span class="sxs-lookup"><span data-stu-id="a945c-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="a945c-197">Op het tabblad **Ontdekte kwetsbaarheden** worden alle algemene kwetsbaarheden en exploits (CvEs) weergegeven die van invloed kunnen zijn op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a945c-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Afbeelding van het tabblad ontdekte kwetsbaarheden voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="a945c-199">De standaardweergave geeft een overzicht van de ernst van de CVE, de Common Vulnerability Score (CVS), de software met betrekking tot de CVE, toen de CVE werd gepubliceerd, toen de CVE voor het laatst werd bijgewerkt, en bedreigingen in verband met de CVE.</span><span class="sxs-lookup"><span data-stu-id="a945c-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="a945c-200">Net als bij de vorige tabbladen kan het aantal weergegeven items en welke kolommen zichtbaar zijn, worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="a945c-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="a945c-201">Als u een item uit deze lijst selecteert, wordt een flyout geopend waarin de CVE wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="a945c-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="a945c-202">Ontbrekende KBs</span><span class="sxs-lookup"><span data-stu-id="a945c-202">Missing KBs</span></span>

<span data-ttu-id="a945c-203">Op het tabblad **Ontbrekende KBs** worden alle Microsoft-updates weergegeven die nog niet op het apparaat moeten worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="a945c-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="a945c-204">De "KBs" in kwestie zijn [Knowledge Base artikelen](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) die deze updates beschrijven; [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="a945c-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Afbeelding van ontbrekend kbs-tabblad voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="a945c-206">In de standaardweergave wordt het bulletin weergegeven met de updates, de os-versie, de betrokken producten, aco's, het KB-nummer en de tags.</span><span class="sxs-lookup"><span data-stu-id="a945c-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="a945c-207">Het aantal items dat per pagina wordt weergegeven en welke kolommen worden weergegeven, kan worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="a945c-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="a945c-208">Als u een item selecteert, wordt een flyout geopend die naar de update verwijst.</span><span class="sxs-lookup"><span data-stu-id="a945c-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a945c-209">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="a945c-209">Related topics</span></span>

* [<span data-ttu-id="a945c-210">Overzicht van Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a945c-210">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="a945c-211">Microsoft-bedreigingsbeveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="a945c-211">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
* [<span data-ttu-id="a945c-212">Entiteiten op apparaten onderzoeken met live respons</span><span class="sxs-lookup"><span data-stu-id="a945c-212">Investigate entities on devices, using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="a945c-213">Geautomatiseerd onderzoek en antwoord (AIR) in Office 365</span><span class="sxs-lookup"><span data-stu-id="a945c-213">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
