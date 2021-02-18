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
description: Lees hoe de bezorgingsgroepen worden gebruikt om de reputatie van e-mailservers in de Microsoft 365-datacenters te beschermen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 89aac1478d3e5840df4379b9f49832b79d0e133a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289803"
---
# <a name="outbound-delivery-pools"></a>Uitgaande bezorgingspools

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

E-mailservers in de Microsoft 365-datacenters kunnen tijdelijk geen spam meer verzenden. Bijvoorbeeld een malware- of kwaadaardige spam-aanval in een on-premises e-mailorganisatie die uitgaande e-mail verzendt via Microsoft 365 of gekromde Microsoft 365-accounts. Aanvallers proberen ook detectie te voorkomen door berichten door te sturen via Doorsturen van Microsoft 365.

Deze scenario's kunnen ertoe leiden dat het IP-adres van de betrokken Servers van het Microsoft 365-datacenter op blokkeringslijsten van derden wordt weergegeven. Doel-e-mailorganisaties die deze blokkeringslijsten gebruiken, weigeren e-mail van deze berichtenbronnen.

## <a name="high-risk-delivery-pool"></a>Bezorgingsgroep met hoog risico
Om dit te voorkomen, worden alle uitgaande berichten van servers in het Microsoft 365-datacenter die als spam worden beschouwd of die de verzendende limieten van het [service-](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) of [uitgaande spambeleid](configure-the-outbound-spam-policy.md) overschrijden, verzonden via de bezorgingsgroep met hoog risico.

De bezorgingsgroep met hoog risico is een afzonderlijke IP-adresgroep voor uitgaande e-mail die alleen wordt gebruikt voor het verzenden van berichten van een lage kwaliteit (bijvoorbeeld spam en [backscatter).](backscatter-messages-and-eop.md) Het gebruik van de groep met hoog risico helpt voorkomen dat de normale IP-adresgroep voor uitgaande e-mail spam verstuurt. De normale IP-adresgroep voor uitgaande e-mail behoudt de reputatie van het verzenden van berichten van hoge kwaliteit, waardoor de kans wordt verkleind dat dit IP-adres wordt weergegeven op blokkeerlijsten met IP-adressen.

De zeer reële mogelijkheid dat IP-adressen in de bezorgingsgroep met hoog risico op ip-blokkeringslijsten worden geplaatst, blijft bestaan, maar dit is volgens het ontwerp. Bezorging bij de beoogde geadresseerden is niet gegarandeerd, omdat veel e-mailorganisaties geen berichten van de bezorgingsgroep met hoog risico accepteren.

Zie Uitgaande spam beheersen [voor meer informatie.](outbound-spam-controls.md)

> [!NOTE]
> Berichten waarin het bron-e-maildomein geen A-record heeft en geen MX-record die is gedefinieerd in openbare DNS, worden altijd omgeleid via de bezorgingsgroep met hoog risico, ongeacht de spam- of verzendingslimiet.

### <a name="bounce-messages"></a>Niet-verzonden berichten

De uitgaande bezorgingsgroep met hoog risico beheert de bezorging van alle niet-bezorgingsrapporten (ook wel NDR's, niet-bezorgdberichten, meldingen over de afleveringsstatus of DSN's genoemd).

Mogelijke oorzaken van een toename van NDR's zijn:

- Een spoofing-campagne die van invloed is op een van de klanten die de service gebruiken.
- Een aanval van een directory-aanval.
- Een spam-aanval.
- Een malafide e-mailserver.

Al deze problemen kunnen ertoe leiden dat het aantal NDR's dat door de service wordt verwerkt, plotseling toeneemt. Vaak lijken deze NR's spam te zijn naar andere e-mailservers en -services (ook wel _[backscatter genoemd).](backscatter-messages-and-eop.md)_

## <a name="relay-pool"></a>Relaygroep

Berichten die worden doorgestuurd of doorgestuurd via Microsoft 365, worden verzonden met een speciale relaygroep, aangezien Microsoft 365 niet als de werkelijke afzender moet worden gezien voor de uiteindelijke bestemming. Het is ook belangrijk dat we dit verkeer isoleren, omdat er legitieme en ongeldige scenario's zijn voor het automatisch doorveren of door te sturen van e-mail uit Microsoft 365. Net als bij de bezorgingsgroep met hoog risico wordt een aparte IP-adresgroep gebruikt voor doorgestuurde e-mail. Deze adresgroep wordt niet gepubliceerd omdat deze vaak kan worden gewijzigd.

Microsoft 365 moet verifiëren of de oorspronkelijke afzender legitiem is, zodat we het doorgestuurde bericht met vertrouwen kunnen bezorgen. Dit kan alleen als e-mailverificatie (SPF, DKIM en DMARC) binnenkomt. In gevallen waarin we de afzender kunnen verifiëren, gebruiken we Rewriting (Afzender) om de ontvanger te laten weten dat het doorgestuurde bericht afkomstig is van een vertrouwde bron. U kunt meer lezen over hoe dat werkt en wat u kunt doen om ervoor te zorgen dat het verzendende domein verificatie passeert in [SRS (Sender Rewriting Scheme).](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)
