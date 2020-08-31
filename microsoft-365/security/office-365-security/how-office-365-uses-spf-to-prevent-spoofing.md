---
title: Het voorkomen van spoofing door Sender Policy Framework (SPF)
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
description: Lees hoe Microsoft 365 de SPF-TXT-record (Sender Policy Framework) in DNS gebruikt om ervoor te zorgen dat e-mail systemen berichten vertrouwen die vanuit uw aangepaste domein zijn verzonden.
ms.openlocfilehash: 702c5de90c53388a3d55ad752010fbaa04b5556b
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307647"
---
# <a name="how-microsoft-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a>Hoe Microsoft 365 SPF (Sender Policy Framework) gebruikt om adresvervalsing te voorkomen

 **Overzicht:** In dit artikel wordt beschreven hoe Microsoft 365 de SPF-TXT-record (Sender Policy Framework) in DNS gebruikt om ervoor te zorgen dat e-mail systemen berichten die vanuit uw aangepaste domein worden verzonden, worden vertrouwd. Dit geldt voor uitgaande e-mail verzonden via Microsoft 365. Berichten die worden verzonden vanaf Microsoft 365 naar een geadresseerde in Microsoft 365, worden altijd SPF weergegeven.

Een SPF TXT-record is een DNS-record die helpt spoofing en phishing te voorkomen door de domeinnaam te verifiëren van e-mailberichten die worden verzonden. SPF valideert de oorsprong van e-mailberichten door het IP-adres van de afzender te verifiëren tegen de gemoedeerde eigenaar van het verzendende domein.

> [!NOTE]
> SPF-recordtypen werden via IETF (Internet Engineering Task Force) in 2014 gedeprecieerd. Zorg er in plaats daarvan voor dat u TXT-records in DNS gebruikt voor het publiceren van uw SPF-gegevens. De rest van dit artikel gebruikt de term SPF TXT-record voor duidelijkheid.

Domeinbeheerders publiceren SPF-informatie in TXT-records in DNS. De SPF-gegevens identificeren geautoriseerde uitgaande e-mailservers. Doel-e-mail systemen verifieert dat berichten afkomstig zijn van gemachtigde uitgaande e-mailservers. Als u al bekend bent met SPF, of als u een eenvoudige implementatie hebt en alleen weet wat u wilt opnemen in uw SPF TXT-record in DNS voor Microsoft 365, gaat u naar [SPF instellen in Microsoft 365 om spoofing te helpen voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Lees verder als u geen implementatie hebt die volledig gehost is in Microsoft 365, of als u meer wilt weten over de manier waarop SPF werkt of hoe u problemen met SPF voor Microsoft 365 oplost.

> [!NOTE]
> Eerder hebt u een andere SPF TXT-record aan uw aangepaste domein toegevoegd als u ook SharePoint Online gebruikt. Dit is niet meer nodig. Deze wijziging moet het risico verkleinen dat SharePoint Online-meldingsberichten in de map Ongewenste e-mail terechtkomen. U hoeft geen wijzigingen direct aan te brengen, maar als u de fout ' te veel zoekresultaten ' ontvangt, wijzigt u de SPF TXT-record zoals beschreven in [SPF instellen in Microsoft 365 om spoofing te helpen voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md).

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-microsoft-365"></a>Hoe SPF werkt spoofing en phishing voorkomen in Microsoft 365
<a name="HowSPFWorks"> </a>

SPF bepaalt of een afzender al dan niet mag worden verzonden namens een domein. Als de afzender dit niet mag doen, dat wil zeggen als de e-mail melding mislukt op de server voor het ontvangen van de e-mail, bepaalt het antispambeleid dat op de server is geconfigureerd wat er met het bericht moet worden gedaan.

Elke SPF TXT-record bevat drie gedeelten: de declaratie dat het een SPF TXT-record is, welke IP-adressen zijn toegestaan voor het verzenden van e-mail van uw domein en de externe domeinen die namens de domeinnamen en een afdwingings regel kunnen verzenden. U hebt alledrie een geldige SPF TXT-record nodig. In dit artikel wordt beschreven hoe u uw SPF TXT-record kunt maken en de aanbevolen procedures voor het werken met de Services kunt in Microsoft 365. Koppelingen naar instructies voor het werken met uw domeinregistratieservice voor het publiceren van uw record met DNS is ook beschikbaar.

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a>SPF-basisbeginselen: IP-adressen die mogen worden verzonden vanuit uw aangepaste domein
<a name="SPFBasicsIPaddresses"> </a>

Bekijk de syntaxis van basis voor een SPF-regel:

v = spf1 \<IP\>\<enforcement rule\>

Stel dat u bijvoorbeeld de volgende SPF-regel bestaat voor contoso.com:

v = spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\>\<enforcement rule\>

In dit voorbeeld wordt met de SPF-regel de ontvangende e-mailserver geïnstrueerd alleen e-mail te accepteren van deze IP-adressen voor de domein contoso.com:

- IP-adres #1

- IP-adres #2

- IP-adres #3

Met deze SPF-regel wordt de e-mailserver van de ontvangst van een bericht op de plaats van contoso.com, maar niet uit een van deze drie IP-adressen, moet de ontvangende server de nalevings regel op het bericht toepassen. De handhavings regel is meestal een van de volgende opties:

- **Moeilijk mislukt.** Markeer het bericht met ' moeilijk fout ' in de envelop van het bericht en voer vervolgens het geconfigureerde spam beleid van de ontvangen server voor dit type bericht uit.

- **Vloeiend, mislukt.** Markeer het bericht met ' zacht fout ' in de bericht envelop. Meestal zijn e-mailservers zodanig geconfigureerd dat ze deze berichten toch leveren. De meeste eindgebruikers zien dit vinkje niet.

- **Neutraal.** Niets doen, dat wil zeggen, dat wil zeggen dat u de envelop met berichten niet markeert. Dit is meestal gereserveerd voor testdoeleinden en wordt zelden gebruikt.

In de volgende voorbeelden wordt getoond hoe SPF in verschillende situaties werkt. In deze voorbeelden is contoso.com de afzender en woodgrovebank.com de ontvanger.

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a>Voorbeeld 1: e-mail verificatie van een bericht dat rechtstreeks van afzender naar ontvanger is verzonden
<a name="spfExample1"> </a>

SPF werkt het best wanneer het pad van afzender naar ontvanger direct is, bijvoorbeeld:

![Diagram waarin wordt weergegeven hoe SPF e-mail verifieert, wanneer deze rechtstreeks wordt verzonden van de server naar de server.](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

Wanneer woodgrovebank.com het bericht ontvangt, als het IP-adres #1 in de SPF TXT-record voor contoso.com, wordt het bericht doorgegeven aan de SPF-controle en is de verificatie geauthenticeerd.

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a>Voorbeeld 2: certificaat met spoofing mislukt de SPF-controle
<a name="spfExample2"> </a>

Stel dat een phisher een manier voor spoofing contoso.com:

![Diagram waarin wordt weergegeven hoe SPF e-mail verifieert als deze wordt verzonden via een vervalste server.](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

Aangezien IP-adres #12 zich niet in de SPF TXT-record van contoso. com bevindt, mislukt het bericht de SPF-controle en kan de ontvanger deze als spam markeren.

### <a name="example-3-spf-and-forwarded-messages"></a>Voorbeeld 3: SPF en doorgestuurde berichten
<a name="spfExample3"> </a>

Eén nadeel van SPF is dat het niet werkt als een e-mailbericht is doorgestuurd. Stel dat de gebruiker bij woodgrovebank.com een doorstuurregel heeft ingesteld voor het verzenden van alle e-mailberichten naar een outlook.com-account:

![Diagram waarin wordt weergegeven hoe SPF geen e-mail kan verifiëren als het bericht wordt doorgestuurd.](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

Het bericht geeft de SPF-controle aan op woodgrovebank.com, maar het is niet mogelijk dat de SPF-controle bij outlook.com is mislukt, omdat IP #25 zich niet in de SPF TXT-record van contoso. com bevindt. Outlook.com kan vervolgens het bericht als spam markeren. Om dit probleem tijdelijk op te lossen, gebruikt u SPF samen met andere verificatiemethoden voor e-mail, zoals DKIM en DMARC.

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a>SPF-basisbeginselen: ook domeinen van derden die e-mail verzenden namens uw domein
<a name="SPFBasicsIncludes"> </a>

Naast IP-adressen kunt u ook uw SPF TXT-record configureren, zodat domeinen als afzenders worden opgenomen. Deze worden toegevoegd aan de statement. SPF TXT-record. In contoso.com kunt u bijvoorbeeld alle IP-adressen van de e-mailservers van contoso.net en contoso.org opnemen. Om dit te doen, publiceert contoso.com een SPF TXT-record die er zo uitziet:

```text
v=spf1 include:contoso.net include:contoso.org -all
```

Wanneer de ontvangende server deze record in DNS ziet, wordt ook een DNS-zoekopdracht uitgevoerd op de SPF TXT-record voor contoso.net en vervolgens voor contoso.org. Als er een aanvullend include-instructie is binnen de records voor contoso.net of contoso.org, wordt deze ook gebruikt. Om te voorkomen dat u denial of service-aanvallen kunt voorkomen, is het maximale aantal DNS-zoekopdrachten voor één e-mailbericht 10. Elk van de instructies omvat een extra DNS-zoekopdracht. Als een bericht de tien limiet overschrijdt, mislukt het bericht SPF. Wanneer een bericht deze limiet heeft bereikt, wordt, afhankelijk van de manier waarop de server wordt geconfigureerd, een bericht weergegeven met de tekst ' te veel zoekwaarden ' of ' het maximum aantal hops voor het bericht is overschreden ' (die kunnen optreden wanneer de zoekopdrachten lussen en de DNS-time-out overschrijden). Voor tips over hoe u dit kunt voorkomen, raadpleegt u [problemen oplossen: Best practices voor spf in Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).

## <a name="requirements-for-your-spf-txt-record-and-microsoft-365"></a>Vereisten voor uw SPF TXT-record en Microsoft 365
<a name="SPFReqsinO365"> </a>

Als u e-mail instelt bij het instellen van Microsoft 365, hebt u al een SPF TXT-record gemaakt waarmee de Microsoft Messaging-servers als een legitieme bron van e-mailberichten voor uw domein worden geïdentificeerd. Deze record ziet er waarschijnlijk zo uit:

```text
v=spf1 include:spf.protection.outlook.com -all
```

Als u een volledig gehoste klant bent, hebt u geen on-premises e-mailservers die uitgaande e-mail verzenden, dit is de enige SPF TXT-record die u moet publiceren voor Office 365.

Als u een hybride implementatie hebt (dat wil zeggen: u beschikt over bepaalde postvakken on-premises en hebt u gehost in Microsoft 365) of u kunt een zelfstandige klant met Exchange Online Protection (dat wil zeggen dat uw organisatie gebruikmaakt van EOP om uw on-premises postvakken te beschermen) door het uitgaande IP-adres toe te voegen voor elk van uw on-premises Edge-e-mailservers in de SPF

## <a name="form-your-spf-txt-record-for-microsoft-365"></a>De SPF TXT-record voor Microsoft 365 maken
<a name="FormYourSPF"> </a>

Gebruik de syntaxisinformatie in dit artikel om de SPF TXT-record voor uw aangepaste domein te vormen. Hoewel er andere syntaxis opties zijn die hier niet worden vermeld, zijn dit de meestgebruikte opties. Wanneer u het record hebt gemaakt, moet u het record bij uw domeinregistrar bijwerken.

Zie [externe DNS-records vereist voor SPF](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)voor informatie over de domeinen die u moet opnemen voor microsoft 365. Volg de [Stapsgewijze instructies](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) voor het bijwerken van SPF (txt)-records voor uw domeinregistratie.

### <a name="spf-txt-record-syntax-for-microsoft-365"></a>SPF TXT-record syntaxis voor Microsoft 365
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

- **v = spf1** is vereist. Hiermee wordt de TXT-record gedefinieerd als een SPF TXT-record.

- **IP4** geeft aan dat u adressen van IP-adres 4 gebruikt. **ip6** geeft aan dat u adressen van IP-versie 6 gebruikt. Als u IPv6 IP-adressen gebruikt, vervangt u **IP4** door **ip6** in de voorbeelden in dit artikel. U kunt ook IP-adresbereiken opgeven met behulp van CIDR-notatie, bijvoorbeeld **ip4:192.168.0.1/26**.

- _IP-adres_ is het IP-adres dat u wilt toevoegen aan de SPF TXT-record. Meestal is dit het IP-adres van de server voor uitgaande e-mail voor uw organisatie. U kunt meerdere uitgaande e-mailservers vermelden. Zie voor meer informatie [: SPF TXT-record voor meerdere uitgaande on-premises e-mailservers en Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).

- _domeinnaam_ is het domein dat u wilt toevoegen als een legitieme afzender. Zie [externe DNS-records die vereist zijn voor SPF](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)voor een lijst met domeinnamen die u moet opnemen voor microsoft 365.

- Nalevings regel is meestal een van de volgende opties:

  - -all

    Geeft aan dat het moeilijk mislukt is. Als u alle geautoriseerde IP-adressen voor uw domein weet, kunt u deze in de SPF TXT-record vermelden en de kwalificatie-all (harde fout) gebruiken. Als u alleen SPF gebruikt, dat wil zeggen dat u niet gebruikmaakt van DMARC of DKIM, moet u de kwalificatie-all gebruiken. U wordt aangeraden altijd deze aanduiding te gebruiken.

  - ~ all

    Duidt op zacht fouten. Als u niet zeker weet of u de volledige lijst met IP-adressen hebt, moet u de kwalificatie alles gebruiken (vloeiend) gebruiken. Als u DMARC gebruikt met p = Quarantine of p = verwerpen, kunt u ook de ~ all gebruiken. U kunt ook-all gebruiken.

  - ? alles

    Geeft neutraal aan. Dit wordt gebruikt bij het testen van SPF. U wordt aangeraden deze kwalificatie niet te gebruiken in uw Live implementatie.

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-microsoft-365"></a>Voorbeeld: SPF TXT-record die moet worden gebruikt wanneer al uw e-mailberichten worden verzonden door Microsoft 365
<a name="ExampleSPFNoSP"> </a>

Als u al uw e-mailberichten verzendt door Microsoft 365, gebruikt u dit in uw SPF TXT-record:

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-microsoft-365"></a>Voorbeeld: SPF TXT-record voor een hybride scenario met een on-premises Exchange-Server en Microsoft 365
<a name="ExampleSPFHybridOneExchangeServer"> </a>

Als in een hybride omgeving het IP-adres van uw on-premises Exchange-Server is 192.168.0.1, moet u de SPF TXT-record als volgt instellen:

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-microsoft-365"></a>Voorbeeld: SPF TXT-record voor meerdere uitgaande on-premises e-mailservers en Microsoft 365
<a name="ExampleSPFMultipleMailServerO365"> </a>

Als u meerdere servers voor uitgaande e-mail hebt, neemt u het IP-adres voor elke e-mailserver op in de SPF TXT-record en scheidt u elk IP-adres met een spatie, gevolgd door een ' ip4: '-instructie. Bijvoorbeeld:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-microsoft-365"></a>Volgende stappen: SPF voor Microsoft 365 instellen
<a name="SPFNextSteps"> </a>

Wanneer u de SPF TXT-record hebt gemaakt, volgt u de stappen in [SPF instellen in Microsoft 365 om spoofing te helpen voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md) dat u dit aan uw domein toevoegt.

Hoewel SPF is bedoeld om spoofing te helpen voorkomen, maar geen spoofing-technieken waarmee SPF geen bescherming biedt. Om deze te beschermen, moet u ook de opties DKIM en DMARC voor Microsoft 365 configureren. Als u aan de slag wilt gaan, raadpleegt u [dkim gebruiken voor het valideren van uitgaande e-mail verzonden vanaf uw aangepaste domein in Microsoft 365](use-dkim-to-validate-outbound-email.md). Zie vervolgens [DMARC gebruiken om e-mail in Microsoft 365 te valideren](use-dmarc-to-validate-email.md).

## <a name="troubleshooting-best-practices-for-spf-in-microsoft-365"></a>Probleemoplossing: Aanbevolen procedures voor SPF in Microsoft 365
<a name="SPFTroubleshoot"> </a>

U kunt maar één SPF TXT-record voor uw aangepaste domein maken. Wanneer meerdere records worden gemaakt, mislukt dit met een Round Robin-situatie en SPF mislukt. Om dit te voorkomen, kunt u afzonderlijke records voor elk subdomein maken. Maak bijvoorbeeld één record voor contoso.com en een andere record voor bulkmail.contoso.com.

Als een e-mailbericht na ontvangst van een e-mailbericht meer dan 10 DNS-lookups veroorzaakt, reageert de ontvangende e-mailserver met een permanente fout, ook wel een  _Perm error_, en zorgt u ervoor dat het bericht mislukt met de SPF-controle. De ontvangende server kan ook reageren op een rapport niet-uitgevoerde bezorging (NDR) met een foutmelding die er ongeveer als volgt uitziet:

- Het bericht heeft het aantal hops overschreden.

- Het bericht vereist te veel zoekopdrachten.

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-microsoft-365"></a>De fout ' te veel zoekacties ' vermijden wanneer u domeinen van derden gebruikt met Microsoft 365
<a name="SPFTroubleshoot"> </a>

Met sommige SPF TXT-records voor domeinen van derden wordt de server voor het ontvangen van een groot aantal DNS-lookups doorgestuurd. Wanneer u bijvoorbeeld op deze wijze Salesforce.com bevat, bevat de record 5 instructies voor de record:

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

Om de fout te voorkomen, kunt u een beleid implementeren waarbij iedereen die bulkmail verstuurt, bijvoorbeeld een subdomein voor dit doel moet gebruiken. Vervolgens definieert u een andere SPF TXT-record voor het subdomein dat de bulk-mail bevat.

 In sommige gevallen, zoals in het voorbeeld salesforce.com, moet u het domein gebruiken in uw SPF TXT-record, maar in andere gevallen is het mogelijk dat de derde partij al een subdomein heeft gemaakt waarmee u dit doel kunt gebruiken. Exacttarget.com heeft bijvoorbeeld een subdomein gemaakt dat u moet gebruiken voor uw SPF TXT-record:

```text
cust-spf.exacttarget.com
```

Wanneer u domeinen van derden opneemt in uw SPF TXT-record, moet u bevestigen met de derde van de domein-of subdomein die moet worden gebruikt om te voorkomen dat de limiet voor 10 lookup wordt overschreden.

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a>Uw huidige SPF TXT-record weergeven en het aantal zoekopdrachten bepalen dat nodig is.
<a name="SPFTroubleshoot"> </a>

U kunt via nslookup de DNS-records weergeven, inclusief uw SPF TXT-record. U kunt ook een aantal gratis online hulpmiddelen gebruiken om de inhoud van uw SPF TXT-record weer te geven. Door te kijken naar de SPF TXT-record en de reeks include-instructies en omleidingen te volgen, kunt u bepalen hoeveel DNS-lookups de record vereist. Met sommige online hulpmiddelen wordt zelfs geteld en worden deze zoekopdrachten voor u weergegeven. Als u dit nummer bijhoudt, kunt u ervoor zorgen dat berichten die van uw organisatie worden verzonden, geen permanente fout, zogeheten Perm error, van de ontvangende server worden geactiveerd.

## <a name="for-more-information"></a>Voor meer informatie
<a name="SPFTroubleshoot"> </a>

Hulp nodig bij het toevoegen van de SPF TXT-record? Lees het artikel [DNS-records maken bij een DNS-hosting provider voor Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) voor gedetailleerde informatie over het gebruik van Framework met verzenderings beleid met uw aangepaste domein in microsoft 365. [Anti spambericht koppen](anti-spam-message-headers.md) bevatten de syntaxis en veldnamen velden die worden gebruikt door microsoft 365 voor spf-controles.


