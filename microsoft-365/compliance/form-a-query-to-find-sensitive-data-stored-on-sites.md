---
title: Een query maken om te zoeken naar gevoelige gegevens die zijn opgeslagen op sites
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Gebruik DLP (Data Loss Prevention) in SharePoint Online om documenten te ontdekken die gevoelige gegevens in uw tenant bevatten.
ms.openlocfilehash: 04bf2e97dd2b5530838aef9fcb4b4467270d2d9d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287477"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>Een query maken om te zoeken naar gevoelige gegevens die zijn opgeslagen op sites

Gebruikers slaan vaak gevoelige gegevens, zoals creditcardnummers, socialezekerheidsnummers of persoonlijke, op hun sites op, en na een tijd kan dit een organisatie blootstellen aan een aanzienlijk risico op gegevensverlies. Documenten die zijn opgeslagen op sites, OneDrive voor Bedrijven sites, kunnen worden gedeeld met personen buiten de organisatie die geen toegang hebben tot de informatie. Met DLP (Data Loss Prevention) in SharePoint Online kunt u documenten ontdekken die gevoelige gegevens bevatten in uw tenant. Nadat u de documenten hebt ontdekt, kunt u samen met de documenteigenaren de gegevens beveiligen. Met dit onderwerp kunt u een query maken om te zoeken naar gevoelige gegevens.

> [!NOTE]
> Elektronische detectie of eDiscovery en DLP zijn premiumfuncties waarvoor SharePoint [online abonnement 2.](https://go.microsoft.com/fwlink/?LinkId=510080)

## <a name="forming-a-basic-dlp-query"></a>Een basis-DLP-query vormen

Er zijn drie onderdelen die een basis-DLP-query maken: SensitiveType, count range en betrouwbaarheidsbereik. Zoals in de volgende afbeelding wordt geïllustreerd, is **SensitiveType:" \<type\> vereist** en beide **|\<count range\>** en zijn ze **|\<confidence range\>** optioneel.

![Voorbeeldquery onderverdeeld in vereist en optioneel](../media/DLP-query-example-text.png)

### <a name="sensitive-type---required"></a>Gevoelig type - vereist

Wat is elk onderdeel? SharePoint DLP-query's beginnen meestal met de eigenschap en een naam van het informatietype uit de inventaris van gevoelige informatietypen `SensitiveType:"` en eindigen met een [](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) `"` . U kunt ook de naam gebruiken van een aangepast type [gevoelige informatie](create-a-custom-sensitive-information-type.md) dat u voor uw organisatie hebt gemaakt. U zoekt bijvoorbeeld documenten met creditcardnummers. In een dergelijk geval gebruikt u de volgende indeling:  `SensitiveType:"Credit Card Number"` . Omdat u het bereik van het aantal of het betrouwbaarheidsbereik niet hebt meegetelde, retourneert de query elk document waarin een creditcardnummer is gedetecteerd. Dit is de eenvoudigste query die u kunt uitvoeren en geeft de meeste resultaten als resultaat. Houd er rekening mee dat de spelling en afstand van het gevoelige type belangrijk zijn.

### <a name="ranges---optional"></a>Bereik - optioneel

Beide volgende twee delen zijn bereikbereiken, dus laten we snel bekijken hoe een bereik eruitziet. In SharePoint DLP-query's wordt een basisbereik vertegenwoordigd door twee getallen die zijn gescheiden door twee perioden, wat er als volgende uitziet: `[number]..[number]` . Als dit bereik bijvoorbeeld wordt gebruikt, worden getallen van  `10..20` 10 tot en met 20 vast gemaakt. Er zijn veel verschillende bereikcombinaties en er worden er verschillende besproken in dit onderwerp.

Laten we een aantalbereik toevoegen aan de query. U kunt het aantalbereiken gebruiken om het aantal exemplaren te definiëren van gevoelige informatie die een document moet bevatten voordat het wordt opgenomen in de queryresultaten. Als u bijvoorbeeld wilt dat uw query alleen documenten retourneert die precies vijf creditcardnummers bevatten, gebruikt u dit:  `SensitiveType:"Credit Card Number|5"` . Het bereik aantal kan u ook helpen bij het identificeren van documenten met een hoog risico. Uw organisatie kan documenten met vijf of meer creditcardnummers bijvoorbeeld als een hoog risico beschouwen. Als u documenten wilt zoeken die aan dit criterium voldoen, gebruikt u deze query:  `SensitiveType:"Credit Card Number|5.."` . U kunt ook documenten met vijf of minder creditcardnummers vinden met behulp van deze query:  `SensitiveType:"Credit Card Number|..5"` .

#### <a name="confidence-range"></a>Betrouwbaarheidsbereik

Ten slotte is het betrouwbaarheidsbereik het betrouwbaarheidsniveau dat het gedetecteerde gevoelige type daadwerkelijk een overeenkomst is. De waarden voor het betrouwbaarheidsbereik werken op dezelfde manier als het aantalbereiken. U kunt een query maken zonder een aantalbereiken op te tellen. Als u bijvoorbeeld wilt zoeken naar documenten met een groot aantal creditcardnummers , zolang het betrouwbaarheidsbereik 85 procent of hoger is, gebruikt u deze query:  `SensitiveType:"Credit Card Number|*|85.."` .

> [!IMPORTANT]
> Het sterretje `*` () is een jokerteken dat betekent dat elke waarde werkt. U kunt het jokerteken () gebruiken in het aantalbereik of in het betrouwbaarheidsbereik, maar `*` niet in een gevoelig type.

### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>Extra query-eigenschappen en zoekoperatoren beschikbaar in het eDiscovery-centrum

DLP in SharePoint introduceert ook de eigenschap LastSensitiveContentScan, waarmee u kunt zoeken naar bestanden die binnen een bepaalde periode zijn gescand. Zie Voorbeelden van complexe query's in de volgende sectie voor queryvoorbeelden `LastSensitiveContentScan` met de eigenschap. [](#examples-of-complex-queries)

U kunt niet alleen DLP-specifieke eigenschappen gebruiken om een query te maken, maar ook standaard SharePoint eDiscovery-zoekeigenschappen zoals `Author` of `FileExtension` . U kunt operatoren gebruiken om complexe query's te maken. Zie het blogbericht Zoekeigenschappen en operatoren gebruiken met [eDiscovery](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery) voor de lijst met beschikbare eigenschappen en operatoren.

## <a name="examples-of-complex-queries"></a>Voorbeelden van complexe query's

In de volgende voorbeelden worden verschillende gevoelige typen, eigenschappen en operatoren gebruikt om te illustreren hoe u uw query's kunt verfijnen om precies te vinden wat u zoekt.

<br>

****

|Query|Uitleg|
|---|---|
|`SensitiveType:"International Banking Account Number (IBAN)"`|De naam lijkt misschien vreemd omdat deze zo lang is, maar het is de juiste naam voor dat gevoelige type. Zorg ervoor dat u exacte namen gebruikt uit de [inventaris van gevoelige informatietypen.](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) U kunt ook de naam gebruiken van een aangepast type [gevoelige informatie](create-a-custom-sensitive-information-type.md) dat u voor uw organisatie hebt gemaakt.|
|`SensitiveType:"Credit Card Number|1..4294967295|1..100"`|Hiermee retourneert u documenten met ten minste één overeenkomst met het gevoelige type 'Creditcardnummer'. De waarden voor elk bereik zijn de respectievelijke minimum- en maximumwaarden. Een eenvoudigere manier om deze query te schrijven is  `SensitiveType:"Credit Card Number"` , maar waar is het plezier in dat?|
|`SensitiveType:"Credit Card Number|5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"`|Dit retourneert documenten met 5-25 creditcardnummers die zijn gescand van 11 augustus 2018 tot en met 13 augustus 2018.|
|`SensitiveType:"Credit Card Number|5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX`|Dit retourneert documenten met 5-25 creditcardnummers die zijn gescand van 11 augustus 2018 tot en met 13 augustus 2018. Bestanden met een XLSX-extensie worden niet opgenomen in de queryresultaten.  `FileExtension` is een van de vele eigenschappen die u in een query kunt opnemen. Zie Zoekeigenschappen en operatoren gebruiken met [eDiscovery](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery)voor meer informatie.|
|`SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"`|Hiermee retourneert u documenten die een creditcardnummer of een sociaal-zekerheidsnummer bevatten.|
|

## <a name="examples-of-queries-to-avoid"></a>Voorbeelden van query's om te voorkomen

Niet alle query's worden gelijk gemaakt. In de volgende tabel worden voorbeelden gegeven van query's die niet werken met DLP in SharePoint en wordt beschreven waarom.

<br>

****

|Niet-ondersteunde query|Reden|
|---|---|
|`SensitiveType:"Credit Card Number|.."`|U moet ten minste één getal toevoegen.|
|`SensitiveType:"NotARule"`|NotARule is geen geldige gevoelige typenaam. Alleen namen in de [inventaristypen voor gevoelige informatie werken](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) in DLP-query's.|
|`SensitiveType:"Credit Card Number|0"`|Nul is niet geldig als de minimumwaarde of de maximumwaarde in een bereik.|
|`SensitiveType:"Credit Card Number"`|Het is misschien moeilijk te zien, maar er is extra witruimte tussen 'Tegoed' en 'Kaart' waardoor de query ongeldig is. Gebruik exacte gevoelige typenamen uit de [inventaris van gevoelige informatietypen.](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)|
|`SensitiveType:"Credit Card Number|1. .3"`|Het gedeelte met twee perioden mag niet worden gescheiden door een spatie.|
|`SensitiveType:"Credit Card Number| |1..|80.."`|Er zijn te veel scheidingstekens voor pijpen ( \| ). Volg in plaats daarvan deze indeling: `SensitiveType: "Credit Card Number|1..|80.."`|
|`SensitiveType:"Credit Card Number|1..|80..101"`|Omdat betrouwbaarheidswaarden een percentage vertegenwoordigen, kunnen ze niet groter zijn dan 100. Kies in plaats daarvan een getal van 1 tot en met 100.|
|

## <a name="for-more-information"></a>Voor meer informatie

- [Entiteitsdefinities voor het type gevoelige informatie](sensitive-information-type-entity-definitions.md)
- [Een inhoudszoekactie uitvoeren](content-search.md)
- [Trefwoordquery's en zoekvoorwaarden voor Zoeken naar inhoud](keyword-queries-and-search-conditions.md)
