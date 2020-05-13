---
title: Veelgestelde vragen over in een wachtrij geplaatste, uitgestelde en niet-bezorgde berichten in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Antwoorden vinden op de meest voorkomende vragen over berichten die in de wachtrij staan, uitgesteld of teruggestuurd zijn tijdens het Filterproces Exchange Online Protection (EOP).
ms.openlocfilehash: 38e72a04e855862c621bd2b170c11407e0d22af3
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206590"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Veelgestelde vragen over in een wachtrij geplaatste, uitgestelde en niet-bezorgde berichten in EOP

In dit onderwerp vindt u antwoorden op veelgestelde vragen over berichten die in de wachtrij staan, uitgesteld of teruggestuurd zijn tijdens het Filterproces (Exchange Online Protection).

## <a name="why-is-mail-queuing"></a>Waarom staat post in de rij?

Berichten worden in de wachtrij of uitgesteld als de service geen verbinding kan maken met de server met de geadresseerde voor levering. Het zal berichten niet uitstellen als een 500-serie fout wordt geretourneerd van het netwerk van de ontvanger.

## <a name="how-does-a-message-become-deferred"></a>Hoe wordt een bericht uitgesteld?

Berichten worden bewaard wanneer een verbinding met de server met de ontvanger niet kan worden gemaakt en de server van de ontvanger een "tijdelijke fout" retoureert, zoals een time-out van de verbinding, geweigerde verbinding of een fout van 400-serie. Als er een permanente fout optreedt, zoals een fout van 500-reeksen, wordt het bericht teruggestuurd naar de afzender.

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>Hoe lang blijft een bericht in uitstel en wat is het interval voor het opnieuw proberen?

Berichten in uitstel blijven 1 dag in onze wachtrijen staan. Pogingen voor het opnieuw proberen van berichten zijn gebaseerd op de fout die we terugkrijgen van het e-mailsysteem van de ontvanger. De eerste paar uitstel zijn 15 minuten of minder, met latere pogingen (in de komende half dozijn of zo) het verhogen van het interval over meerdere pogingen tot een maximum van 60 minuten. De uitbreiding van de intervalduur is dynamisch, rekening houdend met meerdere variabelen, zoals wachtrijformaten en interne berichtprioriteit. In principe is het 15 minuten (of minder) om te beginnen, dan uit te breiden vanaf daar in de komende uren tot 60 minuten max.

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>Hoe worden berichten in de wachtrij gedistribueerd nadat uw e-mailserver is hersteld?

Nadat uw e-mailserver is hersteld, worden alle in de wachtrij staande berichten automatisch verwerkt in de volgorde waarin ze zijn ontvangen en in de wachtrij stonden toen de server niet beschikbaar was.
