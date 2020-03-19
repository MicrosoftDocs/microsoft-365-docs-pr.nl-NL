---
title: Windows 10 Enterprise-beveiligingsfuncties implementeren
description: Biedt een richtlijnen op hoog niveau voor de stappen die u nodig hebt om Windows 10 Enterprise-beveiligingsfuncties op pc's te implementeren als onderdeel van Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-documentatie, Windows 10 Enterprise, beveiliging
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: 5407370933c2a99781adf4ca58d3fa905328ed04
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806289"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>Stap 5: Windows 10 Enterprise-beveiligingsfuncties implementeren

![Fase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 biedt beveiligingsfuncties om zakelijke gebruikers te beschermen, cyberbedreigingen te stoppen en gegevensverlies te voorkomen. 

Zie voor meer informatie over deze technologieën:

* [Identiteitsbeveiliging](https://docs.microsoft.com/windows/security/identity-protection/) : meer informatie over Windows Hello voor Bedrijven, Credential Guard en toegangscontrole.
* [Bescherming tegen bedreigingen](https://docs.microsoft.com/windows/threat-protection/) - Meer informatie over Microsoft Defender Advanced Threat Protection, een uniform platform voor preventieve bescherming, detectie na inbreuk, geautomatiseerd onderzoek en respons.
* [Informatiebeveiliging](https://docs.microsoft.com/windows/security/information-protection/) - Meer informatie over BitLocker, Windows Information Protection en andere manieren waarop Windows 10 bedrijfsgegevens helpt beschermen. 

In deze stap ziet u hoe u deze beveiligingsfuncties implementeren, beheren, configureren en oplossen:

* [Windows Defender Antivirus](#windows-defender-antivirus)
* [Windows Defender Exploit Guard](#windows-defender-exploit-guard)
* [Microsoft Defender Advanced Threat Protection](#windows10-sec-atp)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Windows Defender Antivirus
Windows Defender Antivirus (AV) is een antimalware-oplossing die is ingebouwd in Windows 10. Het biedt beveiliging en antimalwarebeheer voor desktops, draagbare computers en servers. Zie [Windows Defender Antivirus in Windows 10 en Windows Server 2016](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)voor meer informatie over Windows Defender AV, de minimumvereisten en hoe u deze functie beheren.

Als u Windows Defender AV niet als primaire antivirusclient gebruikt, of als u ook Microsoft Defender ATP gebruikt, zijn er enkele overwegingen waar u rekening mee moet houden. Zie [Windows Defender AV-compatibiliteit](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility)voor meer informatie.

### <a name="deployment-and-management"></a>Implementatie en beheer
Als u Windows Defender AV wilt implementeren en beheren, volgt u hier de richtlijnen:

* [Windows Defender AV implementeren, beheren en rapporteren](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Referentieonderwerpen voor beheer- en configuratietools](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>Configuratie
Gebruikers kunnen een aantal functies configureren. Zie de volgende bronnen voor meer informatie:

* [Windows Defender AV-functies configureren](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [Referentieonderwerpen voor beheer- en configuratietools](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

Raadpleeg deze lijst met alle instellingen (gedefinieerd door de configuratie van groepsbeleid): [Groepsbeleidsinstellingen gebruiken om Windows Defender AV te configureren en te beheren](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

U de [Evaluatiehandleiding voor Windows Defender AV-beveiliging](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus) gebruiken om het beschermingsniveau en de impact van Windows Defender AV op uw netwerk te evalueren. Dit kan ook handig zijn bij het maken van een eerste configuratie of als een 'quick start guide' en wordt regelmatig bijgewerkt om de meest nuttige aanbevelingen voor het configureren en inschakelen van functies om maximale bescherming te garanderen.

### <a name="reporting"></a>Rapportage
U rapportage verkrijgen met behulp van een configuratietool, zoals Microsoft Endpoint Configuration Manager of Microsoft Intune. U ook rapportage verkrijgen van Update Compliance (OMS) of door Windows-gebeurtenislogboeken in uw SIEM te gebruiken. Als u een licentie hebt voor Microsoft Defender ATP, u ook rapportage verkrijgen in Windows Defender AV-detecties en basisherstel uitvoeren. Zie de volgende bronnen voor meer informatie:
* [Windows Defender AV implementeren, beheren en rapporteren](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Rapport over Windows Defender AV-beveiliging](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Overzicht van Microsoft Defender ATP-portal](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Problemen oplossen
Zie [Gebeurtenislogboeken en foutcodes controleren om problemen met Windows Defender AV op te lossen](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus)voor informatie over het basisoplossend probleem oplossing voor fout- en gebeurteniscodes.

U ook problemen (zoals false positives) indienen met behulp van het Windows Defender Security Intelligence-indieningssysteem. Zie [Problemen bij Microsoft verzenden](https://www.microsoft.com/wdsi/filesubmission)voor meer informatie.

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard
Windows Defender Exploit Guard is een nieuwe set van host inbraak preventie mogelijkheden voor Windows 10. Zie [Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)voor meer informatie over Windows Defender Exploit Guard, de minimumvereisten en hoe u deze functie beheren.

### <a name="deployment-management-and-configuration"></a>Implementatie, beheer en configuratie
Als u Windows Defender Exploit Guard wilt implementeren, beheren en configureren, volgt u hier de richtlijnen:
* [Bescherming tegen gebruik](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [Bescherming tegen het oppervlak van de aanval](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [Netwerkbeveiliging](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [Beheerde maptoegang](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

U een reeks evaluatieonderwerpen gebruiken om het beschermingsniveau en de impact van Windows Defender Exploit Guard op uw netwerk te evalueren. Dit kan ook handig zijn bij het maken van een eerste configuratie of als een 'quick start guide' en de onderwerpen en richtlijnen worden regelmatig bijgewerkt om de meest nuttige aanbevelingen voor het configureren en inschakelen van functies om maximale bescherming te garanderen. Voor meer informatie, [Evalueren Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard).

### <a name="reporting"></a>Rapportage
U rapportage verkrijgen met behulp van een configuratietool, zoals Configuratiebeheer of Intune. U ook rapportage verkrijgen door Windows-gebeurtenislogboeken in uw SIEM te gebruiken. Als u een licentie hebt voor Microsoft Defender ATP, u ook rapportage verkrijgen in Windows Defender AV-detecties en basisherstel uitvoeren. Zie de volgende bronnen voor meer informatie:
* [Bekijk windows Defender Exploit Guard-gebeurtenissen](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Overzicht van Microsoft Defender ATP-portal](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Problemen oplossen
U eenvoudige probleemoplossing uitvoeren of Microsoft optioneel voorzien van .cab-bestanden en problemen indienen (zoals false positives) met behulp van het Windows Defender Security Intelligence-indieningssysteem. Zie [Problemen bij Microsoft verzenden](https://www.microsoft.com/wdsi/filesubmission)voor meer informatie.


<a name="windows10-sec-atp"></a>
## <a name="microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection
Microsoft Defender ATP, alleen beschikbaar met het Microsoft 365 E5-abonnement, is een beveiligingsservice waarmee zakelijke klanten geavanceerde bedreigingen op hun netwerken kunnen detecteren, onderzoeken en erop kunnen reageren. Zie voor meer informatie over Microsoft Defender ATP, de minimumvereisten en hoe u deze functie beheren:

* [Microsoft Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [Minimumeisen](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>Implementatie, beheer en configuratie
Als u Microsoft Defender ATP wilt implementeren, moet u ervoor zorgen dat u over de juiste Windows-licentie beschikt. Nadat u hebt geverifieerd dat u de juiste licentie hebt, moet u de geolocatie bepalen voor waar uw gegevens worden opgeslagen. Daarna u beginnen met het onboarding van eindpunten van de service.

Zie de volgende onderwerpen voor meer informatie over deze stappen: 

* [Licentieverlening valideren en volledig instellen](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [Gegevensopslag en privacy](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [Endpoints aan boord en toegang tot de installatie](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>Detecteren, onderzoeken, reageren
Nadat u eindpunten met succes aan de service hebt onboarding, u beginnen met het onderzoeken van waarschuwingen van de verschillende dashboards. Zodra u waarschuwingen hebt onderzocht, u reactieacties uitvoeren op waarschuwingen. 

Zie voor meer informatie over hoe u deze doen:
* [Overzicht van Microsoft Defender ATP-portal](https://go.microsoft.com/fwlink/?linkid=861596)
* [De Microsoft Defender ATP-portal gebruiken](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [Reactieacties uitvoeren](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>Integreren met andere producten en gereedschappen
Microsoft Defender ATP integreert en ondersteunt diverse andere producten en tools om zijn beveiligingsmogelijkheden uit te breiden. 

Zie voor meer informatie over de tools en andere producten:
* [SIEM-hulpprogramma's](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [Aangepaste waarschuwingen maken](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [API's gebruiken](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [Power BI-rapporten bouwen](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>Problemen oplossen
Mogelijk u problemen ondervinden tijdens het onboarding of tijdens het gebruik van het product. Zie voor meer informatie over het oplossen van problemen:
* [Problemen met onboarding oplossen](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [Problemen met Microsoft Defender ATP oplossen](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>Volgende stap

[Criteria voor het afsluiten van Windows 10 Enterprise-infrastructuur](windows10-exit-criteria.md)
