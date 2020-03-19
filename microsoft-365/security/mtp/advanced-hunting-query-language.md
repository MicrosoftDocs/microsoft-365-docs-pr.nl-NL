---
title: Meer informatie over de geavanceerde zoekquerytaal in Microsoft Threat Protection
description: Maak uw eerste jachtquery voor bedreigingen en leer meer over veelvoorkomende operators en andere aspecten van de geavanceerde jachtquerytaal
keywords: geavanceerde jacht, bedreigingjacht, cyberdreigingsjacht, microsoft threat protection, microsoft 365, mtp, m365, search, query, taal, leren, eerste query, telemetrie, evenementen, telemetrie, aangepaste detecties, schema, kusto, operators, gegevenstypen, powershell downloaden, query voorbeeld
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
ms.openlocfilehash: 7f2cf7f62060774343354467d27b76456f6581fc
ms.sourcegitcommit: cc3b64a91e16ccdaa9c338b9a9056dbe3963ba9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/09/2020
ms.locfileid: "42809189"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Meer informatie over de geavanceerde jachtquerytaal

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging

Geavanceerde jacht is gebaseerd op de [Kusto query taal](https://docs.microsoft.com/azure/kusto/query/). U kusto-syntaxis en operators gebruiken om query's te maken die informatie vinden in het [schema](advanced-hunting-schema-tables.md) dat specifiek is gestructureerd voor geavanceerde jacht. Voer uw eerste query uit om deze concepten beter te begrijpen.

## <a name="try-your-first-query"></a>Probeer uw eerste query

Ga in microsoft 365-beveiligingscentrum naar **Jagen** om uw eerste query uit te voeren. Gebruik het volgende voorbeeld:

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

Zo zal het eruit zien in de geavanceerde jacht.

![Afbeelding van geavanceerde jachtquery Microsoft Threat Protection](../../media/advanced-hunting-query-example.png)

Een korte opmerking is toegevoegd aan het begin van de query om te beschrijven waar het voor is. Dit helpt als u later besluit de query op te slaan en te delen met anderen in uw organisatie. 

```kusto
// Finds PowerShell execution events that could involve a download
```

De query zelf begint meestal met een tabelnaam, gevolgd door`|`een reeks elementen die zijn gestart door een pipe ( ). In dit voorbeeld beginnen we met het `DeviceProcessEvents` maken `DeviceNetworkEvents`van een unie van twee tabellen en voegen we indien nodig piped-elementen toe.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
Het eerste piped-element is een tijdfilter dat is gescoped tot de voorgaande zeven dagen. Het tijdsbereik zo beperkt mogelijk houden, zorgt ervoor dat query's goed presteren, beheersbare resultaten retourneren en geen time-out hebben.

```kusto
| where Timestamp > ago(7d)
```

Het tijdsbereik wordt onmiddellijk gevolgd door een zoekopdracht naar procesbestandsnamen die de PowerShell-toepassing vertegenwoordigen.

```
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

Daarna wordt in de query gezocht naar tekenreeksen in opdrachtregels die doorgaans worden gebruikt om bestanden te downloaden met PowerShell.

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
Nu uw query duidelijk de gegevens identificeert die u wilt zoeken, u elementen toevoegen die bepalen hoe de resultaten eruit zien. `project`retourneert `top` specifieke kolommen en beperkt het aantal resultaten, waardoor de resultaten goed geformatteerd en redelijk groot en gemakkelijk te verwerken zijn.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Klik op **Query uitvoeren** om de resultaten weer te geven. Selecteer het pictogram Uitvouwen rechtsboven in de queryeditor om u te concentreren op uw jachtquery en de resultaten.

![Afbeelding van de besturingselement Uitbreiden in de geavanceerde jachtqueryeditor](../../media/advanced-hunting-expand.png)

## <a name="learn-common-query-operators-for-advanced-hunting"></a>Meer informatie over veelvoorkomende queryoperators voor geavanceerde jacht

Nu u uw eerste query hebt uitgevoerd en een algemeen idee hebt van de componenten ervan, is het tijd om een beetje terug te krabbelen en een aantal basisprincipes te leren. De Kusto-querytaal die wordt gebruikt door geavanceerde jacht ondersteunt een reeks operatoren, waaronder de volgende veelvoorkomende.

| Operator | Beschrijving en gebruik |
|--|--|
| `where` | Filter een tabel naar de subset van rijen die voldoen aan een predicaat. |
| `summarize` | Een tabel maken die de inhoud van de invoertabel samenvoegt. |
| `join` | Voeg de rijen van twee tabellen samen om een nieuwe tabel te vormen door waarden van de opgegeven kolom(en) van elke tabel te matchen. |
| `count` | Retourneer het aantal records in de invoerrecordset. |
| `top` | De eerste N-records retourneren die zijn gesorteerd op de opgegeven kolommen. |
| `limit` | Terug naar het opgegeven aantal rijen. |
| `project` | Selecteer de kolommen die u wilt opnemen, wijzig de naam of neerzet en voeg nieuwe berekende kolommen in. |
| `extend` | Maak berekende kolommen en appze toe aan de resultaatset. |
| `makeset` |  Retourneer een dynamische (JSON) array van de set van verschillende waarden die Expr in de groep neemt. |
| `find` | Zoek rijen die overeenkomen met een predicaat in een set tabellen. |

Om een live voorbeeld van deze operators te zien, voer ze uit vanaf de sectie **Aan de slag** in geavanceerde jacht.

## <a name="understand-data-types-and-their-query-syntax-implications"></a>Gegevenstypen en de implicaties van de querysyntaxis begrijpen

Gegevens in geavanceerde jachttabellen worden over het algemeen ingedeeld in de volgende gegevenstypen.

| Gegevenstype | Implicaties beschrijving en query |
|--|--|
| `datetime` | Gegevens en tijdsinformatie die doorgaans tijdstempels van gebeurtenissen vertegenwoordigen |
| `string` | Tekentekenreeks |
| `bool` | Waar of onwaar |
| `int` | 32-bits numerieke waarde  |
| `long` | 64-bits numerieke waarde |

## <a name="use-sample-queries"></a>Voorbeeldquery's gebruiken

De sectie **Aan de slag** biedt een paar eenvoudige query's met veelgebruikte operators. Probeer deze query's uit te voeren en kleine wijzigingen aan te brengen.

![Beeld van geavanceerd jachtvenster](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>Naast de basisqueryvoorbeelden hebt u ook toegang tot [gedeelde query's](advanced-hunting-shared-queries.md) voor specifieke scenario's voor het jagen op bedreigingen. Bekijk de gedeelde query's aan de linkerkant van de pagina of de GitHub-queryrepository.

## <a name="access-query-language-documentation"></a>Documentatie voor querytaal openen

Zie [Kusto-querytaaldocumentatie](https://docs.microsoft.com/azure/kusto/query/)voor meer informatie over Kusto-querytaal en ondersteunde operatoren.

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief jagen op bedreigingen](advanced-hunting-overview.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Op zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Het schema begrijpen](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
