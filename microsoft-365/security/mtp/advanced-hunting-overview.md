---
title: Overzicht - Geavanceerd zoeken
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
ms.openlocfilehash: 5101a7516403bfaf1ad5aa21e1f54bc5ecab6aeb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904100"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>Proactief op bedreigingen zoeken met geavanceerde jacht in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

> Wilt u Microsoft 365 Defender ervaren? U kunt [het project evalueren in een labomgeving](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab) of uw [pilotproject uitvoeren in productie.](./mtp-pilot.md?ocid=cx-evalpilot)
>

Geavanceerd zoeken is een op query's gebaseerd hulpprogramma voor bedreigingsjacht waarmee u tot 30 dagen onbewerkte gegevens kunt verkennen. U kunt gebeurtenissen in uw netwerk proactief controleren om bedreigingsindicatoren en entiteiten te zoeken. De flexibele toegang tot gegevens maakt ongeconseld zoeken naar bekende en potentiële bedreigingen mogelijk.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

U kunt dezelfde query's voor het zoeken naar bedreigingen gebruiken om aangepaste detectieregels te maken. Deze regels worden automatisch uitgevoerd om te controleren of en vervolgens te reageren op verdachte inbreukactiviteiten, verkeerd geconfigureerde machines en andere bevindingen.

Deze mogelijkheid is vergelijkbaar met [geavanceerde jacht in Microsoft Defender voor eindpunt.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) Deze functie is beschikbaar in het Microsoft 365-beveiligingscentrum en ondersteunt query's die een bredere gegevensset controleren op basis van:

- Microsoft Defender for Endpoint
- Microsoft Defender voor Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

Als u geavanceerde jacht wilt gebruiken, [schakelt u Microsoft 365 Defender in.](mtp-enable.md)

## <a name="get-started-with-advanced-hunting"></a>Aan de slag met geavanceerde jacht

Het is raadzaam om verschillende stappen uit te voeren om snel aan de slag te gaan met geavanceerde jacht.

| Leerdoel | Beschrijving | Resource |
|--|--|--|
| **De taal leren** | Geavanceerd zoeken is gebaseerd op [de querytaal Kusto,](/azure/kusto/query/)die dezelfde syntaxis en operatoren ondersteunt. Begin de querytaal te leren door de eerste query uit te voeren. | [Overzicht van querytaal](advanced-hunting-query-language.md) |
| **Meer informatie over het gebruik van de queryresultaten** | Meer informatie over grafieken en verschillende manieren waarop u uw resultaten kunt bekijken of exporteren. Ontdek hoe u snel query's kunt aanpassen, kunt inzoomen om uitgebreidere informatie te krijgen en antwoordacties kunt uitvoeren. | - [Werken met queryresultaten](advanced-hunting-query-results.md)<br>- [Actie ondernemen voor queryresultaten](advanced-hunting-take-action.md) |
| **Meer informatie over het schema** | Krijg een goed, goed inzicht in de tabellen in het schema en de kolommen. Informatie over waar u gegevens kunt zoeken bij het maken van query's. | - [Schemaverwijzing](advanced-hunting-schema-tables.md)<br>- [Overgang van Microsoft Defender voor Eindpunt](advanced-hunting-migrate-from-mdatp.md) |
| **Tips en voorbeelden van experts krijgen** | Train gratis met handleidingen van Microsoft-experts. Verken verzamelingen van vooraf gedefinieerde query's met verschillende scenario's voor het zoeken naar bedreigingen. | - [Training van experts krijgen](advanced-hunting-expert-training.md)<br>- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)<br>- [Ga op zoek](advanced-hunting-go-hunt.md)<br>- [Op bedreigingen zoeken op verschillende apparaten, e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md) |
| **Query's optimaliseren en fouten verwerken** | Meer informatie over het maken van efficiënte en foutloze query's. | - [Query-best practices](advanced-hunting-best-practices.md)<br>- [Fouten verwerken](advanced-hunting-errors.md) |
| **Aangepaste detectieregels maken** | Meer informatie over hoe u geavanceerde zoekquery's kunt gebruiken om waarschuwingen te activeren en automatisch antwoordacties uit te voeren. | - [Overzicht van aangepaste detecties](custom-detections-overview.md)<br>- [Aangepaste detectieregels](custom-detection-rules.md) |

## <a name="get-access"></a>Toegang krijgen
Als u geavanceerde zoekmogelijkheden of andere [Microsoft 365 Defender-mogelijkheden](microsoft-threat-protection.md) wilt gebruiken, hebt u een geschikte rol nodig in Azure Active Directory. Uw toegang tot eindpuntgegevens wordt ook bepaald door RBAC-instellingen (Role-Based Access Control) in Microsoft Defender for Endpoint. [Meer informatie over het beheren van toegang tot Microsoft 365 Defender](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>Gegevensverfheid en updatefrequentie
Geavanceerde zoekgegevens kunnen worden gecategoriseerd in twee verschillende typen, elk op een andere manier samengevoegd.

- **Gebeurtenis- of** activiteitsgegevens: vult tabellen over waarschuwingen, beveiligingsgebeurtenissen, systeemgebeurtenissen en routinebeoordelingen. Advanced hunting ontvangt deze gegevens vrijwel direct nadat de sensoren die ze verzamelen deze met succes naar de bijbehorende cloudservices verzenden. U kunt bijvoorbeeld gebeurtenisgegevens opvragen van gezonde sensoren op werkstations of domeincontrollers, vrijwel direct nadat ze beschikbaar zijn op Microsoft Defender voor Eindpunt en Microsoft Defender voor identiteit.
- **Entiteitsgegevens:** vult tabellen met informatie over gebruikers en apparaten. Deze gegevens komen uit zowel relatief statische gegevensbronnen als dynamische bronnen, zoals Active Directory-items en gebeurtenislogboeken. Als u nieuwe gegevens wilt verstrekken, worden tabellen elke 15 minuten bijgewerkt met nieuwe informatie, zodat rijen worden toegevoegd die mogelijk niet volledig zijn ingevuld. Elke 24 uur worden gegevens samengevoegd om een record in te voegen die de meest recente, meest uitgebreide gegevensset over elke entiteit bevat.

## <a name="time-zone"></a>Tijdzone
Tijdinformatie in geavanceerde jacht bevindt zich in de UTC-tijdzone.

## <a name="related-topics"></a>Verwante onderwerpen
- [De querytaal leren](advanced-hunting-query-language.md)
- [Deskundige training verkrijgen](advanced-hunting-expert-training.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van aangepaste detectie](custom-detections-overview.md)