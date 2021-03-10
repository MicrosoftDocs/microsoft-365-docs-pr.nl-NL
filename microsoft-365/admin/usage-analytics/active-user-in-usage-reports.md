---
title: Actieve gebruiker in Microsoft 365-gebruiksrapporten
ms.author: sirkkuw
author: Sirkkuw
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
description: Meer informatie over een actieve gebruiker van Microsoft 365 Gebruiksanalyse, activiteitsrapporten en acceptatiestatistieken.
ms.openlocfilehash: 7b8d15a88568c9af8b11a157dad2ec5f76ace6d3
ms.sourcegitcommit: 9adb89206daa075af34a73bcb7e8fb86d7c2919a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/10/2021
ms.locfileid: "50603970"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Actieve gebruiker in Microsoft 365-gebruiksrapporten

## <a name="active-user-in-usage-reports"></a>Actieve gebruiker in gebruiksrapporten

Een actieve gebruiker van Microsoft 365-producten voor [Microsoft 365](usage-analytics.md) Gebruiksanalyse en de activiteitsrapporten in het [beheercentrum](../activity-reports/activity-reports.md) is als volgt gedefinieerd. 
  
|**Product**|**Definitie van een actieve gebruiker**|**Opmerkingen**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |Elke gebruiker die een van de volgende acties heeft uitgevoerd: Markeren als gelezen, berichten verzenden, afspraken maken, vergaderverzoeken verzenden, (als voorlopig) accepteren of vergaderverzoeken weigeren, vergaderingen annuleren.  <br/> |Agenda-informatie is nog niet opgenomen, dit wordt in een toekomstige update toegevoegd.  <br/> |
|SharePoint Online  <br/> |Elke gebruiker die interactie heeft gehad met een bestand door het te maken, te wijzigen, weer te geven , te verwijderen, intern of extern te delen of te synchroniseren met clients op een site, of door een pagina op een site te bekijken.  <br/> |De metrische gegevens voor actieve gebruikers voor SharePoint Online in de sjabloon-app Microsoft 365 Gebruiksanalyse geven alleen gebruikers weer die een activiteit hebben gedaan met een bestand in een SharePoint-teamsite of -groepssite. De sjabloon-app wordt bijgewerkt om de definitie te synchroniseren met die van de gebruiksrapporten in het beheercentrum.  <br/> |
|OneDrive voor Bedrijven  <br/> |Elke gebruiker die interactie heeft gehad met een bestand door het te maken, te wijzigen, weer te geven , te verwijderen, intern of extern te delen of te synchroniseren met clients.  <br/> ||
|Yammer  <br/> |Elke gebruiker die een bericht heeft gelezen, geplaatst of leuk heeft gevonden op Yammer.  <br/> ||
|Skype voor Bedrijven  <br/> |Elke gebruiker die heeft deelgenomen aan een peer-to-peer-sessie (inclusief chatberichten, audio- en videogesprekken, het delen van een toepassing en bestandsoverdracht) of die een vergadering heeft georganiseerd of eraan heeft deelgenomen.  <br/> ||
|Office  <br/> |Elke gebruiker die zijn of haar abonnement op Microsoft 365 Pro Plus, Visio Pro of Project Pro heeft geactiveerd op ten minste één apparaat.  <br/> ||
|Microsoft 365 Groepen  <br/> |Elk groepslid met activiteit in het postvak (als een bericht is verstuurd naar de groep)  <br/> |Deze definitie wordt uitgebreid met activiteit op een groepssite en in een Yammer-groep (bestandsactiviteit op een groepssite en in een Yammer-groep die is gekoppeld aan de groep).) Deze gegevens zijn momenteel niet beschikbaar in de sjabloon-app Microsoft 365 Gebruiksanalyse  <br/> |
|Microsoft Teams  <br/> |Elke gebruiker die heeft deelgenomen aan chatberichten, privéchatberichten, oproepen, vergaderingen of andere activiteiten. Andere activiteit wordt gedefinieerd als het aantal andere teamactiviteiten door de gebruiker, waaronder, en niet beperkt tot: het leuk vinden van berichten, apps, het werken aan bestanden, zoeken, het volgen van teams en kanaal en het vervangen ervan.  <br/> ||
   
## <a name="adoption-metrics"></a>Meetgegevens over acceptatie

[Microsoft 365 Gebruiksanalyse](usage-analytics.md) bevat aanvullende acceptatiestatistieken met betrekking tot actieve gebruikers om acceptatie van de producten in de tijd weer te geven. Deze statistieken zijn geldig voor de maand, het jaar en het geselecteerde product en worden als volgt gedefinieerd. 
  
|**Metrisch**|**Beschrijving**|
|:-----|:-----|
|EnabledUsers  <br/> |Het aantal gebruikers dat is ingeschakeld voor gebruik van het product in de maand.  <br/> |
|ActiveUsers  <br/> |Het aantal gebruikers dat actief is in de maand.  <br/> |
|MoMReturningUsers  <br/> |Het aantal gebruikers dat actief was in de maand die ook actief was in de voorgaande maand.  <br/> |
|FirstTimeUsers  <br/> |Het aantal gebruikers dat actief is in de maand waarin de service nooit eerder is gebruikt.  <br/> |
|CumulativeActiveUsers  <br/> |Het aantal gebruikers dat actief is in de maand plus een voorgaande maand.  <br/> |
|ActiveUsers(%)  <br/> |Het percentage gebruikers, afgerond op het dichtstbijzijnde tiende deel, is actief in de maand, vergeleken met het aantal gebruikers dat in die maand is ingeschakeld.  <br/> |
|MoMReturningUsers(%)  <br/> |Het percentage gebruikers, afgerond op het dichtstbijzijnde tiende deel, actief in de maand die ook actief was in de vorige maand, vergeleken met het aantal actieve gebruikers.  <br/> |
   
MoMReturningUsers, FirstTimeUsers, CumulativeActiveUsers zijn teruggezet vanaf 1 januari &amp; 2018 met microsoft Teams als opname.
  
