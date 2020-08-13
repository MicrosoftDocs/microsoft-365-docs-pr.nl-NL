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
description: Beheerders kunnen informatie krijgen over de beschikbare en voorkeursopties voor het toestaan van inkomende berichten in Exchange Online Protection (EOP).
ms.openlocfilehash: bbb25e1c499e84a1af34d0f0a52a81f1470aadfd
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652979"
---
# <a name="create-safe-sender-lists-in-eop"></a>Lijsten met veilige afzenders maken in EOP

Als u een klant van Microsoft 365 met postvakken in Exchange Online of een zelfstandige Exchange Online Protection (EOP)-klant zonder postvakken van Exchange Online hebt, biedt EOP meerdere manieren om ervoor te zorgen dat gebruikers e-mail van vertrouwde afzenders ontvangen. Dit zijn de opties voor Exchange-e-mail stroom (ook wel bekend als transportregels), veilige afzenders van Outlook, de lijst met toegestane IP-adressen (verbindingen van verbindingen) en lijsten met toegestane afzenders of toegestane domein lijsten in antispambeleid. Daarnaast kunt u het volgende doen als _lijsten met veilige afzenders_.

De lijst met beschikbare lijsten met veilige afzenders wordt beschreven in de volgende lijst, in volgorde van aanbevolen aan de laagste aanbevolen stappen:

1. Regels voor e-mail stroom
2. Veilige afzenders van Outlook
3. Lijst met toegestane IP-adressen (verbindingen filteren)
4. Lijsten met toegestane afzenders of toegestane domeinen (Antispambeleid)

Regels voor e-mail stroom bieden de meeste flexibiliteit om ervoor te zorgen dat alleen de juiste berichten worden toegestaan. Toegestane verzenders en toegestane domein lijsten in Antispambeleid zijn niet veilig als de lijst met toegestane IP-berichten, omdat het e-mail domein van de afzender eenvoudig wordt vervalst. Het is ook mogelijk dat de lijst met IP-adressen een risico vormt, omdat e-mail van _een_ domein dat via dat IP-adres wordt verzonden, geen spam filteren.

> [!IMPORTANT]
>
> - Let erop dat u uitzonderingen die u met lijsten met veilige afzenders verspamt, *nauwkeurig controleert* .
>
> - U kunt lijsten met veilige afzenders gebruiken om foutberichten te ontvangen (goede e-mailberichten die als spam zijn gemarkeerd), maar u kunt het beste afzenders gebruiken als een tijdelijke oplossing, indien mogelijk. We raden u niet aan dat er geen ongeluk is met behulp van lijsten met veilige afzenders, aangezien uitzonderingen op spam filteren uw organisatie kan openen voor spoofing en andere aanvallen. Als u de lijsten met veilige afzenders wilt gebruiken voor het beheren van foutberichten, moet u Vigilant zijn en het onderwerp in het [rapportberichten en bestanden naar Microsoft](report-junk-email-messages-to-microsoft.md) laten staan.
>
> - Als u wilt dat een domein niet-geverifieerde e-mail kan verzenden (anti-spoofing beveiliging), maar niet antispam en anti-malware controleert, kunt u deze toevoegen aan de [lijst met veilige afzenders van AllowedToSpoof](walkthrough-spoof-intelligence-insight.md)
>
> - In EOP en Outlook worden de verschillende berichteigenschappen gecontroleerd om de afzender van het bericht te bepalen. Zie voor meer informatie de sectie [overwegingen voor bulk e-mail](#considerations-for-bulk-email) verderop in dit onderwerp.

In het contrast hebt u ook verschillende opties om e-mail van bepaalde bronnen te blokkeren met behulp van _lijsten met geblokkeerde afzenders_. Zie [Lijsten met geblokkeerde afzenders maken in EOP](create-block-sender-lists-in-office-365.md) voor meer informatie.

## <a name="recommended-use-mail-flow-rules"></a>Beter Regels voor e-mail stroom gebruiken

Regels voor e-mail stroom in Exchange Online en standalone EOP voorwaarden en uitzonderingen voor het identificeren van berichten en acties om op te geven wat er moet gebeuren met die berichten. Zie voor meer informatie [e-mail stroom regels (transportregels) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).

In het volgende voorbeeld wordt ervan uitgegaan dat u e-mail hebt ontvangen van contoso.com om spam te filteren. Configureer de volgende instellingen:

1. **Voorwaarde**: het domein van **de afzender** \> **is** \> contoso.com.

2. Configureer een van de volgende instellingen:

   - **Voorwaarde voor de e-mail stroom regel**: **een kop van een bericht** \> **bevat een van deze woorden** \> **Header name**: header `Authentication-Results` \> **waarde**: `dmarc=pass` of `dmarc=bestguesspass` .

     Met deze voorwaarde wordt de verificatiestatus van de afzender van het verzonden e-mail domein gecontroleerd om ervoor te zorgen dat het verzendende domein geen spoofing heeft. Zie [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [dkim](use-dkim-to-validate-outbound-email.md)en [DMARC](use-dmarc-to-validate-email.md)voor meer informatie over e-mail verificatie.

   - **Lijst met toegestane IP-** adressen: Geef het bron-IP-adres of-adresbereik op in het filter beleid voor verbindingen.
  
     Gebruik deze instelling als het verzendende domein geen verificatie heeft. Zo beperkt mogelijk wanneer het komt in de bron-IP-adressen in de lijst met toegestane IP-adressen. We raden u aan een IP-adresbereik van/24 of minder te (minder is beter). Gebruik geen IP-adresbereiken die deel uitmaken van consumenten Services (bijvoorbeeld outlook.com) of gedeelde infrastructuur.

   > [!IMPORTANT]
   >
   > - Configureer nooit de configuratie voor e-mail stroom regels met *alleen* het domein van de afzender als voorwaarde om spamfilters over te slaan. Hierdoor wordt de *kans groter dat* kwaadwillenden het verzendend domein kunnen spoofen (of het volledige e-mailadres imiteren), alle spamfilters overslaan en verificatie van afzender overslaan zodat het bericht in het postvak in van de geadresseerde arriveert.
   >
   > - Gebruik geen domeinen die u ook hebt (ook wel geaccepteerde domeinen genoemd) of veelgebruikte domeinen (zoals microsoft.com) als voorwaarden in de e-mail stroom regels. Dit is een zeer risico, omdat er verkoopkansen worden gemaakt voor hackers waarmee e-mail kan worden verzonden die anders wordt gefilterd.
   >
   > - Als u een IP-adres toestaat dat zich achter een NAT-gateway (Network Address Translation) bevindt, moet u weten welke servers bij de NAT-groep betrokken zijn om het bereik van de toegestane lijst met IP-adressen te weten te komen. IP-adressen en NAT-deelnemers kunnen wijzigen. U dient regelmatig te controleren of uw IP-vermeldingen voor lijsten in de standaard onderhoudsprocedures worden toegestaan.

3. **Facultatieve voorwaarden**:

   - **De afzender** \> **is intern/extern** \> **Buiten de organisatie**: deze voorwaarde is impliciet, maar u kunt deze wel gebruiken om te werken met on-premises e-mailservers die mogelijk niet correct zijn geconfigureerd.

   - **Het onderwerp of de hoofdtekst** \> het **onderwerp of de hoofdtekst bevat een van deze woorden** \> \<keywords\>: Als u de berichten verder wilt beperken tegen trefwoorden of woordgroepen in het onderwerp of de hoofdtekst van het bericht, kunt u deze woorden als voorwaarde gebruiken.

4. **Actie**: Configureer beide acties in de regel:

   a. **De berichteigenschappen wijzigen** \> **het betrouwbaarheidsniveau voor ongewenste e-mail (SCL) instellen** \> **Spam filteren negeren**.

   b. **Een berichtkop** \> **bevat een of meer van deze woorden** \> **Naam van koptekst**: \<CustomHeaderName\> **waarde van koptekst**: \<CustomHeaderValue\> .

      Bijvoorbeeld `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`. Als de regel meer dan één domein bevat, kunt u de koptekst van de gewenste tekst aanpassen.

      Wanneer spam filteren wordt overgeslagen door een e-mail stroom regel, wordt de waarde van de waarde `SFV:SKN` in de kop **X-Forefront-spam-report** vastgelegd. Als het bericht afkomstig is van een bron die is opgenomen in de lijst met toegestane IP-adressen, wordt de waarde `IPV:CAL` ook toegevoegd. Deze waarden kunnen u helpen bij het oplossen van problemen.

![Instellingen voor de e-mail stroom regels in het Exchange-Beheercentrum voor komend spamfilters te negeren.](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Veilige afzenders van Outlook gebruiken

In plaats van een organisatie-instelling kunnen gebruikers of beheerders de e-mailadressen van de afzender toevoegen aan de lijst met veilige afzenders in het postvak. Zie voor instructies voor het [instellen van instellingen voor ongewenste e-mail in Exchange Online-postvakken in Office 365](configure-junk-email-settings-on-exo-mailboxes.md). Dit is in de meeste situaties wenselijk, omdat afzenders delen van de filter stapel negeren. Hoewel u de afzender vertrouwt, is de blik van de afzender nog steeds kwetsbaar en kunt u schadelijke inhoud verzenden. Het is raadzaam om de filters uit te voeren die nodig zijn om elk bericht te controleren en vervolgens [de foutwaarde positief/negatief aan Microsoft te melden als de](report-junk-email-messages-to-microsoft.md) filters het probleem hebben. Het omzeilen van de filterstack verstoort ook met [ZAP](zero-hour-auto-purge.md).

Wanneer spam wordt gefilterd door de lijst met veilige afzenders van een gebruiker, bevat het veld **X-Forefront-spam-report** header de waarde `SFV:SFE` waarmee wordt aangegeven dat spam, spoof en phishing-filters zijn genegeerd.

## <a name="use-the-ip-allow-list"></a>De lijst met toegestane IP-adressen gebruiken

Als u de e-mail stroom regels niet zoals hierboven beschreven kunt gebruiken, kunt u de bron-e-mailserver of servers toevoegen aan de lijst met toegestane IP-adressen in het filter beleid voor verbindingen. Zie voor meer informatie het [filteren van verbindingen configureren in EOP](configure-the-connection-filter-policy.md).

**Opmerkingen**:

- Het is belangrijk dat u het aantal toegestane IP-adressen naar een minimum beperkt, dus vermijdt u zo mogelijk volledige IP-adresbereiken.

- Gebruik geen IP-adresbereiken die deel uitmaken van consumenten Services (bijvoorbeeld outlook.com) of gedeelde infrastructuur.

- Controleer regelmatig de vermeldingen in de lijst met toegestane IP-adressen en verwijder de vermeldingen die u niet meer nodig hebt.

> [!CAUTION]
> Zonder verdere verificatie zoals de regels voor de e-mail stroom, worden e-mailberichten van bronnen in de lijst met toegestane IP-berichten over spam gefilterd en worden de verificatie van e-mailberichten (SPF, DKIM, DMARC Dit maakt een hoog risico van kwaadwillende gebruikers die via e-mail een e-mailbericht sturen naar het postvak in, anders gefilterd.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>Lijsten met toegestane afzenders of toegestane domeinen gebruiken

De goedkoopste optie is de lijst met toegestane afzenders of de lijst met toegestane domeinen in antispambeleid. U dient deze optie helemaal niet te vermijden omdat afzenders alle spam, spoofing en phishing-bescherming negeren en authenticatie *van* de afzender (SPF, dkim, DMARC). Deze methode is het meest geschikt voor tijdelijke tests. De gedetailleerde stappen vindt u in het onderwerp [Antispambeleid in EOP](configure-your-spam-filter-policies.md) onderwerp.

De maximumlimiet voor deze lijsten is ongeveer 1000 vermeldingen. u kunt echter maar wel 30 vermeldingen invoeren in de portal. U moet PowerShell gebruiken om meer dan 30 vermeldingen toe te voegen.

> [!CAUTION]
>
> - Met deze methode maakt u een groot risico van kwaadwillende gebruikers die via e-mail een e-mailbericht sturen naar het postvak in, anders gefilterd.
>
> - Gebruik geen domeinen die u hebt (ook wel geaccepteerde domeinen genoemd) of populaire domeinen (bijvoorbeeld microsoft.com) in toegestane domein lijsten.

## <a name="considerations-for-bulk-email"></a>Aandachtspunten voor bulk-e-mail

Een standaard SMTP-e-mailbericht bestaat uit een *envelop met berichten* en de inhoud van het bericht. De envelop bericht bevat informatie die nodig is voor het verzenden en het verzenden van het bericht tussen SMTP-servers. De inhoud van het bericht bevat berichtkop velden (gezamenlijk de kop van het *e-mailbericht*genoemd) en de berichttekst. De envelop van het bericht wordt beschreven in RFC 5321 en de kop van het e-mailbericht wordt beschreven in RFC 5322. Geadresseerden zien de envelop met het werkelijke bericht niet omdat deze wordt gegenereerd door het proces voor het verzenden van berichten en het maakt niet uit van het bericht.

- Het `5321.MailFrom` adres (ook wel **e-mail adres van** de afzender, de afzender van P1 of de afzender) is het e-mailadres dat wordt gebruikt in de SMTP-overdracht van het bericht. Dit e-mailadres wordt meestal opgenomen in het veld voor **de veldnamenrij in de kop van** het bericht (hoewel het mogelijk is dat de afzender een ander e-mailadres voor het **retour traject** aanwijst). Als het bericht niet kan worden bezorgd, is dit de geadresseerde voor het rapport over niet-uitgevoerde bezorging (ook wel een NDR genoemd of een bericht met een stuiter bericht).

- De `5322.From` (ook bekend als de afzender **van** address of P2) is het e-mailadres in het veld **van** koptekst en het e-mailadres van de afzender dat wordt weergegeven in e-mailclients.

Vaak zijn de `5321.MailFrom` en `5322.From` -adressen hetzelfde (communicatie van persoon naar persoon). Wanneer e-mail echter wordt verzonden namens iemand anders, kunnen de adressen afwijken. Dit gebeurt meestal voor bulk-e-mailberichten.

Stel dat Blue Yonder Airlines de reis voor de reis van Marga in dienst heeft. Het bericht dat u ontvangt in uw postvak in heeft de volgende eigenschappen:

- Het `5321.MailFrom` adres is blueyonder.Airlines@margiestravel.com.

- Het `5322.From` adres is blueyonder@news.blueyonderairlines.com, wat u in Outlook ziet.

Lijsten met veilige afzenders en veilige domein lijsten in anti-spam beleid in EOP inspecteert alleen de `5322.From` adressen, dit is vergelijkbaar met veilige afzenders van Outlook waarin het adres wordt gebruikt `5322.From` .

U kunt de volgende stappen uitvoeren om te voorkomen dat dit bericht wordt gefilterd:

- Voeg blueyonder@news.blueyonderairlines.com (het `5322.From` adres) toe als een veilige afzender van Outlook.

- [Gebruik een e-mail stroom regel](#recommended-use-mail-flow-rules) met een voorwaarde waarmee wordt gezocht naar berichten van blueyonder@news.blueyonderairlines.com (het `5322.From` adres, blueyonder.Airlines@margiestravel.com (de `5321.MailFrom` ) of beide.

Zie voor meer informatie [lijsten met veilige afzenders maken in EOP](create-safe-sender-lists-in-office-365.md).
