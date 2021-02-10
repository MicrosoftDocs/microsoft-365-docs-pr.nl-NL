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
description: Lees hoe Exchange Online Protection (EOP) u kan helpen uw on-premises e-mailorganisatie te beschermen in zelfstandige en hybride omgevingen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b84ac26333163caec6117cf042044b9bbfad0a4f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165461"
---
# <a name="exchange-online-protection-overview"></a>Overzicht Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
-    [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
-    [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Exchange Online Protection (EOP) is de cloudfilterservice die uw organisatie helpt beschermen tegen spam en malware. EOP is opgenomen in alle Microsoft 365-organisaties met Exchange Online-postvakken. EOP is echter ook beschikbaar in de volgende on-premises scenario's:

- **In een zelfstandig scenario:** EOP biedt cloudbeveiliging voor e-mail voor uw on-premises Exchange-organisatie of voor een andere on-premises SMTP-e-mailoplossing.

- **In een hybride implementatie:** EOP kan worden geconfigureerd om uw e-mailomgeving te beveiligen en e-mailroutering te controleren wanneer u een combinatie van on-premises postvakken en cloudpostvakken hebt.

In deze scenario's kan EOP het beheer van uw e-mailomgeving vereenvoudigen en een groot deel van de belasting van het onderhoud van on-premises hardware en software voorkomen.

In de rest van dit onderwerp wordt uitgelegd hoe EOP werkt in zelfstandige en hybride omgevingen.

## <a name="how-eop-works"></a>Hoe EOP werkt

Als u wilt weten hoe EOP werkt, is het belangrijk om te zien hoe binnenkomende e-mail wordt verwerkt:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Afbeelding van e-mail van internet of feedback van klanten die wordt verzonden naar EOP en via de verbinding, Anti-malware, Filtering van regels en schuine e-mailbeleidsregels, en Inhoudsfiltering, vóór het instellen van ongewenste e-mail of quarantaine, of de bezorging van e-mail door eindgebruikers.":::

- Wanneer een inkomend bericht wordt verstuurd via EOP, wordt in eerste instantie het verbindingsfilter uitgevoerd, waarmee de reputatie van de afzender wordt gecontroleerd. Het grootste deel van de spam wordt op dit moment gestopt en geweigerd door EOP. Zie [Verbindingsfiltering configureren](configure-the-connection-filter-policy.md) voor meer informatie.

- Vervolgens wordt het bericht gecontroleerd op malware. Als er malware in het bericht of de bijlage(s) wordt gevonden, wordt het bericht alleen door de beheerder in quarantaine opgeslagen. Meer informatie over het configureren van anti-malware vindt u [hier.](configure-anti-malware-policies.md)

- Berichten worden verder gefilterd door middel van beleidsfilters, waarbij deze worden geëvalueerd aan de hand van aangepaste e-mailstroomregels (ook wel transportregels genoemd) die u maakt of afdwingt op basis van een sjabloon. U kunt bijvoorbeeld een regel hebben die een melding naar een manager verzendt wanneer e-mail van een specifieke afzender binnenkomt. Op dit moment worden ook controles voor preventie van gegevensverlies (DLP) uitgevoerd (Exchange Enterprise CAL met Services).

- Vervolgens wordt inhoud gefilterd (ook wel antispam genoemd). Een bericht dat door dit filter als spam of *phish* wordt beschouwd, kan onder andere in quarantaine worden geplaatst, of in de map Ongewenste e-mail van een gebruiker. Zie Antispambeleid [configureren en](configure-your-spam-filter-policies.md) [anti-phishingbeleid configureren](configure-anti-phishing-policies-eop.md)voor meer informatie.

Elk bericht dat al deze beveiligingslagen doorstaat, wordt bezorgd bij de geadresseerde.

Zie Volgorde en prioriteit van [e-mailbeveiliging voor meer informatie.](how-policies-and-protections-are-combined.md)

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>EOP-abonnementen en -functies voor on-premises e-mailorganisaties

De beschikbare EOP-abonnementen zijn:

- **Zelfstandige versie van EOP:** uschrijft zich in EOP om uw on-premises e-mailorganisatie te beveiligen.

- **EOP-functies in Exchange Online:** elk abonnement dat Exchange Online bevat (zelfstandig of als onderdeel van Microsoft 365) maakt gebruik van EOP om uw Exchange Online-postvakken te beveiligen.

- **Exchange Enterprise CAL met Services:** als u een on-premises Exchange-organisatie hebt waar u extra Exchange Enterprise CAL met Services-licenties hebt gekocht, maakt EOP deel uit van de inbegrepen services.

Zie de servicebeschrijving van Exchange Online Protection voor informatie over vereisten, belangrijke limieten en beschikbaarheid van functies in alle [EOP-abonnementen.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>EOP instellen voor on-premises e-mailorganisaties

Het instellen van EOP kan eenvoudig zijn, met name in het geval van een kleine organisatie met een aantal nalevingsregels. Als u echter een grote organisatie met meerdere domeinen, aangepaste nalevingsregels of hybride e-mailstroom hebt, kan het instellen meer planning en tijd inplannen.

Als u EOP al hebt gekocht, zie Uw [EOP-service](set-up-your-eop-service.md) instellen om ervoor te zorgen dat u alle stappen voltooit die nodig zijn om EOP te configureren om uw berichtenomgeving te beschermen.

### <a name="eop-datacenters"></a>EOP-datacenters

EOP wordt uitgevoerd op een wereldwijd netwerk van datacenters die zijn ontworpen om de beste beschikbaarheid te bieden. Als een datacenter bijvoorbeeld niet meer beschikbaar is, worden e-mailberichten automatisch doorvergeleid naar een ander datacenter zonder onderbreking van de service. Servers in elk datacenter accepteren berichten namens u, wat een scheidingslaag biedt tussen uw organisatie en internet, waardoor de belasting van uw servers wordt verminderen. Via dit zeer beschikbare netwerk kan Microsoft ervoor zorgen dat e-mail op tijd bij uw organisatie wordt bereikt.

Met EOP wordt taakverdeling uitgevoerd tussen datacenters, maar alleen binnen een regio. Als u in één regio bent ingericht, worden al uw berichten verwerkt via de e-mailroutering voor die regio. In de volgende lijst ziet u hoe regionale e-mailroutering werkt voor de EOP-datacenters:

- In Europa, het Midden-Oost en Afrika (EMEA), bevinden alle Exchange Online-postvakken zich in EMEA-datacenters en worden alle berichten omgeleid via EMEA-datacenters voor EOP-filtering.

- In Asia-Pacific (APAC) bevinden alle Exchange Online-postvakken zich in APAC-datacenters en worden berichten momenteel gerouteerd via APAC-datacenters voor EOP-filtering.

- In Amerika zijn services verspreid over de volgende locaties:

  - Zuid-Amerika: Exchange Online-postvakken bevinden zich in datacenters in Brazilië en Chili. Alle berichten worden omgeleid via lokale datacenters voor EOP-filtering. Berichten in quarantaine worden opgeslagen in het datacenter waar de tenant zich bevindt.

  - Canada: Exchange Online-postvakken bevinden zich in datacenters in Canada. Alle berichten worden omgeleid via lokale datacenters voor EOP-filtering. Berichten in quarantaine worden opgeslagen in het datacenter waar de tenant zich bevindt.

  - Verenigde Staten: Exchange Online-postvakken bevinden zich in Amerikaanse datacenters. Alle berichten worden omgeleid via lokale datacenters voor EOP-filtering. Berichten in quarantaine worden opgeslagen in het datacenter waar de tenant zich bevindt.

- Voor de Government Community Cloud (GCC) bevinden alle Exchange Online-postvakken zich in Datacenters van de Verenigde Staten en worden alle berichten omgeleid via Amerikaanse datacenters om EOP-filters te kunnen gebruiken.

## <a name="eop-help-for-admins"></a>Help bij EOP voor beheerders

De Help-inhoud voor EOP-beheerders bestaat uit de volgende categorieën op het hoogste niveau:

- [EOP, dag 1,](protect-against-threats.md)configureren voor Beheerders van Microsoft Defender voor Office 365: EOP-beveiligings- en detectiehulpprogramma's configureren in de kern van Microsoft Defender voor Office 365.

- [EOP-functies:](eop-features.md)biedt een lijst met functies die beschikbaar zijn in EOP.

- [Uw EOP-service instellen:](set-up-your-eop-service.md)biedt stappen voor het instellen van uw EOP-service en koppelingen naar aanvullende informatie.

- [Overstappen van Google Postini op EOP, de Barracuda Spam and Virus Firewall of Cisco IronPort:](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)hier wordt het proces beschreven voor het overstappen op EOP van een ander e-mailbeveiligingsproduct.

- [Geadresseerden beheren in zelfstandige EOP:](manage-recipients-in-eop.md)Hier wordt beschreven hoe u e-mailgebruikers en -groepen beheert in EOP.

- [E-mailstroom in EOP:](mail-flow-in-eop.md)hier wordt beschreven hoe u aangepaste scenario's voor e-mailstromen configureert met connectors, hoe u domeinen beheert die aan de service zijn gekoppeld en hoe u de functie Directory Based Edge Blocking (DBEB) inschakelen.

- [Aanbevolen procedures voor het configureren van EOP:](best-practices-for-configuring-eop.md)hier worden aanbevolen configuratie-instellingen en aandachtspunten beschreven voor nadat u de service hebt ingesteld en ingericht.

- [Controlerapporten in zelfstandige EOP:](auditing-reports-in-eop.md)hier wordt beschreven hoe u controlerapporten gebruikt om configuratiewijzigingen in de service bij te houden.

- [Bescherming tegen spam en malware in EOP:](anti-spam-and-anti-malware-protection.md)hier worden spamfilters en malwarefilters beschreven en wordt beschreven hoe u deze kunt aanpassen om zo goed mogelijk te voldoen aan de behoeften van uw organisatie. Beschrijft ook de taken die beheerders en eindgebruikers in quarantaine kunnen uitvoeren.

- [Rapportage en bericht traceren in Exchange Online Protection:](reporting-and-message-trace-in-exchange-online-protection.md)hier worden de beschikbare rapporten en hulpprogramma's voor probleemoplossing beschreven.

- [Exchange-beheercentrum in zelfstandige EOP:](exchange-admin-center-in-exchange-online-protection-eop.md)hier wordt beschreven hoe u toegang krijgt tot en navigeert door de beheerinterface van het Exchange-beheercentrum (EAC) om uw EOP-service te beheren.

- [Exchange Online Protection PowerShell:](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell)biedt informatie over externe PowerShell waarmee u uw EOP-service vanaf de opdrachtregel kunt beheren.

- [Help en ondersteuning voor EOP](help-and-support-for-eop.md) Biedt informatie over het verkrijgen van hulp en technische ondersteuning.
