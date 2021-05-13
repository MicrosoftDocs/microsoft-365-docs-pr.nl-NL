---
title: Microsoft 365 netwerkbeoordeling
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 netwerkbeoordeling
ms.openlocfilehash: c09e34b1bc3a8bf0f82a4a1e3c72e67f320abd43
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470472"
---
# <a name="microsoft-365-network-assessment"></a>Microsoft 365 netwerkbeoordeling

In de Microsoft 365 netwerkconnectiviteit van het beheercentrum **worden** in netwerkbeoordelingen een aggregatie van veel meetwaarden voor netwerkprestaties gedestilleerd tot een momentopname van de perimetertoestand van het bedrijfsnetwerk. Een netwerkbeoordeling laat zien hoeveel het verantwoordelijke netwerkontwerp van de klant van invloed is op Office 365 gebruikerservaring. Netwerkbeoordelingen zijn zowel voor de gehele tenant als voor elke geografische locatie waaruit gebruikers verbinding maken met uw tenant. De beoordelingen bieden Microsoft 365 beheerders een eenvoudige manier om direct inzicht te krijgen in de netwerktoestand van de onderneming en snel in te zoomen op een gedetailleerd rapport voor elke globale kantoorlocatie.

De waarde voor netwerkbeoordelingspunten is 0 tot 100 en is een gemiddelde van TCP-latentie, downloadsnelheid en UDP-verbindingskwaliteitsgegevens. Deze metrische gegevens worden eenmaal per dag gecompileerd. Prestatiemetrische gegevens voor netwerken die eigendom zijn van Microsoft worden uitgesloten van deze metingen om ervoor te zorgen dat de beoordelingsresultaten ondubbelzinnig en specifiek zijn voor het bedrijfsnetwerk.

> [!div class="mx-imgBorder"]
> ![Waarde voor netwerkbeoordeling](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

Een zeer lage netwerkbeoordelingswaarde suggereert dat Microsoft 365 klanten aanzienlijke problemen zullen hebben met het maken van verbinding met de tenant of het onderhouden van een responsieve gebruikerservaring. Een hoge waarde geeft een goed geconfigureerd netwerk aan met weinig lopende prestatieproblemen. Een waarde van 80% vertegenwoordigt een gezonde basislijn, waarboven u niet verwacht dat u regelmatig klachten van gebruikers ontvangt over Microsoft 365 verbinding of reactiesnelheid als gevolg van netwerkprestaties. Naarmate er verbeteringen in de iteratieve netwerkconnectiviteit worden aangebracht, wordt deze waarde samen met de gebruikerservaring groter.

| Netwerkbeoordeling | Verwachte gebruikerservaring |
| :----------------- | :----------------------- |
| 100                | Beste                     |
| 80                 | Voldoet aan aanbevelingen    |
| 60                 | Aanvaardbaar               |
| 40                 | Gebruikers kunnen problemen ervaren |
| 20                 | Gebruikers kunnen een klacht indienen       |
| 0                  | Netwerkproblemen een veelvoorkomende discussie |

>[!IMPORTANT]
>Netwerkinzichten, prestatieaanbevelingen en evaluaties in het Microsoft 365-beheercentrum hebben momenteel de preview-status en zijn alleen beschikbaar voor Microsoft 365-tenants die zijn geregistreerd voor het functievoorbeeldprogramma.

## <a name="network-assessment-panel"></a>Netwerkbeoordelingspaneel

Elke netwerkbeoordeling, ongeacht of deze is beperkt tot de tenant of naar een specifieke kantoorlocatie, toont een paneel met details over de beoordeling. In dit deelvenster ziet u een staafdiagram van de beoordeling als percentage en als het totaal aantal punten voor elke werkbelasting van onderdelen, inclusief alleen werkbelastingen waar meetgegevens zijn ontvangen. Voor een netwerkbeoordeling van een kantoorlocatie wordt ook een vergelijking vergeleken met het percentage Microsoft 365 klanten in elk van de vijf kwintielen die gegevens hebben gerapporteerd in dezelfde plaats als uw kantoorlocatie.

> [!div class="mx-imgBorder"]
> ![Voorbeeld van netwerkbeoordelingswaarde](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

De **uitsplitsing Beoordeling** in het deelvenster toont de beoordeling voor elk van de werkbelastingen van de onderdelen.

De **evaluatiegeschiedenis toont** de afgelopen 30 dagen van de beoordeling en de benchmark. U kunt ook rapporteren over de metrische geschiedenis voor elke kantoorlocatie voor maximaal twee jaar met behulp van het tabblad Geschiedenis. Op het tabblad Geschiedenis kunt u uw kenmerken selecteren waarmee u wilt rapporteren. Door een rapporttijdkader te kiezen, kunt u de impact van een netwerkupdateproject markeren en de verbetering van uw netwerkbeoordeling bekijken.

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>Tenantnetwerkbeoordelingen en netwerkbeoordelingen op kantoorlocatie

Een netwerkbeoordeling meet het ontwerp van de netwerkperimeter van een kantoorlocatie naar het netwerk van Microsoft. Verbeteringen aan de netwerkperimeter kunnen het beste op elke kantoorlocatie worden uitgevoerd.

We geven een netwerkbeoordelingswaarde weer voor de Microsoft 365 tenant op de pagina overzicht van netwerkprestaties. Deze waarde is een gewogen gemiddelde van de netwerkbeoordelingen voor alle kantoorlocaties. Er is ook een specifieke waarde voor netwerkbeoordeling voor elke gedetecteerde kantoorlocatie op de overzichtspagina van die locatie.

## <a name="exchange-online"></a>Exchange Online

Voor Exchange Online wordt de TCP-latentie van de clientmachine naar de Exchange servicedeuren gemeten. Deze latentie kan worden beïnvloed door de afstand die het netwerk over het LAN en WAN van klanten aflegt. Het kan ook worden beïnvloed door netwerktussenliggende apparaten of services, waardoor de verbinding wordt vertraagd of pakketten worden verbolgen. En het wordt beïnvloed door hoe ver weg de dichtstbijzijnde Exchange de servicedeuren is. De mediaan (ook wel de 50e percentiel- of P50-meting genoemd) wordt gebruikt voor alle metingen in de afgelopen drie dagen.

De Exchange Online wordt uitgevoerd met behulp van de volgende tabel. Aan een TCP-latentienummer tussen de drempelwaarden worden lineaire punten toegewezen binnen de band.

| TCP-latentie   | Punten |
| :------------ | :----- |
| 10 ms of minder  | 100    |
| 25 ms          | 80     |
| 100 ms         | 60     |
| 200 ms         | 40     |
| 300 ms         | 20     |
| 350 ms of meer | 0      |

## <a name="sharepoint-online"></a>SharePoint Online

Voor SharePoint Online wordt de downloadsnelheid gemeten die beschikbaar is voor een gebruiker om toegang te krijgen tot een document SharePoint of OneDrive. Dit kan worden beïnvloed door de bandbreedte die beschikbaar is op netwerkcircuits tussen de clientmachine en het netwerk van Microsoft. Het wordt ook vaak beïnvloed door netwerkcongestie die bestaat in knelpunten in complexe netwerkapparaten of in een slechte dekking Wi-Fi gebieden. De downloadsnelheid wordt gemeten in megabytes per seconde, wat ongeveer een tiende is van een circuits met een megabit per seconde. De eenheid MegaByte per seconde is handig omdat u direct kunt zien welke groottebestand in 1 seconde kan worden gedownload. Het 25e percentiel (ook wel bekend als de P25-meting) wordt genomen voor alle metingen in de afgelopen drie dagen. Dit 25e percentiel helpt de impact van verschillende congestie in de tijd te verminderen.

De SharePoint Online wordt uitgevoerd met behulp van de volgende tabel. Aan elk downloadsnelheidsnummer tussen de drempelwaarden worden lineaire punten toegewezen binnen de band.

| Downloadsnelheid | Punten |
| :------------- | :----- |
| 20MBps of meer | 100    |
| 14MBps         | 80     |
| 8MBps          | 60     |
| 4MBps          | 40     |
| 2MBps          | 20     |
| 0MBps          | 0      |

## <a name="microsoft-teams"></a>Microsoft Teams

Voor Microsoft Teams wordt de netwerkkwaliteit gemeten als UDP-latentie, UDP jitter en UDP-pakketverlies. UDP wordt gebruikt voor audio- en videomediaconnectiviteit voor bellen en Microsoft Teams. Dit kan worden beïnvloed door dezelfde factoren als voor latentie en downloadsnelheid, naast de connectiviteitshiaten in de UDP-ondersteuning van een netwerk, aangezien UDP afzonderlijk is geconfigureerd voor het veelgebruikte TCP-protocol. De mediaan (ook wel de 50e percentiel- of P50-meting genoemd) wordt gebruikt voor alle metingen in de afgelopen drie dagen. 

We berekenen een gemiddelde adviesscore van deze UDP-metingen voor een schaal van één tot vijf. Vervolgens wordt dit in kaart gebracht op de schaal 0-100 punten voor de Microsoft Teams netwerkbeoordeling.  Algemeen goed is meer dan 87,5 punten en over het algemeen is slecht minder dan 50 punten.

## <a name="related-topics"></a>Verwante onderwerpen

[Netwerkconnectiviteit in het Microsoft 365 beheercentrum (voorbeeld)](office-365-network-mac-perf-overview.md)

[Microsoft 365 netwerkprestatieinzichten (voorbeeld)](office-365-network-mac-perf-insights.md)

[Microsoft 365 testprogramma voor netwerkconnectiviteit (voorbeeld)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location Services (preview)](office-365-network-mac-location-services.md)
