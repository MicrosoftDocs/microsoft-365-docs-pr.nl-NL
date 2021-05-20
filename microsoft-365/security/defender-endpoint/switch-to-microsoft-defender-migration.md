---
title: De overstap maken van een niet-Microsoft-eindpuntoplossing naar Microsoft Defender voor Eindpunt
description: Maak de overstap naar Microsoft Defender voor Eindpunt. Lees dit artikel voor een overzicht.
keywords: migratie, windows defender advanced endpoint protection, for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365solution-migratetomdatp
- m365solution-overview
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 013205a1b5b9db204f626a6fe6ab76ad07378558
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538001"
---
# <a name="make-the-switch-from-a-non-microsoft-endpoint-solution-to-microsoft-defender-for-endpoint"></a>De overstap maken van een niet-Microsoft-eindpuntoplossing naar Microsoft Defender voor Eindpunt

Als u van plan bent om over te schakelen van een niet-Microsoft-eindpuntbeveiligingsoplossing naar [Microsoft Defender](microsoft-defender-endpoint.md) voor Eindpunt (Defender voor Eindpunt), bent u op de juiste plaats. Gebruik dit artikel als handleiding.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Overzicht van migreren naar Defender voor Eindpunt":::

Wanneer u overschakelt naar Defender voor Eindpunt, begint u met uw niet-Microsoft-oplossing in de actieve modus, configureert u Defender voor Eindpunt in passieve modus, gaat u aan boord van Defender voor Eindpunt en stelt u Defender voor Endpoint in op de actieve modus en verwijdert u de niet-Microsoft-oplossing.

> [!TIP]
> - Zie Migreren van McAfee naar Defender voor Eindpunt als u momenteel McAfee Endpoint Security [(McAfee) gebruikt.](mcafee-to-microsoft-defender-migration.md)
> - Zie Migreren van Symantec naar Defender voor Eindpunt als u momenteel Gebruik Endpoint Protection [(Symantec).](symantec-to-microsoft-defender-endpoint-migration.md)

## <a name="the-migration-process"></a>Het migratieproces

Wanneer u overschakelt naar Defender voor eindpunt, volgt u een proces dat kan worden onderverdeeld in drie fasen, zoals wordt beschreven in de volgende tabel:

![Migratiefasen : voorbereiden, instellen, aan boord](images/phase-diagrams/migration-phases.png)

|Fase |Omschrijving |
|--|--|
|[Voorbereiden op uw migratie](switch-to-microsoft-defender-prepare.md) |Tijdens [de **fase** Voorbereiden,](switch-to-microsoft-defender-prepare.md)werk u de apparaten van uw organisatie bij, krijgt u Defender voor Eindpunt, plant u uw rollen en machtigingen en verleent u toegang tot de Microsoft Defender-beveiligingscentrum. U configureert ook de apparaatproxy- en internetinstellingen om communicatie tussen de apparaten van uw organisatie en Defender voor Eindpunt in te stellen. |
|[Defender voor eindpunt instellen](switch-to-microsoft-defender-setup.md) |Tijdens [de **installatiefase**](switch-to-microsoft-defender-setup.md)stelt u de Microsoft Defender Antivirus in en stelt u deze in op passieve modus. U configureert ook instellingen & uitsluitingen voor Microsoft Defender Antivirus en uw bestaande oplossing voor eindpuntbeveiliging. Vervolgens maakt u uw apparaatgroepen, verzamelingen en organisatie-eenheden. Ten slotte configureert u uw antimalwarebeleid en realtime beveiligingsinstellingen.|
|[Onboard to Defender for Endpoint](switch-to-microsoft-defender-onboard.md) |Tijdens [de **onboard-fase**](switch-to-microsoft-defender-onboard.md)bevestigt u dat Microsoft Defender Antivirus in de passieve modus wordt uitgevoerd en controleert u of uw eindpunten communiceren met Defender voor Eindpunt. Vervolgens verwijdert u uw bestaande oplossing voor eindpuntbeveiliging en zorgt u ervoor dat Defender voor Eindpunt correct werkt. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Wat is inbegrepen in Microsoft Defender voor Eindpunt?

In deze migratiehandleiding [](microsoft-defender-antivirus-in-windows-10.md) richten we ons [](overview-endpoint-detection-response.md) op de volgende generatie beveiliging en eindpuntdetectie en -respons mogelijkheden als uitgangspunt voor de overstap naar Defender voor Eindpunt. Defender for Endpoint bevat echter veel meer dan antivirus- en eindpuntbeveiliging. Defender for Endpoint is een geïntegreerd platform voor preventieve beveiliging, detectie na inbreuken, geautomatiseerd onderzoek en antwoord. In de volgende tabel worden functies en mogelijkheden in Defender voor Eindpunt samengevat. 

| Functie/mogelijkheid | Omschrijving |
|---|---|
| [Bedreigings- en risicobeheer](next-gen-threat-and-vuln-mgt.md) | Bedreigingsfuncties & vulnerability management helpen bij het identificeren, beoordelen en herstellen van zwakke punten in uw eindpunten (zoals apparaten). |
| [Kwetsbaarheid voor aanvallen verminderen](overview-attack-surface-reduction.md) | Regels voor het verminderen van aanvallen helpen de apparaten en toepassingen van uw organisatie te beschermen tegen cyberaanvallen en aanvallen. |
| [Beveiliging van de volgende generatie](microsoft-defender-antivirus-in-windows-10.md) | Beveiliging van de volgende generatie bevat Microsoft Defender Antivirus om bedreigingen en malware te blokkeren. |
| [Detectie van en reactie op eindpunt](overview-endpoint-detection-response.md) | Eindpuntdetectie- en antwoordmogelijkheden detecteren, onderzoeken en reageren op inbraakpogingen en actieve inbreuken.  |
| [Geavanceerd opsporen](advanced-hunting-overview.md) | Met geavanceerde zoekmogelijkheden kan uw beveiligingsteam indicatoren en entiteiten van bekende of potentiële bedreigingen vinden. |
| [Gedragsblokkering en -insluiting](behavioral-blocking-containment.md) | Mogelijkheden voor het blokkeren en inperken van gedrag helpen bij het identificeren en stoppen van bedreigingen, op basis van hun gedrag en procesbomen, zelfs wanneer de bedreiging is gestart met de uitvoering. |
| [Geautomatiseerd onderzoek en herstel](automated-investigations.md) | Geautomatiseerde onderzoeks- en antwoordmogelijkheden onderzoeken waarschuwingen en nemen onmiddellijk herstelmaatregelen om inbreuken op te lossen. |
| [Threat hunting service](microsoft-threat-experts.md) (Microsoft Threat Experts) | Bedreigingsjachtservices bieden beveiligingsteams controle en analyse op expertniveau, en om ervoor te zorgen dat kritieke bedreigingen niet worden gemist. |

**Wilt u meer informatie? Zie [Defender voor eindpunt](microsoft-defender-endpoint.md).**

## <a name="next-step"></a>Volgende stap

- Ga verder [met Voorbereiden op uw migratie.](switch-to-microsoft-defender-prepare.md)
