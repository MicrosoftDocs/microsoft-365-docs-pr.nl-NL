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
description: De volgende tabel bevat een lijst met functies die beschikbaar zijn in de door Exchange Online Protection (EOP) gehoste e-mailfilterservice.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7dbdf30df0659565d775bfba2cf968ac56f6a4ac
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286847"
---
# <a name="eop-features"></a>EOP-functies

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
-  [Zelfstandige versie van Exchange Online Protection](exchange-online-protection-overview.md)

De volgende tabel bevat een lijst met functies die beschikbaar zijn in de door Exchange Online Protection (EOP) gehoste e-mailfilterservice.

> [!TIP]
> De [routekaart voor Microsoft 365 voor Bedrijven](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) is een goede bron voor het zoeken naar informatie over toekomstige nieuwe functies. Zie de servicebeschrijving van Exchange Online Protection voor meer informatie over welke functies beschikbaar zijn in de verschillende [EOP-abonnementen.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

****

|Functie|Beschrijving|
|---|---|
|**Beveiliging tegen ongewenste e-mail**||
|Binnenkomende spamdetectie|Zie Beveiliging [tegen ongewenste e-mail in Microsoft 365](anti-spam-protection.md)voor meer informatie. <p> In standalone EOP-omgevingen waar EOP on-premises Exchange-postvakken beschermt, moet u regels voor e-mailstroom (ook wel transportregels genoemd) configureren in on-premises Exchange om de EOP-spamfilterbeoordeling te vertalen, zodat de regel voor ongewenste e-mail het bericht kan verplaatsen naar de map Ongewenste e-mail. Zie Zelfstandige EOP configureren om spam te leveren aan de map Ongewenste [e-mail in hybride omgevingen voor meer informatie.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)|
|Detectie van uitgaande spam|Beveiliging tegen uitgaande spam is altijd ingeschakeld als u de service gebruikt voor het verzenden van uitgaande e-mail. Zie Uitgaande [spambeveiliging voor meer informatie.](outbound-spam-controls.md)|
|Backscatter-beveiliging|Zie [Backscatter en EOP voor meer informatie.](backscatter-messages-and-eop.md)|
|Bulkmail filteren|EOP gebruikt de drempelwaarde voor bulksgehoorde klacht om bulk-e-mailberichten als spam te markeren. Zie de volgende onderwerpen voor meer informatie: <p> [Wat is het verschil tussen ongewenste e-mail en bulkmail?](what-s-the-difference-between-junk-email-and-bulk-email.md) <p> [Bulksgewijs klachtniveau (BCL) in EOP](bulk-complaint-level-values.md) <p> [Beleid tegen ongewenste e-mail configureren](configure-your-spam-filter-policies.md)|
|Schadelijke URL-blokkeerlijsten|In EOP worden verschillende lijsten met URL-blokkeringen gebruikt om bekende schadelijke koppelingen in berichten te detecteren.|
|Bescherming tegen phishing|EOP bevat 750.000 domeinen van bekende spammers.|
|Beveiliging tegen adresvervalsing (spoofing)|Zie Beveiliging tegen [spoofing voor meer informatie.](anti-spoofing-protection.md)|
|**Spambeheer**||
|Veilige afzenders en geblokkeerde afzenders configureren|Zie Lijsten met veilige afzenders maken [en](create-safe-sender-lists-in-office-365.md) Lijsten met geblokkeerde afzenders [maken voor meer informatie.](create-block-sender-lists-in-office-365.md)|
|Aangepast antispambeleid maken|Voor een grotere granulatie kunt u aangepaste antispambeleidsregels maken en deze toepassen op opgegeven gebruikers, groepen of domeinen in uw organisatie. Aangepaste beleidsregels hebben altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (dat wil zeggen de volgorde van de regels) van uw aangepaste beleidsregels wijzigen. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|De acties op spam gefilterde berichten configureren|U kunt bijvoorbeeld berichten die op inhoud zijn gefilterd verwijderen of naar de map Ongewenste e-mail of de quarantaine sturen. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|Internationale spamfilters|U kunt antispamfilters configureren om berichten te filteren die in bepaalde talen zijn geschreven of die vanuit bepaalde landen of regio's zijn verzonden. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|Spam beheren via Outlook of de webversie van Outlook (voorheen Outlook Web App genoemd)|Beheerders en eindgebruikers kunnen lijsten met veilige afzenders en lijsten met geblokkeerde afzenders maken. Zie Instellingen voor ongewenste [e-mail in Outlook voor meer informatie.](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook) <p> Als u EOP gebruikt om on-premises postvakken te beveiligen, moet u adreslijstsynchronisatie gebruiken om ervoor te zorgen dat deze instellingen worden gesynchroniseerd met de service. Zie Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren in EOP voor meer informatie over het instellen van [adreslijstsynchronisatie.](manage-mail-users-in-eop.md)|
|Fout-positieven en fout-negatieven rapporteren aan Microsoft.|Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).|
|Spam quarantainemeldingen voor eindgebruikers|Zie spammeldingen [voor eindgebruikers en spammeldingen](use-spam-notifications-to-release-and-report-quarantined-messages.md) voor eindgebruikers [configureren voor meer informatie.](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)|
|Berichten weergeven, zoeken en beheren in de quarantaineportal.|Zie In quarantaine geplaatste berichten en bestanden als beheerder [in EOP](manage-quarantined-messages-and-files.md) beheren of in quarantaine geplaatste berichten als gebruiker zoeken [en vrijgeven.](find-and-release-quarantined-messages-as-a-user.md)|
|Berichtkoppen in quarantaine weergeven|Nadat u de berichtkop in de quarantaine hebt bekeken, kunt u ook de koptekst kopiëren en plakken in [Berichtkopanalyse](https://mha.azurewebsites.net/) om erachter te komen wat er is gebeurd met het bericht.|
|**Beveiliging tegen malware**||
|Beveiliging tegen malware met meerdere engine|Meerdere antimalware-engines helpen onze klanten altijd automatisch te beschermen.|
|De mogelijkheid om malwarefilters uit te schakelen|U kunt malwarefilters niet uitschakelen. Wij zijn van mening dat het bieden van een consistente en zorgvuldig beveiligingsniveau voor al onze klanten een belangrijk onderdeel is van de strategie die nodig is om uw e-mailomgeving te helpen beschermen. Het gevolg is dat malwarefilters automatisch worden ingeschakeld voor alle klanten.|
|Malwarecontrole van de bericht zelf en bijlagen|De service controleert de actieve nettolading in de bericht zelf en alle berichtbijlagen op malware.|
|Standaardmeldingen of aangepaste waarschuwingen voor malware|U kunt een meldingsbericht verzenden naar afzenders of beheerders. Zie [Antimalwarebeleid configureren](configure-anti-malware-policies.md)voor meer informatie.|
|Meldingen van geadresseerden|Het bericht of de quarantaine in quarantaine plaatsen en het bericht leveren, met alle bijlagen vervangen door één tekstbestand met standaardtekst of aangepaste tekst. Zie [Antimalwarebeleid configureren](configure-anti-malware-policies.md)voor meer informatie.|
|Veelgebruikte filteropties voor bijlagen|U kunt een lijst met bestandstypen inschakelen en aanpassen die altijd als malware worden gebruikt. Zie Beveiliging tegen [malware in EOP voor meer informatie.](anti-malware-protection.md)|
|Bescherming tegen spyware|Bescherming tegen malware is van bescherming tegen virussen en bescherming tegen spyware.|
|Aangepast beleid voor malwarefilters maken|Voor een grotere granulatie kunt u aangepaste beleidsregels voor malwarefilters maken en deze toepassen op opgegeven gebruikers, groepen of domeinen in uw organisatie. Aangepaste beleidsregels hebben altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (dat wil zeggen de volgorde van de regels) van uw aangepaste beleidsregels wijzigen. Zie [Antimalwarebeleid configureren](configure-anti-malware-policies.md)voor meer informatie.|
|**E-mailroutering en connectors**||
|Voorwaardelijke e-mailroutering|Zie voor meer informatie [scenario: voorwaardelijke routering voor e-mail in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).|
|Of geforceerd TLS|Er is een forceer TLS beschikbaar voor connectors. Als de TLS-verbinding mislukt, wordt een TLS-verbinding geprobeerd, maar wordt een SMTP-verbinding gebruikt. Forceer TLS om TLS-verbindingen af te dwingen, wat betekent dat het bericht wordt geweigerd als de TLS-verbinding mislukt is. Zie Connectors instellen voor een veilige e-mailstroom met een partnerorganisatie voor meer informatie over TLS, [beveiliging en connectors.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)|
|Regionale routering (de beperking van de e-mailstroom naar een specifieke regio)|Zie de sectie EOP-datacenters in het overzicht van [Exchange Online Protection voor meer informatie.](exchange-online-protection-overview.md)|
|Het hulpprogramma SMTP-connectiviteitscontrole|Zie E-mailstroom testen door uw [Microsoft 365-connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)te valideren voor meer informatie over het gebruik van dit hulpmiddel om uw e-mailstroom te testen.|
|Subdomeinen matchen|Zie E-mailstroom in EOP voor meer informatie over het inschakelen van de [e-mailstroom](mail-flow-in-eop.md)van en naar subdomeinen van uw geaccepteerde domeinen.|
|**Regels voor de e-mailstroom**||
|Filteren en acties op basis van beleid|Aangepaste beleidsregels zijn gebaseerd op Exchange-regels voor de e-mailstroom (ook wel transportregels genoemd). U kunt filteren op domein, trefwoord, bestandsnaam, bestandstype, onderwerpregel, berichttekst, afzender, geadresseerde, koptekst en IP-adres. Zie [E-mailstroomregels (transportregels) in Exchange Online Protection voor meer informatie.](mail-flow-rules-transport-rules-0.md)|
|Filteren op tekstpatronen|E-mailstroomregels kunnen een matrix of reguliere expressies gebruiken om tekst aan te passen. U kunt ook één tekenreeks of een matrix van tekenreeksen gebruiken die overeenkomen met een groot aantal berichteigenschappen, zoals het adres, het onderwerp, de tekst of de namen van bijlagen. Zie [E-mailstroomregels (transportregels) in Exchange Online Protection voor meer informatie](mail-flow-rules-transport-rules-0.md)|
|Aangepaste woordenlijsten|E-mailstroomregels kunnen lange lijsten met tekst en trefwoorden bevatten, met dezelfde functionaliteit als een aangepaste woordenlijst.|
|Beleidsregels per domein|Het bereik van een regel voor de e-mailstroom kan worden aangepast aan de domeinnamen van afzenders of geadresseerden, IP-adresbereiken, adresstrefwoorden of -patronen, groepslidmaatschap en andere voorwaarden.|
|Bijlagen scannen|Er kunnen regels worden gemaakt om de bestandsnaam, extensie en inhoud van de bijlage te scannen.|
|Beleidsregelmeldingen verzenden naar de afzender|U kunt berichten weigeren en een rapport over niet-bezorging (ook wel een  NDR of niet-bezorgdbericht genoemd) naar de afzender verzenden via het bericht weigeren met de uitleg of Het bericht weigeren met de verbeterde **statuscodeactie.** Zie [E-mailstroomregelacties in Exchange Online voor meer informatie.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)|
|Berichten omleiden of kopiëren|E-mailstroomregels kunnen omleiden, geadresseerden toevoegen via CC of BCC, eenvoudig geadresseerden toevoegen en andere opties. Zie [E-mailstroomregelacties in Exchange Online voor meer informatie.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)|
|Regelprioriteit aanpassen voor meerdere regels|Gebruik het Exchange-beheercentrum om de volgorde te wijzigen waarin regels worden verwerkt.|
|Berichten filteren en vervolgens de routering of kenmerken van een bericht wijzigen|U kunt berichten filteren op basis van een groot aantal voorwaarden en vervolgens een reeks acties toepassen op elk bericht. Zie [E-mailstroomregels (transportregels) in Exchange Online Protection voor meer informatie.](mail-flow-rules-transport-rules-0.md)|
|Wijzig het betrouwbaarheidsniveau voor spam van een bericht op regel.|U kunt een tijdens het transitbericht controleren en er een betrouwbaarheidsniveau voor spam aan toewijzen op basis van de criteria die u kiest. Zie Regels voor de e-mailstroom gebruiken om het betrouwbaarheidsniveau voor ongewenste e-mail [in berichten in te stellen.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)|
|Berichtbijlagen controleren|U kunt de inhoud van een bijlage of de kenmerken van een bijgevoegd bestand bekijken en een actie definiëren die moet worden ondernomen op basis van wat wordt gevonden. Zie Regels voor de [e-mailstroom gebruiken om berichtbijlagen in Exchange Online te controleren voor meer informatie.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)|
|**Beheer**||
|Webbeheer|Beheerders kunnen de service beheren in het Exchange-beheercentrum (EAC), dat wordt ondersteund in 60 talen. Zie het [Exchange-beheercentrum in de zelfstandige EOP](exchange-admin-center-in-exchange-online-protection-eop.md)voor meer informatie.|
|Adreslijstsynchronisatie|Adreslijstsynchronisatie is beschikbaar via het hulpprogramma Azure Active Directory-synchronisatie. Zie de sectie Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren in [EOP e-mailgebruikers beheren voor meer informatie.](manage-mail-users-in-eop.md)|
|Randblokkering op basis van adreslijst (DBEB)|Met de DBEB-functie kunt u berichten weigeren voor ongeldige geadresseerden aan de perimeter van het servicenetwerk. Met DBEB kunnen beheerders geadresseerden met e-mail toevoegen aan Microsoft 365 en alle berichten blokkeren die worden verzonden naar e-mailadressen die niet aanwezig zijn in Microsoft 365. Zie Op directory gebaseerde randblokkering gebruiken om berichten te weigeren die naar ongeldige geadresseerden zijn verzonden voor meer informatie over het configureren [van](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)DBEB.|
|PowerShell|De volledige EOP-functionaliteit is beschikbaar in zelfstandige EOP PowerShell. Zie [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell)voor meer informatie.|
|**Rapportage en logboekregistratie**||
|Bericht traceren|Beheerders kunnen e-mailberichten volgen terwijl ze de service passeren. U kunt bepalen of een specifiek e-mailbericht is ontvangen, geweigerd, uitgesteld of bezorgd door de service. Op deze manier kunt u efficiënt antwoord krijgen op de vragen van uw gebruikers, problemen met de e-mailstroom oplossen, beleidswijzigingen valideren en de noodzaak om contact op te nemen met de technische ondersteuning voor hulp. Zie Bericht traceren in het beveiligings- & [compliancecentrum voor meer informatie.](message-trace-scc.md)|
|Webrapporten|De rapporten voor e-mailbeveiliging in het & bieden berichtgegevens. U kunt bijvoorbeeld controleren hoeveel spam en malware wordt gedetecteerd of hoe vaak uw regels voor de e-mailstroom worden gematcht. Met deze interactieve rapporten kunt u snel een visueel rapport van overzichtsgegevens krijgen en inzoomen op details van afzonderlijke berichten, tot 90 dagen geleden. Zie Rapporten over e-mailbeveiliging gebruiken om gegevens over malware, spam en regeldetecties weer [te geven voor meer informatie.](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports)|
|Auditlogregistratie|Het rapport beheerdersrolgroep en het auditlogboek voor beheerders zijn beschikbaar voor EOP-beheerders. Zie Controlerapporten [in EOP](auditing-reports-in-eop.md)voor meer informatie.|
|**Service Level Agreements (SLA's) en ondersteuning**||
|Spam-effectiviteit SLA|\> 99%|
|SLA voor fout-positieve verhouding|\< 1:250,000|
|Virusdetectie en blokkeren SLA|100% van bekende virussen|
|SLA voor maandelijkse uptime|99.999%|
|Technische ondersteuning via telefoon en internet 24 uur per dag, zeven dagen per week|Zie de Help en ondersteuning voor EOP voor meer informatie over help en ondersteuning [voor EOP.](help-and-support-for-eop.md)|
|**Andere functies**||
|Een geografisch redundant wereldwijd netwerk van servers|EOP wordt uitgevoerd op een wereldwijd netwerk van datacenters die zijn ontworpen om de beste beschikbaarheid te bieden. Zie de sectie 'EOP-datacenters' in [Exchange Online Protection-overzicht voor meer informatie.](exchange-online-protection-overview.md)|
|Bericht in wachtrij wanneer de on-premises server geen e-mail kan accepteren|Berichten in de wachtrij blijven één dag in onze wachtrijen staan. Pogingen om berichten opnieuw te proberen, zijn gebaseerd op de fout die wordt weergegeven in het e-mailsysteem van de geadresseerde. Gemiddeld worden berichten elke 5 minuten opnieuw verzonden. Zie veelgestelde vragen [over EOP-wachtrijen, uitgestelde en niet-uitgestelde berichten voor meer informatie.](eop-queued-deferred-and-bounced-messages-faq.md)|
|Office 365-berichtversleuteling beschikbaar als een invoegservice|Zie Versleuteling [in Office 365 voor meer informatie.](../../compliance/encryption.md)|
|
