---
title: Capaciteitsplanning en belastingtest van SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/10/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: c932bd9b-fb9a-47ab-a330-6979d03688c0
description: In dit artikel wordt beschreven hoe u een implementatie kunt uitvoeren in SharePoint Online zonder traditionele belasting tests uit te voeren, omdat dit niet is toegestaan.
ms.openlocfilehash: a20ed3b5f9b3108d90ec912ec78efa348d4281b1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689394"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a>Capaciteitsplanning en belastingtest van SharePoint Online
In dit artikel wordt beschreven hoe u een implementatie kunt uitvoeren in SharePoint Online zonder traditionele belasting tests, aangezien laad tests niet zijn toegestaan op SharePoint Online. SharePoint Online is een cloudservice en de geladen functies, status en algemeen saldo van de belasting van de service wordt beheerd door Microsoft.
  
De beste manier om ervoor te zorgen dat uw site wordt gestart is door basisprincipes, richtlijnen en aanbevelingen te volgen, die zijn gemarkeerd in de implementatie van de [Portal-start](planportallaunchroll-out.md).

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a>Overzicht van de manier waarop SharePoint Online capaciteitsplanning uitvoert 
Een van de belangrijkste voordelen van SharePoint Online via een on-premises implementatie is de elasticiteit van de Cloud en optimaliseringen voor gebruikers in gedistribueerde regio's. Onze grootschalige omgeving is ingesteld om miljoenen gebruikers dagelijks te serviceen, dus het is belangrijk dat we de capaciteit effectief hanteren door bedrijven uit te voeren en uit te breiden.
  
Hoewel de groei vaak niet te laat vervalt voor één van de tenants in één farm, kan de geaggregeerde som van aanvragen gedurende een bepaalde periode voorspelbaar zijn. Door de groeitrends te identificeren in SharePoint Online, kunnen we voor toekomstige expansie plannen.
  
Om de capaciteit efficiënt te kunnen gebruiken en de onverwachte groei van een farm te regelen, hebben we automatisering waarmee u diverse elementen van de service kunt bijhouden en monitoren. Meerdere metrieken worden gebruikt, waarbij een van de belangrijkste servers wordt geladen als een signaal om de front-end servers te schalen. Daarnaast wordt u aangeraden een [gefaseerde/Golf aanpak](planportallaunchroll-out.md)te kiezen, aangezien SQL-omgevingen in de loop van de tijd worden geladen en gebracht, en het volgen van de fasen en golven de juiste verdeling van de belasting en groei toestaat. 

U kunt meer informatie vinden over het toevoegen van extra hardware, maar ook om te voorkomen dat de hardware geldig laad aanvragen beheert en beheert. Klanten wordt aangeraden de aanbevolen richtlijnen te volgen om ervoor te zorgen dat ze de beste ervaring hebben. Ook betekent dit dat we patronen en besturingselementen op hun plaats stellen om ervoor te zorgen dat het gedrag van beledigend gedrag in de service niet is toegestaan. Hoewel het gedrag van de ' slecht '-gedrag van opzet is, moet u ervoor zorgen dat we de werking van dat gedrag beperken. Zie voor meer informatie over het beperken en leren hoe u dit voorkomen door het artikel [vertraagd richtlijnen te vermijden](https://docs.microsoft.com/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) .

## <a name="why-you-cannot-load-test-sharepoint-online"></a>Waarom u de test SharePoint Online niet kunt laden
Met een on-premises omgeving wordt het testen van de schaal gebruikt voor de validatie van de beoordeeling van de schaal en uiteindelijk naar het einde punt van een farm. door deze te deverdelen. 

Met SharePoint Online moeten we zaken anders doen omdat de schaal betrekkelijk vloeistof is en de belasting, vertraagd en besturingselementen op basis van bepaalde heuristiek. Als u de omgeving voor meerdere tenants op basis van grote schaal gebruikt, moet u alle tenants in dezelfde farm beschermen, zodat we de lading tests automatisch beperken. Als u toch probeert om testen te laden, wordt u niet alleen vertraagd, maar u ontvangt disappointing en mogelijk misleidende resultaten omdat de farm die u hebt getest, waarschijnlijk gewijzigd werd tijdens het testvenster of binnen uur na het testen.

In plaats van een testversie van SharePoint als een service te laden, kunt u beter de aanbevolen procedures volgen en de richtlijnen voor het [maken, starten en onderhouden van een goede Portal](https://go.microsoft.com/fwlink/?linkid=2105838) volgen.
