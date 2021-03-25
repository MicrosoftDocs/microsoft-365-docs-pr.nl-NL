---
title: Overzicht van Exchange Online Protection (EOP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Lees hoe Exchange Online Protection (EOP) uw on-premises e-mailorganisatie kan beschermen in zelfstandige en hybride omgevingen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3df7b376d559535e168bfa21d2a8770b19569c4f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204822"
---
# <a name="exchange-online-protection-overview"></a>Overzicht Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) is de cloudfilterservice die uw organisatie helpt beschermen tegen spam en malware. EOP is opgenomen in alle Microsoft 365-organisaties met Exchange Online-postvakken. EOP is echter ook beschikbaar in de volgende on-premises scenario's:

- **In een zelfstandig scenario:** EOP biedt e-mailbeveiliging in de cloud voor uw on-premises Exchange-organisatie of voor een andere on-premises SMTP-e-mailoplossing.

- **In een hybride implementatie:** EOP kan worden geconfigureerd om uw e-mailomgeving te beveiligen en de routering van e-mail te controleren wanneer u een combinatie hebt van on-premises postvakken en cloudpostvakken.

In deze scenario's kan EOP het beheer van uw e-mailomgeving vereenvoudigen en veel van de lasten verlichten die het onderhoud van on-premises hardware en software met zich mee brengen.

In de rest van dit onderwerp wordt uitgelegd hoe EOP werkt in zelfstandige en hybride omgevingen.

## <a name="how-eop-works"></a>Hoe EOP werkt

Als u wilt weten hoe EOP werkt, kunt u zien hoe binnenkomende e-mail wordt verwerkt:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Afbeelding van e-mail van internet- of klantfeedback die wordt verzonden naar EOP en via de Verbinding, Anti-malware, Mailflow Rules-slash-Policy Filtering en Content Filtering, vóór de uitspraak van ongewenste e-mail of quarantaine, of de bezorging van e-mail van eindgebruikers.":::

- Wanneer een binnenkomend bericht EOP binnenkomt, wordt in eerste instantie verbindingsfiltering uitgevoerd, waarmee de reputatie van de afzender wordt gecontroleerd. Het grootste deel van de spam wordt op dit moment gestopt en geweigerd door EOP. Zie [Verbindingsfiltering configureren](configure-the-connection-filter-policy.md) voor meer informatie.

- Vervolgens wordt het bericht gecontroleerd op tekenen van malware. Als malware wordt gevonden in het bericht of de bijlage(en) wordt het bericht alleen doorgeleid naar een quarantaineopslag van een beheerder. Hier vindt u meer informatie [](configure-anti-malware-policies.md)over het configureren van anti-malware.

- Berichten gaan door met het filteren van beleid, waarbij ze worden geëvalueerd op basis van aangepaste regels voor e-mailstroom (ook wel transportregels genoemd) die u maakt of afdwingt op basis van een sjabloon. U kunt bijvoorbeeld een regel hebben die een melding naar een manager verzendt wanneer e-mail van een specifieke afzender binnenkomt. DLP-controles (Data Loss Prevention) worden ook uitgevoerd op dit moment (Exchange Enterprise CAL with Services).

- Vervolgens wordt het bericht door inhoudsfilters (ook wel antispam genoemd) gestuurd. Een bericht dat dit filter spam of *phish* is, kan onder andere worden verzonden naar quarantaine of de map Ongewenste e-mail van een gebruiker. Zie [Antispambeleid configureren en](configure-your-spam-filter-policies.md) [Anti-phishingbeleid configureren](configure-anti-phishing-policies-eop.md)voor meer informatie.

Elk bericht dat al deze beveiligingslagen doorstaat, wordt bezorgd bij de geadresseerde.

Zie Bestelling en prioriteit [van e-mailbeveiliging](how-policies-and-protections-are-combined.md)voor meer informatie.

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>EOP-abonnementen en -functies voor on-premises e-mailorganisaties

De beschikbare EOP-abonnementsabonnementen zijn:

- **Zelfstandige EOP:** U kunt zich registreren voor EOP om uw on-premises e-mailorganisatie te beschermen.

- **EOP-functies in Exchange Online:** Elk abonnement met Exchange Online (zelfstandig of als onderdeel van Microsoft 365) gebruikt EOP om uw Exchange Online-postvakken te beschermen.

- **Exchange Enterprise CAL with Services:** Als u een on-premises Exchange-organisatie hebt waar u extra Exchange Enterprise CAL met Services-licenties hebt gekocht, maakt EOP deel uit van de meegeleverde services.

Zie de beschrijving van de Exchange Online Protection-service voor informatie over vereisten, belangrijke limieten en beschikbaarheid van functies in alle [EOP-abonnementsabonnementen.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>EOP instellen voor on-premises e-mailorganisaties

Het instellen van EOP kan eenvoudig zijn, met name in het geval van een kleine organisatie met een handjevol nalevingsregels. Als u echter een grote organisatie hebt met meerdere domeinen, aangepaste complianceregels of hybride e-mailstroom, kan het instellen meer planning en tijd in de tijd duren.

Als u EOP al hebt gekocht, zie Uw [EOP-service](set-up-your-eop-service.md) instellen om ervoor te zorgen dat u alle stappen voltooit die nodig zijn om EOP te configureren om uw berichtenomgeving te beschermen.

### <a name="eop-datacenters"></a>EOP-datacenters

EOP wordt uitgevoerd op een wereldwijd netwerk van datacenters die zijn ontworpen om de beste beschikbaarheid te bieden. Als een datacenter bijvoorbeeld niet beschikbaar wordt, worden e-mailberichten automatisch naar een ander datacenter gerouteerd zonder onderbreking van de service. Servers in elk datacenter accepteren namens u berichten, wat een scheidingslaag tussen uw organisatie en internet biedt, waardoor de belasting op uw servers wordt verkleind. Via dit zeer beschikbare netwerk kan Microsoft ervoor zorgen dat e-mail uw organisatie tijdig bereikt.

EOP voert load balancing uit tussen datacenters, maar alleen binnen een regio. Als u in één regio bent ingericht, worden al uw berichten verwerkt via de e-mailroutering voor die regio. In de volgende lijst ziet u hoe regionale e-mailroutering werkt voor de EOP-datacenters:

- In Europa, het Midden-Oosten en Afrika (EMEA) bevinden alle Exchange Online-postvakken zich in EMEA-datacenters en worden alle berichten door EMEA-datacenters gerouteerd voor EOP-filtering.

- In Asia-Pacific (APAC) bevinden alle Exchange Online-postvakken zich in APAC-datacenters en worden berichten momenteel gerouteerd via APAC-datacenters voor EOP-filtering.

- In Amerika worden services op de volgende locaties gedistribueerd:

  - Zuid-Amerika: Exchange Online-postvakken bevinden zich in datacenters in Brazilië en Chili. Alle berichten worden gerouteerd via lokale datacenters voor EOP-filtering. Berichten in quarantaine worden opgeslagen in het datacenter waar de tenant zich bevindt.

  - Canada: Exchange Online-postvakken bevinden zich in datacenters in Canada. Alle berichten worden gerouteerd via lokale datacenters voor EOP-filtering. Berichten in quarantaine worden opgeslagen in het datacenter waar de tenant zich bevindt.

  - Verenigde Staten: Exchange Online-postvakken bevinden zich in Amerikaanse datacenters. Alle berichten worden gerouteerd via lokale datacenters voor EOP-filtering. Berichten in quarantaine worden opgeslagen in het datacenter waar de tenant zich bevindt.

- Voor de Government Community Cloud (GCC) bevinden alle Exchange Online-postvakken zich in Amerikaanse datacenters en worden alle berichten gerouteerd via Amerikaanse datacenters voor EOP-filtering.

## <a name="eop-help-for-admins"></a>EOP Help voor beheerders

De Help-inhoud voor EOP-beheerders bestaat uit de volgende categorieën op het hoogste niveau:

- EOP, dag 1, configureren voor Microsoft Defender voor [Office 365-beheerders:](protect-against-threats.md)EOP-beveiligings- en detectiehulpmiddelen configureren in de kern van Microsoft Defender voor Office 365.

- [EOP-functies:](eop-features.md)bevat een lijst met functies die beschikbaar zijn in EOP.

- [Uw EOP-service instellen:](set-up-your-eop-service.md)biedt stappen voor het instellen van uw EOP-service en koppelingen naar aanvullende informatie.

- [Overstappen op EOP vanuit Google Postini, de Barracuda Spam- en Virusfirewall of Cisco IronPort:](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)Beschrijft het proces voor het overstappen van een ander e-mailbeveiligingsproduct naar EOP.

- [Geadresseerden beheren in zelfstandige EOP:](manage-recipients-in-eop.md)Hier wordt beschreven hoe u e-mailgebruikers en groepen in EOP kunt beheren.

- [E-mailstroom in EOP:](mail-flow-in-eop.md)Hier wordt beschreven hoe u aangepaste scenario's voor e-mailstroom configureert met behulp van verbindingslijnen, hoe u domeinen beheert die aan de service zijn gekoppeld en hoe u de dbeb-functie (Directory Based Edge Blocking) inschakelen.

- [Aanbevolen procedures voor het configureren van EOP:](best-practices-for-configuring-eop.md)beschrijft aanbevolen configuratie-instellingen en aandachtspunten voor nadat u uw service hebt ingesteld en ingericht.

- [Controlerapporten in zelfstandige EOP:](auditing-reports-in-eop.md)hier wordt beschreven hoe u controlerapporten gebruikt om configuratiewijzigingen in de service bij te houden.

- [Bescherming tegen spam en anti-malware in EOP:](anti-spam-and-anti-malware-protection.md)beschrijft spamfilters en malwarefilters en laat zien hoe u deze kunt aanpassen aan de behoeften van uw organisatie. Ook worden taken beschreven die beheerders en eindgebruikers kunnen uitvoeren op in quarantaine geplaatste berichten.

- [Rapportage en bericht traceren in Exchange Online Protection:](reporting-and-message-trace-in-exchange-online-protection.md)Beschrijft de rapporten en hulpprogramma's voor probleemoplossing die beschikbaar zijn.

- [Exchange-beheercentrum in zelfstandige EOP:](exchange-admin-center-in-exchange-online-protection-eop.md)hier wordt beschreven hoe u toegang krijgt tot en navigeert via de beheerinterface van het Exchange-beheercentrum (EAC) om uw EOP-service te beheren.

- [Exchange Online Protection PowerShell:](/powershell/exchange/exchange-online-protection-powershell)biedt informatie over externe PowerShell, waarmee u uw EOP-service vanaf de opdrachtregel kunt beheren.

- [Hulp en ondersteuning voor EOP](help-and-support-for-eop.md) Geeft informatie over het verkrijgen van hulp en technische ondersteuning.