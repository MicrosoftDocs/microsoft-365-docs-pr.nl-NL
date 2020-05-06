---
title: Veelgestelde vragen over in een wachtrij geplaatste, uitgestelde en niet-bezorgde berichten in EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Antwoorden vinden op veelgestelde vragen over berichten die in de wachtrij staan, uitgesteld of teruggestuurd zijn tijdens het EOP-filterproces (Microsoft Exchange Online Protection).
ms.openlocfilehash: f7a7c8b5466e02353ca114d6c7ed44f37bed5592
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036546"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Veelgestelde vragen over in een wachtrij geplaatste, uitgestelde en niet-bezorgde berichten in EOP

In dit onderwerp vindt u antwoorden op veelgestelde vragen over berichten die in de wachtrij staan, uitgesteld of teruggestuurd zijn tijdens het EOP-filterproces (Microsoft Exchange Online Protection).

**V. Waarom staat post in de rij?**

A. Berichten worden in de wachtrij of uitgesteld als de service geen verbinding kan maken met de server met de geadresseerde voor levering. Het zal berichten niet uitstellen als een 500-serie fout wordt geretourneerd van het netwerk van de ontvanger.

**V. Hoe wordt een bericht uitgesteld?**

A. Berichten worden bewaard wanneer een verbinding met de server met de ontvanger niet kan worden gemaakt en de server van de ontvanger een "tijdelijke fout" retoureert, zoals een time-out van de verbinding, geweigerde verbinding of een fout van 400-serie. Als er een permanente fout optreedt, zoals een fout van 500-reeksen, wordt het bericht teruggestuurd naar de afzender.

**V. Hoe lang blijft een bericht in uitstel en wat is het interval voor het opnieuw proberen?**

A. Berichten in uitstel blijven 1 dag in onze wachtrijen staan. Pogingen voor het opnieuw proberen van berichten zijn gebaseerd op de fout die we terugkrijgen van het e-mailsysteem van de ontvanger. De eerste paar uitstel zijn 15 minuten of minder, met latere pogingen (in de komende half dozijn of zo) het verhogen van het interval over meerdere pogingen tot een maximum van 60 minuten. De uitbreiding van de intervalduur is dynamisch, rekening houdend met meerdere variabelen, zoals wachtrijformaten en interne berichtprioriteit. In principe is het 15 minuten (of minder) om te beginnen, dan uit te breiden vanaf daar in de komende uren tot 60 minuten max.

**V. Hoe worden berichten in de wachtrij gedistribueerd nadat uw e-mailserver is hersteld?**

A. Nadat uw e-mailserver is hersteld, worden alle in de wachtrij staande berichten automatisch verwerkt in de volgorde waarin ze zijn ontvangen en in de wachtrij stonden toen de server niet beschikbaar was.
