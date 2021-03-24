---
title: Migreren van McAfee naar Microsoft Defender voor Eindpunt
description: Maak de overstap van McAfee naar Microsoft Defender voor Eindpunt. Lees dit artikel voor een overzicht.
keywords: migratie, windows defender advanced threat protection, atp, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-mcafeemigrate
- m365solution-overview
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 7cbe74843e0a71cc1e20cb0b57d9bb838704e19a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059674"
---
# <a name="migrate-from-mcafee-to-microsoft-defender-for-endpoint"></a>Migreren van McAfee naar Microsoft Defender voor Eindpunt

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Als u van Plan bent om over te schakelen van McAfee Endpoint Security (McAfee) naar [Microsoft Defender voor](https://docs.microsoft.com/windows/security/threat-protection) Eindpunt (Microsoft Defender voor Eindpunt), bent u op de juiste plaats. Gebruik dit artikel als handleiding.


:::image type="content" source="images/mcafee-mde-migration.png" alt-text="Overzicht van migreren van McAfee naar Defender voor Eindpunt":::

Wanneer u de overstap maakt van McAfee naar Defender voor Eindpunt, begint u met uw McAfee-oplossing in de actieve modus, configureert u Defender voor Eindpunt in passieve modus, gaat u aan boord naar Defender voor Eindpunt en stelt u Defender voor Endpoint in op de actieve modus en verwijdert u McAfee.

## <a name="the-migration-process"></a>Het migratieproces

Wanneer u overschakelt van McAfee naar Microsoft Defender voor Eindpunt, volgt u een proces dat kan worden onderverdeeld in drie fasen: Voorbereiden, Instellen en Onboard. 

![Migratiefasen : setup aan boord voorbereiden](images/phase-diagrams/migration-phases.png)

|Fase |Beschrijving |
|--|--|
|[Voorbereiden op uw migratie](mcafee-to-microsoft-defender-prepare.md) |Tijdens de [**fase**](mcafee-to-microsoft-defender-prepare.md) Voorbereiden werkt u de apparaten van uw organisatie bij, krijgt u Microsoft Defender voor Eindpunt, plant u uw rollen en machtigingen en verleent u toegang tot het Microsoft Defender-beveiligingscentrum. U configureert ook de apparaatproxy- en internetinstellingen om communicatie in te stellen tussen de apparaten van uw organisatie en Microsoft Defender voor Eindpunt. |
|[Microsoft Defender voor Eindpunt instellen](mcafee-to-microsoft-defender-setup.md) |Tijdens [](mcafee-to-microsoft-defender-setup.md) de installatiefase schakelt u Microsoft Defender Antivirus in en controleert u of deze in de passieve modus staat en configureert u instellingen & uitsluitingen voor Microsoft Defender Antivirus, Microsoft Defender voor Eindpunt en McAfee. U maakt ook apparaatgroepen, verzamelingen en organisatie-eenheden. Ten slotte configureert u uw antimalwarebeleid en realtime beveiligingsinstellingen.|
|[Onboard to Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-onboard.md) |Tijdens de [**onboard-fase**](mcafee-to-microsoft-defender-onboard.md) kunt u uw apparaten aan boord van Microsoft Defender voor Eindpunten laten werken en controleren of deze apparaten communiceren met Microsoft Defender voor Eindpunt. Als laatste verwijdert u McAfee en zorgt u ervoor dat de beveiliging via Microsoft Defender Antivirus & Microsoft Defender voor Eindpunt actief is. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Wat is inbegrepen in Microsoft Defender voor Eindpunt?

In deze migratiehandleiding [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) richten we ons [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) op de volgende generatie beveiligings- en eindpuntdetectie- en antwoordmogelijkheden als uitgangspunt voor de overstap naar Microsoft Defender voor Eindpunt. Microsoft Defender voor Eindpunt bevat echter veel meer dan antivirus- en eindpuntbeveiliging. Microsoft Defender voor Eindpunt is een geïntegreerd platform voor preventieve beveiliging, detectie na inbreuken, geautomatiseerd onderzoek en antwoord. In de volgende tabel worden functies en mogelijkheden in Microsoft Defender voor Eindpunt samengevat. 

| Functie/mogelijkheid | Beschrijving |
|---|---|
| [Bedreigings- & kwetsbaarheidsbeheer](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | Met & mogelijkheden voor beveiligingsprobleembeheer kunt u zwakke punten in uw eindpunten (zoals apparaten) identificeren, beoordelen en herstellen. |
| [Surface-beperking voor aanvallen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | Regels voor het verminderen van aanvallen helpen de apparaten en toepassingen van uw organisatie te beschermen tegen cyberaanvallen en aanvallen. |
| [Beveiliging van de volgende generatie](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | Beveiliging van de volgende generatie omvat Microsoft Defender Antivirus om bedreigingen en malware te blokkeren. |
| [Eindpuntdetectie en -antwoord](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | Eindpuntdetectie- en antwoordmogelijkheden detecteren, onderzoeken en reageren op inbraakpogingen en actieve inbreuken.  |
| [Geavanceerd opsporen](advanced-hunting-overview.md) | Met geavanceerde zoekmogelijkheden kan uw beveiligingsteam indicatoren en entiteiten van bekende of potentiële bedreigingen vinden. |
| [Gedrag blokkeren en insluiting](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | Mogelijkheden voor het blokkeren en inperken van gedrag helpen bij het identificeren en stoppen van bedreigingen, op basis van hun gedrag en procesbomen, zelfs wanneer de bedreiging is gestart met de uitvoering. |
| [Geautomatiseerd onderzoek en herstel](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | Geautomatiseerde onderzoeks- en antwoordmogelijkheden onderzoeken waarschuwingen en nemen onmiddellijk herstelmaatregelen om inbreuken op te lossen. |
| [Threat hunting service](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft Threat Experts) | Bedreigingsjachtservices bieden beveiligingsteams controle en analyse op expertniveau, en om ervoor te zorgen dat kritieke bedreigingen niet worden gemist. |

**Wilt u meer informatie? Zie [Microsoft Defender voor Eindpunt](https://docs.microsoft.com/windows/security/threat-protection).**

## <a name="next-step"></a>Volgende stap

- Ga verder [met Voorbereiden op uw migratie.](mcafee-to-microsoft-defender-prepare.md)
