---
title: Hoe Sender Policy Framework (SPF) spoofing voorkomt
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
ms.custom:
- seo-marvel-apr2020
description: Lees hoe Microsoft 365 de TXT-record (Sender Policy Framework) (SPF) in DNS gebruikt om ervoor te zorgen dat e-mailsystemen berichten vertrouwen die vanuit uw aangepaste domein worden verzonden.
ms.openlocfilehash: a86087f510dca328bb5b56af6fd4802f1f42a454
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587482"
---
# <a name="how-microsoft-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a>Hoe Microsoft 365 SPF (Sender Policy Framework) gebruikt om adresvervalsing te voorkomen

 **Samenvatting:** In dit artikel wordt beschreven hoe Microsoft 365 de TXT-record (Sender Policy Framework) (SPF) in DNS gebruikt om ervoor te zorgen dat e-mailsystemen berichten vertrouwen die vanuit uw aangepaste domein worden verzonden. Dit geldt voor uitgaande e-mail die wordt verzonden vanaf Microsoft 365. Berichten die van Microsoft 365 naar een ontvanger binnen Microsoft 365 worden verzonden, worden altijd door SPF verzonden.

Een SPF TXT-record is een DNS-record die spoofing en phishing helpt voorkomen door de domeinnaam te verifiëren waaruit e-mailberichten worden verzonden. SPF valideert de oorsprong van e-mailberichten door het IP-adres van de afzender te verifiëren tegen de vermeende eigenaar van het verzendende domein.

> [!NOTE]
> SPF-recordtypen werden in 2014 afgeschaft door de Internet Engineering Task Force (IETF). Zorg er in plaats daarvan voor dat u TXT-records in DNS gebruikt om uw SPF-informatie te publiceren. De rest van dit artikel maakt gebruik van de term SPF TXT record voor de duidelijkheid.

Domeinbeheerders publiceren SPF-informatie in TXT-records in DNS. De SPF-informatie identificeert geautoriseerde uitgaande e-mailservers. E-mailsystemen voor bestemmingen controleren of berichten afkomstig zijn van geautoriseerde uitgaande e-mailservers. Als u al bekend bent met SPF, of als u een eenvoudige implementatie hebt, en u hoeft alleen maar te weten wat u in uw SPF TXT-record in DNS voor Microsoft 365 moet opnemen, u naar [SPF instellen in Microsoft 365 om spoofing te voorkomen.](set-up-spf-in-office-365-to-help-prevent-spoofing.md) Als u geen implementatie hebt die volledig is gehost in Microsoft 365 of als u meer informatie wilt over hoe SPF werkt of hoe u SPF voor Microsoft 365 oplossen, lees dan verder.

> [!NOTE]
> Voorheen moest u een andere SPF TXT-record toevoegen aan uw aangepaste domein als u ook SharePoint Online gebruikte. Dit is niet meer nodig. Deze wijziging moet het risico verkleinen dat SharePoint Online-meldingsberichten in de map Ongewenste e-mail terechtkomen. U hoeft niet onmiddellijk wijzigingen aan te brengen, maar als u de fout "te veel lookups" ontvangt, wijzigt u uw SPF TXT-record zoals beschreven in [SPF instellen in Microsoft 365 om spoofing te voorkomen.](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-microsoft-365"></a>Hoe SPF werkt om spoofing en phishing in Microsoft 365 te voorkomen
<a name="HowSPFWorks"> </a>

SPF bepaalt of een afzender al dan niet namens een domein mag verzenden. Als de afzender dit niet is toegestaan, dat wil zeggen, als de e-mail niet voldoet aan de SPF-controle op de ontvangende server, bepaalt het op die server geconfigureerde spambeleid wat te doen met het bericht.

Elke SPF TXT-record bestaat uit drie delen: de verklaring dat het een SPF TXT-record is, de IP-adressen die e-mail mogen verzenden vanuit uw domein en de externe domeinen die namens uw domein kunnen worden verzonden, en een handhavingsregel. Je hebt ze alle drie nodig in een geldige SPF TXT-record. In dit artikel wordt beschreven hoe u uw SPF TXT-record vormt en de aanbevolen procedures voor het werken met de services in Microsoft 365. Er worden ook koppelingen naar instructies gegeven over het werken met uw domeinregistrar om uw record op DNS te publiceren.

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a>Basisbeginselen van SPF: IP-adressen die mogen worden verzonden vanuit uw aangepaste domein
<a name="SPFBasicsIPaddresses"> </a>

Bekijk de basissyntaxis voor een SPF-regel:

v=spf1 \<IP\>\<enforcement rule\>

Stel dat de volgende SPF-regel bestaat voor contoso.com:

v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\>\<enforcement rule\>

In dit voorbeeld geeft de SPF-regel de ontvangende e-mailserver opdracht om alleen e-mail van deze IP-adressen voor het domein contoso.com te accepteren:

- #1 IP-adres

- #2 IP-adres

- #3 IP-adres

Deze SPF-regel vertelt de ontvangende e-mailserver dat als een bericht afkomstig is van contoso.com, maar niet van een van deze drie IP-adressen, de ontvangende server de handhavingsregel op het bericht moet toepassen. De handhavingsregel is meestal een van deze opties:

- **Hard falen.** Markeer het bericht met 'harde fail' in de berichtenenvelop en volg vervolgens het geconfigureerde spambeleid van de ontvangende server voor dit type bericht.

- **Zachte mislukken.** Markeer het bericht met 'soft fail' in de berichtenenvelop. Doorgaans zijn e-mailservers geconfigureerd om deze berichten toch af te leveren. De meeste eindgebruikers zien dit merk niet.

- **Neutrale.** Niets doen, dat wil zeggen, niet markeren het bericht envelop. Dit is meestal gereserveerd voor testdoeleinden en wordt zelden gebruikt.

De volgende voorbeelden laten zien hoe SPF werkt in verschillende situaties. In deze voorbeelden is contoso.com de afzender en woodgrovebank.com de ontvanger.

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a>Voorbeeld 1: E-mailverificatie van een bericht dat rechtstreeks van afzender naar ontvanger wordt verzonden
<a name="spfExample1"> </a>

SPF werkt het beste wanneer het pad van afzender naar ontvanger direct is, bijvoorbeeld:

![Diagram met de manier waarop SPF e-mail verifieert wanneer deze rechtstreeks van server naar server wordt verzonden.](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

Wanneer woodgrovebank.com het bericht ontvangt, als IP-adres #1 in de SPF TXT-record voor contoso.com staat, passeert het bericht de SPF-controle en wordt het geverifieerd.

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a>Voorbeeld 2: Vervalst afzenderadres mislukt de SPF-controle
<a name="spfExample2"> </a>

Stel dat een phisher een manier vindt om contoso.com te spoofen:

![Diagram met de manier waarop SPF e-mail verifieert wanneer deze wordt verzonden vanaf een vervalste server.](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

Aangezien IP-adres #12 niet in contoso.com's SPF TXT-record staat, mislukt het bericht de SPF-controle en kan de ontvanger ervoor kiezen om het als spam te markeren.

### <a name="example-3-spf-and-forwarded-messages"></a>Voorbeeld 3: SPF en doorgestuurde berichten
<a name="spfExample3"> </a>

Een nadeel van SPF is dat het niet werkt wanneer een e-mail is doorgestuurd. Stel dat de gebruiker van woodgrovebank.com een doorstuurregel heeft ingesteld om alle e-mail naar een outlook.com-account te verzenden:

![Diagram met de manier waarop SPF e-mail niet kan verifiëren wanneer het bericht wordt doorgestuurd.](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

Het bericht passeert oorspronkelijk de SPF-controle op woodgrovebank.com, maar het mislukt de SPF-controle op outlook.com omdat IP-#25 niet in de SPF TXT-record van contoso.com staat. Outlook.com kan het bericht dan markeren als spam. Als u dit probleem wilt oplossen, gebruikt u SPF in combinatie met andere e-mailverificatiemethoden zoals DKIM en DMARC.

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a>Basisbeginselen van SPF: domeinen van derden opnemen die namens uw domein e-mail kunnen verzenden
<a name="SPFBasicsIncludes"> </a>

Naast IP-adressen u ook uw SPF TXT-record configureren om domeinen als afzenders op te nemen. Deze worden toegevoegd aan de SPF TXT record als "include" statements. Contoso.com wilt bijvoorbeeld alle IP-adressen van de e-mailservers van contoso.net en contoso.org die het ook bezit, opnemen. Hiervoor publiceert contoso.com een SPF TXT-record die er als volgt uitziet:

```text
v=spf1 include:contoso.net include:contoso.org -all
```

Wanneer de ontvangende server deze record in DNS ziet, wordt ook een DNS-lookup uitgevoerd op de SPF TXT-record voor contoso.net en vervolgens voor contoso.org. Als het vindt een extra include verklaring in de records voor contoso.net of contoso.org, zal het ook volgen die. Om denial of service-aanvallen te voorkomen, is het maximum aantal DNS-lookups voor één e-mailbericht 10. Elke include-instructie vertegenwoordigt een extra DNS-lookup. Als een bericht de limiet van 10 overschrijdt, mislukt het bericht SPF. Zodra een bericht deze limiet bereikt, afhankelijk van de manier waarop de ontvangende server is geconfigureerd, kan de afzender een bericht krijgen waarin staat dat het bericht "te veel lookups" genereert of dat het "maximale aantal hop voor het bericht is overschreden" (wat kan gebeuren wanneer de lookups-lus en de DNS-time-out overtreffen). Zie [Probleemoplossing: Aanbevolen procedures voor SPF in Microsoft 365 voor](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)tips om dit te voorkomen.

## <a name="requirements-for-your-spf-txt-record-and-microsoft-365"></a>Vereisten voor uw SPF TXT-record en Microsoft 365
<a name="SPFReqsinO365"> </a>

Als u e-mail instelt wanneer u Microsoft 365 instelt, hebt u al een SPF TXT-record gemaakt waarmee de Berichtenservers van Microsoft worden geïdentificeerd als een legitieme bron van e-mail voor uw domein. Dit record ziet er waarschijnlijk als volgt uit:

```text
v=spf1 include:spf.protection.outlook.com -all
```

Als u een volledig gehoste klant bent, dat wil zeggen dat u geen on-premises e-mailservers hebt die uitgaande e-mail verzenden, is dit de enige SPF TXT-record die u moet publiceren voor Office 365.

Als u een hybride implementatie hebt (dat wil zeggen dat u een aantal postvakken on-premises en sommige hebt gehost in Microsoft 365), of als u een zelfstandige klant (EOP) (dat wil zeggen, uw organisatie gebruikt EOP om uw on-premises mailboxen te beschermen), moet u het uitgaande IP-adres voor elk van uw on-premises edge mailservers toevoegen aan de SPF TXT-record in DNS.

## <a name="form-your-spf-txt-record-for-microsoft-365"></a>Uw SPF TXT-record voor Microsoft 365
<a name="FormYourSPF"> </a>

Gebruik de syntaxisgegevens in dit artikel om de SPF TXT-record voor uw aangepaste domein te vormen. Hoewel er andere syntaxisopties zijn die hier niet worden genoemd, zijn dit de meest gebruikte opties. Wanneer u het record hebt gemaakt, moet u het record bij uw domeinregistrar bijwerken.

Zie [Externe DNS-records die vereist zijn voor SPF](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records)voor informatie over de domeinen die u voor Microsoft 365 moet opnemen. Gebruik de [stapsgewijze instructies](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) voor het bijwerken van SPF-records (TXT) voor uw domeinregistrar.

### <a name="spf-txt-record-syntax-for-microsoft-365"></a>SPF TXT-recordsyntaxis voor Microsoft 365
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

- **ip4** geeft aan dat u IP-adressen van versie 4 gebruikt. **ip6** geeft aan dat u IP-adressen van versie 6 gebruikt. Als u IP-adressen van IPv6 gebruikt, vervangt **u ip4** door **ip6** in de voorbeelden in dit artikel. U ook IP-adresbereiken opgeven met CIDR-notatie, bijvoorbeeld **ip4:192.168.0.1/26**.

- _IP-adres_ is het IP-adres dat u wilt toevoegen aan de SPF TXT-record. Meestal is dit het IP-adres van de uitgaande e-mailserver voor uw organisatie. U meerdere uitgaande e-mailservers aanbieden. Zie [Voorbeeld: SPF TXT-record voor meerdere uitgaande on-premises e-mailservers en Microsoft 365 voor](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365)meer informatie.

- _domeinnaam_ is het domein dat u wilt toevoegen als een legitieme afzender. Zie [Externe DNS-records die vereist zijn voor SPF voor](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records)een lijst met domeinnamen die u voor Microsoft 365 moet opnemen.

- Handhaving regel is meestal een van de volgende:

  - -alles

    Geeft harde mislukking aan. Als u alle geautoriseerde IP-adressen voor uw domein kent, vermeldt u deze in de SPF TXT-record en gebruikt u de -all (hard fail) qualifier. Als u alleen SPF gebruikt, dat wil zeggen dat u DMARC of DKIM niet gebruikt, moet u de -all qualifier gebruiken. Wij raden u aan altijd deze kwalificatie te gebruiken.

  - ~alle

    Geeft zachte fail aan. Als u niet zeker weet of u de volledige lijst met IP-adressen hebt, moet u de ~all (soft fail) qualifier gebruiken. Ook als u DMARC gebruikt met p=quarantaine of p=reject, dan u ~all gebruiken. Anders, gebruik -all.

  - ?alle

    Geeft neutraal aan. Dit wordt gebruikt bij het testen van SPF. We raden je af om deze kwalificatie te gebruiken in je live-implementatie.

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-microsoft-365"></a>Voorbeeld: SPF TXT-record om te gebruiken wanneer al uw e-mail wordt verzonden door Microsoft 365
<a name="ExampleSPFNoSP"> </a>

Als al uw e-mail wordt verzonden door Microsoft 365, gebruikt u deze in uw SPF TXT-record:

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-microsoft-365"></a>Voorbeeld: SPF TXT-record voor een hybride scenario met één on-premises Exchange Server en Microsoft 365
<a name="ExampleSPFHybridOneExchangeServer"> </a>

Als het IP-adres van uw on-premises Exchange Server 192.168.0.1 is, vormt u, om de SPF-handhavingsregel in te stellen als het moeilijk is, de SPF TXT-record als volgt:

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-microsoft-365"></a>Voorbeeld: SPF TXT-record voor meerdere uitgaande on-premises e-mailservers en Microsoft 365
<a name="ExampleSPFMultipleMailServerO365"> </a>

Als u meerdere uitgaande e-mailservers hebt, moet u het IP-adres voor elke e-mailserver opnemen in de SPF TXT-record en elk IP-adres scheiden met een spatie gevolgd door een "ip4:"-instructie. Bijvoorbeeld:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-microsoft-365"></a>Volgende stappen: SPF instellen voor Microsoft 365
<a name="SPFNextSteps"> </a>

Zodra u uw SPF TXT-record hebt geformuleerd, volgt u de stappen in [SPF instellen in Microsoft 365 om spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) te voorkomen om deze aan uw domein toe te voegen.

Hoewel SPF is ontworpen om spoofing te voorkomen, maar er zijn spoofing technieken die SPF niet kan beschermen tegen. Om deze te beschermen, moet u, zodra u SPF hebt ingesteld, ook DKIM en DMARC configureren voor Microsoft 365. Zie [DKIM gebruiken om uitgaande e-mail die vanuit uw aangepaste domein in Microsoft 365 is verzonden, te valideren.](use-dkim-to-validate-outbound-email.md) Zie vervolgens [DMARC gebruiken om e-mail in Microsoft 365 te valideren](use-dmarc-to-validate-email.md).

## <a name="troubleshooting-best-practices-for-spf-in-microsoft-365"></a>Probleemoplossing: aanbevolen procedures voor SPF in Microsoft 365
<a name="SPFTroubleshoot"> </a>

U slechts één SPF TXT-record maken voor uw aangepaste domein. Het maken van meerdere records veroorzaakt een round robin situatie en SPF zal mislukken. Om dit te voorkomen, u afzonderlijke records voor elk subdomein maken. Maak bijvoorbeeld een record voor contoso.com en een andere record voor bulkmail.contoso.com.

Als een e-mailbericht meer dan 10 DNS-lookups veroorzaakt voordat het wordt bezorgd, reageert de ontvangende e-mailserver met een permanente fout, ook wel een _permerror_genoemd, en zorgt het bericht ervoor dat het bericht niet voldoet aan de SPF-controle. De ontvangende server kan ook reageren met een niet-leveringsrapport (NDR) dat een vergelijkbare fout bevat als:

- Het bericht overschreed het aantal hop.

- Het bericht vereiste te veel lookups.

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-microsoft-365"></a>Het vermijden van de fout 'te veel lookups' wanneer u domeinen van derden gebruikt met Microsoft 365
<a name="SPFTroubleshoot"> </a>

Sommige SPF TXT-records voor domeinen van derden sturen de ontvangende server om een groot aantal DNS-lookups uit te voeren. Op het moment van schrijven bevat Salesforce.com bijvoorbeeld 5 instructies in de record:

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

Om de fout te voorkomen, u een beleid implementeren waarbij iedereen die bijvoorbeeld bulke-mail verzendt, een subdomein specifiek voor dit doel moet gebruiken. Vervolgens definieert u een andere SPF TXT-record voor het subdomein dat de bulke-mail bevat.

 In sommige gevallen, zoals het salesforce.com voorbeeld, moet u het domein gebruiken in uw SPF TXT-record, maar in andere gevallen heeft de derde partij mogelijk al een subdomein gemaakt die u voor dit doel gebruiken. Exacttarget.com heeft bijvoorbeeld een subdomein gemaakt dat u moet gebruiken voor uw SPF TXT-record:

```text
cust-spf.exacttarget.com
```

Wanneer u domeinen van derden opneemt in uw SPF TXT-record, moet u met de derde partij bevestigen welk domein of subdomein u moet gebruiken om te voorkomen dat u de opzoeklimiet van 10 moet tegenkomen.

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a>Hoe u uw huidige SPF TXT-record bekijken en het aantal opzoekingen bepalen dat nodig is
<a name="SPFTroubleshoot"> </a>

U nslookup gebruiken om uw DNS-records weer te geven, inclusief uw SPF TXT-record. Of, als u dat liever hebt, zijn er een aantal gratis, online tools beschikbaar die u gebruiken om de inhoud van uw SPF TXT-record te bekijken. Door te kijken naar uw SPF TXT-record en het volgen van de keten van include-instructies en omleidingen, u bepalen hoeveel DNS-lookups de record vereist. Sommige online tools tellen en tonen deze lookups zelfs voor je. Als u dit nummer bijhoudt, voorkomt u dat berichten die vanuit uw organisatie worden verzonden, een permanente fout, een permerror, van de ontvangende server activeren.

## <a name="for-more-information"></a>Voor meer informatie
<a name="SPFTroubleshoot"> </a>

Hulp nodig bij het toevoegen van de SPF TXT-record? Lees het artikel [DNS-records maken bij een DNS-hostingprovider voor Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) voor gedetailleerde informatie over het gebruik van Sender Policy Framework met uw aangepaste domein in Microsoft 365. [Antispamberichtenkoppen](anti-spam-message-headers.md) bevatten de syntaxis- en koptekstvelden die microsoft 365 voor SPF-controles gebruiken.


