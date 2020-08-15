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
ms.openlocfilehash: aacbdf73da9552a12bde250e51544f1de533637c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695738"
---
# <a name="microsoft-365-network-assessment-preview"></a>Microsoft 365-netwerk beoordeling (preview)

In het Microsoft 365-Beheercentrum 365 kunt u met de **netwerk beoordelingen** een samenvatting van tal van de prestaties van de netwerkprestaties in een momentopname van uw Enterprise-netwerkstatus weergeven die wordt weergegeven door een punten waarde van 1-100. Netwerk beoordelingen zijn beperkt tot de gehele Tenant en voor elke geografische locatie van de gebruikers die verbinding maken met uw Tenant, zodat Microsoft 365-beheerders een eenvoudige manier is om een Gestalt van de netwerkstatus van de onderneming te begrijpt en snel een uitzoomen op een gedetailleerd overzicht van een wereldwijd kantoor.

De waarde van het netwerkbeoordelings punt is een gemiddelde tijdsinstelling voor latentie, bandbreedte, downloadsnelheid en hoeveelheid verbindingskwaliteit, gecompileerd Live op het moment dat ze worden bekeken. Prestatiegegevens voor Microsoft-netwerken zijn uitgesloten van deze waarden, om ervoor te zorgen dat de beoordelings resultaten ondubbelzinnig en specifiek zijn voor het bedrijfsnetwerk.

![Waarde van netwerk beoordeling](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

Een zeer lage waarde voor de beoordeling van een netwerk adviseert dat Microsoft 365-clients grote problemen hebben met de Tenant of de gebruikerservaring van een reactie houdt, terwijl een hoge waarde een correct geconfigureerd netwerk aangeeft met enkele voortdurende prestatieproblemen. Een waarde van 80% vertegenwoordigt een gezonde basislijn waarbij u geen normale klachten over de Microsoft 365-verbinding of-antwoord moet ontvangen vanwege de netwerkprestaties. Aangezien er steeds meer verbeteringen in de netwerkverbinding worden aangebracht, zal deze waarde toenemen samen met de gebruikerservaring.

>[!IMPORTANT]
>Netwerk inzichten, prestatie aanbevelingen en beoordelingen in het Microsoft 365-Beheercentrum is momenteel in de preview-versie en is alleen beschikbaar voor Microsoft 365-tenants die zijn geregistreerd in het functie voorbeeldprogramma.

## <a name="network-assessment-panel"></a>Deelvenster netwerk beoordeling

Elke beoordeling van een netwerk, of het bereik van de Tenant of een specifieke kantoorlocatie, een deelvenster toont met details over de beoordeling. Dit deelvenster toont een staafdiagram van de beoordeling, zowel als een percentage, als het totaal aantal punten voor elk onderdeel dat de hoeveelheid werkbelasting omvat, waaronder alleen werkbelastingen waarop meetgegevens zijn ontvangen. Voor een netwerklocatie netwerk beoordeling wordt ook een bench type weergegeven dat de mediaan is van alle Microsoft 365-clients die gegevens hebben gerapporteerd in dezelfde plaats als uw kantoorlocatie.

![Voorbeeld van netwerk beoordeling](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

In **het deelvenster analyse wordt** de beoordeling voor elk van de onderdelen van het onderdeel weergegeven.

De **beoordelings geschiedenis** toont de afgelopen 30 dagen van de beoordeling en de benchte.

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>Inspecties van Tenant netwerkbeoordelingen en netwerk beoordelingen van Office-locaties

Een netwerkbeoordeling meet de opzet van de netwerkverbinding van een kantoorlocatie naar het netwerk van Microsoft. De verbeteringen aan de netwerkverbinding kunt u het beste uitvoeren op elke kantoorlocatie, of als de netwerkverbinding is geaggregeerd, zijn er mogelijk verbeteringen die van invloed zijn op meerdere locaties.

We tonen een netwerkassessmentwaarde voor de gehele Microsoft 365-Tenant op de pagina netwerkprestaties en een specifieke waarde voor elke gedetecteerde Office-locatie op de samenvattings pagina van die locatie.

## <a name="exchange-online"></a>Exchange Online

Voor Exchange Online wordt de TCP-latentie van de clientcomputer naar de front-end-server van Exchange gemeten. Dit kan van invloed zijn op de afstand tussen het netwerk en het LAN en WAN van klanten. Het kan ook worden beïnvloed door de netwerk-of bewerkings apparatuur of de service die de verbinding vertraagt of dat pakketten worden verzonden.

## <a name="sharepoint-online"></a>SharePoint Online

Voor SharePoint Online is de beschikbare downloadsnelheid voor een gebruiker voor toegang tot een document gemeten. Dit kan van invloed zijn op de bandbreedte voor netwerk circuits van de clientcomputer en van het Microsoft-netwerk. Dit wordt vaak beïnvloed door netwerkcongestie die zich bevindt bij knelpunten in ingewikkelde netwerkapparaten of in de WiFi-gebieden met weinig behoefte.

## <a name="microsoft-teams"></a>Microsoft Teams

De netwerkkwaliteit voor Microsoft teams wordt gemeten als UDP-latentie, UDP-jitter en UDP-pakketverlies. UDP wordt gebruikt voor bellen en vergaderen via audio-en videoverbinding voor Microsoft teams. Dit kan van invloed zijn op het moment dat de latentie en de downloadsnelheid van invloed zijn op de latentie en de downloadsnelheid, aangezien UDP voor de ondersteuning van de UDP apart is geconfigureerd voor het meer gangbare TCP-protocol.

## <a name="related-topics"></a>Verwante onderwerpen

[Aanbevelingen voor netwerkprestaties in het Microsoft 365-Beheercentrum (preview)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Network Performance Insights (preview)](office-365-network-mac-perf-insights.md)

[Microsoft 365 connectiviteitstest in het M365-Beheercentrum (preview)](office-365-network-mac-perf-onboarding-tool.md)

[Locatie Services voor Microsoft 365-netwerkconnectiviteit](office-365-network-mac-location-services.md)
