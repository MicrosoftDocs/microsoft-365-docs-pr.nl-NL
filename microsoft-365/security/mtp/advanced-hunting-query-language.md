---
title: De geavanceerde zoekquerytaal in Microsoft 365 Defender leren
description: Uw eerste zoekquery voor bedreigingen maken en meer te weten komen over veelgebruikte operatoren en andere aspecten van de geavanceerde zoekquerytaal
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, language, learn, first query, telemetry, events, telemetry, custom detections, schema, kusto, operators, data types, powershell download, query example
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
ms.technology: m365d
ms.openlocfilehash: 41341a2b5238485fc58021fe4af71cd5c635352c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929800"
---
# <a name="learn-the-advanced-hunting-query-language"></a>De geavanceerde zoekquerytaal leren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Geavanceerd zoeken is gebaseerd op de [Kusto-querytaal.](https://docs.microsoft.com/azure/kusto/query/) U kunt de operatoren en instructies van Kusto gebruiken om query's te maken op zoek naar informatie in een speciaal [schema.](advanced-hunting-schema-tables.md) Voer uw eerste query uit om deze concepten beter te begrijpen.

## <a name="try-your-first-query"></a>Uw eerste query uitproberen

Ga in het Microsoft 365-beveiligingscentrum naar **Op zoek naar** uw eerste query. Gebruik het volgende voorbeeld:

```kusto
// Finds PowerShell execution events that could involve a download
union DeviceProcessEvents, DeviceNetworkEvents
| where Timestamp > ago(7d)
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
 "DownloadFile",
 "DownloadData",
 "DownloadString",
"WebRequest",
"Shellcode",
"http",
"https")
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

**[Voer deze query uit op geavanceerde zoekopdrachten](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>Beschrijf de query en geef de tabellen op waarin u wilt zoeken
Aan het begin van de query is een korte opmerking toegevoegd om te beschrijven waarvoor deze is gebruikt. Deze opmerking helpt als u later besluit de query op te slaan en te delen met anderen in uw organisatie. 

```kusto
// Finds PowerShell execution events that could involve a download
```

De query zelf begint meestal met een tabelnaam, gevolgd door een aantal elementen die beginnen met een s pipe ( `|` ). In dit voorbeeld maken we eerst een samenvoeging van twee tabellen en voegen we naar behoefte door de  `DeviceProcessEvents` `DeviceNetworkEvents` pipetelementen toe.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>Het tijdsbereik instellen
Het eerste element met de pipet is een tijdfilter dat is beperkt tot de vorige zeven dagen. Door het tijdsbereik te beperken, zorgt u ervoor dat query's goed presteren, beheerbare resultaten retourneren en geen time-out optreden.

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>Specifieke processen controleren
Het tijdsbereik wordt direct gevolgd door een zoekopdracht naar namen van procesbestanden die de PowerShell-toepassing vertegenwoordigen.

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>Zoeken naar specifieke opdrachtreeksen
Later zoekt de query naar tekenreeksen in opdrachtregels die meestal worden gebruikt voor het downloaden van bestanden met PowerShell.

```kusto
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
    "DownloadFile",
    "DownloadData",
    "DownloadString",
    "WebRequest",
    "Shellcode",
    "http",
    "https")
```

### <a name="customize-result-columns-and-length"></a>Resultaatkolommen en lengte aanpassen 
Nu uw query duidelijk de gegevens identificeert die u wilt zoeken, kunt u definiëren hoe de resultaten eruit zien. `project` retourneert specifieke kolommen en `top` beperkt het aantal resultaten. Deze operatoren zorgen ervoor dat de resultaten goed zijn opgemaakt en redelijk groot zijn en gemakkelijk kunnen worden verwerkt.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Selecteer **Query uitvoeren om** de resultaten te bekijken. Gebruik het pictogram Uitvbreed rechtsboven in de queryeditor om u te richten op uw zoekquery en de resultaten. 

![Afbeelding van het besturingselement Uitbreiden in de geavanceerde queryeditor](../../media/advanced-hunting-expand.png)

>[!TIP]
>U kunt queryresultaten weergeven als grafieken en filters snel aanpassen. Meer informatie over [het werken met queryresultaten](advanced-hunting-query-results.md)

## <a name="learn-common-query-operators"></a>Algemene queryoperatoren

U hebt zojuist uw eerste query uitgevoerd en hebt een algemeen idee van de onderdelen ervan. Het is tijd om een backtrack te maken en enkele basisprincipes te leren. De kusto-querytaal die wordt gebruikt door geavanceerd zoeken ondersteunt een reeks operatoren, waaronder de volgende algemene operatoren.

| Operator | Beschrijving en gebruik |
|--|--|
| `where` | Filter een tabel op de subset rijen die voldoen aan een predicaat. |
| `summarize` | Maak een tabel die de inhoud van de invoertabel samentelt. |
| `join` | Voeg de rijen van twee tabellen samen om een nieuwe tabel te maken door overeenkomende waarden uit de opgegeven kolommen uit elke tabel te combineren. |
| `count` | Het aantal records in de invoerrecordset retourneren. |
| `top` | Retourneert de eerste N-records die zijn gesorteerd op de opgegeven kolommen. |
| `limit` | Maximaal het opgegeven aantal rijen retourneren. |
| `project` | Selecteer de kolommen die u wilt opnemen, wijzigen of neerzetten en voeg nieuwe berekende kolommen in. |
| `extend` | Berekende kolommen maken en deze toevoegen aan de resultatenset. |
| `makeset` |  Retourneert een dynamische (JSON)-matrix van de set unieke waarden die Expr in de groep neemt. |
| `find` | Rijen zoeken die overeenkomen met een predicaat in een set tabellen. |

Als u een live voorbeeld van deze operators wilt zien, kunt u ze uitvoeren vanuit de sectie **Aan** de slag in geavanceerd zoeken.

## <a name="understand-data-types"></a>Gegevenstypen

Geavanceerd zoeken ondersteunt Kusto-gegevenstypen, waaronder de volgende veelgebruikte typen:

| Gegevenstype | Gevolgen voor beschrijving en query's |
|--|--|
| `datetime` | Gegevens- en tijdgegevens die meestal tijdstempels van gebeurtenissen vertegenwoordigen. [Ondersteunde datum-/tijdnota's bekijken](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | Tekenreeks in UTF-8 tussen enkele aanhalingstekens ( `'` ) of dubbele aanhalingstekens ( `"` ). [Meer informatie over tekenreeksen](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | Dit gegevenstype ondersteunt `true` of `false` wordt ondersteund. [Ondersteunde letterlijke letterlijke en operatoren bekijken](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | 32-bits geheel getal  |
| `long` | 64-bits geheel getal |

Meer informatie over deze gegevenstypen kunt u lezen in meer informatie [over scalaire kusto-gegevenstypen.](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/)

## <a name="get-help-as-you-write-queries"></a>Hulp krijgen tijdens het schrijven van query's
Maak gebruik van de volgende functionaliteit om sneller query's te schrijven:
- **AutoSuggest:** tijdens het schrijven van query's geeft geavanceerd zoeken suggesties van IntelliSense. 
- **Schemastructuur:** een schemaweergave met de lijst met tabellen en de kolommen naast uw werkgebied. Plaats de muisaanwijzer op een item voor meer informatie. Dubbelklik op een item om dit in te voegen in de queryeditor.
- **[Schemaverwijzing:](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** in-portalverwijzing met tabel- en kolombeschrijvingen en ondersteunde gebeurtenistypen `ActionType` (waarden) en voorbeeldquery's

## <a name="work-with-multiple-queries-in-the-editor"></a>Werken met meerdere query's in de editor
U kunt de queryeditor gebruiken om te experimenteren met meerdere query's. Meerdere query's gebruiken:

- Scheidt elke query met een lege regel.
- Plaats de cursor op een deel van een query om de query te selecteren voordat u deze uitvoert. Hiermee wordt alleen de geselecteerde query uitgevoerd. Als u een andere query wilt uitvoeren, verplaatst u de cursor dienovereenkomstig en **selecteert u Query uitvoeren.**

![Afbeelding van de queryeditor met meerdere query's](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a>Voorbeeldquery's gebruiken

De **sectie Aan de** slag bevat een paar eenvoudige query's met veelgebruikte operatoren. Probeer deze query's uit te kunnen uitvoeren en er kleine wijzigingen in aan te brengen.

![Afbeelding van geavanceerd zoekvenster](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>Afgezien van de basisqueryvoorbeelden, hebt u ook toegang tot [gedeelde query's](advanced-hunting-shared-queries.md) voor specifieke scenario's voor het zoeken naar bedreigingen. Verken de gedeelde query's aan de linkerkant van de pagina of de [GitHub-querybibliotheek.](https://aka.ms/hunting-queries)

## <a name="access-query-language-documentation"></a>Taaldocumentatie voor Access-query's

Zie de kusto-querytaaldocumentatie voor meer informatie over de [Kusto-querytaal en ondersteunde operatoren.](https://docs.microsoft.com/azure/kusto/query/)

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
