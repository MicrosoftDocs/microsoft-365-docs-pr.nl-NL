---
title: Apparaatprofiel in Microsoft 365 Security Portal
description: Risico's en belichtings niveaus voor een apparaat in uw organisatie weergeven. Analyseer oude en presenteer bedreigingen en Beveilig het apparaat met de nieuwste updates.
keywords: beveiliging, malware, Microsoft 365, M365, Microsoft Threat Protection, MTP, Security Center, Microsoft Defender ATP, Office 365 ATP, Azure ATP, apparaatklasse, apparaat-profiel, computer pagina, computerprofiel
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
ms.openlocfilehash: f6b79d3252084b298f94e01b18ebe3505f83b480
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196855"
---
# <a name="device-profile-page"></a><span data-ttu-id="a5fcb-105">De pagina apparaat Profiel</span><span class="sxs-lookup"><span data-stu-id="a5fcb-105">Device profile page</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a5fcb-106">Met de Microsoft 365-beveiligings Portal beschikt u over apparaatprofielen, zodat u snel de status en status van apparaten in uw netwerk kunt beoordelen.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5fcb-107">De pagina apparaat-profiel kan enigszins afwijken, afhankelijk van of het apparaat is ingeschreven in Microsoft Defender ATP, Azure ATP of beide.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender ATP, Azure ATP, or both.</span></span>

<span data-ttu-id="a5fcb-108">Als het apparaat is ingeschreven in Microsoft Defender ATP, kunt u ook de profielpagina van het apparaat gebruiken om enkele veelvoorkomende beveiligingstaken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-108">If the device is enrolled in Microsoft Defender ATP, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="a5fcb-109">Navigeren in de profielpagina van het apparaat</span><span class="sxs-lookup"><span data-stu-id="a5fcb-109">Navigating the device profile page</span></span>

<span data-ttu-id="a5fcb-110">De profielpagina is opgesplitst in diverse grote secties.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-110">The profile page is broken up into several broad sections.</span></span>

![Afbeelding van de pagina met het apparaatprofiel met (1) tabblad gebied (2) zijbalk en (3) gemarkeerde acties in rood](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="a5fcb-112">De zijbalk (1) geeft een overzicht van de algemene Details van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="a5fcb-113">Het gebied met de hoofdinhoud (2) bevat tabbladen waarmee u kunt schakelen om verschillende soorten informatie over het apparaat weer te geven.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="a5fcb-114">Als het apparaat is ingeschreven in Microsoft Defender ATP, ziet u ook een lijst met antwoord acties (3).</span><span class="sxs-lookup"><span data-stu-id="a5fcb-114">If the device is enrolled in Microsoft Defender ATP, you will also see a list of response actions (3).</span></span> <span data-ttu-id="a5fcb-115">Met antwoord acties kunt u veelvoorkomende taken uitvoeren met betrekking tot beveiliging.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="a5fcb-116">Protection</span><span class="sxs-lookup"><span data-stu-id="a5fcb-116">Sidebar</span></span>

<span data-ttu-id="a5fcb-117">Naast het gebied met de hoofdinhoud van de profielpagina van het apparaat is de zijbalk.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![Afbeelding van het tabblad zijbalk voor apparaatprofiel](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="a5fcb-119">De zijbalk bevat de volledige naam en het belichtings niveau van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="a5fcb-120">Het biedt ook enkele belangrijke basisinformatie in kleine subsecties die kunnen worden geopend of gesloten.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="a5fcb-121">**Tags** : Microsoft Defender ATP, Azure ATP of aangepaste labels die zijn gekoppeld aan het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-121">**Tags** - Any Microsoft Defender ATP, Azure ATP, or custom tags associated with the device.</span></span> <span data-ttu-id="a5fcb-122">Tags van Azure ATP kunnen niet worden bewerkt.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-122">Tags from Azure ATP are not editable.</span></span>
* <span data-ttu-id="a5fcb-123">**Beveiligingsgegevens** -open incidenten en actieve meldingen.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="a5fcb-124">Op apparaten die zijn geregistreerd in Microsoft Defender ATP worden ook belichtings niveau en risiconiveau weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-124">Devices enrolled in Microsoft Defender ATP will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="a5fcb-125">Belichtings niveau is afhankelijk van het aantal beveiligingsaanbevelingen, waarbij risiconiveau wordt berekend op basis van een aantal factoren, waaronder de typen en de ernst van actieve waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="a5fcb-126">**Apparaatgegevens** : domein, besturingssysteem, tijdstempel van wanneer het apparaat voor het eerst werd gezien, IP-adressen, bronnen.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="a5fcb-127">Op apparaten die zijn geregistreerd in Microsoft Defender ATP wordt ook de status status weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-127">Devices enrolled in Microsoft Defender ATP also display health state.</span></span> <span data-ttu-id="a5fcb-128">In azure ATP ingeschreven apparaten wordt de naam van de SAM weergegeven en wordt een tijdstempel weergegeven voor wanneer het apparaat voor het eerst is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-128">Devices enrolled in Azure ATP will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="a5fcb-129">**Netwerkactiviteit** : tijdstempels voor de eerste keer en de laatste keer dat het apparaat is gedetecteerd op het netwerk.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="a5fcb-130">**Active Directory** [-vlaggen,](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) [spn's](https://docs.microsoft.com/windows/win32/ad/service-principal-names)en groepslidmaatschappen (*alleen voor apparaten die zijn geregistreerd in azure ATP*).</span><span class="sxs-lookup"><span data-stu-id="a5fcb-130">**Directory data** (*only for devices enrolled in Azure ATP*) - [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="a5fcb-131">Antwoord acties</span><span class="sxs-lookup"><span data-stu-id="a5fcb-131">Response actions</span></span>

<span data-ttu-id="a5fcb-132">Antwoord acties bieden een snelle manier om bedreigingen te verdedigen en analyseren.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Afbeelding van actiebalk voor Profiel van apparaat](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="a5fcb-134">[Antwoord acties](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) zijn alleen beschikbaar als het apparaat is ingeschreven in Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-134">[Response actions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender ATP.</span></span>
> * <span data-ttu-id="a5fcb-135">Apparaten die zijn ingeschreven in Microsoft Defender ATP, kunnen verschillende nummers van antwoord acties weergeven, op basis van het OS en het versienummer van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-135">Devices that are enrolled in Microsoft Defender ATP may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="a5fcb-136">Dit zijn de beschikbare acties op de profielpagina van het apparaat:</span><span class="sxs-lookup"><span data-stu-id="a5fcb-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="a5fcb-137">**Tags beheren** : Hiermee worden aangepaste tags bijgewerkt die u hebt toegepast op dit apparaat.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="a5fcb-138">**Isoleer apparaat** : isoleert het apparaat in het netwerk van uw organisatie en houdt het verbonden met Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender Advanced Threat Protection.</span></span> <span data-ttu-id="a5fcb-139">U kunt ervoor kiezen Outlook, teams en Skype voor bedrijven uit te voeren wanneer het apparaat is geïsoleerd voor communicatiedoeleinden.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="a5fcb-140">**Onderhoudscentrum** : de status van ingediende acties weergeven.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="a5fcb-141">Alleen beschikbaar als er nog een actie is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="a5fcb-142">**App-uitvoering beperken** : verhindert toepassingen die niet door Microsoft worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="a5fcb-143">**Voer antivirus scan uit** : updates voor Windows Defender antivirus en direct een antivirus scan uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="a5fcb-144">Kies tussen snelle scan of volledige scan.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="a5fcb-145">**Onderzoek pakket verzamelen** : informatie over het apparaat verzamelen.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="a5fcb-146">Wanneer het onderzoek is voltooid, kunt u het downloaden.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="a5fcb-147">**Live antwoordsessie starten** : Laad een externe shell op het apparaat voor [uitgebreid beveiligings onderzoek](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span><span class="sxs-lookup"><span data-stu-id="a5fcb-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="a5fcb-148">Automatisch **onderzoek initiëren** : Hiermee wordt de [bedreiging automatisch onderzocht en hersteld](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span><span class="sxs-lookup"><span data-stu-id="a5fcb-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="a5fcb-149">Hoewel u automatisch controles handmatig moet uitvoeren op deze pagina, activeren [bepaalde waarschuwings beleidsregels](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) zichzelf automatisch onderzoek.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="a5fcb-150">**Onderhoudscentrum** : Hier vindt u informatie over eventuele antwoord acties die op dat moment actief zijn.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="a5fcb-151">Sectietabbladen</span><span class="sxs-lookup"><span data-stu-id="a5fcb-151">Tabs section</span></span>

<span data-ttu-id="a5fcb-152">Op de tabbladen apparaat-profiel kunt u een overzicht van beveiligings Details over het apparaat en de tabellen met een lijst met waarschuwingen wisselen.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="a5fcb-153">Op apparaten die zijn ingeschreven in Microsoft Defender ATP worden ook tabbladen weergegeven die een tijdlijn betreffen, een lijst met beveiligingsaanbevelingen, een inventarisatie van de software, een lijst met ontdekte beveiligingslekken en ontbrekende KBs (beveiligingsupdates).</span><span class="sxs-lookup"><span data-stu-id="a5fcb-153">Devices enrolled in Microsoft Defender ATP will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="a5fcb-154">Tabblad Overzicht</span><span class="sxs-lookup"><span data-stu-id="a5fcb-154">Overview tab</span></span>

<span data-ttu-id="a5fcb-155">Het standaardtabblad is **overzicht**.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-155">The default tab is **Overview**.</span></span> <span data-ttu-id="a5fcb-156">Dit biedt een kort overzicht van het belangrijkste beveiligings feit van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-156">It provides a quick look at the most important security fact about the device.</span></span>

![Afbeelding van het tabblad Overzicht voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="a5fcb-158">Hier ziet u een beknopt overzicht van de actieve waarschuwingen van het apparaat en van gebruikers die momenteel zijn aangemeld.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="a5fcb-159">Als het apparaat is ingeschreven in Microsoft Defender ATP, wordt ook het risiconiveau van het apparaat en de beschikbare gegevens van beveiligings beoordelingen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-159">If the device is enrolled in Microsoft Defender ATP, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="a5fcb-160">Met de beveiligings beoordelingen wordt het belichtings niveau van het apparaat beschreven, aanbevelingen van beveiligingsaanbevelingen en betroffen software en ontdekte beveiligingslekken.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="a5fcb-161">Tabblad waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="a5fcb-161">Alerts tab</span></span>

<span data-ttu-id="a5fcb-162">Het tabblad **waarschuwingen** bevat een lijst met waarschuwingen die op het apparaat zijn geactiveerd, in zowel Azure ATP als Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Azure ATP and Microsoft Defender ATP.</span></span>

![Afbeelding van tabblad Waarschuwingen voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="a5fcb-164">U kunt het aantal weer te geven items aanpassen, evenals de kolommen die worden weergegeven voor elk item.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="a5fcb-165">Het standaardgedrag is een lijst van dertig items per pagina.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="a5fcb-166">De kolommen op dit tabblad bevatten informatie over de ernst van de bedreiging waarmee de waarschuwing werd geactiveerd, evenals de status, het onderzoek en de persoon aan wie de waarschuwing is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="a5fcb-167">De kolom *beïnvloede entiteiten* verwijst naar het apparaat (de entiteit) waarvan u momenteel kijkt, plus andere apparaten in het netwerk waarop dit van invloed is.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="a5fcb-168">Wanneer u een item in deze lijst selecteert, wordt er een flyout met nog meer informatie over de geselecteerde waarschuwing geopend.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="a5fcb-169">U kunt deze lijst filteren op Ernst, status of de persoon aan wie de waarschuwing is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="a5fcb-170">Het tabblad tijdlijn</span><span class="sxs-lookup"><span data-stu-id="a5fcb-170">Timeline tab</span></span>

<span data-ttu-id="a5fcb-171">Het tabblad **tijdlijn** bevat een interactieve, chronologische grafiek van alle gebeurtenissen die op het apparaat zijn geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="a5fcb-172">Als u het gemarkeerde gebied van de grafiek naar links of naar rechts verplaatst, kunt u gebeurtenissen over verschillende tijdsperioden weergeven.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="a5fcb-173">U kunt ook een aangepast datumbereik kiezen in de vervolgkeuzelijst tussen de interactieve grafiek en de lijst met gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="a5fcb-174">Onder de grafiek bevindt zich een lijst met gebeurtenissen voor het geselecteerde datumbereik.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-174">Below the chart is a list of events for the selected range of dates.</span></span>

![Afbeelding van het tabblad tijdlijn voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="a5fcb-176">Het aantal weergegeven items en de kolommen in de lijst kunnen beide worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="a5fcb-177">De lijst standaardkolommen de gebeurtenistijd, actieve gebruiker, actietype, entiteiten (processen) en aanvullende informatie over de gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="a5fcb-178">Wanneer u een item in deze lijst selecteert, wordt er een flyout geopend met de grafiek gebeurtenis entiteiten, met daarin de bovenliggende en onderliggende processen van de gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="a5fcb-179">De lijst kan worden gefilterd op het specifieke type gebeurtenis; bijvoorbeeld register gebeurtenissen of slim schermgebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="a5fcb-180">U kunt de lijst ook exporteren naar een CSV-bestand als u het bestand wilt downloaden.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="a5fcb-181">Hoewel het bestand niet beperkt is van een aantal gebeurtenissen, kunt u kiezen uit zeven dagen wanneer u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="a5fcb-182">Tabblad beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="a5fcb-182">Security recommendations tab</span></span>

<span data-ttu-id="a5fcb-183">Het tabblad **beveiligingsaanbevelingen** bevat een lijst met acties die u kunt uitvoeren om het apparaat te beschermen.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="a5fcb-184">Wanneer u een item in deze lijst selecteert, wordt een flyout geopend waarin u instructies kunt krijgen voor het toepassen van de aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Afbeelding van het tabblad beveiligingsaanbevelingen voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="a5fcb-186">Net als met de vorige tabbladen, het aantal weergegeven items per pagina en de kolommen die zichtbaar zijn, kunnen worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="a5fcb-187">De standaardweergave bevat kolommen die de beantwoorde zwakke punten, de bijbehorende bedreiging, de bijbehorende component of software beïnvloedt door de bedreiging, en nog veel meer.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="a5fcb-188">Items kunnen worden gefilterd op de status van de aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="a5fcb-189">Software-inventarisatie</span><span class="sxs-lookup"><span data-stu-id="a5fcb-189">Software inventory</span></span>

<span data-ttu-id="a5fcb-190">Het tabblad **software-inventaris** bevat een overzicht van de software die op het apparaat is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-190">The **Software inventory** tab lists software installed on the device.</span></span>

![Afbeelding van het tabblad software-inventarisatie voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="a5fcb-192">In de standaardweergave wordt de softwareleverancier, het geïnstalleerde versienummer, het aantal bekende software-zwakke punten, bedreigings inzichten, productcode en tags weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="a5fcb-193">Het aantal weer te geven items en welke kolommen worden weergegeven, kunnen beide worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="a5fcb-194">Wanneer u een item uit deze lijst selecteert, wordt een flyout geopend met meer informatie over de geselecteerde software, en het pad en de tijdstempel voor de laatste keer dat de software is gevonden.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="a5fcb-195">Deze lijst kan worden gefilterd op productcode.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="a5fcb-196">Tabblad ontdekte zwakke plekken</span><span class="sxs-lookup"><span data-stu-id="a5fcb-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="a5fcb-197">Het tabblad **ontdekte beveiligingslekken** bevat veelvoorkomende problemen met CVEs die van invloed kunnen zijn op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Afbeelding van het tabblad ontdekte zwakke plekken voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="a5fcb-199">De standaardweergave toont de ernst van de CVE, de gang van de gangbare punten van het beveiligingslek (CVS), de software die is gerelateerd aan de CVE, wanneer de CVE werd gepubliceerd, wanneer de CVE voor het laatst is bijgewerkt en de Risico's die zijn gekoppeld aan de CVE.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="a5fcb-200">Net als met de vorige tabbladen, zijn het aantal weer te geven items en welke kolommen zichtbaar zijn, kunnen worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="a5fcb-201">Wanneer u een item in deze lijst selecteert, wordt een flyout geopend met de beschrijving van de CVE.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="a5fcb-202">Ontbrekende KBs</span><span class="sxs-lookup"><span data-stu-id="a5fcb-202">Missing KBs</span></span>

<span data-ttu-id="a5fcb-203">Het **ontbrekende tabblad KBs** bevat een lijst met alle Microsoft-updates die nog op het apparaat moeten worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="a5fcb-204">De vraag ' KBs ' in het [Knowledge Base-artikel bevat Knowledge Base-artikelen](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) die deze updates beschrijven. bijvoorbeeld [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="a5fcb-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Afbeelding van ontbrekend tabblad KBS voor apparaatprofiel](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="a5fcb-206">De standaardweergave bevat het bulletin dat de updates, de versie van het besturingssysteem, de desbetreffende producten bevat, CVEs verholpen, het KB-nummer en de tags.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="a5fcb-207">Het aantal weergegeven items per pagina en welke kolommen worden weergegeven, kunnen worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="a5fcb-208">Wanneer u een item selecteert, wordt een flyout geopend dat is gekoppeld aan de update.</span><span class="sxs-lookup"><span data-stu-id="a5fcb-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a5fcb-209">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="a5fcb-209">Related topics</span></span>

* [<span data-ttu-id="a5fcb-210">Overzicht van Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a5fcb-210">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="a5fcb-211">Microsoft Threat Protection inschakelen</span><span class="sxs-lookup"><span data-stu-id="a5fcb-211">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
* [<span data-ttu-id="a5fcb-212">Entiteiten op apparaten onderzoeken met Live antwoord</span><span class="sxs-lookup"><span data-stu-id="a5fcb-212">Investigate entities on devices, using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="a5fcb-213">Geautomatiseerd onderzoek en antwoord (lucht) in Office 365</span><span class="sxs-lookup"><span data-stu-id="a5fcb-213">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
