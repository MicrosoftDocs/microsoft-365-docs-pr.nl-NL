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
description: Beheerders kunnen veelgestelde vragen en antwoorden over beveiliging tegen spam bekijken in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8620ad3f99c45dae3442ec89d879124053c1a005
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175977"
---
# <a name="anti-spam-protection-faq"></a>Veelgestelde vragen over beveiliging tegen ongewenste e-mail

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Dit onderwerp bevat veelgestelde vragen en antwoorden over beveiliging tegen malware voor Microsoft 365-organisaties met postvakken in Exchange Online, of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken.

Zie Veelgestelde vragen over quarantaine voor vragen en [antwoorden over de quarantaine.](quarantine-faq.md)

Zie veelgestelde vragen en antwoorden over bescherming tegen malware tegen [malware.](anti-malware-protection-faq-eop.md)

Zie Veelgestelde vragen en antwoorden over bescherming tegen [spoofing.](anti-spoofing-protection-faq.md)

## <a name="by-default-what-happens-to-a-spam-detected-message"></a>Wat gebeurt er standaard met een door spam gedetecteerd bericht?

**Voor inkomende berichten:** Het grootste deel van de spam wordt verwijderd via verbindingsfilters, die zijn gebaseerd op het IP-adres van de bron-e-mailserver. Antispambeleid (ook wel spamfilterbeleid of inhoudsfilterbeleid genoemd) controleert en classificeert berichten als spam, bulksgewijs of phishing. Standaard worden berichten die zijn geclassificeerd als spam of bulksgewijs, bezorgd in de map Ongewenste e-mail van de geadresseerde, terwijl berichten die als phishing zijn geclassificeerd in quarantaine worden geplaatst. U kunt het standaardbeleid tegen ongewenste e-mail wijzigen (geldt voor alle geadresseerden) of u kunt een aangepast antispambeleid maken met striktere instellingen voor specifieke groepen gebruikers (u kunt bijvoorbeeld spam in quarantaine plaatsen die naar leidinggevenden wordt verzonden). Zie Antispambeleid [](configure-your-spam-filter-policies.md) configureren en Instellingen voor aanbevolen [antispambeleid configureren voor meer informatie.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

> [!IMPORTANT]
> In hybride implementaties waarin EOP on-premises postvakken beschermt, moet u twee Exchange-regels voor de e-mailstroom (ook wel transportregels genoemd) configureren in uw on-premises Exchange-organisatie om de EOP-spamfilterkoppen te detecteren die aan berichten zijn toegevoegd. Zie [Standalone EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) voor meer informatie. 

 **Voor uitgaande berichten:** Het bericht wordt omgeleid [](high-risk-delivery-pool-for-outbound-messages.md) via de bezorgingsgroep met hoog risico of wordt geretourneerd aan de afzender in een rapport over niet-bezorging (ook wel een NDR- of niet-bezorgdbericht genoemd). Zie de besturingselementen voor uitgaande spam voor meer informatie over de beveiliging van [uitgaande spam.](outbound-spam-controls.md)

## <a name="whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a>Wat is een gratis spamvariant en hoe wordt deze door de service verwerkt?

Een spamvariant van nul dagen is een eerste generatie, voorheen onbekende variant van spam die nooit is vastgelegd of geanalyseerd, dus onze antispamfilters bevatten nog geen informatie die kan worden gedetecteerd. Nadat een 0-daagse spamvoorbeeld is vastgelegd en geanalyseerd door onze spamanalisten, en het voldoet aan de classificatiecriteria voor spam, worden onze antispamfilters bijgewerkt om het te detecteren en wordt het niet langer beschouwd als 'nul-dag'.

**Opmerking:** Als u een bericht ontvangt dat een 0-daagse spamvariant kan zijn, kunt u ons helpen de service te verbeteren door het bericht naar Microsoft te verzenden met een van de methoden die in Rapportberichten en bestanden worden beschreven bij [Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a>Moet ik de service zo configureren dat deze bescherming tegen spam biedt?

Nadat u zich hebt registreren voor de service en uw domein hebt toevoegen, wordt spamfilter automatisch ingeschakeld. Standaard is spamfilters aangepast om u te beschermen zonder dat er extra configuratie nodig is (afgezien van de eerder aangekondigde uitzondering voor zelfstandige klanten van EOP in hybride omgevingen). Als beheerder kunt u de standaardinstellingen voor het filteren van ongewenste e-mail aanpassen aan de behoeften van uw organisatie. Voor een grotere granulatie kunt u ook antispambeleid en uitgaand antispambeleid maken dat wordt toegepast op opgegeven gebruikers, groepen of domeinen in uw organisatie. Aangepaste beleidsregels hebben altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (dat wil zeggen de volgorde van de regels) van uw aangepaste beleidsregels wijzigen.

Zie de volgende onderwerpen voor meer informatie:

[Aanbevolen instellingen voor EOP- en Microsoft Defender voor Office 365-beveiliging](recommended-settings-for-eop-and-office365-atp.md)

[Verbindingsfiltering configureren in EOP](configure-the-connection-filter-policy.md)

[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)

[Het uitgaande spambeleid configureren](configure-the-outbound-spam-policy.md)

## <a name="if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a>Als ik een wijziging aan een antispambeleid maak, hoe lang duurt het dan nadat ik mijn wijzigingen heb op slaan, voordat deze van kracht worden?

Het kan maximaal één uur duren voordat de wijzigingen zijn doorgevoerd.

## <a name="is-bulk-email-filtering-automatically-enabled"></a>Is bulkmailfilter automatisch ingeschakeld?

Ja. Zie wat het verschil is tussen ongewenste e-mail en bulk-e-mail voor meer informatie over [bulk-e-mail.](what-s-the-difference-between-junk-email-and-bulk-email.md)

## <a name="does-the-service-provide-url-filtering"></a>Biedt de service URL-filtering?

Ja, de service heeft een URL-filter dat controleert op URL's in berichten. Als URL's die zijn gekoppeld aan bekende spam of schadelijke inhoud worden gedetecteerd, wordt het bericht gemarkeerd als spam.

## <a name="how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a>Hoe kunnen klanten die de service gebruiken fout-negatieve (spam) en fout-positieve (niet-spam) berichten naar Microsoft verzenden?

Spam en niet-spamberichten kunnen op verschillende manieren bij Microsoft worden ingediend voor analyse. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="can-i-get-spam-reports"></a>Kan ik spamrapporten krijgen?

Ja, u kunt bijvoorbeeld een spamdetectierapport krijgen in het Microsoft 365-beheercentrum. Dit rapport toont het aantal unieke berichten dat wordt verzonden. Zie de volgende koppelingen voor meer informatie over rapporten:

Klanten met Exchange Online: controle, rapportage en [berichttracering in Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)

Zelfstandige EOP-klanten: [Rapportage en bericht traceren in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)

## <a name="someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a>Iemand heeft me een bericht gestuurd en ik kan het niet vinden. Ik vermoed dat het als spam is gedetecteerd. Is er een hulpprogramma dat ik kan gebruiken om erachter te komen?

Ja, met het hulpprogramma bericht traceren kunt u e-mailberichten volgen terwijl ze door de service worden verzonden om erachter te komen wat er met de berichten is gebeurd. Zie Een bericht gemarkeerd als spam voor meer informatie over het gebruik van het hulpprogramma bericht traceren om erachter te komen waarom een bericht als spam [is gemarkeerd?](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)

## <a name="will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a>Beperkt de service (snelheidslimiet) mijn e-mail als mijn gebruikers uitgaande spam verzenden?

Als meer dan de helft van de e-mail die via de service via de service wordt verzonden binnen een bepaalde periode (bijvoorbeeld per uur) door EOP wordt vastgesteld als spam, wordt de gebruiker geblokkeerd voor het verzenden van berichten. In de meeste gevallen wordt een uitgaand bericht dat als spam wordt beschouwd, gerouteerd via de bezorgingsgroep met hoog risico, waardoor de kans wordt verkleind dat de normale uitgaande IP-groep wordt toegevoegd aan een blokkeringslijst.

U kunt een melding verzenden naar een opgegeven e-mailadres wanneer het verzenden van uitgaande spam wordt geblokkeerd. Zie Het beleid voor uitgaande spam configureren voor meer [informatie over deze instelling.](configure-the-outbound-spam-policy.md)

## <a name="can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a>Kan ik een externe provider tegen spam en malware gebruiken in combinatie met Exchange Online?

Ja. Hoewel we u aanraden uw MX-record naar Microsoft te laten wijzen, komen we tot de hoogte dat er betrouwbare zakelijke redenen zijn om uw e-mail naar een andere plaats dan eerst Naar Microsoft te door te sturen.

- **Binnenkomende:** wijzig uw MX-records zo dat deze naar de externe provider wijzen en redirect de berichten om naar EOP voor aanvullende verwerking. Zie [Enhanced Filtering for connectors in Exchange Online voor meer informatie.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- **Uitgaand:** configureer slimme hostroutering vanuit Microsoft 365 naar de externe provider.

## <a name="does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a>Bevat Microsoft documentatie over hoe ik mijzelf kan beschermen tegen phishingpraktijken?

Ja. Zie Uw privacy beschermen [op internet voor meer informatie](https://support.microsoft.com/help/4091455)

## <a name="are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a>Worden spam- en malwareberichten onderzocht door wie ze hebben verzonden of worden ze overgebracht naar entiteiten van de advocatenkantoor?

De service richt zich op het detecteren en verwijderen van spam en malware, maar soms onderzoeken we soms vooral gevaarlijke of schadelijke spam- of aanvalscampagnes en voeren we de aandacht op. Hiervoor kan het nodig zijn om samen te werken met onze juridische en digitale eenheden voor digitale criminelen om een spammer-botnet op te pakken, de spammer te blokkeren voor het gebruik van de service (als deze deze gebruikt voor het verzenden van uitgaande e-mail) en het doorgeven van de informatie aan de advocatenkantoor voor strafrechtelijke activiteiten.

## <a name="what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a>Wat zijn de beste uitgaande mailingprocedures die ervoor zorgen dat mijn e-mail wordt bezorgd?

De onderstaande richtlijnen zijn de beste procedures voor het verzenden van uitgaande e-mailberichten.

- **Het bron-e-maildomein moet worden opgelost in DNS.**

  Als de afzender bijvoorbeeld user@fabrikam, wordt door het domein fabrikam het IP-adres 192.0.43.10 opgelost.

  Als een verzendend domein geen A-record en geen MX-record in DNS heeft, routeert de service het bericht via de bezorgingsgroep met hoog risico, ongeacht of de inhoud van het bericht spam is. Zie de groep met hoog risico voor uitgaande berichten voor meer informatie over de bezorgingsgroep met een hoog [risico.](high-risk-delivery-pool-for-outbound-messages.md)

- **Een uitgaande e-mailserver moet een reverse-DNS-vermelding (PTR) hebben.**

  Als het IP-adres van de e-mailbron bijvoorbeeld 192.0.43.10 is, is de omgekeerde DNS-vermelding `43-10.any.icann.org` .'

- **De opdrachten HELO/EHLO en MAIL FROM moeten consistent zijn en aanwezig zijn in de vorm van een domeinnaam in plaats van een IP-adres.**

  De opdracht HELO/EHLO moet zo worden geconfigureerd dat deze overeenkomen met de omgekeerde DNS van het verzendende IP-adres, zodat het domein in de verschillende onderdelen van de berichtkoppen hetzelfde blijft.

- **Controleer of de juiste SPF-records zijn ingesteld in DNS.**

  SPF-records zijn een mechanisme om te valideren dat e-mail die vanuit een domein wordt verzonden, eigenlijk afkomstig is van dat domein en niet is vervalst. Zie de volgende koppelingen voor meer informatie over SPF-records:

  [SPF instellen om adresvervalsing te helpen voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [Veelgestelde vragen over domeinen](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

- **Onderteken e-mail met DKIM, onderteken met vereenigde canonieke normalisatie.**

  Als een afzender zijn berichten wil ondertekenen met Domeinsleutels geïdentificeerde e-mail (DKIM) en hij of zij uitgaande e-mail via de service wil verzenden, moet deze zich ondertekenen met de grote algoritme canonicalization header. Als u een handtekening met strikt canonieke kopteksten aantekent, kan dit de handtekening ongeldig maken wanneer deze de service doorstaat.

- **Domeineigenaren moeten nauwkeurige informatie in de WHOIS-database hebben.**

  Hiermee worden de eigenaren van het domein geïdentificeerd en hoe u contact met hen kunt opnemen door het stabiele bovenliggende bedrijf, het contactpunt en de naamservers in te gaan.

- **Voor bulkmailers moet de naam Van: laten zien wie het bericht verstuurt, terwijl de onderwerpregel van het bericht een kort overzicht moet zijn van waar het bericht over gaat.**

  De bericht zelf moet een duidelijke indicatie hebben van het aanbod, de service of het product. Als een afzender bijvoorbeeld een bulkmail verstuurt voor het bedrijf Contoso, moet het e-mailbericht Van en Onderwerp er als volgt uit zien:

  > Van: marketing@contoso.com <br> Onderwerp: Nieuwe bijgewerkte catalogus voor de kerstperiode!

  Hier volgt een voorbeeld van wat u niet moet doen omdat het niet beschrijvend is:

  > Van: user@hotmail.com <br> Onderwerp: Catalogi

- **Als u een bulkmailing verstuurt naar een groot aantal geadresseerden en het bericht in nieuwsbriefindeling is, moet er een manier zijn om u af te schrijven onder aan het bericht.**

  De optie voor het afmelden zou er als volgt uit moeten zien:

  > Dit bericht is per example@contoso.com verzonden sender@fabrikam.com. Profiel/e-mailadres bijwerken | Direct verwijderen met **SafeUnsubscribe** &trade; | Privacybeleid

- **Als u bulkmail verstuurt, moet de aanschaf van een lijst worden uitgevoerd met behulp van dubbele aant-in. Als u bulksgewijs e-mailt, kunt u het beste double opt-in gebruiken.**

  Met dubbele aanmelding moet een gebruiker twee acties uitvoeren om zich te registreren voor marketingmail:

  1. Wanneer de gebruiker op een eerder uitgeschakeld selectievakje klikt, kan deze zich ervoor kiezen om verdere aanbiedingen of e-mailberichten van de marketer te ontvangen.

  2. Een tweede keer dat de marketer een bevestigingsbericht verstuurt naar het opgegeven e-mailadres van de gebruiker, waarin de gebruiker wordt gevraagd te klikken op een tijdgevoelige koppeling om de bevestiging te voltooien.

  Het gebruik van double opt-in zorgt voor een goede reputatie van afzenders van bulk-e-mail.

- **Bulksge keer dienen transparante inhoud te maken waarvoor ze verantwoordelijk kunnen worden gehouden:**

  1. Bij het verzoek om geadresseerden de afzender toe te voegen aan het adresboek, moet duidelijk worden aangegeven dat een dergelijke actie geen garantie is voor bezorging.

  2. Gebruik een consistente koppelingsstijl bij het maken van omleiding in de bericht zelf.

  3. Verzend geen grote afbeeldingen of bijlagen of berichten die uitsluitend uit een afbeelding bestaan.

  4. Wanneer u tracking pixels (web bugs ofbakens) gebruikt, moet u hun aanwezigheid duidelijk laten zien in uw openbare privacy- of P3P-instellingen.

- **Maak uitgaande niet-uitgaande berichten op.**

  Bij het genereren van meldingen over de afleveringsstatus (ook wel bekend als rapporten over niet-bezorging, NDR's of niet-bezorgdberichten), moeten afzenders de indeling van een niet-bezorgdbericht volgen zoals is opgegeven in [RFC 3464.](https://www.ietf.org/rfc/rfc3464.txt)

- **Niet-bestaande e-mailadressen verwijderen voor niet-bestaande gebruikers.**

  Als u een NDR ontvangt die aangeeft dat een e-mailadres niet meer wordt gebruikt, verwijdert u de niet-bestaande e-mailalias uit uw lijst. E-mailadressen veranderen in de tijd en deze worden soms genegeerd.

- **Gebruik het SNDS-programma (Smart Network Data Services) van Hotmail.**

  Hotmail gebruikt het programma Smart Network Data Services waarmee afzenders klachten van eindgebruikers kunnen controleren. SNDS is de primaire portal voor het oplossen van bezorgingsproblemen bij Hotmail.
