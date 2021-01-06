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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Dit artikel bevat informatie over het oplossen van problemen met het verzenden van e-mail naar postvakken in Microsoft 365 & best practices voor bulk mailing naar klanten met Microsoft 365.
ms.openlocfilehash: 3504d7518073826f3979c3c837c58d4406886b41
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760480"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a>Problemen met e-mailberichten die worden verzonden naar Microsoft 365 oplossen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Dit artikel bevat informatie over het oplossen van problemen met afzenders die problemen ondervinden wanneer u e-mail probeert te verzenden naar postvakken in Microsoft 365 en best practices voor bulk mailing naar klanten.

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>Beheert u de reputatie van uw IP en domein?

EOP filter technologieën zijn ontworpen om antispam beveiliging voor Microsoft 365 en andere Microsoft-producten zoals Exchange server te bieden. We kunnen ook gebruikmaken van SPF, DKIM en DMARC; verificatietechnologieën voor e-mail die u helpen bij het oplossen van problemen met spoofing en phishing verifieert het domein dat het e-mailbericht verzendt, is geautoriseerd. EOP filteren wordt beïnvloed door een aantal factoren die verband houden met het verzenden van IP, domein, authenticatie, nauwkeurigheid van klachten, klachten tarieven, inhoud en meer. Een van de belangrijkste factoren in het rijden van de reputatie van een afzender en de mogelijkheid om e-mail te bezorgen is hun klachten tarief voor ongewenste e-mail.

## <a name="are-you-sending-email-from-new-ip-addresses"></a>Verzendt u e-mail van nieuwe IP-adressen?

IP-adressen die u niet eerder hebt gebruikt voor het verzenden van e-mail, hebben doorgaans geen reputatie opgebouwd in onze systemen. Daarom hebben e-mailberichten van nieuwe IPs waarschijnlijker problemen met de bezorging. Wanneer het IP-adres voor het versturen van spam niet via spam is opgebouwd, kan EOP u meestal een betere e-mail bezorgings ervaring bieden.

Nieuwe IP-adressen die worden toegevoegd voor domeinen die zijn geverifieerd onder bestaande SPF-records, hebben meestal het extra voordeel van het overnemen van een deel van het domein. Als uw domein een goede vernieuwings ervaring heeft, kunnen de nieuwe IPs sneller worden uitgevoerd. Een nieuw IP-adres kan naar verwachting binnen een paar weken of sneller worden afgehandeld, afhankelijk van volume, nauwkeurigheid van de lijst en een spam tarief voor ongewenste e-mail.

## <a name="confirm-that-your-dns-is-set-up-correctly"></a>Controleren of uw DNS juist is ingesteld

Als u wilt weten hoe u DNS-records maakt en onderhoudt, waaronder de MX-record die nodig is voor e-mail routering, moet u contact opnemen met uw DNS-hosting provider.

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>Ervoor zorgen dat u zichzelf niet adverteert als een niet-routeerbaar IP-adres

We accepteren mogelijk geen e-mailberichten van afzenders die een opzoek service voor omkering van de DNS hebben. In sommige gevallen adverteert legitiem afzenders zichzelf onjuist als een niet-Internet routeerbaar IP-adres bij het openen van een verbinding met EOP. IP-adressen die zijn gereserveerd voor privé-netwerken (niet-routeerbaar), zijn:

- 192.168.0.0/16 (of 192.168.0.0-192.168.255.255)
- 10.0.0.0/8 (of 10.0.0.0-10.255.255.255)
- 172.16.0.0/11 (of 172.16.0.0-172.31.255.255)

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>U hebt een NDR van een niet-uitgevoerde bezorging van een e-mailbericht ontvangen voor het verzenden van e-mail naar een gebruiker in Office 365

Sommige bezorgings problemen zijn het gevolg van het IP-adres van de afzender dat door Microsoft wordt geblokkeerd of omdat het gebruikersaccount wordt herkend als niet-geblokkeerde afzender vanwege eerdere spam activiteiten. Als u van mening bent dat u de NDR een foutmelding hebt ontvangen, volgt u eerst de instructies in het NDR-bericht om het probleem op te lossen.

Als u meer wilt weten over de fout die u hebt ontvangen, raadpleegt u de lijst met foutcodes in [rapporten over niet-uitgevoerde bezorging van e-mail in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).

 Als u bijvoorbeeld de volgende NDR ontvangt, wordt aangegeven dat het verzendende IP-adres door Microsoft is geblokkeerd:

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

Als u de lijst wilt verwijderen, kunt u deze [uit de lijst met geblokkeerde afzenders verwijderen via de portal delijstte](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a>Mijn e-mailbericht in de map Ongewenste E-mail van de geadresseerde

Als een bericht onjuist is geïdentificeerd als spam via EOP, kunt u met de ontvanger werken om dit foutbericht te verzenden naar het Microsoft spam Analysis-Team, dat het bericht evalueert en analyseert. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>Verkeer van mijn IP-adres wordt vertraagd door EOP

Als u een NDR ontvangt van EOP, wordt aangegeven dat uw IP-adres wordt vertraagd door EOP, bijvoorbeeld:

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

U ontving de NDR omdat verdachte activiteiten zijn gedetecteerd van het IP-adres, en het tijdelijk niet is beperkt terwijl de actie wordt voortgezet. Als het vermoeden is opgeheven via evaluatie, wordt deze beperking kort weergegeven.

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a>Ik kan geen e-mail ontvangen van afzenders in Microsoft 365

 Als u berichten van onze gebruikers wilt ontvangen, moet u ervoor zorgen dat uw netwerkverbindingen toestaat van de IP-adressen die EOP in onze datacenters gebruikt. Zie [IP-adressen voor Exchange Online Protection](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)voor meer informatie.

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a>Best practices voor bulksgewijs e-mailen naar Microsoft 365-gebruikers

Als u vaak grote hoeveelheden e-mail campagnes doet voor Microsoft 365-gebruikers en u er zeker van wilt zijn dat uw e-mailberichten op een veilige en tijd uitkomen, volgt u de tips in deze sectie.

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>Ervoor zorgen dat de van-naam weerspiegelt de persoon die het bericht verzendt

Het onderwerp moet een kort overzicht zijn van de inhoud van het bericht en de hoofdtekst van het bericht moet duidelijk en bondig aangeven wat de aanbieding, de service of het product benadert. Bijvoorbeeld:

Juist:

> Van: marketing@shoppershandbag.com <br> Onderwerp: heeft een catalogus voor een kerst seizoen bijgewerkt.

Onjuist:

> Van: someone@outlook.com <br> Onderwerp: catalogi

Het eenvoudiger maken om te weten wie u bent en wat u aan het doen bent, hoe minder problemen u te bieden via de meeste spamfilters.

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>De optie voor het afschrijven van een abonnement altijd opnemen in e-mail van een campagne

Marketing e-mailberichten, met name nieuwsbrieven, moeten altijd een e-mailbericht over het afmelden bij toekomstige e-mailberichten bevatten. Bijvoorbeeld:

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

Sommige afzenders bevatten deze optie, omdat geadresseerden een e-mailbericht naar een bepaalde alias moeten verzenden met ' Afmelden ' in het onderwerp. Dit is niet de voorkeur voor één klik hierboven. Als u wilt dat geadresseerden een e-mailbericht moeten verzenden, moet u ervoor zorgen dat de vereiste velden vooraf zijn ingevuld wanneer ze op de koppeling klikken.

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>Gebruik de optie voor dubbele opt-in voor marketing-e-mail of nieuwsbrief registratie

Deze beste gewoonte is raadzaam als uw bedrijf gebruikers informatie wil registreren of aan te moedigen om toegang te krijgen tot uw product of services. Met sommige bedrijven wordt het automatisch om gebruikers voor marketing-e-mailberichten of e-mail nieuwsbrieven automatisch aan te melden voor het registreren van een e-mailbericht, maar dit wordt beschouwd als een dubieuze marketing procedure in de wereld van e-mail filtering.

Als u tijdens het registratieproces het selectievakje ' Ja, stuur mij uw nieuwsbrief verzenden ' of ' Ja, kies mij een speciale aanbieding ' is ingeschakeld, kunnen gebruikers die niet kunnen worden ingeschreven, registreren voor marketing-e-mailberichten of nieuwsbrieven die ze niet willen ontvangen.

 We raden u aan in plaats daarvan de optie voor dubbele opt-in, wat betekent dat het selectievakje voor marketing-e-mails of nieuwsbrief nieuwsbrieven standaard niet wordt ingeschakeld. Wanneer het registratieformulier is ingediend, wordt er een verificatie-e-mailbericht naar de gebruiker verzonden met een URL, zodat ze hun beslissing kunnen bevestigen voor het ontvangen van marketing-e-mailberichten.

 Dit helpt ervoor te zorgen dat alleen gebruikers van marketing via e-mail een e-mailbericht ontvangen voor de e-mailberichten, en dan de verstuurde vennootschap van een willekeurige e-mail marketing procedure.

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>Zorg ervoor dat de inhoud van het e-mailbericht transparant en vervolgen is

Net zo belangrijk als de manier waarop e-mailberichten worden verzonden, is de inhoud die deze bevat. Wanneer u e-mail inhoud maakt, kunt u de volgende aanbevolen procedures gebruiken om ervoor te zorgen dat uw e-mailberichten niet worden gemarkeerd met een filterservice voor e-mail:

- Als het e-mailbericht verzoekt dat geadresseerden de afzender toevoegen aan het adresboek, moet u duidelijk aangeven dat deze actie geen garantie biedt.

- Omleidingen die in de hoofdtekst van het bericht zijn opgenomen, moeten vergelijkbaar en consistent zijn, en niet meerdere en geen variabele. Een omleiding in deze context is iets dat verwijst naar het bericht, bijvoorbeeld koppelingen en documenten. Als u veel reclame of de koppeling naar het profiel wilt bijwerken of de profielkoppelingen wilt bijwerken, moeten deze allemaal naar hetzelfde domein verwijzen. Bijvoorbeeld:

  Correct (alle domeinen zijn hetzelfde):

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  Onjuist (alle domeinen verschillen):

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- Vermijd inhoud met grote afbeeldingen en bijlagen, of berichten die uitsluitend uit een afbeelding bestaan.

- De aanwezigheid van uw openbare privacy-of P3P-instellingen moet duidelijk duidelijk zijn voor het bijhouden van pixels (web bugs of beacons).

### <a name="remove-incorrect-email-aliases-from-your-databases"></a>Onjuiste e-mail aliassen verwijderen uit uw databases

Elke e-mail alias in de database die een stuiterende stuiter maakt, is overbodig en zet uw uitgaande e-mailberichten op het risico voor verder onderzoek via e-mail filter Services. Zorg ervoor dat uw e-mail database up-to-date is.
