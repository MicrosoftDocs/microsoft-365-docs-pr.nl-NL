---
title: Device monitoring & Reporting-Beveiligingscentrum
description: Hier wordt beschreven hoe u uw apparaten veilig, up-to-date en mogelijke bedreigingen in uw organisatie kunt beschermen
keywords: beveiliging, malware, Microsoft 365, M365, beveiliging centrum, monitor, rapport, apparatuur
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 638fa558d3bc83b94f1a165e8d087e3770357d42
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200027"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="965cf-104">Apparaten volgen en rapporteren in het Microsoft 365-Beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="965cf-104">Device monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="965cf-105">Zorg dat uw apparaten veilig, up-to-date en potentiële bedreigingen in het Microsoft 365-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="965cf-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="965cf-106">Waarschuwingen voor apparaten weergeven</span><span class="sxs-lookup"><span data-stu-id="965cf-106">View device alerts</span></span>

<span data-ttu-id="965cf-107">U ontvangt actuele meldingen over de overtredings activiteit en andere bedreigingen op uw apparaten in Microsoft Defender ATP (beschikbaar met een E5-licentie).</span><span class="sxs-lookup"><span data-stu-id="965cf-107">Get up-to-date alerts about breach activity and other threats on your devices from Microsoft Defender ATP (available with an E5 license).</span></span> <span data-ttu-id="965cf-108">Microsoft 365-Beveiligingscentrum controleert deze meldingen op een hoog niveau met behulp van de door u gewenste werkstroom.</span><span class="sxs-lookup"><span data-stu-id="965cf-108">Microsoft 365 security center effectively monitors these alerts at a high level using your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="965cf-109">Waarschuwingen voor hoge impact volgen</span><span class="sxs-lookup"><span data-stu-id="965cf-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="965cf-110">Elke Microsoft Defender ATP-waarschuwing heeft een corresponderende Ernst (hoog, normaal, laag of informatie).</span><span class="sxs-lookup"><span data-stu-id="965cf-110">Each Microsoft Defender ATP alert has a corresponding severity (high, medium, low, or informational).</span></span> <span data-ttu-id="965cf-111">Dit geeft de potentiële impact op uw netwerk aan als ze niet aanwezig zijn.</span><span class="sxs-lookup"><span data-stu-id="965cf-111">It indicates potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="965cf-112">U kunt de kaart voor de **geluidssignaal** van uw apparaat gebruiken om specifiekere meldingen te benadrukken en mogelijk direct antwoord te vragen.</span><span class="sxs-lookup"><span data-stu-id="965cf-112">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="965cf-113">Op deze kaart kunt u meer informatie weergeven op de portal Microsoft Defender-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="965cf-113">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![Kaart met ernst van apparaat-waarschuwingen](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="965cf-115">Meer informatie over de bronnen van waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="965cf-115">Understand sources of alerts</span></span>

<span data-ttu-id="965cf-116">Microsoft Defender ATP maakt gebruik van gegevens uit tal van beveiligings sensies en intelligence-bronnen voor het genereren van waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="965cf-116">Microsoft Defender ATP leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="965cf-117">Dit kan bijvoorbeeld de detectie informatie van Microsoft Defender antivirus en van malware van derden gebruiken.</span><span class="sxs-lookup"><span data-stu-id="965cf-117">For example, it can use detection information from Microsoft Defender Antivirus and third-party antimalware.</span></span> <span data-ttu-id="965cf-118">U kunt ook uw eigen aangepaste bedreigings informatie gebruiken die beschikbaar is via de API van de webservice.</span><span class="sxs-lookup"><span data-stu-id="965cf-118">It can also use your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="965cf-119">Op de kaart met de detectie bronnen voor **device-meldingen** ziet u de distributie van waarschuwingen per bron.</span><span class="sxs-lookup"><span data-stu-id="965cf-119">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="965cf-120">Activiteiten bijhouden met betrekking tot bepaalde bronnen, met name de aangepaste bronnen.</span><span class="sxs-lookup"><span data-stu-id="965cf-120">Track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="965cf-121">U kunt ook de kaart gebruiken om te focussen op meldingen die afkomstig zijn van sensoren die niet zijn geconfigureerd om schadelijke activiteiten of onderdelen automatisch te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="965cf-121">You can also use the card to focus on alerts coming from sensors that aren't configured to automatically block malicious activity or components.</span></span>

![Kaart voor detectie bronnen voor apparaat voor meldingen](../../media/device-alert-detection-sources.png)

<span data-ttu-id="965cf-123">Op deze kaart kunt u meer informatie weergeven op de portal Microsoft Defender-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="965cf-123">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="965cf-124">Meer informatie over de typen bedreigingen die waarschuwingen activeren</span><span class="sxs-lookup"><span data-stu-id="965cf-124">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="965cf-125">In Microsoft Defender ATP wordt elke waarschuwing in een categorie gesorteerd in een categorie voor een bepaalde fase in de hack-ketting of het type risico onderdeel.</span><span class="sxs-lookup"><span data-stu-id="965cf-125">Microsoft Defender ATP sorts each alert into a category representing a certain stage in the attack chain or type of threat component.</span></span> <span data-ttu-id="965cf-126">Een gedetecteerde bedreiging is bijvoorbeeld mogelijk gecategoriseerd als ' zijdelings verplaatsings actie ' om aan te geven dat er andere apparaten in het netwerk konden worden bereikt.</span><span class="sxs-lookup"><span data-stu-id="965cf-126">For example, a detected threat activity might be categorized as "lateral movement" to indicate there was an attempt to reach other devices on the network.</span></span> <span data-ttu-id="965cf-127">De activiteit is waarschijnlijk opgetreden nadat een hacker een initiële foothold heeft verkregen.</span><span class="sxs-lookup"><span data-stu-id="965cf-127">The activity has likely occurred after attackers gained an initial foothold.</span></span> <span data-ttu-id="965cf-128">Wanneer deze worden gedetecteerd, kan een onderdeel van de bedreiging algemeen als malware of specifiek risico type worden geclassificeerd.</span><span class="sxs-lookup"><span data-stu-id="965cf-128">When detected, a threat component might be classified broadly as malware or specifically as a specific threat type.</span></span> <span data-ttu-id="965cf-129">Specifieke voorbeelden van Ransomware, referentie diefstal of andere typen kwaadaardige en ongewenste software.</span><span class="sxs-lookup"><span data-stu-id="965cf-129">Specifics include ransomware, credential stealing, or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="965cf-130">De kaart **bedreigings categorieën voor apparaten** toont de distributie van waarschuwingen in deze categorieën.</span><span class="sxs-lookup"><span data-stu-id="965cf-130">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="965cf-131">Met deze informatie kunt u bedreigings activiteiten identificeren, zoals diefstal van referenties, die meestal hoger zijn dan de pogingen van sociale engineering.</span><span class="sxs-lookup"><span data-stu-id="965cf-131">Use this information to identify threat activity, such as credential theft attempts, that usually have higher impact than social engineering attempts.</span></span> <span data-ttu-id="965cf-132">U kunt ook controleren op mogelijk destructieve bedreigingen, zoals Ransomware.</span><span class="sxs-lookup"><span data-stu-id="965cf-132">You can also to monitor for potentially destructive threats like ransomware.</span></span>

![Kaart bedreiging categorieën voor apparatuur](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="965cf-134">Actieve waarschuwingen controleren</span><span class="sxs-lookup"><span data-stu-id="965cf-134">Monitor active alerts</span></span>

<span data-ttu-id="965cf-135">De **melding status** kaart van het apparaat geeft het aantal waarschuwingen aan dat nog niet is opgelost en waarvan de aandacht moet worden besteed.</span><span class="sxs-lookup"><span data-stu-id="965cf-135">The **Device alert status** card indicates the number of alerts that haven't been resolved and may require attention.</span></span> <span data-ttu-id="965cf-136">Op deze kaart kunt u meer informatie weergeven op de portal Microsoft Defender-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="965cf-136">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![Meldings status kaart van apparaat](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="965cf-138">De classificatie van opgeloste waarschuwingen controleren</span><span class="sxs-lookup"><span data-stu-id="965cf-138">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="965cf-139">Wanneer u een Microsoft Defender ATP-waarschuwing verhelpt, kunnen uw beveiligingspersoneel opgeven of een waarschuwing is geverifieerd als:</span><span class="sxs-lookup"><span data-stu-id="965cf-139">When resolving a Microsoft Defender ATP alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="965cf-140">Een echte waarschuwing waarin de feitelijke activiteiten van de overtreding of de bedreigings onderdelen worden aangegeven</span><span class="sxs-lookup"><span data-stu-id="965cf-140">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="965cf-141">Een onjuiste waarschuwing met een onjuiste detectie van normaal activiteiten</span><span class="sxs-lookup"><span data-stu-id="965cf-141">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="965cf-142">De **classificatie** kaart voor melding van apparaat geeft aan of de opgeloste waarschuwingen zijn geclassificeerd als waar of onwaar.</span><span class="sxs-lookup"><span data-stu-id="965cf-142">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="965cf-143">Op deze kaart kunt u meer informatie weergeven op de portal Microsoft Defender-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="965cf-143">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="965cf-144">Opmerking: in sommige gevallen is classificatie informatie niet beschikbaar voor bepaalde meldingen.</span><span class="sxs-lookup"><span data-stu-id="965cf-144">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![Classificatie kaart voor het ontvangen van hardware](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="965cf-146">Controle bepaling van opgeloste waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="965cf-146">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="965cf-147">Als u een melding wilt ontvangen, ongeacht of een waarschuwing waar of onwaar is tijdens de oplossing, kunnen uw beveiligingspersoneel een bepaling leveren.</span><span class="sxs-lookup"><span data-stu-id="965cf-147">Along with classifying whether an alert is true or false during resolution, your security staff can provide a determination.</span></span> <span data-ttu-id="965cf-148">Een bepaling geeft het type normale of schadelijke activiteit aan dat is gevonden bij het valideren van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="965cf-148">A determination indicates the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="965cf-149">De kaart voor de **waarschuwings analyse** van uw apparaat toont de bepaling die voor elke melding wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="965cf-149">The **Device alert determination** card shows the determination provided for each alert.</span></span>

* <span data-ttu-id="965cf-150">**Apt**: geavanceerde permanente bedreiging, waarmee wordt aangegeven dat de gedetecteerde activiteit of de bedreiging onderdeel is onderdeel van een verfijnde geschaade schending, ontwikkeld voor het verkrijgen van een foothold in de betreffende netwerk</span><span class="sxs-lookup"><span data-stu-id="965cf-150">**APT**: advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="965cf-151">**Malware**: schadelijk bestand of programmacode</span><span class="sxs-lookup"><span data-stu-id="965cf-151">**Malware**: malicious file or code</span></span>
* <span data-ttu-id="965cf-152">**Beveiligingspersoneel**: normale activiteit uitgevoerd door beveiligingspersoneel</span><span class="sxs-lookup"><span data-stu-id="965cf-152">**Security personnel**: normal activity performed by security staff</span></span>
* <span data-ttu-id="965cf-153">**Beveiliging testen**: activiteit of onderdelen die zijn ontworpen om feitelijke bedreigingen te simuleren en om meldingen te activeren en waarschuwingen te genereren</span><span class="sxs-lookup"><span data-stu-id="965cf-153">**Security testing**: activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="965cf-154">**Ongewenste software**: apps en andere software die niet als schadelijk worden beschouwd, maar op een andere wijze beleidsregels of acceptabele gebruiks normen schenden</span><span class="sxs-lookup"><span data-stu-id="965cf-154">**Unwanted software**: apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="965cf-155">**Andere**bepalingen die niet onder de geleverde soorten vallen.</span><span class="sxs-lookup"><span data-stu-id="965cf-155">**Others**: any other determination that doesn't fall under the provided types</span></span>

<span data-ttu-id="965cf-156">Vanaf dit kaartje kunt u meer informatie weergeven in Microsoft Defender-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="965cf-156">From this card, you can view more information in Microsoft Defender Security Center.</span></span>

![Waarschuwings kaart voor apparaat](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="965cf-158">Begrijpen welke apparaten risico lopen</span><span class="sxs-lookup"><span data-stu-id="965cf-158">Understand which devices are at risk</span></span>

<span data-ttu-id="965cf-159">**Apparaat-bescherming** toont het risiconiveau voor apparaten.</span><span class="sxs-lookup"><span data-stu-id="965cf-159">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="965cf-160">Het risiconiveau is gebaseerd op factoren zoals het type en de ernst van waarschuwingen op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="965cf-160">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![Hardware-beschermings kaart](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="965cf-162">De status van intune-beheerde apparaten controleren en rapporteren</span><span class="sxs-lookup"><span data-stu-id="965cf-162">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="965cf-163">De volgende rapporten bevatten gegevens van apparaten die zijn geregistreerd voor intune.</span><span class="sxs-lookup"><span data-stu-id="965cf-163">The following reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="965cf-164">Gegevens van niet-geregistreerde apparaten zijn niet inbegrepen.</span><span class="sxs-lookup"><span data-stu-id="965cf-164">Data from unenrolled devices isn't included.</span></span> <span data-ttu-id="965cf-165">Alleen globale beheerders kunnen deze kaarten weergeven.</span><span class="sxs-lookup"><span data-stu-id="965cf-165">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="965cf-166">InTune geregistreerde apparaatgegevens zijn onder meer:</span><span class="sxs-lookup"><span data-stu-id="965cf-166">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="965cf-167">Apparaatcompatibiliteit</span><span class="sxs-lookup"><span data-stu-id="965cf-167">Device compliance</span></span>
* <span data-ttu-id="965cf-168">Apparaten met actieve malware</span><span class="sxs-lookup"><span data-stu-id="965cf-168">Devices with active malware</span></span>
* <span data-ttu-id="965cf-169">Typen malware op apparaten</span><span class="sxs-lookup"><span data-stu-id="965cf-169">Types of malware on devices</span></span>
* <span data-ttu-id="965cf-170">Malware op apparaten</span><span class="sxs-lookup"><span data-stu-id="965cf-170">Malware on devices</span></span>
* <span data-ttu-id="965cf-171">Apparaten met detectie van malware</span><span class="sxs-lookup"><span data-stu-id="965cf-171">Devices with malware detections</span></span>
* <span data-ttu-id="965cf-172">Gebruikers met detectie van malware</span><span class="sxs-lookup"><span data-stu-id="965cf-172">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="965cf-173">Naleving van apparaat controleren</span><span class="sxs-lookup"><span data-stu-id="965cf-173">Monitor device compliance</span></span>

<span data-ttu-id="965cf-174">**Naleving van apparaat** laat zien hoeveel apparaten zijn geregistreerd voor intune-afnaleving met het configuratiebeleid.</span><span class="sxs-lookup"><span data-stu-id="965cf-174">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![Hardware compliantie kaart](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="965cf-176">Apparaten detecteren met detectie van malware</span><span class="sxs-lookup"><span data-stu-id="965cf-176">Discover devices with malware detections</span></span>

<span data-ttu-id="965cf-177">**Detectie van detectie van apparaat** geeft het aantal niet-geregistreerde apparaten met malware aan dat niet volledig is opgelost.</span><span class="sxs-lookup"><span data-stu-id="965cf-177">**Device malware detections** provide the number of Intune enrolled devices with malware that hasn't been fully resolved.</span></span> <span data-ttu-id="965cf-178">Het gebrek aan de oplossing kan zijn vanwege acties die in behandeling zijn, een herstart, een volledige scan, handmatige actie van gebruikers of als de herstelbewerking is voltooid.</span><span class="sxs-lookup"><span data-stu-id="965cf-178">A lack of resolution can be because of pending actions, a restart, a full scan, manual user actions, or if the remediation action was not successfully completed.</span></span>

![Kaart detectie van apparaat voor malware](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="965cf-180">Meer informatie over de verschillende typen malware</span><span class="sxs-lookup"><span data-stu-id="965cf-180">Understand the types of malware detected</span></span>

<span data-ttu-id="965cf-181">Met de **typen malware op apparaten** worden verschillende soorten malware weergegeven die zijn gedetecteerd op apparaten die zijn ingeschreven in intune.</span><span class="sxs-lookup"><span data-stu-id="965cf-181">**Types of malware on devices** show different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="965cf-182">U kunt elk type onderzoeken in het Microsoft 365-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="965cf-182">You can investigate each type in the Microsoft 365 security center.</span></span>

![Type malware op de kaart apparaten](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="965cf-184">Meer informatie over de specifieke malware die op uw apparaten is gedetecteerd</span><span class="sxs-lookup"><span data-stu-id="965cf-184">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="965cf-185">**Malware op apparaten** biedt een lijst met de specifieke malware die op uw apparaten is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="965cf-185">**Malware on devices** provides a list of the specific malware detected on your devices.</span></span>

![Malware op apparaten kaart](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="965cf-187">Begrijpen welke apparaten de beste malware hebben</span><span class="sxs-lookup"><span data-stu-id="965cf-187">Understand which devices have the most malware</span></span>

<span data-ttu-id="965cf-188">**Apparaten met detectie van malware** tonen welke apparaten de meeste detectie van malware hebben.</span><span class="sxs-lookup"><span data-stu-id="965cf-188">**Devices with malware detections** show which devices have the most malware detections.</span></span> <span data-ttu-id="965cf-189">in het Microsoft 365-Beveiligingscentrum kunt u nagaan of er malware actief is die het apparaat gebruikt en de Beheerstatus in intune.</span><span class="sxs-lookup"><span data-stu-id="965cf-189">in the Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![Apparaten met detectie van detectie van malware](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="965cf-191">Begrijpen welke gebruikers apparaten met de meeste malware hebben</span><span class="sxs-lookup"><span data-stu-id="965cf-191">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="965cf-192">**Gebruikers met malware-detectie** geven gebruikers weer met apparaten die de meeste detectie van malware hebben.</span><span class="sxs-lookup"><span data-stu-id="965cf-192">**Users with malware detections** show users with devices that had the most malware detections.</span></span> <span data-ttu-id="965cf-193">In het Microsoft 365-Beveiligingscentrum kunt u zien hoeveel apparaten aan elke gebruiker zijn toegewezen en meer informatie over elk apparaat en het type malware.</span><span class="sxs-lookup"><span data-stu-id="965cf-193">In the Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![Gebruikers met detectie Card voor malware](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-attack-surface-reduction-rule-deployment-and-detections"></a><span data-ttu-id="965cf-195">Implementatie en detectie van aanvals regels controleren en beheren</span><span class="sxs-lookup"><span data-stu-id="965cf-195">Monitor and manage attack surface reduction rule deployment and detections</span></span>

<span data-ttu-id="965cf-196">Regels voor het beperken van een [aanval (ASR)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) helpen voorkomen dat acties en apps die meestal door misbruik worden gebruikt, malware willen infecteren.</span><span class="sxs-lookup"><span data-stu-id="965cf-196">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) help prevent actions and apps that are typically used by exploit-seeking malware to infect devices.</span></span> <span data-ttu-id="965cf-197">Met deze regels wordt bepaald wanneer en hoe de uitvoerbare bestanden kunnen worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="965cf-197">These rules control when and how executables can run.</span></span> <span data-ttu-id="965cf-198">U kunt voorkomen dat u een gedownload uitvoerbare uitvoerbare uitvoerbare uitvoerbare uitvoerbare uitvoerbare bestanden uitvoert, Win32 API-oproepen van Office-macro's blokkeert of processen die worden uitgevoerd vanaf USB-stations blokkeren.</span><span class="sxs-lookup"><span data-stu-id="965cf-198">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![Beperking voor oppervlakte van aanval](../../media/attack-surface-reduction-rules.png)

<span data-ttu-id="965cf-200">De kaart **reductie regels** van een aanval biedt een overzicht van de implementatie van regels op uw apparaten.</span><span class="sxs-lookup"><span data-stu-id="965cf-200">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="965cf-201">De bovenste balk van de kaart toont het totale aantal apparaten dat zich in de volgende implementatie modi bevindt:</span><span class="sxs-lookup"><span data-stu-id="965cf-201">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="965cf-202">**Blokmodus**: apparaten met minimaal één regel geconfigureerd om gedetecteerde activiteiten blokkeren</span><span class="sxs-lookup"><span data-stu-id="965cf-202">**Block mode**: devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="965cf-203">**Controlemodus**: apparaten zonder regels die zijn ingesteld voor het blokkeren van gedetecteerde activiteiten, maar er is minimaal één regel ingesteld om controle gedetecteerde activiteiten te controleren</span><span class="sxs-lookup"><span data-stu-id="965cf-203">**Audit mode**: devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="965cf-204">**Uitgeschakeld**: apparaten met alle ASR-regels uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="965cf-204">**Off**: devices with all ASR rules turned off</span></span>

<span data-ttu-id="965cf-205">In het onderste gedeelte van dit kaartje worden instellingen weergegeven op regel op uw apparaten.</span><span class="sxs-lookup"><span data-stu-id="965cf-205">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="965cf-206">Met elke balk wordt het aantal apparaten aangegeven dat is ingesteld op blokkeren, controleren en controleren of de regel volledig is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="965cf-206">Each bar indicates the number of devices that are set to block, audit detection, or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="965cf-207">Detectie van ASR weergeven</span><span class="sxs-lookup"><span data-stu-id="965cf-207">View ASR detections</span></span>

<span data-ttu-id="965cf-208">Als u gedetailleerde informatie over de detectie van de ASR-regel wilt weergeven in uw netwerk, selecteert u **detectie van detectie weergeven** op de kaart voor het risico voor **oppervlakte-aanval** .</span><span class="sxs-lookup"><span data-stu-id="965cf-208">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="965cf-209">Het tabblad **detectie** op de pagina gedetailleerd rapport wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="965cf-209">The **Detections** tab in the detailed report page will open.</span></span>

![Tabblad detectie](../../media/detections-tab.png)

<span data-ttu-id="965cf-211">De grafiek boven aan de pagina toont detecties van detectie van tijds stapels die zijn geblokkeerd of gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="965cf-211">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="965cf-212">De tabel onderaan bevat de meest recente detecties.</span><span class="sxs-lookup"><span data-stu-id="965cf-212">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="965cf-213">Gebruik de volgende informatie op de tabel om inzicht te krijgen in de aard van de detecties:</span><span class="sxs-lookup"><span data-stu-id="965cf-213">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="965cf-214">**Vastgesteld bestand**: het bestand, meestal een script of een document, waarvan de inhoud de inhoud van de verdachte aanval heeft geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="965cf-214">**Detected file**: the file, typically a script or document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="965cf-215">**Regel**: naam waarmee de aanvals activiteiten worden beschreven die de regel is bedoeld om te worden onderschept.</span><span class="sxs-lookup"><span data-stu-id="965cf-215">**Rule**: name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="965cf-216">Meer informatie over bestaande ASR-regels</span><span class="sxs-lookup"><span data-stu-id="965cf-216">Read about existing ASR rules</span></span>
* <span data-ttu-id="965cf-217">**Bron-app**: de toepassing die inhoud heeft geladen of uitgevoerd met de activering van de verdachte aanvals activiteit.</span><span class="sxs-lookup"><span data-stu-id="965cf-217">**Source app**: the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="965cf-218">Het kan een legitieme toepassing zijn, zoals een webbrowser, een Office-toepassing of een systeem hulpmiddel zoals PowerShell</span><span class="sxs-lookup"><span data-stu-id="965cf-218">It could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="965cf-219">**Uitgever**: de leverancier die de bron-app heeft vrijgegeven</span><span class="sxs-lookup"><span data-stu-id="965cf-219">**Publisher**: the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="965cf-220">Instellingen voor ASR-regel voor apparaat controleren</span><span class="sxs-lookup"><span data-stu-id="965cf-220">Review device ASR rule settings</span></span>

<span data-ttu-id="965cf-221">Ga op de pagina het rapport **regels voor risicobeperking** voor een aanval naar het tabblad **configuratie** om regelinstellingen voor afzonderlijke apparaten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="965cf-221">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="965cf-222">Selecteer een apparaat voor gedetailleerde informatie over het feit of elke regel in de blokmodus, de controlemodus of helemaal is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="965cf-222">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

![Het tabblad Configuratie](../../media/configuration-tab.png)

<span data-ttu-id="965cf-224">Microsoft intune biedt beheerfuncties voor de ASR-regels.</span><span class="sxs-lookup"><span data-stu-id="965cf-224">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="965cf-225">Als u uw instellingen wilt bijwerken, selecteert u **aan de slag** onder **apparaten configureren** op het tabblad om Apparaatbeheer te openen op intune.</span><span class="sxs-lookup"><span data-stu-id="965cf-225">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="965cf-226">Bestanden uitsluiten van ASR-regels</span><span class="sxs-lookup"><span data-stu-id="965cf-226">Exclude files from ASR rules</span></span>

<span data-ttu-id="965cf-227">Microsoft 365-Beveiligingscentrum verzamelt de namen van de [bestanden die u mogelijk niet wilt uitsluiten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) van detecties voor de risico regels.</span><span class="sxs-lookup"><span data-stu-id="965cf-227">Microsoft 365 security center collects the names of the [files you might want to exclude](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) from detections by attack surface reduction rules.</span></span> <span data-ttu-id="965cf-228">Door bestanden uit te sluiten, kunt u ongunstige detecties beperken en de beperking voor risico oppervlakte beperking in de blokmodus vertrouwen.</span><span class="sxs-lookup"><span data-stu-id="965cf-228">By excluding files, you can reduce false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="965cf-229">De uitsluitingen worden beheerd op Microsoft intune, maar Microsoft 365 Beveiligingscentrum biedt een hulpmiddel waarmee u de bestanden kunt begrijpen.</span><span class="sxs-lookup"><span data-stu-id="965cf-229">The exclusions are managed on Microsoft Intune, but Microsoft 365 security center provides an analysis tool to help you understand the files.</span></span> <span data-ttu-id="965cf-230">Als u wilt beginnen met het verzamelen van bestanden voor uitsluiting, gaat u naar het tabblad **Uitsluitingen toevoegen** op de rapportpagina regels voor risicobeperking van de **aanval** .</span><span class="sxs-lookup"><span data-stu-id="965cf-230">To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

>[!NOTE]  
><span data-ttu-id="965cf-231">Met het hulpprogramma worden detecties van alle aanvals regels geanalyseerd, maar [slechts enkele regels ondersteunen uitgesloten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)verbindingen.</span><span class="sxs-lookup"><span data-stu-id="965cf-231">The tool analyzes detections by all attack surface reduction rules, but [only some rules support exclusions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).</span></span>

![Tabblad uitzonderingen toevoegen](../../media/add-exclusions-tab.png)

<span data-ttu-id="965cf-233">De tabel bevat een overzicht van alle bestandsnamen die door uw aanvals regels voor oppervlakte worden gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="965cf-233">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="965cf-234">U kunt bestanden selecteren om de gevolgen van de uitsluiting ervan te controleren:</span><span class="sxs-lookup"><span data-stu-id="965cf-234">You can select files to review the impact of excluding them:</span></span>

* <span data-ttu-id="965cf-235">Hoeveel minder detecteren</span><span class="sxs-lookup"><span data-stu-id="965cf-235">How many fewer detections</span></span>
* <span data-ttu-id="965cf-236">Hoeveel minder apparaten de detecties rapporteren</span><span class="sxs-lookup"><span data-stu-id="965cf-236">How many fewer devices report the detections</span></span>

<span data-ttu-id="965cf-237">Als u een lijst met de geselecteerde bestanden met hun volledige paden voor uitsluiting wilt weergeven, selecteert u **uitsluitings paden aanvragen**.</span><span class="sxs-lookup"><span data-stu-id="965cf-237">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="965cf-238">Logboeken voor de inlog regels voor ASR-regels die **van het Windows Local Security Authority Subsystem (lsass.exe) worden gestolen** de bron-app **lsass.exe**vastleggen.</span><span class="sxs-lookup"><span data-stu-id="965cf-238">Logs for the ASR rule **Block credential stealing from the Windows local security authority subsystem (lsass.exe)** capture the source app **lsass.exe**.</span></span> <span data-ttu-id="965cf-239">Het is een normaal systeembestand, maar vastgelegd als het gevonden bestand.</span><span class="sxs-lookup"><span data-stu-id="965cf-239">It is a normal system file, but captured as the detected file.</span></span> <span data-ttu-id="965cf-240">De gegenereerde lijst met uitgesloten paden bevat daarom het bestand.</span><span class="sxs-lookup"><span data-stu-id="965cf-240">As a result, the generated list of exclusion paths will include this file.</span></span> <span data-ttu-id="965cf-241">Als u het bestand wilt uitsluiten dat deze regel heeft geactiveerd in plaats van **lsass.exe**, gebruikt u het pad naar de bron-app in plaats van het gevonden bestand.</span><span class="sxs-lookup"><span data-stu-id="965cf-241">To exclude the file that triggered this rule instead of **lsass.exe**, use the path to the source app instead of the detected file.</span></span>

<span data-ttu-id="965cf-242">U kunt de bron-app vinden door de volgende [geavanceerde zoekopdracht](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) uit te voeren voor deze specifieke regel (aangeduid met regel-id 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span><span class="sxs-lookup"><span data-stu-id="965cf-242">To locate the source app, run the following [advanced hunting query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) for this specific rule (identified by rule ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a><span data-ttu-id="965cf-243">Bestanden controleren op uitsluiting</span><span class="sxs-lookup"><span data-stu-id="965cf-243">Check files for exclusion</span></span>

<span data-ttu-id="965cf-244">Voordat u een bestand uit ASR uitsluit, is het raadzaam om het bestand te controleren om te bepalen of het bestand daadwerkelijk niet schadelijk is.</span><span class="sxs-lookup"><span data-stu-id="965cf-244">Before excluding a file from ASR, we recommend that you inspect the file to determine if it's indeed not malicious.</span></span>

<span data-ttu-id="965cf-245">Als u een bestand wilt controleren, gebruikt u de [pagina met bestandsinformatie](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) in Microsoft Defender-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="965cf-245">To review a file, use the [file information page](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) on Microsoft Defender Security Center.</span></span> <span data-ttu-id="965cf-246">Op de pagina vindt u informatie over de prevalentie en de bezorgings verhouding VirusTotal antivirus.</span><span class="sxs-lookup"><span data-stu-id="965cf-246">The page provides prevalence information and the VirusTotal antivirus detection ratio.</span></span> <span data-ttu-id="965cf-247">U kunt de pagina ook gebruiken om het bestand in te dienen voor uitgebreide analyse.</span><span class="sxs-lookup"><span data-stu-id="965cf-247">You can also use the page to submit the file for deep analysis.</span></span>

<span data-ttu-id="965cf-248">Als u een gevonden bestand wilt zoeken in Microsoft Defender-Beveiligingscentrum, zoekt u alle ASR-detecties met behulp van de volgende geavanceerde zoekopdracht:</span><span class="sxs-lookup"><span data-stu-id="965cf-248">To locate a detected file in Microsoft Defender Security Center, search for all ASR detections using the following advanced hunting query:</span></span>

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

<span data-ttu-id="965cf-249">Gebruik de **UDDI-of de** **InitiatingProcessSHA1** in de zoekresultaten om het bestand te zoeken met behulp van de universele zoekbalk in Microsoft Defender-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="965cf-249">Use the **SHA1** or the **InitiatingProcessSHA1** in the results to search for the file using the universal search bar in Microsoft Defender Security Center.</span></span>
