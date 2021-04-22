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
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 587cf49ddc8d6135047fbb5e0207ed0f94d1dbe0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934727"
---
# <a name="migrate-from-symantec-to-microsoft-defender-for-endpoint"></a>Migreren van Symantec naar Microsoft Defender voor Eindpunt
Als u van plan bent om over te schakelen van De beveiliging van Het eindpunt van Symantec (Symantec) naar [Microsoft Defender voor](https://docs.microsoft.com/windows/security/threat-protection) Eindpunt (Microsoft Defender voor Eindpunt), bent u op de juiste plaats. Gebruik dit artikel als handleiding.

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

:::image type="content" source="images/symantec-mde-migration.png" alt-text="Overzicht van migreren van Symantec naar Defender voor Eindpunt":::

Wanneer u overschakelt van Symantec naar Defender voor Eindpunt, begint u met de Oplossing van Symantec in de actieve modus, configureert u Defender voor Eindpunt in passieve modus, gaat u aan boord naar Defender voor Eindpunt en stelt u Defender voor Endpoint in op de actieve modus en verwijdert u Symantec.

## <a name="the-migration-process"></a>Het migratieproces

Wanneer u overschakelt van Symantec naar Microsoft Defender voor Eindpunt, volgt u een proces dat kan worden onderverdeeld in drie fasen, zoals wordt beschreven in de volgende tabel:

![Migratiefasen : voorbereiden, instellen, aan boord](images/phase-diagrams/migration-phases.png)

|Fase |Beschrijving |
|--|--|
|[Voorbereiden op uw migratie](symantec-to-microsoft-defender-atp-prepare.md) |Tijdens de **fase** Voorbereiden krijgt u Microsoft Defender voor Eindpunt, plant u uw rollen en machtigingen en verleent u toegang tot het Microsoft Defender-beveiligingscentrum. U configureert ook de apparaatproxy- en internetinstellingen om communicatie in te stellen tussen de apparaten van uw organisatie en Microsoft Defender voor Eindpunt. |
|[Microsoft Defender voor Eindpunt instellen](symantec-to-microsoft-defender-atp-setup.md) |Tijdens de **installatiefase** configureert u instellingen en uitsluitingen voor Microsoft Defender Antivirus, Microsoft Defender voor Endpoint en Symantec Endpoint Protection. U maakt ook apparaatgroepen, verzamelingen en organisatie-eenheden. Ten slotte configureert u uw antimalwarebeleid en realtime beveiligingsinstellingen.|
|[Onboard to Microsoft Defender for Endpoint](symantec-to-microsoft-defender-atp-onboard.md) |Tijdens de **onboard-fase** kunt u uw apparaten aan boord van Microsoft Defender voor Eindpunten laten werken en controleren of deze apparaten communiceren met Microsoft Defender voor Eindpunt. Als laatste verwijdert u Symantec en zorgt u ervoor dat de beveiliging via Microsoft Defender voor Eindpunt actief is. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Wat is inbegrepen in Microsoft Defender voor Eindpunt?

In deze migratiehandleiding [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) richten we ons [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) op de volgende generatie beveiligings- en eindpuntdetectie- en antwoordmogelijkheden als uitgangspunt voor de overstap naar Microsoft Defender voor Eindpunt. Microsoft Defender voor Eindpunt bevat echter veel meer dan antivirus- en eindpuntbeveiliging. Microsoft Defender voor Eindpunt is een geïntegreerd platform voor preventieve beveiliging, detectie na inbreuken, geautomatiseerd onderzoek en antwoord. In de volgende tabel worden functies en mogelijkheden in Microsoft Defender voor Eindpunt samengevat. 

| Functie/mogelijkheid | Beschrijving |
|---|---|
| [Bedreigings- en risicobeheer](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | Met & mogelijkheden voor beveiligingsprobleembeheer kunt u zwakke punten in uw eindpunten (zoals apparaten) identificeren, beoordelen en herstellen. |
| [Kwetsbaarheid voor aanvallen verminderen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | Regels voor het verminderen van aanvallen helpen de apparaten en toepassingen van uw organisatie te beschermen tegen cyberaanvallen en aanvallen. |
| [Beveiliging van de volgende generatie](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | Beveiliging van de volgende generatie omvat Microsoft Defender Antivirus om bedreigingen en malware te blokkeren. |
| [Detectie van en reactie op eindpunt](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | Eindpuntdetectie- en antwoordmogelijkheden detecteren, onderzoeken en reageren op inbraakpogingen en actieve inbreuken.  |
| [Geavanceerd opsporen](advanced-hunting-overview.md) | Met geavanceerde zoekmogelijkheden kan uw beveiligingsteam indicatoren en entiteiten van bekende of potentiële bedreigingen vinden. |
| [Gedragsblokkering en -insluiting](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | Mogelijkheden voor het blokkeren en inperken van gedrag helpen bij het identificeren en stoppen van bedreigingen, op basis van hun gedrag en procesbomen, zelfs wanneer de bedreiging is gestart met de uitvoering. |
| [Geautomatiseerd onderzoek en herstel](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | Geautomatiseerde onderzoeks- en antwoordmogelijkheden onderzoeken waarschuwingen en nemen onmiddellijk herstelmaatregelen om inbreuken op te lossen. |
| [Threat hunting service](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft Threat Experts) | Bedreigingsjachtservices bieden beveiligingsteams controle en analyse op expertniveau, en om ervoor te zorgen dat kritieke bedreigingen niet worden gemist. |

**Wilt u meer informatie? Zie [Microsoft Defender voor Eindpunt](https://docs.microsoft.com/windows/security/threat-protection).**

## <a name="next-step"></a>Volgende stap

- Ga verder [met Voorbereiden op uw migratie.](symantec-to-microsoft-defender-atp-prepare.md)
