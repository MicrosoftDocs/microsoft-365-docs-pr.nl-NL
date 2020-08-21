---
title: Veelgestelde vragen over in een wachtrij geplaatste, uitgestelde en niet-bezorgde berichten in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Hier vindt u antwoorden op de meest gestelde vragen over berichten die in de wachtrij zijn gezet, zijn uitgesteld of gestuiterd tijdens het filterproces van Exchange Online Protection (EOP).
ms.openlocfilehash: 76fe08f3a83321b6c0549dae5f1382ead5f0b3ae
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827747"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Veelgestelde vragen over in een wachtrij geplaatste, uitgestelde en niet-bezorgde berichten in EOP

In dit onderwerp vindt u antwoorden op veelgestelde vragen over berichten die in de wachtrij zijn gezet, zijn uitgesteld of gestuiterd tijdens het filterproces van Exchange Online Protection (EOP).

## <a name="why-is-mail-queuing"></a>Waarom is mail Queuing?

Berichten worden in de wachtrij geplaatst of uitgesteld als de service geen verbinding kan maken met de ontvanger van de server. Berichten worden niet weergegeven als een 500-serie-fout wordt geretourneerd via het netwerk van de geadresseerde.

## <a name="how-does-a-message-become-deferred"></a>Hoe wordt een bericht uitgesteld?

Berichten worden gehouden wanneer een verbinding met de server van de ontvanger niet kan worden doorgevoerd en de server van de ontvanger retourneert een tijdelijke fout, zoals een time-out voor de verbinding, een verbinding met een 400-serie. Als er een permanente fout is, zoals een 500-serie-fout, wordt het bericht teruggegeven aan de afzender.

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>Hoe lang blijft een bericht in de tekst uitgesteld en wat is het interval voor opnieuw proberen?

Berichten in uitgesteld blijven gedurende 1 dag in onze wachtrijen. De nieuwe pogingen voor het bericht worden weergegeven op basis van de fout die het e-mailsysteem van de ontvanger van de geadresseerde ontvangt. De eerste paar van de uitstel tekens zijn 15 minuten of minder, met volgende nieuwe pogingen (meer dan een halve dozijn of zo) het verhogen van het interval voor meerdere pogingen tot een maximum van 60 minuten. De expansie van het tijdsinterval is dynamisch, waarbij rekening moet worden gehouden met meerdere variabelen, zoals wachtrij formaten en interne berichtprioriteit. In de basis is dit 15 minuten (of minder) om te beginnen en vervolgens uit te breiden tot de volgende paar uur tot 60 minuten.

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>Wanneer uw e-mailserver is hersteld, hoe worden berichten in de wachtrij gedistribueerd?

Nadat de e-mailserver is hersteld, worden alle berichten in de wachtrij automatisch verwerkt in de volgorde waarin ze zijn ontvangen en in de wachtrij geplaatst wanneer de server niet beschikbaar was.
