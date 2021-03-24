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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Lees hoe Microsoft 365 de TXT-record (Sender Policy Framework) in DNS gebruikt om ervoor te zorgen dat doel-e-mailsystemen berichten vertrouwen die zijn verzonden vanuit uw aangepaste domein.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 972f283f6138bafcebd877a19f0bfc429e0eed03
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057942"
---
# <a name="how-microsoft-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a>Hoe Microsoft 365 SPF (Sender Policy Framework) gebruikt om adresvervalsing te voorkomen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

 **Overzicht:** In dit artikel wordt beschreven hoe Microsoft 365 de TXT-record (Sender Policy Framework) in DNS gebruikt om ervoor te zorgen dat doel-e-mailsystemen berichten vertrouwen die zijn verzonden vanuit uw aangepaste domein. Dit geldt voor uitgaande e-mail die is verzonden vanuit Microsoft 365. Berichten die van Microsoft 365 naar een geadresseerde binnen Microsoft 365 worden verzonden, worden altijd door SPF verzonden.

Een SPF TXT-record is een DNS-record die spoofing en phishing helpt voorkomen door de domeinnaam te verifiëren waaruit e-mailberichten worden verzonden. SPF valideert de oorsprong van e-mailberichten door het IP-adres van de afzender te verifiëren ten opzichte van de vermeende eigenaar van het verzendende domein.

> [!NOTE]
> SPF-recordtypen zijn in 2014 afgeschaft door de Internet Engineering Task Force (IETF). Zorg er in plaats daarvan voor dat u TXT-records in DNS gebruikt om uw SPF-gegevens te publiceren. De rest van dit artikel gebruikt de term SPF TXT-record voor duidelijkheid.

Domeinbeheerders publiceren SPF-informatie in TXT-records in DNS. De SPF-informatie identificeert geautoriseerde uitgaande e-mailservers. Doel-e-mailsystemen controleren of berichten afkomstig zijn van geautoriseerde uitgaande e-mailservers. Als u al bekend bent met SPF of als u een eenvoudige implementatie hebt en alleen wilt weten wat u moet opnemen in uw SPF TXT-record in DNS voor Microsoft 365, kunt u naar [SPF instellen in Microsoft 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md)gaan om spoofing te voorkomen. Als u geen implementatie hebt die volledig wordt gehost in Microsoft 365, of als u meer informatie wilt over hoe SPF werkt of hoe u SPF voor Microsoft 365 kunt oplossen, blijft u lezen.

> [!NOTE]
> Voorheen moest u een andere SPF TXT-record toevoegen aan uw aangepaste domein als u ook SharePoint Online hebt gebruikt. Dit is niet meer nodig. Deze wijziging moet het risico verkleinen dat SharePoint Online-meldingsberichten in de map Ongewenste e-mail terechtkomen. U hoeft niet onmiddellijk wijzigingen aan te brengen, maar als u de fout 'te veel zoekactie' ontvangt, wijzigt u de SPF TXT-record zoals beschreven [in SPF instellen in Microsoft 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md)om spoofing te voorkomen.

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-microsoft-365"></a>Hoe SPF werkt om spoofing en phishing te voorkomen in Microsoft 365
<a name="HowSPFWorks"> </a>

SPF bepaalt of een afzender namens een domein mag verzenden. Als dit niet is toegestaan voor de afzender, dat wil zeggen als de E-mail de SPF-controle op de ontvangende server mislukt, bepaalt het spambeleid dat op die server is geconfigureerd, wat er met het bericht moet worden uitgevoerd.

Elke SPF TXT-record bevat drie onderdelen: de declaratie dat het een SPF TXT-record is, de IP-adressen die e-mail mogen verzenden vanuit uw domein en de externe domeinen die namens uw domein kunnen worden verzonden, en een afdwingingsregel. U hebt alle drie nodig in een geldige SPF TXT-record. In dit artikel wordt beschreven hoe u uw SPF TXT-record vormt en worden best practices beschreven voor het werken met de services in Microsoft 365. Koppelingen naar instructies voor het werken met uw domeinregistrar voor het publiceren van uw record naar DNS worden ook verstrekt.

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a>Basisprincipes van SPF: IP-adressen die mogen worden verzenden vanuit uw aangepaste domein
<a name="SPFBasicsIPaddresses"> </a>

Bekijk de basis syntaxis voor een SPF-regel:

v=spf1 \<IP\>\<enforcement rule\>

Stel dat de volgende SPF-regel bestaat voor contoso.com:

v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\>\<enforcement rule\>

In dit voorbeeld geeft de SPF-regel de ontvangende e-mailserver de opdracht alleen e-mail van deze IP-adressen te accepteren voor het domein contoso.com:

- IP-adres #1

- IP-adres #2

- IP-adres #3

Deze SPF-regel geeft de ontvangende e-mailserver aan dat als een bericht afkomstig is van contoso.com, maar niet van een van deze drie IP-adressen, de ontvangende server de afdwingingsregel op het bericht moet toepassen. De afdwingingsregel is meestal een van de volgende opties:

- **Hard fail.** Markeer het bericht met 'hard fail' in de bericht envelop en volg vervolgens het geconfigureerde spambeleid van de ontvangende server voor dit type bericht.

- **Soft fail.** Markeer het bericht met 'soft fail' in de envelop van het bericht. Meestal zijn e-mailservers zo geconfigureerd dat deze berichten toch worden verzonden. De meeste eindgebruikers zien dit merk niet.

- **Neutraal.** Niets doen, dat wil zeggen, markeer de berichtvelop niet. Dit is meestal gereserveerd voor testdoeleinden en wordt zelden gebruikt.

In de volgende voorbeelden kunt u zien hoe SPF in verschillende situaties werkt. In deze voorbeelden is contoso.com afzender en woodgrovebank.com de ontvanger.

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a>Voorbeeld 1: E-mailverificatie van een bericht dat rechtstreeks van afzender naar ontvanger wordt verzonden
<a name="spfExample1"> </a>

SPF werkt het beste wanneer het pad van afzender naar ontvanger direct is, bijvoorbeeld:

![Diagram met de manier waarop E-mail door SPF wordt geverifieerd wanneer deze rechtstreeks van server naar server wordt verzonden.](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

Wanneer woodgrovebank.com het bericht ontvangt en het IP-adres #1 zich in de SPF TXT-record voor contoso.com, wordt het bericht door de SPF-controle uitgevoerd en wordt het geverifieerd.

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a>Voorbeeld 2: Adres van vervalste afzender mislukt de SPF-controle
<a name="spfExample2"> </a>

Stel dat een phisher een manier vindt om spoofing contoso.com:

![Diagram met de manier waarop E-mail door SPF wordt geverifieerd wanneer deze vanaf een vervalste server wordt verzonden.](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

Aangezien IP-adres #12 niet in de SPF TXT-record van contoso.com staat, mislukt het bericht de SPF-controle en kan de ontvanger ervoor kiezen om het te markeren als spam.

### <a name="example-3-spf-and-forwarded-messages"></a>Voorbeeld 3: SPF en doorgestuurde berichten
<a name="spfExample3"> </a>

Een nadeel van SPF is dat het niet werkt wanneer een e-mailbericht is doorgestuurd. Stel dat de gebruiker op woodgrovebank.com een doorsturende regel heeft ingesteld om alle e-mail naar een account outlook.com verzenden:

![Diagram met de manier waarop SPF e-mail niet kan verifiëren wanneer het bericht wordt doorgestuurd.](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

Het bericht wordt oorspronkelijk door de SPF-controle bij woodgrovebank.com uitgevoerd, maar de SPF-controle bij outlook.com mislukt omdat IP-#25 niet in de SPF TXT-record van contoso.com staat. Outlook.com kan het bericht vervolgens markeren als spam. Als u dit probleem wilt omzeilen, gebruikt u SPF in combinatie met andere methoden voor e-mailverificatie, zoals DKIM en DMARC.

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a>SPF-basisbeginselen: Inclusief domeinen van derden die e-mail namens uw domein kunnen verzenden
<a name="SPFBasicsIncludes"> </a>

Naast IP-adressen kunt u ook uw SPF TXT-record zo configureren dat domeinen als afzenders worden gebruikt. Deze worden toegevoegd aan de SPF TXT-record als 'include'-instructies. U kunt contoso.com alle IP-adressen van de e-mailservers opnemen van contoso.net en contoso.org waarvan de e-mailserver ook de eigenaar is. U kunt dit doen door contoso.com SPF TXT-record te publiceren die er als volgende uitziet:

```text
v=spf1 include:contoso.net include:contoso.org -all
```

Wanneer de ontvangende server deze record in DNS ziet, wordt ook een DNS-opzoekactie uitgevoerd op de SPF TXT-record voor contoso.net en vervolgens voor contoso.org. Als er een aanvullende instructie voor opnemen in de records wordt gevonden voor contoso.net of contoso.org, volgt deze ook. Om denial of service-aanvallen te voorkomen, is het maximum aantal DNS-opzoekingen voor één e-mailbericht 10. Elke instructie include vertegenwoordigt een extra DNS-opzoekactie. Als een bericht de limiet van 10 overschrijdt, mislukt het bericht SPF. Zodra een bericht deze limiet heeft bereikt, kan de afzender, afhankelijk van de manier waarop de ontvangende server is geconfigureerd, een bericht ontvangen met de melding dat het bericht 'te veel opzoekingen' heeft gegenereerd of dat het 'maximum aantal hops voor het bericht is overschreden' (dat kan gebeuren wanneer de opzoekingen de DNS-time-out overschrijden). Zie [Probleemoplossing: Best practices voor SPF in Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)voor tips over hoe u dit kunt voorkomen.

## <a name="requirements-for-your-spf-txt-record-and-microsoft-365"></a>Vereisten voor uw SPF TXT-record en Microsoft 365
<a name="SPFReqsinO365"> </a>

Als u e-mail in stelt bij het instellen van Microsoft 365, hebt u al een SPF TXT-record gemaakt die de Microsoft-berichtenservers identificeert als een legitieme bron van e-mail voor uw domein. Deze record ziet er waarschijnlijk als volgende uit:

```text
v=spf1 include:spf.protection.outlook.com -all
```

Als u een volledig gehoste klant bent, dat wil zeggen dat u geen on-premises e-mailservers hebt die uitgaande e-mail verzenden, is dit de enige SPF TXT-record die u moet publiceren voor Office 365.

Als u een hybride implementatie hebt (dat wil zeggen, u hebt een aantal postvakken on-premises en sommige gehost in Microsoft 365) of als u een zelfstandige EOP-klant bent (dat wil zeggen dat uw organisatie EOP gebruikt om uw on-premises postvakken te beschermen), moet u het uitgaande IP-adres voor elk van uw on-premises edge mailservers toevoegen aan de SPF TXT-record in DNS.

## <a name="form-your-spf-txt-record-for-microsoft-365"></a>Uw SPF TXT-record voor Microsoft 365 maken
<a name="FormYourSPF"> </a>

Gebruik de syntaxisgegevens in dit artikel om de SPF TXT-record voor uw aangepaste domein te vormen. Hoewel er andere syntaxisopties zijn die hier niet worden vermeld, zijn dit de meest gebruikte opties. Wanneer u het record hebt gemaakt, moet u het record bij uw domeinregistrar bijwerken.

Zie Externe [DNS-records](../../enterprise/external-domain-name-system-records.md)vereist voor SPF voor informatie over de domeinen die u moet opnemen voor Microsoft 365. Gebruik de [stapsgewijse instructies voor](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) het bijwerken van SPF-records (TXT) voor uw domeinregistrar.

### <a name="spf-txt-record-syntax-for-microsoft-365"></a>Syntaxis van SPF TXT-record voor Microsoft 365
<a name="SPFSyntaxO365"> </a>

Een normale SPF TXT-record voor Microsoft 365 heeft de volgende syntaxis:

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

Bijvoorbeeld:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

waarbij:

- **v=spf1** is vereist. Hiermee wordt de TXT-record definieert als een SPF TXT-record.

- **ip4** geeft aan dat u IP versie 4-adressen gebruikt. **ip6** geeft aan dat u IP-adressen van versie 6 gebruikt. Als u IPv6-IP-adressen gebruikt, vervangt u **ip4** door **ip6** in de voorbeelden in dit artikel. U kunt ook IP-adresbereiken opgeven met cidr-notatie, bijvoorbeeld **ip4:192.168.0.1/26.**

- _IP-adres_ is het IP-adres dat u wilt toevoegen aan de SPF TXT-record. Meestal is dit het IP-adres van de uitgaande e-mailserver voor uw organisatie. U kunt meerdere uitgaande e-mailservers op een lijst zetten. Zie [Voorbeeld: SPF TXT-record voor meerdere uitgaande on-premises e-mailservers en Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365)voor meer informatie.

- _domeinnaam_ is het domein dat u wilt toevoegen als een legitieme afzender. Zie Externe [DNS-records](../../enterprise/external-domain-name-system-records.md)die vereist zijn voor SPF voor een lijst met domeinnamen die u voor Microsoft 365 moet opnemen.

- Handhavingsregel is meestal een van de volgende:

  - -all

    Geeft hard fail aan. Als u alle geautoriseerde IP-adressen voor uw domein kent, vermeldt u deze in de SPF TXT-record en gebruikt u de kwalificatie -all (hard fail). Als u alleen SPF gebruikt, dat wil zeggen dat u geen DMARC of DKIM gebruikt, moet u de -all qualifier gebruiken. U wordt aangeraden deze kwalificatie altijd te gebruiken.

  - ~all

    Geeft soft fail aan. Als u niet zeker weet of u de volledige lijst met IP-adressen hebt, moet u de kwalificatie ~all (soft fail) gebruiken. Als u ook DMARC gebruikt met p=quarantaine of p=reject, kunt u ~all gebruiken. Anders gebruikt u -all.

  - ?all

    Geeft neutraal aan. Dit wordt gebruikt bij het testen van SPF. We raden u af deze kwalificatie te gebruiken in uw live-implementatie.

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-microsoft-365"></a>Voorbeeld: SPF TXT-record die u kunt gebruiken wanneer al uw e-mail wordt verzonden door Microsoft 365
<a name="ExampleSPFNoSP"> </a>

Als al uw e-mail wordt verzonden door Microsoft 365, gebruikt u dit in uw SPF TXT-record:

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-microsoft-365"></a>Voorbeeld: SPF TXT-record voor een hybride scenario met één on-premises Exchange Server en Microsoft 365
<a name="ExampleSPFHybridOneExchangeServer"> </a>

Als in een hybride omgeving het IP-adres van uw on-premises Exchange Server 192.168.0.1 is, vormt u de SPF TXT-record als volgt om de SPF-afdwingingsregel in te stellen:

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-microsoft-365"></a>Voorbeeld: SPF TXT-record voor meerdere uitgaande on-premises e-mailservers en Microsoft 365
<a name="ExampleSPFMultipleMailServerO365"> </a>

Als u meerdere uitgaande e-mailservers hebt, moet u het IP-adres voor elke e-mailserver opnemen in de SPF TXT-record en elk IP-adres scheiden met een spatie gevolgd door een ip4:-instructie. Bijvoorbeeld:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-microsoft-365"></a>Volgende stappen: SPF instellen voor Microsoft 365
<a name="SPFNextSteps"> </a>

Nadat u uw SPF TXT-record hebt geformuleerd, volgt u de stappen [in SPF instellen in Microsoft 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md) om spoofing te voorkomen om deze toe te voegen aan uw domein.

Hoewel SPF is ontworpen om spoofing te voorkomen, zijn er echter spoofingtechnieken die SPF niet kan beschermen. Als u zich hiertegen wilt beschermen, moet u na het instellen van SPF ook DKIM en DMARC voor Microsoft 365 configureren. Zie DKIM gebruiken om uitgaande e-mail te valideren die is verzonden vanuit uw [aangepaste domein in Microsoft 365](use-dkim-to-validate-outbound-email.md)om aan de slag te gaan. Zie vervolgens [DMARC gebruiken om e-mail in Microsoft 365 te valideren](use-dmarc-to-validate-email.md).

## <a name="troubleshooting-best-practices-for-spf-in-microsoft-365"></a>Probleemoplossing: Best practices voor SPF in Microsoft 365
<a name="SPFTroubleshoot"> </a>

U kunt slechts één SPF TXT-record maken voor uw aangepaste domein. Als u meerdere records maakt, is er een situatie met een ronde roodborstje en SPF mislukt. U kunt dit voorkomen door afzonderlijke records te maken voor elk subdomein. Maak bijvoorbeeld één record voor contoso.com en een andere record voor bulkmail.contoso.com.

Als een e-mailbericht meer dan 10 DNS-opzoekingen veroorzaakt voordat het wordt bezorgd, reageert de ontvangende e-mailserver met een permanente fout, ook wel  _een permerror_ genoemd, en mislukt het bericht bij de SPF-controle. De ontvangende server kan ook reageren met een rapport over niet-bezorging (NDR) dat een fout bevat die vergelijkbaar is met deze:

- Het bericht heeft het aantal hop overschreden.

- Het bericht vereist te veel opzoekingen.

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-microsoft-365"></a>De fout 'te veel zoekactie' vermijden wanneer u domeinen van derden gebruikt met Microsoft 365
<a name="SPFTroubleshoot"> </a>

Sommige SPF TXT-records voor domeinen van derden leiden de ontvangende server naar een groot aantal DNS-opzoekingen. Op het moment van schrijven bevat Salesforce.com bijvoorbeeld 5 instructies in de record:

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

Om de fout te voorkomen, kunt u een beleid implementeren waarbij iedereen die bulk-e-mail verstuurt, bijvoorbeeld een subdomein speciaal voor dit doel moet gebruiken. Vervolgens definieert u een andere SPF TXT-record voor het subdomein dat de bulk-e-mail bevat.

 In sommige gevallen, zoals het salesforce.com voorbeeld, moet u het domein in uw SPF TXT-record gebruiken, maar in andere gevallen heeft de derde partij mogelijk al een subdomein gemaakt dat u voor dit doel kunt gebruiken. U hebt bijvoorbeeld exacttarget.com subdomein gemaakt dat u moet gebruiken voor uw SPF TXT-record:

```text
cust-spf.exacttarget.com
```

Wanneer u domeinen van derden opstelt in uw SPF TXT-record, moet u met de externe partij bevestigen welk domein of subdomein u wilt gebruiken om te voorkomen dat de limiet van 10 opzoeklimieten wordt overschreden.

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a>Uw huidige SPF TXT-record weergeven en het aantal opzoekingen bepalen dat hiervoor nodig is
<a name="SPFTroubleshoot"> </a>

U kunt nslookup gebruiken om uw DNS-records weer te geven, inclusief uw SPF TXT-record. U kunt ook een aantal gratis onlinehulpmiddelen gebruiken om de inhoud van uw SPF TXT-record weer te geven. Door uw SPF TXT-record te bekijken en de keten van inclusief instructies en omleidingen te volgen, kunt u bepalen hoeveel DNS-opzoekingen de record vereist. Sommige onlinehulpprogramma's tellen deze opzoekprogramma's zelfs en geven deze voor u weer. Als u dit nummer bij houdt, voorkomt u dat berichten die vanuit uw organisatie worden verzonden, een permanente fout van de ontvangende server veroorzaken.

## <a name="for-more-information"></a>Voor meer informatie
<a name="SPFTroubleshoot"> </a>

Hulp nodig bij het toevoegen van de SPF TXT-record? Lees het artikel DNS-records maken bij een [DNS-hostingprovider voor Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) voor gedetailleerde informatie over het gebruik van Sender Policy Framework met uw aangepaste domein in Microsoft 365. [Antispamberichtkoppen bevatten](anti-spam-message-headers.md) de syntaxis- en koptekstvelden die door Microsoft 365 worden gebruikt voor SPF-controles.
