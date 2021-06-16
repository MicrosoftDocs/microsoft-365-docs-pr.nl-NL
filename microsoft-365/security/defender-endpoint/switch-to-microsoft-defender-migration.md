---
title: De overstap maken van niet-Microsoft-eindpuntbeveiliging naar Microsoft Defender voor Eindpunt
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
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 06/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 2953103cb3812103740f98a6db5b8f4d369731e3
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930305"
---
# <a name="make-the-switch-from-non-microsoft-endpoint-protection-to-microsoft-defender-for-endpoint"></a>De overstap maken van niet-Microsoft-eindpuntbeveiliging naar Microsoft Defender voor Eindpunt

Als u wilt overstappen van een niet-Microsoft-oplossing voor eindpuntbeveiliging naar [Microsoft Defender](microsoft-defender-endpoint.md) voor Eindpunt (Defender voor Eindpunt), bent u op de juiste plaats. Gebruik dit artikel als handleiding.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Overzicht van migreren naar Defender voor Eindpunt":::

Wanneer u overschakelt naar Defender voor Eindpunt, begint u met uw niet-Microsoft-oplossing die in de actieve modus werkt. Vervolgens configureert u Defender voor Eindpunt in de passieve modus en kunt u uw apparaten inschakelen bij Defender voor Eindpunt. Vervolgens stelt u Defender voor Eindpunt in op actieve modus. Ten slotte verwijdert u de niet-Microsoft-oplossing.

## <a name="the-migration-process"></a>Het migratieproces

Het migratieproces naar Defender voor Eindpunt kan worden onderverdeeld in drie fasen, zoals wordt beschreven in de volgende tabel:

![Migratiefasen : voorbereiden, instellen, aan boord](images/phase-diagrams/migration-phases.png)

|Fase |Omschrijving |
|--|--|
|[Voorbereiden op uw migratie](switch-to-microsoft-defender-prepare.md) |Tijdens [de **fase Voorbereiden:**](switch-to-microsoft-defender-prepare.md) <p>1. Werk de apparaten van uw organisatie bij. <p>2. Krijg Defender voor eindpunt. <p>3. Plan uw rollen en machtigingen en verleen toegang tot de Microsoft Defender-beveiligingscentrum. <p>4. Configureer de apparaatproxy- en internetinstellingen om communicatie tussen de apparaten van uw organisatie en Defender voor Eindpunt in te stellen. |
|[Defender voor eindpunt instellen](switch-to-microsoft-defender-setup.md) |Tijdens [de **installatiefase**](switch-to-microsoft-defender-setup.md): <p>1. De Microsoft Defender Antivirus. <p>2. Configure Defender for Endpoint. <p>3. Voeg Defender voor Eindpunt toe aan de lijst met uitsluitingen voor uw bestaande oplossing. <p>4. Voeg uw bestaande oplossing toe aan de uitsluitingslijst voor Microsoft Defender Antivirus. <p>5. Stel uw apparaatgroepen, verzamelingen en organisatie-eenheden in. <p>6. Configureer uw antimalwarebeleid en realtime beveiligingsinstellingen.|
|[Onboard to Defender for Endpoint](switch-to-microsoft-defender-onboard.md) |Tijdens [de **onboard-fase**](switch-to-microsoft-defender-onboard.md): <p>1. Onboard your devices to Defender for Endpoint. <p>2. Voer een detectietest uit. <p>3. Controleer of Microsoft Defender Antivirus actief is in de passieve modus. <p>4. Ontvang updates voor Microsoft Defender Antivirus. <p>5. Verwijder uw bestaande oplossing voor eindpuntbeveiliging. <p>6. Zorg ervoor dat Defender voor Eindpunt correct werkt. |

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
