---
title: Overzicht van Exchange Online Protection
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
description: Microsoft Exchange Online Protection (EOP) is een cloudgebaseerde e-mailfilterservice die uw organisatie beschermt tegen spam en malware, en functies bevat om uw organisatie te beschermen tegen schendingen van het berichtenbeleid.
ms.openlocfilehash: a87b9b40d1a95f7c4da194ffd2138aa9d1726032
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812042"
---
# <a name="exchange-online-protection-overview"></a>Overzicht van Exchange Online Protection

Microsoft Exchange Online Protection (EOP) is een cloudgebaseerde e-mailfilterservice die uw organisatie beschermt tegen spam en malware, en functies bevat om uw organisatie te beschermen tegen schendingen van het berichtenbeleid. EOP kan het beheer van uw berichtenomgeving vereenvoudigen en veel van de lasten verlichten die gepaard gaan met het onderhouden van on-premises hardware en software.

In de volgende lijst wordt beschreven hoe u EOP gebruiken voor berichtenbescherming:

- **In een zelfstandig scenario:** EOP biedt cloudgebaseerde e-mailbeveiliging voor uw on-premises Exchange-organisatie of voor een andere on-premises SMTP-e-mailoplossing.

- **Als onderdeel van Exchange Online**: EOP is de ingebouwde bescherming voor cloudgehoste postvakken in Exchange Online en Office 365. Zie [Beschermen tegen bedreigingen](protect-against-threats.md) voor hulp bij het configureren van deze Exchange Online-mogelijkheden.

- **In een hybride implementatie:** EOP kan worden geconfigureerd om uw berichtenomgeving te beschermen en e-mailroutering te beheren wanneer u een mix van on-premises en cloudpostvakken hebt.

> [!NOTE]
> Deze Exchange Online Protection-artikelen zijn van toepassing op hybride en on-premises omgevingen.

## <a name="how-eop-works"></a>Hoe EOP werkt

Om te begrijpen hoe EOP werkt, helpt het om te zien hoe het binnenkomende e-mail verwerkt:

![Diagram voor e-mailproces.](../../media/GitHubBugs/emailprocessingineop1.png)

Een binnenkomend bericht gaat in eerste instantie door het filteren van verbindingen, die de reputatie van de afzender controleert en het bericht inspecteert op malware. De meerderheid van de spam wordt gestopt op dit punt en verwijderd door EOP. Berichten worden voortgezet door middel van beleidsfiltering, waarbij berichten worden geëvalueerd aan de hand van aangepaste regels voor e-mailstromen (ook wel transportregels genoemd) die u maakt of afdwingt vanuit een sjabloon. U bijvoorbeeld een regel hebben die een melding naar een manager verzendt wanneer e-mail van een specifieke afzender wordt binnengekomen. (Gegevensverliespreventiecontroles vinden ook op dit punt plaats, als u die functie hebt; raadpleeg voor informatie over de beschikbaarheid van functies de beschrijving van de [Exchange Online Protection-service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).) Vervolgens gaan berichten door inhoudsfiltering, waarbij inhoud wordt gecontroleerd op terminologie of eigenschappen die gemeenschappelijk zijn voor spam. Een bericht dat door het inhoudsfilter als spam wordt aangemerkt, kan worden verzonden naar de map Ongewenste e-mail van een gebruiker of naar de quarantaine, onder andere opties (waaronder Postvak IN of aangepaste map), op basis van uw instellingen. Nadat een bericht al deze beveiligingslagen met succes heeft doorgegeven, wordt het aan de ontvanger geleverd.

### <a name="eop-datacenters"></a>EOP-datacenters

EOP draait op een wereldwijd netwerk van datacenters die zijn ontworpen om de beste beschikbaarheid te bieden. Als een datacenter bijvoorbeeld niet meer beschikbaar is, worden e-mailberichten automatisch doorgestuurd naar een ander datacenter zonder onderbreking van de service. Servers in elk datacenter accepteren namens u berichten, waardoor een scheidingslaag ontstaat tussen uw organisatie en het internet, waardoor de belasting op uw servers wordt verminderd. Via dit zeer beschikbare netwerk kan Microsoft ervoor zorgen dat e-mail uw organisatie tijdig bereikt.

EOP voert taakverdeling uit tussen datacenters, maar alleen binnen een regio. Als u in één regio bent ingericht, worden al uw berichten verwerkt met behulp van de e-mailroutering voor die regio. In de volgende lijst ziet u hoe regionale e-mailroutering werkt voor de EOP-datacenters:

- In Europa, het Midden-Oosten en Afrika (EMEA) bevinden alle Exchange Online-postvakken zich in EMEA-datacenters en worden alle berichten doorgestuurd via EMEA-datacenters voor EOP-filtering.

- In Asia-Pacific (APAC) bevinden alle Exchange Online-postvakken zich in APAC-datacenters en worden berichten momenteel doorgestuurd via APAC-datacenters voor EOP-filtering.

- In Noord- en Zuid-Amerika bevinden alle Exchange Online-postvakken zich in Amerikaanse datacenters, met uitzondering van Zuid-Amerika, waar datacenters in Brazilië en Chili worden gebruikt en in Canada waar datacenters in Canada worden gebruikt. Alle e-mailberichten, inclusief berichten voor klanten in Zuid-Amerika en Canada, worden doorgestuurd via lokale datacenters voor EOP-filtering; in quarantaine geplaatste e-mail wordt opgeslagen in het datacenter waar de tenant zich bevindt.

- Voor de Government Community Cloud (GCC) bevinden alle Exchange Online-postvakken zich in datacenters in de VS en worden alle berichten doorgestuurd via Amerikaanse datacenters voor EOP-filtering.

## <a name="eop-plans-and-features"></a>EOP-abonnementen en -functies

De beschikbare EOP-abonnementen zijn:

- **EOP standalone:** U schrijft zich in voor EOP om uw on-premises e-mailorganisatie te beschermen.

- **EOP-functies in Exchange Online:** elk abonnement dat Exchange Online bevat (zelfstandig of als onderdeel van Office 365) maakt gebruik van EOP om uw Exchange Online-postvakken te beschermen.

- **Exchange Enterprise CAL with Services:** Als u een on-premises Exchange-organisatie hebt waar u aanvullende Exchange Enterprise CAL met Services-licenties hebt gekocht, maakt EOP deel uit van de meegeleverde services.

Zie de beschrijving van de [Exchange Online Protection-service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)voor informatie over vereisten, belangrijke limieten en beschikbaarheid van functies voor alle EOP-abonnementen.

## <a name="setting-up-eop"></a>EOP instellen

Het opzetten van EOP kan eenvoudig zijn, vooral in het geval van een kleine organisatie met een handvol nalevingsregels. Als u echter een grote organisatie hebt met meerdere domeinen, aangepaste nalevingsregels of hybride e-mailstroom, kan het instellen meer planning en tijd in beslag nemen.

Zie EOP-service [instellen](set-up-your-eop-service.md) om ervoor te zorgen dat u alle stappen die nodig zijn om EOP te configureren om uw berichtenomgeving te beschermen, instelt als u EOP al hebt gekocht.

## <a name="for-more-information"></a>Voor meer informatie

[EOP-functies](eop-features.md)

[Algemene Faq van EOP](eop-general-faq.md)

[Veelgestelde vragen over eop-wachtrijen, uitgestelde en teruggestuurde berichten](eop-queued-deferred-and-bounced-messages-faq.md)

[Veelgestelde vragen over gedelegeerd beheer](delegated-administration-faq.md)

[Domeinen en instellingen verplaatsen van de ene EOP-organisatie naar een andere EOP-organisatie](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
