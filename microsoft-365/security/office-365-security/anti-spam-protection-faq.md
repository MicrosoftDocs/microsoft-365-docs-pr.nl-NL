---
title: Veelgestelde vragen over antispambescherming
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
description: Dit onderwerp biedt veelgestelde vragen en antwoorden over anti-spam bescherming. Antwoorden zijn van toepassing op EOP-klanten (Microsoft Exchange Online en Exchange Online Protection).
ms.openlocfilehash: 9be51b4967a558aec254262052d7c01446a7d643
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42805288"
---
# <a name="anti-spam-protection-faq"></a>Veelgestelde vragen over antispambescherming

Dit onderwerp biedt veelgestelde vragen en antwoorden over anti-spam bescherming. Antwoorden zijn van toepassing op EOP-klanten (Microsoft Exchange Online en Exchange Online Protection).

> [!TIP]
> Zie [Lijsten met afzenders en geblokkeerde afzenders in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)voor vragen en antwoorden over veilige afzenderlijsten en geblokkeerde afzenderlijsten. Zie [Veelgestelde vragen](quarantine-faq.md)voor quarantaine voor vragen en antwoorden over de quarantaine.

 **V. Wat gebeurt er standaard met een bericht dat door spam wordt gedetecteerd?**

A. **Voor binnenkomende berichten:** De meerderheid van de spam wordt verwijderd via verbindingsfiltering, die is gebaseerd op het IP-adres van de afzender. De service inspecteert vervolgens de inhoud van het bericht. Standaard wordt spam met inhoud verzonden naar de map Ongewenste e-mail van de ontvanger. U deze actie wijzigen. U er bijvoorbeeld voor kiezen om spamberichten naar de quarantaine te sturen door het beleid voor inhoudsfilter te configureren.

> [!IMPORTANT]
> Voor zelfstandige klanten van EOP: om ervoor te zorgen dat de mapactie **Verplaatsen naar ongewenste e-mail** werkt met on-premises postvakken, moet u twee Exchange-regels voor de stroom (ook wel transportregels genoemd) configureren op uw on-premises servers om spamkoppen van EOP te detecteren. Zie Zorgen [dat spam wordt doorgestuurd naar de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)van elke gebruiker.

 **Voor uitgaande berichten:** Het bericht wordt doorgestuurd door de groep met een levering met een hoger risico of wordt teruggestuurd en niet bezorgd, in welk geval de afzender een DSN-bericht (delivery status notification) moet ontvangen waarin staat somt dat het bericht niet kon worden bezorgd.

 **V. Wat is een zero-day spam variant en hoe wordt het behandeld door de dienst?**

A. Een zero-day spam variant is een eerste generatie, voorheen onbekende variant van spam die nooit is vastgelegd of geanalyseerd, dus onze spam content filters hebben nog geen informatie beschikbaar voor het detecteren van het. Nadat een zero-day spam monster is gevangen en geanalyseerd door onze spam-analisten, als het voldoet aan de spam classificatie criteria, onze spam content filters worden bijgewerkt om het te detecteren, en het is niet langer beschouwd als "zero-day." ( **Opmerking:** Als u een bericht ontvangt dat mogelijk een zero-day spam-variant is, om ons te helpen de service te verbeteren, dient u het bericht in bij Microsoft met behulp van een van de methoden die zijn beschreven in [Spam- en niet-spam- en phishingberichten indienen bij Microsoft voor analyse](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).)

 **V. Moet ik de service configureren om antispambescherming te bieden?**

A. Nadat u zich hebt aangemeld voor de service en uw domein hebt toegevoegd, wordt spamfiltering automatisch bedrijfsbreed ingeschakeld via het standaard antispambeleid. Het standaardbeleid is afgestemd om u te beschermen zonder extra configuratie (afgezien van de bovenstaande uitzondering voor zelfstandige eOP-klanten). Als beheerder u het standaard antispambeleid bewerken, zodat ze zijn afgestemd op de behoeften van uw organisatie. Voor een grotere granulariteit u ook aangepaste inhoudsfilterbeleidsregels maken en deze toepassen op bepaalde gebruikers, groepen of domeinen in uw organisatie. Aangepaste beleidsregels hebben altijd voorrang op het standaardbeleid, maar u de prioriteit (dat wil zeggen de lopende volgorde) van uw aangepaste beleid wijzigen.

Zie de volgende onderwerpen voor meer informatie over het configureren van uw antispambeleid:

[Het beleid van het verbindingsfilter configureren](configure-the-connection-filter-policy.md)

[Uw spamfilterbeleid configureren](configure-your-spam-filter-policies.md)

[Het uitgaande spambeleid configureren](configure-the-outbound-spam-policy.md)

 **V. Hoe lang duurt het voordat ik mijn wijzigingen heb opgeslagen voordat deze van kracht worden?**

A. Het kan tot 1 uur duren voordat de wijzigingen van kracht worden.

 **V. Is bulke-mailfilterautomatisch ingeschakeld?**

A. Standaard is de geavanceerde filteroptie **Bulk mail** ingeschakeld voor nieuwe klanten. Voor gemigreerde klanten komt deze instelling overeen met uw FOPE-configuratie. Zie Wat is het [verschil tussen ongewenste e-mail en bulke-mail voor](what-s-the-difference-between-junk-email-and-bulk-email.md) meer informatie over bulke-mail?

 **V. Biedt de service URL-filtering?**

A. Ja, de service heeft een URL-filter dat controleert op URL's in berichten. Als URL's die zijn gekoppeld aan bekende spam of schadelijke inhoud worden gedetecteerd, wordt het bericht gemarkeerd als spam.

 **V. Hoe kunnen klanten die de service gebruiken valse negatieve (spam) en vals-positieve (niet-spam)berichten naar Microsoft verzenden?**

A. Spam- en niet-spamberichten kunnen op verschillende manieren bij Microsoft worden ingediend voor analyse. Zie [Spam-, niet-spam- en phishingberichten verzenden naar Microsoft voor analyse](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)voor meer informatie.

 **V. Kan ik spamrapporten krijgen?**

A. Ja, u bijvoorbeeld een spamdetectierapport krijgen in het Microsoft 365-beheercentrum. Dit rapport toont het spamvolume als een telling van unieke berichten. Zie de volgende koppelingen voor meer informatie over rapportage:

Exchange Online-klanten: [monitoring, rapportage en berichttracering in Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)

Exchange Online Protection-klanten: [rapportage- en berichttracering in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)

 **V. Iemand stuurde me een bericht en ik kan het niet vinden. Ik vermoed dat het kan zijn gedetecteerd als spam. Is er een tool die ik kan gebruiken om uit te vinden?**

A. Ja, met de tool voor het traceren van berichten u e-mailberichten volgen terwijl ze door de service gaan, om erachter te komen wat er met hen is gebeurd. Zie Was een bericht gemarkeerd als spam voor meer informatie over het gebruik van de hulpprogramma voor het traceren van berichten om erachter te komen waarom een bericht als spam is [gemarkeerd?](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)

 **V. Wordt de service beperkt (begrenzem) mijn e-mail als mijn gebruikers uitgaande spam verzenden?**

A. Als meer dan de helft van de e-mail die binnen een bepaalde tijd (bijvoorbeeld per uur) van een gebruiker wordt verzonden, wordt bepaald als spam door Office 365, wordt de gebruiker geblokkeerd voor het verzenden van berichten. In de meeste gevallen, als een uitgaande boodschap wordt bepaald als spam, wordt het doorgestuurd door de groep met een hoog risico, waardoor de kans op de normale uitgaande IP-pool wordt toegevoegd aan een bloklijst vermindert.

U een melding naar een opgegeven e-mailadres sturen wanneer een afzender wordt geblokkeerd om uitgaande spam te verzenden. Zie [Het uitgaande spambeleid configureren](configure-the-outbound-spam-policy.md)voor meer informatie over deze instelling.

 **V. Kan ik een externe anti-spam- en anti-malwareprovider gebruiken in combinatie met Exchange Online?**

A. Ja, u een andere spam- en malwarefilterservice configureren om uw Exchange Online-mailboxen te beschermen. Om dit voor binnenkomende e-mail te doen, moet u uw e-mailberichten doorverwijzen naar de externe provider door uw MX-records te wijzigen om naar de externe provider te wijzen en vervolgens de berichten door te sturen naar EOP voor extra verwerking. Om dit voor uitgaande e-mail te doen, configureer t u de bestemming van de berichtbezorging naar de externe provider (slimme host).

 **V. Heeft Microsoft documentatie over hoe ik mezelf kan beschermen tegen phishing?**

A. Ja, dat doen we, lees [Bescherm uw privacy op het internet](https://support.microsoft.com/help/4091455)

 **V. Worden spam- en malwareberichten onderzocht over wie ze heeft verzonden of worden overgedragen aan wetshandhavingsinstanties?**

A. De dienst richt zich op spam en malware detectie en verwijdering, hoewel we af en toe kunnen onderzoeken vooral gevaarlijke of schadelijke spam of aanval campagnes en achter de daders. Dit kan betekenen dat u samenwerkt met onze juridische en digitale misdaadeenheden om een spammer-botnet neer te halen, de spammer te blokkeren om de service te gebruiken (als ze deze gebruiken voor het verzenden van uitgaande e-mail) en het doorgeven van de informatie aan de rechtshandhaving voor strafrechtelijke vervolging.

 **V. Wat zijn een reeks beste uitgaande mailingpraktijken die ervoor zorgen dat mijn post wordt bezorgd?**

A. De onderstaande richtlijnen zijn best practices voor het verzenden van uitgaande e-mailberichten.

1. **Het verzendende domein van de e-mail moet worden opgelost in DNS.**

    Als de afzender bijvoorbeeld user@example.com is, wordt het domein example.com opgelost naar het IP-adres 192.0.43.10. Als een verzendend domein geen A-record en geen MX-record in DNS heeft, zal de service het bericht door de leveringsgroep met een hoger risico leiden, ongeacht of de inhoud van het bericht spam is. Zie Groep met [een hoog risico voor uitgaande berichten voor](high-risk-delivery-pool-for-outbound-messages.md)meer informatie over de groep voor levering met een hoger risico.

2. **Het verzenden van IP-adres van de uitgaande e-mailserver moet een reverse DNS (PTR) vermelding hebben.**

    Als u bijvoorbeeld vanaf het IP-adres 192.0.43.10 verzendt, wordt de omgekeerde DNS-vermelding voor dit IP 43-10.any.icann.org.

3. **De OPDRACHTEN HELO/EHLO en MAIL FROM moeten consistent zijn en aanwezig zijn in de vorm van een domeinnaam in plaats van een IP-adres.**

    De opdracht HELO/EHLO moet worden geconfigureerd om de omgekeerde DNS van het verzendende IP-adres te matchen, zodat het domein hetzelfde blijft in de verschillende delen van de berichtkoppen.

4. **Zorg ervoor dat de juiste SPF-records zijn ingesteld in DNS.**

    SPF-records zijn een mechanisme voor het valideren dat e-mail die vanuit een domein wordt verzonden, echt afkomstig is uit dat domein en niet is vervalst. Zie de volgende koppelingen voor meer informatie over SPF-records:

    [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) (SPF in Office 365 instellen om spoofing te helpen voorkomen)

    [Veelgestelde vragen over domeinen](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

5. **E-mail ondertekenen met DKIM, ondertekenen met ontspannen canonicalization.**

    Als een afzender zijn berichten wil ondertekenen met Behulp van Domain Keys Identified Mail (DKIM) en ze willen uitgaande e-mail via de service verzenden, moeten ze zich aanmelden met behulp van het algoritme voor ontspannen headercanonicalization. Tekenen met strikte canonicalisatie van headerkan de handtekening ongeldig maken wanneer deze door de service gaat.

6. **Domeineigenaren moeten beschikken over nauwkeurige informatie in de WHOIS-database.**

    Dit identificeert de eigenaren van het domein en hoe u contact met hen opnemen door het stabiele moederbedrijf, het contactpunt en de naamservers in te voeren.

7. **Voor bulkmailers moet de naam Van: aangeven wie het bericht verzendt, terwijl de onderwerpregel van het bericht een korte samenvatting moet zijn van waar het bericht over gaat.**

    De boodschap moet een duidelijke indicatie hebben van het aanbod, de dienst of het product. Als een afzender bijvoorbeeld een bulkmailing voor het Contoso-bedrijf verzendt, moet de e-mail van en onderwerp lijken:

    Van: marketing@contoso.com

    Onderwerp: Nieuwe bijgewerkte catalogus voor het kerstseizoen!

    Het volgende is een voorbeeld van wat niet te doen, omdat het niet beschrijvend is:

    Van: user@hotmail.com

    Onderwerp: Catalogs

8. **Als het verzenden van een bulk mailing naar veel ontvangers en het bericht is in nieuwsbrief formaat, moet er een manier van afmelden aan de onderkant van het bericht.**

    De optie afmelden moet lijken op het volgende:

    Dit bericht is door sender@fabrikam.com naar example@contoso.com verzonden. Profiel/e-mailadres bijwerken | Onmiddellijke verwijdering met **SafeUnsubscribe**™ | Privacybeleid

9. **Als het verzenden van bulke-mail, moet list acquisitie worden uitgevoerd met behulp van dubbele opt-in. Als u een bulk mailer, dubbele opt-in is een industrie best practice.**

    Dubbele opt-in is de praktijk van het vereisen van een gebruiker om twee acties te nemen aan te melden voor marketing mail:

   1. Zodra de gebruiker klikt op een eerder niet aangevinkt selectievakje waar ze zich aanmelden om verdere aanbiedingen of e-mailberichten van de marketeer te ontvangen.

   2. Een tweede keer wanneer de marketeer een bevestigingsmail stuurt naar het opgegeven e-mailadres van de gebruiker met de vraag om op een tijdgevoelige link te klikken die de bevestiging zal voltooien.

      Het gebruik van dubbele opt-in bouwt een goede reputatie op voor afzenders van bulke-mail.

10. **Bulkafzenders moeten transparante inhoud maken waarvoor ze ter verantwoording kunnen worden geroepen:**

    1. Verbiage met het verzoek om ontvangers de afzender toe te voegen aan het adresboek moet duidelijk aangeven dat een dergelijke actie geen garantie voor levering is.

    2. Gebruik bij het construeren van omleidingen in de hoofdtekst van het bericht een consistente koppelingsstijl.

    3. Stuur geen grote afbeeldingen of bijlagen of berichten die uitsluitend uit een afbeelding bestaan.

    4. Bij het gebruik van tracking pixels (web bugs of beacons), duidelijk staat hun aanwezigheid in uw openbare privacy of P3P-instellingen.

11. **Meldingen van uitgaande leveringsstatus opmaken.**

    Bij het genereren van meldingsberichten voor de leveringsstatus moeten afzenders de indeling van een bounce volgen zoals opgegeven in [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt).

12. **Teruggestuurde e-mailadressen verwijderen voor niet-bestaande gebruikers.**

    Als u een NDR ontvangt die aangeeft dat een e-mailadres niet meer in gebruik is, verwijdert u de niet-bestaande e-mailalias uit uw lijst. E-mailadressen veranderen in de loop van de tijd en mensen gooien ze soms weg.

13. **Gebruik het Smart Network Data Services (SNDS) programma van Hotmail.**

    Hotmail maakt gebruik van een programma genaamd Smart Network Data Services waarmee afzenders klachten van eindgebruikers kunnen controleren. De SNDS is de primaire portal voor het oplossen van leveringsproblemen naar Hotmail.

## <a name="for-more-information"></a>Voor meer informatie

[Office 365 email anti-spam protection](anti-spam-protection.md)

[Lijsten met afzenders en geblokkeerde afzenders in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)

[Kopteksten voor spamberichten](anti-spam-message-headers.md)

[Backscatter messages and EOP](backscatter-messages-and-eop.md)(Backscatter-berichten en EOP)
