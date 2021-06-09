---
title: Bedreigingsbeveiliging (Windows 10)
description: Microsoft Defender voor Eindpunt is een geïntegreerd platform voor preventieve beveiliging, detectie na inbreuken, geautomatiseerd onderzoek en antwoord.
keywords: bedreigingsbeveiliging, Microsoft Defender voor eindpunt, surface reduction van aanvallen, bescherming van de volgende generatie, eindpuntdetectie en -respons, geautomatiseerd onderzoek en antwoord, microsoft threat experts, Microsoft Secure Score for Devices, advanced hunting, cyber threat hunting, web threat protection
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 3db1517d87a47aae254d36cfb28f6c057830ef3e
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840992"
---
# <a name="threat-protection"></a><span data-ttu-id="89635-104">Bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="89635-104">Threat Protection</span></span>
<span data-ttu-id="89635-105">[Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) is een geïntegreerd platform voor preventieve beveiliging, detectie na inbreuken, geautomatiseerd onderzoek en antwoord.</span><span class="sxs-lookup"><span data-stu-id="89635-105">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="89635-106">Defender for Endpoint beschermt eindpunten tegen cyberdreigingen, detecteert geavanceerde aanvallen en datalekken, automatiseert beveiligingsincidenten en verbetert de beveiliging.</span><span class="sxs-lookup"><span data-stu-id="89635-106">Defender for Endpoint protects endpoints from cyber threats, detects advanced attacks and data breaches, automates security incidents, and improves security posture.</span></span>

> [!TIP]
> <span data-ttu-id="89635-107">Laat uw gebruikers eenvoudig toegang krijgen tot cloudservices en on-premises toepassingen en schakel moderne beheermogelijkheden voor alle apparaten in.</span><span class="sxs-lookup"><span data-stu-id="89635-107">Enable your users to access cloud services and on-premises applications with ease and enable modern management capabilities for all devices.</span></span> <span data-ttu-id="89635-108">Zie Uw externe werknemers beveiligen voor [meer informatie.](/enterprise-mobility-security/remote-work/)</span><span class="sxs-lookup"><span data-stu-id="89635-108">For more information, see [Secure your remote workforce](/enterprise-mobility-security/remote-work/).</span></span> 

<center><h2><span data-ttu-id="89635-109">Microsoft Defender for Endpoint</center></span><span class="sxs-lookup"><span data-stu-id="89635-109">Microsoft Defender for Endpoint</center></span></span></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><span data-ttu-id="89635-110"><b>Bedreiging & vulnerability management</b></center></a></span><span class="sxs-lookup"><span data-stu-id="89635-110"><b>Threat & vulnerability management</b></center></a></span></span></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><span data-ttu-id="89635-111"><b>Surface-beperking voor aanvallen</b></center></a></span><span class="sxs-lookup"><span data-stu-id="89635-111"><b>Attack surface reduction</b></center></a></span></span></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <span data-ttu-id="89635-112"><b>Beveiliging van de volgende generatie</b></a></center></span><span class="sxs-lookup"><span data-stu-id="89635-112"><b>Next-generation protection</b></a></center></span></span></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <span data-ttu-id="89635-113"><b>Eindpuntdetectie en -antwoord</b></a></center></span><span class="sxs-lookup"><span data-stu-id="89635-113"><b>Endpoint detection and response</b></a></center></span></span></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <span data-ttu-id="89635-114"><b>Geautomatiseerd onderzoek en herstel</b></a></center></span><span class="sxs-lookup"><span data-stu-id="89635-114"><b>Automated investigation and remediation</b></a></center></span></span></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <span data-ttu-id="89635-115"><b>Microsoft Threat Experts</b></a></center></span><span class="sxs-lookup"><span data-stu-id="89635-115"><b>Microsoft Threat Experts</b></a></center></span></span></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="89635-116">
<a href="#apis"><center><b>Gecentraliseerde configuratie en beheer, API's</a></span><span class="sxs-lookup"><span data-stu-id="89635-116">
<a href="#apis"><center><b>Centralized configuration and administration, APIs</a></span></span></b></center></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="89635-117"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span><span class="sxs-lookup"><span data-stu-id="89635-117"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span></span></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>


>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4obJq]

<span data-ttu-id="89635-118">**[Bedreigings- en risicobeheer](next-gen-threat-and-vuln-mgt.md)**</span><span class="sxs-lookup"><span data-stu-id="89635-118">**[Threat & vulnerability management](next-gen-threat-and-vuln-mgt.md)**</span></span><br>
<span data-ttu-id="89635-119">Deze ingebouwde mogelijkheid maakt gebruik van een spelveranderende risicobenadering voor het ontdekken, prioriteren en herstellen van eindpuntproblemen en onjuiste configuraties.</span><span class="sxs-lookup"><span data-stu-id="89635-119">This built-in capability uses a game-changing risk-based approach to the discovery, prioritization, and remediation of endpoint vulnerabilities and misconfigurations.</span></span>

- [<span data-ttu-id="89635-120">Overzicht & vulnerability management bedreiging</span><span class="sxs-lookup"><span data-stu-id="89635-120">Threat & vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="89635-121">Aan de slag</span><span class="sxs-lookup"><span data-stu-id="89635-121">Get started</span></span>](tvm-prerequisites.md)
- [<span data-ttu-id="89635-122">Toegang krijgen tot uw beveiligingsstatus</span><span class="sxs-lookup"><span data-stu-id="89635-122">Access your security posture</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="89635-123">Uw beveiligingshouding verbeteren en risico's beperken</span><span class="sxs-lookup"><span data-stu-id="89635-123">Improve your security posture and reduce risk</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="89635-124">Beveiligingsproblemen op uw apparaten begrijpen</span><span class="sxs-lookup"><span data-stu-id="89635-124">Understand vulnerabilities on your devices</span></span>](tvm-software-inventory.md)

<a name="asr"></a>

<span data-ttu-id="89635-125">**[Kwetsbaarheid voor aanvallen verminderen](overview-attack-surface-reduction.md)**</span><span class="sxs-lookup"><span data-stu-id="89635-125">**[Attack surface reduction](overview-attack-surface-reduction.md)**</span></span><br>
<span data-ttu-id="89635-126">De surface reduction set met mogelijkheden voor aanvallen biedt de eerste verdedigingslinie in de stapel.</span><span class="sxs-lookup"><span data-stu-id="89635-126">The attack surface reduction set of capabilities provide the first line of defense in the stack.</span></span> <span data-ttu-id="89635-127">Door ervoor te zorgen dat configuratie-instellingen correct zijn ingesteld en technieken voor risicobeperking worden toegepast, zijn deze mogelijkheden bestand tegen aanvallen en misbruik.</span><span class="sxs-lookup"><span data-stu-id="89635-127">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span>

- [<span data-ttu-id="89635-128">Isolatie op basis van hardware</span><span class="sxs-lookup"><span data-stu-id="89635-128">Hardware based isolation</span></span>](overview-hardware-based-isolation.md)
- [<span data-ttu-id="89635-129">Toepassingsbeheer</span><span class="sxs-lookup"><span data-stu-id="89635-129">Application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [<span data-ttu-id="89635-130">Apparaatbesturing</span><span class="sxs-lookup"><span data-stu-id="89635-130">Device control</span></span>](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [<span data-ttu-id="89635-131">Bescherming tegen misbruik</span><span class="sxs-lookup"><span data-stu-id="89635-131">Exploit protection</span></span>](exploit-protection.md)
- <span data-ttu-id="89635-132">[Netwerkbeveiliging](network-protection.md), [webbeveiliging](web-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="89635-132">[Network protection](network-protection.md), [web protection](web-protection-overview.md)</span></span>
- [<span data-ttu-id="89635-133">Beheerde maptoegang</span><span class="sxs-lookup"><span data-stu-id="89635-133">Controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="89635-134">Netwerkfirewall</span><span class="sxs-lookup"><span data-stu-id="89635-134">Network firewall</span></span>](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [<span data-ttu-id="89635-135">Regels voor het verminderen van kwetsbaarheid voor aanvallen</span><span class="sxs-lookup"><span data-stu-id="89635-135">Attack surface reduction rules</span></span>](attack-surface-reduction.md)

<a name="ngp"></a>

<span data-ttu-id="89635-136">**[Beveiliging van de volgende generatie](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span><span class="sxs-lookup"><span data-stu-id="89635-136">**[Next-generation protection](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span></span><br>
<span data-ttu-id="89635-137">Om de beveiligingsperimeter van uw netwerk verder te versterken, gebruikt Microsoft Defender voor Eindpunt de volgende generatie beveiliging die is ontworpen om alle soorten nieuwe bedreigingen op te vangen.</span><span class="sxs-lookup"><span data-stu-id="89635-137">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>

- [<span data-ttu-id="89635-138">Gedragscontrole</span><span class="sxs-lookup"><span data-stu-id="89635-138">Behavior monitoring</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="89635-139">Cloudbeveiliging</span><span class="sxs-lookup"><span data-stu-id="89635-139">Cloud-based protection</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [<span data-ttu-id="89635-140">Machine learning</span><span class="sxs-lookup"><span data-stu-id="89635-140">Machine learning</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="89635-141">URL-beveiliging</span><span class="sxs-lookup"><span data-stu-id="89635-141">URL Protection</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [<span data-ttu-id="89635-142">Geautomatiseerde sandbox-service</span><span class="sxs-lookup"><span data-stu-id="89635-142">Automated sandbox service</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

<span data-ttu-id="89635-143">**[Detectie van en reactie op eindpunt](overview-endpoint-detection-response.md)**</span><span class="sxs-lookup"><span data-stu-id="89635-143">**[Endpoint detection and response](overview-endpoint-detection-response.md)**</span></span><br>
<span data-ttu-id="89635-144">De mogelijkheden voor eindpuntdetectie en -reactie worden gebruikt om inbraakpogingen en actieve inbreuken op te sporen, te onderzoeken en te reageren.</span><span class="sxs-lookup"><span data-stu-id="89635-144">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to intrusion attempts and active breaches.</span></span> <span data-ttu-id="89635-145">Met Geavanceerd zoeken hebt u een op query's gebaseerd hulpprogramma voor het zoeken naar bedreigingen waarmee u proactief inbreuken kunt vinden en aangepaste detecties kunt maken.</span><span class="sxs-lookup"><span data-stu-id="89635-145">With Advanced hunting, you have a query-based threat-hunting tool that lets your proactively find breaches and create custom detections.</span></span>

- [<span data-ttu-id="89635-146">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="89635-146">Alerts</span></span>](alerts-queue.md)
- [<span data-ttu-id="89635-147">Historische eindpuntgegevens</span><span class="sxs-lookup"><span data-stu-id="89635-147">Historical endpoint data</span></span>](investigate-machines.md#timeline)
- [<span data-ttu-id="89635-148">Reactie-orkestratie</span><span class="sxs-lookup"><span data-stu-id="89635-148">Response orchestration</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [<span data-ttu-id="89635-149">Gerechtelijke verzameling</span><span class="sxs-lookup"><span data-stu-id="89635-149">Forensic collection</span></span>](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [<span data-ttu-id="89635-150">Bedreigingsinformatie</span><span class="sxs-lookup"><span data-stu-id="89635-150">Threat intelligence</span></span>](threat-indicator-concepts.md)
- [<span data-ttu-id="89635-151">Geavanceerde detonatie- en analyseservice</span><span class="sxs-lookup"><span data-stu-id="89635-151">Advanced detonation and analysis service</span></span>](respond-file-alerts.md#deep-analysis)
- [<span data-ttu-id="89635-152">Geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="89635-152">Advanced hunting</span></span>](advanced-hunting-overview.md)
    - [<span data-ttu-id="89635-153">Aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="89635-153">Custom detections</span></span>](overview-custom-detections.md)

<a name="ai"></a>

<span data-ttu-id="89635-154">**[Geautomatiseerd onderzoek en herstel](automated-investigations.md)**</span><span class="sxs-lookup"><span data-stu-id="89635-154">**[Automated investigation and remediation](automated-investigations.md)**</span></span><br>
<span data-ttu-id="89635-155">Microsoft Defender voor Eindpunt biedt niet alleen snel reageren op geavanceerde aanvallen, maar biedt ook mogelijkheden voor automatisch onderzoek en herstel om het aantal waarschuwingen in minuten op schaal te verminderen.</span><span class="sxs-lookup"><span data-stu-id="89635-155">In addition to quickly responding to advanced attacks, Microsoft Defender for Endpoint offers automatic investigation and remediation capabilities that help reduce the volume of alerts in minutes at scale.</span></span>

- [<span data-ttu-id="89635-156">Geautomatiseerd onderzoek en herstel</span><span class="sxs-lookup"><span data-stu-id="89635-156">Automated investigation and remediation</span></span>](automated-investigations.md)
- [<span data-ttu-id="89635-157">Gegevens en resultaten van een geautomatiseerd onderzoek weergeven</span><span class="sxs-lookup"><span data-stu-id="89635-157">View details and results of automated investigations</span></span>](auto-investigation-action-center.md)
- [<span data-ttu-id="89635-158">Herstelacties bekijken en goedkeuren</span><span class="sxs-lookup"><span data-stu-id="89635-158">View and approve remediation actions</span></span>](manage-auto-investigation.md)

<a name="mte"></a>

<span data-ttu-id="89635-159">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span><span class="sxs-lookup"><span data-stu-id="89635-159">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span></span><br>
<span data-ttu-id="89635-160">Microsoft Defender for Endpoint's new managed threat hunting service biedt proactieve jacht, prioriteit en extra context en inzichten.</span><span class="sxs-lookup"><span data-stu-id="89635-160">Microsoft Defender for Endpoint's new managed threat hunting service provides proactive hunting, prioritization, and additional context and insights.</span></span> <span data-ttu-id="89635-161">Microsoft Threat Experts stelt Security Operation Centers (SOC's) verder in staat om bedreigingen snel en nauwkeurig te identificeren en te beantwoorden.</span><span class="sxs-lookup"><span data-stu-id="89635-161">Microsoft Threat Experts further empowers Security Operation Centers (SOCs) to identify and respond to threats quickly and accurately.</span></span>

- [<span data-ttu-id="89635-162">Melding van gerichte aanval</span><span class="sxs-lookup"><span data-stu-id="89635-162">Targeted attack notification</span></span>](microsoft-threat-experts.md)
- [<span data-ttu-id="89635-163">Experts-on-demand</span><span class="sxs-lookup"><span data-stu-id="89635-163">Experts-on-demand</span></span>](microsoft-threat-experts.md)
- [<span data-ttu-id="89635-164">Uw beheerde Microsoft 365 defender configureren</span><span class="sxs-lookup"><span data-stu-id="89635-164">Configure your Microsoft 365 Defender managed hunting service</span></span>](configure-microsoft-threat-experts.md)

<a name="apis"></a>

<span data-ttu-id="89635-165">**[Gecentraliseerde configuratie en beheer, API's](management-apis.md)**</span><span class="sxs-lookup"><span data-stu-id="89635-165">**[Centralized configuration and administration, APIs](management-apis.md)**</span></span><br>
<span data-ttu-id="89635-166">Integreer Microsoft Defender voor Eindpunt in uw bestaande werkstromen.</span><span class="sxs-lookup"><span data-stu-id="89635-166">Integrate Microsoft Defender for Endpoint into your existing workflows.</span></span>
- [<span data-ttu-id="89635-167">Onboarding</span><span class="sxs-lookup"><span data-stu-id="89635-167">Onboarding</span></span>](onboard-configure.md)
- [<span data-ttu-id="89635-168">API- en SIEM-integratie</span><span class="sxs-lookup"><span data-stu-id="89635-168">API and SIEM integration</span></span>](configure-siem.md)
- [<span data-ttu-id="89635-169">Blootgestelde API's</span><span class="sxs-lookup"><span data-stu-id="89635-169">Exposed APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="89635-170">Toegangsbeheer op basis van rollen (RBAC)</span><span class="sxs-lookup"><span data-stu-id="89635-170">Role-based access control (RBAC)</span></span>](rbac.md)
- [<span data-ttu-id="89635-171">Rapportage en trends</span><span class="sxs-lookup"><span data-stu-id="89635-171">Reporting and trends</span></span>](threat-protection-reports.md)

<a name="integration"></a>
<span data-ttu-id="89635-172">**[Integratie met Microsoft-oplossingen](threat-protection-integration.md)**</span><span class="sxs-lookup"><span data-stu-id="89635-172">**[Integration with Microsoft solutions](threat-protection-integration.md)**</span></span> <br>
 <span data-ttu-id="89635-173">Microsoft Defender voor Eindpunt wordt rechtstreeks geïntegreerd met verschillende Microsoft-oplossingen, waaronder:</span><span class="sxs-lookup"><span data-stu-id="89635-173">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions, including:</span></span>
- <span data-ttu-id="89635-174">Intune</span><span class="sxs-lookup"><span data-stu-id="89635-174">Intune</span></span>
- <span data-ttu-id="89635-175">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="89635-175">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="89635-176">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="89635-176">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="89635-177">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="89635-177">Azure Defender</span></span>
- <span data-ttu-id="89635-178">Skype voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="89635-178">Skype for Business</span></span>
- <span data-ttu-id="89635-179">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="89635-179">Microsoft Cloud App Security</span></span>

<a name="mtp"></a>
<span data-ttu-id="89635-180">**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**</span><span class="sxs-lookup"><span data-stu-id="89635-180">**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**</span></span><br>
 <span data-ttu-id="89635-181">Met Microsoft 365 Defender vormen Microsoft Defender voor Eindpunt en diverse Microsoft-beveiligingsoplossingen een geïntegreerde suite voor bedrijfsdefensie vóór en na inbreuk die inheems is geïntegreerd in eindpunten, identiteit, e-mail en toepassingen om geavanceerde aanvallen op te sporen, te voorkomen, te onderzoeken en automatisch te beantwoorden.</span><span class="sxs-lookup"><span data-stu-id="89635-181">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate, and automatically respond to sophisticated attacks.</span></span>
