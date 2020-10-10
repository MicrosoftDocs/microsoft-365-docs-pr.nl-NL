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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d231e1d2f05a2ff7c5abc86a74c6301043268f6e
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412668"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Ervaring opzeggen met een geavanceerde jacht in Microsoft Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

Geavanceerd zoeken is een probleem met de hulpmiddelen op basis van een query die u kunt gebruiken om maximaal 30 dagen onbewerkte gegevens te bekijken. U kunt gebeurtenissen in uw netwerk proactief controleren om te zoeken naar bedreigings indicatoren en entiteiten. De flexibele toegang tot gegevens veroorzaakt een ongebeperkinge jacht voor zowel bekende als potentiële bedreigingen.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

U kunt dezelfde aanvals opdrachten gebruiken om aangepaste detectieregels te maken. Deze regels worden automatisch uitgevoerd om te controleren op de verdachte inbreuk activiteiten, verkeerd geconfigureerde computers en andere bevindingen.

Deze mogelijkheid is vergelijkbaar met de [geavanceerde jacht in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview). Deze functie is beschikbaar in Microsoft 365 Beveiligingscentrum en biedt ondersteuning voor query's waarmee een bredere gegevensset wordt gecontroleerd:

- Microsoft Defender Advanced Threat Protection
- Office 365 Advanced Threat Protection
- Microsoft Cloud App Security
- Azure Advanced Threat Protection

Als u de geavanceerde jacht wilt gebruiken, [schakelt u Microsoft Threat Protection in](mtp-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Aan de slag met geavanceerde jacht

We raden u aan diverse stappen te volgen om snel aan de slag te gaan met de geavanceerde jacht.

| Leer doel | Beschrijving | Materialen |
|--|--|--|
| **Meer informatie over de taal** | De geavanceerde jacht is gebaseerd op de [querytaal Kusto](https://docs.microsoft.com/azure/kusto/query/), die dezelfde syntaxis en operatoren ondersteunt. Begin met het leren van de querytaal door uw eerste query uit te voeren. | [Overzicht van query taal](advanced-hunting-query-language.md) |
| **Meer informatie over het gebruik van de queryresultaten** | Meer informatie over grafieken en verschillende manieren waarop u uw resultaten kunt weergeven of exporteren. Ontdek hoe u snel aan de slag kunt met query's, inzoomen om meer informatie te verkrijgen en antwoord acties te ondernemen. | - [Werken met queryresultaten](advanced-hunting-query-results.md)<br>- [Actie ondernemen op queryresultaten](advanced-hunting-take-action.md) |
| **Meer informatie over het schema** | U kunt beter inzicht krijgen in de tabellen in het schema en de bijbehorende kolommen. Meer informatie over waar u kunt zoeken naar gegevens bij het maken van uw query's. | - [Overzicht van schema](advanced-hunting-schema-tables.md)<br>- [Overstappen van Microsoft Defender ATP](advanced-hunting-migrate-from-mdatp.md) |
| **Geniet van deskundige tips en voorbeelden** | Gratis training met gidsen van Microsoft experts. Verken verzamelingen van vooraf gedefinieerde query's met verschillende scenario's voor bedreigings jacht. | - [Professionele training krijgen](advanced-hunting-expert-training.md)<br>- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)<br>- [Ga naar zoeken](advanced-hunting-go-hunt.md)<br>- [Zoeken naar bedreigingen op apparaten, e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md) |
| **Query's en fouten afhandelen optimaliseren** | Meer informatie over het maken van efficiënt en zonder fouten. | - [Aanbevolen procedures voor query's](advanced-hunting-best-practices.md)<br>- [Fouten afhandelen](advanced-hunting-errors.md) |
| **Aangepaste detectieregels maken** | Meer informatie over hoe u geavanceerde zoekopdrachten kunt gebruiken om waarschuwingen te activeren en antwoord acties automatisch te ondernemen. | - [Overzicht van aangepaste detectie](custom-detections-overview.md)<br>- [Aangepaste detectieregels](custom-detection-rules.md) |

## <a name="get-access"></a>Toegang krijgen
Als u de geavanceerde jacht of andere mogelijkheden van [Microsoft Threat Protection](microsoft-threat-protection.md) wilt gebruiken, hebt u een juiste rol nodig in azure Active Directory. Ook wordt uw toegang tot eindpuntgegevens bepaald door de instellingen voor toegangsbeheer op basis van rollen in Microsoft Defender ATP. [Lees meer over het beheren van de toegang tot Microsoft Threat Protection](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>Gegevens versheid en frequentie bijwerken
Geavanceerde jacht-gegevens kunnen worden ingedeeld in twee verschillende typen, elk samengevoegd.

- **Gegevens uit een gebeurtenis of activiteit**: hierin worden tabellen over waarschuwingen, beveiligingsgebeurtenissen, systeemgebeurtenissen en routine beoordelingen ingevuld. De geavanceerde jacht ontvangt deze gegevens bijna direct na de sensoren die de sensoren met succesvol verzamelen naar de bijbehorende cloudservices. U kunt bijvoorbeeld een query uitvoeren op gegevens van een evenement met een goede sensoren op een werkstation of domeincontroller bijna direct nadat deze beschikbaar zijn in Microsoft Defender ATP en Azure ATP.
- **Entiteitsgegevens**: tabellen met informatie over gebruikers en apparaten vullen. Deze gegevens zijn afkomstig uit zowel relatief statische gegevensbronnen als dynamische bronnen, zoals Active Directory vermeldingen en gebeurtenislogboeken. Als u nieuwe gegevens wilt weergeven, worden de tabellen elke 15 minuten bijgewerkt met alle nieuwe gegevens, waarbij de rijen die mogelijk niet volledig zijn ingevuld, worden toegevoegd. Elke 24 uur worden gegevens samengevoegd om een record in te voegen die de meest recente gegevensverzameling bevat voor elke entiteit.

## <a name="time-zone"></a>Tijdzone
De tijdinformatie in de geavanceerde jacht bevindt zich in de UTC-tijdzone.

## <a name="related-topics"></a>Verwante onderwerpen
- [De querytaal leren](advanced-hunting-query-language.md)
- [Deskundige training verkrijgen](advanced-hunting-expert-training.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van aangepaste detectie](custom-detections-overview.md)

