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
description: Hier vindt u antwoorden op de meest voorkomende vragen over berichten die in de wachtrij zijn geplaatst, zijn uitgesteld of niet zijn gevonden tijdens het EOP-filterproces (Exchange Online Protection).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e54a260a70a9c68a94412243308bffe60d989e99
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289697"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Veelgestelde vragen over in een wachtrij geplaatste, uitgestelde en niet-bezorgde berichten in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Dit onderwerp bevat antwoorden op veelgestelde vragen over berichten die in de wachtrij zijn geplaatst, zijn uitgesteld of niet zijn bezorgd tijdens het filterproces van Exchange Online Protection (EOP).

## <a name="why-is-mail-queuing"></a>Waarom staat e-mail in wachtrij?

Berichten worden in de wachtrij geplaatst of uitgesteld als de service geen verbinding kan maken met de ontvangerserver voor bezorging. Het stelt berichten niet uit als er een fout van 500 reeksen wordt geretourneerd van het netwerk van de ontvanger.

## <a name="how-does-a-message-become-deferred"></a>Hoe wordt een bericht uitgesteld?

Berichten worden opgeslagen wanneer er geen verbinding kan worden gemaakt met de ontvangerserver en de server van de geadresseerde een 'tijdelijke fout' retournt, zoals een time-out van de verbinding, een verbinding geweigerd of een fout van 400 reeksen. Als er een permanente fout is, zoals een fout van 500 reeksen, wordt het bericht geretourneerd aan de afzender.

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>Hoe lang blijft een bericht in de uitstelperiode staan en wat is het interval voor opnieuw proberen?

Berichten in de wachtrij blijven 1 dag in onze wachtrijen staan. Pogingen om berichten opnieuw te proberen, zijn gebaseerd op de fout die we krijgen uit het e-mailsysteem van de geadresseerde. De eerste paar uitstelperioden zijn 15 minuten of minder, met volgende keren opnieuw proberen (de volgende half uur of zo) het interval over meerdere keren opnieuw tot een maximum van 60 minuten te verhogen. De uitbreiding van de intervalduur is dynamisch, waarbij rekening wordt gehouden met meerdere variabelen, zoals de grootte van wachtrijen en interne berichtprioriteit. In het basisprincipe is het 15 minuten (of minder) om te beginnen en vervolgens van hier uit te breiden tot maximaal 60 minuten.

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>Hoe worden berichten in de wachtrij gedistribueerd nadat de e-mailserver is hersteld?

Nadat de e-mailserver is hersteld, worden alle berichten in de wachtrij automatisch verwerkt in de volgorde waarin ze zijn ontvangen en in de wachtrij werden geplaatst wanneer de server niet meer beschikbaar werd.
