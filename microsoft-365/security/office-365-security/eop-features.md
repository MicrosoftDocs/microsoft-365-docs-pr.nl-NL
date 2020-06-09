---
title: EOP-functies
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: De volgende tabel bevat een lijst met functies die beschikbaar zijn in de eop-service (Exchange Online Protection).
ms.openlocfilehash: 820f635e679be9d579ba94fc3288830dc6996a0e
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617040"
---
# <a name="eop-features"></a>EOP-functies

De volgende tabel bevat een lijst met functies die beschikbaar zijn in de eop-service (Exchange Online Protection).

> [!TIP]
> De [Microsoft 365 voor zakelijke roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) is een goede bron voor het vinden van informatie over aankomende nieuwe functies. Zie Beschrijving van [de Exchange Online Protection Service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)voor een bredere weergave van de functies die beschikbaar zijn met de verschillende EOP-abonnementen.

|||
|---|---|
|**Functie**|**Beschrijving**|
|**Beveiliging tegen ongewenste e-mail**||
|Inkomende spamdetectie|Zie [Antispambeveiliging in Microsoft 365](anti-spam-protection.md)voor meer informatie. <br/><br/> In standalone EOP-omgevingen waar EOP on-premises Exchange-postvakken beschermt, moet u regels voor e-mailstroom (ook wel transportregels genoemd) configureren in on-premises Exchange om de EOP-spamfilterbeoordeling te vertalen, zodat de regel voor ongewenste e-mail het bericht kan verplaatsen naar de map Ongewenste e-mail. Zie Zelfstandige [EOP configureren om spam te leveren aan de map Ongewenste e-mail in hybride omgevingen voor](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) meer informatie|
|Uitgaande spamdetectie|Uitgaande antispambeveiliging is altijd ingeschakeld als u de service gebruikt voor het verzenden van uitgaande e-mail. Zie [Uitgaande spambescherming](outbound-spam-controls.md)voor meer informatie.|
|Bescherming tegensluipje|Zie [Backscatter en EOP voor](backscatter-messages-and-eop.md)meer informatie.|
|Bulkmailfiltering|EOP gebruikt de bulkklachtendrempel (BCL) om bulke-mailberichten als spam te markeren. Lees de volgende onderwerpen voor meer informatie: <br/><br/> [Wat is het verschil tussen ongewenste e-mail en bulkmail?](what-s-the-difference-between-junk-email-and-bulk-email.md) <br/> [Bulkklachtenniveau (BCL) in EOP](bulk-complaint-level-values.md) <br/> [Beleid tegen ongewenste e-mail configureren](configure-your-spam-filter-policies.md)|
|Lijsten met schadelijke URL-blokkeringen|EOP maakt gebruik van verschillende URL-bloklijsten die helpen bij het detecteren van bekende kwaadaardige koppelingen in berichten.|
|Bescherming tegen phishing|EOP omvat 750.000 domeinen van bekende spammers.|
|Beveiliging tegen adresvervalsing|Zie [Anti-spoofing-beveiliging](anti-spoofing-protection.md)voor meer informatie.|
|**Spambeheer**||
|Veilige afzenders en geblokkeerde afzenders configureren|Zie [Lijsten met veilige afzenders maken](create-safe-sender-lists-in-office-365.md) en Lijsten met [geblokkeerde afzenders maken voor](create-block-sender-lists-in-office-365.md)meer informatie.|
|Aangepaste antispambeleid maken|Voor meer granulariteit u aangepaste antispambeleidsregels maken en toepassen op specifieke gebruikers, groepen of domeinen in uw organisatie. Aangepaste beleidsregels hebben altijd voorrang op het standaardbeleid, maar u de prioriteit (dat wil zeggen de uitvoerende volgorde) van uw aangepaste beleid wijzigen. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|De acties op spamgefilterde berichten configureren|U bijvoorbeeld inhoudsgefilterde berichten verwijderen of naar de map Ongewenste e-mail of de quarantaine verzenden. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|Internationale spamfiltering|U antispamfiltering configureren om berichten te filteren die in specifieke talen zijn geschreven of vanuit specifieke landen of regio's worden verzonden. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|Spam beheren via Outlook of Outlook in de web (voorheen Outlook Web App genoemd)|Beheerders en eindgebruikers kunnen veilige afzenderlijsten en geblokkeerde afzenderlijsten maken. Zie [Instellingen voor ongewenste e-mail in Outlook voor](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook)meer informatie . <br/><br/> Als u EOP gebruikt om on-premises postvakken te beschermen, moet u adreslijstsynchronisatie gebruiken om ervoor te zorgen dat deze instellingen worden gesynchroniseerd met de service. Zie 'Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren' in [EOP beheren](manage-mail-users-in-eop.md)voor meer informatie over het instellen van adreslijstsynchronisatie.|
|Valse positieven en valse negatieven melden aan Microsoft.|Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).|
|Meldingen van spam-quarantaine van eindgebruikers|Zie [spammeldingen](use-spam-notifications-to-release-and-report-quarantined-messages.md) voor eindgebruikers en [spammeldingen voor eindgebruikers configureren](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)voor meer informatie.|
|Berichten in de quarantaineportal weergeven, zoeken en beheren.|Zie [In quarantaine geplaatste berichten en bestanden beheren als beheerder in EOP](manage-quarantined-messages-and-files.md) of Berichten in [quarantaine zoeken en vrijgeven als gebruiker](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie.|
|Berichtenkoppen in quarantaine weergeven|Nadat u de berichtkop in quarantaine hebt weergegeven, u de koptekst ook kopiëren en plakken in de [Message Header Analyzer](https://mha.azurewebsites.net/) om erachter te komen wat er met het bericht is gebeurd.|
|**Beveiliging tegen malware**||
|Anti-malwarebescherming met meerdere motoren|Meerdere anti-malware engines helpen om onze klanten te allen tijde automatisch te beschermen.|
|De mogelijkheid om malwarefiltering uit te schakelen|U malwarefiltering niet uitschakelen. Wij zijn van mening dat het helpen bieden van een consistent en rigoureus niveau van bescherming voor al onze klanten een essentieel onderdeel is van de defensie-diepgaande strategie die nodig is om uw e-mailberichtenomgeving te beschermen. Als gevolg hiervan wordt malwarefiltering automatisch ingeschakeld voor alle klanten.|
|Malware inspectie van het bericht lichaam en bijlagen|De service inspecteert de actieve payload in de berichttekst en alle berichtbijlagen voor malware.|
|Standaard- of aangepaste waarschuwingsmeldingen voor malware|U een meldingsbericht sturen naar afzenders of beheerders. Zie [Anti-malwarebeleid configureren](configure-anti-malware-policies.md)voor meer informatie.|
|Meldingen van geadresseerden|Zet het bericht in een stilte in quarantaine of zet het bericht in quarantaine en lever het ook af met alle bijlagen die zijn vervangen door één tekstbestand met standaard of aangepaste tekst. Zie [Anti-malwarebeleid configureren](configure-anti-malware-policies.md)voor meer informatie.|
|Veelvoorkomende bijlagefiltering|U een lijst met bestandstypen in- en uit- of aanpassen waarvan wordt aangenomen dat het malware is. Zie [Anti-malwarebescherming in EOP](anti-malware-protection.md)voor meer informatie.|
|Bescherming tegen spyware|Bescherming tegen malware omvat anti-virus bescherming en anti-spyware bescherming.|
|Aangepaste beleid voor malwarefilter maken|Voor meer granulariteit u aangepaste beleid voor malwarefilters maken en deze toepassen op specifieke gebruikers, groepen of domeinen in uw organisatie. Aangepaste beleidsregels hebben altijd voorrang op het standaardbeleid, maar u de prioriteit (dat wil zeggen de uitvoerende volgorde) van uw aangepaste beleid wijzigen. Zie [Anti-malwarebeleid configureren](configure-anti-malware-policies.md)voor meer informatie.|
|**E-mailroutering en -connectoren**||
|Voorwaardelijke e-mailroutering|Zie [Scenario: Voorwaardelijke e-mailroutering in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing)voor meer informatie.|
|Opportunistische of geforceerde TLS|Opportunistische of geforceerde TLS is beschikbaar met connectoren. Opportunistische TLS probeert een TLS-verbinding, maar maakt gebruik van een SMTP-verbinding als de TLS-verbinding niet succesvol is. Force TLS dwingt TLS-verbindingen af, wat betekent dat het bericht wordt geweigerd als de TLS-verbinding niet succesvol is. Zie [Connectors instellen voor een beveiligde e-mailstroom met een partnerorganisatie voor](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)meer informatie over TLS, beveiliging en connectoren.|
|Regionale routering (de beperking van de e-mailstroom naar een specifieke regio)|Zie voor meer informatie de sectie "EOP datacenters" in het [overzicht van Exchange Online Protection.](exchange-online-protection-overview.md)|
|De TOOL SMTP Connectivity Checker|Zie [E-mailstroom testen door uw Microsoft 365-connectoren](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)te valideren voor meer informatie over het gebruik van deze tool om uw e-mailstroom te testen.|
|Subdomeinen overeenkomen|Zie [EOP voor](mail-flow-in-eop.md)meer informatie over het inschakelen van e-mailstroom van en naar subdomeinen van uw geaccepteerde domeinen.|
|**Regels voor e-mailstroom**||
|Filteren op beleid gebaseerde maatregelen|Aangepaste beleidsregels zijn gebaseerd op Exchange-regels voor de stroom van e-mail (ook wel transportregels genoemd). U filteren op domein, trefwoord, bestandsnaam, bestandstype, onderwerpregel, berichttekst, afzender, ontvanger, koptekst en IP-adres. Zie [Regels voor e-mailstroom (transportregels) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md)voor meer informatie.|
|Filteren op tekstpatronen|E-mailstroomregels kunnen een array of reguliere expressie gebruiken om tekst aan te passen. U ook één tekenreeks of een array met tekenreeksen gebruiken die overeenkomen met veel berichteigenschappen, zoals het adres, onderwerp, hoofdtekst of bijlagenamen. Zie [Regels voor e-mailstroom (transportregels) in Exchange Online Protection voor](mail-flow-rules-transport-rules-0.md) meer informatie|
|Aangepaste woordenboeken|E-mailstroomregels kunnen lange lijsten met tekst en zoekwoorden bevatten, die dezelfde functionaliteit bieden als een aangepast woordenboek.|
|Beleidsregels per domein|Het bereik van een e-mailstroomregel kan worden aangepast aan de domeinnamen van afzender of ontvanger, IP-adresbereiken, adreszoekwoorden of -patronen, groepslidmaatschappen en andere voorwaarden.|
|Het scannen van bijlagen|Er kunnen regels worden gemaakt om de bestandsnaam, extensie en inhoud van de bijlage te scannen.|
|Beleidsregelmeldingen naar de afzender verzenden|U berichten weigeren en een rapport zonder levering (ook wel een NDR- of bouncebericht genoemd) naar de afzender verzenden via het **bericht weigeren met de uitleg** of Het bericht weigeren met de verbeterde **statuscodeactie.** Zie Acties van [de mailstroomregel in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)voor meer informatie.|
|Berichten omleiden of kopiëren|E-mailstroomregels kunnen omleiden, geadresseerden toevoegen door Cc of BCC, gewoon ontvangers toevoegen en andere opties. Zie Acties van [de mailstroomregel in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)voor meer informatie.|
|Regelprioriteit aanpassen voor meerdere regels|Gebruik het Exchange-beheercentrum om de volgorde te wijzigen waarin regels worden verwerkt.|
|Berichten filteren en vervolgens de routering of kenmerken van een bericht wijzigen|U berichten filteren op basis van een breed scala aan voorwaarden en vervolgens een reeks acties toepassen op elk bericht. Zie [Regels voor e-mailstroom (transportregels) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md)voor meer informatie.|
|Wijzig het spamvertrouwensniveau (SCL) van een bericht per regel.|U een in-transitbericht inspecteren en er een spamvertrouwensniveau aan toewijzen op basis van criteria die u kiest. Zie [Regels voor e-mailstroom gebruiken om het spamvertrouwensniveau (SCL) in berichten in te stellen](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)voor meer informatie.|
|Berichtbijlagen inspecteren|U de inhoud van een bijlage of de kenmerken van een bijgevoegd bestand onderzoeken en een actie definiëren die u moet uitvoeren op basis van wat er wordt gevonden. Zie [Regels voor e-mailstroom gebruiken om berichtbijlagen in Exchange Online te inspecteren](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)voor meer informatie.|
|**Beheer**||
|Webgebaseerde administratie|Beheerders kunnen de service beheren in het Exchange-beheercentrum (EAC), dat in 60 talen wordt ondersteund. Zie [Exchange-beheercentrum in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md)voor meer informatie.|
|Adreslijstsynchronisatie|Adreslijstsynchronisatie is beschikbaar via het hulpprogramma Azure Active Directory Sync. Zie de sectie 'Mapsynchronisatie gebruiken om e-mailgebruikers te beheren' in [EOP beheren](manage-mail-users-in-eop.md)voor meer informatie.|
|Directory Based Edge Blocking (DBEB)|Met de DBEB-functie u berichten weigeren voor ongeldige ontvangers bij de omtrek van het servicenetwerk. Met DBEB kunnen beheerders ontvangers met e-mail toevoegen aan Microsoft 365 en alle berichten blokkeren die worden verzonden naar e-mailadressen die niet aanwezig zijn in Microsoft 365. Zie Directory Based Edge Blocking [gebruiken om berichten die naar ongeldige ontvangers zijn verzonden, te weigeren voor](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)meer informatie over het configureren van DBEB.|
|Powershell|Volledige EOP-functionaliteit is beschikbaar in standalone EOP PowerShell. Zie [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell)voor meer informatie.|
|**Rapportage en logboekregistratie**||
|Berichttracering|Beheerders kunnen e-mailberichten volgen terwijl ze door de service gaan. U bepalen of een gericht e-mailbericht is ontvangen, geweigerd, uitgesteld of geleverd door de service. Hiermee u efficiënt de vragen van uw gebruikers beantwoorden, problemen met de e-mailstroom oplossen, beleidswijzigingen valideren en u geen contact opnemen met technische ondersteuning voor hulp. Zie [Berichttracering in het Security & Compliance Center](message-trace-scc.md)voor meer informatie.|
|Webgebaseerde rapporten|De rapporten over e-mailbeveiliging in het Security & Compliance Center bieden berichtengegevens. U bijvoorbeeld controleren hoeveel spam en malware wordt gedetecteerd of hoe vaak uw regels voor e-mailstromen worden geëerste. Met deze interactieve rapporten u snel een visueel rapport van overzichtsgegevens ontvangen en inzoomen op details over afzonderlijke berichten, voor al 90 dagen terug. Zie [Rapporten voor e-mailbeveiliging gebruiken om gegevens over malware, spam en regeldetecties te bekijken](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports)voor meer informatie.|
|Controlelogboekregistratie|Het beheerdersrolgroeprapport en het beheerdersauditlogboek zijn beschikbaar voor EOP-beheerders. Zie [Auditing rapporten in EOP](auditing-reports-in-eop.md)voor meer informatie .|
|**Service Level Agreements (SLA's) en ondersteuning**||
|Spam effectiviteit SLA|\>99%|
|Sla over de vals-positieve verhouding|\<1:250,000|
|Virusdetectie en -blokkering van SLA|100% van de bekende virussen|
|Sla -uptime per maand|99.999%|
|Telefonische en webtechnische ondersteuning 24 uur per dag, zeven dagen per week|Zie [Help en ondersteuning voor EOP voor](help-and-support-for-eop.md)meer informatie over EOP-ondersteuningsopties.|
|**Andere functies**||
|Een geo-redundant wereldwijd netwerk van servers|EOP draait op een wereldwijd netwerk van datacenters die zijn ontworpen om de beste beschikbaarheid te bieden. Zie voor meer informatie de sectie "EOP datacenters" in [het overzicht van Exchange Online Protection.](exchange-online-protection-overview.md)|
|Bericht in de rij staan wanneer de on-premises server geen e-mail kan accepteren|Berichten in uitstel blijven één dag in onze wachtrijen staan. Pogingen voor opnieuw proberen van berichten zijn gebaseerd op de fout die we terugkrijgen van het e-mailsysteem van de ontvanger. Gemiddeld worden berichten elke 5 minuten opnieuw geprobeerd. Zie veelgestelde vragen over [EOP in de wachtrij, uitgesteld en teruggestuurde berichten](eop-queued-deferred-and-bounced-messages-faq.md)voor meer informatie.|
|Office 365-berichtversleuteling beschikbaar als invoegservice|Zie [Versleuteling in Office 365](../../compliance/encryption.md)voor meer informatie .|
