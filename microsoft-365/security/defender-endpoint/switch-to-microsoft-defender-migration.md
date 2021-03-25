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
ms.date: 02/11/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 2c6029a1aada8f5f5fb27723c868f28c3de6f8aa
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218650"
---
# <a name="make-the-switch-from-a-non-microsoft-endpoint-solution-to-microsoft-defender-for-endpoint"></a>De overstap maken van een niet-Microsoft-eindpuntoplossing naar Microsoft Defender voor Eindpunt

Als u van plan bent om over te schakelen van een niet-Microsoft-eindpuntbeveiligingsoplossing naar [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) voor Eindpunt (Defender voor Eindpunt), bent u op de juiste plaats. Gebruik dit artikel als handleiding.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Overzicht van migreren naar Defender voor Eindpunt":::

Wanneer u overschakelt naar Defender voor Eindpunt, begint u met uw niet-Microsoft-oplossing in de actieve modus, configureert u Defender voor Eindpunt in passieve modus, gaat u aan boord van Defender voor Eindpunt en stelt u Defender voor Endpoint in op de actieve modus en verwijdert u de niet-Microsoft-oplossing.

> [!TIP]
> - Zie Migreren van McAfee naar Microsoft Defender voor Eindpunt als u momenteel McAfee Endpoint Security [(McAfee) gebruikt.](mcafee-to-microsoft-defender-migration.md)
> - Zie Migreren van Symantec naar Microsoft Defender [voor Eindpunt](symantec-to-microsoft-defender-endpoint-migration.md)als u momenteel Gebruik maakt van De beveiliging van Het eindpunt van Symantec .

## <a name="the-migration-process"></a>Het migratieproces

Wanneer u overschakelt naar Microsoft Defender voor Eindpunt, volgt u een proces dat kan worden onderverdeeld in drie fasen, zoals wordt beschreven in de volgende tabel:

![Migratiefasen : voorbereiden, instellen, aan boord](images/phase-diagrams/migration-phases.png)

|Fase |Omschrijving |
|--|--|
|[Voorbereiden op uw migratie](switch-to-microsoft-defender-prepare.md) |Tijdens [de **fase** Voorbereiden](switch-to-microsoft-defender-prepare.md)werkt u de apparaten van uw organisatie bij, krijgt u Microsoft Defender voor Eindpunt, plant u uw rollen en machtigingen en verleent u toegang tot het Microsoft Defender-beveiligingscentrum. U configureert ook de apparaatproxy- en internetinstellingen om communicatie in te stellen tussen de apparaten van uw organisatie en Microsoft Defender voor Eindpunt. |
|[Microsoft Defender voor Eindpunt instellen](switch-to-microsoft-defender-setup.md) |Tijdens de installatiefase [stelt  ](switch-to-microsoft-defender-setup.md)u Microsoft Defender Antivirus in en zorgt u ervoor dat deze in de passieve modus staat en configureert u instellingen & uitsluitingen voor Microsoft Defender Antivirus, Microsoft Defender voor Eindpunt en uw bestaande oplossing voor eindpuntbeveiliging. U maakt ook apparaatgroepen, verzamelingen en organisatie-eenheden. Ten slotte configureert u uw antimalwarebeleid en realtime beveiligingsinstellingen.|
|[Onboard to Microsoft Defender for Endpoint](switch-to-microsoft-defender-onboard.md) |Tijdens [de **onboard-fase**](switch-to-microsoft-defender-onboard.md)kunt u uw apparaten aan boord van Microsoft Defender voor Eindpunt laten gaan en controleren of deze apparaten communiceren met Microsoft Defender voor Eindpunt. Als laatste verwijdert u uw bestaande oplossing voor eindpuntbeveiliging en zorgt u ervoor dat de beveiliging via Microsoft Defender Antivirus & Microsoft Defender voor Eindpunt actief is. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Wat is inbegrepen in Microsoft Defender voor Eindpunt?

In deze migratiehandleiding [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) richten we ons [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) op de volgende generatie beveiligings- en eindpuntdetectie- en antwoordmogelijkheden als uitgangspunt voor de overstap naar Microsoft Defender voor Eindpunt. Microsoft Defender voor Eindpunt bevat echter veel meer dan antivirus- en eindpuntbeveiliging. Microsoft Defender voor Eindpunt is een geïntegreerd platform voor preventieve beveiliging, detectie na inbreuken, geautomatiseerd onderzoek en antwoord. In de volgende tabel worden functies en mogelijkheden in Microsoft Defender voor Eindpunt samengevat. 

| Functie/mogelijkheid | Omschrijving |
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

- Ga verder [met Voorbereiden op uw migratie.](switch-to-microsoft-defender-prepare.md)
