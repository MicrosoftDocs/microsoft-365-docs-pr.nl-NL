---
title: Hoe Microsoft 365 Sender Policy Framework (SPF) gebruikt om spoofing te voorkomen
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/15/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- M365-security-compliance
description: 'Samenvatting: In dit artikel wordt beschreven hoe Microsoft 365 de SPF-record (Sender Policy Framework) (SPF) in DNS gebruikt om ervoor te zorgen dat e-mailsystemen van bestemming berichten vertrouwen die vanuit uw aangepaste domein worden verzonden. Dit geldt voor uitgaande e-mail die is verzonden vanuit Microsoft 365. Berichten die van Microsoft 365 naar een ontvanger binnen Microsoft 365 worden verzonden, passeren altijd SPF.'
ms.openlocfilehash: d73fb881b8395c6c1383cca70e506694795f1364
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633988"
---
# <a name="how-microsoft-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a>Hoe Microsoft 365 Sender Policy Framework (SPF) gebruikt om spoofing te voorkomen

 **Samenvatting:** In dit artikel wordt beschreven hoe Microsoft 365 de SPF-record (Sender Policy Framework) (SPF) in DNS gebruikt om ervoor te zorgen dat e-mailsystemen van bestemming berichten vertrouwen die vanuit uw aangepaste domein worden verzonden. Dit geldt voor uitgaande e-mail die is verzonden vanuit Microsoft 365. Berichten die van Microsoft 365 naar een ontvanger binnen Microsoft 365 worden verzonden, passeren altijd SPF.

Een SPF TXT-record is een DNS-record die spoofing en phishing helpt voorkomen door de domeinnaam te verifiëren van waaruit e-mailberichten worden verzonden. SPF valideert de oorsprong van e-mailberichten door het IP-adres van de afzender te verifiëren tegen de vermeende eigenaar van het verzendende domein.

> [!NOTE]
> SPF record types werden afgeschaft door de Internet Engineering Task Force (IETF) in 2014. Controleer in plaats daarvan of u TXT-records in DNS gebruikt om uw SPF-gegevens te publiceren. De rest van dit artikel maakt gebruik van de term SPF TXT record voor de duidelijkheid.

Domeinbeheerders publiceren SPF-informatie in TXT-records in DNS. De SPF-informatie identificeert geautoriseerde uitgaande e-mailservers. Bestemmingse-mailsystemen controleren of berichten afkomstig zijn van geautoriseerde uitgaande e-mailservers. Als u al bekend bent met SPF, of als u een eenvoudige implementatie hebt en alleen maar wilt weten wat u in uw SPF TXT-record in DNS voor Microsoft 365 moet opnemen, u naar [SPF instellen in Microsoft 365 om spoofing te voorkomen.](set-up-spf-in-office-365-to-help-prevent-spoofing.md) Als u geen implementatie hebt die volledig wordt gehost in Microsoft 365, of als u meer informatie wilt over hoe SPF werkt of hoe u SPF voor Microsoft 365 oplossen, blijft u lezen.

> [!NOTE]
> Voorheen moest u een andere SPF TXT-record toevoegen aan uw aangepaste domein als u ook SharePoint Online hebt gebruikt. Dit is niet meer nodig. Deze wijziging moet het risico verkleinen dat SharePoint Online-meldingsberichten in de map Ongewenste e-mail terechtkomen. U hoeft niet onmiddellijk wijzigingen aan te brengen, maar als u de fout "te veel lookups" ontvangt, wijzigt u uw SPF TXT-record zoals beschreven in [SPF instellen in Microsoft 365 om spoofing te voorkomen.](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-microsoft-365"></a>Hoe SPF werkt om spoofing en phishing in Microsoft 365 te voorkomen
<a name="HowSPFWorks"> </a>

SPF bepaalt of een afzender al dan niet namens een domein mag verzenden. Als de afzender dit niet mag doen, dat wil zeggen, als de e-mail de SPF-controle op de ontvangende server niet haalt, bepaalt het spambeleid dat op die server is geconfigureerd, wat te doen met het bericht.

Elke SPF TXT-record bestaat uit drie delen: de verklaring dat het een SPF TXT-record is, de IP-adressen die e-mail mogen verzenden vanuit uw domein en de externe domeinen die namens uw domein kunnen worden verzonden, en een handhavingsregel. Je hebt ze alle drie nodig in een geldige SPF TXT-record. In dit artikel wordt beschreven hoe u uw SPF TXT-record vormt en worden aanbevolen procedures voor het werken met de services in Microsoft 365. Er worden ook koppelingen naar instructies verstrekt over het werken met uw domeinregistrar om uw record naar DNS te publiceren.

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a>SPF-basisbeginselen: IP-adressen die vanuit uw aangepaste domein mogen worden verzonden
<a name="SPFBasicsIPaddresses"> </a>

Bekijk de basissyntaxis voor een SPF-regel:

v=spf1 \<\> \<IP-handhavingsregel\>

Stel dat de volgende SPF-regel bestaat voor contoso.com:

v=spf1 \<\> \<IP-adres #1\> \<IP-adres #2 IP-adres #3\> \<handhavingsregel\>

In dit voorbeeld geeft de SPF-regel de ontvangende e-mailserver de opdracht om alleen e-mail van deze IP-adressen voor het domein contoso.com te accepteren:

- IP-adres #1

- IP-adres #2

- IP-adres #3

Deze SPF-regel vertelt de ontvangende e-mailserver dat als een bericht afkomstig is van contoso.com, maar niet van een van deze drie IP-adressen, de ontvangende server de handhavingsregel op het bericht moet toepassen. De handhavingsregel is meestal een van deze opties:

- **Hard falen.** Markeer het bericht met 'hard fail' in de berichtenvelop en volg vervolgens het geconfigureerde spambeleid van de ontvangende server voor dit type bericht.

- **Soft fail.** Markeer het bericht met 'soft fail' in de berichtenvelop. E-mailservers zijn meestal geconfigureerd om deze berichten toch te leveren. De meeste eindgebruikers zien dit merk niet.

- **Neutrale.** Doe niets, dat wil zeggen, niet markeren het bericht envelop. Dit is meestal gereserveerd voor testdoeleinden en wordt zelden gebruikt.

De volgende voorbeelden laten zien hoe SPF werkt in verschillende situaties. In deze voorbeelden is contoso.com de afzender en is woodgrovebank.com de ontvanger.

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a>Voorbeeld 1: E-mailverificatie van een bericht dat rechtstreeks van afzender naar ontvanger wordt verzonden
<a name="spfExample1"> </a>

SPF werkt het beste wanneer het pad van verzender naar ontvanger direct is, bijvoorbeeld:

![Diagram met de manier waarop SPF e-mail verifieert wanneer deze rechtstreeks van server naar server wordt verzonden.](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

Wanneer woodgrovebank.com het bericht ontvangt, als IP-adres #1 in de SPF TXT-record voor contoso.com staat, passeert het bericht de SPF-controle en wordt het geverifieerd.

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a>Voorbeeld 2: Vervalst afzenderadres voldoet niet aan de SPF-controle
<a name="spfExample2"> </a>

Stel dat een phisher een manier vindt om contoso.com te spoofen:

![Diagram met de manier waarop SPF e-mail verifieert wanneer deze wordt verzonden vanaf een vervalste server.](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

Aangezien IP-adres #12 niet in contoso.com's SPF TXT record, het bericht mislukt de SPF-controle en de ontvanger kan ervoor kiezen om het te markeren als spam.

### <a name="example-3-spf-and-forwarded-messages"></a>Voorbeeld 3: SPF en doorgestuurde berichten
<a name="spfExample3"> </a>

Een nadeel van SPF is dat het niet werkt wanneer een e-mail is doorgestuurd. Stel dat de gebruiker op woodgrovebank.com een doorstuurregel heeft ingesteld om alle e-mail naar een outlook.com account te verzenden:

![Diagram met de manier waarop SPF e-mail niet kan verifiëren wanneer het bericht wordt doorgestuurd.](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

Het bericht passeert oorspronkelijk de SPF-controle op woodgrovebank.com maar het mislukt de SPF-controle op outlook.com omdat IP-#25 niet in de SPF TXT-record van contoso.com staat. Outlook.com kunnen het bericht dan markeren als spam. Gebruik SPF in combinatie met andere e-mailverificatiemethoden zoals DKIM en DMARC om dit probleem op te lossen.

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a>SPF-basisprincipes: domeinen van derden opnemen die namens uw domein e-mail kunnen verzenden
<a name="SPFBasicsIncludes"> </a>

Naast IP-adressen u uw SPF TXT-record ook configureren om domeinen als afzenders op te nemen. Deze worden toegevoegd aan de SPF TXT record als "include" statements. Contoso.com wilt bijvoorbeeld alle IP-adressen van de e-mailservers van contoso.net en contoso.org die het ook bezit, opnemen. Om dit te doen, publiceert contoso.com een SPF TXT-record die er als volgt uitziet:

```text
v=spf1 include:contoso.net include:contoso.org -all
```

Wanneer de ontvangende server deze record in DNS ziet, voert deze ook een DNS-lookup uit op de SPF TXT-record voor contoso.net en vervolgens voor contoso.org. Als het vindt een extra instructie op te nemen in de records voor contoso.net of contoso.org, zal het ook volgen die. Om denial of service-aanvallen te voorkomen, is het maximum aantal DNS-lookups voor één e-mailbericht 10. Elke instructie bevat een extra DNS-lookup. Als een bericht de limiet van 10 overschrijdt, mislukt het bericht SPF. Zodra een bericht deze limiet bereikt, afhankelijk van de manier waarop de ontvangende server is geconfigureerd, kan de afzender een bericht ontvangen waarin staat dat het bericht "te veel lookups" heeft gegenereerd of dat het "maximale hopaantal voor het bericht is overschreden" (wat kan gebeuren wanneer de lookups loop en de DNS-time-out overschrijdt). Zie [Probleemoplossing: Aanbevolen procedures voor SPF in Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)voor tips om dit te voorkomen.

## <a name="requirements-for-your-spf-txt-record-and-microsoft-365"></a>Vereisten voor uw SPF TXT-record en Microsoft 365
<a name="SPFReqsinO365"> </a>

Als u e-mail instelt wanneer u Microsoft 365 instelt, hebt u al een SPF TXT-record gemaakt waarmee de Microsoft-berichtenservers worden geïdentificeerd als een legitieme bron van e-mail voor uw domein. Deze plaat ziet er waarschijnlijk als volgt uit:

```text
v=spf1 include:spf.protection.outlook.com -all
```

Als u een volledig gehoste klant bent, dat wil zeggen dat u geen on-premises e-mailservers hebt die uitgaande e-mail verzenden, dit is de enige SPF TXT-record die u moet publiceren voor Office 365.

Als u een hybride implementatie hebt (dat wil zeggen dat u een aantal postvakken on-premises hebt en sommige gehost in Microsoft 365), of als u een zelfstandige Exchange Online Protection-klant (dat wil zeggen, uw organisatie eop gebruikt om uw on-premises postvakken te beschermen), moet u het uitgaande IP-adres voor elk van uw on-premises edge-mailservers toevoegen aan de SPF TXT-record in DNS.

## <a name="form-your-spf-txt-record-for-microsoft-365"></a>Uw SPF TXT-record vormen voor Microsoft 365
<a name="FormYourSPF"> </a>

Gebruik de syntaxisgegevens in dit artikel om de SPF TXT-record voor uw aangepaste domein te vormen. Hoewel er andere syntaxisopties zijn die hier niet worden genoemd, zijn dit de meest gebruikte opties. Wanneer u het record hebt gemaakt, moet u het record bij uw domeinregistrar bijwerken.

Zie [Externe DNS-records die nodig zijn voor SPF](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records)voor informatie over de domeinen die u voor Microsoft 365 moet opnemen. Gebruik de stapsgewijze instructies voor het bijwerken van [SPF-records](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) (TXT) voor uw domeinregistrar.

### <a name="spf-txt-record-syntax-for-microsoft-365"></a>Syntaxis van SPF TXT-record voor Microsoft 365
<a name="SPFSyntaxO365"> </a>

Een typische SPF TXT-record voor Microsoft 365 heeft de volgende syntaxis:

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

Bijvoorbeeld:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

waarbij:

- **v=spf1** is vereist. Dit definieert de TXT-record als een SPF TXT-record.

- **ip4** geeft aan dat u IP-adressen van versie 4 gebruikt. **ip6** geeft aan dat u IP-versie 6-adressen gebruikt. Als u IPv6 IP-adressen gebruikt, vervangt **u ip4** door **ip6** in de voorbeelden in dit artikel. U ook IP-adresbereiken opgeven met CIDR-notatie, bijvoorbeeld **ip4:192.168.0.1/26**.

- _IP-adres_ is het IP-adres dat u wilt toevoegen aan de SPF TXT-record. Meestal is dit het IP-adres van de uitgaande e-mailserver voor uw organisatie. U meerdere uitgaande e-mailservers weergeven. Zie [Voorbeeld: SPF TXT-record voor meerdere uitgaande on-premises e-mailservers en Microsoft 365 voor](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365)meer informatie.

- _domeinnaam_ is het domein dat u wilt toevoegen als legitieme afzender. Zie [Externe DNS-records die nodig zijn voor SPF voor](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records)een lijst met domeinnamen die u voor Microsoft 365 moet opnemen.

- Handhaving regel is meestal een van de volgende:

  - -alle

    Geeft harde mislukken aan. Als u alle geautoriseerde IP-adressen voor uw domein kent, vermeldze dan in de SPF TXT-record en gebruikt de (hard fail)-kwalificatie. Ook als u alleen SPF gebruikt, dat wil zeggen dat u geen DMARC of DKIM gebruikt, moet u de -all qualifier gebruiken. Wij raden u aan altijd deze kwalificatie te gebruiken.

  - ~alle

    Geeft aan dat er een zachte fail is. Als u niet zeker weet of u de volledige lijst met IP-adressen hebt, moet u de ~all (soft fail) qualifier gebruiken. Ook als u DMARC gebruikt met p=quarantine of p=reject, dan u ~allen gebruiken. Gebruik anders -all.

  - ?allen

    Geeft neutraal aan. Dit wordt gebruikt bij het testen van SPF. We raden u niet aan deze kwalificatie te gebruiken in uw live-implementatie.

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-microsoft-365"></a>Voorbeeld: SPF TXT-record dat moet worden gebruikt wanneer al uw e-mail wordt verzonden door Microsoft 365
<a name="ExampleSPFNoSP"> </a>

Als al uw e-mail door Microsoft 365 wordt verzonden, gebruikt u deze in uw SPF TXT-record:

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-microsoft-365"></a>Voorbeeld: SPF TXT-record voor een hybride scenario met één on-premises Exchange Server en Microsoft 365
<a name="ExampleSPFHybridOneExchangeServer"> </a>

Als het IP-adres van uw on-premises Exchange Server in een hybride omgeving 192.168.0.1 is, om de SPF-handhavingsregel op harde fail in te stellen, vormt u de SPF TXT-record als volgt:

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-microsoft-365"></a>Voorbeeld: SPF TXT-record voor meerdere uitgaande on-premises e-mailservers en Microsoft 365
<a name="ExampleSPFMultipleMailServerO365"> </a>

Als u meerdere uitgaande e-mailservers hebt, neemt u het IP-adres voor elke e-mailserver op in de SPF TXT-record en scheidt u elk IP-adres met een ruimte gevolgd door een "ip4:"-instructie. Bijvoorbeeld:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-microsoft-365"></a>Volgende stappen: SPF instellen voor Microsoft 365
<a name="SPFNextSteps"> </a>

Zodra u uw SPF TXT-record hebt geformuleerd, volgt u de stappen in [SPF instellen in Microsoft 365 om spoofing te voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md) om deze aan uw domein toe te voegen.

Hoewel SPF is ontworpen om spoofing te voorkomen, maar er zijn spoofing technieken die SPF niet kan beschermen tegen. Om u hiertegen te beschermen, moet u, zodra u SPF hebt ingesteld, ook DKIM en DMARC configureren voor Microsoft 365. Zie [DKIM gebruiken om uitgaande e-mail die vanuit uw aangepaste domein in Microsoft 365 is verzonden, te valideren.](use-dkim-to-validate-outbound-email.md) Zie vervolgens [DMARC gebruiken om e-mail te valideren in Microsoft 365](use-dmarc-to-validate-email.md).

## <a name="troubleshooting-best-practices-for-spf-in-microsoft-365"></a>Probleemoplossing: aanbevolen procedures voor SPF in Microsoft 365
<a name="SPFTroubleshoot"> </a>

U slechts één SPF TXT-record maken voor uw aangepaste domein. Het maken van meerdere records veroorzaakt een ronde robin situatie en SPF zal mislukken. Om dit te voorkomen, u afzonderlijke records maken voor elk subdomein. Maak bijvoorbeeld één record voor contoso.com en een andere record voor bulkmail.contoso.com.

Als een e-mailbericht meer dan 10 DNS-lookups veroorzaakt voordat het wordt bezorgd, reageert de ontvangende e-mailserver met een permanente fout, ook wel een _permanent fout_genoemd, en zorgt ervoor dat het bericht de SPF-controle mislukt. De ontvangende server kan ook reageren met een NDR (non-delivery report) dat een fout bevat die vergelijkbaar is met deze:

- Het bericht overschreed het aantal hop.

- Het bericht vereiste te veel lookups.

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-microsoft-365"></a>Het vermijden van de fout "te veel lookups" wanneer u domeinen van derden gebruikt met Microsoft 365
<a name="SPFTroubleshoot"> </a>

Sommige SPF TXT-records voor domeinen van derden sturen de ontvangende server om een groot aantal DNS-lookups uit te voeren. Op het moment van schrijven bevat Salesforce.com bijvoorbeeld 5 verklaringen in de record:

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

Om de fout te voorkomen, u een beleid implementeren waarbij iedereen die bulke-mail verzendt, bijvoorbeeld een subdomein specifiek voor dit doel moet gebruiken. Vervolgens definieert u een andere SPF TXT-record voor het subdomein dat de bulk-e-mail bevat.

 In sommige gevallen, zoals het salesforce.com voorbeeld, moet u het domein in uw SPF TXT-record gebruiken, maar in andere gevallen heeft de derde partij mogelijk al een subdomein gemaakt dat u voor dit doel gebruiken. Exacttarget.com heeft bijvoorbeeld een subdomein gemaakt dat u moet gebruiken voor uw SPF TXT-record:

```text
cust-spf.exacttarget.com
```

Wanneer u domeinen van derden opneemt in uw SPF TXT-record, moet u met de derde partij bevestigen welk domein of subdomein u moet gebruiken om te voorkomen dat u de 10-opzoeklimiet binnenloopt.

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a>Uw huidige SPF TXT-record bekijken en het aantal lookups bepalen dat nodig is
<a name="SPFTroubleshoot"> </a>

U nslookup gebruiken om uw DNS-records weer te geven, inclusief uw SPF TXT-record. Of, als u dat liever hebt, zijn er een aantal gratis, online tools beschikbaar die u gebruiken om de inhoud van uw SPF TXT-record te bekijken. Door te kijken naar uw SPF TXT-record en de keten van instructies en omleidingen te volgen, u bepalen hoeveel DNS-lookups de record vereist. Sommige online tools tellen zelfs en geven deze lookups voor u weer. Als u dit nummer bijhoudt, voorkomt u dat berichten die van uw organisatie worden verzonden, een permanente fout, een zogenaamde permfout, van de ontvangende server veroorzaken.

## <a name="for-more-information"></a>Voor meer informatie
<a name="SPFTroubleshoot"> </a>

Hulp nodig bij het toevoegen van de SPF TXT-record? Lees het artikel [DNS-records maken bij elke DNS-hostingprovider voor Microsoft 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) voor gedetailleerde informatie over het gebruik van Sender Policy Framework met uw aangepaste domein in Microsoft 365. [Antispamberichtenkoppen](anti-spam-message-headers.md) bevatten de syntaxis- en koptekstvelden die door Microsoft 365 worden gebruikt voor SPF-controles.


