---
title: Overzicht van Exchange Online Protection (EOP)
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
ms.custom:
- seo-marvel-apr2020
description: Ontdek hoe Exchange Online Protection (EOP) uw on-premises e-mailorganisatie kan beschermen in zelfstandige en hybride omgevingen.
ms.openlocfilehash: 7a019b2651eda114bab8dcf9df6d9a6201558704
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206683"
---
# <a name="exchange-online-protection-overview"></a>Overzicht van Exchange Online Protection

Exchange Online Protection (EOP) is de cloudgebaseerde filterservice die uw organisatie beschermt tegen spam en malware. EOP is opgenomen in alle Microsoft 365-organisaties met Exchange Online-postvakken.

Maar EOP is ook beschikbaar in de volgende on-premises scenario's:

- **In een zelfstandig scenario:** EOP biedt cloudgebaseerde e-mailbeveiliging voor uw on-premises Exchange-organisatie of voor een andere on-premises SMTP-e-mailoplossing.

- **In een hybride implementatie**: EOP kan worden geconfigureerd om uw e-mailomgeving te beschermen en e-mailroutering te beheren wanneer u een mix van on-premises en cloudpostvakken hebt.

In deze scenario's kan EOP het beheer van uw e-mailomgeving vereenvoudigen en veel van de lasten verlichten die gepaard gaan met het onderhouden van on-premises hardware en software.

De rest van dit onderwerp legt uit hoe EOP werkt in standalone en hybride omgevingen.

## <a name="how-eop-works"></a>Hoe EOP werkt

Om te begrijpen hoe EOP werkt, helpt het om te zien hoe het binnenkomende e-mail verwerkt:

![Diagram voor e-mailproces](../../media/emailprocessingineop1.png)

- Een binnenkomend bericht gaat in eerste instantie door het filteren van verbindingen, die de reputatie van de afzender controleert en het bericht inspecteert op malware. De meerderheid van de spam wordt gestopt op dit punt en verwijderd door EOP. Zie [Verbindingsfiltering configureren](configure-the-connection-filter-policy.md) voor meer informatie.

- Berichten worden voortgezet door middel van beleidsfiltering, waarbij berichten worden geëvalueerd aan de hand van aangepaste regels voor e-mailstromen (ook wel transportregels genoemd) die u maakt of afdwingt vanuit een sjabloon. U bijvoorbeeld een regel hebben die een melding naar een manager verzendt wanneer e-mail van een specifieke afzender wordt binnengekomen. Gegevensverliespreventie (DLP) controles vinden ook plaats op dit punt (Exchange Enterprise CAL with Services).

- Vervolgens gaan berichten door antispamfiltering (ook wel contentfiltering genoemd). Een bericht dat is bepaald dat het spam is, kan onder andere naar de map Ongewenste e-mail van een gebruiker of naar de quarantaine worden verzonden. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.

- Nadat een bericht al deze beveiligingslagen met succes heeft doorgegeven, wordt het aan de ontvanger geleverd.

Zie [Orde en voorrang van e-mailbeveiliging](how-policies-and-protections-are-combined.md)voor meer informatie.

### <a name="eop-datacenters"></a>EOP-datacenters

EOP draait op een wereldwijd netwerk van datacenters die zijn ontworpen om de beste beschikbaarheid te bieden. Als een datacenter bijvoorbeeld niet meer beschikbaar is, worden e-mailberichten automatisch doorgestuurd naar een ander datacenter zonder onderbreking van de service. Servers in elk datacenter accepteren namens u berichten, waardoor een scheidingslaag ontstaat tussen uw organisatie en het internet, waardoor de belasting op uw servers wordt verminderd. Via dit zeer beschikbare netwerk kan Microsoft ervoor zorgen dat e-mail uw organisatie tijdig bereikt.

EOP voert taakverdeling uit tussen datacenters, maar alleen binnen een regio. Als u in één regio bent ingericht, worden al uw berichten verwerkt met behulp van de e-mailroutering voor die regio. In de volgende lijst ziet u hoe regionale e-mailroutering werkt voor de EOP-datacenters:

- In Europa, het Midden-Oosten en Afrika (EMEA) bevinden alle Exchange Online-postvakken zich in EMEA-datacenters en worden alle berichten doorgestuurd via EMEA-datacenters voor EOP-filtering.

- In Asia-Pacific (APAC) bevinden alle Exchange Online-postvakken zich in APAC-datacenters en worden berichten momenteel doorgestuurd via APAC-datacenters voor EOP-filtering.

- In Noord- en Zuid-Amerika bevinden alle Exchange Online-postvakken zich in Amerikaanse datacenters, met uitzondering van Zuid-Amerika, waar datacenters in Brazilië en Chili worden gebruikt en in Canada waar datacenters in Canada worden gebruikt. Alle e-mailberichten, inclusief berichten voor klanten in Zuid-Amerika en Canada, worden doorgestuurd via lokale datacenters voor EOP-filtering; in quarantaine geplaatste e-mail wordt opgeslagen in het datacenter waar de tenant zich bevindt.

- Voor de Government Community Cloud (GCC) bevinden alle Exchange Online-postvakken zich in datacenters in de VS en worden alle berichten doorgestuurd via Amerikaanse datacenters voor EOP-filtering.

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>EOP-plannen en -functies voor on-premises e-mailorganisaties

De beschikbare EOP-abonnementen zijn:

- **EOP standalone:** U schrijft zich in voor EOP om uw on-premises e-mailorganisatie te beschermen.

- **EOP-functies in Exchange Online:** elk abonnement dat Exchange Online bevat (zelfstandig of als onderdeel van Microsoft 365) maakt gebruik van EOP om uw Exchange Online-postvakken te beschermen.

- **Exchange Enterprise CAL with Services:** Als u een on-premises Exchange-organisatie hebt waar u aanvullende Exchange Enterprise CAL met Services-licenties hebt gekocht, maakt EOP deel uit van de meegeleverde services.

Zie de beschrijving van de [Exchange Online Protection-service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)voor informatie over vereisten, belangrijke limieten en beschikbaarheid van functies voor alle EOP-abonnementen.

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>EOP instellen voor on-premises e-mailorganisaties

Het opzetten van EOP kan eenvoudig zijn, vooral in het geval van een kleine organisatie met een handvol nalevingsregels. Als u echter een grote organisatie hebt met meerdere domeinen, aangepaste nalevingsregels of hybride e-mailstroom, kan het instellen meer planning en tijd in beslag nemen.

Zie EOP-service [instellen](set-up-your-eop-service.md) om ervoor te zorgen dat u alle stappen die nodig zijn om EOP te configureren om uw berichtenomgeving te beschermen, instelt als u EOP al hebt gekocht.

## <a name="eop-help-for-admins"></a>EOP Help voor beheerders

De Help-inhoud voor EOP-beheerders bestaat uit de volgende categorieën op het hoogste niveau:

- [Overzicht van Exchange Online Protection](exchange-online-protection-overview.md): introduceert hoe EOP werkt en biedt links naar aanvullende informatie.

- [EOP-functies:](eop-features.md)biedt een lijst met functies die beschikbaar zijn in EOP.

- [Uw EOP-service instellen:](set-up-your-eop-service.md)biedt stappen voor het instellen van uw EOP-service en koppelingen naar aanvullende informatie.

- [Overschakelen naar EOP van Google Postini, de Barracuda Spam en Virus Firewall, of Cisco IronPort:](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)Beschrijft het proces voor de overstap naar EOP van een ander e-mail beveiligingsproduct.

- [Geadresseerden beheren in zelfstandige EOP:](manage-recipients-in-eop.md)beschrijft hoe u e-mailgebruikers en -groepen in EOP beheert.

- [E-mailstroom in EOP:](mail-flow-in-eop.md)beschrijft hoe u aangepaste e-mailstroomscenario's configureert met behulp van connectors, hoe domeinen die aan de service zijn gekoppeld beheren en hoe u de functie DBEB (Directory Based Edge Blocking) inschakelt.

- [Aanbevolen procedures voor het configureren van EOP:](best-practices-for-configuring-eop.md)beschrijft aanbevolen configuratie-instellingen en overwegingen voor nadat u uw service hebt ingesteld en in- of ingericht.

- [Controlerapporten in zelfstandige EOP:](auditing-reports-in-eop.md)beschrijft hoe u controlerapporten gebruiken om configuratiewijzigingen in de service bij te houden.

- [Bescherming tegen spam en malware bestrijding in EOP](anti-spam-and-anti-malware-protection.md): Beschrijft spamfiltering en malwarefiltering en laat zien hoe u deze aanpassen aan de behoeften van uw organisatie. Beschrijft ook taken die beheerders en eindgebruikers kunnen uitvoeren op in quarantaine geplaatste berichten.

- [Rapportage en berichttracering in Exchange Online Protection:](reporting-and-message-trace-in-exchange-online-protection.md)beschrijft de rapporten en hulpprogramma's voor probleemoplossing die beschikbaar zijn.

- [Exchange-beheercentrum in zelfstandige EOP:](exchange-admin-center-in-exchange-online-protection-eop.md)beschrijft hoe u toegang krijgt tot en navigeert via de Beheerinterface van het Exchange-beheercentrum (EAC) om uw EOP-service te beheren.

- [Exchange Online Protection PowerShell:](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell)biedt informatie over externe PowerShell, waarmee u uw EOP-service vanaf de opdrachtregel beheren.

- [Hulp en ondersteuning voor EOP](help-and-support-for-eop.md) Geeft informatie over het verkrijgen van hulp en technische ondersteuning.
