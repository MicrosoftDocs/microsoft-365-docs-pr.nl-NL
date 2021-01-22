---
title: 'Overzicht : geavanceerd zoeken'
description: Meer informatie over geavanceerde zoekquery's in Microsoft 365 en hoe u deze kunt gebruiken om proactief bedreigingen en zwakke punten in uw netwerk te vinden
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, custom detections, schema, kusto, microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 8fbf9c3d93434ec2dbc3f069bc0fbd3fe03fc260
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932272"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>Proactief zoeken naar bedreigingen met geavanceerd zoeken in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

> Wilt u ervaring met Microsoft 365 Defender? U kunt [dit evalueren in een testomgeving](https://aka.ms/mtp-trial-lab) of uw [pilotproject in productie nemen.](https://aka.ms/m365d-pilotplaybook)
>

Geavanceerd zoeken is een op query's gebaseerd hulpprogramma voor bedreigingen zoeken waarmee u tot 30 dagen onbewerkte gegevens kunt verkennen. U kunt gebeurtenissen in uw netwerk proactief controleren om bedreigingsindicatoren en entiteiten te vinden. De flexibele toegang tot gegevens maakt het mogelijk om ongeconsenseerd te zoeken naar zowel bekende als potentiële bedreigingen.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

U kunt dezelfde zoekquery's gebruiken om aangepaste detectieregels te maken. Deze regels worden automatisch uitgevoerd om te controleren op verdachte inbreukactiviteit, onjuist geconfigureerde computers en andere bevindingen en deze vervolgens te beantwoorden.

Deze mogelijkheid is vergelijkbaar met [geavanceerd zoeken in Microsoft Defender voor eindpunt.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) Deze functie is beschikbaar in het Microsoft 365-beveiligingscentrum en ondersteunt query's om een bredere gegevensset te controleren van:

- Microsoft Defender for Endpoint
- Microsoft Defender voor Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

Als u geavanceerd zoeken wilt gebruiken, [moet u Microsoft 365 Defender in te zetten.](mtp-enable.md)

## <a name="get-started-with-advanced-hunting"></a>Aan de slag met geavanceerd zoeken

We raden u aan diverse stappen uit te voeren om snel aan de slag te gaan met geavanceerd zoeken.

| Leerdoel | Beschrijving | Resource |
|--|--|--|
| **De taal leren** | Geavanceerd zoeken is gebaseerd op [de kusto-querytaal,](https://docs.microsoft.com/azure/kusto/query/)die dezelfde syntaxis en operatoren ondersteunt. Begin de querytaal te leren door uw eerste query uit te voeren. | [Overzicht van querytaal](advanced-hunting-query-language.md) |
| **Informatie over het gebruik van de queryresultaten** | Meer informatie over grafieken en verschillende manieren waarop u uw resultaten kunt weergeven of exporteren. Ontdek hoe u snel query's kunt aanpassen, inzoomen om uitgebreidere informatie te krijgen en antwoordacties kunt uitvoeren. | - [Werken met queryresultaten](advanced-hunting-query-results.md)<br>- [Actie ondernemen voor queryresultaten](advanced-hunting-take-action.md) |
| **Meer informatie over het schema** | Krijg een goed, goed inzicht in de tabellen in het schema en de kolommen. Informatie over waar u naar gegevens kunt zoeken wanneer u query's maakt. | - [Schemaverwijzing](advanced-hunting-schema-tables.md)<br>- [Overstappen van Microsoft Defender voor eindpunt](advanced-hunting-migrate-from-mdatp.md) |
| **Tips en voorbeelden van experts krijgen** | Train gratis met gidsen van Microsoft-experts. U kunt verzamelingen van vooraf gedefinieerde query's verkennen, waarin verschillende scenario's voor het zoeken naar bedreigingen worden beslaat. | - [Training voor experts krijgen](advanced-hunting-expert-training.md)<br>- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)<br>- [Zoeken](advanced-hunting-go-hunt.md)<br>- [Zoeken naar bedreigingen op apparaten, e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md) |
| **Query's optimaliseren en fouten verwerken** | Meer informatie over het maken van efficiënte en foutloze query's. | - [Best practices voor query's](advanced-hunting-best-practices.md)<br>- [Fouten verwerken](advanced-hunting-errors.md) |
| **Aangepaste detectieregels maken** | Meer informatie over hoe u geavanceerde zoekquery's kunt gebruiken om waarschuwingen te activeren en automatisch antwoordacties te ondernemen. | - [Overzicht van aangepaste detecties](custom-detections-overview.md)<br>- [Aangepaste detectieregels](custom-detection-rules.md) |

## <a name="get-access"></a>Toegang krijgen
Als u geavanceerd zoeken of andere mogelijkheden van [Microsoft 365 Defender](microsoft-threat-protection.md) wilt gebruiken, hebt u een geschikte rol in Azure Active Directory nodig. De toegang tot eindpuntgegevens wordt ook bepaald door instellingen voor toegangsbeheer op basis van rollen in Microsoft Defender voor eindpunt. [Meer informatie over het beheren van de toegang tot Microsoft 365 Defender](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>Actualiteit en frequentie van bijwerken van gegevens
Geavanceerde zoekgegevens kunnen worden gecategoriseerd in twee verschillende typen, elk samengevoegd op twee verschillende manieren.

- **Gebeurtenis- of activiteitsgegevens:** vult tabellen over waarschuwingen, beveiligingsgebeurtenissen, systeemgebeurtenissen en routinebeoordelingen. Geavanceerd zoeken ontvangt deze gegevens vrijwel direct na de sensoren die ze hebben verzameld om ze naar de bijbehorende cloudservices te sturen. U kunt bijvoorbeeld vrijwel direct nadat ze beschikbaar zijn op Microsoft Defender for Endpoint en Microsoft Defender for Identity, gebeurtenisgegevens opvragen uit gezonde sensoren op werkstations of domeincontrollers.
- **Entiteitsgegevens:** vult tabellen met informatie over gebruikers en apparaten. Deze gegevens zijn afkomstig van zowel relatief statische gegevensbronnen als dynamische bronnen, zoals Active Directory-vermeldingen en gebeurtenislogboeken. Als u nieuwe gegevens wilt leveren, worden tabellen elke 15 minuten bijgewerkt met nieuwe informatie en worden rijen toegevoegd die mogelijk niet volledig zijn ingevuld. Elke 24 uur worden gegevens samengevoegd om een record in te voegen die de nieuwste, meest uitgebreide gegevensset over elke entiteit bevat.

## <a name="time-zone"></a>Tijdzone
Tijdinformatie in geavanceerd zoeken bevindt zich in de UTC-tijdzone.

## <a name="related-topics"></a>Verwante onderwerpen
- [De querytaal leren](advanced-hunting-query-language.md)
- [Deskundige training verkrijgen](advanced-hunting-expert-training.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van aangepaste detectie](custom-detections-overview.md)

