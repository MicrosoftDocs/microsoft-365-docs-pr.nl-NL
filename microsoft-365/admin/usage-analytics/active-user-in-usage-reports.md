---
title: Actieve gebruiker in Microsoft 365-gebruiksrapporten
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: Meer informatie over een actieve gebruiker van Microsoft 365-gebruiksanalyses, activiteitenrapporten en acceptatiestatistieken.
ms.openlocfilehash: 0e2f5f5112593c142b4a7829977221c5542adf49
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42812842"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Actieve gebruiker in Microsoft 365-gebruiksrapporten

## <a name="active-user-in-usage-reports"></a>Actieve gebruiker in gebruiksrapporten

Een actieve gebruiker van Microsoft 365-producten voor [Microsoft 365-gebruiksanalyses](usage-analytics.md) en de [activiteitsrapporten in het beheercentrum](../activity-reports/activity-reports.md) wordt als volgt gedefinieerd. 
  
|**Product**|**Definitie van een actieve gebruiker**|**Opmerkingen**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |Elke gebruiker die een e-mail heeft gelezen of verzonden.  <br/> |Agenda-informatie is nog niet opgenomen, dit wordt in een toekomstige update toegevoegd.  <br/> |
|SharePoint Online  <br/> |Elke gebruiker die interactie heeft gehad met een bestand door het te maken, te wijzigen, weer te geven , te verwijderen, intern of extern te delen of te synchroniseren met clients op een site, of door een pagina op een site te bekijken.  <br/> |De actieve gebruikersstatistiek voor SharePoint Online in de sjabloon-app Microsoft 365 Usage Analytics geeft alleen gebruikers weer die zich hebben geregistreerd op een SharePoint-teamsite of een groepssite. De sjabloon-app wordt bijgewerkt om de definitie te synchroniseren met dezelfde als die in de gebruiksrapporten in het beheercentrum.  <br/> |
|OneDrive voor Bedrijven  <br/> |Elke gebruiker die interactie heeft gehad met een bestand door het te maken, te wijzigen, weer te geven , te verwijderen, intern of extern te delen of te synchroniseren met clients.  <br/> ||
|Yammer  <br/> |Elke gebruiker die een bericht heeft gelezen, geplaatst of leuk heeft gevonden op Yammer.  <br/> ||
|Skype voor Bedrijven  <br/> |Elke gebruiker die heeft deelgenomen aan een peer-to-peer-sessie (inclusief chatberichten, audio- en videogesprekken, het delen van een toepassing en bestandsoverdracht) of die een vergadering heeft georganiseerd of eraan heeft deelgenomen.  <br/> ||
|Office  <br/> |Elke gebruiker die zijn Microsoft 365 Pro Plus-, Visio Pro- of Project Pro-abonnement op ten minste één apparaat heeft geactiveerd.  <br/> ||
|Microsoft 365-groepen  <br/> |Elk groepslid met activiteit in het postvak (als een bericht is verstuurd naar de groep)  <br/> |Deze definitie wordt uitgebreid met groepssitebestandsactiviteit en Yammer-groepsactiviteit (bestandsactiviteit op groepssite en bericht dat is geplaatst in yammer-groep die is gekoppeld aan de groep.) Deze gegevens zijn momenteel niet beschikbaar in de sjabloon-app Microsoft 365 Usage Analytics  <br/> |
|Microsoft Teams  <br/> |Elke gebruiker die heeft deelgenomen aan chatberichten, privéchatberichten, gesprekken, vergaderingen of andere activiteiten. Andere activiteiten worden gedefinieerd als het aantal andere teamactiviteiten van de gebruiker, waarvan sommige, en niet beperkt tot: het leuk vinden van berichten, apps, het werken aan bestanden, zoeken, teams volgen en channelen en ze bevoordelen.  <br/> ||
   
## <a name="adoption-metrics"></a>Adoptiestatistieken

[Microsoft 365-gebruiksanalyses](usage-analytics.md) bevatten aanvullende acceptatiestatistieken met betrekking tot actieve gebruikers om de acceptatie van de producten in de loop van de tijd weer te geven. Deze statistieken zijn geldig voor de maand, het jaar en het product geselecteerd en worden als volgt gedefinieerd. 
  
|**Metrische**|**Beschrijving**|
|:-----|:-----|
|Ingeschakelde gebruikers  <br/> |Aantal gebruikers ingeschakeld om het product te gebruiken in de maand.  <br/> |
|Actievegebruikers  <br/> |Aantal gebruikers actief in de maand.  <br/> |
|MomReturningUsers  <br/> |Aantal gebruikers dat actief is in de maand dat ook actief was in de voorgaande maand.  <br/> |
|FirstTimeUsers FirstTimeUsers  <br/> |Aantal gebruikers dat actief is in de maand dat de service nog nooit eerder had gebruikt.  <br/> |
|Cumulatieve Actievegebruikers  <br/> |Aantal gebruikers dat actief is in de maand plus een voorafgaande maand.  <br/> |
|ActiveUsers(%)  <br/> |Percentage gebruikers, afgerond op de dichtstbijzijnde tiende, actief in de maand in vergelijking met het aantal gebruikers ingeschakeld in die maand.  <br/> |
|MomReturningUsers(%)  <br/> |Percentage gebruikers, afgerond op de dichtstbijzijnde tiende, actief in de maand die ook actief was in de voorgaande maand in vergelijking met het aantal actieve gebruikers.  <br/> |
   
MoMReturningUsers, FirstTimeUsers, &amp; CumulativeActiveUsers werden vanaf 1 januari 2018 gereset met de toevoeging van Microsoft Teams.
  
