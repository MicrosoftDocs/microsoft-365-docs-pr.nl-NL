---
title: Berichtkoppen tegen ongewenste e-mail
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
description: Lees meer over de koptekstvelden die Exchange Online Protection toevoegt aan berichten om informatie te geven over het bericht en hoe het is verwerkt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7f86b5ffa02b6f84c10ab2300f913b5f03726713
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173402"
---
# <a name="anti-spam-message-headers"></a>Berichtkoppen tegen ongewenste e-mail

Wanneer Exchange Online Protection (EOP) een inkomend e-mailbericht scant, wordt de berichtkop **X-Forefront-Antispam-Report** in elk bericht ingevoegd. De velden in deze kop kunnen beheerders informatie bieden over het bericht en over hoe het is verwerkt. De velden in de kop **X-Microsoft-Antispam** bevatten extra informatie over bulkmail en phishing. Naast deze twee koppen worden door Exchange Online Protection ook resultaten over e-mailverificatie ingevoegd voor elk bericht dat wordt verwerkt in de kop **Authentication-results**.

Zie [Internetberichtkoppen weergeven in Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c) voor meer informatie over het weergeven van een e-mailberichtkop in verschillende e-mailclients.

> [!TIP]
> U kunt de inhoud van een berichtkop kopiëren en plakken in het hulpmiddel [Message Analyzer](https://testconnectivity.microsoft.com/?tabid=mha). Met dit hulpprogramma kunt u headers parseren en deze een leesbare indeling geven.

## <a name="x-forefront-antispam-report-message-header-fields"></a>Berichtkopvelden van de vorm X-Forefront-Antispam-Report

Na het openen van de berichtkopinformatie zoekt u **X-Forefront-Antispam-Report** en zoekt u deze velden. Andere velden in deze kop worden uitsluitend door het Microsoft-antispamteam voor diagnostische doeleinden gebruikt.

|||
|---|---|
|**Berichtkopveld**|**Beschrijving**|
|ARC|Het ARC-protocol heeft de volgende berichtkoppen: <ul><li>AAR: hiermee wordt de inhoud van de berichtkop met verificatieresultaten van DMARC vastgelegd.</li><li>AMS: deze kop bevat cryptografische handtekeningen van het bericht.</li><li>AS: bevat cryptografische handtekeningen van de berichtkoppen. Deze koptekst bevat een tag voor een ketenvalidatie met de naam 'cv=', die het resultaat van de ketenvalidatie bevat als **none**, **pass** of **fail**.</li></ul>|
|CAT:|De categorie beveiligingsbeleid, toegepast op het bericht: <ul><li>BULK: bulk</li><li>DIMP: imitatie van domein</li><li>GIMP: Mailbox Intelligence</li><li>HPHSH or HPHISH: phishing van hoge waarschijnlijkheid </li><li>HSPM: spam van hoge waarschijnlijkheid</li><li>MALW: malware</li><li>PHSH: phishing</li><li>SPM: spam</li><li>SPOOF: spoofing</li><li>UIMP: imitatie van gebruiker</li></ul><br/>Een inkomend bericht kan zijn gemarkeerd door meerdere beveiligingswijzen en meerdere detectiescans. Beleidsregels hebben verschillende prioriteiten en de regel met de hoogste prioriteit wordt het eerst toegepast. Zie [Welke beleidsregel wordt toegepast wanneer meerdere beveiligingswijzen en detectiescans op uw e-mail worden uitgevoerd?](how-policies-and-protections-are-combined.md) voor meer informatie.|
|CIP: \[IP-adres\]|Het IP-verbindingsadres. U kunt dit IP-adres gebruiken in de IP-acceptatielijst of IP-blokkeringslijst. Zie [Verbindingsfiltering configureren](configure-the-connection-filter-policy.md) voor meer informatie.|
|CTRY|Het bronland wordt bepaald door het verbindings-IP-adres. Dit hoeft niet hetzelfde te zijn als het oorspronkelijke verzend-IP-adres.|
|H:\[helostring\]|De HELO- of EHLO-tekenreeks van de verbindende e-mailserver.|
|IPV:CAL|Het bericht is door het spamfilter overgeslagen omdat het bron-IP-adres in de IP-acceptatielijst vermeld staat. Zie [Verbindingsfiltering configureren](configure-the-connection-filter-policy.md) voor meer informatie.|
|IPV:NLI|Het IP-adres staat niet vermeld in de IP-reputatielijst.|
|LANG|De taal waarin het bericht is geschreven, zoals opgegeven door de landcode (bijvoorbeeld ru_RU voor Russisch).|
|PTR:\[ReverseDNS\]|De PTR-record (ook wel het omgekeerde DNS-adres genoemd) van het bron-IP-adres.|
|SCL|De spamwaarschijnlijkheidswaarde (SCL) van het bericht. Hoe hoger de waarde, hoe groter de kans dat het bericht spam is. Zie [Spamwaarschijnlijkheidswaarde (SCL)](spam-confidence-levels.md) voor meer informatie.|
|SFTY|Het bericht is geïdentificeerd als phishing en wordt tevens gemarkeerd met een van de volgende waarden: <ul><li>9.1: standaardwaarde. Het bericht bevat een phishing-URL, kan andere phishing-inhoud bevatten of kan zijn gemarkeerd als phishing door een ander e-mailfilter, zoals een on-premises versie van Exchange, voordat het bericht naar Microsoft 365 is doorgestuurd.</li><li>9.11: [Intra-org of self-to-self spoofing](anti-spoofing-protection.md#different-types-of-spoofing). Het bericht heeft antispoofing-controles niet doorstaan, waarbij het domein van de afzender in de berichtkop Van: hetzelfde is als, overeenkomt met, of deel uitmaakt van dezelfde organisatie als het ontvangende domein. De beveiligingstip over spoofing van binnen de organisatie wordt toegevoegd aan het bericht.</li><li>9.19: domeinimitatie. Het verzendende domein probeert zich voor te doen als een beveiligd domein (een domein dat eigendom is van de organisatie van de ontvanger of een aangepast domein), dat is gespecificeerd in een ATP-antiphishingbeleid. De veiligheidstip voor imitatie van een domein wordt aan het bericht toegevoegd (als de veiligheidstip is ingeschakeld in het ATP-antiphishingbeleid).</li><li>9.20: gebruikersimitatie. De verzendende gebruiker probeert zich voor te doen als een gebruiker in de organisatie van de ontvanger of als een beveiligde gebruiker die is gespecificeerd in een ATP-antiphishingbeleid. De veiligheidstip voor imitatie van een gebruiker wordt aan het bericht toegevoegd (als de veiligheidstip is ingeschakeld in het ATP-antiphishingbeleid).</li><li>9.21: [adresvervalsing tussen domeinen](anti-spoofing-protection.md#different-types-of-spoofing). Het bericht heeft antispoofingcontroles niet doorstaan en het domein van de afzender in de berichtkop Van: is niet geverifieerd en is afkomstig van een extern domein. Wordt gebruikt in combinatie met [CompAuth](#authentication-results-message-header-fields-used-by-microsoft-email-authentication)).</li><li>9.22: hetzelfde als 9.21, behalve dat de gebruiker een veilige afzender heeft die is overschreven.</li><li>9.23: hetzelfde als 9.22, behalve dat de organisatie een toegestane afzender of toegestaan domein heeft, waarbij een van de twee is overschreven.</li><li>9.24: hetzelfde als 9.23, behalve dat de gebruiker een Exchange-e-mailstroomregel (ook wel transportregel genoemd) heeft, die is overschreven.</li></ul>|
|SFV:BLK|Filteren is overgeslagen en het bericht is geblokkeerd omdat het is verzonden vanaf een adres in de lijst met geblokkeerde afzenders in Outlook van de gebruiker.<br/></br> Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken](configure-junk-email-settings-on-exo-mailboxes.md) voor meer informatie over de manier waarop beheerders de lijst met geblokkeerde afzenders van een gebruiker kunnen beheren.|
|SFV:NSPM|Het bericht is gemarkeerd als niet-spam en is verzonden naar de beoogde geadresseerden.|
|SFV:SFE|Filteren is overgeslagen en het bericht is doorgelaten omdat het is verzonden vanaf een adres in de lijst met veilige afzenders in Outlook van de gebruiker.<br/></br> Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken](configure-junk-email-settings-on-exo-mailboxes.md) voor meer informatie over de manier waarop beheerders de lijst met veilige afzenders van een gebruiker kunnen beheren.|
|SFV:SKA|Het bericht is door het spamfilter overgeslagen en is bezorgd in het Postvak IN, omdat het overeenkomt met een vermelding in een lijst met toegestane afzenders of een lijst met toegestane domeinen in een antispambeleidsregel. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|SFV:SKB|Het bericht is gemarkeerd als spam, omdat het overeenkomt met een vermelding in een lijst met geblokkeerde afzenders of geblokkeerde domeinen in een antispambeleidsregel. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|SFV:SKI|Soortgelijk als SFV: SKN; het bericht is om een andere reden door het spamfilter overgeslagen (bijvoorbeeld een e-mail van binnen een organisatie binnen een tenant).|
|SFV:SKN|Het bericht is gemarkeerd als niet-spam voordat het is verwerkt door het spamfilter (het bericht is bijvoorbeeld gemarkeerd als SCL-1 of **Spamfilter omzeilen**).|
|SFV:SKQ|Het bericht is vrijgegeven uit quarantaine en is verzonden naar de beoogde geadresseerden.|
|SFV:SKS|Het bericht is gemarkeerd als spam voordat het is verwerkt door het spamfilter (het bericht is bijvoorbeeld gemarkeerd als SCL 5 t/m 9).|
|SFV:SPM|Het bericht is gemarkeerd als spam.|
|SRV:BULK|Het bericht is geïdentificeerd als bulk-e-mail door het spamfilter en de drempelwaarde van het bulkklachtniveau (BCL). Als parameter _MarkAsSpamBulkMail_ `On` is (standaard ingeschakeld), wordt een bulk-e-mailbericht gemarkeerd als spam van hoge waarschijnlijkheid (SCL 9). Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|X-CustomSpam: \[ASFOption\]|Het bericht komt overeen met een instelling voor Geavanceerd spamfilter (ASF). Zie [Instellingen voor geavanceerd spamfilter (ASF)](advanced-spam-filtering-asf-options.md) als u de waarde van de X-header voor elke ASF-instelling wilt zien.|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>Berichtkopvelden van de vorm X-Microsoft-Antispam

In de volgende tabel worden nuttige velden in de berichtkop **X-Microsoft-Antispam** beschreven. Andere velden in deze kop worden uitsluitend door het Microsoft-antispamteam voor diagnostische doeleinden gebruikt.

|||
|---|---|
|**Berichtkopveld**|**Beschrijving**|
|BCL|Het bulkklachtniveau (BCL) van het bericht. Een hogere BCL duidt op een bulk-e-mailbericht (ook wel _gray mail_ genoemd) en levert vermoedelijk meer klachten op (en is dus vermoedelijk spam). Zie [Bulkklachtniveau (BCL)](bulk-complaint-level-values.md) voor meer informatie.|
|

## <a name="authentication-results-message-header"></a>Berichtkop Authentication-results

De resultaten van controles op SPF, DKIM en DMARC worden met Microsoft 365 vastgelegd of gestempeld in de berichtkop **Authentication-results** als de e-mailservers een e-mailbericht ontvangen.

### <a name="check-stamp-syntax-and-examples"></a>Syntaxis van controlestempel, met voorbeelden

De volgende voorbeelden van syntaxis tonen een deel van het 'tekststempel' dat met Microsoft 365 op elk e-mailbericht dat een e-mailverificatiecontrole ondergaat wanneer het op de e-mailservers wordt ontvangen, wordt toegepast op de berichtkop. Het stempel wordt toegevoegd aan de berichtkop **Authentication-Results**.

#### <a name="syntax-spf-check-stamp"></a>Syntaxis: SPF-controlestempel

Voor SPF geldt de volgende syntaxis.

```text
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

##### <a name="examples-spf-check-stamp"></a>Voorbeelden: SPF-controlestempel

```text
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
```

#### <a name="syntax-dkim-check-stamp"></a>Syntaxis: DKIM-controlestempel

Voor DKIM geldt de volgende syntaxis.

```text
dkim=<pass|fail (reason)|none> header.d=<domain>
```

##### <a name="examples-dkim-check-stamp"></a>Voorbeelden: DKIM-controlestempel

```text
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

#### <a name="syntax-dmarc-check-stamp"></a>Syntaxis: DMARC-controlestempel

Voor DMARC geldt de volgende syntaxis.

```text
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

##### <a name="examples-dmarc-check-stamp"></a>Voorbeelden: DMARC-controlestempel

```text
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-microsoft-email-authentication"></a>Berichtkopvelden van de vorm Authentication-results die door e-mailverificatie van Microsoft worden gebruikt

In deze tabel worden de velden en mogelijke waarden voor elke e-mailverificatie beschreven.

|||
|---|---|
|**Berichtkopveld**|**Beschrijving**|
|actie|Hiermee wordt aangegeven welke actie door het spamfilter is uitgevoerd op basis van de resultaten van de DMARC-controle. Bijvoorbeeld: <ul><li>**oreject** of **o.reject**: staat voor weigering negeren. In dit geval gebruikt Microsoft 365 deze actie als een bericht wordt ontvangen dat de DMARC-controle niet doorstaat van een domein met een DMARC TXT-record met beleidsregel p=reject. In plaats van het bericht te verwijderen of te weigeren, wordt het bericht in Microsoft 365 als spam gemarkeerd. Zie [Verwerken van inkomende e-mailberichten in Microsoft 365 die DMARC niet doorstaan](use-dmarc-to-validate-email.md#how-microsoft-365-handles-inbound-email-that-fails-dmarc) voor meer informatie over de manier waarom Microsoft 365 op deze manier wordt geconfigureerd.</li><li>**pct.quarantine**: hiermee wordt aangegeven dat minder dan 100% van de berichten die DMARC niet doorstaan, toch wordt bezorgd. Dit betekent dat het bericht DMARC niet heeft doorstaan en dat de beleidsregel is ingesteld op quarantine, maar dat het percentageveld niet is ingesteld op 100% en dat het systeem willekeurig heeft bepaald dat de actie DMARC niet wordt toegepast, conform het beleid van het opgegeven domein.</li><li>**pct.reject**: hiermee wordt aangegeven dat minder dan 100% van de berichten die DMARC niet doorstaan, toch wordt bezorgd. Dit betekent dat het bericht DMARC niet heeft doorstaan en dat de beleidsregel is ingesteld op reject, maar dat het percentageveld niet is ingesteld op 100% en dat het systeem willekeurig heeft bepaald dat de actie DMARC niet wordt toegepast, conform het beleid van het opgegeven domein.</li><li>**permerror**: er is een permanente fout opgetreden tijdens de DMARC-evaluatie, zoals bij een verkeerd geformuleerd DMARC TXT-record in DNS. Het opnieuw verzenden van dit bericht, leidt hoogstwaarschijnlijk tot hetzelfde resultaat. U kunt contact opnemen met de eigenaar van het domein om het probleem op te lossen.</li><li>**temperror**: er is een tijdelijke fout opgetreden tijdens de DMARC-evaluatie. U kunt de afzender vragen het bericht later opnieuw te verzenden om het e-mailbericht correct te kunnen verwerken.</li></ul>|
|compauth|Resultaat van samengestelde verificatie. Wordt gebruikt voor Microsoft 365 om meerdere typen verificatie te combineren, zoals SPF, DKIM, DMARC of een ander deel van het bericht om te bepalen of het bericht al dan niet wordt geverifieerd. Hierbij wordt het domein Van: gebruikt als basis voor de evaluatie.|
|dkim|Beschrijft de resultaten van de DKIM-controle van het bericht. Mogelijke waarden zijn: <ul><li>**pass**: hiermee wordt aangegeven dat de DKIM-controle van het bericht is geslaagd.</li><li>**fail (reden)**: hiermee wordt aangegeven dat de DKIM-controle van het bericht is mislukt en de reden waarom. Bijvoorbeeld als het bericht niet is ondertekend of als de handtekening niet is gecontroleerd.</li><li>**none**: hiermee wordt aangegeven dat het bericht niet is ondertekend. Dit kan al of niet betekenen dat het domein een DKIM-record heeft of dat het DKIM-record geen resultaat oplevert. Het betekent in elk geval dat dit bericht niet is ondertekend.</li></ul>|
|dmarc|Beschrijft de resultaten van de DMARC-controle van het bericht. Mogelijke waarden zijn: <ul><li>**pass**: hiermee wordt aangegeven dat de DMARC-controle van het bericht is geslaagd.</li><li>**fail**: hiermee wordt aangegeven dat de DMARC-controle van het bericht is mislukt.</li><li>**bestguesspass**: hiermee wordt aangegeven dat er geen DMARC TXT-record voor het domein aanwezig is, maar dat indien er wel een zou zijn de DMARC-controle van het bericht zou zijn geslaagd. Dit komt omdat het domein in het `5321.MailFrom`-adres (ook wel MAIL FROM-adres, P1-afzender of envelopafzender genoemd), overeenkomt met het domein in het `5322.From`-adres (ook wel Van-adres of P2-afzender genoemd).</li><li>**none**: hiermee wordt aangegeven dat er geen DMARC TXT-record aanwezig is voor het verzendende domein in DNS.|
|header.d|Domein dat is geïdentificeerd in de DKIM-handtekening, voor zover aanwezig. Dit is het domein waarop een query wordt uitgevoerd voor de openbare sleutel.|
|header.from|Het domein van het `5322.From`-adres de berichtkop van het e-mailbericht (ook wel Van-adres of P2-afzender genoemd). Geadresseerden zien het Van-adres in e-mailclients.|
|reason|De reden waarom de samengestelde verificatie is geslaagd of mislukt. De waarde is een code van drie cijfers. Bijvoorbeeld: <ul><li>**000**: het bericht heeft de verificatie expliciet niet doorstaan (`compauth=fail`). Bijvoorbeeld: het bericht heeft een DMARC-controle niet doorstaan met de actie Quarantine of Weigeren.</li><li>**001**: het bericht heeft impliciete verificatie niet doorstaan (`compauth=fail`). Dit houdt in dat het verzendende domein geen e-mail records voor e-mailverificatie heeft gepubliceerd of dat ze een zwakker foutbeleid hanteerden (SPF-softfail of Neutraal, DMARC-beleid `p=none`).</li><li>**002**: de organisatie heeft een beleid voor het afzender/domein-paar dat expliciet is uitgesloten van het verzenden van vervalste e-mail. Deze instelling wordt handmatig ingesteld door een beheerder.</li><li>**010**: het bericht is verworpen door DMARC met als actie weigering of quarantaine, en het verzendende domein is een van de geaccepteerde domeinen van uw organisatie (dit is onderdeel van self-to-self- of intra-org-adresvervalsing).</li><li>**1xx** of **7xx**: het bericht heeft de verificatie doorstaan (`compauth=pass`). De twee laatste cijfers zijn interne codes die voor Microsoft 365 worden gebruikt.</li><li>**2xx**: het bericht heeft de verificatie doorstaan met resultaat 'soft-pass' (`compauth=softpass`). De twee laatste cijfers zijn interne codes die voor Microsoft 365 worden gebruikt.</li><li>**3xx**: het bericht is niet gecontroleerd op samengestelde verificatie (`compauth=none`).</li><li>**4xx** of **9xx**: het bericht heeft samengestelde verificatie omzeild (`compauth=none`). De twee laatste cijfers zijn interne codes die voor Microsoft 365 worden gebruikt.</li><li>**6xx**: het bericht is verworpen door impliciete e-mailverificatie, en het verzendende domein is een van de geaccepteerde domeinen van uw organisatie (dit is onderdeel van self-to-self- of intra-org-adresvervalsing).</li></ul>|
|smtp.mailfrom|Het domein van het `5321.MailFrom`-adres (ook wel MAIL FROM-adres, P1-afzender of envelopafzender genoemd). Dit is het e-mailadres dat voor rapporten over niet-uitgevoerde bezorging wordt gebruikt (ook wel NDR's of niet-bezorgberichten genoemd).|
|spf|Beschrijft de resultaten van de SPF-controle van het bericht. Mogelijke waarden zijn: <ul><li>**pass (IP-adres)**: hiermee wordt aangegeven dat de SPF-check van het bericht is geslaagd, en het bevat het IP-adres van de afzender. De client wordt geautoriseerd e-mail te verzenden of door te sturen namens het domein van de afzender.</li><li>**fail (IP-adres)**: hiermee wordt aangegeven dat de SPF-check van het bericht is mislukt, en het bevat het IP-adres van de afzender. Dit wordt ook wel een _hard fail_ genoemd.</li><li>**softfail (reden)**: hiermee wordt aangegeven dat door het SPF-record is bepaald dat de host niet mag verzenden, maar dat deze zich in een overgangsfase bevindt.</li><li>**neutral**: hiermee wordt aangegeven dat door het SPF-record expliciet is vastgelegd dat het niet bepaalt of het IP-adres is geautoriseerd.</li><li>**none**: hiermee wordt aangegeven dat het domein geen SPF-record heeft of dat het SPF-record niet tot een resultaat leidt.</li><li>**temperror**: hiermee wordt aangegeven dat er een fout is opgetreden die tijdelijk van aard kan zijn, bijvoorbeeld een DNS-fout. U kunt het later opnieuw proberen zonder dat een ingreep door een beheerder vereist is.</li><li>**permerror**: hiermee wordt aangegeven dat er een permanente fout is opgetreden. Dit treedt bijvoorbeeld op als het domein een foutief ingedeeld SPF-record heeft.</li></ul>|
|
