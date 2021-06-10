---
title: Actieve gebruiker in Microsoft 365 gebruiksrapporten
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: Meer informatie over een actieve gebruiker Microsoft 365 gebruiksanalyse, activiteitenrapporten en acceptatiestatistieken.
ms.openlocfilehash: 21663722d1a3850389db2ad79321daf363d314c6
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579072"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Actieve gebruiker in Microsoft 365 gebruiksrapporten

## <a name="active-user-in-usage-reports"></a>Actieve gebruiker in gebruiksrapporten

Een actieve gebruiker van Microsoft 365 producten [voor Microsoft 365 gebruiksanalyse](usage-analytics.md) en de [activiteitenrapporten in](../activity-reports/activity-reports.md) het beheercentrum worden als volgt gedefinieerd. 
  
|**Product**|**Definitie van een actieve gebruiker**|**Opmerkingen**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |Elke gebruiker die een van de volgende acties heeft uitgevoerd: Markeren als gelezen, berichten verzenden, afspraken maken, vergaderverzoeken verzenden, vergaderverzoeken accepteren (als voorlopig) of vergaderverzoeken weigeren, vergaderingen annuleren.  <br/> |Agenda-informatie is nog niet opgenomen, dit wordt in een toekomstige update toegevoegd.  <br/> |
|SharePoint Online  <br/> |Elke gebruiker die interactie heeft gehad met een bestand door het te maken, te wijzigen, weer te geven , te verwijderen, intern of extern te delen of te synchroniseren met clients op een site, of door een pagina op een site te bekijken.  <br/> |De actieve gebruikersmetrische gegevens voor SharePoint Online in de Microsoft 365 Usage Analytics-sjabloon-app geven alleen gebruikers weer die bestandsactiviteit hebben gedaan op een SharePoint Teamsite of een groepssite. De sjabloon-app wordt bijgewerkt om de definitie te synchroniseren met dezelfde definitie als in de gebruiksrapporten in het beheercentrum.  <br/> |
|OneDrive voor Bedrijven  <br/> |Elke gebruiker die interactie heeft gehad met een bestand door het te maken, te wijzigen, weer te geven , te verwijderen, intern of extern te delen of te synchroniseren met clients.  <br/> ||
|Yammer  <br/> |Elke gebruiker die een bericht heeft gelezen, geplaatst of leuk heeft gevonden op Yammer.  <br/> ||
|Skype voor Bedrijven  <br/> |Elke gebruiker die heeft deelgenomen aan een peer-to-peer-sessie (inclusief chatberichten, audio- en videogesprekken, het delen van een toepassing en bestandsoverdracht) of die een vergadering heeft georganiseerd of eraan heeft deelgenomen.  <br/> ||
|Office  <br/> |Elke gebruiker die zijn of haar Microsoft 365 Pro Plus, Visio Pro of Project Pro op ten minste één apparaat heeft geactiveerd.  <br/> ||
|Microsoft 365 Groepen  <br/> |Elk groepslid met activiteit in het postvak (als een bericht is verstuurd naar de groep)  <br/> |Deze definitie wordt uitgebreid met groepssitebestandsactiviteit en groepsactiviteit Yammer (bestandsactiviteit op de groepssite en bericht dat is gepost Yammer groep die is gekoppeld aan de groep.) Deze gegevens zijn momenteel niet beschikbaar in de Microsoft 365 De sjabloon-app Gebruiksanalyse  <br/> |
|Microsoft Teams  <br/> |Elke gebruiker die heeft deelgenomen aan chatberichten, privéchatberichten, gesprekken, vergaderingen of andere activiteiten. Andere activiteiten worden gedefinieerd als het aantal andere teamactiviteiten van de gebruiker, waaronder enkele, en niet beperkt tot: het leuk vinden van berichten, apps, het werken aan bestanden, zoeken, het volgen van teams en het kanaal en het begunstigen van deze activiteiten.  <br/> ||
   
## <a name="adoption-metrics"></a>Adoption Metrics

[Microsoft 365 gebruiksanalyse](usage-analytics.md) bevat aanvullende acceptatiestatistieken met betrekking tot actieve gebruikers om aan te geven dat de producten in de afgelopen tijd zijn gebruikt. Deze metrische gegevens zijn geldig voor de maand, het jaar en het geselecteerde product en worden als volgt gedefinieerd. 
  
|**Metrische**|**Beschrijving**|
|:-----|:-----|
|EnabledUsers  <br/> |Het aantal gebruikers dat is ingeschakeld om het product in de maand te gebruiken.  <br/> |
|ActiveUsers  <br/> |Het aantal gebruikers dat actief is in de maand.  <br/> |
|MoMReturningUsers  <br/> |Het aantal gebruikers dat actief is in de maand die ook actief was in de voorgaande maand.  <br/> |
|FirstTimeUsers  <br/> |Het aantal gebruikers dat actief is in de maand die de service nog nooit heeft gebruikt.  <br/> |
|CumulatieveactiveUsers  <br/> |Het aantal gebruikers dat actief is in de maand plus een voorgaande maand.  <br/> |
|ActiveUsers(%)  <br/> |Het percentage gebruikers, afgerond op het dichtstbijzijnde tiende, is actief in de maand vergeleken met het aantal gebruikers dat in die maand is ingeschakeld.  <br/> |
|MoMReturningUsers(%)  <br/> |Het percentage gebruikers, afgerond op het dichtstbijzijnde tiende, actief in de maand die ook actief was in de voorgaande maand, vergeleken met het aantal actieve gebruikers.  <br/> |
   
MoMReturningUsers, FirstTimeUsers, CumulativeActiveUsers zijn vanaf 1 januari 2018 opnieuw ingesteld met de opname van &amp; Microsoft Teams.
  
