---
title: Problemen met e-mailberichten die worden verzonden naar Microsoft 365 oplossen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Dit artikel bevat informatie over het oplossen van problemen met het verzenden van e-mail naar Postvak IN in Microsoft 365 & procedures voor bulkmailing naar Microsoft 365 klanten.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c3017b0e7d0c583c9038f695f9f47010ff92c18a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204473"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a>Problemen met e-mailberichten die worden verzonden naar Microsoft 365 oplossen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)

Dit artikel bevat informatie over probleemoplossing voor afzenders die problemen ondervinden bij het verzenden van e-mail naar Postvak IN in Microsoft 365 en best practices voor bulkmailing naar klanten.

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>Beheert u de verzendende reputatie van uw IP en domein?

EOP-filtertechnologieën zijn ontworpen om antispambeveiliging te bieden voor Microsoft 365 en andere Microsoft-producten zoals Exchange Server. We maken ook gebruik van SPF, DKIM en DMARC; E-mailverificatietechnologieën die helpen bij het oplossen van het probleem van spoofing en phishing door te controleren of het domein dat de e-mail verstuurt, gemachtigd is om dit te doen. EOP-filtering wordt beïnvloed door een aantal factoren met betrekking tot het verzenden van IP, domein, verificatie, lijstnauwkeurigheid, klachttarieven, inhoud en meer. Een van deze factoren is een van de belangrijkste factoren bij het in de weg zitten van de reputatie van een afzender en hun mogelijkheid om e-mail te leveren, is het percentage ongewenste e-mail dat wordt geklaagd.

## <a name="are-you-sending-email-from-new-ip-addresses"></a>Verstuurt u e-mail van nieuwe IP-adressen?

IP-adressen die voorheen niet werden gebruikt om e-mail te verzenden, hebben meestal geen reputatie opgebouwd in onze systemen. Hierdoor hebben e-mailberichten van nieuwe IPs meer kans op bezorgingsproblemen. Zodra het IP een reputatie heeft opgebouwd voor het niet verzenden van spam, zal EOP meestal zorgen voor een betere e-mailbezorgingservaring.

Nieuwe IPs die worden toegevoegd voor domeinen die zijn geverifieerd onder bestaande SPF-records, hebben meestal het extra voordeel van het overnemen van een deel van de verzendende reputatie van het domein. Als uw domein een goede verzendende reputatie heeft, kunnen nieuwe IP's een snellere oprijtijd ervaren. Een nieuw IP-adres kan binnen een paar weken of eerder volledig worden uitgevoerd, afhankelijk van het volume, de nauwkeurigheid van de lijst en de tarieven voor ongewenste e-mail.

## <a name="confirm-that-your-dns-is-set-up-correctly"></a>Controleren of uw DNS correct is ingesteld

Voor instructies over het maken en onderhouden van DNS-records, inclusief de MX-record die vereist is voor het routeren van e-mail, moet u contact opnemen met uw DNS-hostingprovider.

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>Zorg ervoor dat u geen reclame maakt als een niet-routable IP

Het is mogelijk dat we geen e-mail accepteren van afzenders die een reverse-DNS-zoekactie mislukken. In sommige gevallen geven legitieme afzenders zich onjuist aan als een ip-adres dat niet via internet kan worden gebruikt bij het openen van een verbinding met EOP. IP-adressen die zijn gereserveerd voor privénetwerken (niet-routeerbaar) zijn onder andere:

- 192.168.0.0/16 (of 192.168.0.0 - 192.168.255.255)
- 10.0.0.0/8 (of 10.0.0.0 - 10.255.255.255)
- 172.16.0.0/11 (of 172.16.0.0 - 172.31.255.255)

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>U hebt een rapport over niet-bezorging (NDR) ontvangen bij het verzenden van e-mail naar een gebruiker in Office 365

Sommige bezorgingsproblemen zijn het gevolg van het blokkeren van het IP-adres van de afzender door Microsoft of omdat het gebruikersaccount is geïdentificeerd als geblokkeerde afzender vanwege eerdere spamactiviteiten. Als u denkt dat u de NDR fout hebt ontvangen, volgt u eerst de instructies in het NDR-bericht om het probleem op te lossen.

Zie de lijst met foutcodes in rapporten over [niet-bezorgde e-mail in](/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)Exchange Online.

 Als u bijvoorbeeld de volgende NDR ontvangt, geeft dit aan dat het verzendende IP-adres is geblokkeerd door Microsoft:

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

Als u verwijdering uit deze lijst wilt aanvragen, kunt u de portal voor het verwijderen van de lijst met geblokkeerde [afzenders gebruiken.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a>Mijn e-mail is geland in de map Ongewenste e-mail van de geadresseerde

Als een bericht onjuist is geïdentificeerd als spam door EOP, kunt u samen met de geadresseerde dit onwaar positieve bericht indienen bij het Microsoft Spam Analysis Team, dat het bericht evalueert en analyseert. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>Verkeer van mijn IP-adres wordt beperkt door EOP

Als u een NDR van EOP ontvangt die aangeeft dat uw IP-adres wordt beperkt door EOP, bijvoorbeeld:

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

U hebt de NDR ontvangen omdat verdachte activiteit is gedetecteerd vanaf het IP-adres en tijdelijk is beperkt terwijl deze verder wordt geëvalueerd. Als de verdenking wordt geweend door evaluatie, wordt deze beperking binnenkort opgeheven.

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a>Ik kan geen e-mail ontvangen van afzenders in Microsoft 365

 Als u berichten van onze gebruikers wilt ontvangen, moet u ervoor zorgen dat uw netwerk verbindingen toestaat van de IP-adressen die door EOP in onze datacenters worden gebruikt. Zie Exchange Online Protection [IP-adressen voor meer informatie.](../../enterprise/urls-and-ip-address-ranges.md)

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a>Best practices voor bulksgewijs e-mailen naar Microsoft 365 gebruikers

Als u vaak bulksgewijs e-mailcampagnes voert Microsoft 365 gebruikers en ervoor wilt zorgen dat uw e-mailberichten op een veilige en tijdige manier binnenkomen, volgt u de tips in deze sectie.

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>Controleer of de van-naam weerspiegelt wie het bericht verstuurt

Het onderwerp moet een korte samenvatting zijn van waar het bericht over gaat, en de berichtin body moet duidelijk en beknopt aangeven waar het aanbod, de service of het product over gaat. Bijvoorbeeld:

Juist:

> Van: marketing@shoppershandbag.com <br> Onderwerp: Bijgewerkte catalogus voor het kerstseizoen!

Onjuist:

> Van: someone@outlook.com <br> Onderwerp: Catalogi

Hoe gemakkelijker u het voor mensen maakt om te weten wie u bent en wat u doet, hoe minder problemen u hebt met het leveren van spamfilters.

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>Altijd een optie voor afmelden opnemen in campagne-e-mailberichten

Marketing-e-mailberichten, met name nieuwsbrieven, moeten altijd een manier bevatten om zich af te schrijven van toekomstige e-mailberichten. Bijvoorbeeld:

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

Sommige afzenders bevatten deze optie door geadresseerden te verplichten een e-mail te verzenden naar een bepaalde alias met 'Afmelden' in het onderwerp. Dit is niet de voorkeur boven het bovenstaande voorbeeld met één klik. Als u ervoor kiest om geadresseerden te verplichten een e-mailbericht te verzenden, moet u ervoor zorgen dat wanneer ze op de koppeling klikken, alle vereiste velden vooraf zijn ingevuld.

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>Gebruik de optie dubbele aanmelding voor marketing-e-mail of nieuwsbriefregistratie

Deze aanbevolen praktijk wordt aanbevolen als uw bedrijf gebruikers vereist of aanmoedigt om hun contactgegevens te registreren om toegang te krijgen tot uw product of services. Sommige bedrijven maken het een gewoonte om hun gebruikers automatisch te registreren voor marketing-e-mailberichten of e-nieuwsbrieven tijdens het registratieproces, maar dit wordt beschouwd als een twijfelachtige marketingpraktijk in de wereld van het filteren van e-mail.

Als tijdens het registratieproces het selectievakje 'Ja, stuur mij uw nieuwsbrief' of 'Ja, stuur mij speciale aanbiedingen' standaard is ingeschakeld, kunnen gebruikers die niet goed opletten zich onbedoeld registreren voor marketing-e-mail of nieuwsbrieven die ze niet willen ontvangen.

 In plaats daarvan raden we de optie dubbele opt-in aan, wat betekent dat het selectievakje voor marketing-e-mailberichten of nieuwsbrieven standaard niet is ingeschakeld. Wanneer het registratieformulier is ingediend, wordt er bovendien een verificatie-e-mail naar de gebruiker verzonden met een URL waarmee ze kunnen bevestigen dat ze besluiten marketing-e-mailberichten te ontvangen.

 Dit helpt ervoor te zorgen dat alleen gebruikers die marketing-e-mail willen ontvangen, zijn aangemeld voor de e-mailberichten, zodat het verzendende bedrijf vervolgens wordt vrij gesteld van twijfelachtige e-mailmarketingpraktijken.

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>Controleer of de inhoud van e-mailberichten transparant en traceerbaar is

Net zo belangrijk als de manier waarop de e-mailberichten worden verzonden, is de inhoud die ze bevatten. Gebruik bij het maken van e-mailinhoud de volgende best practices om ervoor te zorgen dat uw e-mailberichten niet worden gemarkeerd door e-mailfilterservices:

- Wanneer in het e-mailbericht wordt gevraagd of geadresseerden de afzender aan het adresboek moeten toevoegen, moet duidelijk worden aangegeven dat een dergelijke actie geen garantie voor bezorging is.

- Omleidingen die in de tekst van het bericht zijn opgenomen, moeten vergelijkbaar en consistent zijn, en niet veelvoudig en gevarieerd. Een omleiding in deze context is alles wat weg wijst van het bericht, zoals koppelingen en documenten. Als u veel reclame- of afmeldkoppelingen hebt of De profielkoppelingen bijwerken, moeten ze allemaal naar hetzelfde domein wijzen. Bijvoorbeeld:

  Correct (alle domeinen zijn hetzelfde):

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  Onjuist (alle domeinen zijn verschillend):

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- Vermijd inhoud met grote afbeeldingen en bijlagen of berichten die uitsluitend uit een afbeelding zijn samengesteld.

- In uw openbare privacy- of P3P-instellingen moet de aanwezigheid van trackingpixels (web bugs of beacons) duidelijk worden aangegeven.

### <a name="remove-incorrect-email-aliases-from-your-databases"></a>Onjuiste e-mailalias verwijderen uit uw databases

Elke e-mailalias in uw database die een bounce-back maakt, is overbodig en brengt uw uitgaande e-mailberichten in gevaar voor nader onderzoek door e-mailfilterservices. Zorg ervoor dat uw e-maildatabase up-to-date is.