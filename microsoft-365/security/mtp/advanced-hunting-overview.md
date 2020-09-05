---
title: Overzicht-geavanceerde jacht
description: Meer informatie over geavanceerde zoekopdrachten in Microsoft 365 en hoe u deze kunt gebruiken om bedreigingen en zwakke plekken te vinden in uw netwerk
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, aangepaste detectie, schema, kusto, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ae0105fd5eba134c7896daef34136748802e9010
ms.sourcegitcommit: 916fa2dacbc13287b49823176375259d7af03f86
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/04/2020
ms.locfileid: "47394679"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Ervaring opzeggen met een geavanceerde jacht in Microsoft Threat Protection

**Van toepassing op:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Geavanceerd zoeken is een probleem met de hulpmiddelen op basis van een query die u kunt gebruiken om maximaal 30 dagen onbewerkte gegevens te bekijken. U kunt de gebeurtenissen in uw netwerk proactief controleren om interessante indicatoren en entiteiten te vinden. De flexibele toegang tot gegevens bevordert het vergemakkelijken van de jacht voor zowel bekende als potentiële bedreigingen.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

U kunt dezelfde aanvals opdrachten gebruiken om aangepaste detectieregels te maken. Deze regels worden automatisch uitgevoerd om diverse gebeurtenissen en systeem statussen te controleren en te beantwoorden, waaronder verdachte inbreuk activiteiten en onjuist geconfigureerde computers.

Deze mogelijkheid is vergelijkbaar met de [geavanceerde jacht in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview), met uitzondering van de geavanceerde jacht in Microsoft Threat Protection, dat beschikbaar is in het microsoft 365-Beveiligingscentrum, biedt ondersteuning voor query's die in gegevens van diverse werkruimten kijken, waaronder informatie over apparaten, e-mailberichten, apps en identiteiten, en van Azure ATP voor Office 365. Als u de geavanceerde jacht wilt gebruiken, [schakelt u Microsoft Threat Protection in](mtp-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Aan de slag met geavanceerde jacht

We raden u aan meerdere stappen uit te voeren om snel aan de slag te gaan met de geavanceerde jacht.

| Leer doel | Beschrijving | Materialen |
|--|--|--|
| **Zorg voor de taal** | De geavanceerde jacht is gebaseerd op de [querytaal Kusto](https://docs.microsoft.com/azure/kusto/query/), die dezelfde syntaxis en operatoren ondersteunt. Begin met het leren van de querytaal door uw eerste query uit te voeren. | [Overzicht van query taal](advanced-hunting-query-language.md) |
| **Meer informatie over het gebruik van de queryresultaten** | Meer informatie over grafieken en verschillende manieren waarop u uw resultaten kunt weergeven of exporteren. Ontdek hoe u snel aan de slag kunt met query's, inzoomen om meer informatie te verkrijgen en antwoord acties te ondernemen. | - [Werken met queryresultaten](advanced-hunting-query-results.md)<br>- [Actie ondernemen op queryresultaten](advanced-hunting-take-action.md) |
| **Meer informatie over het schema** | U kunt beter inzicht krijgen in de tabellen in het schema en de bijbehorende kolommen. Dit helpt u bij de locatie van de zoekresultaten en de manier waarop u query's opstelt. | [Overzicht van schema](advanced-hunting-schema-tables.md) |
| **Voor gebruik van vooraf gedefinieerde query's** | Verken verzamelingen van vooraf gedefinieerde query's met verschillende scenario's voor bedreigings jacht. | - [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)<br>- [Ga naar zoeken](advanced-hunting-go-hunt.md) |
| **Query's optimaliseren** | Meer informatie over hoe u efficiënte query's en query's maakt waarmee u gegevens uit e-mailberichten en apparaten kunt combineren. | - [Aanbevolen procedures voor query's](advanced-hunting-best-practices.md) <br>- [Over apparaten en e-mailberichten doorzoeken](advanced-hunting-query-emails-devices.md) |
| **Aangepaste detectieregels maken** | Meer informatie over hoe u geavanceerde zoekopdrachten kunt gebruiken om waarschuwingen te activeren en antwoord acties automatisch toe te passen. | - [Overzicht van aangepaste detectie](custom-detections-overview.md)<br>- [Aangepaste detectieregels](custom-detection-rules.md) |

## <a name="get-access"></a>Toegang krijgen
Als u de geavanceerde jacht of andere mogelijkheden van [Microsoft Threat Protection](microsoft-threat-protection.md) wilt gebruiken, moet u beschikken over de juiste rol in azure AD. Houd er rekening mee dat uw toegang tot eindpuntgegevens wordt beïnvloed door de instellingen voor toegangsbeheer op basis van rollen in Microsoft Defender ATP. [Lees meer over het beheren van de toegang tot Microsoft Threat Protection](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>Gegevens versheid en frequentie bijwerken
Geavanceerde jacht-gegevens kunnen worden ingedeeld in twee verschillende typen, elk samengevoegd.

- **Gegevens uit een gebeurtenis of activiteit** : hierin worden tabellen over waarschuwingen, beveiligingsgebeurtenissen, systeemgebeurtenissen en routine beoordelingen ingevuld. De geavanceerde jacht ontvangt deze gegevens bijna direct na de sensoren die de sensoren met succesvol verzamelen naar de bijbehorende cloudservices. U kunt bijvoorbeeld een query uitvoeren op gegevens van een evenement met een goede sensoren op een werkstation of domeincontroller bijna direct nadat deze beschikbaar zijn in Microsoft Defender ATP en Azure ATP.
- **Entiteitsgegevens** : tabellen met geconsolideerde informatie over gebruikers en apparaten vullen. Deze gegevens zijn afkomstig uit niet-tamelijk statische gegevensbronnen, zoals Active Directory-vermeldingen en dynamische bronnen, zoals gebeurtenislogboeken. Als u nieuwe gegevens wilt weergeven, worden tabellen elke 15 minuten bijgewerkt met nieuwe gegevens, waarbij het toevoegen van rijen die mogelijk niet volledig zijn ingevuld, wordt toegevoegd. Elke 24 uur worden gegevens samengevoegd om een record in te voegen die de meest recente gegevensverzameling bevat voor elke entiteit.

## <a name="time-zone"></a>Tijdzone
Alle tijdinformatie in de geavanceerde jacht bevindt zich in de UTC-tijdzone.

## <a name="related-topics"></a>Verwante onderwerpen
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Actie ondernem op queryresultaten](advanced-hunting-take-action.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van aangepaste detectie](custom-detections-overview.md)
