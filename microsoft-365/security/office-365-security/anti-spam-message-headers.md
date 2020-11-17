---
title: Berichtkoppen tegen ongewenste e-mail
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Beheerders kunnen meer informatie krijgen over de velden met berichtkoppen die door Exchange Online Protection (EOP) worden toegevoegd aan berichten. Deze koptekstvelden bieden informatie over het bericht en hoe dit is verwerkt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6f54ffad5107e0de00b0098d5f347ab37ae92d80
ms.sourcegitcommit: 2d3e85173c65a9e0ce92624a80ed7a9839f5b8bd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2020
ms.locfileid: "49123466"
---
# <a name="anti-spam-message-headers-in-microsoft-365"></a>Berichtkoppen tegen ongewenste e-mail in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In alle Microsoft 365-organisaties scant Exchange Online Protection (EOP) alle inkomende berichten op spam, malware en andere bedreigingen. De resultaten van deze scans worden toegevoegd aan de volgende koptekstvelden in berichten:

- **X-Forefront-spam-rapport**: bevat informatie over het bericht en hoe dit is verwerkt.

- **X-Microsoft-Antispam**: bevat extra informatie over bulkmail en phishing.

- **Authentication-results**: bevat informatie over SPF-, DKIM-en DMARC-resultaten (e-mailverificatie).

In dit artikel wordt beschreven wat er beschikbaar is in deze koptekstvelden.

Zie [Internetberichtkoppen weergeven in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c) voor meer informatie over het weergeven van een e-mailberichtkop in verschillende e-mailclients.

> [!TIP]
> U kunt de inhoud van een berichtkop kopiëren en plakken in het hulpmiddel [Message Header Analyzer](https://mha.azurewebsites.net/). Met dit hulpprogramma kunt u headers parseren en deze een leesbare indeling geven.

## <a name="x-forefront-antispam-report-message-header-fields"></a>Berichtkopvelden van de vorm X-Forefront-Antispam-Report

Nadat u de informatie in de kop van het bericht hebt, zoekt u de koptekst van het **X-Forefront-Antispam-Report**. Er staan meerdere paren van velden en -waarden in deze koptekst gescheiden door puntkomma's (;). Bijvoorbeeld:

`...CTRY:;LANG:hr;SCL:1;SRV:;IPV:NLI;SFV:NSPM;PTR:;CAT:NONE;SFTY:;...`

De afzonderlijke velden en waarden worden beschreven in de volgende tabel.

> [!NOTE]
> De koptekst **X-Forefront-Antispam-Report** bevat vele verschillende velden en -waarden. Velden die niet worden beschreven in de tabel worden uitsluitend door het Microsoft-antispamteam voor diagnostische doeleinden gebruikt.

****

|Veld|Beschrijving|
|---|---|
|`ARC`|Het `ARC`-protocol heeft de volgende velden: <ul><li>`AAR`: hierin wordt de inhoud van de kop **Authentication-results** van DMARC vastgelegd.</li><li>`AMS`: bevat cryptografische handtekeningen van het bericht.</li><li>`AS`: bevat cryptografische handtekeningen van de berichtkoppen. Deze koptekst bevat een tag voor een ketenvalidatie met de naam `"cv="`, die het resultaat van de ketenvalidatie bevat als **none**, **pass** of **fail**.</li></ul>|
|`CAT:`|De categorie beveiligingsbeleid, toegepast op het bericht: <ul><li>`BULK`: bulk</li><li>`DIMP`: domeinimitatie</li><li>`GIMP`: [op postvakanalyse gebaseerde imitatie](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>`HPHSH` of `HPHISH`: hoogstwaarschijnlijk phishing</li><li>`HSPM`: hoogstwaarschijnlijk spam</li><li>`MALW`: malware</li><li>`PHSH`: phishing</li><li>`SPM`: spam</li><li>`SPOOF`: spoofing</li><li>`UIMP`: imitatie van gebruiker</li><li>`AMP`: anti-malware</li><li>`SAP`: veilige bijlagen</li><li>`OSPM`: uitgaande spam</li></ul><br/>Een inkomend bericht kan zijn gemarkeerd door meerdere beveiligingswijzen en meerdere detectiescans. Beleidsregels hebben verschillende prioriteiten en de regel met de hoogste prioriteit wordt het eerst toegepast. Zie [Welke beleidsregel wordt toegepast wanneer meerdere beveiligingswijzen en detectiescans op uw e-mail worden uitgevoerd?](how-policies-and-protections-are-combined.md) voor meer informatie.|
|`CIP:[IP address]`|Het IP-verbindingsadres. U kunt dit IP-adres gebruiken in de IP-acceptatielijst of IP-blokkeringslijst. Zie [Verbindingsfiltering configureren](configure-the-connection-filter-policy.md) voor meer informatie.|
|`CTRY`|Het bronland wordt bepaald door het verbindings-IP-adres. Dit hoeft niet hetzelfde te zijn als het oorspronkelijke verzend-IP-adres.|
|`H:[helostring]`|De HELO- of EHLO-tekenreeks van de verbindende e-mailserver.|
|`IPV:CAL`|Het bericht is door het spamfilter overgeslagen omdat het bron-IP-adres in de IP-acceptatielijst vermeld staat. Zie [Verbindingsfiltering configureren](configure-the-connection-filter-policy.md) voor meer informatie.|
|`IPV:NLI`|Het IP-adres staat niet vermeld in de IP-reputatielijst.|
|`LANG`|De taal waarin het bericht is geschreven, zoals opgegeven door de landcode (bijvoorbeeld ru_RU voor Russisch).|
|`PTR:[ReverseDNS]`|De PTR-record (ook wel het omgekeerde DNS-adres genoemd) van het bron-IP-adres.|
|`SCL`|De spamwaarschijnlijkheidswaarde (SCL) van het bericht. Hoe hoger de waarde, hoe groter de kans dat het bericht spam is. Zie [Spamwaarschijnlijkheidswaarde (SCL)](spam-confidence-levels.md) voor meer informatie.|
|`SFTY`|Het bericht is geïdentificeerd als phishing en wordt tevens gemarkeerd met een van de volgende waarden: <ul><li>9.1: standaardwaarde. Het bericht bevat een of meer van de volgende elementen: een phishing-URL, andere phishingwebsites of is gemarkeerd als phishing door on-premises Exchange.</li><li>9.11: [Intra-org of self-to-self spoofing](anti-spoofing-protection.md#different-types-of-spoofing). De beveiligingstip over spoofing van binnen de organisatie wordt toegevoegd aan het bericht.</li><li>9.19: domeinimitatie. Het verzendende domein probeert een [beschermd domein na te bootsen](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365). De beveiligingstip voor domeinimitatie wordt toegevoegd aan het bericht (als dit is ingeschakeld).</li><li>9.20: gebruikersimitatie. De verzendende gebruiker probeert zich voor te doen als een gebruiker in de organisatie van de ontvanger of als een beveiligde gebruiker die is gespecificeerd in een antiphishingbeleid in Microsoft Defender voor Office 365. De beveiligingstip voor gebruikersimitatie wordt toegevoegd aan het bericht (als dit is ingeschakeld).</li><li>9.21: [adresvervalsing tussen domeinen](anti-spoofing-protection.md#different-types-of-spoofing). Het bericht heeft antispoofingcontroles niet doorstaan. Het domein van de afzender in de berichtkop Van: is niet geverifieerd en is afkomstig van een extern domein. Wordt gebruikt in combinatie met [samengestelde verificatie](#authentication-results-message-header-fields).</li><li>9.22: hetzelfde als 9.21, behalve dat de gebruiker een veilige afzender heeft die is overschreven.</li><li>9.23: hetzelfde als 9.22, behalve dat de organisatie een toegestane afzender of toegestaan domein heeft, waarbij een van de twee is overschreven.</li><li>9.24: hetzelfde als 9.23, behalve dat de gebruiker een Exchange-e-mailstroomregel (ook wel transportregel genoemd) heeft, die is overschreven.</li></ul>|
|`SFV:BLK`|Filteren is overgeslagen en het bericht is geblokkeerd, omdat het is verzonden vanaf een adres in de lijst met geblokkeerde afzenders van een gebruiker.<br/></br> Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken](configure-junk-email-settings-on-exo-mailboxes.md) voor meer informatie over de manier waarop beheerders de lijst met geblokkeerde afzenders van een gebruiker kunnen beheren.|
|`SFV:NSPM`|Het bericht is gemarkeerd als niet-spam en is verzonden naar de beoogde geadresseerden.|
|`SFV:SFE`|Filteren is overgeslagen en het bericht is toegestaan, omdat het is verzonden vanaf een adres in de lijst met veilige afzenders van een gebruiker.<br/></br> Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken](configure-junk-email-settings-on-exo-mailboxes.md) voor meer informatie over de manier waarop beheerders de lijst met veilige afzenders van een gebruiker kunnen beheren.|
|`SFV:SKA`|Het bericht is door het spamfilter overgeslagen en is bezorgd in het Postvak IN, omdat de afzender voorkomt in de lijst met toegestane afzenders of de lijst met toegestane domeinen in een antispambeleidsregel. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|`SFV:SKB`|Het bericht is gemarkeerd als spam, omdat de afzender overeenkomt met een afzender in de lijst met geblokkeerde afzenders of de lijst met geblokkeerde domeinen in een antispambeleidsregel. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|`SFV:SKI`|Vergelijkbaar met SFV: SKN; het bericht is om een andere reden door het spamfilter overgeslagen (bijvoorbeeld een e-mail van binnen een organisatie binnen een tenant).|
|`SFV:SKN`|Het bericht is gemarkeerd als niet-spam voordat het werd verwerkt door het spamfilter. Het bericht is bijvoorbeeld gemarkeerd als SCL-1 of **spamfilter niet toepassen** door een regel voor de e-mailstroom.|
|`SFV:SKQ`|Het bericht is vrijgegeven uit quarantaine en is verzonden naar de beoogde geadresseerden.|
|`SFV:SKS`|Het bericht is gemarkeerd als spam voordat het werd verwerkt door het spamfilter. Het bericht is bijvoorbeeld gemarkeerd als SCL 5 tot en met 9 door een regel voor de e-mailstroom.|
|`SFV:SPM`|Het bericht is gemarkeerd als spam door het spamfilter.|
|`SRV:BULK`|Het bericht is geïdentificeerd als bulk-e-mail door het spamfilter en de drempelwaarde van het bulkklachtniveau (BCL). Als parameter _MarkAsSpamBulkMail_ `On` is (standaard ingeschakeld), wordt een bulk-e-mailbericht gemarkeerd als spam van hoge waarschijnlijkheid (SCL 9). Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|`X-CustomSpam: [ASFOption]`|Het bericht komt overeen met een instelling voor Geavanceerd spamfilter (ASF). Zie [Instellingen voor geavanceerd spamfilter (ASF)](advanced-spam-filtering-asf-options.md) als u de waarde van de X-header voor elke ASF-instelling wilt zien.|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>Berichtkopvelden van de vorm X-Microsoft-Antispam

In de volgende tabel worden nuttige velden in de berichtkop **X-Microsoft-Antispam** beschreven. Andere velden in deze kop worden uitsluitend door het Microsoft-antispamteam voor diagnostische doeleinden gebruikt.

****

|Veld|Beschrijving|
|---|---|
|`BCL`|Het bulkklachtniveau (BCL) van het bericht. Een hogere BCL duidt op een bulk-e-mailbericht en levert vermoedelijk meer klachten op (en is dus vermoedelijk spam). Zie [Bulkklachtniveau (BCL)](bulk-complaint-level-values.md) voor meer informatie.|
|

## <a name="authentication-results-message-header"></a>Berichtkop Authentication-results

De resultaten van e-mailverificatie worden gecontroleerd op SPF, DKIM en DMARC, en worden vastgelegd in de berichtkop **Authentication-results** in binnenkomende berichten.

In de volgende lijst vindt u een beschrijving van de tekst die wordt toegevoegd aan de koptekst **Authentication-results** voor elk type e-mailverificatie:

- SPF gebruikt de volgende syntaxis:

  ```text
  spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
  ```

  Bijvoorbeeld:

  ```text
  spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
  spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
  ```

- DKIM gebruikt de volgende syntaxis:

  ```text
  dkim=<pass|fail (reason)|none> header.d=<domain>
  ```

  Bijvoorbeeld:

  ```text
  dkim=pass (signature was verified) header.d=contoso.com
  dkim=fail (body hash did not verify) header.d=contoso.com
  ```

- DMARC gebruikt de volgende syntaxis:

  ```text
  dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
  ```

  Bijvoorbeeld:

  ```text
  dmarc=pass action=none header.from=contoso.com
  dmarc=bestguesspass action=none header.from=contoso.com
  dmarc=fail action=none header.from=contoso.com
  dmarc=fail action=oreject header.from=contoso.com
  ```

### <a name="authentication-results-message-header-fields"></a>Velden berichtkop Authentication-results

In de volgende tabel worden de velden en mogelijke waarden voor elke e-mailverificatie beschreven.

****

|Veld|Beschrijving|
|---|---|
|`action`|Hiermee wordt aangegeven welke actie door het spamfilter is uitgevoerd op basis van de resultaten van de DMARC-controle. Bijvoorbeeld: <ul><li>**oreject** of **o.reject**: staat voor weigering negeren. In dit geval gebruikt Microsoft 365 deze actie als een bericht wordt ontvangen dat de DMARC-controle niet doorstaat van een domein met een DMARC TXT-record met beleidsregel p=reject. In plaats van het bericht te verwijderen of te weigeren, wordt het bericht in Microsoft 365 als spam gemarkeerd. Zie [Verwerken van inkomende e-mailberichten in Microsoft 365 die DMARC niet doorstaan](use-dmarc-to-validate-email.md#how-microsoft-365-handles-inbound-email-that-fails-dmarc) voor meer informatie over de manier waarom Microsoft 365 op deze manier wordt geconfigureerd.</li><li>**pct.quarantine**: hiermee wordt aangegeven dat minder dan 100% van de berichten die DMARC niet doorstaan, toch wordt bezorgd. Dit betekent dat het bericht DMARC niet heeft doorstaan en dat de beleidsregel is ingesteld op quarantine, maar dat het percentageveld niet is ingesteld op 100% en dat het systeem willekeurig heeft bepaald dat de actie DMARC niet wordt toegepast, conform het beleid van het opgegeven domein.</li><li>**pct.reject**: hiermee wordt aangegeven dat minder dan 100% van de berichten die DMARC niet doorstaan, toch wordt bezorgd. Dit betekent dat het bericht DMARC niet heeft doorstaan en dat de beleidsregel is ingesteld op reject, maar dat het percentageveld niet is ingesteld op 100% en dat het systeem willekeurig heeft bepaald dat de actie DMARC niet wordt toegepast, conform het beleid van het opgegeven domein.</li><li>**permerror**: er is een permanente fout opgetreden tijdens de DMARC-evaluatie, zoals bij een verkeerd geformuleerd DMARC TXT-record in DNS. Het opnieuw verzenden van dit bericht, leidt hoogstwaarschijnlijk tot hetzelfde resultaat. U kunt contact opnemen met de eigenaar van het domein om het probleem op te lossen.</li><li>**temperror**: er is een tijdelijke fout opgetreden tijdens de DMARC-evaluatie. U kunt de afzender vragen het bericht later opnieuw te verzenden om het e-mailbericht correct te kunnen verwerken.</li></ul>|
|`compauth`|Resultaat van samengestelde verificatie. Wordt gebruikt voor Microsoft 365 om meerdere typen verificatie te combineren, zoals SPF, DKIM, DMARC of een ander deel van het bericht om te bepalen of het bericht al dan niet wordt geverifieerd. Hierbij wordt het domein Van: gebruikt als basis voor de evaluatie.|
|`dkim`|Beschrijft de resultaten van de DKIM-controle van het bericht. Mogelijke waarden zijn: <ul><li>**pass**: hiermee wordt aangegeven dat de DKIM-controle van het bericht is geslaagd.</li><li>**fail (reden)**: hiermee wordt aangegeven dat de DKIM-controle van het bericht is mislukt en de reden waarom. Bijvoorbeeld als het bericht niet is ondertekend of als de handtekening niet is gecontroleerd.</li><li>**none**: hiermee wordt aangegeven dat het bericht niet is ondertekend. Dit kan al of niet betekenen dat het domein een DKIM-record heeft of dat het DKIM-record geen resultaat oplevert. Het betekent in elk geval dat dit bericht niet is ondertekend.</li></ul>|
|`dmarc`|Beschrijft de resultaten van de DMARC-controle van het bericht. Mogelijke waarden zijn: <ul><li>**pass**: hiermee wordt aangegeven dat de DMARC-controle van het bericht is geslaagd.</li><li>**fail**: hiermee wordt aangegeven dat de DMARC-controle van het bericht is mislukt.</li><li>**bestguesspass**: hiermee wordt aangegeven dat er geen DMARC TXT-record voor het domein aanwezig is, maar dat indien er wel een zou zijn de DMARC-controle van het bericht zou zijn geslaagd. Dit komt omdat het domein in het `5321.MailFrom`-adres (ook wel MAIL FROM-adres, P1-afzender of envelopafzender genoemd), overeenkomt met het domein in het `5322.From`-adres (ook wel Van-adres of P2-afzender genoemd).</li><li>**none**: hiermee wordt aangegeven dat er geen DMARC TXT-record aanwezig is voor het verzendende domein in DNS.|
|`header.d`|Domein dat is geïdentificeerd in de DKIM-handtekening, voor zover aanwezig. Dit is het domein waarop een query wordt uitgevoerd voor de openbare sleutel.|
|`header.from`|Het domein van het `5322.From`-adres de berichtkop van het e-mailbericht (ook wel Van-adres of P2-afzender genoemd). Geadresseerden zien het Van-adres in e-mailclients.|
|`reason`|De reden waarom de samengestelde verificatie is geslaagd of mislukt. De waarde is een code van drie cijfers. Bijvoorbeeld: <ul><li>**000**: het bericht heeft de verificatie expliciet niet doorstaan (`compauth=fail`). Bijvoorbeeld: het bericht heeft een DMARC-controle niet doorstaan met de actie Quarantine of Weigeren.</li><li>**001**: het bericht heeft impliciete verificatie niet doorstaan (`compauth=fail`). Dit houdt in dat het verzendende domein geen e-mail records voor e-mailverificatie heeft gepubliceerd of dat ze een zwakker foutbeleid hanteerden (SPF-softfail of Neutraal, DMARC-beleid `p=none`).</li><li>**002**: de organisatie heeft een beleid voor het afzender/domein-paar dat expliciet is uitgesloten van het verzenden van vervalste e-mail. Deze instelling wordt handmatig ingesteld door een beheerder.</li><li>**010**: het bericht is verworpen door DMARC met als actie weigering of quarantaine, en het verzendende domein is een van de geaccepteerde domeinen van uw organisatie (dit is onderdeel van self-to-self- of intra-org-adresvervalsing).</li><li>**1xx** of **7xx**: het bericht heeft de verificatie doorstaan (`compauth=pass`). De twee laatste cijfers zijn interne codes die voor Microsoft 365 worden gebruikt.</li><li>**2xx**: het bericht heeft de verificatie doorstaan met resultaat 'soft-pass' (`compauth=softpass`). De twee laatste cijfers zijn interne codes die voor Microsoft 365 worden gebruikt.</li><li>**3xx**: het bericht is niet gecontroleerd op samengestelde verificatie (`compauth=none`).</li><li>**4xx** of **9xx**: het bericht heeft samengestelde verificatie omzeild (`compauth=none`). De twee laatste cijfers zijn interne codes die voor Microsoft 365 worden gebruikt.</li><li>**6xx**: het bericht is verworpen door impliciete e-mailverificatie, en het verzendende domein is een van de geaccepteerde domeinen van uw organisatie (dit is onderdeel van self-to-self- of intra-org-adresvervalsing).</li></ul>|
|`smtp.mailfrom`|Het domein van het `5321.MailFrom`-adres (ook wel MAIL FROM-adres, P1-afzender of envelopafzender genoemd). Dit is het e-mailadres dat voor rapporten over niet-uitgevoerde bezorging wordt gebruikt (ook wel NDR's of niet-bezorgberichten genoemd).|
|`spf`|Beschrijft de resultaten van de SPF-controle van het bericht. Mogelijke waarden zijn: <ul><li>`pass (IP address)`: de SPF-check van het bericht is geslaagd, en het bevat het IP-adres van de afzender. De client wordt geautoriseerd e-mail te verzenden of door te sturen namens het domein van de afzender.</li><li>`fail (IP address)`: de SPF-check van het bericht is mislukt, en het bevat het IP-adres van de afzender. Dit wordt ook wel een _hard fail_ genoemd.</li><li>`softfail (reason)`: door het SPF-record is bepaald dat de host niet mag verzenden, maar dat deze zich in een overgangsfase bevindt.</li><li>`neutral`: in het SPF-record wordt expliciet aangegeven dat er geen toestemming wordt gevraagd of het IP-adres mag verzenden.</li><li>`none`: het domein geen SPF-record heeft of het SPF-record leidt niet tot een resultaat.</li><li>`temperror`: er is een tijdelijke fout opgetreden. Bijvoorbeeld een DNS-fout. Dezelfde controle kan mogelijk later wel worden uitgevoerd.</li><li>`permerror`: er is een permanente fout opgetreden. Het domein heeft bijvoorbeeld een foutief ingedeeld SPF-record.</li></ul>|
|
