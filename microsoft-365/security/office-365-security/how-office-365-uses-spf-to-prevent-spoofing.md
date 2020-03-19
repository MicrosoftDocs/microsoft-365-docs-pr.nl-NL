---
title: Hoe Office 365 Sender Policy Framework (SPF) gebruikt om spoofing te voorkomen
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
description: 'Samenvatting: In dit artikel wordt beschreven hoe Office 365 de TXT-record (Sender Policy Framework) in DNS gebruikt om ervoor te zorgen dat berichten die vanuit uw aangepaste domein zijn verzonden, van doele-mailsystemen worden vertrouwd. Dit geldt voor uitgaande e-mail die vanuit Office 365 wordt verzonden. Berichten die vanuit Office 365 naar een ontvanger in Office 365 worden verzonden, slagen altijd voor SPF.'
ms.openlocfilehash: e2863c0b8a66fa511c4ce842dc8026e880594292
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42805478"
---
# <a name="how-office-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a>Hoe Office 365 Sender Policy Framework (SPF) gebruikt om spoofing te voorkomen

 **Samenvatting:** In dit artikel wordt beschreven hoe Office 365 de TXT-record (Sender Policy Framework) in DNS gebruikt om ervoor te zorgen dat doele-mailsystemen berichten die vanuit uw aangepaste domein zijn verzonden, vertrouwen. Dit geldt voor uitgaande e-mail die vanuit Office 365 wordt verzonden. Berichten die vanuit Office 365 naar een ontvanger in Office 365 worden verzonden, slagen altijd voor SPF.

Een SPF TXT-record is een DNS-record die spoofing en phishing helpt voorkomen door de domeinnaam te verifiëren van welke e-mailberichten worden verzonden. SPF valideert de oorsprong van e-mailberichten door het IP-adres van de afzender te verifiëren tegen de vermeende eigenaar van het verzendende domein.

> [!NOTE]
> SPF recordtypes werden in 2014 afgeschaft door de Internet Engineering Task Force (IETF). Zorg er in plaats daarvan voor dat u TXT-records in DNS gebruikt om uw SPF-gegevens te publiceren. De rest van dit artikel gebruikt de term SPF TXT record voor de duidelijkheid.

Domeinbeheerders publiceren SPF-informatie in TXT-records in DNS. De SPF-informatie identificeert geautoriseerde uitgaande e-mailservers. Doele-mailsystemen controleren of berichten afkomstig zijn van geautoriseerde uitgaande e-mailservers. Als u al bekend bent met SPF of een eenvoudige implementatie hebt en alleen moet weten wat u in uw SPF TXT-record in DNS voor Office 365 wilt opnemen, u naar [SPF instellen in Office 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md)gaan om spoofing te voorkomen. Als u geen implementatie hebt die volledig is gehost in Office 365 of als u meer informatie wilt over hoe SPF werkt of hoe u SPF voor Office 365 oplossen, blijft u lezen.

> [!NOTE]
> Voorheen moest u een andere SPF TXT-record toevoegen aan uw aangepaste domein als u ook SharePoint Online hebt gebruikt. Dit is niet langer nodig. Deze wijziging moet het risico verminderen dat meldingsberichten van SharePoint Online in de map Ongewenste e-mail terechtkomen. U hoeft niet onmiddellijk wijzigingen aan te brengen, maar als u de fout 'te veel opzoekingen' ontvangt, wijzigt u uw SPF TXT-record zoals beschreven in [SPF instellen in Office 365 om spoofing te voorkomen.](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-office-365"></a>Hoe SPF werkt om spoofing en phishing in Office 365 te voorkomen
<a name="HowSPFWorks"> </a>

SPF bepaalt of een afzender al dan niet namens een domein mag verzenden. Als de afzender dit niet mag doen, dat wil zeggen dat als de e-mail de SPF-controle op de ontvangende server mislukt, het spambeleid dat op die server is geconfigureerd, bepaalt wat te doen met het bericht.

Elke SPF TXT-record bevat drie delen: de verklaring dat het een SPF TXT-record is, de IP-adressen die e-mail mogen verzenden vanuit uw domein en de externe domeinen die namens uw domein kunnen worden verzonden, en een handhavingsregel. Je hebt ze alle drie nodig in een geldige SPF TXT-record. In dit artikel wordt beschreven hoe u uw SPF TXT-record vormt en biedt u aanbevolen procedures voor het werken met de services in Office 365. Links naar instructies voor het werken met uw domeinregistrar om uw record te publiceren naar DNS zijn ook aanwezig.

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a>SPF-basisbeginselen: IP-adressen die vanuit uw aangepaste domein mogen worden verzonden
<a name="SPFBasicsIPaddresses"> </a>

Bekijk de basissyntaxis voor een SPF-regel:

v=spf1 \<\> \<IP-handhavingsregel\>

Stel dat er de volgende SPF-regel bestaat voor contoso.com:

v=spf1 \<\> \<IP-adres #1\> \<IP-adres #2 IP-adres #3\> \<handhavingsregel\>

In dit voorbeeld geeft de SPF-regel de ontvangende e-mailserver de opdracht om alleen e-mail van deze IP-adressen voor het domein te accepteren contoso.com:

- IP-adres #1

- IP-adres #2

- IP-adres #3

Deze SPF-regel vertelt de ontvangende e-mailserver dat als een bericht afkomstig is van contoso.com, maar niet van een van deze drie IP-adressen, de ontvangende server de handhavingsregel op het bericht moet toepassen. De handhavingsregel is meestal een van de volgende opties:

- **Hard mislukken.** Markeer het bericht met 'hard fail' in de berichtenvelop en volg vervolgens het geconfigureerde spambeleid van de ontvangende server voor dit type bericht.

- **Soft fail.** Markeer het bericht met 'soft fail' in de berichtenvelop. Meestal zijn e-mailservers geconfigureerd om deze berichten toch te leveren. De meeste eindgebruikers zien dit merk niet.

- **Neutrale.** Doe niets, dat wil zeggen, niet markeren het bericht envelop. Dit is meestal gereserveerd voor testdoeleinden en wordt zelden gebruikt.

De volgende voorbeelden laten zien hoe SPF werkt in verschillende situaties. In deze voorbeelden is contoso.com de afzender en woodgrovebank.com de ontvanger is.

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a>Voorbeeld 1: E-mailverificatie van een bericht dat rechtstreeks van afzender naar ontvanger wordt verzonden
<a name="spfExample1"> </a>

SPF werkt het beste wanneer het pad van afzender naar ontvanger direct is, bijvoorbeeld:

![Diagram met hoe SPF e-mail verifieert wanneer deze rechtstreeks van server naar server wordt verzonden.](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

Wanneer woodgrovebank.com het bericht ontvangt, als IP-adres #1 in de SPF TXT-record voor contoso.com staat, wordt het bericht doorgegeven aan de SPF-controle en is het geverifieerd.

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a>Voorbeeld 2: Vervalst afzenderadres mislukt de SPF-controle
<a name="spfExample2"> </a>

Stel dat een phisher een manier vindt om contoso.com te spoofen:

![Diagram met hoe SPF e-mail verifieert wanneer deze vanaf een vervalste server wordt verzonden.](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

Aangezien IP-adres #12 niet in contoso.com's SPF TXT-record staat, mislukt het bericht de SPF-controle en kan de ontvanger ervoor kiezen om het als spam te markeren.

### <a name="example-3-spf-and-forwarded-messages"></a>Voorbeeld 3: SPF en doorgestuurde berichten
<a name="spfExample3"> </a>

Een nadeel van SPF is dat het niet werkt wanneer een e-mail is doorgestuurd. Stel dat de gebruiker van woodgrovebank.com een doorstuurregel heeft ingesteld om alle e-mail naar een outlook.com-account te verzenden:

![Diagram dat laat zien hoe SPF e-mail niet kan verifiëren wanneer het bericht wordt doorgestuurd.](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

Het bericht passeert oorspronkelijk de SPF-controle op woodgrovebank.com, maar het mislukt de SPF-controle op outlook.com omdat IP-#25 niet in contoso.com's SPF TXT-record staat. Outlook.com kan het bericht dan markeren als spam. Gebruik SPF in combinatie met andere e-mailverificatiemethoden zoals DKIM en DMARC om dit probleem te omzeilen.

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a>SPF-basisbeginselen: domeinen van derden opnemen die namens uw domein e-mail kunnen verzenden
<a name="SPFBasicsIncludes"> </a>

Naast IP-adressen u uw SPF TXT-record ook configureren om domeinen als afzenders op te nemen. Deze worden toegevoegd aan de SPF TXT record als "include" statements. Zo wilt contoso.com bijvoorbeeld alle IP-adressen van de e-mailservers van contoso.net en contoso.org die het ook bezit, opnemen. Om dit te doen, publiceert contoso.com een SPF TXT-record die er als volgt uitziet:

```text
v=spf1 include:contoso.net include:contoso.org -all
```

Wanneer de ontvangende server deze record in DNS ziet, voert het ook een DNS-lookup uit op de SPF TXT-record voor contoso.net en vervolgens voor contoso.org. Als het vindt een extra verklaring in de records voor contoso.net of contoso.org, zal het volgen die ook. Om denial of service-aanvallen te voorkomen, is het maximum aantal DNS-lookups voor één e-mailbericht 10. Elke instructie opnemen vertegenwoordigt een extra DNS-lookup. Als een bericht de limiet van 10 overschrijdt, mislukt het bericht SPF. Zodra een bericht deze limiet bereikt, afhankelijk van de manier waarop de ontvangende server is geconfigureerd, kan de afzender een bericht ontvangen waarin staat dat het bericht "te veel opzoekingen" heeft gegenereerd of dat het "maximale hopaantal voor het bericht is overschreden" (wat kan gebeuren wanneer de lookups lus en overtreffen de DNS time-out). Zie [Probleemoplossing: Aanbevolen procedures voor SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)voor tips over hoe u dit voorkomen.

## <a name="requirements-for-your-spf-txt-record-and-office-365"></a>Vereisten voor uw SPF TXT-record en Office 365
<a name="SPFReqsinO365"> </a>

Als u e-mail instelt wanneer u Office 365 instelt, hebt u al een SPF TXT-record gemaakt waarin de Berichtenservers van Microsoft worden geïdentificeerd als een legitieme bron van e-mail voor uw domein. Deze plaat ziet er waarschijnlijk als volgt uit:

```text
v=spf1 include:spf.protection.outlook.com -all
```

Als u een volledig gehoste Office 365-klant bent, dat wil zeggen dat u geen on-premises e-mailservers hebt die uitgaande e-mail verzenden, is dit de enige SPF TXT-record die u voor Office 365 moet publiceren.

Als u een hybride implementatie hebt (dat wil zeggen dat u sommige postvakken on-premises hebt en sommige gehost in Office 365), of als u een zelfstandige klant van Exchange Online Protection (EOP) bent (dat wil zeggen dat uw organisatie EOP gebruikt om uw on-premises mailboxen te beschermen), moet u voeg het uitgaande IP-adres voor elk van uw on-premises edge mailservers toe aan de SPF TXT-record in DNS.

## <a name="form-your-spf-txt-record-for-office-365"></a>Uw SPF TXT-record voor Office 365 vormen
<a name="FormYourSPF"> </a>

Gebruik de syntaxisgegevens in dit artikel om de SPF TXT-record voor uw aangepaste domein te vormen. Hoewel er andere syntaxisopties zijn die hier niet worden genoemd, zijn dit de meest gebruikte opties. Zodra u uw record hebt gevormd, moet u de record bijwerken bij uw domeinregistrar.

Zie [Externe DNS-records](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records)die nodig zijn voor SPF voor informatie over de domeinen die u voor Office 365 moet opnemen. Gebruik de [stapsgewijze instructies](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) voor het bijwerken van SPF-records (TXT) voor uw domeinregistrar.

### <a name="spf-txt-record-syntax-for-office-365"></a>SPF TXT-recordsyntaxis voor Office 365
<a name="SPFSyntaxO365"> </a>

Een typische SPF TXT-record voor Office 365 heeft de volgende syntaxis:

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

Bijvoorbeeld:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

Waar:

- **v=spf1** is vereist. Dit definieert de TXT-record als een SPF TXT-record.

- **ip4** geeft aan dat u IP versie 4-adressen gebruikt. **ip6** geeft aan dat u IP-versie 6-adressen gebruikt. Als u IPv6 IP-adressen gebruikt, vervangt u **ip4** door **ip6** in de voorbeelden in dit artikel. U ook IP-adresbereiken opgeven met cidr-notatie, bijvoorbeeld **ip4:192.168.0.1/26**.

- _IP-adres_ is het IP-adres dat u wilt toevoegen aan de SPF TXT-record. Meestal is dit het IP-adres van de uitgaande e-mailserver voor uw organisatie. U meerdere uitgaande e-mailservers aanbieden. Zie [Voorbeeld: SPF TXT-record voor meerdere uitgaande on-premises e-mailberichten servers en Office 365 voor](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365)meer informatie.

- _domeinnaam_ is het domein dat u wilt toevoegen als legitieme afzender. Zie [Externe DNS-records die nodig zijn voor SPF](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records)voor een lijst met domeinnamen die u voor Office 365 moet opnemen.

- Handhaving regel is meestal een van de volgende:

  - -alle

    Geeft harde mislukking aan. Als u alle geautoriseerde IP-adressen voor uw domein kent, vermeldt u deze in de SPF TXT-record en gebruikt u de kwalificatie -all (hard fail). Als u alleen SPF gebruikt, dat wil zeggen dat u DMARC of DKIM niet gebruikt, moet u de kwalificatie gebruiken. We raden je aan om deze kwalificatie altijd te gebruiken.

  - ~alle

    Geeft zachte fail aan. Als u niet zeker weet dat u de volledige lijst met IP-adressen hebt, moet u de ~alle (soft fail) kwalificatie gebruiken. Ook als u DMARC met p = quarantaine of p = weigeren gebruikt, u ~allen gebruiken. Anders, gebruik -alle.

  - ?alle

    Geeft neutraal aan. Dit wordt gebruikt bij het testen van SPF. We raden je niet aan deze kwalificatie te gebruiken in je live-implementatie.

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-office-365"></a>Voorbeeld: SPF TXT-record dat moet worden gebruikt wanneer al uw e-mail wordt verzonden door Office 365
<a name="ExampleSPFNoSP"> </a>

Als al uw e-mail wordt verzonden door Office 365, gebruikt u deze in uw SPF TXT-record:

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-office-365"></a>Voorbeeld: SPF TXT-record voor een hybride scenario met één on-premises Exchange Server en Office 365
<a name="ExampleSPFHybridOneExchangeServer"> </a>

Als in een hybride omgeving het IP-adres van uw on-premises Exchange Server 192.168.0.1 is om de SPF-handhavingsregel hard te mislukken, vormt u de SPF TXT-record als volgt:

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-office-365"></a>Voorbeeld: SPF TXT-record voor meerdere uitgaande on-premises e-mailberichten servers en Office 365
<a name="ExampleSPFMultipleMailServerO365"> </a>

Als u meerdere uitgaande e-mailservers hebt, neemt u het IP-adres voor elke e-mailserver op in de SPF TXT-record en scheidt u elk IP-adres met een spatie, gevolgd door een "ip4:"-instructie. Bijvoorbeeld:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-office-365"></a>Volgende stappen: SPF instellen voor Office 365
<a name="SPFNextSteps"> </a>

Nadat u uw SPF TXT-record hebt geformuleerd, volgt u de stappen in [SPF instellen in Office 365 om te voorkomen dat spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) deze aan uw domein toevoegt.

Hoewel SPF is ontworpen om spoofing te voorkomen, maar er zijn spoofing technieken die SPF niet kan beschermen tegen. Om deze te beschermen, moet u, zodra u SPF hebt ingesteld, ook DKIM en DMARC configureren voor Office 365. Zie [DKIM gebruiken om uitgaande e-mail te valideren die vanuit uw aangepaste domein in Office 365 is verzonden.](use-dkim-to-validate-outbound-email.md) Zie [Vervolgens DMARC gebruiken om e-mail te valideren in Office 365](use-dmarc-to-validate-email.md).

## <a name="troubleshooting-best-practices-for-spf-in-office-365"></a>Probleemoplossing: aanbevolen procedures voor SPF in Office 365
<a name="SPFTroubleshoot"> </a>

U slechts één SPF TXT-record maken voor uw aangepaste domein. Het maken van meerdere records veroorzaakt een ronde robin situatie en SPF zal mislukken. Om dit te voorkomen, u afzonderlijke records maken voor elk subdomein. Maak bijvoorbeeld één record voor contoso.com en een andere record voor bulkmail.contoso.com.

Als een e-mailbericht meer dan 10 DNS-opzoekingen veroorzaakt voordat het wordt geleverd, reageert de ontvangende e-mailserver met een permanente fout, ook wel een _permerror_genoemd, en zorgt ervoor dat het bericht niet voldoet aan de SPF-controle. De ontvangende server kan ook reageren met een ndr (non-delivery report) die een fout bevat die vergelijkbaar is met deze:

- Het bericht overschreed het hopaantal.

- Het bericht vereiste te veel lookups.

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-office-365"></a>De fout 'te veel opzoekingen' vermijden wanneer u domeinen van derden gebruikt met Office 365
<a name="SPFTroubleshoot"> </a>

Sommige SPF TXT-records voor domeinen van derden leiden de ontvangende server ertoe een groot aantal DNS-lookups uit te voeren. Op het moment van schrijven bevat Salesforce.com bijvoorbeeld 5 verklaringen in zijn dossier:

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

Om de fout te voorkomen, u een beleid implementeren waarbij iedereen die bijvoorbeeld bulke-mail verzendt, speciaal voor dit doel een subdomein moet gebruiken. Vervolgens definieert u een andere SPF TXT-record voor het subdomein dat de bulke-mail bevat.

 In sommige gevallen, zoals het salesforce.com voorbeeld, moet u het domein in uw SPF TXT-record gebruiken, maar in andere gevallen heeft de derde partij mogelijk al een subdomein voor u gemaakt om voor dit doel te gebruiken. Exacttarget.com heeft bijvoorbeeld een subdomein gemaakt dat u moet gebruiken voor uw SPF TXT-record:

```text
cust-spf.exacttarget.com
```

Wanneer u domeinen van derden opneemt in uw SPF TXT-record, moet u met de derde partij bevestigen welk domein of subdomein moet worden gebruikt om te voorkomen dat u de opzoeklimiet van 10 tegenkomt.

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a>Hoe bekijk je je huidige SPF TXT-record en bepaal je het aantal opzoekingen dat nodig is
<a name="SPFTroubleshoot"> </a>

U nslookup gebruiken om uw DNS-records te bekijken, inclusief uw SPF TXT-record. Of, als u dat liever hebt, zijn er een aantal gratis, online tools beschikbaar die u gebruiken om de inhoud van uw SPF TXT-record te bekijken. Door te kijken naar uw SPF TXT record en het volgen van de keten van include verklaringen en omleidingen, u bepalen hoeveel DNS lookups de record vereist. Sommige online tools tellen en geven deze lookups zelfs voor u weer. Als u dit nummer bijhoudt, voorkomt u dat berichten die vanuit uw organisatie worden verzonden, een permanente fout, een zogenaamde permerror, van de ontvangende server activeren.

## <a name="for-more-information"></a>Voor meer informatie
<a name="SPFTroubleshoot"> </a>

Hulp nodig bij het toevoegen van de SPF TXT-record? Lees het artikel [DNS-records maken bij elke DNS-hostingprovider voor Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) voor gedetailleerde informatie over het gebruik van Sender Policy Framework met uw aangepaste domein in Office 365. [Anti-spamberichtkoppen](anti-spam-message-headers.md) bevatten de syntaxis- en kopvelden die door Office 365 worden gebruikt voor SPF-controles.


