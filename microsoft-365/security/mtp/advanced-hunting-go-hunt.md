---
title: Relevante informatie over een entiteit aanvragen met behulp van Go
description: Meer informatie over het gebruik van het hulpprogramma ' go go ' om snel de benodigde informatie over een entiteit of gebeurtenis te doorzoeken met behulp van geavanceerde jacht.
keywords: geavanceerde jacht, incident, Pivot, entiteit, zoeken, relevante evenementen, bedreigings jacht, Cyber Threat jacht, zoeken, query, telemetrie, Microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: e381793caf49318074bcd096e4301cdf49d12e88
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412188"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>Snel zoeken naar informatie over entiteiten of evenementen met Go Go

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

Met de actie *Go jacht* kunt u snel gebeurtenissen en verschillende entiteitstypen met [krachtige zoekfuncties op basis](advanced-hunting-overview.md) van query's. Met deze actie voert u automatisch een geavanceerde zoekopdracht uit om relevante informatie over de geselecteerde gebeurtenis of entiteit te zoeken.

De actie *Go* -actie is beschikbaar in diverse secties van het Beveiligingscentrum wanneer de details van een gebeurtenis of entiteit worden weergegeven. U kunt bijvoorbeeld de volgende secties gebruiken om te *zoeken* :

- Op de [pagina incident](investigate-incidents.md#incident-overview)kunt u Details bekijken van gebruikers, apparaten en vele andere entiteiten die aan een incident zijn gekoppeld. Wanneer u een entiteit selecteert, vindt u aanvullende informatie en verschillende acties die u kunt uitvoeren op die entitity. In het onderstaande voorbeeld is er een postvak geselecteerd, met details over het postvak en de optie om te zoeken naar meer informatie over het postvak.

    ![Afbeelding met details postvak met de optie Ga naar](../../media/mtp-ah/go-hunt-email.png)

- Op de pagina incidenten kunt u ook een lijst met entiteiten openen op het tabblad bewijs. Het selecteren van een van deze entiteiten biedt een mogelijkheid snel te zoeken naar informatie over die entiteit.

    ![Afbeelding van een geselecteerd bestand met de optie Ga naar het tabblad gegevens](../../media/mtp-ah/go-hunt-evidence-file.png)


- Wanneer u de tijdlijn voor een apparaat bekijkt, kunt u een gebeurtenis selecteren in de tijdlijn om aanvullende informatie over die gebeurtenis te bekijken. Als u een gebeurtenis hebt geselecteerd, kunt u de optie voor het zoeken naar andere relevante gebeurtenissen in de geavanceerde jacht.

    ![Afbeelding met gebeurtenisdetails met de optie Ga naar](../../media/mtp-ah/go-hunt-event.png)

Wanneer u **Ga start of zoeken** **naar gerelateerde gebeurtenissen** selecteert, worden andere query's uitgevoerd, afhankelijk van of u een entiteit of een gebeurtenis hebt geselecteerd.

## <a name="query-for-entity-information"></a>Query voor entiteits informatie
Wanneer u *Go* -zoekopdracht gebruikt om informatie te lezen over een gebruiker, apparaat of ander type entiteit, controleert de query alle relevante schema tabellen voor gebeurtenissen die betrekking hebben op die entiteit. Om de resultaten beheersbaar te houden, is de query in de loop van de vroegste periode in de afgelopen 30 dagen in de afgelopen 30 dagen voor de laatste 30 dagen die de entiteit omvat, in de afgelopen 30 dagen voor de laatste dertig dagen van de entiteit met het incident.

Hier ziet u een voorbeeld van de zoekopdracht Go voor een apparaat:

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
### <a name="supported-entity-types"></a>Ondersteunde entiteittypen
Wanneer u een van de volgende entiteittypen selecteert, kunt u de *overgaan* gebruiken.

- Bestanden
- Sturen
- E-mail clusters
- Postbus
- Gebruikers
- Apparaten
- IP-adressen
- URLs

## <a name="query-for-event-information"></a>Query voor informatie over gebeurtenissen
Wanneer u *Ga* naar de query voor het maken van een tijdlijn gaat, controleert de query alle relevante schema tabellen op andere gebeurtenissen over de tijd van de geselecteerde gebeurtenis. De volgende query bevat bijvoorbeeld een overzicht van gebeurtenissen in verschillende schema tabellen die in dezelfde periode plaatsvonden op hetzelfde apparaat:

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
Met enige kennis van de [querytaal](advanced-hunting-query-language.md)kunt u de query aanpassen aan uw voorkeur. U kunt bijvoorbeeld de volgende regel aanpassen om de grootte van het tijdvenster te bepalen:

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

Naast het wijzigen van de query om meer relevante resultaten te bereiken, kunt u ook het volgende doen:
- [Het resultaat weergeven als grafiek](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [Een aangepaste detectieregel maken](custom-detection-rules.md)

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Aangepaste detectieregels](custom-detection-rules.md)
