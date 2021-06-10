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
# <a name="threat-protection"></a>Bedreigingsbeveiliging
[Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) is een geïntegreerd platform voor preventieve beveiliging, detectie na inbreuken, geautomatiseerd onderzoek en antwoord. Defender for Endpoint beschermt eindpunten tegen cyberdreigingen, detecteert geavanceerde aanvallen en datalekken, automatiseert beveiligingsincidenten en verbetert de beveiliging.

> [!TIP]
> Laat uw gebruikers eenvoudig toegang krijgen tot cloudservices en on-premises toepassingen en schakel moderne beheermogelijkheden voor alle apparaten in. Zie Uw externe werknemers beveiligen voor [meer informatie.](/enterprise-mobility-security/remote-work/) 

<center><h2>Microsoft Defender voor Eindpunt</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><b>Bedreiging & vulnerability management</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><b>Surface-beperking voor aanvallen</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <b>Beveiliging van de volgende generatie</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <b>Eindpuntdetectie en -antwoord</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <b>Geautomatiseerd onderzoek en herstel</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <b>Microsoft Threat Experts</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>Gecentraliseerde configuratie en beheer, API's</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Microsoft 365 Defender</a></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>


>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4obJq]

**[Bedreigings- en risicobeheer](next-gen-threat-and-vuln-mgt.md)**<br>
Deze ingebouwde mogelijkheid maakt gebruik van een spelveranderende risicobenadering voor het ontdekken, prioriteren en herstellen van eindpuntproblemen en onjuiste configuraties.

- [Overzicht & vulnerability management bedreiging](next-gen-threat-and-vuln-mgt.md)
- [Aan de slag](tvm-prerequisites.md)
- [Toegang krijgen tot uw beveiligingsstatus](tvm-dashboard-insights.md)
- [Uw beveiligingshouding verbeteren en risico's beperken](tvm-security-recommendation.md)
- [Beveiligingsproblemen op uw apparaten begrijpen](tvm-software-inventory.md)

<a name="asr"></a>

**[Kwetsbaarheid voor aanvallen verminderen](overview-attack-surface-reduction.md)**<br>
De surface reduction set met mogelijkheden voor aanvallen biedt de eerste verdedigingslinie in de stapel. Door ervoor te zorgen dat configuratie-instellingen correct zijn ingesteld en technieken voor risicobeperking worden toegepast, zijn deze mogelijkheden bestand tegen aanvallen en misbruik.

- [Isolatie op basis van hardware](overview-hardware-based-isolation.md)
- [Toepassingsbeheer](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [Apparaatbesturing](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [Bescherming tegen misbruik](exploit-protection.md)
- [Netwerkbeveiliging](network-protection.md), [webbeveiliging](web-protection-overview.md)
- [Beheerde maptoegang](controlled-folders.md)
- [Netwerkfirewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [Regels voor het verminderen van kwetsbaarheid voor aanvallen](attack-surface-reduction.md)

<a name="ngp"></a>

**[Beveiliging van de volgende generatie](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
Om de beveiligingsperimeter van uw netwerk verder te versterken, gebruikt Microsoft Defender voor Eindpunt de volgende generatie beveiliging die is ontworpen om alle soorten nieuwe bedreigingen op te vangen.

- [Gedragscontrole](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [Cloudbeveiliging](/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [Machine learning](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [URL-beveiliging](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [Geautomatiseerde sandbox-service](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

**[Detectie van en reactie op eindpunt](overview-endpoint-detection-response.md)**<br>
De mogelijkheden voor eindpuntdetectie en -reactie worden gebruikt om inbraakpogingen en actieve inbreuken op te sporen, te onderzoeken en te reageren. Met Geavanceerd zoeken hebt u een op query's gebaseerd hulpprogramma voor het zoeken naar bedreigingen waarmee u proactief inbreuken kunt vinden en aangepaste detecties kunt maken.

- [Waarschuwingen](alerts-queue.md)
- [Historische eindpuntgegevens](investigate-machines.md#timeline)
- [Reactie-orkestratie](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [Gerechtelijke verzameling](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [Bedreigingsinformatie](threat-indicator-concepts.md)
- [Geavanceerde detonatie- en analyseservice](respond-file-alerts.md#deep-analysis)
- [Geavanceerd opsporen](advanced-hunting-overview.md)
    - [Aangepaste detectie](overview-custom-detections.md)

<a name="ai"></a>

**[Geautomatiseerd onderzoek en herstel](automated-investigations.md)**<br>
Microsoft Defender voor Eindpunt biedt niet alleen snel reageren op geavanceerde aanvallen, maar biedt ook mogelijkheden voor automatisch onderzoek en herstel om het aantal waarschuwingen in minuten op schaal te verminderen.

- [Geautomatiseerd onderzoek en herstel](automated-investigations.md)
- [Gegevens en resultaten van een geautomatiseerd onderzoek weergeven](auto-investigation-action-center.md)
- [Herstelacties bekijken en goedkeuren](manage-auto-investigation.md)

<a name="mte"></a>

**[Microsoft Threat Experts](microsoft-threat-experts.md)**<br>
Microsoft Defender for Endpoint's new managed threat hunting service biedt proactieve jacht, prioriteit en extra context en inzichten. Microsoft Threat Experts stelt Security Operation Centers (SOC's) verder in staat om bedreigingen snel en nauwkeurig te identificeren en te beantwoorden.

- [Melding van gerichte aanval](microsoft-threat-experts.md)
- [Experts-on-demand](microsoft-threat-experts.md)
- [Uw beheerde Microsoft 365 defender configureren](configure-microsoft-threat-experts.md)

<a name="apis"></a>

**[Gecentraliseerde configuratie en beheer, API's](management-apis.md)**<br>
Integreer Microsoft Defender voor Eindpunt in uw bestaande werkstromen.
- [Onboarding](onboard-configure.md)
- [API- en SIEM-integratie](configure-siem.md)
- [Blootgestelde API's](apis-intro.md)
- [Toegangsbeheer op basis van rollen (RBAC)](rbac.md)
- [Rapportage en trends](threat-protection-reports.md)

<a name="integration"></a>
**[Integratie met Microsoft-oplossingen](threat-protection-integration.md)** <br>
 Microsoft Defender voor Eindpunt wordt rechtstreeks geïntegreerd met verschillende Microsoft-oplossingen, waaronder:
- Intune
- Microsoft Defender voor Office 365
- Microsoft Defender for Identity
- Azure Defender
- Skype voor Bedrijven
- Microsoft Cloud App Security

<a name="mtp"></a>
**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**<br>
 Met Microsoft 365 Defender vormen Microsoft Defender voor Eindpunt en diverse Microsoft-beveiligingsoplossingen een geïntegreerde suite voor bedrijfsdefensie vóór en na inbreuk die inheems is geïntegreerd in eindpunten, identiteit, e-mail en toepassingen om geavanceerde aanvallen op te sporen, te voorkomen, te onderzoeken en automatisch te beantwoorden.
