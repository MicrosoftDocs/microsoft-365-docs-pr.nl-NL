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
description: Dit artikel bevat informatie over het oplossen van problemen met het verzenden van e-mail naar Postvak IN in Microsoft 365 & voor het bulksgewijs verzenden van e-mail naar klanten van Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1e4a91f70b59debc770a5811638bd64a1eef36dd
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286379"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a>Problemen met e-mailberichten die worden verzonden naar Microsoft 365 oplossen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)

Dit artikel bevat informatie over het oplossen van problemen met afzenders die problemen ondervinden bij het verzenden van e-mail naar Postvak IN in Microsoft 365 en met de beste procedures voor bulkmailing naar klanten.

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>Beheert u uw IP- en domeinreputatie?

EOP-filtertechnologieën zijn ontworpen om bescherming tegen spam te bieden voor Microsoft 365 en andere Microsoft-producten, zoals Exchange Server. We maken ook gebruik van SPF, DKIM en DMARC; Technologieën voor e-mailverificatie die helpen het probleem van spoofing en phishing op te lossen door te controleren of het domein dat het e-mailbericht verstuurt, gemachtigd is om dit te doen. EOP-filtering wordt beïnvloed door een aantal factoren die te maken hebben met het verzenden van IP, domein, verificatie, lijstnauwkeurigheid, klachttarieven, inhoud en meer. Een van deze factoren is een van de belangrijkste factoren voor het verbeteren van de reputatie van een afzender en de mogelijkheid om e-mail te leveren is de klacht over ongewenste e-mail.

## <a name="are-you-sending-email-from-new-ip-addresses"></a>Verstuurt u e-mail vanaf nieuwe IP-adressen?

IP-adressen die voorheen niet werden gebruikt voor het verzenden van e-mail, hebben meestal geen goede reputatie die in onze systemen is opgebouwd. Hierdoor is de kans groter dat e-mails van nieuwe IP's problemen met de bezorging ervaren. Nadat het IP-adres een goede reputatie heeft gekregen voor het niet verzenden van spam, zal EOP meestal zorgen voor een betere ervaring met de bezorging van e-mail.

Nieuwe IPs die worden toegevoegd voor domeinen die worden geverifieerd onder bestaande SPF-records, hebben meestal het extra voordeel van het overnemen van een deel van de verzendende reputatie van het domein. Als uw domein een goede reputatie heeft voor het verzenden van nieuwe IP's, kan het sneller verlopen. Een nieuw IP-adres kan naar verwachting binnen enkele weken of sneller volledig worden ge ramped, afhankelijk van het volume, de nauwkeurigheid van de lijst en de tarieven van ongewenste e-mail.

## <a name="confirm-that-your-dns-is-set-up-correctly"></a>Controleer of uw DNS correct is ingesteld

Neem contact op met uw DNS-hostingprovider voor instructies over het maken en onderhouden van DNS-records, inclusief de MX-record die is vereist voor het routeren van e-mail.

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>Zorg ervoor dat u uzelf niet als een niet-routeerbaar IP-adres aanseert

Het is mogelijk dat er geen e-mail wordt geaccepteerd van afzenders die een reverse-DNS-zoekactie mislukt. In sommige gevallen worden legitieme afzenders onjuist aangekondigd als een niet-internet routeerbaar IP wanneer ze proberen een verbinding met EOP te openen. Ip-adressen die zijn gereserveerd voor privénetwerken (niet-routeerbaar), zijn:

- 192.168.0.0/16 (of 192.168.0.0 - 192.168.255.255)
- 10.0.0.0/8 (of 10.0.0.0 - 10.255.255.255)
- 172.16.0.0/11 (of 172.16.0.0 - 172.31.255.255)

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>U hebt een rapport over niet-bezorging (NDR) ontvangen bij het verzenden van e-mail naar een gebruiker in Office 365

Sommige bezorgingsproblemen worden veroorzaakt doordat het IP-adres van de afzender wordt geblokkeerd door Microsoft of omdat het gebruikersaccount is geïdentificeerd als geblokkeerde afzender vanwege eerdere spamactiviteit. Als u denkt dat u de NDR ten fout hebt ontvangen, volgt u eerst de instructies in het NDR-bericht om het probleem op te lossen.

Zie de lijst met foutcodes in rapporten over niet-bezorging van [e-mail in Exchange Online voor meer](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)informatie over de fout die u hebt ontvangen.

 Als u bijvoorbeeld de volgende NDR ontvangt, betekent dit dat het verzendende IP-adres is geblokkeerd door Microsoft:

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

Als u een verwijdering uit deze lijst wilt aanvragen, kunt u de portal Delist gebruiken om uzelf uit de [lijst met geblokkeerde afzenders te verwijderen.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a>Mijn e-mail komt terecht in de map Ongewenste e-mail van de geadresseerde

Als een bericht door EOP ten onrechte is geïdentificeerd als spam, kunt u samen met de geadresseerde dit fout-positieve bericht verzenden naar het Microsoft Spam Analysis Team, dat het bericht evalueert en analyseert. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>Verkeer van mijn IP-adres wordt beperkt door EOP

Als u een NDR van EOP ontvangt om aan te geven dat uw IP-adres wordt beperkt door EOP, bijvoorbeeld:

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

U hebt de NDR ontvangen omdat er verdachte activiteiten zijn gedetecteerd vanaf het IP-adres en het adres tijdelijk is beperkt terwijl het verder wordt geëvalueerd. Als de verdenking via evaluatie wordt opgeheven, wordt deze beperking binnenkort opgeheven.

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a>Ik kan geen e-mail ontvangen van afzenders in Microsoft 365

 Als u berichten van onze gebruikers wilt ontvangen, moet u ervoor zorgen dat uw netwerk verbindingen toestaat van de IP-adressen die door EOP in onze datacenters worden gebruikt. Zie IP-adressen van [Exchange Online Protection voor meer informatie.](../../enterprise/urls-and-ip-address-ranges.md)

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a>Best practices voor bulksgewijs e-mailen naar Gebruikers van Microsoft 365

Als u vaak bulkmailcampagnes voert voor Microsoft 365-gebruikers en er zeker van wilt zijn dat uw e-mailberichten op een veilige en tijdige manier worden ontvangen, volgt u de tips in dit gedeelte.

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>Zorg ervoor dat de Van-naam weerspiegelt wie het bericht verstuurt

Het onderwerp moet een kort overzicht zijn van waar het bericht over gaat en de bericht zelf moet duidelijk en bondig aangeven waar het aanbod, de service of het product over gaat. Bijvoorbeeld:

Juist:

> Van: marketing@shoppershandbag.com <br> Onderwerp: Bijgewerkte catalogus voor de kerstperiode!

Onjuist:

> Van: someone@outlook.com <br> Onderwerp: Catalogi

Hoe gemakkelijker u het mensen maakt om te weten wie u bent en wat u doet, hoe minder problemen u krijgt door de meeste spamfilters.

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>Altijd een optie voor afmelden opnemen in e-mails in campagne

Marketing-e-mails, met name nieuwsbrieven, moeten altijd een manier bevatten om u af te schrijven van toekomstige e-mailberichten. Bijvoorbeeld:

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

Sommige afzenders nemen deze optie op door te vereisen dat geadresseerden een e-mailbericht verzenden naar een bepaalde alias met 'Afmelden' in het onderwerp. Dit heeft niet de voorkeur boven het voorbeeld met één klik hierboven. Als u wilt dat geadresseerden een e-mailbericht moeten verzenden, controleert u of alle vereiste velden al zijn ingevuld wanneer ze op de koppeling klikken.

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>De optie voor dubbele aanmelding gebruiken voor registratie van marketing-e-mail of nieuwsbrief

Deze aanbevolen praktijk wordt aanbevolen als uw bedrijf vereist of stimuleert gebruikers hun contactgegevens te registreren om toegang te krijgen tot uw product of services. Sommige bedrijven maken het een gewoonte om hun gebruikers automatisch te registreren voor marketing-e-mails of e-nieuwsbrieven tijdens het registratieproces, maar dit wordt gezien als een twijfelachtige marketingprocedure in de wereld van het filteren van e-mail.

Als tijdens het registratieproces het selectievakje 'Ja, graag uw nieuwsbrief verzenden' of 'Ja, graag me speciale aanbiedingen sturen' is ingeschakeld, is het mogelijk dat gebruikers die niet zo goed op de hoogte zijn, zich onbedoeld registreren voor marketing-e-mail of nieuwsbrieven die ze niet willen ontvangen.

 U wordt aangeraden de optie voor dubbele opt-in te gebruiken, wat betekent dat het selectievakje voor marketinge-mailberichten of nieuwsbrieven standaard niet is ingeschakeld. Wanneer het registratieformulier is ingediend, wordt er bovendien een verificatie-e-mail naar de gebruiker verzonden met een URL waarmee hij of zij kan bevestigen dat hij of zij marketinge-mailberichten wil ontvangen.

 Dit zorgt ervoor dat alleen gebruikers die marketinge-mail willen ontvangen, zijn aangemeld voor de e-mailberichten, waardoor het verzendende bedrijf wordt leeg gemaakt van twijfelachtige marketingpraktijken voor e-mail.

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>Controleer of de inhoud van e-mailberichten transparant en traceerbaar is

Net zo belangrijk als de manier waarop de e-mailberichten worden verzonden, is de inhoud die ze bevatten. Wanneer u e-mailinhoud maakt, gebruikt u de volgende best practices om ervoor te zorgen dat uw e-mailberichten niet worden gemarkeerd door e-mailfilterservices:

- Wanneer geadresseerden in het e-mailbericht worden gevraagd de afzender aan het adresboek toe te voegen, moet duidelijk worden aangegeven dat een dergelijke actie geen garantie is voor bezorging.

- Omleidingen in de bericht zelf moeten gelijk en consistent zijn en mogen niet veelvoud en gevarieerd zijn. Een omleiding in deze context is alles wat van het bericht af wijst, zoals koppelingen en documenten. Als u veel advertenties ziet of u zich afmeldt of de profielkoppelingen bijwerkt, moeten ze allemaal naar hetzelfde domein wijzen. Bijvoorbeeld:

  Juist (alle domeinen zijn hetzelfde):

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  Onjuist (alle domeinen verschillen):

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- Vermijd inhoud met grote afbeeldingen en bijlagen of berichten die uitsluitend uit een afbeelding bestaan.

- Uw openbare privacy- of P3P-instellingen moeten duidelijk de aanwezigheid van tracerings pixels (web bugs ofbakens) melden.

### <a name="remove-incorrect-email-aliases-from-your-databases"></a>Onjuiste e-mailaliassen verwijderen uit uw databases

Elke e-mailalias in uw database die een niet-uitgaande e-mail maakt, is niet nodig en hiermee worden uw uitgaande e-mailberichten in gevaar gebracht zodat u deze nader kunt onderzoeken door e-mailfilterservices. Controleer of uw e-maildatabase is bijgewerkt.
