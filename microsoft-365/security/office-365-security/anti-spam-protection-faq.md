---
title: Veelgestelde vragen over beveiliging tegen ongewenste e-mail
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen veelgestelde vragen en antwoorden over bescherming tegen spam bekijken in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cc1aa26832830dce4f529566a589cb8bf3e1df01
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925218"
---
# <a name="anti-spam-protection-faq"></a>Veelgestelde vragen over beveiliging tegen ongewenste e-mail

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Dit onderwerp bevat veelgestelde vragen en antwoorden over bescherming tegen malware voor Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken.

Zie Veelgestelde vragen over quarantaine voor vragen en antwoorden over de [quarantaine.](quarantine-faq.md)

Zie Veelgestelde vragen en antwoorden [](anti-malware-protection-faq-eop.md)over anti-malwarebeveiliging.

Zie Veelgestelde vragen over bescherming tegen spoofing voor vragen en antwoorden over bescherming tegen [spoofing.](anti-spoofing-protection-faq.md)

## <a name="by-default-what-happens-to-a-spam-detected-message"></a>Wat gebeurt er standaard met een door spam gedetecteerd bericht?

**Voor binnenkomende berichten:** De meeste spam wordt verwijderd via verbindingsfilters, die is gebaseerd op het IP-adres van de bron-e-mailserver. Antispambeleid (ook wel spamfilterbeleid of inhoudsfilterbeleid genoemd) controleert en classificeert berichten als spam, bulk of phishing. Berichten die zijn geclassificeerd als spam of bulksgewijs worden standaard bezorgd in de map Ongewenste e-mail van de geadresseerde, terwijl berichten die als phishing zijn geclassificeerd, in quarantaine worden geplaatst. U kunt het standaard antispambeleid wijzigen (van toepassing op alle geadresseerden) of u kunt aangepaste antispambeleidsregels maken met striktere instellingen voor specifieke groepen gebruikers (u kunt bijvoorbeeld spam in quarantaine plaatsen die naar leidinggevenden wordt verzonden). Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) en Aanbevolen [antispambeleidsinstellingen configureren voor meer informatie.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

> [!IMPORTANT]
> In hybride implementaties waarin EOP on-premises postvakken beschermt, moet u twee Exchange-regels voor e-mailstroom (ook wel transportregels genoemd) configureren in uw on-premises Exchange-organisatie om de EOP-spamfilterkoppen te detecteren die aan berichten worden toegevoegd. Zie [Standalone EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) voor meer informatie. 

 **Voor uitgaande berichten:** Het bericht wordt gerouteerd via de groep met een hoog risico of wordt geretourneerd aan de afzender in een rapport over niet-bezorging (ook wel een NDR- of bouncebericht genoemd). [](high-risk-delivery-pool-for-outbound-messages.md) Zie Besturingselementen voor uitgaande spam voor meer informatie over uitgaande [spambeveiliging.](outbound-spam-controls.md)

## <a name="whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a>Wat is een zero-day spamvariant en hoe wordt dit verwerkt door de service?

Een zero-day spamvariant is een eerste generatie, voorheen onbekende variant van spam die nooit is vastgelegd of geanalyseerd, zodat onze antispamfilters nog geen informatie beschikbaar hebben om deze te detecteren. Nadat een steekproef van nul dagen spam is vastgelegd en geanalyseerd door onze spamanalisten, worden onze antispamfilters bijgewerkt om deze te detecteren en wordt het niet meer beschouwd als 'zero-day'.

**Opmerking:** Als u een bericht ontvangt dat een zero-day spamvariant kan zijn, kunt u het bericht naar Microsoft verzenden met behulp van een van de methoden die in Berichten en bestanden rapporteren worden beschreven bij [Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a>Moet ik de service zo configureren dat ik antispambeveiliging kan bieden?

Nadat u zich hebt registreren voor de service en uw domein hebt toevoegen, wordt spamfilters automatisch ingeschakeld. Spamfilters zijn standaard afgestemd om u te beschermen zonder extra configuratie nodig te hebben (afgezien van de eerder bekende uitzondering voor zelfstandige EOP-zelfstandige klanten in hybride omgevingen). Als beheerder kunt u de standaardinstellingen voor spamfilters bewerken om het beste aan de behoeften van uw organisatie te voldoen. Voor meer granulariteit kunt u ook antispambeleid en uitgaand antispambeleid maken dat wordt toegepast op opgegeven gebruikers, groepen of domeinen in uw organisatie. Aangepaste beleidsregels hebben altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (dat wil zeggen de lopende volgorde) van uw aangepaste beleid wijzigen.

Zie de volgende onderwerpen voor meer informatie:

[Aanbevolen instellingen voor EOP- en Microsoft Defender-beveiliging voor Office 365](recommended-settings-for-eop-and-office365-atp.md)

[Verbindingsfilters configureren in EOP](configure-the-connection-filter-policy.md)

[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)

[Het uitgaande spambeleid configureren](configure-the-outbound-spam-policy.md)

## <a name="if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a>Als ik een wijziging aan een antispambeleid maak, hoe lang duurt het nadat ik mijn wijzigingen heb op slaan voordat deze van kracht worden?

Het kan maximaal 1 uur duren voordat de wijzigingen van kracht worden.

## <a name="is-bulk-email-filtering-automatically-enabled"></a>Is bulksgewijs filteren van e-mail automatisch ingeschakeld?

Ja. Zie Wat is het verschil tussen ongewenste e-mail en bulk-e-mail? voor meer informatie over [bulksgewijs e-mail.](what-s-the-difference-between-junk-email-and-bulk-email.md)

## <a name="does-the-service-provide-url-filtering"></a>Biedt de service URL-filtering?

Ja, de service heeft een URL-filter dat controleert op URL's in berichten. Als URL's die zijn gekoppeld aan bekende spam of schadelijke inhoud worden gedetecteerd, wordt het bericht gemarkeerd als spam.

## <a name="how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a>Hoe kunnen klanten die de service gebruiken, fout-negatieve (spam) en onwaar positieve (niet-spam) berichten naar Microsoft verzenden?

Spam- en niet-spamberichten kunnen op verschillende manieren worden ingediend bij Microsoft voor analyse. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="can-i-get-spam-reports"></a>Kan ik spamrapporten krijgen?

Ja, u kunt bijvoorbeeld een spamdetectierapport krijgen in het Microsoft 365-beheercentrum. In dit rapport ziet u het spamvolume als een aantal unieke berichten. Zie de volgende koppelingen voor meer informatie over rapportage:

Exchange Online-klanten: [Monitoring, Reporting en Message Tracing in Exchange Online](/exchange/monitoring/monitoring)

Zelfstandige EOP-klanten: [Rapportage en bericht traceren in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)

## <a name="someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a>Iemand heeft me een bericht gestuurd en ik kan het niet vinden. Ik vermoed dat het mogelijk is gedetecteerd als spam. Is er een hulpmiddel dat ik kan gebruiken om erachter te komen?

Ja, met het hulpprogramma bericht traceren kunt u e-mailberichten volgen terwijl ze door de service lopen, om erachter te komen wat er met hen is gebeurd. Zie Was een bericht gemarkeerd als spam voor meer informatie over het gebruik van het hulpprogramma voor het traceren van berichten om erachter te komen waarom een bericht is gemarkeerd als [spam?](/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)

## <a name="will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a>Wordt mijn e-mail beperkt door de service (tarieflimiet) als mijn gebruikers uitgaande spam verzenden?

Als meer dan de helft van de e-mail die binnen een bepaald tijdsbestek (bijvoorbeeld per uur) van een gebruiker via de service wordt verzonden, door EOP als spam wordt beschouwd, wordt de gebruiker geblokkeerd voor het verzenden van berichten. In de meeste gevallen wordt een uitgaande e-mail door de groep met hoog risico's gerouteerd, waardoor de kans wordt verkleind dat de normale uitgaande IP-groep wordt toegevoegd aan een bloklijst.

U kunt een melding verzenden naar een opgegeven e-mailadres wanneer een afzender wordt geblokkeerd bij het verzenden van uitgaande spam. Zie Het uitgaande [spambeleid configureren](configure-the-outbound-spam-policy.md)voor meer informatie over deze instelling.

## <a name="can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a>Kan ik een externe antispam- en anti-malwareprovider gebruiken in combinatie met Exchange Online?

Ja. Hoewel het raadzaam is om uw MX-record aan te wijzen op Microsoft, realiseren we ons dat er legitieme zakelijke redenen zijn om uw e-mail eerst naar een andere plaats te sturen dan Microsoft.

- **Binnenkomende:** Wijzig uw MX-records om naar de externe provider te wijzen en omleiden de berichten vervolgens naar EOP voor aanvullende verwerking. Zie Verbeterde filtering [voor verbindingslijnen in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)voor meer informatie.

- **Uitgaande:** Configureer slimme hostroutering van Microsoft 365 naar de doelprovider van derden.

## <a name="does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a>Heeft Microsoft documentatie over hoe ik mijzelf kan beschermen tegen phishing?

Ja. Zie Uw privacy op internet beschermen voor [meer informatie.](https://support.microsoft.com/help/4091455)

## <a name="are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a>Worden spam- en malwareberichten onderzocht over wie ze heeft verzonden of worden ze overgebracht naar rechtshandhavingsinstanties?

De service richt zich op het opsporen en verwijderen van spam en malware, hoewel we af en toe vooral gevaarlijke of schadelijke spam- of aanvalscampagnes kunnen onderzoeken en de daders kunnen achtervolgen. Dit kan betrekking hebben op het werken met onze juridische en digitale criminaliteitseenheden om een spammer botnet neer te zetten, de spammer te blokkeren van het gebruik van de service (als ze deze gebruiken voor het verzenden van uitgaande e-mail) en het doorgeven van de informatie aan de ordehandhavers voor strafrechtelijke vervolging.

## <a name="what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a>Wat zijn de beste uitgaande verzendpraktijken om ervoor te zorgen dat mijn e-mail wordt bezorgd?

De onderstaande richtlijnen zijn best practices voor het verzenden van uitgaande e-mailberichten.

- **Het bron-e-maildomein moet worden opgelost in DNS.**

  Als de afzender bijvoorbeeld een user@fabrikam, wordt het domein fabrikam verplaatst naar het IP-adres 192.0.43.10.

  Als een verzendend domein geen A-record en geen MX-record in DNS heeft, wordt het bericht door de service door de groep met een hoger risico verzonden, ongeacht of de inhoud van het bericht spam is. Zie Risicovolle bezorgingsgroep voor uitgaande berichten voor meer informatie over de groep met een hoger [risico.](high-risk-delivery-pool-for-outbound-messages.md)

- **Uitgaande e-mailserver moet een reverse DNS -vermelding (PTR) hebben.**

  Als het IP-adres van de e-mailbron bijvoorbeeld 192.0.43.10 is, is de omgekeerde DNS-invoer `43-10.any.icann.org` .'

- **De HELO/EHLO- en MAIL FROM-opdrachten moeten consistent zijn en aanwezig zijn in de vorm van een domeinnaam in plaats van een IP-adres.**

  De opdracht HELO/EHLO moet zo worden geconfigureerd dat deze overeenkomen met de reverse DNS van het verzendende IP-adres, zodat het domein hetzelfde blijft in de verschillende onderdelen van de berichtkoppen.

- **Zorg ervoor dat de juiste SPF-records zijn ingesteld in DNS.**

  SPF-records zijn een mechanisme om te valideren dat e-mail die vanuit een domein wordt verzonden, echt afkomstig is van dat domein en niet wordt vervalst. Zie de volgende koppelingen voor meer informatie over SPF-records:

  [SPF instellen om adresvervalsing te helpen voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [Veelgestelde vragen over domeinen](../../admin/setup/domains-faq.yml#how-can-i-validate-spf-records-for-my-domain)

- **Als u e-mail ondertekent bij DKIM, tekent u met een relaxte canonicalisatie.**

  Als een afzender zijn berichten wil ondertekenen met domeinsleutels geïdentificeerde e-mail (DKIM) en uitgaande e-mail via de service wil verzenden, moet hij of zij zich aanmelden met het algoritme voor het canoniseren van een ontspannen koptekst. Het ondertekenen met een strikte canonieke koptekst kan de handtekening ongeldig maken wanneer de handtekening door de service wordt doorverkoend.

- **Domeineigenaren moeten nauwkeurige informatie hebben in de WHOIS-database.**

  Hiermee worden de eigenaren van het domein geïdentificeerd en hoe u contact met hen op kunt nemen door het stabiele moederbedrijf, het contactpunt en de naamservers in te gaan.

- **Voor bulkmailers moet de naam Van: weerspiegelen wie het bericht verstuurt, terwijl de onderwerpregel van het bericht een korte samenvatting moet zijn van waar het bericht over gaat.**

  De berichtindicatie moet een duidelijke indicatie hebben van het aanbod, de service of het product. Als een afzender bijvoorbeeld een bulkmailing verstuurt voor het contoso-bedrijf, moet het e-mailbericht Van en Onderwerp er als volgt uit zien:

  > Van: marketing@contoso.com <br> Onderwerp: Nieuwe bijgewerkte catalogus voor het kerstseizoen!

  Hieronder volgt een voorbeeld van wat u niet moet doen omdat het niet beschrijvend is:

  > Van: user@hotmail.com <br> Onderwerp: Catalogi

- **Als het verzenden van een bulkmailing naar veel geadresseerden en het bericht in de nieuwsbriefindeling is, moet er een manier zijn om het abonnement onder aan het bericht op te geven.**

  De optie afmelden moet er als volgt uit zien:

  > Dit bericht is per example@contoso.com verzonden sender@fabrikam.com. Profiel/e-mailadres bijwerken | Direct verwijderen met **SafeUnsubscribe** &trade; | Privacybeleid

- **Als u bulk-e-mail verstuurt, moet het verkrijgen van een lijst worden uitgevoerd met dubbele opt-in. Als u een bulkmailer bent, is dubbele opt-in een goede gewoonte voor de industrie.**

  Dubbele aanmelding is de gewoonte dat een gebruiker twee acties moet uitvoeren om zich aan te melden voor marketingmail:

  1. Wanneer de gebruiker eenmaal op een eerder niet-uitgeschakeld selectievakje klikt, kiest hij of zij zich voor verdere aanbiedingen of e-mailberichten van de marketeer.

  2. Een tweede keer wanneer de marketeer een bevestigings-e-mail verzendt naar het opgegeven e-mailadres van de gebruiker met de vraag of hij of zij op een tijdgevoelige koppeling moet klikken om de bevestiging te voltooien.

  Als u dubbele opt-in gebruikt, wordt een goede reputatie opgebouwd voor bulk-afzenders van e-mail.

- **Bulk afzenders moeten transparante inhoud maken waarvoor ze verantwoordelijk kunnen worden gehouden:**

  1. Verbiage vraagt dat geadresseerden de afzender aan het adresboek toevoegen, moeten duidelijk stellen dat een dergelijke actie geen garantie voor bezorging is.

  2. Gebruik een consistente koppelingsstijl bij het maken van omleidingen in de berichtstijl.

  3. Verzend geen grote afbeeldingen of bijlagen of berichten die uitsluitend uit een afbeelding zijn samengesteld.

  4. Wanneer u trackingpixels (web bugs of beacons) gebruikt, geeft u duidelijk aan dat ze aanwezig zijn in uw openbare privacy- of P3P-instellingen.

- **Uitgaande bounceberichten opmaken.**

  Bij het genereren van meldingen over de bezorgingsstatus (ook wel bekend als niet-bezorgingsrapporten, NDR's of niet-bezorgdberichten), moeten afzenders de notatie van een bounce volgen, zoals is opgegeven in [RFC 3464.](https://www.ietf.org/rfc/rfc3464.txt)

- **Niet-bestaande e-mailadressen verwijderen.**

  Als u een NDR ontvangt die aangeeft dat een e-mailadres niet meer wordt gebruikt, verwijdert u de niet-bestaande e-mailalias uit uw lijst. E-mailadressen veranderen in de tijd en mensen verwijderen ze soms.

- **Gebruik het SNDS-programma (Smart Network Data Services) van Hotmail.**

  Hotmail gebruikt een programma met de naam Smart Network Data Services waarmee afzenders klachten kunnen controleren die door eindgebruikers zijn ingediend. De SNDS is de primaire portal voor het oplossen van bezorgingsproblemen bij Hotmail.