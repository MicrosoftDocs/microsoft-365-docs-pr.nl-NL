---
title: Veelgestelde vragen over beveiliging tegen ongewenste e-mail
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
- m365-initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen Veelgestelde vragen en antwoorden over antispam beveiliging bekijken in Exchange Online Protection (EOP).
ms.openlocfilehash: c6ad0bf903ef7283415035581ed11ecb6e4336bd
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48411852"
---
# <a name="anti-spam-protection-faq"></a>Veelgestelde vragen over beveiliging tegen ongewenste e-mail

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Dit onderwerp bevat veelgestelde vragen en antwoorden over beveiliging tegen malware voor Microsoft 365-organisaties met postvakken in Exchange Online, of zelfstandige Exchange Online Protection (EOP)-organisaties zonder postvakken van Exchange Online.

Zie Veelgestelde vragen over [quarantaine](quarantine-faq.md)voor vragen en antwoorden over de quarantaine.

Zie [Veelgestelde vragen over beveiliging tegen malware](anti-malware-protection-faq-eop.md)voor vragen en antwoorden over beveiliging tegen malware.

Zie [Veelgestelde vragen over beveiliging tegen spoofing](anti-spoofing-protection-faq.md)voor vragen en antwoorden over beveiliging tegen spoofing.

## <a name="by-default-what-happens-to-a-spam-detected-message"></a>Wat gebeurt er met een spam gedetecteerde fout?

**Voor inkomende berichten:** Het merendeel van de spam wordt verwijderd via het filteren van verbindingen, dat is gebaseerd op het IP-adres van de bron-e-mailserver. Anti spam beleid (ook wel spamfilter beleid of beleidsregels voor inhouds filters) inspecteert en classificeert berichten als spam, bulk of phishing. Berichten die zijn geclassificeerd als spam of bulksgewijs, worden standaard weergegeven in de map Ongewenste E-mail van de geadresseerde, terwijl berichten die zijn geclassificeerd als phishing, worden quarantaine. U kunt het standaard Antispambeleid wijzigen (geldt voor alle geadresseerden), of u kunt een aangepast Antispambeleid maken met strikte instellingen voor specifieke groepen gebruikers (u kunt bijvoorbeeld ongewenste e-mail die naar leidinggevenden wordt verzonden). Zie [Antispambeleid](configure-your-spam-filter-policies.md) en [Aanbevolen antispam beleidsinstellingen](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)configureren voor meer informatie.

> [!IMPORTANT]
> In hybride implementaties waarbij EOP on-premises postvakken beveiligt, moet u twee Exchange-e-mail stroom regels (ook wel de zogenaamde transportregels) configureren in uw on-premises Exchange-organisatie om de EOP spamfilter koppen te detecteren die aan berichten zijn toegevoegd. Zie [Standalone EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) voor meer informatie. 

 **Voor uitgaande berichten:** Het bericht wordt doorgestuurd via de [bezorgings pool voor hoog risico](high-risk-delivery-pool-for-outbound-messages.md) of wordt teruggegeven aan de afzender in een rapport over niet-uitgevoerde bezorging (ook wel een NDR genoemd of een stuiter bericht). Zie [uitgaand spam besturingselementen](outbound-spam-controls.md)voor meer informatie over uitgaande spam bescherming.

## <a name="whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a>Wat is een spam variant met een nulwaarde en hoe wordt deze door de service verwerkt?

Een Zero-Day spam variant is een eerste generatie, eerder onbekende variant van spam die niet is opgenomen of geanalyseerd, zodat onze antispam filters nog geen gegevens kunnen detecteren. Na het opsporen en analyseren van een spam analist via onze spam analisten vindt u na het voldoen aan de criteria voor de classificatie van spam, dan zijn de filters voor ongewenste e-mail bijgewerkt zodat het niet meer wordt beschouwd.

**Opmerking:** Als u een bericht ontvangt dat mogelijk een variant van een variant met een nulwaarde is, zodat u de service kunt verbeteren, moet u het bericht indienen bij Microsoft met een van de methoden die worden beschreven in [berichten en bestanden aan Microsoft rapporteren](report-junk-email-messages-to-microsoft.md).

## <a name="do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a>Moet ik de service configureren om bescherming tegen spam te bieden?

Nadat u zich hebt aangemeld voor de service en uw domein toevoegt, wordt het filteren van spam automatisch ingeschakeld. Filters voor spam filteren is standaard afgestemd op het beschermen van uw gebruikers zonder dat u extra configuratie hoeft te hebben (afgezien van de eerdere uitzondering voor zelfstandige EOP zelfstandige klanten in hybride omgevingen). Als beheerder kunt u de standaardinstellingen voor het filteren van ongewenste e-mail bewerken, zodat deze het beste aansluiten op de behoeften van uw organisatie. Voor een grotere nauwkeurigheid kunt u ook Antispambeleid en beleid voor uitgaande anti-spam maken die worden toegepast op opgegeven gebruikers, groepen of domeinen in uw organisatie. Aangepaste beleidsregels hebben altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (dat wil zeggen, de actieve order) van uw aangepaste beleid wijzigen.

Zie de volgende onderwerpen voor meer informatie:

[Aanbevolen instellingen voor EOP en Office 365 ATP-beveiliging](recommended-settings-for-eop-and-office365-atp.md)

[Het filteren van verbindingen configureren in EOP](configure-the-connection-filter-policy.md)

[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)

[Het uitgaande spam beleid configureren](configure-the-outbound-spam-policy.md)

## <a name="if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a>Als ik een wijziging aanbrengt in een anti-spam beleid, hoe lang duurt het voordat mijn wijzigingen worden doorgevoerd?

Het kan tot 1 uur duren voordat de wijzigingen zijn doorgevoerd.

## <a name="is-bulk-email-filtering-automatically-enabled"></a>Wordt filteren van bulk berichten automatisch ingeschakeld?

Ja. Zie [Wat is het verschil tussen ongewenste e-mail en bulk-](what-s-the-difference-between-junk-email-and-bulk-email.md)e-mail? voor meer informatie over bulk-e-mail.

## <a name="does-the-service-provide-url-filtering"></a>Levert de service URL'S filteren?

Ja, de service heeft een URL-filter waarmee wordt gecontroleerd op Url's in berichten. Als Url's die zijn gekoppeld aan bekende spam of schadelijke inhoud worden gedetecteerd, wordt het bericht als spam gemarkeerd.

## <a name="how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a>Hoe kunnen klanten met de service onjuiste negatieve (spam) en fout-positieve (niet-spam) berichten naar Microsoft versturen?

U kunt op verschillende manieren spam-en niet-spamberichten ter analyse indienen bij Microsoft. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="can-i-get-spam-reports"></a>Kan ik spam rapporten weergeven?

Ja, u kunt bijvoorbeeld een spam detectie rapport weergeven in het Microsoft 365-Beheercentrum. In dit rapport wordt spam volume weergegeven als het aantal unieke berichten. Zie de volgende koppelingen voor meer informatie over rapportage:

Exchange Online-klanten: [controle, rapportage en berichten traceren in Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)

Zelfstandige EOP klanten: [rapporteren en berichten traceren in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)

## <a name="someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a>Iemand heeft mij een bericht gestuurd en ik kan het niet vinden. Ik vermoedt dat het al als spam is gedetecteerd. Is er een hulpmiddel waarmee ik erachter kan komen?

Met behulp van het hulpprogramma voor bericht tracering kunt u e-mailberichten volgen terwijl ze de service passeren, om erachter te komen wat er is gebeurd. Zie voor meer informatie over het gebruik van het hulpprogramma voor bericht tracering waarom een bericht is gemarkeerd als spam [?](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)

## <a name="will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a>Wordt de servicebeperking (tarief limiet) voor mijn e-mail weergegeven als mijn gebruikers uitgaande spam versturen?

Als meer dan de helft van het e-mailbericht dat vanaf een gebruiker is verzonden via de service binnen een bepaald tijdsbestek (bijvoorbeeld per uur), wordt vastgesteld dat er spam wordt verzonden via EOP, wordt de gebruiker geblokkeerd voor het verzenden van berichten. In de meeste gevallen geldt dat als een uitgaand e-mailbericht als ongewenste e-mail is vastgesteld, wordt doorgestuurd via de bezorgings pool voor hoog risico, waardoor de kans kleiner is dat de normale uitgaande IP-groep wordt toegevoegd aan een bloklijst.

U kunt een melding verzenden naar een opgegeven e-mailadres wanneer een afzender het verzenden van uitgaande spam blokkeert. Zie voor meer informatie over deze instelling [het beleid voor uitgaande spam configureren](configure-the-outbound-spam-policy.md).

## <a name="can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a>Kan ik een externe antispam-en anti-malware provider gebruiken in combinatie met Exchange Online?

Ja. We raden u aan om uw MX-record naar Microsoft te laten verwijzen, maar er zijn ook goede zakelijke redenen om uw e-mail door te sturen naar een ander dan Microsoft.

- **Inkomend**: Wijzig uw MX-records zodat ze verwijzen naar de externe provider, en leid de berichten vervolgens om naar EOP voor verdere verwerking. Zie voor meer informatie [uitgebreid filteren van connectors in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- **Uitgaand**: Configureer Smart host routering van microsoft 365 naar de doeltoepassing van derden.

## <a name="does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a>Heb Microsoft een documentatie over hoe ik mij kan beschermen tegen phishing scams?

Ja. Zie [uw privacy beschermen op Internet](https://support.microsoft.com/help/4091455) voor meer informatie.

## <a name="are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a>Worden spam-en malware-berichten ter onderzoek verzonden naar wie ze zijn verzonden, of worden ze overgezet naar de politiediensten?

De service richt zich op het detecteren en verwijderen van spam en malware, hoewel we af en toe de schade van spam of kwaadaardige campagnes kunnen nastreven en de Perpetrators gaan. Dit kan van toepassing zijn op een afzender van een natuurlijke en digitale criminaliteit, zodat de spammer van de dienst gebruik kan maken (als ze dit gebruiken voor het verzenden van uitgaande e-mail) en de informatie ter naleving van de gerechtelijke vervolging ter vergelijkings dienst doorgeven.

## <a name="what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a>Wat zijn de beste uitgaand e-mail praktijken, zodat mijn e-mail wordt bezorgd?

De hieronder weergegeven richtlijnen zijn aanbevolen procedures voor het verzenden van uitgaande e-mailberichten.

- **U moet het bron-e-mail domein omzetten in DNS.**

  Als de afzender bijvoorbeeld user@fabrikam is, wordt het domein fabrikam omgezet in het IP Address 192.0.43.10.
  
  Als een verzendend domein geen A-record en geen MX-record in DNS bevat, stuurt de service het bericht door naar de groep grotere risico levering, ongeacht of de inhoud van het bericht spam is. Zie voor meer informatie over de extra groep risico levering de [groep hoog risico voor uitgaande berichten](high-risk-delivery-pool-for-outbound-messages.md).

- **Uitgaande e-mail eServer moet een reverse DNS-vermelding (PTR) hebben.**

  Bijvoorbeeld: als het IP-adres van de e-mail bron 192.0.43.10 is, dan is de omgekeerde DNS-vermelding `43-10.any.icann.org` .

- **De opdrachten HELO/EHLO en MAIL uit zijn consistent en staan in de vorm van een domeinnaam in plaats van een IP-adres.**

  De opdracht HELO/EHLO moet zo worden geconfigureerd dat deze overeenkomt met de omgekeerde DNS van het verzendende IP-adres, zodat het domein ongewijzigd blijft in de verschillende delen van de berichtkoppen.

- **Zorg ervoor dat de juiste SPF-records zijn ingesteld in DNS.**

  SPF-records zijn een mechanisme voor het valideren van de verzending van e-mailberichten die afkomstig zijn van een domein en die niet is vervalst. Zie de volgende koppelingen voor meer informatie over SPF-records:

  [SPF instellen om adresvervalsing te helpen voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [Veelgestelde vragen over domeinen](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

- **Meld u aan bij een e-mailbericht met DKIM, Meld u met beperkte beeigenlijke**

  Als een afzender zijn of haar berichten wil ondertekenen met behulp van via de E-mail (DKIM) en via de service uitgaande e-mail wil verzenden, moet hij zich nu aanmelden met behulp van de een beperkte koptekst van de header. Als u zich aanmeldt met strikte header-basisisatie, kunt u de handtekening mogelijk ongeldig maken wanneer de service wordt doorlopen.

- **Domein eigenaren moeten de juiste informatie in de WHOIS-database hebben.**

  Hiermee worden de eigenaren van het domein aangegeven en wordt aangegeven hoe u contact kunt opnemen met de eigenaren van het bovenliggende bedrijf, het punt van de contactpersoon en de naamservers.

- **Voor bulk Mailers moet de naam van: de naam aangeven wie het bericht verstuurt, en de onderwerpregel van het bericht moet een beknopt overzicht van de inhoud van het bericht.**

  De hoofdtekst van het bericht dient een duidelijke aanwijzing te hebben van de aanbieding, service of product. Als een afzender een bulk mailing verzendt voor de contoso-organisatie, kunt u bijvoorbeeld de volgende items van het e-mailbericht en de naam van het onderwerp zien:

  > Van: marketing@contoso.com <br/> Onderwerp: nieuwe bijgewerkte catalogus voor een kerst seizoen.

  Hieronder ziet u een voorbeeld van wat niet te doen is omdat dit niet het geval is:

  > Van: user@hotmail.com <br/> Onderwerp: catalogi

- **Als u een groot aantal geadresseerden en het bericht in de nieuwsbrief indeling verzendt, moet u de abonnement onder aan het bericht op een andere manier afmelden.**

  De optie voor het afschrijven van Afmelden moet er ongeveer als volgt uitzien:

  > Dit bericht is verzonden naar example@contoso.com door sender@fabrikam.com. Profiel/e-mailadres bijwerken | Direct verwijderen met **SafeUnsubscribe** &trade; | Privacybeleid

- **Als u bulk-e-mail verzendt, moet u de lijst-aanschaf uitvoeren met behulp van dubbele opt-in. Als u een grote mailings hebt, kunt u het beste een goede gewoonte van een bedrijfstak maken.**

  Met de optie voor het instellen van een e-mailbericht kunt u ervoor zorgen dat een gebruiker twee acties moet ondernemen voor de registratie van marketing mail:

  1. Wanneer de gebruiker op een eerder uitgeschakeld selectievakje klikt, waar ze zich ook voor een extra aanbieding of e-mailbericht van de marketing willen ontvangen.

  2. Een tweede keer wanneer een marketing bericht wordt verzonden naar het e-mailadres van de gebruiker waarin u wordt gevraagd om op een tijds gevoelige koppeling te klikken die hun bevestiging zal voltooien.

  Met de optie dubbele opt-in maakt u een goede reputatie voor bulksgewijs e-mail afzenders.

- **Voor bulk afzenders moet u transparante inhoud maken waarvoor deze account kan worden bewaard:**

  1. Verbiage waarom vraagt dat geadresseerden de afzender toevoegen aan het adresboek, moet u duidelijk aangeven dat deze actie geen garantie biedt.

  2. Wanneer u omleidingen in de hoofdtekst van het bericht bouwt, gebruikt u een consistente koppelingsstijl.

  3. Verstuur geen grote afbeeldingen of bijlagen, of berichten die uitsluitend uit een afbeelding bestaan.

  4. Wanneer u tracerings pixels (web bugs of beacons) hanteert, moet u hun aanwezigheidsstatus duidelijk aangeven in uw openbare privacy-of P3P-instellingen.

- **Uitgaande berichten voor een stuiteren opmaken.**

  Wanneer de bezorgingsstatus meldingsberichten (ook wel rapporten over niet-uitgevoerde bezorging, Ndr's of stuiteren) worden gegenereerd, moeten afzenders de indeling van een stuitering volgen zoals is opgegeven in [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt).

- **Verwijder niet-bestaande e-mailadressen voor niet-bestaande gebruikers.**

  Als u een NDR ontvangt waarmee wordt aangegeven dat een e-mailadres niet meer in gebruik is, verwijdert u de niet-bestaande e-mail alias uit uw lijst. E-mailadressen veranderen in de loop van de tijd, en personen kunnen ze ook verwijderen.

- **Gebruik het SNDS-programma (Smart Network Data Services) van Hotmail.**

  Hotmail gebruikt een programma genaamd Smart Network Data Services waarmee afzenders de klachten kunnen controleren die door eindgebruikers zijn verzonden. De SNDS is de primaire portal voor het oplossen van problemen met de bezorging van Hotmail.
