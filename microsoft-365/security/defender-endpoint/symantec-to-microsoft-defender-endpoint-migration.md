---
title: Migreren van Symantec naar Microsoft Defender voor Eindpunt
description: Een overzicht van hoe u overschakelt van Symantec naar Microsoft Defender voor Eindpunt
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
- m365solution-symantecmigrate
- m365solution-overview
ms.topic: article
ms.date: 05/14/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 62a916fcf89432a512ada1b85002cce401e4dd23
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52530896"
---
# <a name="migrate-from-symantec-to-microsoft-defender-for-endpoint"></a>Migreren van Symantec naar Microsoft Defender voor Eindpunt
Als u van plan bent om over te schakelen van Symantec Endpoint Protection (Symantec) naar [Microsoft Defender voor](microsoft-defender-endpoint.md) Eindpunt (Microsoft Defender voor Eindpunt), bent u op de juiste plaats. Gebruik dit artikel als handleiding.

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

:::image type="content" source="images/symantec-mde-migration.png" alt-text="Overzicht van migreren van Symantec naar Defender voor Eindpunt":::

Wanneer u overschakelt van Symantec naar Defender voor Eindpunt, begint u met de Oplossing van Symantec in de actieve modus, configureert u Defender voor Eindpunt in passieve modus, gaat u aan boord naar Defender voor Eindpunt en stelt u Defender voor Endpoint in op de actieve modus en verwijdert u Symantec.

## <a name="the-migration-process"></a>Het migratieproces

Wanneer u overschakelt van Symantec naar Microsoft Defender voor Eindpunt, volgt u een proces dat kan worden onderverdeeld in drie fasen, zoals wordt beschreven in de volgende tabel:

![Migratiefasen : voorbereiden, instellen, aan boord](images/phase-diagrams/migration-phases.png)

|Fase |Omschrijving |
|--|--|
|[Voorbereiden op uw migratie](symantec-to-microsoft-defender-atp-prepare.md) |Tijdens de **fase** Voorbereiden werkt u de apparaten van uw organisatie bij, krijgt u Microsoft Defender voor Eindpunt, plant u uw rollen en machtigingen en verleent u toegang tot de Microsoft Defender-beveiligingscentrum. U configureert ook de apparaatproxy- en internetinstellingen om communicatie tussen de apparaten van uw organisatie en Defender voor Eindpunt in te stellen. |
|[Microsoft Defender voor Eindpunt instellen](symantec-to-microsoft-defender-atp-setup.md) |Tijdens de **installatiefase** stelt u de Microsoft Defender Antivirus in en stelt u deze in op de passieve modus. U configureert ook instellingen & uitsluitingen voor Microsoft Defender Antivirus en Endpoint Protection. Vervolgens maakt u uw apparaatgroepen, verzamelingen en organisatie-eenheden. Ten slotte configureert u uw antimalwarebeleid en realtime beveiligingsinstellingen.|
|[Onboard to Microsoft Defender for Endpoint](symantec-to-microsoft-defender-atp-onboard.md) |Tijdens de **onboard-fase** kunt u uw apparaten inschakelen bij Microsoft Defender voor Eindpunt, bevestigen dat Microsfot Defender Antivirus wordt uitgevoerd in de passieve modus en controleren of uw eindpunten communiceren met Defender voor Eindpunt. Vervolgens verwijdert u Symantec en zorgt u ervoor dat Defender voor Eindpunt correct werkt. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Wat is inbegrepen in Microsoft Defender voor Eindpunt?

In deze migratiehandleiding [](microsoft-defender-antivirus-in-windows-10.md) richten we ons [](overview-endpoint-detection-response.md) op de volgende generatie beveiliging en eindpuntdetectie en -respons mogelijkheden als uitgangspunt voor de overstap naar Microsoft Defender voor Eindpunt. Microsoft Defender voor Eindpunt bevat echter veel meer dan antivirus- en eindpuntbeveiliging. Microsoft Defender voor Eindpunt is een geïntegreerd platform voor preventieve beveiliging, detectie na inbreuken, geautomatiseerd onderzoek en antwoord. In de volgende tabel worden functies en mogelijkheden in Microsoft Defender voor Eindpunt samengevat. 

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

**Wilt u meer informatie? Zie [Microsoft Defender voor Eindpunt](microsoft-defender-endpoint.md).**

## <a name="next-step"></a>Volgende stap

- Ga verder [met Voorbereiden op uw migratie.](symantec-to-microsoft-defender-atp-prepare.md)
