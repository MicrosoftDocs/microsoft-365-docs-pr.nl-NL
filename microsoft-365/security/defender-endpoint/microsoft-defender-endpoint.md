---
title: Microsoft Defender voor Eindpunt
description: Microsoft Defender voor Eindpunt is een beveiligingsplatform voor zakelijke eindpunten dat helpt bij het beschermen tegen geavanceerde permanente bedreigingen.
keywords: inleiding tot Microsoft Defender voor Eindpunt, inleiding tot Microsoft Defender voor Eindpunt, cyberbeveiliging, geavanceerde permanente bedreiging, bedrijfsbeveiliging, machine-gedrags sensor, cloudbeveiliging, analyse, bedreigingsinformatie, beperking van het oppervlak van de aanval, bescherming van de volgende generatie, geautomatiseerd onderzoek en herstel, microsoft threat experts, secure score, advanced hunting, Microsoft 365 Defender, cyber threat hunting
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3bab9d0248a2ed8e83807f3c38215e653cba26eb
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843552"
---
# <a name="microsoft-defender-for-endpoint"></a><span data-ttu-id="46165-104">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="46165-104">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="46165-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="46165-105">**Applies to:**</span></span>
- [<span data-ttu-id="46165-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="46165-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="46165-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="46165-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="46165-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="46165-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="46165-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="46165-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> <span data-ttu-id="46165-110">Voor meer informatie over Windows 10 Enterprise Edition-functies en -functionaliteit, zie [Windows 10 Enterprise edition.](https://www.microsoft.com/WindowsForBusiness/buy)</span><span class="sxs-lookup"><span data-stu-id="46165-110">For more info about Windows 10 Enterprise Edition features and functionality, see [Windows 10 Enterprise edition](https://www.microsoft.com/WindowsForBusiness/buy).</span></span>

<span data-ttu-id="46165-111">Microsoft Defender for Endpoint is een beveiligingsplatform voor zakelijke eindpunten dat is ontworpen om bedrijfsnetwerken te helpen geavanceerde bedreigingen te voorkomen, te detecteren, te onderzoeken en erop te reageren.</span><span class="sxs-lookup"><span data-stu-id="46165-111">Microsoft Defender for Endpoint is an enterprise endpoint security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span>
<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

<span data-ttu-id="46165-112">Defender voor Eindpunt gebruikt de volgende combinatie van technologie die is ingebouwd in Windows 10 en de krachtige cloudservice van Microsoft:</span><span class="sxs-lookup"><span data-stu-id="46165-112">Defender for Endpoint uses the following combination of technology built into Windows 10 and Microsoft's robust cloud service:</span></span>

-   <span data-ttu-id="46165-113">**Gedragssensoren voor** eindpunten: deze sensoren Windows 10 ingesloten in Windows 10 verzamelen en verwerken gedragssignalen van het besturingssysteem en verzenden deze sensorgegevens naar uw persoonlijke, geïsoleerde, cloud-exemplaar van Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="46165-113">**Endpoint behavioral sensors**: Embedded in Windows 10, these sensors collect and process behavioral signals from the operating system and send this sensor data to your private, isolated, cloud instance of Microsoft Defender for Endpoint.</span></span>


-   <span data-ttu-id="46165-114">**Cloudbeveiligingsanalyse:** gebruik maken van big data, apparaatleren en unieke Microsoft-optica in het Windows-ecosysteem, enterprise cloudproducten (zoals Office 365) en onlineactiva, gedragssignalen worden vertaald in inzichten, detecties en aanbevolen antwoorden op geavanceerde bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="46165-114">**Cloud security analytics**: Leveraging big-data, device-learning, and unique Microsoft optics across the Windows ecosystem, enterprise cloud products (such as Office 365), and online assets, behavioral signals are translated into insights, detections, and recommended responses to advanced threats.</span></span>

-   <span data-ttu-id="46165-115">**Bedreigingsinformatie:** Gegenereerd door Microsoft-jagers, beveiligingsteams en aangevuld met bedreigingsinformatie die door partners wordt geleverd, stelt Threat Intelligence Defender voor Eindpunt in staat om hulpprogramma's, technieken en procedures voor aanvallers te identificeren en waarschuwingen te genereren wanneer ze worden waargenomen in verzamelde sensorgegevens.</span><span class="sxs-lookup"><span data-stu-id="46165-115">**Threat intelligence**: Generated by Microsoft hunters, security teams, and augmented by threat intelligence provided by partners, threat intelligence enables Defender for Endpoint to identify attacker tools, techniques, and procedures, and generate alerts when they are observed in collected sensor data.</span></span>

<center><h2><span data-ttu-id="46165-116">Microsoft Defender voor Eindpunt</center></span><span class="sxs-lookup"><span data-stu-id="46165-116">Microsoft Defender for Endpoint</center></span></span></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><span data-ttu-id="46165-117"><b>Threat & Vulnerability Management</b></center></a></span><span class="sxs-lookup"><span data-stu-id="46165-117"><b>Threat & Vulnerability Management</b></center></a></span></span></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><span data-ttu-id="46165-118"><b>Surface-beperking voor aanvallen</b></center></a></span><span class="sxs-lookup"><span data-stu-id="46165-118"><b>Attack surface reduction</b></center></a></span></span></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <span data-ttu-id="46165-119"><b>Beveiliging van de volgende generatie</b></a></center></span><span class="sxs-lookup"><span data-stu-id="46165-119"><b>Next-generation protection</b></a></center></span></span></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <span data-ttu-id="46165-120"><b>Eindpuntdetectie en -antwoord</b></a></center></span><span class="sxs-lookup"><span data-stu-id="46165-120"><b>Endpoint detection and response</b></a></center></span></span></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <span data-ttu-id="46165-121"><b>Geautomatiseerd onderzoek en herstel</b></a></center></span><span class="sxs-lookup"><span data-stu-id="46165-121"><b>Automated investigation and remediation</b></a></center></span></span></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <span data-ttu-id="46165-122"><b>Microsoft Threat Experts</b></a></center></span><span class="sxs-lookup"><span data-stu-id="46165-122"><b>Microsoft Threat Experts</b></a></center></span></span></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="46165-123">
<a href="#apis"><center><b>Gecentraliseerde configuratie en beheer, API's</a></span><span class="sxs-lookup"><span data-stu-id="46165-123">
<a href="#apis"><center><b>Centralized configuration and administration, APIs</a></span></span></b></center></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="46165-124"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span><span class="sxs-lookup"><span data-stu-id="46165-124"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span></span></center></b></td>
</tr>
</table>
<br>

<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0] 

> [!TIP]
> - <span data-ttu-id="46165-125">Meer informatie over de nieuwste verbeteringen in Defender voor Eindpunt: Nieuwe functies [in Microsoft Defender voor Eindpunt.](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="46165-125">Learn about the latest enhancements in Defender for Endpoint: [What's new in Microsoft Defender for Endpoint](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
> - <span data-ttu-id="46165-126">Microsoft Defender voor Eindpunt heeft in de recente MITRE-evaluatie toonaangevende mogelijkheden voor optica en detectie gedemonstreerd.</span><span class="sxs-lookup"><span data-stu-id="46165-126">Microsoft Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="46165-127">Lees: [Inzichten uit de MITRE-ATT-&op CK gebaseerde evaluatie](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="46165-127">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<a name="tvm"></a>

<span data-ttu-id="46165-128">**[Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md)**</span><span class="sxs-lookup"><span data-stu-id="46165-128">**[Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md)**</span></span><br>
<span data-ttu-id="46165-129">Deze ingebouwde mogelijkheid maakt gebruik van een spelveranderende risicobenadering voor het ontdekken, prioriteren en herstellen van eindpuntproblemen en onjuiste configuraties.</span><span class="sxs-lookup"><span data-stu-id="46165-129">This built-in capability uses a game-changing risk-based approach to the discovery, prioritization, and remediation of endpoint vulnerabilities and misconfigurations.</span></span> 

<a name="asr"></a>

<span data-ttu-id="46165-130">**[Kwetsbaarheid voor aanvallen verminderen](overview-attack-surface-reduction.md)**</span><span class="sxs-lookup"><span data-stu-id="46165-130">**[Attack surface reduction](overview-attack-surface-reduction.md)**</span></span><br>
<span data-ttu-id="46165-131">De surface reduction set met mogelijkheden voor aanvallen biedt de eerste verdedigingslinie in de stapel.</span><span class="sxs-lookup"><span data-stu-id="46165-131">The attack surface reduction set of capabilities provides the first line of defense in the stack.</span></span> <span data-ttu-id="46165-132">Door ervoor te zorgen dat configuratie-instellingen correct zijn ingesteld en technieken voor risicobeperking worden toegepast, zijn de mogelijkheden bestand tegen aanvallen en misbruik.</span><span class="sxs-lookup"><span data-stu-id="46165-132">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, the capabilities resist attacks and exploitation.</span></span> <span data-ttu-id="46165-133">Deze set mogelijkheden omvat ook [netwerkbeveiliging](network-protection.md) en [webbeveiliging,](web-protection-overview.md)waarmee de toegang tot schadelijke IP-adressen, domeinen en URL's wordt geregeld.</span><span class="sxs-lookup"><span data-stu-id="46165-133">This set of capabilities also includes [network protection](network-protection.md) and [web protection](web-protection-overview.md), which regulate access to malicious IP addresses, domains, and URLs.</span></span> 

<a name="ngp"></a>

<span data-ttu-id="46165-134">**[Beveiliging van de volgende generatie](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span><span class="sxs-lookup"><span data-stu-id="46165-134">**[Next-generation protection](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span></span><br>
<span data-ttu-id="46165-135">Om de beveiligingsperimeter van uw netwerk verder te versterken, gebruikt Microsoft Defender voor Eindpunt de volgende generatie beveiliging die is ontworpen om alle soorten nieuwe bedreigingen op te vangen.</span><span class="sxs-lookup"><span data-stu-id="46165-135">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>

<a name="edr"></a>

<span data-ttu-id="46165-136">**[Detectie van en reactie op eindpunt](overview-endpoint-detection-response.md)**</span><span class="sxs-lookup"><span data-stu-id="46165-136">**[Endpoint detection and response](overview-endpoint-detection-response.md)**</span></span><br>
<span data-ttu-id="46165-137">De mogelijkheden voor eindpuntdetectie en -antwoorden worden gebruikt om geavanceerde bedreigingen op te sporen, te onderzoeken en te beantwoorden, zodat deze mogelijk voorbij de eerste twee beveiligingspijlers zijn gekomen.</span><span class="sxs-lookup"><span data-stu-id="46165-137">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to advanced threats that may have made it past the first two security pillars.</span></span> <span data-ttu-id="46165-138">[Geavanceerde jacht](advanced-hunting-overview.md) biedt een op query's gebaseerd hulpprogramma voor bedreigingsjacht waarmee u proactief inbreuken kunt vinden en aangepaste detecties kunt maken.</span><span class="sxs-lookup"><span data-stu-id="46165-138">[Advanced hunting](advanced-hunting-overview.md) provides a query-based threat-hunting tool that lets you proactively find breaches and create custom detections.</span></span>

<a name="ai"></a>

<span data-ttu-id="46165-139">**[Geautomatiseerd onderzoek en herstel](automated-investigations.md)**</span><span class="sxs-lookup"><span data-stu-id="46165-139">**[Automated investigation and remediation](automated-investigations.md)**</span></span><br>
<span data-ttu-id="46165-140">In combinatie met de mogelijkheid om snel te kunnen reageren op geavanceerde aanvallen, biedt Microsoft Defender voor Eindpunt mogelijkheden voor automatisch onderzoek en herstel om het aantal waarschuwingen in minuten op schaal te verminderen.</span><span class="sxs-lookup"><span data-stu-id="46165-140">In conjunction with being able to quickly respond to advanced attacks, Microsoft Defender for Endpoint offers automatic investigation and remediation capabilities that help reduce the volume of alerts in minutes at scale.</span></span> 

<a name="ss"></a>

<span data-ttu-id="46165-141">**[Microsoft Secure Score voor apparaten](tvm-microsoft-secure-score-devices.md)**</span><span class="sxs-lookup"><span data-stu-id="46165-141">**[Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md)**</span></span><br>

<span data-ttu-id="46165-142">Defender voor Eindpunt bevat Microsoft Secure Score voor apparaten om u te helpen de beveiligingstoestand van uw bedrijfsnetwerk dynamisch te beoordelen, onbeveiligde systemen te identificeren en aanbevolen acties uit te voeren om de algehele beveiliging van uw organisatie te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="46165-142">Defender for Endpoint includes Microsoft Secure Score for Devices to help you dynamically assess the security state of your enterprise network, identify unprotected systems, and take recommended actions to improve the overall security of your organization.</span></span>

<a name="mte"></a>

<span data-ttu-id="46165-143">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span><span class="sxs-lookup"><span data-stu-id="46165-143">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span></span><br>
<span data-ttu-id="46165-144">De nieuwe beheerde bedreigingsjachtservice van Microsoft Defender for Endpoint biedt proactief zoeken, prioriteit geven en extra context en inzichten die beveiligingscentrums (SOC's) in staat stellen om bedreigingen snel en nauwkeurig te identificeren en erop te reageren.</span><span class="sxs-lookup"><span data-stu-id="46165-144">Microsoft Defender for Endpoint's new managed threat hunting service provides proactive hunting, prioritization, and additional context and insights that further empower Security operation centers (SOCs) to identify and respond to threats quickly and accurately.</span></span>

>[!IMPORTANT]
><span data-ttu-id="46165-145">Klanten van Defender voor Eindpunt moeten een aanvraag indienen voor de Microsoft Threat Experts managed threat hunting service om proactieve targeted attack notifications te krijgen en samen te werken met experts op aanvraag.</span><span class="sxs-lookup"><span data-stu-id="46165-145">Defender for Endpoint customers need to apply for the Microsoft Threat Experts managed threat hunting service to get proactive Targeted Attack Notifications and to collaborate with experts on demand.</span></span> <span data-ttu-id="46165-146">Experts on Demand is een invoegservice.</span><span class="sxs-lookup"><span data-stu-id="46165-146">Experts on Demand is an add-on service.</span></span> <span data-ttu-id="46165-147">Targeted Attack Notifications worden altijd opgenomen nadat u bent geaccepteerd in Microsoft Threat Experts managed threat hunting service.</span><span class="sxs-lookup"><span data-stu-id="46165-147">Targeted Attack Notifications are always included after you have been accepted into Microsoft Threat Experts managed threat hunting service.</span></span><p>
><p><span data-ttu-id="46165-148">Als u nog niet bent ingeschreven en de voordelen <b></b> ervan wilt ervaren, gaat u naar Instellingen > <b>algemene</b> > <b></b> geavanceerde > <b>functies Microsoft Threat Experts</b> toe te passen.</span><span class="sxs-lookup"><span data-stu-id="46165-148">If you are not enrolled yet and would like to experience its benefits, go to <b>Settings</b> > <b>General</b> > <b>Advanced features</b> > <b>Microsoft Threat Experts</b> to apply.</span></span> <span data-ttu-id="46165-149">Nadat u deze hebt geaccepteerd, krijgt u de voordelen van Meldingen voor gerichte aanvallen en start u een proefversie van 90 dagen met experts op aanvraag.</span><span class="sxs-lookup"><span data-stu-id="46165-149">Once accepted, you will get the benefits of Targeted Attack Notifications, and start a  90-day trial of Experts on Demand.</span></span> <span data-ttu-id="46165-150">Neem contact op met uw Microsoft-vertegenwoordiger voor een volledig abonnement op aanvraag.</span><span class="sxs-lookup"><span data-stu-id="46165-150">Contact your Microsoft representative to get a full Experts on Demand subscription.</span></span>

<a name="apis"></a>

<span data-ttu-id="46165-151">**[Gecentraliseerde configuratie en beheer, API's](management-apis.md)**</span><span class="sxs-lookup"><span data-stu-id="46165-151">**[Centralized configuration and administration, APIs](management-apis.md)**</span></span><br>
<span data-ttu-id="46165-152">Integreer Microsoft Defender voor Eindpunt in uw bestaande werkstromen.</span><span class="sxs-lookup"><span data-stu-id="46165-152">Integrate Microsoft Defender for Endpoint into your existing workflows.</span></span>

<a name="mtp"></a>

<span data-ttu-id="46165-153">**[Integratie met Microsoft-oplossingen](threat-protection-integration.md)**</span><span class="sxs-lookup"><span data-stu-id="46165-153">**[Integration with Microsoft solutions](threat-protection-integration.md)**</span></span> <br>
<span data-ttu-id="46165-154">Defender for Endpoint wordt rechtstreeks geïntegreerd met verschillende Microsoft-oplossingen, waaronder:</span><span class="sxs-lookup"><span data-stu-id="46165-154">Defender for Endpoint directly integrates with various Microsoft solutions, including:</span></span>
- <span data-ttu-id="46165-155">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="46165-155">Azure Defender</span></span>
- <span data-ttu-id="46165-156">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="46165-156">Azure Sentinel</span></span>
- <span data-ttu-id="46165-157">Intune</span><span class="sxs-lookup"><span data-stu-id="46165-157">Intune</span></span>
- <span data-ttu-id="46165-158">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="46165-158">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="46165-159">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="46165-159">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="46165-160">Microsoft Defender voor Office</span><span class="sxs-lookup"><span data-stu-id="46165-160">Microsoft Defender for Office</span></span>
- <span data-ttu-id="46165-161">Skype voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="46165-161">Skype for Business</span></span>

<span data-ttu-id="46165-162">**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**</span><span class="sxs-lookup"><span data-stu-id="46165-162">**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**</span></span><br>
<span data-ttu-id="46165-163">Met Microsoft 365 Defender, Defender voor Eindpunt en diverse microsoft-beveiligingsoplossingen vormen ze een geïntegreerde suite voor bedrijfsdefensie vóór en na inbreuk die inheems is geïntegreerd in eindpunten, identiteit, e-mail en toepassingen om geavanceerde aanvallen op te sporen, te voorkomen, te onderzoeken en automatisch te beantwoorden.</span><span class="sxs-lookup"><span data-stu-id="46165-163">With Microsoft 365 Defender, Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate, and automatically respond to sophisticated attacks.</span></span>


## <a name="related-topic"></a><span data-ttu-id="46165-164">Verwant onderwerp</span><span class="sxs-lookup"><span data-stu-id="46165-164">Related topic</span></span>
[<span data-ttu-id="46165-165">Microsoft Defender voor Eindpunt helpt bij het opsporen van geavanceerde bedreigingen</span><span class="sxs-lookup"><span data-stu-id="46165-165">Microsoft Defender for Endpoint helps detect sophisticated threats</span></span>](https://www.microsoft.com/itshowcase/microsoft-defender-atps-antivirus-capabilities-boost-malware-protection)
