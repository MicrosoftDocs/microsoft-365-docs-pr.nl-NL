---
title: Microsoft Defender voor Eindpunt
description: Microsoft Defender voor Eindpunt is een beveiligingsplatform voor zakelijke eindpunten dat helpt bij het beschermen tegen geavanceerde permanente bedreigingen.
keywords: inleiding tot Microsoft Defender voor Eindpunt, inleiding tot Microsoft Defender Advanced Threat Protection, inleiding tot Microsoft Defender voor Endpoint, cyberbeveiliging, geavanceerde permanente bedreiging, bedrijfsbeveiliging, computergedrags sensor, cloudbeveiliging, analyse, bedreigingsinformatie, aanvalsoppervlakverminding, beveiliging van de volgende generatie, geautomatiseerd onderzoek en herstel, microsoft threat experts, secure score, advanced hunting, microsoft threat protection, cyber threat hunting
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
ms.openlocfilehash: adc7d780c1af73d8cb4fe229720ac2ed74f90251
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861825"
---
# <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender voor Eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> Zie Windows 10 Enterprise edition voor meer informatie over de functies en functionaliteit van [Windows 10 Enterprise Edition.](https://www.microsoft.com/WindowsForBusiness/buy)

Microsoft Defender for Endpoint is een beveiligingsplatform voor zakelijke eindpunten dat is ontworpen om bedrijfsnetwerken te helpen geavanceerde bedreigingen te voorkomen, te detecteren, te onderzoeken en erop te reageren.
<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

Defender voor Eindpunt gebruikt de volgende combinatie van technologie die is ingebouwd in Windows 10 en de krachtige cloudservice van Microsoft:

-   **Gedragssensoren voor** eindpunten: Deze sensoren, ingesloten in Windows 10, verzamelen en verwerken gedragssignalen van het besturingssysteem en verzenden deze sensorgegevens naar uw persoonlijke, geïsoleerde, cloud-exemplaar van Microsoft Defender voor Eindpunt.


-   **Cloudbeveiligingsanalyse:** gebruikmakend van big data, apparaatleren en unieke Microsoft-optica in het Windows-ecosysteem, enterprise cloudproducten (zoals Office 365) en onlineactiva, worden gedragssignalen vertaald in inzichten, detecties en aanbevolen antwoorden op geavanceerde bedreigingen.

-   **Bedreigingsinformatie:** Gegenereerd door Microsoft-jagers, beveiligingsteams en aangevuld met bedreigingsinformatie die door partners wordt geleverd, stelt Threat Intelligence Defender voor Eindpunt in staat om hulpprogramma's, technieken en procedures voor aanvallers te identificeren en waarschuwingen te genereren wanneer ze worden waargenomen in verzamelde sensorgegevens.

<center><h2>Microsoft Defender voor Eindpunt</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><b>Threat & Vulnerability Management</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>Surface-beperking voor aanvallen</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <b>Beveiliging van de volgende generatie</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <b>Eindpuntdetectie en -antwoord</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <b>Geautomatiseerd onderzoek en herstel</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <b>Microsoft Threat Experts</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>Gecentraliseerde configuratie en beheer, API's</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Microsoft Threat Protection</a></center></b></td>
</tr>
</table>
<br>

<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0] 

> [!TIP]
> - Meer informatie over de nieuwste verbeteringen in Defender voor Eindpunt: Nieuwe functies [in Microsoft Defender voor Eindpunt.](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)
> - Microsoft Defender voor Eindpunt heeft in de recente MITRE-evaluatie toonaangevende mogelijkheden voor optica en detectie gedemonstreerd. Lees: [Inzichten uit de MITRE-ATT-&op CK gebaseerde evaluatie](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

<a name="tvm"></a>

**[Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md)**<br>
Deze ingebouwde mogelijkheid maakt gebruik van een spelveranderende risicobenadering voor het ontdekken, prioriteren en herstellen van eindpuntproblemen en onjuiste configuraties. 

<a name="asr"></a>

**[Kwetsbaarheid voor aanvallen verminderen](overview-attack-surface-reduction.md)**<br>
De surface reduction set met mogelijkheden voor aanvallen biedt de eerste verdedigingslinie in de stapel. Door ervoor te zorgen dat configuratie-instellingen correct zijn ingesteld en technieken voor risicobeperking worden toegepast, zijn de mogelijkheden bestand tegen aanvallen en misbruik. Deze set mogelijkheden omvat ook [netwerkbeveiliging](network-protection.md) en [webbeveiliging,](web-protection-overview.md)waarmee de toegang tot schadelijke IP-adressen, domeinen en URL's wordt geregeld. 

<a name="ngp"></a>

**[Beveiliging van de volgende generatie](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
Om de beveiligingsperimeter van uw netwerk verder te versterken, gebruikt Microsoft Defender voor Eindpunt de volgende generatie beveiliging die is ontworpen om alle soorten nieuwe bedreigingen op te vangen.

<a name="edr"></a>

**[Detectie van en reactie op eindpunt](overview-endpoint-detection-response.md)**<br>
De mogelijkheden voor eindpuntdetectie en -antwoorden worden gebruikt om geavanceerde bedreigingen op te sporen, te onderzoeken en te beantwoorden, zodat deze mogelijk voorbij de eerste twee beveiligingspijlers zijn gekomen. [Geavanceerde jacht](advanced-hunting-overview.md) biedt een op query's gebaseerd hulpprogramma voor bedreigingsjacht waarmee u proactief inbreuken kunt vinden en aangepaste detecties kunt maken.

<a name="ai"></a>

**[Geautomatiseerd onderzoek en herstel](automated-investigations.md)**<br>
In combinatie met de mogelijkheid om snel te kunnen reageren op geavanceerde aanvallen, biedt Microsoft Defender voor Eindpunt mogelijkheden voor automatisch onderzoek en herstel om het aantal waarschuwingen in minuten op schaal te verminderen. 

<a name="ss"></a>

**[Microsoft Secure Score voor apparaten](tvm-microsoft-secure-score-devices.md)**<br>

Defender voor Eindpunt bevat Microsoft Secure Score voor apparaten om u te helpen de beveiligingstoestand van uw bedrijfsnetwerk dynamisch te beoordelen, onbeveiligde systemen te identificeren en aanbevolen acties uit te voeren om de algehele beveiliging van uw organisatie te verbeteren.

<a name="mte"></a>

**[Microsoft Threat Experts](microsoft-threat-experts.md)**<br>
De nieuwe beheerde bedreigingsjachtservice van Microsoft Defender for Endpoint biedt proactief zoeken, prioriteit geven en extra context en inzichten die beveiligingscentrums (SOC's) in staat stellen om bedreigingen snel en nauwkeurig te identificeren en erop te reageren.

>[!IMPORTANT]
>Klanten van Defender voor Eindpunten moeten een aanvraag indienen voor de beheerde threat hunting-service van Microsoft Threat Experts om proactieve targeted attack notifications te krijgen en samen te werken met experts op aanvraag. Experts on Demand is een invoegservice. Targeted Attack Notifications worden altijd opgenomen nadat u bent geaccepteerd in de beheerde threat hunting-service van Microsoft Threat Experts.<p>
><p>Als u nog niet bent geregistreerd en de voordelen <b></b> > <b></b> > <b></b> ervan wilt ervaren, gaat u naar Algemene geavanceerde functies van > <b>Instellingen microsoft Threat Experts</b> die u wilt toepassen. Nadat u deze hebt geaccepteerd, krijgt u de voordelen van Meldingen voor gerichte aanvallen en start u een proefversie van 90 dagen met experts op aanvraag. Neem contact op met uw Microsoft-vertegenwoordiger voor een volledig abonnement op aanvraag.

<a name="apis"></a>

**[Gecentraliseerde configuratie en beheer, API's](management-apis.md)**<br>
Integreer Microsoft Defender voor Eindpunt in uw bestaande werkstromen.

<a name="mtp"></a>

**[Integratie met Microsoft-oplossingen](threat-protection-integration.md)** <br>
Defender for Endpoint wordt rechtstreeks geïntegreerd met verschillende Microsoft-oplossingen, waaronder:
- Azure Security Center
- Azure Sentinel
- Intune
- Microsoft Cloud App Security
- Microsoft Defender for Identity
- Microsoft Defender voor Office
- Skype voor Bedrijven

**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**<br>
Met Microsoft 365 Defender vormen Defender voor Eindpunt en diverse microsoft-beveiligingsoplossingen een geïntegreerde suite voor bedrijfsdefensie vóór en na inbreuk die inheems is geïntegreerd in eindpunten, identiteit, e-mail en toepassingen om geavanceerde aanvallen op te sporen, te voorkomen, te onderzoeken en automatisch te beantwoorden.


## <a name="related-topic"></a>Verwant onderwerp
[Microsoft Defender voor Eindpunt helpt bij het opsporen van geavanceerde bedreigingen](https://www.microsoft.com/itshowcase/microsoft-defender-atps-antivirus-capabilities-boost-malware-protection)
