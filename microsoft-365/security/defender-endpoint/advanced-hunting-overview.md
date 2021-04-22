---
title: Overzicht van geavanceerd zoeken in Microsoft Defender voor Eindpunt
description: Gebruik mogelijkheden voor het zoeken naar bedreigingen in Microsoft Defender voor Eindpunt om query's te maken waarin bedreigingen en zwakke punten in uw netwerk worden gevonden
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, microsoft defender for endpoint, wdatp, search, query, telemetry, custom detections, schema, kusto, time zone, UTC
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 906ae4bdebcc46e210fa9c5dcb5387c880fdbb38
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939658"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting"></a>Proactief op bedreigingen zoeken met geavanceerde jacht

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Geavanceerd zoeken is een op query's gebaseerd hulpprogramma voor bedreigingsjacht waarmee u tot 30 dagen onbewerkte gegevens kunt verkennen. U kunt gebeurtenissen in uw netwerk proactief controleren om bedreigingsindicatoren en entiteiten te zoeken. De flexibele toegang tot gegevens maakt ongeconseld zoeken naar bekende en potentiële bedreigingen mogelijk.

Bekijk deze video voor een kort overzicht van geavanceerde jacht en een korte zelfstudie om snel aan de slag te gaan.
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqo]

U kunt dezelfde query's voor het zoeken naar bedreigingen gebruiken om aangepaste detectieregels te maken. Deze regels worden automatisch uitgevoerd om te controleren of en vervolgens te reageren op verdachte inbreukactiviteiten, verkeerd geconfigureerde machines en andere bevindingen.

>[!TIP]
>Gebruik [geavanceerde jacht in Microsoft 365 Defender](/microsoft-365/security/defender/advanced-hunting-overview) om te zoeken naar bedreigingen met behulp van gegevens van Defender voor Eindpunt, Microsoft Defender voor Office 365, Microsoft Cloud App Security en Microsoft Defender voor identiteit. [Schakel Microsoft 365 Defender in.](/microsoft-365/security/defender/m365d-enable)<br><br>
Meer informatie over het verplaatsen van uw geavanceerde zoekwerkstromen van Microsoft Defender voor Eindpunt naar Microsoft 365 Defender in Geavanceerde zoekquery's migreren van [Microsoft Defender voor Eindpunt.](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde)

## <a name="get-started-with-advanced-hunting"></a>Aan de slag met geavanceerde jacht

Ga door de volgende stappen om uw geavanceerde kennis op het gebied van jagen te verbreeden.

We raden u aan om verschillende stappen uit te voeren om snel aan de haal te gaan met geavanceerde jacht.

| Leerdoel | Beschrijving | Resource |
|--|--|--|
| **De taal leren** | Geavanceerd zoeken is gebaseerd op [de querytaal Kusto,](https://docs.microsoft.com/azure/kusto/query/)die dezelfde syntaxis en operatoren ondersteunt. Begin de querytaal te leren door de eerste query uit te voeren. | [Overzicht van querytaal](advanced-hunting-query-language.md) |
| **Meer informatie over het gebruik van de queryresultaten** | Meer informatie over grafieken en verschillende manieren waarop u uw resultaten kunt bekijken of exporteren. Ontdek hoe u snel query's kunt aanpassen en kunt inzoomen om uitgebreidere informatie te krijgen. | [Werken met queryresultaten](advanced-hunting-query-results.md) |
| **Meer informatie over het schema** | Krijg een goed, goed inzicht in de tabellen in het schema en de kolommen. Informatie over waar u gegevens kunt zoeken bij het maken van query's. | [Schemaverwijzing](advanced-hunting-schema-reference.md) |
| **Vooraf gedefinieerde query's gebruiken** | Verken verzamelingen van vooraf gedefinieerde query's met verschillende scenario's voor het zoeken naar bedreigingen. | [Gedeelde query's](advanced-hunting-shared-queries.md) |
| **Query's optimaliseren en fouten verwerken** | Meer informatie over het maken van efficiënte en foutloze query's. | - [Query-best practices](advanced-hunting-best-practices.md)<br>- [Fouten verwerken](advanced-hunting-errors.md) |
| **De meest volledige dekking krijgen** | Gebruik auditinstellingen om een betere gegevensdekking voor uw organisatie te bieden. | - [Geavanceerde dekking voor jagen uitbreiden](advanced-hunting-extend-data.md) |
| **Een snel onderzoek uitvoeren** | Voer snel een geavanceerde query uit om verdachte activiteiten te onderzoeken. | - [Snel zoeken naar entiteits- of gebeurtenisgegevens met *go hunt*](advanced-hunting-go-hunt.md) |
| **Bedreigingen bevatten en compromissen aanpakken** | Reageren op aanvallen door bestanden te quarantineren, de uitvoering van apps te beperken en andere acties | - [Actie ondernemen voor geavanceerde resultaten van query's](advanced-hunting-take-action.md) |
| **Aangepaste detectieregels maken** | Meer informatie over hoe u geavanceerde zoekquery's kunt gebruiken om waarschuwingen te activeren en automatisch antwoordacties uit te voeren. | - [Overzicht van aangepaste detecties](overview-custom-detections.md)<br>- [Aangepaste detectieregels](custom-detection-rules.md) |

## <a name="data-freshness-and-update-frequency"></a>Gegevensverfheid en updatefrequentie

Geavanceerde zoekgegevens kunnen worden gecategoriseerd in twee verschillende typen, elk op een andere manier samengevoegd.

- **Gebeurtenis- of** activiteitsgegevens: vult tabellen over waarschuwingen, beveiligingsgebeurtenissen, systeemgebeurtenissen en routinebeoordelingen. Advanced hunting ontvangt deze gegevens vrijwel direct nadat de sensoren die ze verzamelen deze met succes naar Defender voor Eindpunt verzenden.
- **Entiteitsgegevens:** hiermee worden tabellen gevuld met samengevoegde informatie over gebruikers en apparaten. Deze gegevens komen uit zowel relatief statische gegevensbronnen als dynamische bronnen, zoals Active Directory-items en gebeurtenislogboeken. Als u nieuwe gegevens wilt verstrekken, worden tabellen elke 15 minuten bijgewerkt met nieuwe informatie, zodat rijen worden toegevoegd die mogelijk niet volledig zijn ingevuld. Elke 24 uur worden gegevens samengevoegd om een record in te voegen die de meest recente, meest uitgebreide gegevensset over elke entiteit bevat.

## <a name="time-zone"></a>Tijdzone

Tijdinformatie in geavanceerde jacht bevindt zich momenteel in de UTC-tijdzone.

## <a name="related-topics"></a>Verwante onderwerpen

- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Meer informatie over het schema](advanced-hunting-schema-reference.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van aangepaste detectie](overview-custom-detections.md)
