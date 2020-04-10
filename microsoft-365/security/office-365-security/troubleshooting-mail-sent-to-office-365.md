---
title: Problemen met e-mail die naar Office 365 worden verzonden
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
description: In dit artikel vindt u informatie over probleemoplossing voor afzenders die problemen ondervinden wanneer ze e-mail naar inboxen in Office 365 proberen te verzenden en aanbevolen procedures voor bulkmailing naar Office 365-klanten.
ms.openlocfilehash: 7c5d355f1037df94d856ffff7080d4a12d22f709
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211905"
---
# <a name="troubleshooting-mail-sent-to-office-365"></a>Problemen met e-mail die naar Office 365 worden verzonden

In dit artikel vindt u informatie over probleemoplossing voor afzenders die problemen ondervinden wanneer ze e-mail naar inboxen in Office 365 proberen te verzenden en aanbevolen procedures voor bulkmailing naar Office 365-klanten.

## <a name="troubleshooting-common-problems-with-mail-delivery-to-office-365"></a>Veelvoorkomende problemen met e-mailbezorging naar Office 365 oplossen

Kies uit een van deze veelvoorkomende problemen.

- [Beheert u de verzendreputatie van uw IP en domein?](#are-you-managing-your-ip-and-domains-sending-reputation)

- [Stuurt u e-mail vanaf nieuwe IP-adressen?](#are-you-sending-email-from-new-ip-addresses)

- [Controleren of uw DNS correct is ingesteld](#confirm-that-your-dns-is-set-up-correctly)

- [Zorg ervoor dat u niet adverteren jezelf als een niet-routeerbare IP](#ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip)

- [U hebt een NDR (Non-Delivery Report) ontvangen bij het verzenden van e-mail naar een gebruiker in Office 365](#you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365)

- [Mijn e-mail is geland in de ongewenste map van de ontvanger in EOP](#my-email-landed-in-the-recipients-junk-folder-in-eop)

- [Verkeer vanaf mijn IP-adres wordt beperkt door EOP](#traffic-from-my-ip-address-is-throttled-by-eop)

### <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>Beheert u de verzendreputatie van uw IP en domein?

EOP-filtertechnologieën zijn ontworpen om antispambeveiligingen te bieden voor Microsoft Office 365 en andere Microsoft-producten zoals Exchange Server, Microsoft Office Outlook en Windows Live Mail. We maken ook gebruik van SPF, DKIM en DMARC; e-mailverificatietechnologieën die helpen bij het oplossen van het probleem van spoofing en phishing door te controleren of het domein dat de e-mail verzendt, daartoe is gemachtigd. EOP-filtering wordt beïnvloed door een aantal factoren die verband houden met het verzenden van IP, domein, authenticatie, lijstnauwkeurigheid, klachtenpercentages, inhoud en meer. Van deze, een van de belangrijkste factoren in het rijden van de reputatie van een afzender en hun vermogen om e-mail te leveren is hun junk e-mail klacht tarief.

### <a name="are-you-sending-email-from-new-ip-addresses"></a>Stuurt u e-mail vanaf nieuwe IP-adressen?

IP-adressen die niet eerder werden gebruikt om e-mail te verzenden, hebben doorgaans geen reputatie opgebouwd in onze systemen. Als gevolg hiervan hebben e-mails van nieuwe IP's meer kans op leveringsproblemen. Zodra het IP een reputatie heeft opgebouwd voor het niet verzenden van spam, zal EOP meestal zorgen voor een betere e-maillevering.

Nieuwe IP's die worden toegevoegd voor domeinen die zijn geverifieerd onder bestaande SPF-records, ervaren doorgaans het extra voordeel van het overnemen van een deel van de verzendreputatie van het domein. Als uw domein heeft een goede serverreputatie nieuwe IP's kunnen ervaren een snellere oprit tijd. Een nieuwe IP kan verwachten volledig worden opvoeren binnen een paar weken of eerder, afhankelijk van het volume, lijst nauwkeurigheid, en ongewenste e-mail klachtenpercentages.

### <a name="confirm-that-your-dns-is-set-up-correctly"></a>Controleren of uw DNS correct is ingesteld

Voor instructies over het maken en onderhouden van DNS-records, inclusief de MX-record die vereist is voor e-mailroutering, moet u contact opnemen met uw DNS-hostingprovider.

### <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>Zorg ervoor dat u niet adverteren jezelf als een niet-routeerbare IP

We accepteren geen e-mail van afzenders die niet op zoek zijn naar reverse-DNS. In sommige gevallen adverteren legitieme afzenders zichzelf verkeerd als een niet-internet routeerbaar IP wanneer ze een verbinding met EOP proberen te openen. IP-adressen die zijn gereserveerd voor privénetwerken (niet-routeerbaar) zijn onder andere:

- 192.168.0.0/16 (of 192.168.0 - 192.168.255.255)

- 10.0.0.0/8 (of 10.0.0.0 - 10.255.255.255)

- 172.16.0.0/11 (of 172.16.0.0 - 172.31.255.255)

### <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>U hebt een NDR (Non-Delivery Report) ontvangen bij het verzenden van e-mail naar een gebruiker in Office 365

Sommige leveringsproblemen zijn het gevolg van het feit dat het IP-adres van de afzender wordt geblokkeerd door Microsoft of omdat het gebruikersaccount is geïdentificeerd als geblokkeerde afzender vanwege eerdere spamactiviteiten. Als u van mening bent dat u de NDR ten onrechte hebt ontvangen, volgt u eerst alle instructies in het NDR-bericht om het probleem op te lossen.

Zie de lijst met foutcodes in rapporten zonder [bezorging e-mail in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)voor meer informatie over de fout die u hebt ontvangen.

 Als u bijvoorbeeld de volgende NDR ontvangt, geeft dit aan dat het verzendende IP-adres door Microsoft is geblokkeerd.

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

Als u verwijdering uit deze lijst wilt aanvragen, u [de lijst met contactpersonen gebruiken om uzelf uit de lijst met geblokkeerde afzenders van Office 365 te verwijderen.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)

### <a name="my-email-landed-in-the-recipients-junk-folder-in-eop"></a>Mijn e-mail is geland in de ongewenste map van de ontvanger in EOP

Als een bericht door EOP ten onrechte als spam is geïdentificeerd, u samenwerken met de ontvanger om dit fout-positieve bericht in te dienen bij het Microsoft Spam Analysis Team, dat het bericht evalueert en analyseert. Afhankelijk van de resultaten van de analyse kunnen de filterregels voor spaminhoud voor de hele service worden aangepast om het bericht door te laten gaan. U gebruikt e-mail om berichten aan Microsoft in te dienen die niet als spam moeten worden geclassificeerd. Houd daarbij de stappen in de volgende procedure.

### <a name="to-use-email-to-submit-false-positive-messages-to-the-microsoft-spam-analysis-team"></a>E-mail gebruiken om fout-positieve berichten in te dienen bij het Microsoft Spam Analysis Team

1. Sla het bericht dat u wilt verzenden op als niet-spam.

2. Maak een nieuw, leeg bericht en voeg het niet-spambericht eraan toe.

    U indien nodig meerdere niet-spamberichten toevoegen.

3. Kopieer en plak de onderwerpregel van het oorspronkelijke bericht in de nieuwe onderwerpregel van het bericht.

    > [!IMPORTANT]
    > Laat het lichaam van het nieuwe bericht leeg.

4. Stuur je nieuwe bericht naar [not_junk@office365.microsoft.com.](mailto:not_junk@office365.microsoft.com)

### <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>Verkeer vanaf mijn IP-adres wordt beperkt door EOP

Als u een NDR van EOP ontvangt die aangeeft dat uw IP-adres wordt beperkt door EOP, bijvoorbeeld:

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

U hebt de NDR ontvangen omdat verdachte activiteit is gedetecteerd vanaf het IP-adres en deze tijdelijk is beperkt terwijl deze verder wordt geëvalueerd. Als de verdenking wordt opgehelderd door middel van evaluatie, zal deze beperking binnenkort worden opgeheven.

### <a name="i-cant-receive-email-from-senders-in-office-365"></a>Ik kan geen e-mail ontvangen van afzenders in Office 365

 Om berichten van onze gebruikers te ontvangen, moet u ervoor zorgen dat uw netwerk verbindingen toestaat vanaf de IP-adressen die EOP in onze datacenters gebruikt. Zie [IP-adressen van Exchange Online Protection](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)voor meer informatie .

## <a name="best-practices-for-bulk-emailing-to-office-365-users"></a>Aanbevolen procedures voor bulke-mailen naar Office 365-gebruikers

Als u vaak bulke-mailcampagnes uitvoert naar Office 365-gebruikers en ervoor wilt zorgen dat uw e-mails op een veilige en tijdige manier binnenkomen, volgt u de tips in deze sectie.

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>Ervoor zorgen dat de naam Van: aangeeft wie het bericht verzendt

Het onderwerp moet een korte samenvatting van wat het bericht over gaat, en de bericht lichaam moet duidelijk en beknopt aangeven wat het aanbod, de dienst, of het product over gaat. Bijvoorbeeld:

Juiste:

> Van: marketing@shoppershandbag.com <br/> Onderwerp: Updated catalog for the Christmas season!

Onjuiste:

> Van: someone@outlook.com <br/> Onderwerp: Catalogi

Hoe makkelijker je het maakt voor mensen om te weten wie je bent en wat je doet, hoe minder moeite je zult hebben leveren door de meeste spamfilters.

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>Voeg altijd een afmeldoptie toe in campagne-e-mails

Marketing e-mails, met name nieuwsbrieven, moet altijd een manier van afmelden van toekomstige e-mails. Bijvoorbeeld:

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

Sommige afzenders bevatten deze optie door ontvangers te verplichten een e-mail te sturen naar een bepaalde alias met 'Afmelden' in het onderwerp. Dit is niet te verkiezen boven het bovenstaande voorbeeld met één klik. Als u ervoor kiest dat ontvangers een e-mail verzenden, moet u ervoor zorgen dat wanneer ze op de koppeling klikken, alle vereiste velden vooraf zijn ingevuld.

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>Gebruik de dubbele opt-in optie voor het op de markt brengen van e-mail of nieuwsbriefregistratie

Deze best practice wordt aanbevolen als uw bedrijf gebruikers nodig heeft of aanmoedigt om hun contactgegevens te registreren om toegang te krijgen tot uw product of services. Sommige bedrijven maken het een praktijk om automatisch aanmelden hun gebruikers voor marketing e-mails of e-nieuwsbrieven tijdens het registratieproces, maar dit wordt beschouwd als een twijfelachtige marketing praktijk in de wereld van e-mail filtering.

Tijdens het registratieproces, als het "Ja, stuur me uw nieuwsbrief" of "Ja, stuur me speciale aanbiedingen" checkbox is standaard ingeschakeld, gebruikers die niet goed opletten kan onbedoeld aanmelden voor marketing e-mail of nieuwsbrieven die ze niet willen ontvangen.

 In plaats daarvan raden we de dubbele opt-in-optie aan, wat betekent dat het selectievakje voor marketinge-mails of nieuwsbrieven standaard niet is aangevinkt. Bovendien, zodra het registratieformulier is ingediend, wordt een verificatie-e-mail verzonden naar de gebruiker met een URL die hen in staat stelt om hun beslissing om marketing e-mails te ontvangen te bevestigen.

 Dit helpt ervoor te zorgen dat alleen gebruikers die marketinge-mail willen ontvangen, worden aangemeld voor de e-mails, en vervolgens het verzendende bedrijf van twijfelachtige e-mailmarketingpraktijken wissen.

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>Ervoor zorgen dat de inhoud van e-mailberichten transparant en traceerbaar is

Net zo belangrijk als de manier waarop de e-mails worden verzonden is de inhoud die ze bevatten. Wanneer u e-mailinhoud maakt, gebruikt u de volgende aanbevolen procedures om ervoor te zorgen dat uw e-mails niet worden gemarkeerd door e-mailfilterservices:

- Wanneer in het e-mailbericht wordt gevraagd dat ontvangers de afzender aan het adresboek toevoegen, moet duidelijk worden vermeld dat een dergelijke actie geen garantie voor levering is.

- Omleidingen opgenomen in de hoofdtekst van het bericht moeten vergelijkbaar en consistent zijn, en niet meervoudig en gevarieerd. Een omleiding in deze context is alles wat wijst weg van het bericht, zoals links en documenten. Als je veel advertenties hebt of Links afmelden of De profielkoppelingen bijwerken, moeten ze allemaal naar hetzelfde domein verwijzen. Bijvoorbeeld:

  Juiste:

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  Onjuiste:

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- Vermijd inhoud met grote afbeeldingen en bijlagen of berichten die uitsluitend uit een afbeelding zijn samengesteld.

- Uw openbare privacy- of P3P-instellingen moeten duidelijk de aanwezigheid van trackingpixels (webbugs of beacons) vermelden.

### <a name="remove-incorrect-email-aliases-from-your-databases"></a>Onjuiste e-mailaliassen uit uw databases verwijderen

Elke e-mailalias in uw database die een bounce-back creëert, is niet nodig en brengt uw uitgaande e-mails in gevaar voor verdere controle door e-mailfilterservices. Zorg ervoor dat uw e-maildatabase up-to-date is.
