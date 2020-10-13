---
title: Meer informatie over de querytaal Advanced jacht in Microsoft Threat Protection
description: Maak uw eerste bedreigings informatie en leer meer over de gangbare operatoren en andere aspecten van de geavanceerde jacht-querytaal
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, update, learn, First query, Telemetry, gebeurtenissen, telemetrie, aangepaste detectie, schema, telemetrie, en voorbeeld van gegevenstypen
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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 09f0a5437c3ae3b54fa086d93e475e4881c2d4bf
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48431049"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Meer informatie over de querytaal Advanced jacht

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

Voor de geavanceerde jacht op basis van de [querytaal Kusto](https://docs.microsoft.com/azure/kusto/query/). U kunt Kusto operatoren en statements gebruiken om query's te maken waarmee informatie in een speciaal [schema](advanced-hunting-schema-tables.md)wordt gezocht. Voor een betere uitleg van deze concepten voert u uw eerste query uit.

## <a name="try-your-first-query"></a>Probeer uw eerste query

In Microsoft 365 Beveiligingscentrum gaat u naar **jacht** om uw eerste query uit te voeren. Gebruik het volgende voorbeeld:

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

**[Voer deze query uit in geavanceerde jacht](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>De query beschrijven en de tabellen opgeven waarnaar moet worden gezocht
Er is een korte opmerking toegevoegd aan het begin van de query om te beschrijven wat het is. Deze opmerking helpt u als u later besluit om de query op te slaan en te delen met anderen in uw organisatie. 

```kusto
// Finds PowerShell execution events that could involve a download
```

De query zelf begint meestal met een tabelnaam gevolgd door meerdere elementen die beginnen met een sluisteken ( `|` ). In dit voorbeeld beginnen we met het maken van een samenvoeging van twee tabellen, en het  `DeviceProcessEvents` `DeviceNetworkEvents` toevoegen van elementen met een sluisteken.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>Het tijdsbereik instellen
Het eerste element met een pipet is een tijdfilter bereik dat de afgelopen zeven dagen is beperkt. Wanneer u de periode beperkt, kunt u ervoor zorgen dat query's goed worden uitgevoerd, de beheerbare resultaten kunnen resulteren en geen tijd in beslag gaan.

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>Specifieke processen controleren
Het tijdsbereik wordt direct gevolgd door een zoekopdracht naar proces bestandsnamen die de PowerShell-toepassing vertegenwoordigen.

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>Zoeken naar specifieke opdrachtreeksen
Vervolgens zoekt de query naar tekenreeksen in opdrachtregels die meestal worden gebruikt om bestanden te downloaden met PowerShell.

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

### <a name="customize-result-columns-and-length"></a>Resultatenkolommen en lengte aanpassen 
Wanneer de gegevens die u wilt zoeken duidelijk worden geïdentificeerd met de query, kunt u definiëren hoe de resultaten eruit komen te zien. `project` geeft als resultaat bepaalde kolommen en `top` beperkt het aantal resultaten. Met deze operatoren zorgt u ervoor dat de resultaten goed opgemaakt en redelijk zijn.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Selecteer **query uitvoeren** om de resultaten te bekijken. Met het pictogram uitvouwen in de rechterbovenhoek van de query editor kunt u zich richten op de jacht-query en de resultaten. 

![Afbeelding van het besturingselement uitvouwen in de geavanceerde jacht query editor](../../media/advanced-hunting-expand.png)

>[!TIP]
>U kunt queryresultaten weergeven als grafieken en de filters snel aanpassen. [Zie voor meer informatie over het werken met queryresultaten](advanced-hunting-query-results.md)

## <a name="learn-common-query-operators"></a>Veelgebruikte queryoperators

U voer zojuist uw eerste query uit en hebt een algemeen idee van de onderdelen. Het is tijd om iets iets te terugkeren iets en meer informatie over de basisbeginselen te leren kennen. De Kusto querytaal die wordt gebruikt in de geavanceerde jacht, biedt ondersteuning voor een bereik van operatoren, waaronder de volgende algemene versies.

| Werk | Beschrijving en gebruik |
|--|--|
| `where` | Een tabel filteren op de subset van rijen die op een predicaat voldoen. |
| `summarize` | Een tabel maken waarmee de inhoud van de invoertabel wordt geaggregeerd. |
| `join` | De rijen van twee tabellen samenvoegen om een nieuwe tabel te maken door te zoeken naar waarden van de opgegeven kolommen in elke tabel. |
| `count` | Het aantal records in de invoerrecord retourneren. |
| `top` | De eerste N records die op de opgegeven kolommen zijn gesorteerd, retourneren. |
| `limit` | Naar het opgegeven aantal rijen gaan. |
| `project` | Selecteer de kolommen die u wilt opnemen, waarvan u de naam wilt wijzigen of die u wilt verwijderen en voeg nieuwe berekende kolommen in. |
| `extend` | Berekende kolommen maken en deze toevoegen aan de resultatenset. |
| `makeset` |  Retourneert een dynamische (JSON) matrix van de reeks unieke waarden die in de groep worden gebruikt. |
| `find` | Rijen zoeken die overeenkomen met een predicaat in een set tabellen. |

Als u een voorbeeld van deze operatoren wilt zien, voert u deze uit in de sectie **aan de slag** in geavanceerde jacht.

## <a name="understand-data-types"></a>Meer informatie over gegevenstypen

Geavanceerde jacht biedt ondersteuning voor Kusto-gegevenstypen, waaronder de volgende algemene typen:

| Gegevenstype | Beschrijving van de gevolgen van de query |
|--|--|
| `datetime` | Gegevens en tijds informatie die meestal tijdstempels voor gebeurtenissen vertegenwoordigen. [Ondersteunde notaties voor datetime weergeven](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | Tekenreeks in UTF-8 tussen enkele aanhalingstekens ( `'` ) of dubbele aanhalingstekens ( `"` ). [Lees meer over tekenreeksen](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | Dit gegevenstype ondersteunt `true` of `false` staat. [Ondersteunde letterlijke waarden en operatoren weergeven](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | 32-bits integer  |
| `long` | 64-bits integer |

Meer informatie over deze gegevenstypen vindt u in [Kusto scalaire gegevenstypen](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).

## <a name="get-help-as-you-write-queries"></a>Hulp vragen bij het schrijven van query's
Profiteer van de volgende functies om query's sneller te schrijven:
- **Suggesties, wanneer**u query's schrijft, biedt geavanceerde jacht suggesties voor IntelliSense. 
- **Schemastructuur**: een schema weergave met daarin de lijst met tabellen en de bijbehorende kolommen wordt weergegeven naast uw werkruimte. Plaats de muisaanwijzer op een item voor meer informatie. Dubbelklik op een item om het in te voegen in de query editor.
- Naslag voor **[schema verwijzingen](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** in de portal met beschrijvingen van tabellen en kolommen, en ondersteunde gebeurtenistypen ( `ActionType` waarden) en voorbeeldquery's

## <a name="work-with-multiple-queries-in-the-editor"></a>Werken met meerdere query's in de editor
Met de query editor kunt u experimenteren met meerdere query's. Meerdere query's gebruiken:

- Afzonderlijke query's met een lege regel scheiden.
- Plaats de cursor op een deel van een query om die query te selecteren voordat u deze uitvoert. Hiermee wordt alleen de geselecteerde query uitgevoerd. Als u een andere query wilt uitvoeren, verplaatst u de cursor dienovereenkomstig en selecteert u **query uitvoeren**.

![Afbeelding van de query editor met meerdere query's](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a>Voorbeeldquery's gebruiken

De sectie **aan** de slag biedt een paar eenvoudige query's waarbij veelgebruikte operatoren worden gebruikt. Voer deze query's uit en wijzig deze met een kleine wijziging.

![Afbeelding van het venster Geavanceerde jacht](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>Afgezien van de basisvoorbeelden van de query, hebt u ook toegang tot [gedeelde query's](advanced-hunting-shared-queries.md) voor specifieke scenario's voor bedreigings jacht. Verstudeer de gedeelde query's aan de linkerkant van de pagina of in de [github query-bibliotheek](https://aka.ms/hunting-queries).

## <a name="access-query-language-documentation"></a>Documentatie voor Access-querytalen

Zie de [documentatie bij de querytaal van Kusto](https://docs.microsoft.com/azure/kusto/query/)voor meer informatie over Kusto querytaal en ondersteunde operatoren.

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
