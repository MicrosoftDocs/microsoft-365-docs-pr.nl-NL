---
title: Gegevens verwijderen in Office 365 Skype voor bedrijven
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In dit artikel vindt u een beschrijving van de verwijdering van gegevens in Skype voor bedrijven, met inbegrip van de typen inhoud die niet behouden blijven.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bf317f2ecd3d547ae8601553a34fb43fb4b5bd9d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689379"
---
# <a name="skype-for-business-data-deletion-in-office-365"></a>Skype voor bedrijven-data verwijdering in Office 365

Skype voor bedrijven biedt de archivering van chatberichten van peer-to-peer, chatberichten met meer informatie en activiteiten voor het uploaden van inhoud in vergaderingen. Voor de archiveringsfunctie is Exchange vereist en deze wordt beheerd door het in-place bewarings kenmerk van de gebruiker, waarin zowel e-mail als Skype voor bedrijven-inhoud wordt gearchiveerd.

Alle archiveringsfuncties in Skype voor bedrijven worden als ' archivering op gebruikersniveau ' beschouwd, omdat u het in-of uitschakelt voor een of meer specifieke gebruikers of groepen gebruikers door een beleidsregels voor archivering op gebruikersniveau te maken, configureren en toepassen voor deze gebruikers. Er is geen directe controle van de archiveringsinstellingen in het Skype voor bedrijven-Beheercentrum.

De volgende soorten inhoud worden niet gearchiveerd in Skype voor bedrijven:

- Peer-to-peer-bestandsoverdracht
- Audio/video voor chatberichten en conferenties van peer-to-peer
- Toepassingen delen voor chatberichten en vergaderingen van peer-to-peer
- Aantekeningen voor vergaderingen 

## <a name="meeting-content-retention"></a>Bewaren van inhoud van de vergadering

Klanten die Skype voor bedrijven gebruiken, kunnen inhoud naar een Skype voor bedrijven-vergadering uploaden als bijlage, zoals PowerPoint-presentaties, OneNote-bestanden en andere bestanden. De bewaarperiode voor inhoud die is geüpload naar een vergadering, luidt als volgt:

- **Eenmalige vergadering** -inhoud wordt 15 dagen lang bewaard vanaf wanneer de laatste persoon de vergadering verlaat.
- **Terugkerende vergadering** -inhoud blijft 15 dagen lang geldig nadat de laatste persoon de laatste sessie van de vergadering verlaat. De Bewaar timer wordt opnieuw ingesteld als iemand binnen 15 dagen aan dezelfde Vergader sessie deelneemt. Als u bijvoorbeeld een vergadering in Skype voor bedrijven voor één jaar wekelijks plant, en een bestand wordt geüpload naar de vergadering tijdens het eerste exemplaar. Als ten minste één persoon elke week aan de vergadering deelneemt, blijft het bestand in Skype voor bedrijven online-servers voor het hele jaar en 15 dagen na de laatste persoon de laatste vergadering van de reeks verlaten.
- **Nu vergaderen** -inhoud wordt gedurende 8 uur na de eindtijd van de vergadering bewaard.

> [!NOTE]
> Als een gebruiker geen licentie heeft of is uitgeschakeld (bijvoorbeeld als **msRTCSIP-userenabled** is ingesteld op *Onwaar*) en dan opnieuw een licentie voor de vergadering blijft behouden of opnieuw inschakelt, wordt de inhoud van de vergadering niet bewaard.

## <a name="meeting-expiration"></a>Verloop van vergadering

Gebruikers hebben toegang tot een specifieke vergadering nadat de vergadering is beëindigd, met inachtneming van de volgende verloopperiode:

- **Eenmalige vergadering** -vergadering verloopt 14 dagen na de geplande eindtijd van de vergadering.
- **Terugkerende vergadering met einddatum** -de vergadering verloopt 14 dagen na de geplande eindtijd van het laatste exemplaar van de vergadering.
- Verg **aderen tot nu** toe: de vergadering verloopt na acht uur.

## <a name="whiteboard-collaboration"></a>Samenwerken met Whiteboard

Aantekeningen op whiteboards worden weergegeven door alle deelnemers. Wanneer u een whiteboard opslaat, worden het whiteboard en alle aantekeningen opgeslagen op een Skype voor bedrijven-server en wordt het op de server bewaard op basis van het verloopbeleid voor de inhoud van de beheerder.

## <a name="audio-test-service"></a>Service voor audio tests

Tijdens de audio test service wordt een kort voorbeeld van de audio test opgenomen. Het spraak voorbeeld wordt door u gebruikt om de geluidskwaliteit van uw gesprekken in Skype voor bedrijven te controleren en/of te verifiëren op basis van de kwaliteit van de opname. Wanneer de audio test service oproep eindigt, wordt het spraak voorbeeld verwijderd.

## <a name="persistent-group-chat"></a>Permanente chat voor groepen

Permanente groepsgesprek slaat de inhoud van de groepsgesprekken op. Als deze functie is ingeschakeld, kan de beheerder de bewaarperiode beheren, de server waarop deze informatie is opgeslagen, en de geschiedenis van een groepsgesprek wordt gearchiveerd voor compliance of andere doeleinden en de eigenschappen van een ruimte beheren/wijzigen. Gebruikers met verschillende rollen hebben als volgt verschillende toegang tot de permanente gegevens:

- Beheerders kunnen oudere inhoud verwijderen (bijvoorbeeld inhoud die vóór een bepaalde datum is gepubliceerd) vanuit een chatruimte, zodat de grootte van de database sterk opvalt. U kunt ook berichten verwijderen of vervangen als ongepaste berichten die niet geschikt zijn voor een bepaalde chatruimte (of als niet-bruikbaar).
- Eindgebruikers, waaronder schrijvers van berichten, kunnen geen inhoud verwijderen uit een chatruimte.
- Beheerders van een chat ruimte kunnen kamers uitschakelen, maar ruimten niet verwijderen. Alleen beheerders kunnen een chatruimte verwijderen nadat deze is gemaakt.