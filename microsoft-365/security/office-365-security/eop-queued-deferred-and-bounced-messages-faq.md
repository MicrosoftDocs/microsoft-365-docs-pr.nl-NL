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
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Antwoorden vinden op de meest voorkomende vragen over berichten die in de wachtrij zijn geplaatst, uitgesteld of zijn afgeketst tijdens het EOP-filterproces (Exchange Online Protection).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c7b5ba595e9a6401efd1b733c9e5a11c8a966037
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204828"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Veelgestelde vragen over in een wachtrij geplaatste, uitgestelde en niet-bezorgde berichten in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Dit onderwerp bevat antwoorden op veelgestelde vragen over berichten die in de wachtrij zijn geplaatst, uitgesteld of zijn afgeketst tijdens het EOP-filterproces (Exchange Online Protection).

## <a name="why-is-mail-queuing"></a>Waarom staat e-mail in de wachtrij?

Berichten worden in de wachtrij geplaatst of uitgesteld als de service geen verbinding kan maken met de geadresseerdeserver voor bezorging. Berichten worden niet uitgesteld als er een fout van 500 reeksen wordt geretourneerd vanuit het netwerk van de geadresseerde.

## <a name="how-does-a-message-become-deferred"></a>Hoe wordt een bericht uitgesteld?

Berichten worden opgeslagen wanneer er geen verbinding kan worden gemaakt met de server van de geadresseerde en de server van de geadresseerde een 'tijdelijke fout' retournt, zoals een time-out van de verbinding, geweigerde verbinding of een fout in de 400-reeks. Als er een permanente fout is, zoals een fout van 500 reeksen, wordt het bericht geretourneerd aan de afzender.

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>Hoe lang blijft een bericht in de uitstelperiode staan en wat is het interval voor het opnieuw proberen?

Berichten in uitstel blijven 1 dag in onze wachtrijen staan. Pogingen voor het opnieuw proberen van berichten zijn gebaseerd op de fout die we krijgen van het e-mailsysteem van de geadresseerde. De eerste paar uitstelperioden zijn 15 minuten of minder, met de volgende wijzigingen (in de komende zes maanden) waardoor het interval over meerdere hervervolgingen wordt oplopende tot maximaal 60 minuten. De uitbreiding van de intervalduur is dynamisch, waarbij rekening wordt gehouden met meerdere variabelen, zoals wachtrijgrootten en interne berichtprioriteit. In de basis is het 15 minuten (of minder) om te beginnen en vervolgens in de komende uren uit te breiden tot max 60 minuten.

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>Hoe worden berichten in de wachtrij verdeeld nadat uw e-mailserver is hersteld?

Nadat uw e-mailserver is hersteld, worden alle wachtrijberichten automatisch verwerkt in de volgorde waarin ze zijn ontvangen en in de wachtrij staan wanneer de server niet beschikbaar is.
