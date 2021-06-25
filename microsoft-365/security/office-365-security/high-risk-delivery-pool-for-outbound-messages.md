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
ms.openlocfilehash: 85f200cf226a050762db4ea37255f71241d1f98c
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137716"
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


### <a name="relay-pool"></a>Relaisgroep

Berichten die in bepaalde scenario's via Microsoft 365 worden doorgestuurd of doorgestuurd, worden verzonden met een speciale relaisgroep, omdat de bestemming de Microsoft 365 niet moet beschouwen als de werkelijke afzender. Het is belangrijk dat we dit e-mailverkeer isoleren, omdat er legitieme en ongeldige scenario's zijn voor het automatisch doorsturen of doorsturen van e-mail Microsoft 365. Net als bij de groep met een hoog risico wordt een aparte IP-adresgroep gebruikt voor doorgestuurde e-mail. Deze adresgroep wordt niet gepubliceerd omdat deze vaak kan worden gewijzigd en het maakt geen deel uit van de gepubliceerde SPF-record voor Microsoft 365.

Microsoft 365 moet controleren of de oorspronkelijke afzender legitiem is, zodat we het doorgestuurde bericht met vertrouwen kunnen bezorgen.

Het doorgestuurde/doorgestuurde bericht moet voldoen aan een van de volgende criteria om te voorkomen dat de doorgestuurde groep wordt gebruikt:

- De uitgaande afzender is in een [geaccepteerd domein.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
- SPF wordt pas weergegeven wanneer het bericht wordt Microsoft 365.
- DKIM op het afzenderdomein wordt weergegeven wanneer het bericht wordt Microsoft 365.
 
U kunt zien dat een bericht is verzonden via de relaygroep door te kijken naar het IP-adres van de uitgaande server (de relaisgroep zal zich in het bereik 40.95.0.0/16) of door te kijken naar de naam van de uitgaande server (er staat 'rly' in de naam).

In gevallen waarin we de afzender kunnen verifiëren, gebruiken we Sender Rewriting Scheme (SRS) om het e-mailsysteem van de geadresseerde te helpen weten dat het doorgestuurde bericht afkomstig is van een vertrouwde bron. U kunt meer lezen over hoe dat werkt en wat u kunt doen om ervoor te zorgen dat het verzendende domein verificatie doorstaat in [Sender Rewriting Scheme (SRS) in Office 365.](/office365/troubleshoot/antispam/sender-rewriting-scheme)

Als DKIM werkt, moet u DKIM inschakelen voor het verzenden van domein. De fabrikam.com maakt bijvoorbeeld deel uit van contoso.com en wordt gedefinieerd in de geaccepteerde domeinen van de organisatie. Als de afzender van het bericht sender@fabrikam.com, moet DKIM zijn ingeschakeld voor fabrikam.com. U kunt lezen hoe u [DKIM](use-dkim-to-validate-outbound-email.md)kunt inschakelen om uitgaande e-mail te valideren die is verzonden vanuit uw aangepaste domein.

Als u een aangepast domein wilt toevoegen, volgt u de stappen in [Een domein toevoegen aan Microsoft 365.](../../admin/setup/add-domain.md)
