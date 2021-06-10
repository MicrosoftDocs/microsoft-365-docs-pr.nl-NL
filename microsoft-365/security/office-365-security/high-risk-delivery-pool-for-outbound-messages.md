---
title: Uitgaande bezorgingspools
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Lees hoe de bezorgingsgroepen worden gebruikt om de reputatie van e-mailservers in de Microsoft 365 beschermen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac3469150ef5cf5c1040fcddf7f0bc95e7a18805
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599909"
---
# <a name="outbound-delivery-pools"></a>Uitgaande bezorgingspools

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

E-mailservers in Microsoft 365 datacenters zijn mogelijk tijdelijk schuldig aan het verzenden van spam. Bijvoorbeeld een malware- of schadelijke spamaanval in een on-premises e-mailorganisatie die uitgaande e-mail verzendt via Microsoft 365 of gecompromitteerde Microsoft 365 accounts. Aanvallers proberen detectie ook te voorkomen door berichten door te sturen via Microsoft 365 doorsturen.

Deze scenario's kunnen resulteren in het IP-adres van de Microsoft 365 datacenterservers die worden weergegeven op blokkeringen van derden. Doel-e-mailorganisaties die deze blokkeringen gebruiken, weigeren e-mail uit deze berichtenbronnen.

## <a name="high-risk-delivery-pool"></a>Bezorgingsgroep met hoog risico
Om dit te voorkomen, worden alle uitgaande berichten van Microsoft 365 datacenterservers die zijn vastgesteld dat ze spam zijn of die de verzendende limieten van het [service-](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) of uitgaande [spambeleid](configure-the-outbound-spam-policy.md) overschrijden, verzonden via de groep met een hoog _risico._

De groep bezorging met hoog risico is een aparte IP-adresgroep voor uitgaande e-mail die alleen wordt gebruikt om berichten van 'lage kwaliteit' te verzenden (bijvoorbeeld spam en [backscatter).](backscatter-messages-and-eop.md) Als u de groep met een hoog risico gebruikt, voorkomt u dat de normale IP-adresgroep voor uitgaande e-mail spam verstuurt. De normale IP-adresgroep voor uitgaande e-mail behoudt de reputatie van het verzenden van berichten van hoge kwaliteit, waardoor de kans wordt verkleind dat dit IP-adres wordt weergegeven in IP-blokkeringen.

De zeer reële mogelijkheid dat IP-adressen in de groep met een hoog risico worden geplaatst op IP-blokkeringen blijft bestaan, maar dit is een ontwerp. Bezorging aan de beoogde geadresseerden is niet gegarandeerd, omdat veel e-mailorganisaties geen berichten accepteren uit de groep met hoge risico's.

Zie Uitgaande spam controleren [voor meer informatie.](outbound-spam-controls.md)

> [!NOTE]
> Berichten waarin het bron-e-maildomein geen A-record heeft en geen MX-record die is gedefinieerd in openbare DNS, worden altijd door de groep met hoge risico's verzonden, ongeacht de spam of het verzenden van limieten.

### <a name="bounce-messages"></a>Berichten bouncen

De groep uitgaande bezorging met hoog risico beheert de bezorging voor alle niet-bezorgingsrapporten (ook wel NDR's genoemd, niet-bezorgdberichten, meldingen over de bezorgingsstatus of DSN's).

Mogelijke oorzaken voor een toename van NDR's zijn:

- Een spoofing-campagne die van invloed is op een van de klanten die de service gebruiken.
- Een directory oogst aanval.
- Een spam-aanval.
- Een malafide e-mailserver.

Al deze problemen kunnen leiden tot een plotse toename van het aantal NR's dat door de service wordt verwerkt. Vaak lijken deze NR's spam te zijn naar andere e-mailservers en -services (ook wel _[backscatter genoemd).](backscatter-messages-and-eop.md)_
