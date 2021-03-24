---
title: E-mailverificatie in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: Beheerders kunnen meer informatie krijgen over hoe EOP e-mailverificatie (SPF, DKIM en DMARC) gebruikt om adresvervalsing, phishing en spam te helpen voorkomen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 633494717ad7cf68319a2332f435fd8b56fc8aeb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059873"
---
# <a name="email-authentication-in-eop"></a>E-mailverificatie in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


E-mailverificatie (ook wel e-mailvalidatie genoemd) is een groep standaarden die probeert om spoofing (e-mailberichten van vervalste afzenders) te stoppen. In alle Microsoft 365-organisaties maakt EOP gebruik van deze standaarden om binnenkomende e-mail te verifiëren:

- [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

- [DKIM](use-dkim-to-validate-outbound-email.md)

- [DMARC](use-dmarc-to-validate-email.md)

E-mailverificatie verifieert dat e-mailberichten van een afzender (bijvoorbeeld laura@contoso.com) legitiem zijn en afkomstig zijn van verwachte bronnen voor dat e-maildomein (bijvoorbeeld contoso.com).

In de rest van dit artikel wordt uitgelegd hoe deze technologieën werken en hoe EOP ze gebruikt om binnenkomende e-mail te controleren.

## <a name="use-email-authentication-to-help-prevent-spoofing"></a>E-mailverificatie gebruiken om spoofing te voorkomen

DMARC voorkomt spoofing door het **Van** adres in berichten te onderzoeken. Het **Van** adres is het e-mailadres van de afzender dat gebruikers zien in de e-mailclient. E-mail organisaties kunnen er ook voor zorgen dat het e-mail domein is doorgegeven aan SPF of DKIM. Met andere woorden, het domein is geverifieerd en daarom is het e-mailadres van de afzender niet vervalst.

Echter, DNS-records voor SPF, DKIM en DMARC (gezamenlijk bekend als e-mail verificatiebeleid) zijn optioneel. Domeinen met een sterk e-mail verificatiebeleid, zoals microsoft.com en skype.com, worden beschermd tegen spoofing. Maar domeinen met een zwakkere e-mail verificatie, of helemaal geen beleid, zijn hoofddoelen om te worden vervalst.

Slechts 9% van de domeinen van bedrijven in de Fortune 500 hanteerde in maart 2018 een sterk e-mailverificatiebeleid. De resterende 91% van de bedrijven kan door een kwaadwillende worden gespooft. Tenzij er een ander filtermechanisme voor e-mail aanwezig is, kan e-mail van vervalste afzenders in deze domeinen aan gebruikers worden bezorgd.

![DMARC-beleid van Fortune 500-bedrijven](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

Het aantal kleine en middelgrote bedrijven die een sterk e-mail verificatiebeleid publiceren, is kleiner. En het nummer is nog kleiner voor e-mail domeinen buiten Noord-Amerika en West-Europa.

Het ontbreken van een sterk beleid voor e-mailverificatie is een groot probleem. Hoewel organisaties niet kunnen zien hoe e-mailverificatie werkt, zijn hackers volledig op de hoogte en kunnen ze hiervan profiteren van. Vanwege phishing en de beperkte acceptatie van een sterk e-mailverificatiebeleid, gebruikt Microsoft *impliciete e-mailverificatie* om inkomende e-mail te controleren.

Impliciete e-mailverificatie is gebaseerd een uitbreiding van het reguliere e-mailbeleid. Deze extensies bevatten de reputatie van de afzender, de geschiedenis van de afzender, de geschiedenis van de ontvanger, gedragsanalyse en andere geavanceerde technieken. Als er geen andere signalen van deze extensies worden verzonden, worden berichten die zijn verzonden vanuit domeinen die geen beleid voor e-mail verificatie gebruiken, gemarkeerd als spoof.

Zie [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209) om de algemene aankondiging van Microsoft te lezen.

## <a name="composite-authentication"></a>Samengestelde verificatie

Als een domein geen traditionele SPF-, DKIM-en DMARC-records heeft, communiceren deze recordcontroles niet voldoende informatie over de status van de verificatie. Microsoft heeft daarom een algoritme ontwikkeld voor impliciete e-mail verificatie. Dit algoritme combineert meerdere signalen tot één waarde met de naam _Samengestelde verificatie_, of `compauth` afgekort. De `compauth`-waarde wordt in de koptekst **Verificatie-resultaten** in de berichtkoppen gestempeld.

```text
Authentication-Results:
   compauth=<fail | pass | softpass | none> reason=<yyy>
```

Deze waarden worden uitgelegd in de [berichtkop Verificatie-resultaten](anti-spam-message-headers.md#authentication-results-message-header).

Door de berichtkoppen te bekijken, kunnen beheerders of zelfs eindgebruikers nagaan hoe in Microsoft 365 is vastgesteld dat de afzender is vervalst.

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>Waarom e-mailverificatie niet altijd voldoende is om adresvervalsing te stoppen

Alleen vertrouwen op records voor e-mailverificatie om te bepalen of een inkomend bericht vervalst is, heeft de volgende beperkingen:

- Het verzendende domein heeft mogelijk niet de vereiste DNS-records of de records zijn onjuist geconfigureerd.

- Het brondomein heeft correct geconfigureerde DNS-records, maar dat domein komt niet overeen met het domein in het Van-adres. SPF en DKIM vereisen niet dat het domein wordt gebruikt in het Van-adres. Hackers of legitieme services kunnen een domein registreren, SPF en DKIM configureren voor het domein en een geheel ander domein gebruiken in het Van-adres. Berichten van afzenders in dit domein worden doorgegeven aan SPF en DKIM.

Samengestelde verificatie kan deze beperkingen verhelpen door berichten door te geven die anders niet door de e-mailverificatie zouden komen.

Voor de eenvoud zijn de volgende voorbeelden gericht op resultaten van e-mailverificatie. Andere intelligentiefactoren in de back-end kunnen berichten die e-mailverificatie doorstaan identificeren als vervalst, of berichten die e-mailverificatie niet doorstaan identificeren als legitiem.

Het domein fabrikam.com heeft bijvoorbeeld geen SPF-, DKIM- of DMARC-records. Berichten van afzenders van het fabrikam.com-domein kunnen samengestelde verificatie niet doorstaan (noteer de `compauth`waarde en reden):

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

Als fabrikam.com een SPF-record zonder DKIM configureert, kan het bericht samengestelde verificatie doorgeven. Het domein waaraan SPF-controles zijn doorgegeven, wordt uitgelijnd met het domein in het Van-adres:

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

Als fabrikam.com een DKIM-record zonder SPF-record configureert, kan het bericht samengestelde verificatie doorgeven. Het domein in het DKIM-handtekening wordt uitgelijnd met het domein in het Van-adres:

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

Als het domein in SPF of de DKIM-handtekening niet overeenkomt met het domein in het Van-adres, kan het bericht door samengestelde verificatie worden tegengehouden:

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a>Oplossingen voor legitieme afzenders die niet-geverifieerde e-mail verzenden

In Microsoft 365 wordt bijgehouden wie niet-geverifieerde e-mail naar uw organisatie verzendt. Als de service denkt dat de afzender niet legitiem is, worden berichten van deze afzender gemarkeerd als een samengestelde verificatiefout. U kunt dit voorkomen door de aanbevelingen in deze sectie te gebruiken.

### <a name="configure-email-authentication-for-domains-you-own"></a>Configureer e-mailverificatie voor uw domeinen

U kunt deze methode gebruiken om spoofing binnen organisaties en spoofing tussen domeinen op te lossen in gevallen waarbij u eigenaar bent van of interactie heeft met meerdere tenants. Het helpt ook adresvervalsing tussen domeinen op te lossen wanneer u naar andere klanten binnen Microsoft 365 verzendt of naar derden die worden gehost door andere providers.

- [SPF-records configureren](set-up-spf-in-office-365-to-help-prevent-spoofing.md) voor uw domeinen.

- [DKIM-records configureren](use-dkim-to-validate-outbound-email.md) voor uw primaire domeinen.

- [U kunt overwegen om DMARC-records in te stellen](use-dmarc-to-validate-email.md) voor uw domein om te bepalen wie uw legitieme afzenders zijn.

Microsoft biedt geen gedetailleerde implementatierichtlijnen voor SPF-, DKIM-en DMARC-records. Er is echter veel informatie online beschikbaar. Er zijn ook andere bedrijven die uw organisatie kunnen helpen bij het opzetten van e-mailverificatierecords.

#### <a name="you-dont-know-all-sources-for-your-email"></a>U kent niet alle bronnen voor uw e-mailberichten

Veel domeinen publiceren geen SPF-records omdat ze niet alle e-mailbronnen kennen voor berichten in hun domein. Begin met het publiceren van een SPF-record met alle e-mailbronnen die u kent (vooral waar uw zakelijke verkeer zich bevindt) en publiceer het neutrale SPF-beleid `?all`. Bijvoorbeeld:

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

Dit voorbeeld betekent dat e-mail van uw bedrijfsinfrastructuur e-mailverificatie doorstaat, maar e-mail van onbekende bronnen wordt gemarkeerd als neutraal.

Microsoft 365 behandelt inkomende e-mail van uw bedrijfsinfrastructuur als geverifieerd. E-mail van niet-geïdentificeerde bronnen wordt mogelijk nog steeds gemarkeerd als spoof als de impliciete verificatie mislukt. Dit is echter nog steeds een verbetering in plaats van dat alle e-mail door Microsoft 365 als spoof wordt gemarkeerd.

Als u eenmaal bent begonnen met een SPF-terugvalbeleid van `?all`, kunt u geleidelijk meer e-mailbronnen voor uw berichten ontdekken en opnemen en vervolgens uw SPF-record bijwerken met een strikter beleid.

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a>Spoof Intelligence gebruiken om toegestane afzenders van niet-geverifieerde e-mail te configureren

U kunt [Spoof Intelligence](learn-about-spoof-intelligence.md) ook gebruiken om afzenders toe te staan niet-geverifieerde berichten naar uw organisatie te verzenden.

Voor externe domeinen is de vervalste gebruiker het domein in het Van-adres, terwijl de verzendende infrastructuur het bron-IP-adres is (onderverdeeld in 24 CIDR-bereiken) of het organisatiedomein van het omgekeerde DNS(PTR)-record.

In de onderstaande schermafbeelding is het bron-IP-adres mogelijk 131.107.18.4 met het PTR-record outbound.mail.protection.outlook.com. Dit wordt weergegeven als outlook.com voor de verzendende infrastructuur.

Om deze afzender toe te staan niet-geverifieerde e-mail te verzenden, wijzigt u **Nee** in **Ja**.

![Anti-adresvervalsing instellen voor toegestane afzenders](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a>Een vermelding met toestemming maken voor het afzender/geadresseerde-paar

Zie [Lijsten met veilige afzenders maken in Microsoft 365](create-safe-sender-lists-in-office-365.md) om spamfilters, sommige onderdelen van phish-filters, maar niet malwarefilters voor specifieke afzenders te omzeilen.

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a>Vraag de afzender om e-mailverificatie te configureren voor domeinen waarvan u niet de eigenaar bent

Vanwege het probleem van spam en phishing raadt Microsoft e-mailverificatie aan voor alle e-mailorganisaties. In plaats van handmatige overschrijvingen in uw organisatie te configureren, kunt u een beheerder in het verzendende domein vragen om hun e-mailverificatierecords te configureren.

- Zelfs als ze in het verleden geen e-mailverificatierecords hoefden te publiceren, zouden ze dit wel moeten doen als ze e-mail naar Microsoft sturen.

- U moet SPF instellen om de verzend-IP-adressen van het domein te publiceren en DKIM (indien beschikbaar) instellen om berichten digitaal te ondertekenen. Ze moeten ook overwegen om DMARC-records in te stellen.

- Als ze bulkmailers gebruiken om namens hen e-mail te verzenden, controleer dan of het domein in het Van-adres (als het van hen is) overeenkomt met het domein dat SPF of DMARC doorgeeft.

- Controleer of de volgende locaties (als ze deze gebruiken) zijn opgenomen in het SPF-record:

  - On-premises e-mailservers.
  - E-mail die is verzonden via een software-als-een-service (SaaS)-provider.
  - E-mail die is verzonden via een cloudservice (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, enz).

- Voor kleine domeinen die worden gehost door een internetprovider, configureert u de SPF-record volgens hun instructies.

Hoewel het in het begin misschien moeilijk is om zendende domeinen zo ver te krijgen dat ze verifiëren, zullen ze na verloop van tijd, als er meer en meer e-mailfilters hun e-mail als ongewenst markeren of zelfs afwijzen, de juiste records instellen voor betere aflevering. Bovendien kan hun deelname helpen bij het bestrijden van phishing en kan het de mogelijkheid van phishing in hun organisatie of organisaties waarnaar ze e-mail sturen, verminderen.

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a>Informatie voor infrastructuurproviders (ISP's, ESP's of cloudhostingservices)

Als u de e-mail van een domein host of een hosting-infrastructuur biedt die e-mail kan verzenden, moet u de volgende stappen uitvoeren:

- Zorg ervoor dat uw klanten beschikken over de documentatie waarin wordt uitgelegd hoe zij hun SPF-records moeten configureren

- U kunt DKIM-handtekeningen ondertekenen voor uitgaande e-mail, zelfs als de klant deze niet expliciet instelt (met een standaarddomein). U kunt zelfs het e-mailbericht met DKIM-handtekeningen dubbel ondertekenen (eenmaal met het domein van de klant als ze het hebben ingesteld, en een tweede keer met de handtekening van de DKIM van uw organisatie).

Bezorging aan Microsoft is niet gegarandeerd, zelfs niet als u e-mail verifieert die afkomstig is van uw platform, maar het zorgt er in ieder geval voor dat Microsoft uw e-mail niet als spam markeert, omdat deze niet is geverifieerd.

## <a name="related-links"></a>Verwante koppelingen

Zie voor meer informatie over aanbevolen procedures voor serviceproviders [M3AAWG aanbevolen procedures voor mobiele berichten voor serviceproviders](https://www.m3aawg.org/sites/default/files/m3aawg-mobile-messaging-best-practices-service-providers-2015-08_0.pdf).

Meer informatie over de manier waarop Office 365 SPF gebruikt en DKIM-validatie ondersteunt:

- [Meer informatie over SPF](how-office-365-uses-spf-to-prevent-spoofing.md)

- [Meer informatie over DKIM](support-for-validation-of-dkim-signed-messages.md)
