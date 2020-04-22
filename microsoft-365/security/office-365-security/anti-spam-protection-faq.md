---
title: Veelgestelde vragen over beveiliging tegen ongewenste e-mail
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
description: Veelgestelde vragen en antwoorden voor beheerders over antispambescherming in Exchange Online en standalone Exchange Online Protection (EOP).
ms.openlocfilehash: 0bd34639d717b979a02272e3c2f5de243c68d3ab
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636056"
---
# <a name="anti-spam-protection-faq"></a>Veelgestelde vragen over beveiliging tegen ongewenste e-mail

Dit onderwerp biedt veelgestelde vragen en antwoorden over antispambeveiliging voor Microsoft 365-klanten met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-klanten zonder Exchange Online-postvakken.

Zie [Veelgestelde vragen](quarantine-faq.md)over quarantaine voor vragen en antwoorden over de quarantaine.

Zie [Veelgestelde vragen](anti-malware-protection-faq-eop.md)over bescherming tegen malware voor vragen en antwoorden over bescherming tegen malware.

Zie Veelgestelde vragen over [anti-spoofing bescherming](anti-spoofing-protection-faq.md)voor vragen en antwoorden over anti-spoofing bescherming.

## <a name="q-by-default-what-happens-to-a-spam-detected-message"></a>V. Wat gebeurt er standaard met een door spam gedetecteerd bericht?

A. **Voor binnenkomende berichten:** De meerderheid van de spam wordt verwijderd via verbindingsfiltering, die is gebaseerd op het IP-adres van de bron-e-mailserver. Antispambeleid (ook wel spamfilterbeleid of inhoudsfilterbeleid genoemd) inspecteert en classificeert berichten als spam, bulk of phishing. Standaard worden berichten die zijn geclassificeerd als spam of bulk, bezorgd in de map Ongewenste e-mail van de ontvanger, terwijl berichten die als phishing zijn geclassificeerd, in quarantaine worden geplaatst. U het standaard antispambeleid wijzigen (van toepassing op alle ontvangers) of u aangepaste antispambeleidsregels maken met strengere instellingen voor specifieke groepen gebruikers (u bijvoorbeeld spam die naar leidinggevenden wordt verzonden, in quarantaine plaatsen). Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) en [Aanbevolen antispambeleidsinstellingen](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)configureren voor meer informatie.

> [!IMPORTANT]
> In hybride implementaties waarbij EOP on-premises postvakken beschermt, moet u twee Exchange-mailstroomregels (ook wel transportregels genoemd) configureren in uw on-premises Exchange-organisatie om de EOP-spamfilterkoppen te detecteren die aan berichten worden toegevoegd. Zie [Standalone EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) voor meer informatie. 

 **Voor uitgaande berichten:** Het bericht wordt omgeleid via de groep voor levering met [een hoog risico](high-risk-delivery-pool-for-outbound-messages.md) of wordt teruggestuurd naar de afzender in een rapport zonder levering (ook wel een NDR- of bouncebericht genoemd). Zie [Uitgaande spambesturingselementen voor](outbound-spam-controls.md)meer informatie over uitgaande spambeveiliging.

## <a name="q-whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a>V. Wat is een zero-day spam variant en hoe wordt deze behandeld door de service?

A. Een zero-day spam variant is een eerste generatie, voorheen onbekende variant van spam die nooit is vastgelegd of geanalyseerd, dus onze anti-spam filters hebben nog geen informatie beschikbaar voor het detecteren ervan. Nadat een zero-day spamsample is vastgelegd en geanalyseerd door onze spamanalisten, als het voldoet aan de spamclassificatiecriteria, worden onze antispamfilters bijgewerkt om het te detecteren en wordt het niet langer beschouwd als 'zero-day'.

**Let op:** Als u een bericht ontvangt dat mogelijk een zero-day spamvariant is, dient u het bericht bij Microsoft in te dienen met behulp van een van de methoden die in [Berichten en bestanden melden aan Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="q-do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a>V. Moet ik de service configureren om bescherming tegen spam te bieden?

A. Nadat u zich hebt aangemeld voor de service en uw domein hebt toegevoegd, wordt spamfilterautomatisch ingeschakeld. Standaard is spamfiltering afgestemd om u te beschermen zonder extra configuratie (afgezien van de eerder opgemerkte uitzondering voor zelfstandige EOP-standalone klanten in hybride omgevingen). Als beheerder u de standaardinstellingen voor het filteren van spam bewerken om zo goed mogelijk aan de behoeften van uw organisatie te voldoen. Voor een grotere granulariteit u ook antispambeleid en uitgaand antispambeleid maken dat wordt toegepast op opgegeven gebruikers, groepen of domeinen in uw organisatie. Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u de prioriteit (dat wil zeggen de lopende volgorde) van uw aangepaste beleid wijzigen.

Lees de volgende onderwerpen voor meer informatie:

[Aanbevolen instellingen voor EOP- en Office 365 ATP-beveiliging](recommended-settings-for-eop-and-office365-atp.md)

[Antibeleid configureren](configure-the-connection-filter-policy.md)

[Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)

[Het uitgaande spambeleid configureren](configure-the-outbound-spam-policy.md)

## <a name="q-if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a>V. Hoe lang duurt het voordat ik mijn wijzigingen heb opgeslagen voordat ik mijn wijzigingen heb opgeslagen?

A. Het kan tot 1 uur duren voordat de wijzigingen van kracht worden.

## <a name="q-is-bulk-email-filtering-automatically-enabled"></a>V. Is bulke-mailfilterautomatisch ingeschakeld?

A. Ja. Zie Wat is het [verschil tussen ongewenste e-mail en bulke-mail voor](what-s-the-difference-between-junk-email-and-bulk-email.md)meer informatie over bulke-mail?

## <a name="q-does-the-service-provide-url-filtering"></a>V. Biedt de service URL-filtering?

A. Ja, de service heeft een URL-filter dat controleert op URL's binnen berichten. Als URL's die zijn gekoppeld aan bekende spam of schadelijke inhoud worden gedetecteerd, wordt het bericht gemarkeerd als spam.

## <a name="q-how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a>V. Hoe kunnen klanten die de service gebruiken valse negatieve (spam) en fout-positieve (niet-spam) berichten naar Microsoft sturen?

A. Spam- en niet-spamberichten kunnen op verschillende manieren bij Microsoft worden ingediend voor analyse. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="q-can-i-get-spam-reports"></a>V. Kan ik spamrapporten ontvangen?

A. Ja, u bijvoorbeeld een spamdetectierapport krijgen in het Microsoft 365-beheercentrum. Dit rapport toont spamvolume als een telling van unieke berichten. Zie de volgende koppelingen voor meer informatie over rapportage:

Exchange Online-klanten: [monitoring, rapportage en berichttracering in Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)

Zelfstandige EOP-klanten: [rapportage en berichttracering in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)

## <a name="q-someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a>V. Iemand heeft me een bericht gestuurd en ik kan het niet vinden. Ik vermoed dat het kan zijn gedetecteerd als spam. Is er een tool die ik kan gebruiken om erachter te komen?

A. Ja, met de tool voor het traceren van berichten u e-mailberichten volgen terwijl ze door de service gaan, om erachter te komen wat er met hen is gebeurd. Zie Is een bericht gemarkeerd als spam voor meer informatie over het gebruik van de tool voor het traceren van berichten om erachter te komen waarom een bericht is gemarkeerd als [spam?](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)

## <a name="q-will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a>V. Wordt de service mijn e-mail beperkt (beoordeeld) als mijn gebruikers uitgaande spam verzenden?

A. Als meer dan de helft van de e-mail die binnen een bepaalde termijn (bijvoorbeeld per uur) van een gebruiker via de service wordt verzonden, wordt bepaald dat het spam is door Office 365, wordt de gebruiker geblokkeerd voor het verzenden van berichten. In de meeste gevallen, als een uitgaande bericht wordt bepaald als spam, wordt het doorgestuurd via de risicogroep voor levering, waardoor de kans dat de normale uitgaande IP-groep wordt toegevoegd aan een bloklijst wordt verminderd.

U een melding naar een opgegeven e-mailadres sturen wanneer een afzender wordt geblokkeerd voor het verzenden van uitgaande spam. Zie Het [uitgaande spambeleid configureren](configure-the-outbound-spam-policy.md)voor meer informatie over deze instelling.

## <a name="q-can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a>V. Kan ik een externe antispam- en anti-malwareprovider gebruiken in combinatie met Exchange Online?

A. Ja. Hoewel we u aanbevelen uw MX-record naar Microsoft te wijzen, realiseren we ons dat er legitieme zakelijke redenen zijn om uw e-mail eerst naar een andere plaats dan Microsoft te leiden.

- **Binnenkomend:** wijzig uw MX-records om naar de externe provider te verwijzen en verwijs de berichten vervolgens door naar EOP voor extra verwerking. Zie [Verbeterde filtering voor connectors in Exchange Online voor](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)meer informatie.

- **Uitgaand:** Smart Host routing configureren van Microsoft 365 naar de bestemming externe provider.

## <a name="q-does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a>V. Heeft Microsoft documentatie over hoe ik mezelf kan beschermen tegen phishing?

A. Ja. Zie [Uw privacy op internet beschermen](https://support.microsoft.com/help/4091455) voor meer informatie

## <a name="q-are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a>V. Worden spam- en malwareberichten onderzocht over wie ze heeft verzonden of overgedragen aan wetshandhavingsinstanties?

A. De dienst richt zich op spam en malware detectie en verwijdering, hoewel we af en toe kunnen onderzoeken bijzonder gevaarlijke of schadelijke spam of aanval campagnes en de daders achtervolgen. Dit kan gaan om het werken met onze juridische en digitale misdaad eenheden te nemen van een spammer botnet, het blokkeren van de spammer van het gebruik van de dienst (als ze het gebruiken voor het verzenden van uitgaande e-mail), en het doorgeven van de informatie aan de rechtshandhaving voor strafrechtelijke vervolging.

## <a name="q-what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a>V. Wat zijn een reeks beste uitgaande mailingpraktijken die ervoor zorgen dat mijn e-mail wordt bezorgd?

A. De onderstaande richtlijnen zijn best practices voor het verzenden van uitgaande e-mailberichten.

- **Het brone-maildomein moet worden opgelost in DNS.**

  Als de afzender bijvoorbeeld user@fabrikam is, wordt het domein fabrikam ophet IP-adres 192.0.43.10 opgelost.
  
  Als een verzendend domein geen A-record en geen MX-record in DNS heeft, stuurt de service het bericht door de groep voor levering met een hoger risico, ongeacht of de inhoud van het bericht spam is. Zie Groep voor levering met [een hoog risico voor uitgaande berichten voor](high-risk-delivery-pool-for-outbound-messages.md)meer informatie over de groep voor levering met een hoger risico.

- **Uitgaande e-maileserver moet een omgekeerde DNS -vermelding (PTR) hebben.**

  Als het IP-adres van de e-mailbron bijvoorbeeld 192.0.43.10 is, is `43-10.any.icann.org`de omgekeerde DNS-vermelding .'

- **De OPDRACHTEN HELO/EHLO en MAIL FROM moeten consistent zijn en aanwezig zijn in de vorm van een domeinnaam in plaats van een IP-adres.**

  De opdracht HELO/EHLO moet worden geconfigureerd om de omgekeerde DNS van het verzendende IP-adres te matchen, zodat het domein hetzelfde blijft over de verschillende delen van de berichtheaders.

- **Zorg ervoor dat de juiste SPF-records zijn ingesteld in DNS.**

  SPF-records zijn een mechanisme voor het valideren dat e-mail verzonden vanuit een domein echt afkomstig is uit dat domein en is niet vervalst. Zie de volgende koppelingen voor meer informatie over SPF-records:

  [SPF instellen om spoofing te voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [Veelgestelde vragen over domeinen](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

- **Ondertekenen e-mail met DKIM, teken met ontspannen canonicalization.**

  Als een afzender zijn berichten wil ondertekenen met Behulp van Domain Keys Identified Mail (DKIM) en ze willen uitgaande e-mail via de service verzenden, moeten ze ondertekenen met behulp van het algoritme voor het bewerken van de automatische header canonicalization. Ondertekening met strikte header canonicalization kan de handtekening ongeldig maken wanneer deze door de service gaat.

- **Domeineigenaren moeten over nauwkeurige informatie beschikken in de WHOIS-database.**

  Dit identificeert de eigenaren van het domein en hoe ze contact met hen kunnen opnemen door het invoeren van de stabiele moedermaatschappij, aanspreekpunt en naamservers.

- **Voor bulkmailers moet de naam Van: aangeven wie het bericht verzendt, terwijl de onderwerpregel van het bericht een korte samenvatting moet zijn over waar het bericht over gaat.**

  De berichtinstantie moet een duidelijke indicatie hebben van het aanbod, de service of het product. Als een afzender bijvoorbeeld een bulkmailing verzendt voor het Bedrijf Contoso, moet de e-mail van en het onderwerp erop lijken:

  > Van: marketing@contoso.com <br/> Onderwerp: Nieuwe bijgewerkte catalogus voor het kerstseizoen!

  Het volgende is een voorbeeld van wat niet te doen omdat het niet beschrijvend is:

  > Van: user@hotmail.com <br/> Onderwerp: Catalogi

- **Als het verzenden van een bulk mailing naar veel ontvangers en het bericht is in nieuwsbrief formaat, moet er een manier van afmelden aan de onderkant van het bericht.**

  De optie afmelden moet op het volgende lijken:

  > Dit bericht is door sender@fabrikam.com naar example@contoso.com gestuurd. Profiel/e-mailadres bijwerken | Direct verwijderen met **SafeUnsubscribe** &trade; | Privacybeleid

- **Als u bulke-mail verzendt, moet de acquisitie van de lijst worden uitgevoerd met dubbele opt-in. Als u een bulk mailer, dubbele opt-in is een industrie best practice.**

  Dubbele opt-in is de praktijk van het vereisen van een gebruiker om twee acties te ondernemen om zich aan te melden voor marketing mail:

  1. Zodra de gebruiker op een nog niet eerder aangevinkt selectievakje klikt waar hij zich aanbiedt om verdere aanbiedingen of e-mailberichten van de marketeer te ontvangen.

  2. Een tweede keer wanneer de marketeer een bevestigingsmail stuurt naar het opgegeven e-mailadres van de gebruiker met de vraag of hij op een tijdgevoelige link moet klikken die zijn bevestiging zal voltooien.

  Met behulp van dubbele opt-in bouwt een goede reputatie voor bulk e-mail afzenders.

- **Bulkafzenders moeten transparante inhoud maken waarvoor ze ter verantwoording kunnen worden geroepen:**

  1. Verbiage vraagt ontvangers om de afzender aan het adresboek toe te voegen, en moet duidelijk aangeven dat een dergelijke actie geen garantie is voor levering.

  2. Gebruik bij het maken van omleidingen in de hoofdtekst van het bericht een consistente koppelingsstijl.

  3. Stuur geen grote afbeeldingen of bijlagen of berichten die uitsluitend uit een afbeelding bestaan.

  4. Wanneer u trackingpixels gebruikt (webbugs of beacons), geeft u duidelijk hun aanwezigheid in uw openbare privacy- of P3P-instellingen.

- **Uitgaande bounceberichten opmaken.**

  Bij het genereren van meldingen voor de leveringsstatus (ook bekend als niet-leveringsrapporten, NDR's of bounceberichten), moeten afzenders de indeling volgen van een bounce zoals opgegeven in [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt).

- **Verwijderde teruggestuurde e-mailadressen voor niet-bestaande gebruikers.**

  Als u een NDR ontvangt die aangeeft dat een e-mailadres niet meer in gebruik is, verwijdert u de niet-bestaande e-mailalias uit uw lijst. E-mailadressen veranderen in de loop van de tijd en mensen verwijderen ze soms.

- **Gebruik het SNDS-programma (Smart Network Data Services) van Hotmail.**

  Hotmail maakt gebruik van een programma genaamd Smart Network Data Services waarmee afzenders klachten van eindgebruikers kunnen controleren. De SNDS is de primaire portal voor het oplossen van leveringsproblemen bij Hotmail.
