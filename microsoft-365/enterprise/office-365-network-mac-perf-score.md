---
title: Microsoft 365-netwerk beoordeling (preview)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365-netwerk beoordeling (preview)
ms.openlocfilehash: 15eb514980bb53bd32380e44b6bfa174670f6b85
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948313"
---
# <a name="microsoft-365-network-assessment-preview"></a>Microsoft 365-netwerk beoordeling (preview)

In het Microsoft 365-Beheercentrum 365 kunt u met de **netwerk beoordelingen** een samenvatting van diverse netwerkprestatieswaarde waarden omzetten in een momentopname van de status van de netwerkverbinding van uw onderneming, aangeduid met een punten waarde van 0-100. Netwerk beoordelingen zijn beperkt tot de gehele Tenant en voor elke geografische locatie van de gebruikers die verbinding maken met uw Tenant, zodat Microsoft 365-beheerders een eenvoudige manier is om een Gestalt van de netwerkstatus van de onderneming te begrijpt en snel een uitzoomen op een gedetailleerd overzicht van een wereldwijd kantoor.

De waarde van het netwerkassessment Points is een gemiddelde waarde voor de TCP-latentie, de downloadsnelheid en UDP-verbindingskwaliteit gecompileerde Live op het moment dat ze worden bekeken. Prestatiegegevens voor Microsoft-netwerken zijn uitgesloten van deze waarden, om ervoor te zorgen dat de beoordelings resultaten ondubbelzinnig en specifiek zijn voor het bedrijfsnetwerk.

![Waarde van netwerk beoordeling](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

Een zeer lage waarde voor de beoordeling van een netwerk adviseert dat Microsoft 365-clients grote problemen hebben met de Tenant of de gebruikerservaring van een reactie houdt, terwijl een hoge waarde een correct geconfigureerd netwerk aangeeft met enkele voortdurende prestatieproblemen. Een waarde van 80% vertegenwoordigt een gezonde basislijn waarbij u geen normale klachten over de Microsoft 365-verbinding of-antwoord moet ontvangen vanwege de netwerkprestaties. Aangezien er steeds meer verbeteringen in de netwerkverbinding worden aangebracht, zal deze waarde toenemen samen met de gebruikerservaring.

>[!IMPORTANT]
>Netwerk inzichten, prestatie aanbevelingen en beoordelingen in het Microsoft 365-Beheercentrum is momenteel in de preview-versie en is alleen beschikbaar voor Microsoft 365-tenants die zijn geregistreerd in het functie voorbeeldprogramma.

## <a name="network-assessment-panel"></a>Deelvenster netwerk beoordeling

Elke beoordeling van een netwerk, of het bereik van de Tenant of een specifieke kantoorlocatie, een deelvenster toont met details over de beoordeling. Dit deelvenster toont een staafdiagram van de beoordeling, zowel als een percentage, als het totaal aantal punten voor elk onderdeel dat de hoeveelheid werkbelasting omvat, waaronder alleen werkbelastingen waarop meetgegevens zijn ontvangen. Voor een netwerklocatie netwerk beoordeling wordt ook een bench type weergegeven dat de mediaan is van alle Microsoft 365-clients die gegevens hebben gerapporteerd in dezelfde plaats als uw kantoorlocatie.

![Voorbeeld van netwerk beoordeling](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

In **het deelvenster analyse wordt** de beoordeling voor elk van de onderdelen van het onderdeel weergegeven.

De **beoordelings geschiedenis** toont de afgelopen 30 dagen van de beoordeling en de benchte. Met behulp van het tabblad geschiedenis kunt u ook rapporten maken over de metrische geschiedenis van de Office-locaties van maximaal twee jaar.

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>Inspecties van Tenant netwerkbeoordelingen en netwerk beoordelingen van Office-locaties

Een netwerkbeoordeling meet de opzet van de netwerkverbinding van een kantoorlocatie naar het netwerk van Microsoft. De verbeteringen aan de netwerkverbinding kunt u het beste uitvoeren op elke kantoorlocatie, of als de netwerkverbinding is geaggregeerd, zijn er mogelijk verbeteringen die van invloed zijn op meerdere locaties.

We tonen een netwerkassessmentwaarde voor de gehele Microsoft 365-Tenant op de pagina netwerkprestaties en een specifieke waarde voor elke gedetecteerde Office-locatie op de samenvattings pagina van die locatie.

## <a name="exchange-online"></a>Exchange Online

Voor Exchange Online wordt de TCP-latentie van de clientcomputer naar de front-end-server van Exchange gemeten. Dit kan van invloed zijn op de afstand tussen het netwerk en het LAN en WAN van klanten. Het kan ook worden beïnvloed door de netwerk-of bewerkings apparatuur of de service die de verbinding vertraagt of dat pakketten worden verzonden. De mediaan (ook wel het 50e percentiel of de P50 maat) wordt voor alle maten van de afgelopen drie dagen genomen.

De analyse van Exchange Online wordt uitgevoerd met behulp van de volgende tabel. Elk TCP-latentie nummer tussen de drempelwaarden wordt in de band lineair toegewezen aan punten.

| TCP-latentie   | Distributiepunten |
| :------------ | :----- |
| 10 MS of minder  | 100    |
| 25ms          | 80     |
| 100 MS         | 60     |
| 200ms         | 40     |
| 300ms         | Maxi     |
| 350ms of meer | 0      |

## <a name="sharepoint-online"></a>SharePoint Online

Voor SharePoint Online is de beschikbare downloadsnelheid voor een gebruiker om toegang te krijgen tot een document via SharePoint Online of OneDrive gemeten. Dit kan van invloed zijn op de bandbreedte voor netwerk circuits van de clientcomputer en van het Microsoft-netwerk. Dit wordt vaak beïnvloed door netwerkcongestie die zich bevindt bij knelpunten in ingewikkelde netwerkapparaten of in de WiFi-gebieden met weinig behoefte. De downloadsnelheid wordt gemeten in megabytes per seconde en is ongeveer een tiende van een circuits met een classificatie van megabits per seconde. Het 25e percentiel (ook wel bekend als P25 meetwaarde) wordt gebruikt voor alle maten van de afgelopen drie dagen.

De beoordeling van SharePoint Online wordt uitgevoerd in de volgende tabel. Elk Download snelheids nummer tussen de drempelwaarden wordt in de band lineair toegewezen.

| Download snelheid | Distributiepunten |
| :------------- | :----- |
| 20MBps of meer | 100    |
| 14MBps         | 80     |
| 8MBps          | 60     |
| 4 Mbps          | 40     |
| 2MBps          | Maxi     |
| 0MBps          | 0      |

## <a name="microsoft-teams"></a>Microsoft Teams

De netwerkkwaliteit voor Microsoft teams wordt gemeten als UDP-latentie, UDP-jitter en UDP-pakketverlies. UDP wordt gebruikt voor bellen en vergaderen via audio-en videoverbinding voor Microsoft teams. Dit kan van invloed zijn op het moment dat de latentie en de downloadsnelheid van invloed zijn op de latentie en de downloadsnelheid, aangezien UDP voor de ondersteuning van de UDP apart is geconfigureerd voor het meer gangbare TCP-protocol. De mediaan (ook wel het 50e percentiel of de P50 maat) wordt voor alle maten van de afgelopen drie dagen genomen. 

De beoordeling van Microsoft teams wordt uitgevoerd in de volgende tabel. Alle drie de UDP-meetwaarden moeten hoger zijn dan de drempelwaarde voor het bereiken van de punten die worden weergegeven. Er zijn geen Beoordelingen voor één locatie binnen een band.

| UDP-pakketverlies | UDP-latentie | UDP-jitter | Distributiepunten |
| :-------------- | :---------- | :--------- | :----- |
| 0,25%           | 60ms        | 15ms       | 100    |
| 1,00%           | 120ms       | 40 MS       | 80     |
| 1,50%           | 240ms       | 65ms       | 60     |
| 3,00%           | 275ms       | 80ms       | 40     |
| 5,00%           | 350ms       | 150ms      | Maxi     |
| Een groter      | Een groter  | Een groter | 0      |

## <a name="related-topics"></a>Verwante onderwerpen

[Aanbevelingen voor netwerkprestaties in het Microsoft 365-Beheercentrum (preview)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Network Performance Insights (preview)](office-365-network-mac-perf-insights.md)

[Microsoft 365 connectiviteitstest in het M365-Beheercentrum (preview)](office-365-network-mac-perf-onboarding-tool.md)

[Locatie Services voor Microsoft 365-netwerkconnectiviteit](office-365-network-mac-location-services.md)
