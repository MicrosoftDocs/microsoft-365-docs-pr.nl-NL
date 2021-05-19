---
title: Lijsten met veilige afzenders maken
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer informatie krijgen over de beschikbare en voorkeursopties om binnenkomende berichten toe te staan in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f76b34a439d2eaf2c8315d174483b0b30d3b3b0b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538757"
---
# <a name="create-safe-sender-lists-in-eop"></a>Lijsten met veilige afzenders maken in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Als u een Microsoft 365-klant bent met postvakken in Exchange Online of een zelfstandige Exchange Online Protection-klant (EOP) zonder Exchange Online-postvakken, biedt EOP meerdere manieren om ervoor te zorgen dat gebruikers e-mail ontvangen van vertrouwde afzenders. Deze opties zijn Exchange regels voor e-mailstroom (ook wel transportregels genoemd), Outlook Safe Afzenders, ip-lijst toestaan (verbindingsfiltering) en toegestane afzenderlijsten of toegestane domeinlijsten in antispambeleid. U kunt deze opties gezamenlijk zien als lijsten _met veilige afzenders._

De beschikbare lijsten met veilige afzenders worden in de volgende lijst beschreven in volgorde van meest aanbevolen tot minst aanbevolen:

1. Regels voor e-mailstroom
2. Outlook Safe afzenders
3. Ip Allow List (verbindingsfiltering)
4. Lijsten met toegestane afzenders of toegestane domeinlijsten (antispambeleid)

E-mailstroomregels bieden de meeste flexibiliteit om ervoor te zorgen dat alleen de juiste berichten zijn toegestaan. Toegestane afzender- en toegestane domeinlijsten in antispambeleid zijn niet zo veilig als de IP-lijst toestaan, omdat het e-maildomein van de afzender eenvoudig is vervalst. Maar de lijst met IP-toegestane gegevens  vormt ook een risico, omdat e-mail van elk domein dat vanaf dat IP-adres wordt verzonden spamfilters zal omzeilen.

> [!IMPORTANT]
>
> - Wees voorzichtig met het nauwlettend *controleren van eventuele* uitzonderingen die u maakt op spamfilters met behulp van lijsten met veilige afzenders.
>
> - Hoewel u lijsten met veilige afzenders kunt gebruiken om te helpen bij fout-positieven (goede e-mail die als slecht is gemarkeerd), moet u het gebruik van lijsten met veilige afzenders beschouwen als een tijdelijke oplossing die indien mogelijk moet worden vermeden. Het is niet raadzaam om false positives te beheren met behulp van lijsten met veilige afzenders, omdat uitzonderingen op spamfilters uw organisatie kunnen openen voor spoofing en andere aanvallen. Als u lijsten met veilige afzenders wilt gebruiken om fout-positieven te beheren, moet u op uw hoede zijn en het onderwerp Berichten en bestanden rapporteren bij [Microsoft](report-junk-email-messages-to-microsoft.md) gereed houden.
>
> - Als u wilt toestaan dat een domein niet-vervalste e-mail verzendt (bescherming tegen spoofing omzeilen), maar antispam- en anti-malwarecontroles niet wilt omzeilen, kunt u het inzicht in [spoofinformatie](learn-about-spoof-intelligence.md) en de [tenantlijst Toestaan/blokkeren gebruiken.](tenant-allow-block-list.md)
>
> - EOP en Outlook verschillende berichteigenschappen controleren om de afzender van het bericht te bepalen. Zie de sectie Overwegingen voor [bulk-e-mail](#considerations-for-bulk-email) verder in dit artikel voor meer informatie.

U hebt daarentegen ook verschillende opties om e-mail van specifieke bronnen te blokkeren met behulp _van lijsten met geblokkeerde afzenders._ Zie [Lijsten met geblokkeerde afzenders maken in EOP](create-block-sender-lists-in-office-365.md) voor meer informatie.

## <a name="recommended-use-mail-flow-rules"></a>(Aanbevolen) Regels voor e-mailstroom gebruiken

E-mailstroomregels in Exchange Online en zelfstandige EOP gebruiken voorwaarden en uitzonderingen om berichten te identificeren en acties om op te geven wat er met die berichten moet worden gedaan. Zie Regels voor [e-mailstroom (transportregels) in](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)Exchange Online.

In het volgende voorbeeld wordt ervan uitgenomen dat u e-mail contoso.com spamfilters wilt overslaan. U doet dit door de volgende instellingen te configureren:

1. **Voorwaarde:** **Het domein van de** afzender \> **is** \> contoso.com.

2. Configureer een van de volgende instellingen:

   - **Voorwaarde voor de e-mailstroomregel:** **een berichtkop** \> **bevat een van de volgende woorden** \> **Koptekstnaam**: `Authentication-Results` \> **Koptekstwaarde**: of `dmarc=pass` `dmarc=bestguesspass` .

     Deze voorwaarde controleert de e-mailverificatiestatus van het verzendende e-maildomein om ervoor te zorgen dat het verzendende domein niet wordt vervalst. Zie [SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)en DMARC voor meer informatie over [e-mailverificatie.](use-dmarc-to-validate-email.md)

   - **IP Allow List**: Geef het bron-IP-adres- of adresbereik op in het verbindingsfilterbeleid.

     Gebruik deze instelling als het verzendende domein geen e-mailverificatie gebruikt. Wees zo beperkend mogelijk als het gaat om de bron-IP-adressen in de LIJST MET IP-toestaan. U wordt aangeraden een IP-adresbereik van /24 of minder te gebruiken (minder is beter). Gebruik geen IP-adresbereiken die behoren tot consumentenservices (bijvoorbeeld outlook.com) of gedeelde infrastructuren.

   > [!IMPORTANT]
   >
   > - Configureer nooit e-mailstroomregels met *alleen* het afzenderdomein als voorwaarde om spamfilters over te slaan. Hierdoor wordt  de kans aanzienlijk groter dat aanvallers het verzendende domein kunnen vervalsen (of zich voordoen als het volledige e-mailadres), alle spamfilters overslaan en verificatiecontroles voor afzenders overslaan, zodat het bericht in het Postvak IN van de geadresseerde wordt weergegeven.
   >
   > - Gebruik geen domeinen die u bezit (ook wel geaccepteerde domeinen genoemd) of populaire domeinen (bijvoorbeeld microsoft.com) als voorwaarden in e-mailstroomregels. Dit wordt beschouwd als een hoog risico, omdat dit mogelijkheden biedt voor aanvallers om e-mail te verzenden die anders zou worden gefilterd.
   >
   > - Als u een IP-adres toestaat dat achter een NAT-gateway (Network Address Translation) staat, moet u de servers kennen die betrokken zijn bij de NAT-pool om het bereik van uw IP-lijst toestaan te weten. IP-adressen en NAT-deelnemers kunnen wijzigen. U moet uw IP Allow List-vermeldingen regelmatig controleren als onderdeel van uw standaardonderhoudsprocedures.

3. **Optionele voorwaarden:**

   - **De afzender** \> **is intern/extern** \> **Buiten de organisatie:** Deze voorwaarde is impliciet, maar het is ok om deze te gebruiken om rekening te houden met on-premises e-mailservers die mogelijk niet correct zijn geconfigureerd.

   - **Het onderwerp of de body** \> **onderwerp of het lichaam bevat een van deze woorden** \> : Als u de berichten verder kunt beperken op trefwoorden of woordgroepen in de onderwerpregel of berichtgroep, kunt u deze woorden gebruiken \<keywords\> als voorwaarde.

4. **Actie:** Configureer beide acties in de regel:

   a. **De berichteigenschappen wijzigen** \> **het betrouwbaarheidsniveau voor spam instellen (SCL)** \> **Spamfilters omzeilen.**

   b. **De berichteigenschappen wijzigen** \> **een berichtkop instellen:** **stel de berichtkop in** op de \<CustomHeaderName\> **waarde** \<CustomHeaderValue\> .

      Bijvoorbeeld `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`. Als de regel meerdere domeinen bevat, kunt u de koptekst naar wens aanpassen.

      Wanneer een bericht spamfilters overslaat vanwege een regel voor de e-mailstroom, wordt de waarde gestempeld in de `SFV:SKN` **kop X-Forefront-Antispam-Report.** Als het bericht afkomstig is van een bron die zich in de lijst MET IP-toestaan, wordt de waarde `IPV:CAL` ook toegevoegd. Deze waarden kunnen u helpen bij het oplossen van problemen.

![Instellingen voor e-mailstroomregel in het EAC voor het omzeilen van spamfilters.](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Afzenders Outlook Safe gebruiken

> [!CAUTION]
> Met deze methode wordt een hoog risico gemaakt dat aanvallers e-mail leveren aan het Postvak IN die anders zou worden gefilterd. De gebruikersaccounts Safe afzenders of Safe domeinen voorkomen echter niet dat malware of phishingberichten met veel vertrouwen worden gefilterd.

In plaats van een organisatieinstelling kunnen gebruikers of beheerders de e-mailadressen van de afzender toevoegen aan de lijst Safe afzenders in het postvak. Zie Instellingen voor [ongewenste e-mail configureren voor Exchange Online postvakken in Office 365.](configure-junk-email-settings-on-exo-mailboxes.md) Dit is in de meeste gevallen niet wenselijk omdat afzenders delen van de filtertack zullen omzeilen. Hoewel u de afzender vertrouwt, kan de afzender nog steeds worden gecompromitteerd en schadelijke inhoud verzenden. Het is het beste dat u onze filters laat doen wat nodig is om elk bericht te controleren en vervolgens de [fout-positief/negatief](report-junk-email-messages-to-microsoft.md) aan Microsoft te melden als onze filters het fout hebben gedaan. Als u de filtertack overzeilt, wordt [ZAP ook in de weg ermee geslagen.](zero-hour-auto-purge.md)

Wanneer berichten spamfilters overslaan vanwege de lijst met Safe-afzenders van een gebruiker, bevat het veld **X-Forefront-Antispam-Report** de waarde , wat aangeeft dat het filteren op spam, spoofing en phishing is `SFV:SFE` overgeslagen.

## <a name="use-the-ip-allow-list"></a>De lijst met IP-toegestane gegevens gebruiken

Als u geen regels voor e-mailstroom kunt gebruiken zoals eerder is beschreven, kunt u het beste de bron-e-mailserver of -servers toevoegen aan de lijst met IP-toegestane e-mail in het verbindingsfilterbeleid. Zie Verbindingsfilters [configureren in EOP](configure-the-connection-filter-policy.md)voor meer informatie.

**Opmerkingen**:

- Het is belangrijk dat u het aantal toegestane IP-adressen tot een minimum beperkt, dus vermijd het gebruik van volledige IP-adresbereiken waar mogelijk.

- Gebruik geen IP-adresbereiken die behoren tot consumentenservices (bijvoorbeeld outlook.com) of gedeelde infrastructuren.

- Controleer regelmatig de vermeldingen in de LIJST TOESTAAN VAN IP en verwijder de items die u niet meer nodig hebt.

> [!CAUTION]
> Zonder aanvullende verificatie, zoals e-mailstroomregels, worden spamfilters en afzenderverificatie (SPF, DKIM, DMARC) overgeslagen door e-mail uit bronnen in de LIJST met IP-toestaan. Hierdoor is het risico groot dat aanvallers e-mail leveren aan het Postvak IN die anders zou worden gefilterd. De lijst met IP-toestaan voorkomt echter niet dat malware of phishingberichten met veel vertrouwen worden gefilterd.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>Lijsten met toegestane afzenders of toegestane domeinlijsten gebruiken

De minst wenselijke optie is het gebruik van de lijst met toegestane afzenders of de toegestane domeinlijst in antispambeleid. U moet deze optie zo *mogelijk* vermijden omdat afzenders alle spam-, spoof- en phishingbeveiliging en afzenderverificatie (SPF, DKIM, DMARC) omzeilen. Deze methode wordt het beste alleen gebruikt voor tijdelijke tests. De gedetailleerde stappen vindt u in [Antispambeleid configureren in EOP-onderwerp.](configure-your-spam-filter-policies.md)

De maximumlimiet voor deze lijsten is ongeveer 1000 vermeldingen; hoewel u slechts 30 items in de portal kunt invoeren. U moet PowerShell gebruiken om meer dan 30 items toe te voegen.

> [!CAUTION]
>
> - Met deze methode wordt een hoog risico gemaakt dat aanvallers e-mail leveren aan het Postvak IN die anders zou worden gefilterd. De toegestane afzenders of toegestane domeinenlijsten voorkomen echter niet dat malware of phishingberichten met veel vertrouwen worden gefilterd.
>
> - Gebruik geen domeinen die u bezit (ook wel geaccepteerde domeinen genoemd) of populaire domeinen (bijvoorbeeld microsoft.com) in toegestane domeinlijsten.

## <a name="considerations-for-bulk-email"></a>Overwegingen voor bulk-e-mail

Een standaard SMTP-e-mailbericht bestaat uit een *envelop met berichten* en berichtinhoud. De envelop met berichten bevat informatie die nodig is voor het verzenden en verzenden van het bericht tussen SMTP-servers. De berichtinhoud bevat berichtkopvelden (gezamenlijk de *berichtkop* genoemd) en de hoofdtekst van het bericht. De bericht envelop wordt beschreven in RFC 5321 en de berichtkop wordt beschreven in RFC 5322. Geadresseerden zien nooit de werkelijke bericht envelop omdat deze wordt gegenereerd door het berichttransmissieproces en het bericht niet deel uitmaakt van het bericht.

- Het `5321.MailFrom` adres (ook wel mail **from-adres,** P1-afzender of afzender van de envelop genoemd) is het e-mailadres dat wordt gebruikt bij de SMTP-verzending van het bericht. Dit **e-mailadres** wordt meestal opgenomen in het veld Koptekst van het retourpad in de berichtkoptekst (hoewel de afzender een ander **e-mailadres** voor retourpaden kan aanwijzen). Als het bericht niet kan worden bezorgd, is het de geadresseerde voor het rapport niet-bezorging (ook wel een NDR- of bouncebericht genoemd).

- De afzender (ook wel het Van-adres of de afzender van P2 genoemd) is het e-mailadres in het veld Koptekst van Van en is het e-mailadres van de afzender dat wordt weergegeven `5322.From` in e-mail  clients. 

Vaak zijn de `5321.MailFrom` adressen en adressen hetzelfde `5322.From` (communicatie tussen personen). Wanneer e-mail echter namens iemand anders wordt verzonden, kunnen de adressen anders zijn. Dit gebeurt meestal voor bulk-e-mailberichten.

Stel dat Blue Yonder Airlines Margie's Travel heeft aangenomen om de e-mailreclame te verzenden. Het bericht dat u in uw Postvak IN ontvangt, heeft de volgende eigenschappen:

- Het `5321.MailFrom` adres is blueyonder.airlines@margiestravel.com.

- Het adres is blueyonder@news.blueyonderairlines.com, wat u ziet `5322.From` in Outlook.

Safe afzenderlijsten en veilige domeinlijsten in antispambeleid in EOP alleen de adressen controleren, is dit vergelijkbaar met Outlook Safe afzenders die het adres `5322.From` `5322.From` gebruiken.

Als u wilt voorkomen dat dit bericht wordt gefilterd, kunt u de volgende stappen ondernemen:

- Voeg blueyonder@news.blueyonderairlines.com (het `5322.From` adres) toe als Outlook Safe afzender.

- [Gebruik een e-mailstroomregel](#recommended-use-mail-flow-rules) met een voorwaarde die zoekt naar berichten uit blueyonder@news.blueyonderairlines.com (het `5322.From` adres, blueyonder.airlines@margiestravel.com (de `5321.MailFrom` ) of beide.

Zie Lijsten met veilige afzenders maken in EOP voor [meer informatie.](create-safe-sender-lists-in-office-365.md)
