---
title: Hoe SPF (Sender Policy Framework) spoofing voorkomt
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
description: Meer informatie over hoe Microsoft 365 de TXT-record (Sender Policy Framework) in DNS gebruikt om ervoor te zorgen dat doel-e-mailsystemen berichten vertrouwen die vanuit uw aangepaste domein worden verzonden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b6b79957f84e660fe952f88dab18d8934937d875
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167525"
---
# <a name="how-microsoft-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a>Hoe Microsoft 365 SPF (Sender Policy Framework) gebruikt om adresvervalsing te voorkomen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

 **Overzicht:** In dit artikel wordt beschreven hoe Microsoft 365 de TXT-record (Sender Policy Framework) in DNS gebruikt om ervoor te zorgen dat de doel-e-mailsystemen berichten vertrouwen die vanuit uw aangepaste domein worden verzonden. Dit geldt voor uitgaande e-mail die wordt verzonden vanuit Microsoft 365. Berichten die van Microsoft 365 naar een ontvanger binnen Microsoft 365 worden verzonden, worden altijd door SPF verzonden.

Een SPF TXT-record is een DNS-record die spoofing en phishing helpt voorkomen door de domeinnaam te verifiëren waaruit e-mailberichten worden verzonden. SPF valideert de oorsprong van e-mailberichten door het IP-adres van de afzender te verifiëren ten opzichte van de zogenaamde eigenaar van het verzendende domein.

> [!NOTE]
> SPF-recordtypen zijn in 2014 afgeschaft door IETF (Internet Engineering Task Force). Zorg er in plaats daarvan voor dat u TXT-records in DNS gebruikt om uw SPF-gegevens te publiceren. In de rest van dit artikel wordt de term SPF TXT-record gebruikt voor duidelijkheid.

Domeinbeheerders publiceren SPF-gegevens in TXT-records in DNS. De SPF-informatie identificeert geautoriseerde uitgaande e-mailservers. Doel-e-mailsystemen controleren of berichten afkomstig zijn van geautoriseerde uitgaande e-mailservers. Als u al bekend bent met SPF of als u een eenvoudige implementatie hebt, en alleen wilt weten wat u in uw SPF TXT-record moet opnemen in DNS voor Microsoft 365, gaat u naar [SPF instellen in Microsoft 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md)om spoofing te helpen voorkomen. Lees verder als u geen implementatie hebt die volledig wordt gehost in Microsoft 365, of als u meer informatie wilt over hoe SPF werkt of hoe u problemen met SPF voor Microsoft 365 kunt oplossen.

> [!NOTE]
> Voorheen moest u een andere SPF TXT-record toevoegen aan uw aangepaste domein als u ook SharePoint Online gebruikte. Dit is niet meer nodig. Deze wijziging moet het risico verkleinen dat SharePoint Online-meldingsberichten in de map Ongewenste e-mail terechtkomen. U hoeft niet onmiddellijk wijzigingen aan te brengen, maar als de fout 'te veel zoekactie' wordt weergegeven, wijzigt u de SPF TXT-record zoals beschreven [in SPF instellen in Microsoft 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md)om spoofing te helpen voorkomen.

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-microsoft-365"></a>Hoe SPF werkt om spoofing en phishing in Microsoft 365 te voorkomen
<a name="HowSPFWorks"> </a>

SPF bepaalt of het een afzender is toegestaan om namens een domein te verzenden. Als dit niet is toegestaan voor de afzender, dat wil zeggen als de e-mail niet door de SPF-controle op de ontvangende server wordt nagelaten, bepaalt het spambeleid dat op die server is geconfigureerd wat er met het bericht moet worden gebeurd.

Elke SPF TXT-record bevat drie onderdelen: de declaratie dat het een SPF TXT-record is, de IP-adressen die e-mail mogen verzenden vanaf uw domein en de externe domeinen die namens uw domein kunnen worden verzonden, en een regel voor het afdwingen van e-mail. U hebt alle drie nodig in een geldige SPF TXT-record. In dit artikel wordt beschreven hoe u uw SPF TXT-record vormt en vindt u best practices voor het werken met de services in Microsoft 365. Er worden ook koppelingen naar instructies gegeven voor het samenwerken met uw domeinregistrar om uw record te publiceren naar DNS.

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a>SPF-basisprincipes: IP-adressen die zijn toegestaan om te verzenden vanuit uw aangepaste domein
<a name="SPFBasicsIPaddresses"> </a>

Bekijk de basissyntaxis voor een SPF-regel:

v=spf1 \<IP\>\<enforcement rule\>

Stel dat de volgende SPF-regel bestaat voor contoso.com:

v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\>\<enforcement rule\>

In dit voorbeeld geeft de SPF-regel aan dat de ontvangende e-mailserver alleen e-mail van deze IP-adressen mag accepteren voor het contoso.com:

- IP-adres #1

- IP-adres #2

- IP-adres #3

Met deze SPF-regel weet de ontvangende e-mailserver dat als een bericht afkomstig is van contoso.com, maar niet van een van deze drie IP-adressen, de ontvangende server de regel voor het afdwingen op het bericht moet toepassen. De regel voor het afdwingen is meestal een van de volgende opties:

- **Mislukt.** Markeer het bericht met 'mislukt' in de berichtvelop en volg het geconfigureerde spambeleid van de ontvangende server voor dit type bericht.

- **Mislukt zacht.** Markeer het bericht met 'mislukt' in de berichtvelop. E-mailservers zijn meestal toch geconfigureerd voor het bezorgen van deze berichten. De meeste eindgebruikers zien dit markering niet.

- **Neutraal.** Doe niets, dat wil zeggen, markeer de berichtvelop niet. Deze is meestal gereserveerd voor testdoeleinden en wordt zelden gebruikt.

De volgende voorbeelden laten zien hoe SPF werkt in verschillende situaties. In deze voorbeelden is contoso.com de afzender en woodgrovebank.com de ontvanger is.

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a>Voorbeeld 1: E-mailverificatie van een bericht dat rechtstreeks van afzender naar ontvanger is verzonden
<a name="spfExample1"> </a>

SPF werkt het beste wanneer het pad van afzender naar ontvanger direct is, bijvoorbeeld:

![Diagram waarin wordt getoond hoe SPF e-mail verifieert wanneer deze rechtstreeks van server naar server wordt verzonden.](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

Wanneer woodgrovebank.com het bericht ontvangt en het IP-adres #1 in de SPF TXT-record voor contoso.com staat, wordt de SPF-controle uitgevoerd en wordt het geverifieerd.

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a>Voorbeeld 2: Adres van vervalste afzender mislukt tijdens de SPF-controle
<a name="spfExample2"> </a>

Stel dat een phisher een manier vindt om e-contoso.com:

![Diagram waarin wordt getoond hoe SPF e-mail verifieert wanneer deze wordt verzonden vanaf een vervalste server.](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

Aangezien het IP-adres #12 niet in de SPF TXT-record van contoso.com staat, mislukt de SPF-controle voor het bericht en kan de ontvanger ervoor kiezen het als spam te markeren.

### <a name="example-3-spf-and-forwarded-messages"></a>Voorbeeld 3: SPF en doorgestuurde berichten
<a name="spfExample3"> </a>

Een nadeel van SPF is dat het niet werkt wanneer een e-mailbericht is doorgestuurd. Stel bijvoorbeeld dat de gebruiker van woodgrovebank.com een doorsturenregel heeft ingesteld om alle e-mailberichten naar een ander outlook.com verzenden:

![Diagram waarin wordt getoond hoe SPF geen e-mail kan verifiëren wanneer het bericht wordt doorgestuurd.](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

Het bericht passeert oorspronkelijk de SPF-controle bij woodgrovebank.com, maar de SPF-controle bij outlook.com mislukt omdat IP #25 niet in de SPF TXT-record van contoso.com staat. Outlook.com kan het bericht vervolgens markeren als spam. U kunt dit probleem omzeilen door SPF in combinatie met andere methoden voor e-mailverificatie, zoals DKIM en DMARC, te gebruiken.

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a>Basisprincipes van SPF: Inclusief domeinen van derden die e-mail kunnen verzenden namens uw domein
<a name="SPFBasicsIncludes"> </a>

Naast IP-adressen kunt u ook uw SPF TXT-record zo configureren dat domeinen als afzenders worden gebruikt. Deze worden toegevoegd aan de SPF TXT-record als 'include'-instructies. Zo wilt contoso.com mogelijk alle IP-adressen van de e-mailservers van uw contoso.net en contoso.org ook eigenaar zijn. U doet dit door contoso.com SPF TXT-record te publiceren die er als volgende uitziet:

```text
v=spf1 include:contoso.net include:contoso.org -all
```

Wanneer de ontvangende server deze record in DNS ziet, wordt ook een DNS-zoekactie uitgevoerd op de SPF TXT-record voor contoso.net en vervolgens voor contoso.org. Als er een extra instructie include wordt gevonden in de records voor contoso.net of contoso.org, volgen die ook die. Om Denial of Service-aanvallen te helpen voorkomen, is het maximum aantal DNS-zoekactieen voor één e-mailbericht 10. Elke include-instructie vertegenwoordigt een extra DNS-zoekactie. Als een bericht de limiet van 10 overschrijdt, mislukt het bericht SPF. Wanneer een bericht deze limiet bereikt, kan de afzender, afhankelijk van de manier waarop de ontvangende server is geconfigureerd, een bericht krijgen dat het bericht 'te veel zoekactie' is gegenereerd of dat het maximumaantal hops voor het bericht is overschreden (wat kan gebeuren wanneer de zoekactie meer en groter wordt dan de DNS-time-out). Zie Probleemoplossing: Best practices voor [SPF in Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)voor tips om dit te voorkomen.

## <a name="requirements-for-your-spf-txt-record-and-microsoft-365"></a>Vereisten voor uw SPF TXT-record en Microsoft 365
<a name="SPFReqsinO365"> </a>

Als u e-mail in stelt bij het instellen van Microsoft 365, hebt u al een SPF TXT-record gemaakt die de microsoft-berichtservers identificeert als een legitieme e-mailbron voor uw domein. Deze record ziet er waarschijnlijk zo uit:

```text
v=spf1 include:spf.protection.outlook.com -all
```

Als u een volledig gehoste klant bent, dat wil zeggen dat u geen on-premises e-mailservers hebt die uitgaande e-mail verzenden, is dit de enige SPF TXT-record die u moet publiceren voor Office 365.

Als u een hybride implementatie hebt (dat wil zeggen, u hebt een aantal postvakken on-premises en andere gehost in Microsoft 365), of als u een zelfstandige klant van Exchange Online Protection (EOP) bent (uw organisatie maakt gebruik van EOP om uw on-premises postvakken te beveiligen), moet u het uitgaande IP-adres voor elk van uw on-premises rand-e-mailservers toevoegen aan de SPF TXT-record in DNS.

## <a name="form-your-spf-txt-record-for-microsoft-365"></a>De SPF TXT-record voor Microsoft 365 vormen
<a name="FormYourSPF"> </a>

Gebruik de syntaxisinformatie in dit artikel om de SPF TXT-record voor uw aangepaste domein te vormen. Hoewel er andere syntaxisopties zijn die hier niet worden vermeld, zijn dit de meest gebruikte opties. Wanneer u het record hebt gemaakt, moet u het record bij uw domeinregistrar bijwerken.

Zie Externe [DNS-records](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)die vereist zijn voor SPF voor informatie over de domeinen die u moet opnemen voor Microsoft 365. Gebruik de [stapsgewijste instructies voor het](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) bijwerken van SPF-records (TXT) voor uw domeinregistrar.

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

- **v=spf1** is vereist. Hiermee definieert u de TXT-record als een SPF TXT-record.

- **ip4** geeft aan dat u ip-versie 4-adressen gebruikt. **ip6 geeft** aan dat u ip-versie 6-adressen gebruikt. Als u IPv6-IP-adressen gebruikt, vervangt u **ip4** door **ip6** in de voorbeelden in dit artikel. U kunt ook IP-adresbereiken opgeven met CIDR-notatie, bijvoorbeeld **ip4:192.168.0.1/26.**

- _Het IP-adres_ is het IP-adres dat u wilt toevoegen aan de SPF TXT-record. Dit is meestal het IP-adres van de uitgaande e-mailserver voor uw organisatie. U kunt meerdere uitgaande e-mailservers op een lijst zetten. Zie voorbeeld: [SPF TXT-record voor meerdere uitgaande on-premises e-mailservers en Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365)voor meer informatie.

- _domeinnaam_ is het domein dat u wilt toevoegen als een legitieme afzender. Zie Externe [DNS-records](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)die vereist zijn voor SPF voor een lijst met domeinnamen die u moet opnemen voor Microsoft 365.

- Regel voor afdwingen is meestal een van de volgende:

  - -all

    Geeft een harde fail aan. Als u alle geautoriseerde IP-adressen voor uw domein kent, vermeldt u deze in de SPF TXT-record en gebruikt u de kwalificatie -all (hard fail). Als u alleen SPF gebruikt, dus niet DMARC of DKIM, moet u de kwalificatie -all gebruiken. U wordt aangeraden altijd deze kwalificatie te gebruiken.

  - ~all

    Geeft aan dat de fout niet goed is. Als u niet zeker weet of u de volledige lijst met IP-adressen hebt, moet u de kwalificatie ~all (soft fail) gebruiken. Als u DMARC gebruikt met p=quarantaine of p=reject, kunt u ook ~all gebruiken. Anders gebruikt u -all.

  - ?all

    Geeft neutraal aan. Dit wordt gebruikt bij het testen van SPF. U wordt aangeraden deze kwalificaties niet te gebruiken in uw live implementatie.

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-microsoft-365"></a>Voorbeeld: SPF TXT-record voor gebruik wanneer al uw e-mail wordt verzonden door Microsoft 365
<a name="ExampleSPFNoSP"> </a>

Als al uw e-mailberichten door Microsoft 365 worden verzonden, gebruikt u deze in uw SPF TXT-record:

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-microsoft-365"></a>Voorbeeld: SPF TXT-record voor een hybride scenario met één on-premises Exchange Server en Microsoft 365
<a name="ExampleSPFHybridOneExchangeServer"> </a>

Als in een hybride omgeving het IP-adres van uw on-premises Exchange Server 192.168.0.1 is, vormt u de SPF TXT-record als volgt om in te stellen dat de SPF-regel voor het afdwingen hard mislukt:

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-microsoft-365"></a>Voorbeeld: SPF TXT-record voor meerdere uitgaande on-premises e-mailservers en Microsoft 365
<a name="ExampleSPFMultipleMailServerO365"> </a>

Als u meerdere uitgaande e-mailservers hebt, moet u het IP-adres voor elke e-mailserver opnemen in de SPF TXT-record en elk IP-adres scheiden met een spatie gevolgd door een 'ip4:'-instructie. Bijvoorbeeld:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-microsoft-365"></a>Volgende stappen: SPF instellen voor Microsoft 365
<a name="SPFNextSteps"> </a>

Nadat u uw SPF TXT-record hebt opgesteld, volgt u de stappen [in SPF instellen in Microsoft 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md) om spoofing te helpen voorkomen en deze aan uw domein toe te voegen.

SPF is ontworpen om spoofing te helpen voorkomen, maar er zijn spoofing-technieken die SPF niet kan beveiligen tegen. Om u hiertegen te beschermen, moet u, nadat u SPF hebt ingesteld, ook DKIM en DMARC voor Microsoft 365 configureren. Zie DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanaf uw aangepaste domein [in Microsoft 365](use-dkim-to-validate-outbound-email.md)om aan de slag te gaan. Zie vervolgens [DMARC gebruiken om e-mail in Microsoft 365 te valideren](use-dmarc-to-validate-email.md).

## <a name="troubleshooting-best-practices-for-spf-in-microsoft-365"></a>Probleemoplossing: Best practices voor SPF in Microsoft 365
<a name="SPFTroubleshoot"> </a>

U kunt slechts één SPF TXT-record maken voor uw aangepaste domein. Als u meerdere records maakt, ting de situatie rond en mislukt SPF. U kunt dit voorkomen door afzonderlijke records te maken voor elk subdomein. Maak bijvoorbeeld één record voor contoso.com en een andere record voor bulkmail.contoso.com.

Als een e-mailbericht meer dan tien DNS-lookups veroorzaakt voordat het wordt bezorgd, reageert de ontvangende e-mailserver met een permanente fout, ook wel  _een permerror_ genoemd, en mislukt de SPF-controle van het bericht. De ontvangende server kan ook reageren met een rapport over niet-levering (NDR) met een fout die er ongeveer zo uit komt:

- Het bericht heeft het aantal hops overschreden.

- Voor het bericht zijn te veel zoekactieen vereist.

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-microsoft-365"></a>Vermijd de fout 'te veel zoekactie' wanneer u domeinen van derden gebruikt met Microsoft 365
<a name="SPFTroubleshoot"> </a>

Sommige SPF TXT-records voor domeinen van derden leiden de ontvangende server om een groot aantal DNS-lookups uit te voeren. Op het moment van schrijven bevat Salesforce.com bijvoorbeeld vijf instructies in de record:

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

U kunt de fout vermijden door een beleid te implementeren waarbij iedereen die bulk-e-mail verstuurt, hiervoor bijvoorbeeld een subdomein moet gebruiken. Vervolgens definieert u een andere SPF TXT-record voor het subdomein dat de bulk-e-mail bevat.

 In sommige gevallen, zoals in het salesforce.com-voorbeeld, moet u het domein gebruiken in uw SPF TXT-record, maar in andere gevallen heeft de derde partij mogelijk al een subdomein gemaakt dat u hiervoor kunt gebruiken. Zo heeft exacttarget.com een subdomein gemaakt dat u moet gebruiken voor uw SPF TXT-record:

```text
cust-spf.exacttarget.com
```

Wanneer u domeinen van derden in uw SPF TXT-record op nemen, moet u bevestigen met de derde partij welk domein of subdomein moet worden gebruikt om te voorkomen dat de opzoeklimiet van 10 wordt bereikt.

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a>Uw huidige SPF TXT-record weergeven en het aantal zoekactie vaststellen dat hiervoor nodig is
<a name="SPFTroubleshoot"> </a>

U kunt nslookup gebruiken om uw DNS-records weer te geven, inclusief uw SPF TXT-record. Als u wilt, zijn er verschillende gratis onlinehulpprogramma's beschikbaar waarmee u de inhoud van uw SPF TXT-record kunt bekijken. Door naar uw SPF TXT-record te kijken en de reeks instructies en omleiding te volgen, kunt u bepalen hoeveel DNS-lookups de record nodig heeft. Sommige onlinehulpprogramma's tellen deze zoekactie zelfs en worden voor u weergegeven. Als u dit nummer bij houdt, voorkomt u dat berichten van uw organisatie een permanente fout, een zogenaamde permerror, van de ontvangende server activeren.

## <a name="for-more-information"></a>Voor meer informatie
<a name="SPFTroubleshoot"> </a>

Hulp nodig bij het toevoegen van de SPF TXT-record? Lees het artikel [DNS-records maken bij een DNS-hostingprovider voor Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) voor gedetailleerde informatie over het gebruik van Sender Policy Framework met uw aangepaste domein in Microsoft 365. [Berichtkoppen tegen ongewenste e-mail](anti-spam-message-headers.md) bevatten de syntaxis- en koptekstvelden die door Microsoft 365 worden gebruikt voor SPF-controles.


