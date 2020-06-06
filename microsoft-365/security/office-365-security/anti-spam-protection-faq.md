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
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen veelgestelde vragen en antwoorden over antispambeveiliging bekijken in Exchange Online Protection (EOP).
ms.openlocfilehash: 11c80a4cb93cf0c37ffbdf917e238960dd8fea80
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588038"
---
# <a name="anti-spam-protection-faq"></a>Veelgestelde vragen over beveiliging tegen ongewenste e-mail

Dit onderwerp biedt veelgestelde vragen en antwoorden over anti-malware bescherming voor Microsoft 365 organisaties met mailboxen in Exchange Online, of standalone Exchange Online Protection (EOP) organisaties zonder Exchange Online mailboxen.

Zie [Faq quarantaine](quarantine-faq.md)voor vragen en antwoorden over de quarantaine.

Zie Veelgestelde vragen over [anti-malwarebeveiliging](anti-malware-protection-faq-eop.md)voor vragen en antwoorden over bescherming tegen malware.

Zie Veelgestelde vragen over antispoedbeveiliging voor vragen en antwoorden over [antispoedbeveiliging.](anti-spoofing-protection-faq.md)

## <a name="by-default-what-happens-to-a-spam-detected-message"></a>Wat gebeurt er standaard met een door spam gedetecteerd bericht?

**Voor binnenkomende berichten:** De meerderheid van spam wordt verwijderd via verbindingsfiltering, die is gebaseerd op het IP-adres van de brone-mailserver. Antispambeleid (ook wel spamfilterbeleid of inhoudsfilterbeleid genoemd) inspecteert en classificeert berichten als spam, bulk of phishing. Berichten die zijn geclassificeerd als spam of bulk, worden standaard bezorgd in de map Ongewenste e-mail van de ontvanger, terwijl berichten die als phishing zijn geclassificeerd, in quarantaine worden geplaatst. U het standaardantispambeleid wijzigen (van toepassing op alle ontvangers), of u aangepaste antispambeleid maken met strengere instellingen voor specifieke groepen gebruikers (u bijvoorbeeld spam die naar leidinggevenden wordt verzonden in quarantaine plaatsen). Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) en [Aanbevolen antispambeleidsinstellingen](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)configureren voor meer informatie.

> [!IMPORTANT]
> In hybride implementaties waarbij EOP on-premises postvakken beschermt, moet u twee Exchange-e-mailstroomregels (ook wel transportregels genoemd) configureren in uw on-premises Exchange-organisatie om de EOP-spamfilterkoppen te detecteren die aan berichten worden toegevoegd. Zie [Standalone EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) voor meer informatie. 

 **Voor uitgaande berichten:** Het bericht wordt doorgestuurd via de [leveringspool met een hoog risico](high-risk-delivery-pool-for-outbound-messages.md) of wordt teruggestuurd naar de afzender in een rapport zonder levering (ook wel een NDR- of bouncebericht genoemd). Zie Uitgaande spamcontroles voor meer informatie over uitgaande [spambeveiliging.](outbound-spam-controls.md)

## <a name="whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a>Wat is een zero-day spam variant en hoe wordt het behandeld door de dienst?

Een zero-day spam variant is een eerste generatie, voorheen onbekende variant van spam die nooit is vastgelegd of geanalyseerd, dus onze anti-spam filters hebben nog geen informatie beschikbaar voor het detecteren ervan. Nadat een zero-day spammonster is vastgelegd en geanalyseerd door onze spamanalisten, worden onze antispamfilters bijgewerkt om het te detecteren en wordt het niet langer beschouwd als 'zero-day'.

**Let op:** Als u een bericht ontvangt dat een spamvariant van zero-day kan zijn, om ons te helpen de service te verbeteren, dient u het bericht bij Microsoft in met behulp van een van de methoden die in [Rapportberichten en -bestanden worden](report-junk-email-messages-to-microsoft.md)beschreven bij Microsoft.

## <a name="do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a>Moet ik de service configureren om bescherming tegen spam te bieden?

Nadat u zich hebt aangemeld voor de service en uw domein hebt toegevoegd, wordt spamfiltering automatisch ingeschakeld. Standaard is spamfiltering afgestemd om u te beschermen zonder dat u extra configuratie nodig hebt (afgezien van de eerder genoteerde uitzondering voor zelfstandige EOP-standalone klanten in hybride omgevingen). Als beheerder u de standaardinstellingen voor spamfilters zo eenvoudig bewerken dat het beste aan de behoeften van uw organisatie voldoet. Voor meer granulariteit u ook antispambeleid en uitgaand antispambeleid maken dat wordt toegepast op specifieke gebruikers, groepen of domeinen in uw organisatie. Aangepaste beleidsregels hebben altijd voorrang op het standaardbeleid, maar u de prioriteit (dat wil zeggen de uitvoerende volgorde) van uw aangepaste beleid wijzigen.

Lees de volgende onderwerpen voor meer informatie:

[Aanbevolen instellingen voor EOP- en Office 365 ATP-beveiliging](recommended-settings-for-eop-and-office365-atp.md)

[Verbindingsfilter configureren in EOP](configure-the-connection-filter-policy.md)

[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)

[Het uitgaande spambeleid configureren](configure-the-outbound-spam-policy.md)

## <a name="if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a>Hoe lang duurt het voordat ik mijn wijzigingen heb opgeslagen nadat ik mijn wijzigingen heb opgeslagen?

Het kan tot 1 uur duren voordat de wijzigingen van kracht worden.

## <a name="is-bulk-email-filtering-automatically-enabled"></a>Is bulk-e-mailfiltering automatisch ingeschakeld?

Ja. Zie Wat is het [verschil tussen ongewenste e-mail en bulke-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md)

## <a name="does-the-service-provide-url-filtering"></a>Biedt de service URL-filtering?

Ja, de service heeft een URL-filter dat controleert op URL's in berichten. Als URL's die zijn gekoppeld aan bekende spam of schadelijke inhoud worden gedetecteerd, wordt het bericht gemarkeerd als spam.

## <a name="how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a>Hoe kunnen klanten die de service gebruiken valse negatieve (spam) en vals-positieve (niet-spam) berichten naar Microsoft sturen?

Spam- en niet-spamberichten kunnen op verschillende manieren bij Microsoft worden ingediend voor analyse. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="can-i-get-spam-reports"></a>Kan ik spamrapporten krijgen?

Ja, u bijvoorbeeld een spamdetectierapport krijgen in het Microsoft 365-beheercentrum. Dit rapport toont spamvolume als een telling van unieke berichten. Zie de volgende links voor meer informatie over rapportage:

Exchange Online-klanten: [Monitoring, rapportage en message tracing in Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)

Standalone EOP-klanten: [Rapportage en berichttracering in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)

## <a name="someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a>Iemand stuurde me een bericht en ik kan het niet vinden. Ik vermoed dat het kan zijn gedetecteerd als spam. Is er een tool die ik kan gebruiken om uit te vinden?

Ja, met de tool voor het traceren van berichten u e-mailberichten volgen terwijl ze door de service gaan, om erachter te komen wat er met hen is gebeurd. Zie Is een bericht gemarkeerd als spam voor meer informatie over het gebruik van de hulpprogramma voor het traceren van berichten om erachter te komen waarom een bericht als spam [is gemarkeerd?](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)

## <a name="will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a>Zal de service throttle (rate limit) mijn e-mail als mijn gebruikers uitgaande spam verzenden?

Als meer dan de helft van de e-mail die binnen een bepaald tijdsbestek (bijvoorbeeld per uur) van een gebruiker via de service wordt verzonden, wordt bepaald dat deze spam is, wordt de gebruiker geblokkeerd voor het verzenden van berichten. In de meeste gevallen, als een uitgaande bericht wordt bepaald als spam, wordt het doorgestuurd via de hoog-risico leveringspool, die de kans op de normale uitgaande-IP-pool wordt toegevoegd aan een bloklijst vermindert.

U een melding naar een opgegeven e-mailadres sturen wanneer een afzender wordt geblokkeerd door uitgaande spam te verzenden. Zie [Het uitgaande spambeleid configureren](configure-the-outbound-spam-policy.md)voor meer informatie over deze instelling.

## <a name="can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a>Kan ik een antispam- en anti-malwareprovider van derden gebruiken in combinatie met Exchange Online?

Ja. Hoewel we u aanraden uw MX-record naar Microsoft te wijzen, realiseren we ons dat er legitieme zakelijke redenen zijn om uw e-mail eerst naar een andere dan Microsoft te leiden.

- **Binnenkomend**: Wijzig uw MX-records om naar de externe provider te verwijzen en vervolgens de berichten om te leiden naar EOP voor extra verwerking. Zie [Uitgebreide filtering voor connectoren in Exchange Online voor](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)meer informatie.

- **Uitgaand**: Configureer slimme hostroutering van Microsoft 365 naar de externe provider van de bestemming.

## <a name="does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a>Heeft Microsoft documentatie over hoe ik mezelf kan beschermen tegen phishing?

Ja. Zie [Uw privacy beschermen op internet voor](https://support.microsoft.com/help/4091455) meer informatie

## <a name="are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a>Worden spam- en malwareberichten onderzocht naar wie ze heeft verzonden of naar wetshandhavingsinstanties wordt overgebracht?

De dienst richt zich op spam en malware detectie en verwijdering, hoewel we af en toe kunnen onderzoeken bijzonder gevaarlijke of schadelijke spam of aanval campagnes en achter de daders. Dit kan inhouden dat we samenwerken met onze legale en digitale misdaadeenheden om een spammerbotnet te maken, de spammer te blokkeren om de service te gebruiken (als ze deze gebruiken voor het verzenden van uitgaande e-mail) en de informatie door te geven aan de rechtshandhaving voor strafrechtelijke vervolging.

## <a name="what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a>Wat zijn een set van de beste uitgaande mailing praktijken die ervoor zorgen dat mijn e-mail wordt geleverd?

De onderstaande richtlijnen zijn best practices voor het verzenden van uitgaande e-mailberichten.

- **Het brone-maildomein moet worden opgelost in DNS.**

  Als de afzender bijvoorbeeld user@fabrikam is, wordt het domein fabrikam opgelost naar het IP-adres 192.0.43.10.
  
  Als een verzendend domein geen A-record heeft en geen MX-record in DNS, zal de service het bericht door de leveringspool met een hoger risico leiden, ongeacht of de inhoud van het bericht spam is. Zie [Een leveringspool](high-risk-delivery-pool-for-outbound-messages.md)met een hoog risico voor uitgaande berichten voor meer informatie over de pool met een hoger risico.

- **Uitgaande e-mail eserver moet een omgekeerde DNS (PTR) vermelding.**

  Als het IP-adres van de e-mailbron bijvoorbeeld 192.0.43.10 is, is de omgekeerde DNS-vermelding `43-10.any.icann.org` .'

- **De helo/EHLO- en MAIL FROM-opdrachten moeten consistent zijn en aanwezig zijn in de vorm van een domeinnaam in plaats van een IP-adres.**

  De opdracht HELO/EHLO moet worden geconfigureerd om de omgekeerde DNS van het verzendende IP-adres aan te passen, zodat het domein hetzelfde blijft over de verschillende delen van de berichtkoppen.

- **Zorg ervoor dat de juiste SPF-records zijn ingesteld in DNS.**

  SPF-records zijn een mechanisme voor het valideren van die e-mail die vanuit een domein wordt verzonden, komt echt uit dat domein en is niet vervalst. Zie de volgende koppelingen voor meer informatie over SPF-records:

  [SPF instellen om adresvervalsing te helpen voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [Veelgestelde vragen over domeinen](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

- **Het ondertekenen van e-mail met DKIM, teken met ontspannen canonicalization.**

  Als een afzender zijn berichten wil ondertekenen met Behulp van Domain Keys Identified Mail (DKIM) en hij/zij uitgaande e-mail via de service wil verzenden, moet hij of zij ondertekenen met behulp van het algoritme voor het ontspannen algoritme voor canonicalisatie van de koptekst. Ondertekening met strikte header canonicalisatie kan de handtekening ongeldig maken wanneer deze door de service gaat.

- **Domeineigenaren moeten beschikken over nauwkeurige informatie in de WHOIS-database.**

  Hiermee worden de eigenaren van het domein geïdentificeerd en hoe u contact met hen opnemen door de stabiele moedermaatschappij, het contactpunt en de naamservers in te voeren.

- **Voor bulkmailers moet de naam Van: weergeven wie het bericht verzendt, terwijl de onderwerpregel van het bericht een korte samenvatting moet zijn over waar het bericht over gaat.**

  De berichttekst moet een duidelijke indicatie hebben van het aanbod, de service of het product. Als een afzender bijvoorbeeld een bulkmailing verzendt voor het bedrijf Contoso, is de volgende e-mail Van en onderwerp moet lijken op:

  > Van: marketing@contoso.com <br/> Onderwerp: Nieuwe bijgewerkte catalogus voor het kerstseizoen!

  Het volgende is een voorbeeld van wat niet te doen, omdat het niet beschrijvend is:

  > Van: user@hotmail.com <br/> Onderwerp: Catalogi

- **Als het verzenden van een bulk mailing naar veel ontvangers en het bericht is in nieuwsbrief formaat, moet er een manier van uitschrijven aan de onderkant van het bericht.**

  De optie afmelden moet lijken op het volgende:

  > Dit bericht is door sender@fabrikam.com naar example@contoso.com verzonden. Profiel/e-mailadres bijwerken | Onmiddellijke verwijdering met **SafeUnsubscribe** &trade; | Privacybeleid

- **Als u bulke-mail verzendt, moet de aankoop van de lijst worden uitgevoerd met behulp van dubbele opt-in. Als u een bulk mailer, dubbele opt-in is een industrie best practice.**

  Dubbele opt-in is de praktijk van het vereisen van een gebruiker om twee acties te ondernemen om zich aan te melden voor marketing mail:

  1. Zodra de gebruiker klikt op een niet eerder aangevinkt selectievakje waar ze zich aanmelden om verdere aanbiedingen of e-mailberichten van de marketeer te ontvangen.

  2. Een tweede keer wanneer de marketeer een bevestigingsmail stuurt naar het opgegeven e-mailadres van de gebruiker met de vraag om op een tijdgevoelige link te klikken die de bevestiging zal voltooien.

  Met behulp van dubbele opt-in bouwt een goede reputatie voor bulk e-mail afzenders.

- **Bulk afzenders moeten transparante inhoud maken waarvoor ze ter verantwoording kunnen worden geroepen:**

  1. Verbiage verzoekt ontvangers de afzender toe te voegen aan het adresboek moet duidelijk aangeven dat een dergelijke actie geen garantie is voor levering.

  2. Wanneer u omleidingen in de hoofdtekst van het bericht maakt, gebruikt u een consistente koppelingsstijl.

  3. Stuur geen grote afbeeldingen of bijlagen of berichten die uitsluitend uit een afbeelding bestaan.

  4. Wanneer u trackingpixels (webbugs of beacons) gebruikt, vermeldt u duidelijk hun aanwezigheid in uw openbare privacy of P3P-instellingen.

- **Opmaak uitgaande bounceberichten.**

  Bij het genereren van meldingen van leveringsstatusmeldingen (ook bekend als niet-leveringsrapporten, NDR's of bounceberichten), moeten afzenders de indeling van een bounce volgen zoals opgegeven in [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt).

- **Verwijder teruggestuurde e-mailadressen voor niet-bestaande gebruikers.**

  Als u een NDR ontvangt die aangeeft dat een e-mailadres niet meer in gebruik is, verwijdert u de niet-bestaande e-mailalias uit uw lijst. E-mailadressen veranderen in de loop van de tijd en mensen gooien ze soms weg.

- **Gebruik het Smart Network Data Services (Smart Network Data Services) programma van Hotmail.**

  Hotmail maakt gebruik van een programma genaamd Smart Network Data Services waarmee afzenders klachten van eindgebruikers kunnen controleren. De SNDS is de primaire portal voor het oplossen van problemen met de levering van Hotmail.
