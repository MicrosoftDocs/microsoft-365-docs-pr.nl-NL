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
description: In dit artikel wordt beschreven hoe u kunt implementeren naar SharePoint Online zonder traditionele laadtests uit te voeren, omdat dit niet is toegestaan.
ms.openlocfilehash: fb54864168b35fed290ccb1139cb6c607969820d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905222"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a>Capaciteitsplanning en belastingtest van SharePoint Online
In dit artikel wordt beschreven hoe u kunt implementeren naar SharePoint Online zonder traditionele laadtests, omdat laden testen niet is toegestaan in SharePoint Online. SharePoint Online is een cloudservice en de laadmogelijkheden, de status en de totale belastingsbalans in de service worden beheerd door Microsoft.
  
De beste manier om ervoor te zorgen dat uw site succesvol wordt gelanceerd, is het volgen van basisprincipes, procedures en aanbevelingen die worden gemarkeerd in het plan voor de implementatie van uw [portallancering.](planportallaunchroll-out.md)

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a>Overzicht van de manier waarop SharePoint Online capaciteitsplanning uitvoert 
Een van de belangrijkste voordelen van SharePoint Online ten opzichte van een on-premises implementatie is de elasticiteit van de cloud en optimalisaties voor gebruikers in gedistribueerde regio's. Onze grootschalige omgeving is ingesteld voor dagelijks gebruik van miljoenen gebruikers, dus het is belangrijk dat we de capaciteit effectief kunnen verwerken door farms te balanceren en uit te breiden.
  
Hoewel de groei vaak onvoorspelbaar is voor elke tenant in een farm, is de samengevoegde som van aanvragen voorspelbaar in de tijd. Door de groeitrends in SharePoint Online te identificeren, kunnen we toekomstige uitbreiding plannen.
  
Om de capaciteit efficiënt te kunnen gebruiken en onverwachte groei aan te kunnen, hebben we in elke farm automatisering die verschillende elementen van de service bij houdt en bewaakt. Er worden meerdere metrische gegevens gebruikt, waarbij een van de belangrijkste gegevens cpu-belasting is, die wordt gebruikt als signaal om front-endservers op te schalen. Daarnaast raden we een gefaseerd [/golfaanpak](planportallaunchroll-out.md)aan, omdat SQL-omgevingen worden geschaald op basis van belasting en groei in de tijd, en als u de fasen en golven volgt, zorgt u voor de juiste verdeling van die belasting en groei. 

Capaciteit is meer dan alleen het toevoegen van meer hardware op continue basis, maar heeft ook betrekking op het beheren en beheren van die capaciteit om ervoor te zorgen dat geldige laadaanvragen worden onderhouden. We raden klanten aan de aanbevolen richtlijnen te volgen om ervoor te zorgen dat ze de beste ervaring hebben. Het betekent ook dat er beperkingspatronen en besturingselementen zijn om ervoor te zorgen dat we geen 'misbruik' in de service toestaan. Hoewel niet alle 'slechte' gedrag opzettelijk is, moeten we ervoor zorgen dat we het effect van dat gedrag beperken. Voor meer informatie over beperking en hoe u dit kunt voorkomen, bekijkt u hoe u kunt voorkomen dat richtlijnen [worden](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) beperkt.

## <a name="why-you-cannot-load-test-sharepoint-online"></a>Waarom u de test van SharePoint Online niet kunt laden
Bij on-premises omgevingen wordt belastingstests gebruikt om schaalondername te valideren en uiteindelijk het breekpunt van een farm te vinden. door het te verzadigen met belasting. 

Met SharePoint Online moeten we dingen anders doen, omdat de schaal relatief vloeiend is en de belasting wordt aangepast, beperkt en besturingselementen worden bepaald op basis van bepaalde heuristiek. Omdat het zo'n grootschalige omgeving met meerdere tenants is, moeten we alle tenants in dezelfde farm beschermen, zodat we elke belastingstest automatisch beperken. Als u echter probeert om de test te laden, ontvangt u niet alleen een beperkt aantal resultaten, maar ook teleurstellende en potentieel misleidende resultaten, omdat de farm die u vandaag hebt getest waarschijnlijk schaalwijzigingen heeft gehad tijdens het testvenster of binnen enkele uren na het testen, omdat de schaal- en farmbalanceringsacties op een aan de gang zijnde basis worden uitgevoerd.

In plaats van te proberen test SharePoint als een service te laden, moet u zich liever richten op het volgen van de aanbevolen procedures en de richtlijnen voor het [maken,](/sharepoint/portal-health) starten en onderhouden van een gezonde portal volgen.