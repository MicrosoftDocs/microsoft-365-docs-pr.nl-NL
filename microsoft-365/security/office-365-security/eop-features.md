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
description: In de volgende tabel vindt u een lijst met functies die beschikbaar zijn in de door Exchange Online Protection (EOP) gehoste e-mailfilterservice.
ms.openlocfilehash: d3b7638a1ff060d1c1760f62e487a7cd649a9131
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209461"
---
# <a name="eop-features"></a>EOP-functies

In de volgende tabel vindt u een lijst met functies die beschikbaar zijn in de door Exchange Online Protection (EOP) gehoste e-mailfilterservice.

> [!TIP]
> De [Microsoft 365 voor bedrijven roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) is een goede bron voor het vinden van informatie over aankomende nieuwe functies. Zie [Exchange Online Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)voor een bredere weergave van welke functies beschikbaar zijn met de verschillende EOP-abonnementsplannen.

|||
|---|---|
|**Functie**|**Beschrijving**|
|**Beveiliging tegen ongewenste e-mail**||
|Binnenkomende spamdetectie|Zie [Bescherming tegen spam in Microsoft 365](anti-spam-protection.md)voor meer informatie. <br/><br/> In standalone EOP-omgevingen waar EOP on-premises Exchange-postvakken beschermt, moet u regels voor e-mailstroom (ook wel transportregels genoemd) configureren in on-premises Exchange om de EOP-spamfilterbeoordeling te vertalen, zodat de regel voor ongewenste e-mail het bericht kan verplaatsen naar de map Ongewenste e-mail. Zie Zelfstandige [EOP configureren om spam te leveren aan de map Ongewenste e-mail in hybride omgevingen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) voor meer informatie.|
|Uitgaande spamdetectie|Uitgaande antispambeveiliging is altijd ingeschakeld als u de service gebruikt voor het verzenden van uitgaande e-mail. Zie [Uitgaande spambeveiliging](outbound-spam-controls.md)voor meer informatie .|
|Backscatter-beveiliging|Zie [Backscatter en EOP](backscatter-messages-and-eop.md)voor meer informatie.|
|Filteren op bulkpost|EOP gebruikt de bulkklachtendrempel (BCL) om bulke-mailberichten als spam te markeren. Lees de volgende onderwerpen voor meer informatie: <br/><br/> [Wat is het verschil tussen ongewenste e-mail en bulkmail?](what-s-the-difference-between-junk-email-and-bulk-email.md) <br/> [Bulkklachtenniveau (BCL) in EOP](bulk-complaint-level-values.md) <br/> [Beleid tegen ongewenste e-mail configureren](configure-your-spam-filter-policies.md)|
|Schadelijke URL-bloklijsten|EOP maakt gebruik van verschillende URL-bloklijsten die helpen bij het detecteren van bekende kwaadaardige links in berichten.|
|Bescherming tegen phishing|EOP bevat 750.000 domeinen van bekende spammers.|
|Beveiliging tegen adresvervalsing|Zie [Bescherming tegen spoofing](anti-spoofing-protection.md)voor meer informatie .|
|**Spambeheer**||
|Veilige afzenders en geblokkeerde afzenders configureren|Zie [Lijsten met veilige afzenders maken](create-safe-sender-lists-in-office-365.md) en Lijsten met [geblokkeerde afzenders maken](create-block-sender-lists-in-office-365.md)voor meer informatie.|
|Aangepaste antispambeleid maken|Voor een grotere granulariteit u aangepaste antispambeleidsregels maken en deze toepassen op opgegeven gebruikers, groepen of domeinen in uw organisatie. Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u de prioriteit (dat wil zeggen de lopende volgorde) van uw aangepaste beleid wijzigen. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|De acties op door spam gefilterde berichten configureren|U bijvoorbeeld door inhoud gefilterde berichten verwijderen of ze naar de map Ongewenste e-mail of de quarantaine sturen. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|Internationale spamfiltering|U antispamfilters configureren om berichten te filteren die in specifieke talen zijn geschreven of vanuit specifieke landen of regio's worden verzonden. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|Spam beheren via de webversie van Outlook of Outlook (voorheen Outlook Web App)|Beheerders en eindgebruikers kunnen veilige afzenderlijsten en geblokkeerde afzenderlijsten maken. Zie [Instellingen voor ongewenste e-mail in Outlook](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook)voor meer informatie. <br/><br/> Als u EOP gebruikt om on-premises postvakken te beschermen, moet u adreslijstsynchronisatie gebruiken om ervoor te zorgen dat deze instellingen worden gesynchroniseerd met de service. Zie 'Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren' voor meer informatie over het instellen van adreslijstsynchronisatie in [EOP.](manage-mail-users-in-eop.md)|
|Valse positieven en valse negatieven melden aan Microsoft.|Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).|
|Spamquarantainemeldingen voor eindgebruikers|Zie [Spammeldingen voor eindgebruikers](use-spam-notifications-to-release-and-report-quarantined-messages.md) en [Spammeldingen voor eindgebruikers configureren](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)voor meer informatie.|
|Berichten weergeven, zoeken en beheren in de quarantainepoort.|Zie [In quarantaine geplaatste berichten en bestanden beheren als beheerder in EOP](manage-quarantined-messages-and-files.md) of [In quarantaine geplaatste berichten als gebruiker beheren](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie.|
|Spamberichtenkoppen weergeven|Nadat u de berichtkop in de quarantaine hebt weergegeven, u de koptekst ook kopiëren en plakken in de [Message Header Analyzer](https://mha.azurewebsites.net/) om erachter te komen wat er met het bericht is gebeurd.|
|**Beveiliging tegen malware**||
|Bescherming tegen meerdere motoren anti-malware|Meerdere anti-malware engines helpen om onze klanten te allen tijde automatisch te beschermen.|
|De mogelijkheid om malwarefiltering uit te schakelen|U malwarefiltering niet uitschakelen. Wij zijn van mening dat het helpen om een consistent en rigoureus niveau van bescherming te bieden voor al onze klanten een essentieel onderdeel is van de diepgaande strategie die nodig is om uw e-mailberichtenomgeving te beschermen. Als gevolg hiervan wordt malwarefiltering automatisch ingeschakeld voor alle klanten.|
|Malware inspectie van de berichtlichaam en bijlagen|De service inspecteert de actieve payload in de berichtbody en alle berichtbijlagen op malware.|
|Standaard- of aangepaste meldingen van malwaremeldingen|U een melding verzenden naar afzenders of beheerders. Zie [Beleid voor antimalware configureren](configure-anti-malware-policies.md)voor meer informatie.|
|Meldingen van ontvangers|Plaats het bericht in stilte in quarantaine of quarantaine het bericht en lever het ook af met alle bijlagen die zijn vervangen door één tekstbestand met standaard- of aangepaste tekst. Zie [Beleid voor antimalware configureren](configure-anti-malware-policies.md)voor meer informatie.|
|Common Attachment Filtering|U een lijst met bestandstypen inschakelen en aanpassen waarvan altijd wordt aangenomen dat het malware is. Zie [Bescherming tegen malware in EOP](anti-malware-protection.md)voor meer informatie.|
|Bescherming tegen spyware|Anti-malware bescherming omvat anti-virus bescherming en anti-spyware bescherming.|
|Aangepaste beleid voor malwarefilters maken|Voor een grotere granulariteit u aangepaste malwarefilterbeleidsregels maken en deze toepassen op opgegeven gebruikers, groepen of domeinen in uw organisatie. Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u de prioriteit (dat wil zeggen de lopende volgorde) van uw aangepaste beleid wijzigen. Zie [Beleid voor antimalware configureren](configure-anti-malware-policies.md)voor meer informatie.|
|**E-mailroutering en -connectoren**||
|Voorwaardelijke e-mailroutering|Zie [Scenario: Voorwaardelijke e-mailroutering in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing)voor meer informatie.|
|Opportunistische of gedwongen TLS|Opportunistische of gedwongen TLS is beschikbaar met connectoren. Opportunistische TLS probeert een TLS-verbinding, maar maakt gebruik van een SMTP-verbinding als de TLS-verbinding mislukt. Force TLS dwingt TLS-verbindingen af, wat betekent dat het bericht wordt geweigerd als de TLS-verbinding mislukt. Zie [Connectors instellen voor beveiligde e-mailstroom instellen met een partnerorganisatie voor](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)meer informatie over TLS, beveiliging en connectors.|
|Regionale routering (beperking van de e-mailstroom naar een specifieke regio)|Zie voor meer informatie de sectie "EOP-datacenters" in het [exchange onlinebeveiliging-overzicht.](exchange-online-protection-overview.md)|
|Het gereedschap SMTP-connectiviteitscontrole|Zie [E-mailstroom testen door uw Microsoft 365-connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)te valideren voor meer informatie over het gebruik van deze tool om uw e-mailstroom te testen.|
|Subdomeinen overeenkomen|Zie [E-mailstroom in EOP](mail-flow-in-eop.md)voor meer informatie over het inschakelen van e-mailstromen van en naar subdomeinen van uw geaccepteerde domeinen.|
|**Regels voor e-mailstromen**||
|Filteren en acties op basis van beleid|Aangepaste beleidsregels zijn gebaseerd op exchange-mailstroomregels (ook wel transportregels genoemd). U filteren op domein, trefwoord, bestandsnaam, bestandstype, onderwerpregel, berichttekst, afzender, ontvanger, koptekst en IP-adres. Zie [E-mailstroomregels (transportregels) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md)voor meer informatie.|
|Filteren op tekstpatronen|E-mailstroomregels kunnen een array of reguliere expressies gebruiken om tekst te matchen. U ook één tekenreeks of een reeks tekenreeksen gebruiken om overeen te komen met veel berichteigenschappen, zoals het adres, onderwerp, hoofd of bijlage. Zie [E-mailstroomregels (transportregels) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md) voor meer informatie|
|Aangepaste woordenboeken|E-mailstroomregels kunnen lange lijsten met tekst en zoekwoorden bevatten, die dezelfde functionaliteit bieden als een aangepast woordenboek.|
|Beleidsregels per domein|Het bereik van een e-mailstroomregel kan worden aangepast aan afzender- of geadresseerde domeinnamen, IP-adresbereiken, adreszoekwoorden of -patronen, groepslidmaatschappen en andere voorwaarden.|
|Het scannen van bijlagen|Er kunnen regels worden gemaakt om de bestandsnaam, extensie en inhoud van de bijlage te scannen.|
|Beleidsregelmeldingen naar de afzender verzenden|U berichten weigeren en een niet-leveringsrapport (ook wel ndr- of bouncebericht genoemd) naar de afzender sturen via **het bericht weigeren met de uitleg** of Het bericht weigeren met de verbeterde **statuscodeactie.** Zie [Regelacties voor e-mailstromen in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)voor meer informatie .|
|Berichten omleiden of kopiëren|E-mailstroomregels kunnen worden omgeleid, geadresseerden toevoegen via Cc of BCC, gewoon geadresseerden toevoegen en andere opties toevoegen. Zie [Regelacties voor e-mailstromen in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)voor meer informatie .|
|Regelprioriteit aanpassen voor meerdere regels|Gebruik het Exchange-beheercentrum om de volgorde te wijzigen waarin regels worden verwerkt.|
|Berichten filteren en vervolgens de routebeschrijving of kenmerken van een bericht wijzigen|U berichten filteren op basis van een breed scala aan voorwaarden en vervolgens een reeks acties toepassen op elk bericht. Zie [E-mailstroomregels (transportregels) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md)voor meer informatie.|
|Wijzig het spamvertrouwensniveau (SCL) van een bericht per regel.|U een in-transit-bericht inspecteren en er een spambetrouwbaarheidsniveau aan toewijzen op basis van criteria die u kiest. Zie [Regels voor e-mailstroom gebruiken om het spamvertrouwensniveau (SCL) in berichten in te stellen](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)voor meer informatie.|
|Berichtbijlagen inspecteren|U de inhoud van een bijlage of de kenmerken van een bijgevoegd bestand onderzoeken en een actie definiëren die u moet uitvoeren op basis van wat er wordt gevonden. Zie [Regels voor e-mailstroom gebruiken om berichtbijlagen in Exchange Online te inspecteren](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)voor meer informatie.|
|**Beheer**||
|Web-based beheer|Beheerders kunnen de service beheren in het Exchange-beheercentrum (EAC), dat wordt ondersteund in 60 talen. Zie [Exchange-beheercentrum in het zelfstandige EOP](exchange-admin-center-in-exchange-online-protection-eop.md)voor meer informatie.|
|Adreslijstsynchronisatie|Adreslijstsynchronisatie is beschikbaar via het Azure Active Directory Sync-hulpprogramma. Zie de sectie 'Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren' voor meer informatie in [EOP beheren.](manage-mail-users-in-eop.md)|
|Directory Based Edge Blocking (DBEB)|Met de DBEB-functie u berichten weigeren voor ongeldige ontvangers bij de perimeter van het servicenetwerk. Met DBEB kunnen beheerders geadresseerden met e-mail toevoegen aan Microsoft 365 en alle berichten blokkeren die naar e-mailadressen worden verzonden en die niet aanwezig zijn in Microsoft 365. Zie [Directory based edge blocking gebruiken om berichten die naar ongeldige ontvangers worden verzonden, te weigeren voor](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)meer informatie over het configureren van DBEB.|
|Powershell|Volledige EOP-functionaliteit is beschikbaar in Exchange Online Protection PowerShell. Zie [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell)voor meer informatie.|
|**Rapportage en logboekregistratie**||
|Berichttracering|Beheerders kunnen e-mailberichten volgen wanneer ze de service passeren. U bepalen of een doelbericht is ontvangen, geweigerd, uitgesteld of geleverd door de service. Hiermee u de vragen van uw gebruikers efficiënt beantwoorden, problemen met de e-mailstroom oplossen, beleidswijzigingen valideren en de noodzaak om contact op te nemen met de technische ondersteuning voor hulp te verlichten. Zie [Berichttracering in het Security & Compliance Center](message-trace-scc.md)voor meer informatie.|
|Webgebaseerde rapporten|De rapporten over e-mailbeveiliging in het Security & Compliance Center bieden berichtengegevens. U bijvoorbeeld controleren hoeveel spam en malware wordt gedetecteerd of hoe vaak uw regels voor e-mailstroom worden geëvenaard. Met deze interactieve rapporten u snel een visueel rapport van beknopte gegevens krijgen en inzoomen op details over afzonderlijke berichten, tot 90 dagen terug. Zie [Rapporten over e-mailbeveiliging gebruiken om gegevens over malware, spam en regeldetecties weer te geven](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports)voor meer informatie.|
|Controlelogboekregistratie|Het rapport van de beheerdersrolgroep en het controlelogboek van de beheerder zijn beschikbaar voor EOP-beheerders. Zie [Controlerapporten in EOP voor](auditing-reports-in-eop.md)meer informatie.|
|**Service Level Agreements (SLA's) en ondersteuning**||
|Spameffectiviteit SLA|\>99%|
|False positive ratio SLA|\<1:250,000|
|Virusdetectie en het blokkeren van SLA|100% van de bekende virussen|
|Maandelijkse uptime SLA|99.999%|
|Telefonische en webtechnische ondersteuning 24 uur per dag, zeven dagen per week|Zie [Help en ondersteuning voor EOP voor](help-and-support-for-eop.md)meer informatie over eop-help- en ondersteuningsopties.|
|**Andere functies**||
|Een georedundant wereldwijd netwerk van servers|EOP draait op een wereldwijd netwerk van datacenters die zijn ontworpen om de beste beschikbaarheid te bieden. Zie voor meer informatie de sectie "EOP-datacenters" in [het overzicht van Exchange Online Protection.](exchange-online-protection-overview.md)|
|Bericht wachtrijen wanneer de on-premises server geen e-mail kan accepteren|Berichten in uitstel blijven één dag in onze wachtrijen staan. Pogingen voor het opnieuw proberen van berichten zijn gebaseerd op de fout die we terugkrijgen van het e-mailsysteem van de ontvanger. Gemiddeld worden berichten elke 5 minuten opnieuw geprobeerd. Zie [Veelgestelde vragen over eop in de wachtrij, uitgesteld en teruggestuurde berichten](eop-queued-deferred-and-bounced-messages-faq.md)voor meer informatie.|
|Office 365-berichtversleuteling beschikbaar als invoegservice|Zie [Versleuteling in Office 365](../../compliance/encryption.md)voor meer informatie.|
