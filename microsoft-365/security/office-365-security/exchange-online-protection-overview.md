---
title: Exchange Online Protection (EOP) overzicht
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
ms.openlocfilehash: ad083e828fbed27cce4b8929c1bee3081c983c17
ms.sourcegitcommit: 76c91e7b0d3172de57988eb4576d2b91c2f9ce18
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2021
ms.locfileid: "52707282"
---
# <a name="exchange-online-protection-overview"></a>Overzicht Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) is de cloudfilterservice die uw organisatie beschermt tegen spam, malware en andere e-mailrisico's. EOP is opgenomen in alle Microsoft 365 organisaties met Exchange Online postvakken.

> [!NOTE]
> EOP is ook op zichzelf beschikbaar om on-premises postvakken en in hybride omgevingen te beveiligen om on-premises postvakken Exchange beschermen. Zie Zelfstandige Exchange Online Protection voor [meer informatie.](/exchange/standalone-eop/standaonline-eop)

De stappen voor het instellen van EOP-beveiligingsfuncties en een vergelijking met de toegevoegde beveiliging die u krijgt in Microsoft Defender voor Office 365, zie Beschermen [tegen bedreigingen.](protect-against-threats.md) De aanbevolen instellingen voor EOP-functies zijn beschikbaar in aanbevolen instellingen voor EOP en Microsoft Defender voor [Office 365 beveiliging.](recommended-settings-for-eop-and-office365.md)

In de rest van dit artikel wordt uitgelegd hoe EOP werkt en welke functies beschikbaar zijn in EOP.

## <a name="how-eop-works"></a>Hoe EOP werkt

Als u wilt weten hoe EOP werkt, kunt u zien hoe binnenkomende e-mail wordt verwerkt:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Afbeelding van e-mail van internet of feedback van klanten die wordt verzonden naar EOP en via de Verbinding, Anti-malware, Mailflow Rules-slash-Policy Filtering en Content Filtering, vóór de uitspraak van ongewenste e-mail of quarantaine, of de bezorging van e-mail van eindgebruikers.":::

1. Wanneer een binnenkomend bericht EOP binnenkomt, wordt in eerste instantie verbindingsfiltering uitgevoerd, waarmee de reputatie van de afzender wordt gecontroleerd. Het grootste deel van de spam wordt op dit moment gestopt en geweigerd door EOP. Zie [Verbindingsfiltering configureren](configure-the-connection-filter-policy.md) voor meer informatie.

2. Vervolgens wordt het bericht gecontroleerd op malware. Als malware wordt gevonden in het bericht of de bijlage(en) wordt het bericht alleen doorgeleid naar een quarantaineopslag van een beheerder. Zie Bescherming tegen malware in EOP voor meer informatie over [malwarebeveiliging.](anti-malware-protection.md)

3. Het bericht wordt voortgezet door middel van beleidsfilters, waarbij het wordt geëvalueerd op basis van e-mailstroomregels (ook wel transportregels genoemd) die u hebt gemaakt. Een regel kan bijvoorbeeld een melding naar een manager verzenden wanneer een bericht van een specifieke afzender binnenkomt.

   In on-premises organisatie met Exchange Enterprise CAL met Services-licenties, vindt op dit moment ook DLP-controles (Data Loss Prevention) in EOP (Data Loss Prevention) (Data Loss Prevention) in EOP (Data Loss Prevention) (Data Loss Prevention) in EOP (Data Loss Prevention) (DLP) (Data Loss Prevention) in EOP (Data [Loss Prevention) (Data Loss Prevention) (DLP)](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) (Data Loss Prevention) in EOP (Data Loss Prevention)

4. Het bericht wordt verzonden door middel van inhoudsfilters (antispam en anti-spoofing) waarbij schadelijke berichten worden geïdentificeerd als spam, spam met hoog vertrouwen, phishing, phishing met hoog vertrouwen of bulksgewijs (antispambeleid) of spoofing (spoofinstellingen in anti-phishingbeleid). U kunt de actie voor het bericht configureren op basis van het filteroordeel (quarantaine, verplaatsen naar de map Ongewenste e-mail, enzovoort). Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) en [anti-phishingbeleid](configure-anti-phishing-policies-eop.md)configureren in EOP voor meer informatie.

Een bericht dat al deze beveiligingslagen doorstaat, wordt bezorgd bij de geadresseerden.

Zie Bestelling en prioriteit [van e-mailbeveiliging](how-policies-and-protections-are-combined.md)voor meer informatie.

### <a name="eop-datacenters"></a>EOP-datacenters

EOP wordt uitgevoerd op een wereldwijd netwerk van datacenters die zijn ontworpen om de beste beschikbaarheid te bieden. Als een datacenter bijvoorbeeld niet beschikbaar wordt, worden e-mailberichten automatisch naar een ander datacenter gerouteerd zonder onderbreking van de service. Servers in elk datacenter accepteren namens u berichten, wat een scheidingslaag tussen uw organisatie en internet biedt, waardoor de belasting op uw servers wordt verkleind. Via dit zeer beschikbare netwerk kan Microsoft ervoor zorgen dat e-mail uw organisatie tijdig bereikt.

EOP voert load balancing uit tussen datacenters, maar alleen binnen een regio. Als u in één regio bent ingericht, worden al uw berichten verwerkt via de e-mailroutering voor die regio. In de volgende lijst ziet u hoe regionale e-mailroutering werkt voor de EOP-datacenters:

- In Europa, het Midden-Oosten en Afrika (EMEA) bevinden alle Exchange Online postvakken zich in EMEA-datacenters en worden alle berichten gerouteerd via EMEA-datacenters voor EOP-filtering.
- In Asia-Pacific (APAC) bevinden alle Exchange Online postvakken zich in APAC-datacenters en worden berichten momenteel gerouteerd via APAC-datacenters voor EOP-filtering.
- In Amerika worden services op de volgende locaties gedistribueerd:
  - Zuid-Amerika: Exchange Online postvakken bevinden zich in datacenters in Brazilië en Chili. Alle berichten worden gerouteerd via lokale datacenters voor EOP-filtering. Berichten in quarantaine worden opgeslagen in het datacenter waar de tenant zich bevindt.
  - Canada: Exchange Online postvakken bevinden zich in datacenters in Canada. Alle berichten worden gerouteerd via lokale datacenters voor EOP-filtering. Berichten in quarantaine worden opgeslagen in het datacenter waar de tenant zich bevindt.
  - Verenigde Staten: Exchange Online postvakken bevinden zich in Amerikaanse datacenters. Alle berichten worden gerouteerd via lokale datacenters voor EOP-filtering. Berichten in quarantaine worden opgeslagen in het datacenter waar de tenant zich bevindt.
- Voor de Government Community Cloud (GCC) bevinden alle Exchange Online-postvakken zich in Amerikaanse datacenters en worden alle berichten door U.S. datacenters gerouteerd voor EOP-filtering.

### <a name="eop-features"></a>EOP-functies

In deze sectie vindt u een overzicht op hoog niveau van de belangrijkste functies die beschikbaar zijn in EOP.

Zie de beschrijving van de Exchange Online Protection service voor informatie over vereisten, belangrijke limieten en beschikbaarheid van [functies in alle EOP-abonnementen.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

**Opmerkingen**:

- EOP gebruikt verschillende URL-blokkeringslijsten om bekende schadelijke koppelingen in berichten te detecteren.
- EOP gebruikt een uitgebreide lijst met domeinen die bekend staan om het verzenden van spam.
- EOP gebruikt meerdere anti-malware-engines om onze klanten altijd automatisch te beschermen.
- EOP controleert de actieve payload in de berichtoplage en alle berichtbijlagen op malware.
- Zie Aanbevolen instellingen voor EOP en Microsoft Defender voor Office 365 beveiliging voor [aanbevolen waarden voor beveiligingsbeleid.](recommended-settings-for-eop-and-office365.md)
- Zie Beschermen tegen bedreigingen voor snelle instructies voor het configureren van [beveiligingsbeleid.](protect-against-threats.md)

<br>

****
|Functie|Opmerkingen|
|---|---|
|**Beveiliging**||
|Anti-malware|[Anti-malwarebeveiliging in EOP](anti-malware-protection.md) <p> [Veelgestelde vragen over beveiliging tegen malware](anti-malware-protection-faq-eop.yml) <p> [Anti-malwarebeleid configureren in EOP](configure-anti-malware-policies.md)|
|Inkomende antispam|[Bescherming tegen spam in EOP](anti-spam-protection.md) <p> [Veelgestelde vragen over beveiliging tegen ongewenste e-mail](anti-spam-protection-faq.yml) <p> [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)|
|Uitgaande antispam|[Beveiliging tegen uitgaande spam in EOP](outbound-spam-controls.md) <p> [Uitgaande spamfilters configureren in EOP](configure-the-outbound-spam-policy.md) <p> [Automatische externe e-mail doorsturen in Microsoft 365](external-email-forwarding.md)|
|Verbindingsfilters|[Filteren van verbinding configureren](configure-the-connection-filter-policy.md)|
|Anti-phishing|[Anti-phishingbeleid in Microsoft 365](set-up-anti-phishing-policies.md) <p> [Antiphishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md)|
|Beveiliging tegen adresvervalsing (spoofing)|[Inzicht in spoof intelligence in EOP](learn-about-spoof-intelligence.md) <p> [Tenant Toestaan/Blokkeren-lijst beheren](tenant-allow-block-list.md)|
|Zero-hour auto purge (ZAP) voor bezorgde malware, spam en phishingberichten|[ZAP in Exchange Online](zero-hour-auto-purge.md)|
|Beveiligingsbeleid vooraf instellen|[Vooraf ingestelde beveiligingsbeleidsregels in EOP en Microsoft Defender voor Office 365](preset-security-policies.md) <p> [Configuratieanalyse voor beveiligingsbeleid in EOP en Microsoft Defender voor Office 365](configuration-analyzer-for-security-policies.md)|
|Lijst met tenants toestaan/blokkeren|[Tenant Toestaan/Blokkeren-lijst beheren](tenant-allow-block-list.md)|
|Lijsten blokkeren voor afzenders van berichten|[Geblokkeerde afzenderlijsten maken in EOP](create-block-sender-lists-in-office-365.md)|
|Lijsten toestaan voor afzenders van berichten|[Lijsten met veilige afzenders maken in EOP](create-safe-sender-lists-in-office-365.md)|
|Directory Based Edge Blocking (DBEB)|[Randblokkering op basis van adreslijst gebruiken om berichten te weigeren die naar ongeldige geadresseerden zijn verzonden](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|
|**Quarantaine en inzendingen**||
|Inzending door beheerder|[Beheerdersinzending gebruiken om verdachte spam, phish, URL's en bestanden naar Microsoft te verzenden](admin-submission.md)|
|Gebruikersinzendingen (aangepast postvak)|[Beleid voor gebruikersinzendingen](user-submission.md)|
|Quarantaine - beheerders|[Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md) <p> [Veelgestelde vragen over in quarantaine geplaatste berichten](quarantine-faq.yml) <p> [Berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md) <p> [Berichtkoppen tegen ongewenste e-mail in Microsoft 365](anti-spam-message-headers.md) <p> U kunt de berichtkoppen van in quarantaine geplaatste berichten analyseren met de [berichtkopanalyse op](https://mha.azurewebsites.net/).|
|Quarantaine - eindgebruikers|[Berichten in quarantaine zoeken en vrijgeven als gebruiker in EOP](find-and-release-quarantined-messages-as-a-user.md) <p> [Gebruikersspammeldingen gebruiken om in quarantaine geplaatste berichten vrij te geven en te rapporteren](use-spam-notifications-to-release-and-report-quarantined-messages.md)|
|**E-mailstroom**||
|Regels voor e-mailstroom|[Regels voor e-mailstroom (transportregels) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) <p> [Voorwaarden en uitzonderingen voor e-mailstroomregel (predicaten) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions) <p> [Acties voor e-mailstroomregel in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions) <p> [Regels voor e-mailstroom beheren in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) <p> [Procedures voor e-mailstroomregel in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-procedures)|
|Geaccepteerde domeinen|[Geaccepteerde domeinen beheren in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)|
|Verbindingslijnen|[E-mailstroom configureren met behulp van verbindingslijnen in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)|
|Verbeterde filtering voor verbindingslijnen|[Verbeterde filtering voor verbindingslijnen in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)|
|**Monitoring**||
|Bericht traceren|[Bericht traceren](message-trace-scc.md) <p> [Bericht traceren in het Exchange beheercentrum](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)|
|Samenwerkingsrapporten & e-mail|[Beveiligingsrapporten voor e-mail weergeven](view-email-security-reports.md)|
|E-mailstroomrapporten|[E-mailstroomrapporten weergeven](view-mail-flow-reports.md) <p> [E-mailstroomrapporten in het Exchange beheercentrum](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|Inzichten in e-mailstroom|[Inzichten in e-mailstroom](mail-flow-insights-v2.md) <p> [Inzichten in e-mailstroom in het Exchange beheercentrum](/exchange/monitoring/mail-flow-insights/mail-flow-insights)|
|Controlerapporten|[Controlerapporten in het Exchange beheercentrum](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)|
|Waarschuwingsbeleid|[Waarschuwingsbeleid](../../compliance/alert-policies.md)|
|**Service level agreements (SLA's) en ondersteuning**||
|Spameffectiviteit SLA|\> 99%|
|Fout-positieve ratio SLA|\< 1:250,000|
|Virusdetectie en het blokkeren van SLA|100% van bekende virussen|
|Maandelijkse uptime SLA|99.999%|
|Telefoon en web technische ondersteuning 24 uur per dag, zeven dagen per week|[Help en ondersteuning voor EOP.](help-and-support-for-eop.md)|
|**Andere functies**||
|Een geo-redundant globaal netwerk van servers|EOP wordt uitgevoerd op een wereldwijd netwerk van datacenters die zijn ontworpen om de beste beschikbaarheid te bieden. Zie de sectie [EOP-datacenters](#eop-datacenters) eerder in dit artikel voor meer informatie.|
|Bericht in de wachtrij wanneer de on-premises server geen e-mail kan accepteren|Berichten in uitstel blijven één dag in onze wachtrijen staan. Pogingen voor het opnieuw proberen van berichten zijn gebaseerd op de fout die we krijgen van het e-mailsysteem van de geadresseerde. Gemiddeld worden berichten elke 5 minuten opnieuw verzonden. Zie veelgestelde vragen [over EOP-berichten in de wachtrij, uitgestelde en niet-verzonden berichten voor meer informatie.](eop-queued-deferred-and-bounced-messages-faq.yml)|
|Office 365-berichtversleuteling beschikbaar als een invoegvoeging|Zie Versleuteling [in Office 365.](../../compliance/encryption.md)|
|||
