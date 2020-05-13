---
title: Lijsten met veilige afzenders maken
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer te weten komen over de beschikbare en voorkeursopties om binnenkomende berichten toe te staan in Exchange Online Protection (EOP).
ms.openlocfilehash: 3ef05c919a86bc3458cceb2a2bc73522e16e4bb1
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209533"
---
# <a name="create-safe-sender-lists-in-eop"></a>Lijsten met veilige afzenders maken in EOP

Als u een Microsoft 365-klant bent met postvakken in Exchange Online of een zelfstandige Exchange Online Protection(EOP)-klant zonder Exchange Online-postvakken, biedt EOP meerdere manieren om ervoor te zorgen dat gebruikers e-mail van vertrouwde afzenders ontvangen. Deze opties omvatten Exchange-mailstroomregels (ook wel transportregels genoemd), Outlook Safe Senders, de IP-lijst toestaan (verbindingsfiltering) en toegestane afzenderlijsten of toegestane domeinlijsten in antispambeleid. Gezamenlijk u deze opties zien als _lijsten met veilige afzenders._

De beschikbare lijsten met veilige afzenders worden in de volgende lijst beschreven in volgorde van de meest aanbevolen tot de minst aanbevolen:

1. Regels voor e-mailstromen
2. Outlook-veilige afzenders
3. Lijst met IP-regels (verbindingsfiltering)
4. Toegestane afzenderlijsten of toegestane domeinlijsten (antispambeleid)

Regels voor e-mailstroom bieden de meeste flexibiliteit om ervoor te zorgen dat alleen de juiste berichten zijn toegestaan. Toegestane afzender- en toegestane domeinlijsten in antispambeleid zijn niet zo veilig als de LIJST met IP-toegestane lijsten, omdat het e-maildomein van de afzender gemakkelijk kan worden vervalst. Maar de IP-lijst toestaan brengt ook een risico met zich mee, omdat e-mail van _elk_ domein dat vanaf dat IP-adres wordt verzonden, spamfilters omzeilt.

> [!IMPORTANT]
> • Let erop dat *u eventuele* uitzonderingen op spamfilter seert met behulp van veilige afzenderlijsten. <br/><br/> • Hoewel u veilige afzenderlijsten gebruiken om te helpen met valse positieven (goede e-mail gemarkeerd als spam), moet u het gebruik van veilige afzenderlijsten beschouwen als een tijdelijke oplossing die indien mogelijk moet worden vermeden. We raden u aan valse positieven te beheren met behulp van lijsten met veilige afzenders, omdat uitzonderingen op spamfiltering uw organisatie kunnen openen voor spoofing en andere aanvallen. Als u erop staat veilige afzenderlijsten te gebruiken om fout-positieven te beheren, moet u waakzaam zijn en het onderwerp [Berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md) in de aanslag houden. <br/><br/> • Om een domein toe te staan om niet-geverifieerde e-mail te verzenden (bypass anti-spoofing bescherming), maar niet te omzeilen anti-spam en anti-malware controles, u het toevoegen aan de [AllowedToSpoof veilige afzender lijst](walkthrough-spoof-intelligence-insight.md) <br/><br/> • EOP en Outlook inspecteren verschillende berichteigenschappen om de afzender van het bericht te bepalen. Zie de sectie [Overwegingen voor bulke-mail](#considerations-for-bulk-email) later in dit onderwerp voor meer informatie.

U hebt daarentegen ook verschillende opties om e-mail van specifieke bronnen te blokkeren met behulp van _geblokkeerde afzenderlijsten._ Zie [Lijsten met blokafzenders maken in EOP](create-block-sender-lists-in-office-365.md)voor meer informatie.

## <a name="recommended-use-mail-flow-rules"></a>(Aanbevolen) Regels voor e-mailstromen gebruiken

E-mailstroomregels in Exchange Online en zelfstandige EOP gebruiken voorwaarden en uitzonderingen om berichten te identificeren en acties om aan te geven wat er met die berichten moet worden gedaan. Zie [E-mailstroomregels (transportregels) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)voor meer informatie.

In het volgende voorbeeld wordt ervan uitgegaan dat u e-mail van contoso.com nodig hebt om spamfilters over te slaan. Configureer hiervoor de volgende instellingen:

1. **Voorwaarde**: **Het** \> **afzenderdomein is** \> contoso.com.

2. Een van de volgende instellingen configureren:

   - **Voorwaarde voor e-mailstroomregel:** **een berichtkop** \> **bevat een van deze woorden** \> **Koptekstnaam:** `Authentication-Results` \> **Kopwaarde**: of `dmarc=pass` `dmarc=bestguesspass` .

     Met deze voorwaarde wordt de verificatiestatus van afzenders van het verzendende e-maildomein gecontroleerd om ervoor te zorgen dat het verzendende domein niet wordt vervalst. Zie [SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)en [DMARC](use-dmarc-to-validate-email.md)voor meer informatie over e-mailverificatie.

   - **Lijst met IP-regels:** geef het bron-IP-adres of adresbereik op in het beleid voor verbindingsfilter.
  
     Gebruik deze instelling als het verzendende domein geen verificatie heeft. Wees zo restrictief mogelijk als het gaat om de bron IP-adressen in de IP-lijst toestaan. Wij raden een IP-adres bereik van / 24 of minder (minder is beter). Gebruik geen IP-adresbereiken die behoren tot consumentendiensten (bijvoorbeeld outlook.com) of gedeelde infrastructuren.

   > [!IMPORTANT]
   > <ul><li>Configureer nooit regels voor e-mailstromen met *alleen* het afzenderdomein als voorwaarde om spamfilters over te slaan. Als u dit doet, *wordt* de kans aanzienlijk groter dat aanvallers het verzendende domein kunnen spoofen (of zich kunnen voordoen als het volledige e-mailadres), alle spamfilters overslaan en verificatiecontroles voor afzenders overslaan, zodat het bericht in het Postvak IN van de ontvanger wordt weergegeven.</li><li>Gebruik geen domeinen die u bezit (ook wel geaccepteerde domeinen genoemd) of populaire domeinen (bijvoorbeeld microsoft.com) als voorwaarden in de regels voor e-mailstromen. Hierdoor wordt beschouwd als een hoog risico, omdat het kansen creëert voor aanvallers om e-mail te verzenden die anders zou worden gefilterd.</li><li>Als u een IP-adres toestaat dat zich achter een NAT-gateway (Network Address Translation) bevindt, moet u de servers kennen die betrokken zijn bij de NAT-groep om het bereik van uw IP-lijst met toegestane gegevens te kennen. IP-adressen en NAT-deelnemers kunnen wijzigen. U moet uw IP-lijstvermeldingen voor statoestaan regelmatig controleren als onderdeel van uw standaardonderhoudsprocedures.</li></ul>

3. **Facultatieve voorwaarden**:

   - **De afzender** \> **is intern/extern** \> **Buiten de organisatie**: Deze voorwaarde is impliciet, maar het is OK om deze te gebruiken om rekening te houden met on-premises e-mailservers die mogelijk niet correct zijn geconfigureerd.

   - **Het onderwerp of lichaam** \> **onderwerp of lichaam bevat een van deze woorden** \> \< \> trefwoorden: Als u de berichten verder beperken op trefwoorden of woordgroepen in de onderwerpregel of berichttekst, u deze woorden als voorwaarde gebruiken.

4. **Actie:** Configureer beide acties in de regel:

   a. **De berichteigenschappen** \> wijzigen **stel het spambetrouwbaarheidsniveau (SCL)** \> in **Spamfiltering omzeilen.**

   b. **Een berichtkoptekst** \> **bevat een van deze woorden** \> **Naam van koptekst:** \< waarde van de CustomHeaderName-header: \> **Header value** \< CustomHeaderValue \> .

      Bijvoorbeeld `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`. Als u meer dan één domein in de regel hebt, u de koptekst naar gelang van het geval aanpassen.

      Wanneer een bericht spamfilters overslaat vanwege een e-mailstroomregel, wordt de `SFV:SKN` waardewaarde gestempeld in de header **X-Forefront-Antispam-Report.** Als het bericht afkomstig is van een bron die zich op de lijst met IP-toegestane gegevens bevindt, wordt de waarde `IPV:CAL` ook toegevoegd. Deze waarden kunnen u helpen bij het oplossen van problemen.

![Instellingen voor e-mailstroomregels in de EAC voor het omzeilen van spamfiltering.](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Outlook Safe Senders gebruiken

In plaats van een organisatieinstelling kunnen gebruikers of beheerders de e-mailadressen van de afzender toevoegen aan de lijst Veilige afzenders in het postvak. Zie Instellingen [voor ongewenste e-mail configureren in Exchange Online-postvakken in Office 365](configure-junk-email-settings-on-exo-mailboxes.md)voor instructies. Dit is niet wenselijk in de meeste situaties, omdat afzenders delen van de filterstapel zullen omzeilen. Hoewel u de afzender vertrouwt, kunnen de verzenderblikken nog steeds worden gecompromitteerd en kunnen schadelijke inhoud verzenden. Het is het beste dat u onze filters laat doen wat nodig is om elk bericht te controleren en vervolgens [het false positive/negative aan Microsoft te melden](report-junk-email-messages-to-microsoft.md) als onze filters het verkeerd hebben. Het omzeilen van de filterstapel interfereert ook met [ZAP.](zero-hour-auto-purge.md)

Wanneer berichten spamfilters overslaan vanwege de lijst Met veilige afzenders van een gebruiker, bevat het headerveld **X-Forefront-Antispam-Report** de waarde `SFV:SFE` , wat aangeeft dat spam, spoof en phish-filtering zijn omzeild.

## <a name="use-the-ip-allow-list"></a>De lijst met IP-toegestane gebruiken

Als u geen e-mailstroomregels gebruiken zoals eerder beschreven, u de volgende beste optie toevoegen aan de lijst met brone-mailgegevens in het verbindingsfilterbeleid. Zie [Verbindingsfiltering configureren in EOP](configure-the-connection-filter-policy.md)voor meer informatie.

**Opmerkingen**:

- Het is belangrijk dat u het aantal toegestane IP-adressen tot een minimum beperkt, dus vermijd het gebruik van volledige IP-adresbereiken waar mogelijk.

- Gebruik geen IP-adresbereiken die behoren tot consumentendiensten (bijvoorbeeld outlook.com) of gedeelde infrastructuren.

- Controleer regelmatig de vermeldingen in de LIJST MET IP-toegestane items en verwijder de items die u niet meer nodig hebt.

> [!CAUTION]
> Zonder extra verificatie, zoals regels voor e-mailstroom, worden bij e-mailvan bronnen in de LIJST IP-status toestaan spamfilters en afzenderverificatie (SPF, DKIM, DMARC) overgeslagen. Dit creëert een hoog risico dat aanvallers met succes e-mail leveren aan het Postvak IN dat anders zou worden gefilterd.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>Toegestane afzenderlijsten of toegestane domeinlijsten gebruiken

De minst wenselijke optie is om de toegestane afzenderlijst of toegestane domeinlijst te gebruiken in antispambeleid. U moet deze optie zo *mogelijk* vermijden, omdat afzenders alle spam-, spoof- en phish-beveiliging en afzenderverificatie (SPF, DKIM, DMARC) omzeilen. Deze methode wordt het best alleen gebruikt voor tijdelijke tests. De gedetailleerde stappen zijn te vinden in [Antispambeleid configureren in het EOP-onderwerp.](configure-your-spam-filter-policies.md)

De maximumlimiet voor deze lijsten is ongeveer 1000 vermeldingen; hoewel, u zult slechts 30 ingangen in de portaal kunnen ingaan. U moet PowerShell gebruiken om meer dan 30 vermeldingen toe te voegen.

> [!CAUTION]
> <ul><li>Deze methode creëert een hoog risico dat aanvallers met succes e-mail leveren aan het Postvak IN dat anders zou worden gefilterd.</li><li>Gebruik geen domeinen die u bezit (ook wel geaccepteerde domeinen genoemd) of populaire domeinen (bijvoorbeeld microsoft.com) in toegestane domeinlijsten.</li></ul>

## <a name="considerations-for-bulk-email"></a>Overwegingen voor bulke-mail

Een standaard SMTP-e-mailbericht bestaat uit een *berichtenvelop* en berichtinhoud. De berichtenvelop bevat informatie die nodig is voor het verzenden en leveren van het bericht tussen SMTP-servers. De inhoud van het bericht bevat teksttekstvelden (gezamenlijk de *berichtkop genoemd)* en de berichttekst. De berichtenvelop wordt beschreven in RFC 5321 en de berichtkop wordt beschreven in RFC 5322. Ontvangers zien nooit de werkelijke berichtenvelop omdat deze wordt gegenereerd door het berichtoverdrachtsproces en het is eigenlijk geen onderdeel van het bericht.

- Het `5321.MailFrom` adres (ook bekend als het **e-mailadres van** het adres, de afzender van P1 of de afzender van de envelop) is het e-mailadres dat wordt gebruikt in de SMTP-transmissie van het bericht. Dit e-mailadres wordt meestal opgenomen in het koptekstveld **Return-Path** in de berichtkop (hoewel het mogelijk is dat de afzender een ander **e-mailadres van het retourpad** aanwijst). Als het bericht niet kan worden bezorgd, is het de ontvanger voor het rapport niet-bezorging (ook wel een NDR- of bouncebericht genoemd).

- Het `5322.From` (ook wel bekend als de **Afzender Van** of P2) is het e-mailadres in het veld **Van** koptekst en is het e-mailadres van de afzender dat wordt weergegeven in e-mailclients.

Vaak zijn de `5321.MailFrom` en `5322.From` adressen hetzelfde (persoonlijke communicatie). Wanneer e-mail echter namens iemand anders wordt verzonden, zijn de adressen vaak verschillend. Dit gebeurt meestal voor bulk e-mailberichten.

Stel dat Blue Yonder Airlines Margie's Travel heeft ingehuurd om zijn e-mailadvertenties uit te sturen. Het bericht dat u in uw Postvak IN ontvangt, heeft de volgende eigenschappen:

- Het `5321.MailFrom` adres is blueyonder.airlines@margiestravel.com.

- Het `5322.From` adres is blueyonder@news.blueyonderairlines.com, dat is wat je ziet in Outlook.

Veilige afzenderlijsten en veilige domeinlijsten in antispambeleid in EOP inspecteren zowel de adressen als de `5321.MailFrom` `5322.From` adressen. Outlook Safe Senders gebruikt alleen het `5322.From` adres.

Om te voorkomen dat dit bericht wordt gefilterd, u de volgende stappen uitvoeren:

- Voeg blueyonder@news.blueyonderairlines.com (het adres) toe `5322.From` als veilige afzender van Outlook.

- [Gebruik een e-mailstroomregel](#recommended-use-mail-flow-rules) met een voorwaarde die zoekt naar berichten van blueyonder@news.blueyonderairlines.com (het `5322.From` adres, blueyonder.airlines@margiestravel.com (de `5321.MailFrom` ) of beide.

Zie [Lijsten met veilige afzenders maken in EOP](create-safe-sender-lists-in-office-365.md)voor meer informatie.
