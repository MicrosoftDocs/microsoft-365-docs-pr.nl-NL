---
title: EOP-functies
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: De volgende tabel bevat een lijst met functies die beschikbaar zijn in Exchange Online Protection EOP-gehoste e-mailfilterservice.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 62530a7c5da7ab0b7fd0e8415c8c366a1caafdda
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/28/2021
ms.locfileid: "52696452"
---
# <a name="eop-features"></a>EOP-functies

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)

De volgende tabel bevat een lijst met functies die beschikbaar zijn in Exchange Online Protection EOP-e-mailfilterservice.

> [!TIP]
> De [Microsoft 365 roadmap voor bedrijven](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) is een goede bron voor het vinden van informatie over toekomstige nieuwe functies. Zie voor een bredere weergave over welke functies beschikbaar zijn met de verschillende [EOP-abonnementsabonnementen Exchange Online Protection Servicebeschrijving.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

<br>

****

|Functie|Beschrijving|
|---|---|
|**Beveiliging tegen malware**||
|Beveiliging tegen malware met meerdere engines|Meerdere anti-malware-engines helpen onze klanten altijd automatisch te beschermen.|
|Always-on malwarefilters|U kunt malwarefiltering niet uitschakelen. We zijn van mening dat het helpen bij het bieden van een consistent en strikt beveiligingsniveau voor al onze klanten een essentieel onderdeel is van de uitgebreide strategie die nodig is om uw e-mailomgeving te beschermen. Hierdoor wordt malwarefilters automatisch ingeschakeld voor alle klanten.|
|Malware-inspectie van de bericht-body en bijlagen|De service controleert de actieve payload in de berichtbeslag en alle berichtbijlagen op malware.|
|Anti-spywarebeveiliging|Anti-malwarebeveiliging omvat bescherming tegen virussen en bescherming tegen spyware.|
|Malwarefilterbeleid|Elke organisatie heeft een standaard antispambeleid dat van toepassing is op alle geadresseerden. Voor meer granulariteit kunt u aangepaste anti-malwarebeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie. Aangepaste beleidsregels worden altijd toegepast vóór standaardbeleid, maar u kunt de volgorde wijzigen dat aangepaste beleidsregels worden toegepast. <p> U kunt de volgende instellingen configureren in anti-malwarebeleid: <ul><li>**Veelgebruikte bijlagefilters:** Schakel een aangepaste lijst in met bestandstypen die altijd malware zijn.</li><li>**ZAP voor malware:** Met terugwerkende kracht heeft quarantaine malwareberichten bezorgd. Zie Voor meer informatie [Zero-hour Auto Purge (ZAP) in Exchange Online.](zero-hour-auto-purge.md)</li><li>**Meldingen van geadresseerden:** het bericht in quarantaine plaatsen of het bericht in quarantaine plaatsen en het bericht ook in quarantaine plaatsen met alle bijlagen die worden vervangen door één tekstbestand met standaard- of aangepaste tekst.</li><li>**Afzendermeldingen:** Laat afzenders weten dat hun bericht is gedetecteerd als malware.</li><li>**Beheerdersmeldingen:** Een beheerder op de hoogte stellen wanneer berichten van interne of externe afzenders zijn gedetecteerd als malware.</li></ul> <p> Zie [Anti-malwarebeleid configureren](configure-anti-malware-policies.md)voor meer informatie.|
|**Bescherming tegen phishing**||
|Bescherming tegen phishing|EOP gebruikt een lijst met domeinen die worden gebruikt door bekende spammers.|
|Beveiliging tegen adresvervalsing (spoofing)|Anti-phishingbeveiliging in EOP bevat bescherming tegen spoofing. Zie Bescherming tegen [spoofing voor meer informatie.](anti-spoofing-protection.md) <p> Anti-phishingbeveiliging in Microsoft Defender voor Office 365 omvat ook imitatiebeveiliging. Zie voor meer informatie [Exclusieve instellingen in anti-phishingbeleid in Microsoft Defender voor Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).|
|**Beveiliging tegen ongewenste e-mail**||
|Detectie van binnenkomende spam|Zie Bescherming tegen [spam in Microsoft 365.](anti-spam-protection.md) <p> Zie EOP configureren om spam te verzenden naar de map Ongewenste e-mail in hybride omgevingen voor aanvullende stappen die vereist zijn [in hybride omgevingen.](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)|
|Backscatterbeveiliging|Zie [Backscatter en EOP voor meer informatie.](backscatter-messages-and-eop.md)|
|Bulksgewijs filteren van e-mail|EOP gebruikt de drempelwaarde voor bulkklachten (BCL) in antispambeleid om bulk-e-mailberichten als spam te markeren. Zie de volgende onderwerpen voor meer informatie: <ul><li>[Wat is het verschil tussen ongewenste e-mail en bulkmail?](what-s-the-difference-between-junk-email-and-bulk-email.md)</li><li>[Bulkklachtsniveau (BCL) in EOP](bulk-complaint-level-values.md)</li><li>[Beleid tegen ongewenste e-mail configureren](configure-your-spam-filter-policies.md)</li></ul>|
|Lijsten met schadelijke URL-blokkeringen|EOP gebruikt verschillende URL-blokkeringslijsten om bekende schadelijke koppelingen in berichten te detecteren.|
|**Beveiliging tegen uitgaande spam**||
|Detectie van uitgaande spam|Uitgaande antispambeveiliging is altijd ingeschakeld als u de service gebruikt voor het verzenden van uitgaande e-mail. Zie Uitgaand spambeveiliging voor meer [informatie.](outbound-spam-controls.md)|
|Uitgaand spambeleid|Elke organisatie heeft een standaardbeleid voor uitgaande spam die van toepassing is op alle geadresseerden. Voor meer granulariteit kunt u aangepaste antispambeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie. Aangepaste beleidsregels worden altijd toegepast vóór standaardbeleid, maar u kunt de volgorde wijzigen dat aangepaste beleidsregels worden toegepast. <p> U kunt de volgende instellingen configureren in antispambeleid: <ul><li>**Messsage-limts:** U kunt limieten instellen die lager zijn dan de [standaardinstellingen](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) voor externe geadresseerden **per** uur, interne geadresseerden **per** uur en het maximum aantal geadresseerden **per dag**</li><li>**Actie voor gebruikers die een** limiet overschrijden: De gebruiker 24 uur beperken, de gebruiker beperken tot de release of alleen waarschuwen.</li><li>**Automatische externe e-mail doorsturen in- of uitschakelen**: [Meer informatie](external-email-forwarding.md)</li><li>**Kopieën van berichten melden of verzenden naar beheerders**</li></ul> <p> Zie Uitgaande spamfilters configureren in EOP voor [meer informatie.](configure-the-outbound-spam-policy.md)|
|**Verbindingsfilters**||
|Verbindingsfilterbeleid|Configureer de lijst IP-toestaan en de lijst IP-blokkering voor de organisatie. Zie Verbindingsfilters [configureren voor meer informatie.](configure-the-connection-filter-policy.md)|
|**Spambeheer**||
|Antispambeleid|Elke organisatie heeft een standaard antispambeleid dat van toepassing is op alle geadresseerden. Voor meer granulariteit kunt u aangepaste antispambeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie. Aangepaste beleidsregels worden altijd toegepast vóór standaardbeleid, maar u kunt de volgorde wijzigen dat aangepaste beleidsregels worden toegepast. <p> U kunt de volgende instellingen configureren in antispambeleid: <ul><li>**Acties voor het** filteren van spamfilters: Wanneer een bericht wordt gedetecteerd, kunt u de actie configureren die moet worden ondernomen (verwijderen, naar de map Ongewenste e-mail gaan, quarantaine, enzovoort) op basis van de uitspraak.</li><li>**Geavanceerde instellingen voor spamfilter (ASF)**: Deze instellingen worden beschreven in de instellingen van [Advanced Spam Filter (ASF) in EOP](advanced-spam-filtering-asf-options.md)</li><li>**ZAP voor phishing en spam:** Met terugwerkende kracht in quarantaine plaatsen of bezorgde berichten verplaatsen naar de map Ongewenste e-mail. Zie Voor meer informatie [Zero-hour Auto Purge (ZAP) in Exchange Online.](zero-hour-auto-purge.md)</li><li>**Spammeldingen voor eindgebruikers inschakelen**: [Meer informatie over spammeldingen voor eindgebruikers]. (use-spam-notifications-to-release-and-report-quarantined-messages.md)</li>**Toegestane en geblokkeerde afzenders** en domeinen : Zie Lijsten met [](create-safe-sender-lists-in-office-365.md) veilige afzenders maken en Lijsten met geblokkeerde afzenders maken voor belangrijke informatie over het veilig gebruiken [van deze lijsten.](create-block-sender-lists-in-office-365.md)</li><li>**Internationale spam-instellingen:** Berichten blokkeren op basis van taal of bronland.</li></ul> <p> Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|Spam beheren via Outlook of Outlook op internet (voorheen bekend als Outlook Web App)|Gebruikers en beheerders kunnen lijsten met persoonlijke veilige afzenders en geblokkeerde afzenderlijsten maken in Exchange Online postvakken. Zie Instellingen voor ongewenste [e-mail in Outlook.](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook) <p> Als u EOP gebruikt om on-premises Exchange postvakken te beveiligen, moet u adreslijstsynchronisatie gebruiken om ervoor te zorgen dat deze instellingen worden gesynchroniseerd met de service. Zie Adreslijstsynchronisatie gebruiken om [e-mailgebruikers te beheren voor meer informatie.](/exchange/standalone-eop/manage-mail-users-in-eop#synchronize-directories-with-azure-active-directory-connect-aad-connect)|
|Rapporteer onwaar positieven en onwaar negatieven aan Microsoft.|Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).|
|Berichten weergeven, zoeken en beheren in de quarantaineportal.|Zie In quarantaine geplaatste berichten en bestanden beheren als beheerder [in EOP](manage-quarantined-messages-and-files.md) of Berichten in quarantaine zoeken en vrijgeven [als gebruiker voor meer informatie.](find-and-release-quarantined-messages-as-a-user.md)|
|Berichtenkoppen met spam in quarantaine weergeven|Nadat u de berichtkop in de quarantaine hebt weergegeven, kunt u de koptekst ook kopiëren en plakken in de berichtkopanalyse [om](https://mha.azurewebsites.net/) erachter te komen wat er met het bericht is gebeurd.|
|**E-mailroutering en verbindingslijnen**||
|
|Voorwaardelijke e-mailroutering|Zie voor meer informatie [scenario: voorwaardelijke routering voor e-mail in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).|
|Opportunistisch of gedwongen TLS|<ul><li>Als de TLS-verbinding mislukt, wordt een TLS-verbinding geprobeerd, maar wordt een SMTP-verbinding gebruikt.</li><li>Gedwongen TLS dwingt TLS-verbindingen af, wat betekent dat het bericht wordt geweigerd als de TLS-verbinding mislukt.</li></ul> <p> Zie Connectors instellen voor een veilige [e-mailstroom met een partnerorganisatie](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)voor meer informatie over TLS, beveiliging en connectors.|
|Regionale routering (de beperking van de e-mailstroom naar een bepaalde regio)|Zie [EOP-datacenters](exchange-online-protection-overview.md#eop-datacenters)voor meer informatie.|
|Het hulpmiddel SMTP-connectiviteitscontrole|Zie E-mailstroom testen door uw verbindingslijnen te valideren voor Microsoft 365 meer informatie over het gebruik van dit hulpprogramma [om uw e-mailstroom te testen.](/exchange/mail-flow-best-practices/test-mail-flow)|
|Subdomeinen matchen|Zie E-mailstroom [in EOP](mail-flow-in-eop.md)voor meer informatie over het inschakelen van e-mailstroom van en naar subdomeinen van uw geaccepteerde domeinen.|
|**Regels voor e-mailstroom**||
|E-mailstroomregels in EOP|Vrijwel alle voorwaarden, uitzonderingen en acties die beschikbaar zijn in regels voor e-mailstroom (ook wel transportregels genoemd) in Exchange Online zijn ook beschikbaar in zelfstandige EOP-organisaties zonder Exchange Online postvakken. Zie de volgende onderwerpen voor meer informatie over regels voor e-mailstroom: <ul><li>[Regels voor e-mailstroom](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</li><li>[Voorwaarden en uitzonderingen voor e-mailstroomregel](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)</li><li>[Acties voor e-mailstroomregel](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</li></ul>|
|Scenario's voor e-mailstroomregel|Er zijn veel scenario's beschikbaar met behulp van transportregels. Bijvoorbeeld: <ul><li>Filter en acties op basis van beleid: u kunt filteren op domein, trefwoord, bestandsnaam, bestandstype, onderwerpregel, berichttekst, afzender, geadresseerde, koptekst en **IP-adres.**</li><li>**Filteren op tekstpatronen:** e-mailstroomregels kunnen een matrix of gewone expressies gebruiken om tekst aan te passen. U kunt ook één tekenreeks of een matrix met tekenreeksen gebruiken om veel berichteigenschappen aan te passen, zoals het adres, het onderwerp, de body of de namen van bijlagen.</li><li>**Aangepaste woordenlijsten:** E-mailstroomregels kunnen lange lijsten met tekst en trefwoorden bevatten, die dezelfde functionaliteit bieden als een aangepaste woordenlijst.</li><li>**Beleidsregels per** domein: U kunt het bereik van een e-mailstroomregel aanpassen aan afzender- of geadresseerdedomeinnamen, IP-adresbereiken, adreswoorden of patronen, groepslidmaatschap en andere voorwaarden.</li><li>**Bijlage scannen:** U kunt regels voor e-mailstroom maken om de bestandsnaam, extensie en inhoud van e-mailbijlagen te scannen.</li><li>Beleidsregelmeldingen verzenden naar de **afzender:** U kunt berichten weigeren en een rapport over niet-bezorging (ook wel een NDR- of bouncebericht genoemd) naar de afzender verzenden via het bericht weigeren met de uitleg of Het bericht weigeren met de verbeterde **statuscodeactie.** </li><li>**Berichten omleiden** of kopiëren: E-mailstroomregels kunnen omleiden, geadresseerden toevoegen via CC of BCC, alleen geadresseerden toevoegen en andere opties.</li><li>**Berichten filteren en de berichtkenmerken** of routering wijzigen: u kunt berichten filteren op basis van een groot aantal voorwaarden en vervolgens een reeks acties toepassen op elk bericht.</li><li>**Het betrouwbaarheidsniveau voor spam (SCL) wijzigen van berichten die onderweg zijn**</li></ul> <p> Zie Procedures voor e-mailstroomregel voor specifieke scenario's voor [e-mailstroomregel.](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-procedures)|
|**Beheer**||
|Webbeheer|U gebruikt de volgende beheercentra om EOP te beheren: <ul><li>Het [Microsoft 365 beveiligingscentrum](/microsoft-365/security/defender/overview-security-center)</li><li>Het [Exchange beheercentrum](/exchange/exchange-admin-center)</li><li>Het [Microsoft 365 beheercentrum](/microsoft-365/admin/admin-overview/about-the-admin-center)</li></ul>|
|PowerShell|Als uw organisatie Exchange Online postvakken heeft, beheert u EOP-functies in [Exchange Online PowerShell.](/powershell/exchange/exchange-online-powershell) Als uw organisatie geen postvakken Exchange Online, beheert u EOP-functies in [Exchange Online Protection PowerShell.](/powershell/exchange/exchange-online-protection-powershell)|
|**Rapportage en logboekregistratie**||
|Bericht traceren|Beheerders kunnen e-mailberichten volgen wanneer ze door de service lopen. U kunt bepalen of een gericht e-mailbericht is ontvangen, geweigerd, uitgesteld of bezorgd door de service. Op deze manier kunt u de vragen van uw gebruikers efficiënt beantwoorden, problemen met de e-mailstroom oplossen, beleidswijzigingen valideren en de noodzaak om contact op te nemen met de technische ondersteuning voor hulp, verminderen. Zie Bericht traceren in het Beveiligings- & [compliancecentrum voor meer informatie.](message-trace-scc.md)|
|Webrapporten|De e-mailbeveiligingsrapporten in het & compliancecentrum bieden berichtengegevens. U kunt bijvoorbeeld controleren hoeveel spam en malware wordt gedetecteerd of hoe vaak uw regels voor e-mailstromen worden afgestemd. Met deze interactieve rapporten kunt u snel een visueel rapport met overzichtsgegevens krijgen en inzoomen op details over afzonderlijke berichten, tot 90 dagen. Zie E-mailbeveiligingsrapporten gebruiken om [gegevens over malware, spam](/exchange/monitoring/use-mail-protection-reports)en regeldetecties weer te geven voor meer informatie.|
|Auditregistratie|Zie Controlerapporten [in](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)Exchange Online.|
|**Service level agreements (SLA's) en ondersteuning**||
|Spameffectiviteit SLA|\> 99%|
|Fout-positieve ratio SLA|\< 1:250,000|
|Virusdetectie en het blokkeren van SLA|100% van bekende virussen|
|Maandelijkse uptime SLA|99.999%|
|Telefoon en web technische ondersteuning 24 uur per dag, zeven dagen per week|Zie Help en [ondersteuning voor EOP](help-and-support-for-eop.md)voor meer informatie over EOP-help- en ondersteuningsopties.|
|**Andere functies**||
|Een geo-redundant globaal netwerk van servers|EOP wordt uitgevoerd op een wereldwijd netwerk van datacenters die zijn ontworpen om de beste beschikbaarheid te bieden. Zie de sectie 'EOP-datacenters' in Exchange Online Protection [overzicht voor meer informatie.](exchange-online-protection-overview.md)|
|Bericht in de wachtrij wanneer de on-premises server geen e-mail kan accepteren|Berichten in uitstel blijven één dag in onze wachtrijen staan. Pogingen voor het opnieuw proberen van berichten zijn gebaseerd op de fout die we krijgen van het e-mailsysteem van de geadresseerde. Gemiddeld worden berichten elke 5 minuten opnieuw verzonden. Zie veelgestelde vragen [over EOP-berichten in de wachtrij, uitgestelde en niet-verzonden berichten voor meer informatie.](eop-queued-deferred-and-bounced-messages-faq.yml)|
|Office 365-berichtversleuteling beschikbaar als een invoegservice|Zie Versleuteling [in Office 365.](../../compliance/encryption.md)|
|
