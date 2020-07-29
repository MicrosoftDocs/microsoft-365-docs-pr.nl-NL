---
title: Krijg relevante informatie over een entiteit met go hunt
description: Meer informatie over het gebruik van de tool 'go hunt' om snel relevante informatie over een entiteit of gebeurtenis te zoeken met behulp van geavanceerde jacht.
keywords: geavanceerde jacht, incident, pivot, entiteit, gaan jagen, relevante gebeurtenissen, bedreiging jacht, cyber bedreiging jacht, zoeken, query, telemetrie, Microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: b9afecb3d0efce93ae5d5725bba71d8d9719d17f
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430409"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>Snel op zoek naar entiteits- of evenementinformatie met go hunt

**Van toepassing op:**
- Microsoft Threat Protection

Met de *go hunt-actie* u gebeurtenissen en verschillende entiteitstypen snel onderzoeken met behulp van krachtige op query gebaseerde [geavanceerde jachtmogelijkheden.](advanced-hunting-overview.md) Met deze actie wordt automatisch een geavanceerde jachtquery uitgevoerd om relevante informatie over de geselecteerde gebeurtenis of entiteit te vinden.

De *actie Go Hunt* is beschikbaar in verschillende delen van het beveiligingscentrum wanneer gebeurtenis- of entiteitsgegevens worden weergegeven. U bijvoorbeeld *go hunt* gebruiken vanuit de volgende secties:

- Op de [incidentpagina](investigate-incidents.md#incident-overview)u details bekijken over gebruikers, apparaten en vele andere entiteiten die aan een incident zijn gekoppeld. Als u een entiteit selecteert, krijgt u aanvullende informatie en verschillende acties die u op die entitity uitvoeren. In het onderstaande voorbeeld wordt een postvak geselecteerd, waarin details over het postvak worden weergegeven en de optie om te zoeken naar meer informatie over het postvak.

    ![Afbeelding met postvakdetails met de optie Go Hunt](../../media/mtp-ah/go-hunt-email.png)

- Op de incidentpagina u ook toegang krijgen tot een lijst met entiteiten onder het tabblad Bewijs. Het selecteren van een van deze entiteiten biedt een optie om snel te zoeken naar informatie over die entiteit.

    ![Afbeelding met geselecteerd bestand met de optie Go Hunt op het tabblad Bewijs](../../media/mtp-ah/go-hunt-evidence-file.png)


- Wanneer u de tijdlijn voor een apparaat bekijkt, u een gebeurtenis in de tijdlijn selecteren om aanvullende informatie over die gebeurtenis weer te geven. Zodra een evenement is geselecteerd, krijg je de mogelijkheid om te jagen voor andere relevante gebeurtenissen in geavanceerde jacht.

    ![Afbeelding met gebeurtenisdetails met de optie go hunt](../../media/mtp-ah/go-hunt-event.png)

Als u **Ga hunt** of Hunt voor **gerelateerde gebeurtenissen** selecteert, worden verschillende query's doorstaan, afhankelijk van of u een entiteit of een gebeurtenis hebt geselecteerd.

## <a name="query-for-entity-information"></a>Query voor entiteitsgegevens
Wanneer u *go hunt* gebruikt om informatie over een gebruiker, apparaat of een ander type entiteit op te vragen, controleert de query alle relevante schematabellen op gebeurtenissen waarbij die entiteit betrokken is. Om de resultaten beheersbaar te houden, wordt de query beperkt tot ongeveer dezelfde periode als de vroegste activiteit in de afgelopen 30 dagen waarbij de entiteit betrokken is en is gekoppeld aan het incident.

Hier is een voorbeeld van de go hunt query voor een apparaat:

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
U *go hunt* gebruiken nadat u een van deze entiteitstypen hebt geselecteerd:

- Bestanden
- E-mails
- E-mailclusters
- Postvakken
- Gebruikers
- Apparaten
- IP-adressen
- Urls

## <a name="query-for-event-information"></a>Query voor gebeurtenisgegevens
Wanneer u *go hunt* gebruikt om informatie over een tijdlijngebeurtenis op te vragen, controleert de query alle relevante schematabellen voor andere gebeurtenissen rond het tijdstip van de geselecteerde gebeurtenis. In de volgende query worden bijvoorbeeld gebeurtenissen weergegeven in verschillende schematabellen die zich rond dezelfde periode op hetzelfde apparaat hebben voorgedaan:

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
Met enige kennis van de [querytaal](advanced-hunting-query-language.md)u de query aanpassen aan uw voorkeur. U deze regel bijvoorbeeld aanpassen, die de grootte van het tijdvenster bepaalt:

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

Naast het wijzigen van de query om relevantere resultaten te krijgen, u ook:
- [Bekijk de resultaten als grafieken](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [Een aangepaste detectieregel maken](custom-detection-rules.md)

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Aangepaste detectieregels](custom-detection-rules.md)