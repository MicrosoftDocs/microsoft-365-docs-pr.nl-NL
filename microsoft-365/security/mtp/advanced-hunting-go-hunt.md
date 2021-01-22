---
title: Krijg relevante informatie over een entiteit met zoeken
description: Meer informatie over het gebruik van het hulpprogramma voor zoeken naar onderweg om snel te zoeken naar relevante informatie over een entiteit of gebeurtenis met behulp van geavanceerd zoeken.
keywords: advanced hunt, incident, pivot, entity, go hunt, relevant events, threat hunt, cyber threat hunt, search, query, telemetry, Microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: 9e707fe8b3dff40d0698630cd0592b297042e5fb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929503"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>Snel zoeken naar entiteits- of gebeurtenisgegevens met zoeken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Met de *zoekactie kunt* u snel gebeurtenissen en verschillende entiteitstypen onderzoeken met behulp van krachtige geavanceerde zoekmogelijkheden op basis van query's. [](advanced-hunting-overview.md) Met deze actie wordt automatisch een geavanceerde zoekquery uitgevoerd om relevante informatie over de geselecteerde gebeurtenis of entiteit te vinden.

De *zoekactie* is beschikbaar in verschillende secties van het beveiligingscentrum wanneer details van gebeurtenissen of entiteiten worden weergegeven. U kunt bijvoorbeeld zoeken in *de* volgende secties:

- Op de [incidentpagina](investigate-incidents.md#incident-overview)kunt u details bekijken over gebruikers, apparaten en vele andere entiteiten die aan een incident zijn gekoppeld. Als u een entiteit selecteert, krijgt u aanvullende informatie en verschillende acties die u op die entiteit kunt uitvoeren. In het onderstaande voorbeeld is een postvak geselecteerd, met informatie over het postvak en de optie om te zoeken naar meer informatie over het postvak.

    ![Afbeelding met postvakdetails met de optie voor zoeken naar onderweg](../../media/mtp-ah/go-hunt-email.png)

- Op de pagina met incidenten kunt u ook een lijst met entiteiten openen op het tabblad Bewijs. Als u een van deze entiteiten selecteert, kunt u snel zoeken naar informatie over die entiteit.

    ![Afbeelding van geselecteerd bestand met de optie Zoeken naar onderweg op het tabblad Bewijs](../../media/mtp-ah/go-hunt-evidence-file.png)


- Wanneer u de tijdlijn van een apparaat bekijkt, kunt u een gebeurtenis selecteren in de tijdlijn om aanvullende informatie over die gebeurtenis weer te geven. Wanneer een gebeurtenis is geselecteerd, krijgt u de mogelijkheid om te zoeken naar andere relevante gebeurtenissen in geavanceerd zoeken.

    ![Afbeelding met gebeurtenisdetails met de optie om te zoeken](../../media/mtp-ah/go-hunt-event.png)

Als **u Zoeken naar** of Zoeken naar gerelateerde **gebeurtenissen** selecteert, worden verschillende query's doorstaat, afhankelijk van of u een entiteit of gebeurtenis hebt geselecteerd.

## <a name="query-for-entity-information"></a>Query voor entiteitsinformatie
Wanneer u *zoeken gebruikt om* te zoeken naar informatie over een gebruiker, apparaat of ander type entiteit, controleert de query alle relevante schematabellen op gebeurtenissen die betrekking hebben op die entiteit. Om de resultaten beheersbaar te houden, heeft de query een bereik van ongeveer dezelfde periode als de eerste activiteit in de afgelopen 30 dagen waarbij de entiteit betrokken is en is gerelateerd aan het incident.

Hier is een voorbeeld van de zoekquery voor een apparaat:

```kusto
let selectedTimestamp = datetime(2020-06-02T02:06:47.1167157Z);
let deviceName = "fv-az770.example.com";
let deviceId = "device-guid";
search in (DeviceLogonEvents, DeviceProcessEvents, DeviceNetworkEvents, DeviceFileEvents, DeviceRegistryEvents, DeviceImageLoadEvents, DeviceEvents, DeviceImageLoadEvents, IdentityLogonEvents, IdentityQueryEvents)
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
and DeviceName == deviceName
// or RemoteDeviceName == deviceName
// or DeviceId == deviceId
| take 100
```
### <a name="supported-entity-types"></a>Ondersteunde entiteitstypen
U kunt zoeken *gebruiken nadat* u een van deze entiteitstypen hebt geselecteerd:

- Bestanden
- E-mailberichten
- E-mailclusters
- Postvakken
- Gebruikers
- Apparaten
- IP-adressen
- URL's

## <a name="query-for-event-information"></a>Query voor gebeurtenisgegevens
Wanneer u *zoeken gebruikt om* te zoeken naar informatie over een tijdlijngebeurtenis, controleert de query alle relevante schematabellen op andere gebeurtenissen rond de tijd van de geselecteerde gebeurtenis. De volgende query bevat bijvoorbeeld gebeurtenissen in verschillende schematabellen die hebben plaatsgevonden rond dezelfde periode op hetzelfde apparaat:

```kusto
// List relevant events 30 minutes before and after selected LogonAttempted event
let selectedEventTimestamp = datetime(2020-06-04T01:29:09.2496688Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "079ecf9c5798d249128817619606c1c47369eb3e"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a>De query aanpassen
Met enige kennis van de [querytaal](advanced-hunting-query-language.md)kunt u de query aan uw voorkeur aanpassen. U kunt bijvoorbeeld deze regel aanpassen, die de grootte van het tijdvenster bepaalt:

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

Naast het wijzigen van de query om relevantere resultaten te krijgen, kunt u ook:
- [De resultaten weergeven als grafieken](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [Een aangepaste detectieregel maken](custom-detection-rules.md)

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Aangepaste detectieregels](custom-detection-rules.md)
