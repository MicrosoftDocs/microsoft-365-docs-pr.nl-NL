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
description: Beheerders kunnen meer informatie krijgen over de beschikbare en voorkeursopties voor het toestaan van inkomende berichten in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ddcd6240cfc80350920999f9fc1e8ea188834553
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289709"
---
# <a name="create-safe-sender-lists-in-eop"></a>Lijsten met veilige afzenders maken in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Als u een Microsoft 365-klant bent met postvakken in Exchange Online of een zelfstandige klant van Exchange Online Protection (EOP) zonder Exchange Online-postvakken, biedt EOP verschillende manieren om ervoor te zorgen dat gebruikers e-mail ontvangen van vertrouwde afzenders. Deze opties omvatten Exchange-regels voor de e-mailstroom (ook wel transportregels genoemd), veilige afzenders van Outlook, de lijst met toegestane IP-adressen (verbindingsfilters) en lijsten met toegestane afzenders of toegestane domeinlijsten in antispambeleidsregels. U kunt deze opties gezamenlijk zien als lijsten _met veilige afzenders._

De beschikbare lijsten met veilige afzenders worden in de volgende lijst beschreven op volgorde van aanbevolen naar minst aanbevolen:

1. Regels voor de e-mailstroom
2. Veilige afzenders in Outlook
3. Lijst met toegestane IP-adressen (filteren van verbinding)
4. Lijsten met toegestane afzenders of lijsten met toegestane domeinen (antispambeleid)

Regels voor de e-mailstroom bieden de meeste flexibiliteit om ervoor te zorgen dat alleen de juiste berichten zijn toegestaan. Toegestane afzenders en toegestane domeinlijsten in antispambeleid zijn niet zo veilig als de lijst met toegestane IP-adressen, omdat het e-maildomein van de afzender eenvoudig kan worden vervalst. Maar de lijst met toegestane IP-adressen  vormt ook een risico, omdat spamfilters worden overgeslagen op e-mail van elk domein dat vanaf dat IP-adres wordt verzonden.

> [!IMPORTANT]
>
> - Wees voorzichtig met het zorgvuldig *controleren van eventuele* uitzonderingen die u maakt op spamfilters met lijsten met veilige afzenders.
>
> - Hoewel u lijsten met veilige afzenders kunt gebruiken om te helpen met fout-positieven (goede e-mail gemarkeerd als slecht), kunt u het gebruik van lijsten met veilige afzenders beter beschouwen als tijdelijke oplossing die u indien mogelijk moet vermijden. Het wordt niet aangeraden fout-positieven te beheren met behulp van lijsten met veilige afzenders, omdat uitzonderingen op spamfilters uw organisatie kunnen openen voor spoofing en andere aanvallen. Als u het gebruik van lijsten met veilige afzenders niet wilt gebruiken om fout-positieven te beheren, moet u goed de berichten en bestanden over het onderwerp rapporteren aan [Microsoft](report-junk-email-messages-to-microsoft.md) bij de hand houden.
>
> - Als u wilt toestaan dat een domein niet-geauteerde e-mail verzendt (beveiliging tegen spoofing omzeilen) maar geen controles tegen ongewenste e-mail en malware wilt omzeilen, kunt u dit toevoegen aan de lijst met veilige afzenders van [AllowedToSpoof.](walkthrough-spoof-intelligence-insight.md)
>
> - EOP en Outlook controleren verschillende berichteigenschappen om de afzender van het bericht te bepalen. Zie de sectie Aandachtspunten voor het [bulksgewijs verzenden van e-mail](#considerations-for-bulk-email) verder naar dit artikel voor meer informatie.

U hebt daarentegen ook verschillende opties voor het blokkeren van e-mail van specifieke bronnen die _gebruikmaken van lijsten met geblokkeerde afzenders._ Zie [Lijsten met geblokkeerde afzenders maken in EOP](create-block-sender-lists-in-office-365.md) voor meer informatie.

## <a name="recommended-use-mail-flow-rules"></a>(Aanbevolen) Regels voor de e-mailstroom gebruiken

E-mailstroomregels in Exchange Online en zelfstandige EOP gebruiken voorwaarden en uitzonderingen voor het identificeren van berichten en acties om aan te geven wat er met die berichten moet worden gedaan. Zie [E-mailstroomregels (transportregels) in Exchange Online voor meer informatie.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

In het volgende voorbeeld wordt ervan uitgenomen dat u e-mail contoso.com spamfilters wilt overslaan. Configureer hiervoor de volgende instellingen:

1. **Voorwaarde:** **het domein van de** afzender \> **is** \> contoso.com.

2. Configureer een van de volgende instellingen:

   - **Voorwaarde voor e-mailstroomregel:** **een berichtkop** bevat een van deze \> **woorden** \> **Koptekstnaam:** `Authentication-Results` \> **Koptekstwaarde**: `dmarc=pass` of `dmarc=bestguesspass` .

     Met deze voorwaarde wordt de status van de e-mailverificatie van het verzendende e-maildomein gecontroleerd om er zeker van te zijn dat het verzendende domein niet is vervalst. Zie [SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)en DMARC voor meer informatie [over e-mailverificatie.](use-dmarc-to-validate-email.md)

   - **Lijst met toegestane** IP-adressen: geef het IP-bronadres of adresbereik op in het verbindingsfilterbeleid.

     Gebruik deze instelling als het verzendende domein geen e-mailverificatie gebruikt. Wees zo beperkend mogelijk wanneer het gaat om de bron-IP-adressen in de lijst met toegestane IP-adressen. U wordt aangeraden een IP-adresbereik van /24 of minder te gebruiken (minder is beter). Gebruik geen IP-adresbereiken die deel uitmaken van consumentenservices (bijvoorbeeld outlook.com) of gedeelde infrastructuur.

   > [!IMPORTANT]
   >
   > - Configureer nooit regels voor de e-mailstroom *met alleen* het domein van de afzender als voorwaarde om spamfilters over te slaan. Als u  dit doet, is de kans aanzienlijk groter dat kwaadwillende gebruikers het verzendende domein kunnen vervalsen (of het volledige e-mailadres kunnen imiteren), alle spamfilters kunnen overslaan en verificatiecontroles van de afzender kunnen overslaan zodat het bericht in het Postvak IN van de geadresseerde wordt ontvangen.
   >
   > - Gebruik geen domeinen die u bezit (ook wel geaccepteerde domeinen genoemd) of populaire domeinen (bijvoorbeeld microsoft.com) als voorwaarden in regels voor de e-mailstroom. Dit wordt als hoog risico beschouwd omdat kwaadwillende aanvallers dan e-mail kunnen verzenden die anders zou worden gefilterd.
   >
   > - Als u een IP-adres achter een NAT-gateway (Network Address Translation) toestaat, moet u weten welke servers betrokken zijn bij de NAT-pool om het bereik van uw lijst met toegestane IP-adressen te weten. IP-adressen en NAT-deelnemers kunnen wijzigen. Als onderdeel van uw standaardonderhoudsprocedures moet u regelmatig de vermeldingen in de lijst met toegestane IP-adressen controleren.

3. **Optionele voorwaarden:**

   - **De afzender** \> **is intern/extern** \> **Buiten de organisatie:** Deze voorwaarde is impliciet, maar het is OK om deze te gebruiken voor on-premises e-mailservers die mogelijk niet correct zijn geconfigureerd.

   - **Het onderwerp of de lichaam** \> **onderwerp of de tekst bevat een van deze woorden** \> : Als u de berichten verder kunt beperken met trefwoorden of woordgroepen in de onderwerpregel of de bericht zelf, kunt u deze woorden als \<keywords\> voorwaarde gebruiken.

4. **Actie:** configureer beide acties in de regel:

   a. **De berichteigenschappen wijzigen** \> **het betrouwbaarheidsniveau voor ongewenste e-mail instellen** \> **Spamfilters omzeilen.**

   b. **De berichteigenschappen wijzigen** \> **stel een berichtkop in:** **stel de berichtkop in** op de \<CustomHeaderName\> **waarde.** \<CustomHeaderValue\>

      Bijvoorbeeld `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`. Als de regel meer dan één domein bevat, kunt u de koptekst naar wens aanpassen.

      Wanneer een bericht geen spamfilters overslaat vanwege een regel voor de e-mailstroom, wordt de waarde in de `SFV:SKN` **koptekst X-Forefront-Antispam-Report** voorzien van een stempel. Als het bericht afkomstig is van een bron die op de lijst met toegestane IP-adressen staat, wordt de `IPV:CAL` waarde ook toegevoegd. Deze waarden kunnen u helpen bij het oplossen van problemen.

![Instellingen voor e-mailstroomregel in het EAC om spamfilters te omzeilen.](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Veilige afzenders van Outlook gebruiken

> [!CAUTION]
> Deze methode creëert een hoog risico dat kwaadwillende mensen e-mail kunnen bezorgen in het Postvak IN die anders zou worden gefilterd. De lijsten met veilige afzenders of veilige domeinen van de gebruiker voorkomen echter niet dat malware of phishingberichten met hoge betrouwbaarheid worden gefilterd.

In plaats van een organisatie-instelling kunnen gebruikers of beheerders de e-mailadressen van de afzender toevoegen aan de lijst met veilige afzenders in het postvak. Zie Instellingen voor ongewenste [e-mail configureren in Exchange Online-postvakken in Office 365 voor instructies.](configure-junk-email-settings-on-exo-mailboxes.md) Dit is in de meeste gevallen niet wenselijk omdat afzenders delen van de filterstack omzeilen. Hoewel u de afzender vertrouwt, kan de afzender nog steeds worden gehackt en schadelijke inhoud verzenden. Het is beter om onze filters te laten doen wat nodig is om elk bericht te controleren en vervolgens de [fout-positief/negatief](report-junk-email-messages-to-microsoft.md) aan Microsoft te melden als onze filters het verkeerd hebben gekregen. Het omzeilen van de filter stack is ook van invloed op [ZAP.](zero-hour-auto-purge.md)

Wanneer berichten geen spamfilters bevatten vanwege de lijst met veilige afzenders van een gebruiker, bevat het veld **X-Forefront-Antispam-Report** de waarde die aangeeft dat filteren op spam, spoofing en phishing is `SFV:SFE` overgeslagen.

## <a name="use-the-ip-allow-list"></a>De lijst met toegestane IP-adressen gebruiken

Als u geen regels voor de e-mailstroom kunt gebruiken zoals eerder is beschreven, kunt u het beste de bron-e-mailserver of -servers toevoegen aan de lijst met toegestane IP-adressen in het verbindingsfilterbeleid. Zie Verbindingsfiltering [configureren in EOP voor meer informatie.](configure-the-connection-filter-policy.md)

**Opmerkingen**:

- Het is belangrijk dat u het aantal toegestane IP-adressen tot een minimum beperkt, dus vermijd het gebruik van volledige IP-adresbereiken waar mogelijk.

- Gebruik geen IP-adresbereiken die deel uitmaken van consumentenservices (bijvoorbeeld outlook.com) of gedeelde infrastructuur.

- Controleer regelmatig de items in de lijst toestaan voor IP en verwijder de vermeldingen die u niet meer nodig hebt.

> [!CAUTION]
> Zonder extra verificatie, zoals regels voor de e-mailstroom, worden controles voor spamfilters en afzenderverificatie (SPF, DKIM, DMARC) overgeslagen uit bronnen in de lijst Toestaan van IP. Hierdoor ontstaat een groot risico dat kwaadwillende mensen e-mail kunnen bezorgen in het Postvak IN die anders zou worden gefilterd. De lijst met toegestane IP-adressen voorkomt echter niet dat malware of phishingberichten met hoge betrouwbaarheid worden gefilterd.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>Lijsten met toegestane afzenders of toegestane domeinlijsten gebruiken

U kunt het beste de lijst met toegestane afzenders of de lijst met toegestane domeinen in antispambeleid gebruiken. Vermijd deze optie, indien mogelijk, omdat afzenders alle spam, spoof, en phishingbeveiliging en verificatie van afzenders (SPF, DKIM, DMARC) omzeilen.  Deze methode is alleen het meest gebruikt voor tijdelijke tests. De gedetailleerde stappen vindt u in [Antispambeleid configureren in EOP-onderwerp.](configure-your-spam-filter-policies.md)

De maximumlimiet voor deze lijsten is ongeveer 1000 items; hoewel u slechts 30 vermeldingen in de portal kunt invoeren. U moet PowerShell gebruiken om meer dan 30 vermeldingen toe te voegen.

> [!CAUTION]
>
> - Deze methode creëert een hoog risico dat kwaadwillende mensen e-mail kunnen bezorgen in het Postvak IN die anders zou worden gefilterd. De toegestane afzenders of lijsten met toegestane domeinen voorkomen echter niet dat malware of phishing-berichten met hoge betrouwbaarheid worden gefilterd.
>
> - Gebruik geen domeinen die u bezit (ook wel geaccepteerde domeinen genoemd) of populaire domeinen (bijvoorbeeld microsoft.com) in toegestane domeinlijsten.

## <a name="considerations-for-bulk-email"></a>Overwegingen voor bulk-e-mail

Een standaard SMTP-e-mailbericht bestaat uit een *envelop met berichten* en berichtinhoud. De envelop met berichten bevat informatie die is vereist voor het verzenden en bezorgen van het bericht tussen SMTP-servers. De inhoud van het bericht bevat berichtkopvelden (gezamenlijk de berichtkop *genoemd)* en de berichttekst. De berichtvelop wordt beschreven in RFC 5321 en de berichtkop wordt beschreven in RFC 5322. Geadresseerden zien de feitelijke berichtvelopop niet, omdat deze wordt gegenereerd door het verzendingsproces voor berichten en niet daadwerkelijk deel uitmaakt van het bericht.

- Het adres (ook wel bekend als het `5321.MailFrom` MAIL **FROM-adres,** de afzender van P1 of de afzender van de envelop) is het e-mailadres dat wordt gebruikt in de SMTP-verzending van het bericht. Dit e-mailadres wordt  meestal opgenomen in het koptekstveld Retourpad in de berichtkoptekst (hoewel de afzender een ander **e-mailadres** voor het retourpad kan aanwijzen). Als het bericht niet kan worden bezorgd, is het de geadresseerde van het rapport over niet-bezorging (ook wel een NDR- of niet-bezorgdbericht genoemd).

- De afzender (ook wel het Van-adres of P2 genoemd) is het e-mailadres in het veld Van en is het e-mailadres van de afzender dat wordt weergegeven `5322.From` in e-mail clients.  

Vaak zijn de adressen en de adressen hetzelfde (communicatie tussen twee `5321.MailFrom` `5322.From` personen). Wanneer e-mail echter namens iemand anders wordt verzonden, kunnen de adressen verschillend zijn. Dit gebeurt het vaakst bij bulk-e-mailberichten.

Stel dat Blue Yonder Airlines Margie's Travel heeft aangenomen om haar e-mail reclame te sturen. Het bericht dat u in uw Postvak IN ontvangt, heeft de volgende eigenschappen:

- Het `5321.MailFrom` adres is blueyonder.airlines@margiestravel.com.

- Het `5322.From` adres is blueyonder@news.blueyonderairlines.com, dit is wat u in Outlook ziet.

Lijsten met veilige afzenders en lijsten met veilige domeinen in antispambeleid in EOP inspecteren alleen de adressen. Dit is vergelijkbaar met de veilige afzenders van Outlook die het adres `5322.From` `5322.From` gebruiken.

Als u wilt voorkomen dat dit bericht wordt gefilterd, kunt u de volgende stappen nemen:

- Voeg blueyonder@news.blueyonderairlines.com (het `5322.From` adres) toe als veilige afzender van Outlook.

- [Gebruik een regel voor de](#recommended-use-mail-flow-rules) e-mailstroom met een voorwaarde die zoekt naar berichten blueyonder@news.blueyonderairlines.com berichten (het `5322.From` adres, blueyonder.airlines@margiestravel.com (de `5321.MailFrom` ) of beide.

Zie Lijsten met veilige afzenders maken in EOP voor [meer informatie.](create-safe-sender-lists-in-office-365.md)
