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
description: Beheerders kunnen meer te weten komen over de beschikbare en gewenste opties om binnenkomende berichten toe te staan in Exchange Online Protection (EOP).
ms.openlocfilehash: 9ca1fc3911dd3417304d0d1de6923408373bc33c
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005856"
---
# <a name="create-safe-sender-lists-in-eop"></a>Veilige afzenderlijsten maken in EOP

Als u een Microsoft 365-klant bent met postvakken in Exchange Online of een zelfstandige EOP-klant (Exchange Online Protection) zonder Exchange Online-postvakken, biedt EOP meerdere manieren om ervoor te zorgen dat gebruikers e-mail ontvangen van vertrouwde afzenders. Deze opties omvatten Exchange-regels voor e-mailstroom (ook wel transportregels genoemd), Outlook Safe Senders, de IP Allow List (verbindingsfiltering) en toegestane afzenderlijsten of toegestane domeinlijsten in antispambeleid. Samen u deze opties zien als _veilige afzenderlijsten._

De beschikbare lijsten met veilige afzenders worden beschreven in de volgende lijst, zodat van de meest aanbevolen tot minst aanbevolen volgorde:

1. Regels voor e-mailstroom
2. Veilige afzenders van Outlook
3. LIJST MET IP-toestaan (verbindingsfilter)
4. Toegestane afzenderlijsten of toegestane domeinlijsten (antispambeleid)

Mailflowregels bieden de meeste flexibiliteit om ervoor te zorgen dat alleen de juiste berichten zijn toegestaan. Toegestane afzender en toegestane domeinlijsten in antispambeleid zijn niet zo veilig als de IP Allow List, omdat het e-maildomein van de afzender gemakkelijk kan worden vervalst. Maar de IP Allow List vormt ook een risico, omdat e-mail van _elk_ domein dat vanaf dat IP-adres wordt verzonden, spamfiltering zal omzeilen.

> [!IMPORTANT]
> • Houd alle *uitzonderingen* die u op spamfiltert nauwlettend in de gaten met veilige afzenderlijsten. <br/><br/> • Hoewel u veilige afzenderlijsten gebruiken om te helpen met valse positieven (goede e-mail gemarkeerd als spam), moet u het gebruik van lijsten met veilige afzenders beschouwen als een tijdelijke oplossing die indien mogelijk moet worden vermeden. We raden je af om false positives te beheren door veilige afzenderlijsten te gebruiken, omdat uitzonderingen op spamfiltering uw organisatie kunnen openen voor spoofing en andere aanvallen. Als u erop staat om veilige afzenderlijsten te gebruiken om false positives te beheren, moet u waakzaam zijn en het onderwerp [Rapporteren berichten en bestanden aan Microsoft](report-junk-email-messages-to-microsoft.md) in de aanslag houden. <br/><br/> • Om een domein toe te staan om ongeautoriseerde e-mail te verzenden (bypass anti-spoofing bescherming), maar niet omzeilen anti-spam en anti-malware controles, u deze toevoegen aan de [AllowedToSpoof veilige afzender lijst](walkthrough-spoof-intelligence-insight.md) <br/><br/> • EOP en Outlook inspecteren verschillende berichteigenschappen om de afzender van het bericht te bepalen. Zie de sectie [Overwegingen voor bulke-mail](#considerations-for-bulk-email) later in dit onderwerp voor meer informatie.

Daarentegen hebt u ook verschillende opties om e-mail te blokkeren van specifieke bronnen met behulp van _geblokkeerde afzenderlijsten._ Zie [Lijsten met geblokkeerde afzenders maken in EOP](create-block-sender-lists-in-office-365.md) voor meer informatie.

## <a name="recommended-use-mail-flow-rules"></a>(Aanbevolen) Regels voor e-mailstroom gebruiken

Regels voor e-mailstroom in Exchange Online en zelfstandige EOP gebruiken voorwaarden en uitzonderingen om berichten te identificeren en acties om aan te geven wat er met die berichten moet worden gedaan. Zie [Regels voor e-mailstroom (transportregels) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)voor meer informatie.

In het volgende voorbeeld wordt ervan uitgegaan dat u e-mail van contoso.com nodig hebt om spamfilters over te slaan. Configureer hiervoor de volgende instellingen:

1. **Voorwaarde**: **Het** \> **afzenderdomein is** \> contoso.com.

2. Een van de volgende instellingen configureren:

   - **Voorwaarde voor de regel van de e-mailstroomregel**: **een berichtkoptekst** \> **bevat een van de woorden** \> **Koptekstnaam**: `Authentication-Results` \> **Koptekstwaarde**: of `dmarc=pass` `dmarc=bestguesspass` .

     Met deze voorwaarde wordt de verificatiestatus van de afzender van het verzendende e-maildomein gecontroleerd om ervoor te zorgen dat het verzendende domein niet wordt vervalst. Zie [SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)en [DMARC](use-dmarc-to-validate-email.md)voor meer informatie over e-mailverificatie.

   - **LIJST MET IP-toestaan:** geef het bron-IP-adres of adresbereik op in het verbindingsfilterbeleid.
  
     Gebruik deze instelling als het verzendende domein geen verificatie heeft. Wees zo beperkend mogelijk als het gaat om de bron-IP-adressen in de IP Allow List. Wij raden een IP-adres bereik van / 24 of minder (minder is beter). Gebruik geen IP-adresbereiken die behoren tot consumentendiensten (bijvoorbeeld outlook.com) of gedeelde infrastructuren.

   > [!IMPORTANT]
   > <ul><li>Configureer nooit configureer e-mailstroomregels met *alleen* het afzenderdomein als voorwaarde om spamfilters over te slaan. Hierdoor wordt de kans *aanzienlijk* groter dat aanvallers het verzendende domein kunnen spoofen (of zich voordoen als het volledige e-mailadres), alle spamfilters kunnen overslaan en verificatiecontroles van afzenders kunnen overslaan, zodat het bericht in het Postvak IN van de ontvanger terechtkomt.</li><li>Gebruik geen domeinen die u bezit (ook wel geaccepteerde domeinen genoemd) of populaire domeinen (bijvoorbeeld microsoft.com) als voorwaarden in de regels voor e-mailstroom. Dit wordt beschouwd als een hoog risico omdat het mogelijkheden creëert voor aanvallers om e-mail te verzenden die anders zou worden gefilterd.</li><li>Als u een IP-adres toestaat dat zich achter een NAT-gateway (Network Address Translation) bevindt, moet u de servers kennen die betrokken zijn bij de NAT-groep om het bereik van uw IP Allow List te weten. IP-adressen en NAT-deelnemers kunnen wijzigen. U moet uw IP Allow List-vermeldingen periodiek controleren als onderdeel van uw standaardonderhoudsprocedures.</li></ul>

3. **Facultatieve voorwaarden**:

   - **De afzender** \> **intern/extern** \> is **Buiten de organisatie**: Deze voorwaarde is impliciet, maar het is ok om deze te gebruiken om rekening te houden met on-premises e-mailservers die mogelijk niet correct zijn geconfigureerd.

   - **Het onderwerp of het lichaam** \> **onderwerp of lichaam bevat een van deze woorden** \> \<keywords\>: Als u de berichten verder beperken door trefwoorden of zinnen in de onderwerpregel of berichttekst, u deze woorden als voorwaarde gebruiken.

4. **Actie**: Configureer beide acties in de regel:

   a. **De berichteigenschappen** \> wijzigen **het spamvertrouwensniveau (SCL)** \> instellen **Omzeil spamfiltering**.

   b. **Een berichtkop** \> **bevat een van deze woorden** \> **Koptekstnaam**: \<CustomHeaderName\> **Koptekstwaarde**: \<CustomHeaderValue\> .

      Bijvoorbeeld `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`. Als u meer dan één domein in de regel hebt, u de koptekst naar gelang van het geval aanpassen.

      Wanneer een bericht spamfiltering overslaat vanwege een e-mailstroomregel, wordt de waarde `SFV:SKN` gestempeld in de kop **X-Forefront-Antispam-Report.** Als het bericht afkomstig is van een bron die op de LIJST met IP-toestaan staat, wordt de waarde `IPV:CAL` ook toegevoegd. Deze waarden kunnen u helpen bij het oplossen van problemen.

![Instellingen voor e-mailstroomregel in de EAC voor het omzeilen van spamfilters.](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Veilige afzenders van Outlook gebruiken

In plaats van een organisatieinstelling kunnen gebruikers of beheerders de e-mailadressen van de afzender toevoegen aan de lijst Veilige afzenders in het postvak. Zie Instellingen [voor ongewenste e-mail configureren in Exchange Online-postvakken configureren in Office 365](configure-junk-email-settings-on-exo-mailboxes.md)voor instructies. Dit is in de meeste situaties niet wenselijk, omdat afzenders delen van de filterstapel zullen omzeilen. Hoewel u de afzender vertrouwt, worden de blikjes van de afzender nog steeds gecompromitteerd en kunnen schadelijke inhoud worden verzonden. Het is het beste dat u onze filters laat doen wat nodig is om elk bericht te controleren en vervolgens [de false positive/negative aan Microsoft te melden](report-junk-email-messages-to-microsoft.md) als onze filters het verkeerd hebben. Het omzeilen van de filterstapel verstoort ook [ZAP](zero-hour-auto-purge.md).

Wanneer berichten spamfiltering overslaan vanwege de lijst Veilige afzenders van een gebruiker, bevat het kopveld **X-Forefront-Antispam-Report** de waarde `SFV:SFE` , wat aangeeft dat spam-, spoof- en phish-filtering is omzeild.

## <a name="use-the-ip-allow-list"></a>De lijst met IP-toestaan gebruiken

Als u geen regels voor e-mailstroom gebruiken zoals eerder beschreven, u de volgende beste optie zijn om de brone-mailserver of -servers toe te voegen aan de LIJST MET IP-toestaan in het verbindingsfilterbeleid. Zie [Verbindingsfiltering configureren in EOP](configure-the-connection-filter-policy.md)voor meer informatie.

**Opmerkingen**:

- Het is belangrijk dat u het aantal toegestane IP-adressen tot een minimum beperkt, dus vermijd het gebruik van volledige IP-adresbereiken waar mogelijk.

- Gebruik geen IP-adresbereiken die behoren tot consumentendiensten (bijvoorbeeld outlook.com) of gedeelde infrastructuren.

- Controleer regelmatig de vermeldingen in de LIJST MET IP-toestaan en verwijder de vermeldingen die u niet meer nodig hebt.

> [!CAUTION]
> Zonder extra verificatie, zoals e-mailstroomregels, slaat e-mail uit bronnen in de IP Allow List spamfiltering en afzenderverificatie (SPF, DKIM, DMARC) over. Dit creëert een hoog risico dat aanvallers met succes e-mail naar het Postvak IN leveren dat anders zou worden gefilterd.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>Lijsten met toegestane afzenders of toegestane domeinlijsten gebruiken

De minst wenselijke optie is het gebruik van de lijst met toegestane afzenders of de toegestane domeinlijst in het antispambeleid. U moet deze optie *zo mogelijk* vermijden omdat afzenders alle spam-, spoof- en phish-beveiliging en afzenderverificatie (SPF, DKIM, DMARC) omzeilen. Deze methode wordt het beste gebruikt voor tijdelijke testen alleen. De gedetailleerde stappen zijn te vinden in [Het beleid van het configureren van antispam in het EOP-onderwerp.](configure-your-spam-filter-policies.md)

De maximumlimiet voor deze lijsten is ongeveer 1000 vermeldingen; hoewel, u zult slechts in staat zijn om 30 inzendingen in te voeren in de portal. U moet PowerShell gebruiken om meer dan 30 vermeldingen toe te voegen.

> [!CAUTION]
> <ul><li>Deze methode creëert een hoog risico dat aanvallers met succes e-mail naar het Postvak IN leveren dat anders zou worden gefilterd.</li><li>Gebruik geen domeinen die u bezit (ook wel geaccepteerde domeinen genoemd) of populaire domeinen (bijvoorbeeld microsoft.com) in toegestane domeinlijsten.</li></ul>

## <a name="considerations-for-bulk-email"></a>Overwegingen voor bulke-mail

Een standaard SMTP-e-mailbericht bestaat uit een *berichtenvelop* en berichtinhoud. De berichtenenvelop bevat informatie die nodig is voor het verzenden en afleveren van het bericht tussen SMTP-servers. De berichtinhoud bevat berichtkopvelden (gezamenlijk de *berichtkop genoemd)* en de berichttekst. De berichtenenvelop wordt beschreven in RFC 5321 en de berichtkoptekst wordt beschreven in RFC 5322. Ontvangers zien nooit de werkelijke berichtenenvelop omdat deze wordt gegenereerd door het berichtoverdrachtsproces en het is eigenlijk geen onderdeel van het bericht.

- Het `5321.MailFrom` adres (ook bekend als het **E-mailadres,** P1 afzender of envelop afzender) is het e-mailadres dat wordt gebruikt in de SMTP-transmissie van het bericht. Dit e-mailadres wordt meestal opgenomen in het kopveld **Return-Path** in de berichtkop (hoewel het mogelijk is dat de afzender een ander **e-mailadres voor retourpad** aanwijst). Als het bericht niet kan worden bezorgd, is het de ontvanger voor het rapport niet-levering (ook wel een NDR- of bouncebericht genoemd).

- `5322.From`Het e-mailadres (ook wel bekend als het **van-adres** of de P2-afzender) is het e-mailadres in het veld **Van** koptekst en is het e-mailadres van de afzender dat wordt weergegeven in e-mailclients.

Vaak zijn de `5321.MailFrom` adressen en de adressen `5322.From` hetzelfde (persoonlijke communicatie). Wanneer e-mail echter namens iemand anders wordt verzonden, kunnen de adressen anders zijn. Dit gebeurt meestal voor bulk e-mailberichten.

Stel dat Blue Yonder Airlines Margie's Travel heeft ingehuurd om zijn e-mailadvertenties te verzenden. Het bericht dat u in uw Postvak IN ontvangt, heeft de volgende eigenschappen:

- Het `5321.MailFrom` adres is blueyonder.airlines@margiestravel.com.

- Het `5322.From` adres is blueyonder@news.blueyonderairlines.com, dat is wat u ziet in Outlook.

Veilige afzenderlijsten en veilige domeinlijsten in antispambeleid in EOP inspecteren alleen de `5322.From` adressen, dit is vergelijkbaar met Outlook Safe Senders die het `5322.From` adres gebruikt.

Als u wilt voorkomen dat dit bericht wordt gefilterd, u de volgende stappen uitvoeren:

- Voeg blueyonder@news.blueyonderairlines.com (het `5322.From` adres) toe als veilige afzender van Outlook.

- [Gebruik een e-mailstroomregel](#recommended-use-mail-flow-rules) met een voorwaarde die zoekt naar berichten van blueyonder@news.blueyonderairlines.com (het `5322.From` adres, blueyonder.airlines@margiestravel.com (de), `5321.MailFrom` of beide.

Zie [Veilige afzenderlijsten maken in EOP](create-safe-sender-lists-in-office-365.md)voor meer informatie.
