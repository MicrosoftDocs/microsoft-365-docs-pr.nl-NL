---
title: Migreren van McAfee naar Microsoft Defender voor Eindpunt
description: Maak de overstap van McAfee naar Microsoft Defender voor Eindpunt. Lees dit artikel voor een overzicht.
keywords: migratie, Microsoft Defender voor Eindpunt, edr
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
ms.topic: article
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 5bbcf885ec160204916507aee60398aee35e470b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538049"
---
# <a name="migrate-from-mcafee-to-microsoft-defender-for-endpoint"></a>Migreren van McAfee naar Microsoft Defender voor Eindpunt

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Als u van Plan bent om over te schakelen van McAfee Endpoint Security (McAfee) naar [Microsoft Defender voor](microsoft-defender-endpoint.md) Eindpunt (Microsoft Defender voor Eindpunt), bent u op de juiste plaats. Gebruik dit artikel als handleiding.


:::image type="content" source="images/mcafee-mde-migration.png" alt-text="Overzicht van migreren van McAfee naar Defender voor Eindpunt":::

Wanneer u de overstap maakt van McAfee naar Defender voor Eindpunt, begint u met uw McAfee-oplossing in de actieve modus, configureert u Defender voor Eindpunt in passieve modus, gaat u aan boord naar Defender voor Eindpunt en stelt u Defender voor Endpoint in op de actieve modus en verwijdert u McAfee.

## <a name="the-migration-process"></a>Het migratieproces

Wanneer u overschakelt van McAfee naar Microsoft Defender voor Eindpunt, volgt u een proces dat kan worden onderverdeeld in drie fasen: Voorbereiden, Instellen en Onboard. 

![Migratiefasen : setup aan boord voorbereiden](images/phase-diagrams/migration-phases.png)

|Fase |Beschrijving |
|--|--|
|[Voorbereiden op uw migratie](mcafee-to-microsoft-defender-prepare.md) |Tijdens de [**fase**](mcafee-to-microsoft-defender-prepare.md) Voorbereiden werkt u de apparaten van uw organisatie bij, krijgt u Microsoft Defender voor Eindpunt, plant u uw rollen en machtigingen en verleent u toegang tot de Microsoft Defender-beveiligingscentrum. U configureert ook de apparaatproxy- en internetinstellingen om communicatie in te stellen tussen de apparaten van uw organisatie en Microsoft Defender voor Eindpunt. |
|[Microsoft Defender voor Eindpunt instellen](mcafee-to-microsoft-defender-setup.md) |Tijdens de [**installatiefase**](mcafee-to-microsoft-defender-setup.md) stelt u de Microsoft Defender Antivirus in en stelt u deze in op de passieve modus. U configureert ook instellingen & uitsluitingen voor Microsoft Defender Antivirus en uw bestaande oplossing voor eindpuntbeveiliging. Vervolgens maakt u uw apparaatgroepen, verzamelingen en organisatie-eenheden. Ten slotte configureert u uw antimalwarebeleid en realtime beveiligingsinstellingen.|
|[Onboard to Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-onboard.md) |Tijdens de [**onboard-fase**](mcafee-to-microsoft-defender-onboard.md) kunt u uw apparaten inschakelen bij Microsoft Defender voor Eindpunt, bevestigen dat Microsoft Defender Antivirus in de passieve modus wordt uitgevoerd en controleren of uw eindpunten communiceren met Defender voor Eindpunt. Vervolgens verwijdert u McAfee en controleert u of Defender voor Eindpunt correct werkt. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Wat is inbegrepen in Microsoft Defender voor Eindpunt?

In deze migratiehandleiding [](microsoft-defender-antivirus-in-windows-10.md) richten we ons [](overview-endpoint-detection-response.md) op de volgende generatie beveiliging en eindpuntdetectie en -respons mogelijkheden als uitgangspunt voor de overstap naar Microsoft Defender voor Eindpunt. Microsoft Defender voor Eindpunt bevat echter veel meer dan antivirus- en eindpuntbeveiliging. Microsoft Defender voor Eindpunt is een geïntegreerd platform voor preventieve beveiliging, detectie na inbreuken, geautomatiseerd onderzoek en antwoord. In de volgende tabel worden functies en mogelijkheden in Microsoft Defender voor Eindpunt samengevat. 

| Functie/mogelijkheid | Beschrijving |
|---|---|
| [Bedreigings- en risicobeheer](next-gen-threat-and-vuln-mgt.md) | Bedreigingsfuncties & vulnerability management helpen bij het identificeren, beoordelen en herstellen van zwakke punten in uw eindpunten (zoals apparaten). |
| [Kwetsbaarheid voor aanvallen verminderen](overview-attack-surface-reduction.md) | Regels voor het verminderen van aanvallen helpen de apparaten en toepassingen van uw organisatie te beschermen tegen cyberaanvallen en aanvallen. |
| [Beveiliging van de volgende generatie](microsoft-defender-antivirus-in-windows-10.md) | Beveiliging van de volgende generatie bevat Microsoft Defender Antivirus om bedreigingen en malware te blokkeren. |
| [Detectie van en reactie op eindpunt](overview-endpoint-detection-response.md) | Eindpuntdetectie- en antwoordmogelijkheden detecteren, onderzoeken en reageren op inbraakpogingen en actieve inbreuken.  |
| [Geavanceerd opsporen](advanced-hunting-overview.md) | Met geavanceerde zoekmogelijkheden kan uw beveiligingsteam indicatoren en entiteiten van bekende of potentiële bedreigingen vinden. |
| [Gedragsblokkering en -insluiting](behavioral-blocking-containment.md) | Mogelijkheden voor het blokkeren en inperken van gedrag helpen bij het identificeren en stoppen van bedreigingen, op basis van hun gedrag en procesbomen, zelfs wanneer de bedreiging is gestart met de uitvoering. |
| [Geautomatiseerd onderzoek en herstel](automated-investigations.md) | Geautomatiseerde onderzoeks- en antwoordmogelijkheden onderzoeken waarschuwingen en nemen onmiddellijk herstelmaatregelen om inbreuken op te lossen. |
| [Threat hunting service](microsoft-threat-experts.md) (Microsoft Threat Experts) | Bedreigingsjachtservices bieden beveiligingsteams controle en analyse op expertniveau, en om ervoor te zorgen dat kritieke bedreigingen niet worden gemist. |

**Wilt u meer informatie? Zie [Microsoft Defender voor Eindpunt](microsoft-defender-endpoint.md).**

## <a name="next-step"></a>Volgende stap

- Ga verder [met Voorbereiden op uw migratie.](mcafee-to-microsoft-defender-prepare.md)
