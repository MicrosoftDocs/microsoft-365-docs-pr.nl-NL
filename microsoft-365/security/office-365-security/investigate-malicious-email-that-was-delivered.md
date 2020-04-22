---
title: Schadelijke e-mail zoeken en onderzoeken die is geleverd in Office 365, herstellen, verhelpen, herstellen, bescherming tegen bedreigingen, bedreigingsverkenner, bescherming
keywords: TIMailData-Inline, Security Incident, incident, ATP PowerShell, e-mail malware, gecompromitteerde gebruikers, e-mail phish, e-mail malware, lees e-mail headers, lees headers, open e-mail headers
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Meer informatie over het gebruik van mogelijkheden voor het onderzoeken en reageren van bedreigingen om schadelijke e-mail te vinden en te onderzoeken.
ms.openlocfilehash: ec70bc585d4067357c9871cffc7475357fbfb5bb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634132"
---
# <a name="investigate-and-remediate-malicious-email-that-was-delivered-in-office-365"></a>Kwaadaardige e-mail onderzoeken en herstellen die in Office 365 is geleverd

[Met Office 365 Advanced Threat Protection](office-365-atp.md) u activiteiten onderzoeken die mensen in uw organisatie in gevaar brengen en actie ondernemen om uw organisatie te beschermen. Als u bijvoorbeeld deel uitmaakt van het beveiligingsteam van uw organisatie, u verdachte e-mailberichten die zijn bezorgd, vinden en onderzoeken. U dit doen met [Threat Explorer (of real-time detecties).](threat-explorer.md)
  
## <a name="before-you-begin"></a>Voordat u begint...

Zorg ervoor dat aan de volgende eisen wordt voldaan:
  
- Uw organisatie heeft [Office 365 Advanced Threat Protection](office-365-atp.md) en licenties zijn toegewezen aan [gebruikers.](../../admin/manage/assign-licenses-to-users.md)
    
- [controlelogboekregistratie](../../compliance/turn-audit-log-search-on-or-off.md) is ingeschakeld voor uw organisatie. 
    
- Uw organisatie heeft beleid gedefinieerd voor anti-spam, anti-malware, anti-phishing, enzovoort. Zie [Beschermen tegen bedreigingen in Office 365](protect-against-threats.md).
    
- U bent een globale beheerder of u hebt de beveiligingsbeheerder of &amp; de rol Zoeken en verwijderen toegewezen in het Security Compliance Center. Zie [Machtigingen in &amp; het Security Compliance Center](permissions-in-the-security-and-compliance-center.md). Voor sommige acties moet u ook een nieuwe voorbeeldrol hebben toegewezen. 

#### <a name="preview-role-permissions"></a>Voorvertoning van functiemachtigingen

Als u bepaalde acties wilt uitvoeren, zoals het bekijken van berichtkoppen of het downloaden van inhoud van e-mailberichten, moet u een nieuwe rol met de naam *Preview* hebben toegevoegd aan een andere geschikte rolgroep. In de volgende tabel worden vereiste rollen en machtigingen verduidelijkt.

|Activiteit  |Rolgroep |Preview rol nodig?  |
|---------|---------|---------|
|Threat Explorer (en realtime detecties) gebruiken om bedreigingen te analyseren     |Globale beheerder <br> Beveiligingsbeheerder <br> Beveiligingslezer     | Nee   |
|Threat Explorer (en realtime detecties) gebruiken om kopteksten voor e-mailberichten weer te geven en in quarantaine geplaatste e-mailberichten te bekijken en te downloaden    |Globale beheerder <br> Beveiligingsbeheerder <br>Beveiligingslezer   |       Nee  |
|Threat Explorer gebruiken om kopteksten weer te geven en e-mailberichten te downloaden die bij postvakken worden bezorgd     |Globale beheerder <br>Beveiligingsbeheerder <br> Beveiligingslezer <br> Voorbeeld   |   Ja      |

> [!NOTE]
> *Preview* is een rol en geen rolgroep; de voorbeeldrol moet worden toegevoegd aan een bestaande rolgroep voor Office 365. De functie Globale beheerder krijgt het Microsoft[https://admin.microsoft.com](https://admin.microsoft.com)365-beheercentrum ( ) toegewezen en de rollen[https://protection.office.com](https://protection.office.com)Beveiligingsbeheerder en Beveiligingslezer worden toegewezen in het Security & Compliance Center ( ). Zie [Machtigingen in het Beveiligings& Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over rollen en machtigingen.

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>Verdachte e-mail zoeken en verwijderen die is bezorgd

Threat Explorer is een krachtig rapport dat meerdere doeleinden kan dienen, zoals het vinden en verwijderen van berichten, het identificeren van het IP-adres van een kwaadaardige e-mailafzender of het starten van een incident voor verder onderzoek. De volgende procedure is gericht op het gebruik van Explorer om schadelijke e-mail uit de postvakken van de ontvanger te vinden en te verwijderen.

> [!NOTE]
> Standaardzoekopdrachten in Explorer bevatten momenteel geen Zapped-items.  Dit geldt voor alle weergaven, bijvoorbeeld malware of phish-weergaven. Om Zapped-items op te nemen, moet je een 'Delivery-actie' toevoegen om 'Verwijderd door ZAP' op te nemen. Als u alle opties opneemt, ziet u alle resultaten van de leveringsactie, inclusief Zapped-artikelen.

1. **Navigeer naar Threat Explorer:** Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw werk- of schoolaccount voor Office 365. Dit brengt u &amp; naar het Security Compliance Center.

2. Kies in de snelle lancering van de navigatienavigatie de optie **Threat management** \> **Explorer**.

    ![Explorer met de velden Delivery Action en Delivery Location.](../../media/ThreatExFields.PNG)

    <!-- You may notice the new **Special actions** column. This feature is aimed at telling admins the outcome of processing an email. The **Special actions** column can be accessed in the same place as **Delivery action** and **Delivery location**. Special actions might be updated at the end of Threat Explorer's email timeline, which is a new feature aimed at making the hunting experience better for admins.-->

3. **Weergaven in Threat Explorer:** Kies in het menu **Weergave** **alle e-mail**.

    ![Threat explorer Bekijk menu, en E-mail - Malware, Phish, Inzendingen en Alle e-mail opties, ook Inhoud - Malware.](../../media/tp-InvestigateMalEmail-viewmenu.png)

    De *malware* weergave is momenteel de standaard, en vangt e-mails waar een malware bedreiging wordt gedetecteerd. De *Phish-visie* werkt op dezelfde manier, voor Phish.

    Alle *e-mailweergave* bevat echter elke e-mail die door de organisatie is ontvangen, ongeacht of er bedreigingen zijn gedetecteerd of niet. Zoals u zich voorstellen, dit is een heleboel gegevens, dat is de reden waarom deze weergave toont een tijdelijke aanduiding die vraagt een filter worden toegepast. (Deze weergave is alleen beschikbaar voor ATP P2-klanten.)

    *In de weergave Inzendingen* toont alle e-mails die zijn ingediend door de beheerder of gebruiker die aan Microsoft zijn gemeld.

4. **Zoeken en filteren in Threat Explorer:** filters worden boven aan de pagina in de zoekbalk weergegeven om beheerders te helpen bij hun onderzoeken. Merk op dat meerdere filters tegelijkertijd kunnen worden toegepast en meerdere door komma's gescheiden waarden die aan een filter zijn toegevoegd om de zoekopdracht te beperken. Herinneren:
    - Filters doen exacte matching op de meeste filtervoorwaarden.
    - Onderwerpfilter gebruikt een CONTAINS-query.
    - URL-filters werken met of zonder protocollen (bijvoorbeeld. https).
    - Voor URL-domein-, URL-pad- en URL-domein- en padfilters is geen protocol vereist dat wordt gefilterd.
    - U moet telkens op het pictogram Vernieuwen klikken wanneer u de filterwaarden wijzigt om relevante resultaten te krijgen.

5. **Geavanceerde filters:** Met deze filters u complexe query's maken en uw gegevensset filteren. Als u op *Geavanceerde filters klikt,* wordt een flyout met opties geopend.

   Geavanceerde filtering is een geweldige aanvulling op de zoekmogelijkheden. Er is een booleaans **NIET-filter** geïntroduceerd op het domein *Ontvanger,* *Afzender* en *Afzender,* zodat beheerders het kunnen onderzoeken door waarden uit te sluiten. Deze optie wordt weergegeven onder selectieparameter *Bevat geen van*. **NOT** laat beheerders waarschuwingspostvakken uitsluiten, standaard postvakken beantwoorden van hun onderzoeken en is handig voor gevallen waarin beheerders zoeken naar een specifiek onderwerp (onderwerp="Aandacht") waarbij de ontvanger kan worden ingesteld op *geen van defaultMail@contoso.com*. Dit is een exacte waarde zoeken.

   ![Het filter Ontvangers - 'Bevat geen van' geavanceerd filter.](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   *Filteren op uren* helpt het beveiligingsteam van uw organisatie snel in te zoomen. De kortste toegestane tijdis 30 minuten. Als u de verdachte actie beperken op tijdskader (bijvoorbeeld het gebeurde 3 uur geleden), zal dit de context beperken en helpen het probleem lokaliseren.

  ![De filtering op uren optie om de hoeveelheid data security teams te beperken moeten verwerken, en waarvan de kortste duur is 30 minuten.](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. **Velden in threat explorer**: Threat Explorer onthult veel meer beveiligingsgerelateerde e-mailinformatie, zoals *delivery actie*, *Delivery locatie*, *Speciale actie*, *Directionaliteit*, *Overrides*en *URL bedreiging*. Het stelt het beveiligingsteam van uw organisatie ook in staat om met een grotere zekerheid te onderzoeken. 

    *Leveringsactie* is de actie die wordt uitgevoerd op een e-mail vanwege bestaande beleidsregels of detecties. Hier zijn de mogelijke acties die een e-mail kan ondernemen:
    - **Geleverd** - e-mail is geleverd aan de inbox of map van een gebruiker en de gebruiker heeft er rechtstreeks toegang toe.
    - **Ongewenste** e-mail (geleverd aan ongewenste e-mail): e-mail is verzonden naar de ongewenste map van een gebruiker of verwijderde map, en de gebruiker heeft toegang tot e-mailberichten in de map Ongewenste of verwijderde bestanden.
    - **Geblokkeerd** : alle e-mailberichten die in quarantaine zijn geplaatst, die zijn mislukt of zijn verwijderd. (Dit is volledig ontoegankelijk voor de gebruiker.)
    - **Vervangen** : elke e-mail waarin schadelijke bijlagen worden vervangen door .txt-bestanden waarin staat dat de bijlage schadelijk was

    **Leveringslocatie**: Het filter Locatie bezorging is beschikbaar om beheerders te helpen begrijpen waar vermoedelijke schadelijke e-mail is beland en welke acties er op zijn uitgevoerd. De resulterende gegevens kunnen worden geëxporteerd naar spreadsheets. Mogelijke bezorglocaties zijn:
    - **Postvak IN of map** : de e-mail bevindt zich in het Postvak IN of een specifieke map, volgens uw e-mailregels.
    - **On-prem of extern** – Het postvak bestaat niet in de cloud, maar is on-premises.
    - **Map ongewenste e-mail** : de e-mail bevindt zich in de map Ongewenste e-mail van een gebruiker.
    - **Map verwijderde items :** de e-mail bevindt zich in de map Verwijderde items van een gebruiker.
    - **Quarantaine** : de e-mail in quarantaine en niet in het postvak van een gebruiker.
    - **Mislukt** : de e-mail kan het postvak niet bereiken.
    - **Dropped** - De e-mail is ergens in de e-mailstroom verloren gegaan.

    **Directionaliteit:** Met deze optie kan uw beveiligingsteam filteren op de 'richting' waar een e-mail vandaan komt of gaat. Directionaliteitswaarden zijn *Inbound,* *Outbound*en *Intra-org* (overeenkomend met e-mail die van buitenaf in uw organisatie komt, vanuit uw organisatie wordt verzonden of intern naar uw organisatie wordt verzonden). Deze informatie kan beveiligingsteams helpen spoofing en imitatie te herkennen, omdat er een mismatch is tussen de waarde Directionaliteit (bijvoorbeeld. *Inbound*), en het domein van de afzender (dat *lijkt* te zijn een intern domein) zal duidelijk zijn! De waarde Directionaliteit is gescheiden en kan afwijken van de berichttracering. Resultaten kunnen worden geëxporteerd naar spreadsheets.

    **Overschrijft:** Met dit filter worden gegevens weergegeven die op het tabblad gegevens van de e-mail *worden*weergegeven en wordt deze gebruikt om aan te geven waar het organisatie- of gebruikersbeleid is weergegeven voor het toestaan en blokkeren van e-mails. Het belangrijkste aan dit filter is dat het beveiligingsteam van uw organisatie helpt te zien hoeveel verdachte e-mails zijn bezorgd vanwege de configuratie. Dit geeft hen de mogelijkheid om te wijzigen staat en blokken als dat nodig is. Deze resultatenset van dit filter kan worden geëxporteerd naar spreadsheets.

|Overschrijft Threat Explorer  | Wat ze bedoelen  |
|---------|---------|
|Toegestaan door het org-beleid     |   E-mail is toegestaan in de mailbox zoals aangegeven door het organisatiebeleid.       |
|Geblokkeerd door het beleid van de organisatie      |  E-mail is geblokkeerd van levering naar het postvak zoals aangegeven door het organisatiebeleid.    |
|Bestandsextensie geblokkeerd door org-beleid     | Bestand is geblokkeerd van levering naar het postvak zoals aangegeven door het organisatiebeleid.        |
|Toegestaan door gebruikersbeleid     | E-mail is toegestaan in het postvak zoals aangegeven door het gebruikersbeleid.        |
|Geblokkeerd door gebruikersbeleid     | E-mail is geblokkeerd van levering naar het postvak zoals aangegeven door het gebruikersbeleid.        |

**URL-dreiging:** het veld URL-dreiging is opgenomen op het *tabblad details* van een e-mail om de bedreiging aan te geven die wordt weergegeven door een URL. Bedreigingen gepresenteerd door een URL kan *malware,* *Phish*, of *Spam,* en een URL *zonder bedreiging* zal zeggen *Geen* in de bedreigingen sectie.

7. **Tijdlijnweergave e-mail:** uw beveiligingsteam moet mogelijk dieper ingaan op e-mailgegevens om verder onderzoek te doen. Met de e-mailtijdlijn kunnen beheerders acties bekijken die zijn uitgevoerd op een e-mail, van levering tot na levering. Als u een e-mailtijdlijn wilt weergeven, klikt u op het onderwerp van een e-mailbericht en klikt u vervolgens op Tijdlijn e-mail. (Het verschijnt onder andere koppen in het paneel zoals Samenvatting of Details.) Deze resultaten kunnen worden geëxporteerd naar spreadsheets.

    De tijdlijn van de e-mail wordt geopend voor een tabel met alle leverings- en post-deliverygebeurtenissen voor de e-mail. Als er geen verdere acties op de e-mail, moet u een enkele gebeurtenis voor de oorspronkelijke levering die een resultaat, zoals *Geblokkeerd,* met een vonnis als *Phish*staat. Beheerders kunnen de volledige e-mailtijdlijn exporteren, inclusief alle gegevens op het tabblad en e-mail (zoals onderwerp, afzender, ontvanger, netwerk en bericht-id). De e-mailtijdlijn vermindert randomisatie omdat er minder tijd wordt besteed aan het controleren van verschillende locaties om te proberen gebeurtenissen te begrijpen die zijn gebeurd sinds de e-mail is aangekomen. Wanneer meerdere gebeurtenissen op of in de buurt van een e-mail tegelijkertijd plaatsvinden, worden deze gebeurtenissen weergegeven in een tijdlijnweergave.

8. **Preview / download**: Threat Explorer geeft uw beveiligingsteam de details die ze nodig hebben om verdachte e-mail te onderzoeken. Uw beveiligingsteam kan:

    - [Controleer de leveringsactie en locatie](#check-the-delivery-action-and-location).

    - [Bekijk de tijdlijn van uw e-mail.](#view-the-timeline-of-your-email)

    ##### <a name="check-the-delivery-action-and-location"></a>Controleer de leveringsactie en -locatie

    In [Threat Explorer (en real-time detecties)](threat-explorer.md)hebt u nu **kolommen Leveringsactie** en **leveringslocatie** in plaats van de voormalige kolom **Leveringsstatus.** Dit resulteert in een completer beeld van waar uw e-mailberichten landen. Een deel van het doel van deze wijziging is om onderzoeken gemakkelijker te maken voor beveiligingsteams, maar het nettoresultaat is het in één oogopslag kennen van de locatie van probleeme-mailberichten.

    De leveringsstatus is nu opgesplitst in twee kolommen:

    - **Bezorgactie** - Wat is de status van deze e-mail?

    - **Leveringslocatie** - Waar is deze e-mail naartoe gerouteerd?

    Leveringsactie is de actie die wordt uitgevoerd op een e-mail vanwege bestaande beleidsregels of detecties. Hier zijn de mogelijke acties die een e-mail kan ondernemen:

    - **Geleverd** - e-mail is geleverd aan de inbox of map van een gebruiker en de gebruiker heeft er rechtstreeks toegang toe.

    - **Ongewenste** e-mail is verzonden naar de ongewenste map van een gebruiker of verwijderde map, en de gebruiker heeft toegang tot e-mailberichten in de map Ongewenste of verwijderde.

    - **Geblokkeerd** : alle e-mailberichten die in quarantaine zijn geplaatst, die zijn mislukt of zijn verwijderd. (Dit is volledig ontoegankelijk voor de gebruiker.)

    - **Vervangen** : elke e-mail waarin schadelijke bijlagen worden vervangen door .txt-bestanden waarin staat dat de bijlage schadelijk was.
 
    De leveringslocatie toont de resultaten van beleid en detecties die na levering worden uitgevoerd. Het is gekoppeld aan een bezorgactie. Dit veld is toegevoegd om inzicht te geven in de actie die wordt ondernomen wanneer een probleemmail wordt gevonden. Hier zijn de mogelijke waarden van de levering locatie:

    - **Postvak IN of map** : de e-mail bevindt zich in de inbox of een map (volgens uw e-mailregels).

    - **On-prem of extern** – Het postvak bestaat niet in de cloud, maar is on-premises.

    - **Map ongewenste e-mail** : de e-mail bevindt zich in de map Ongewenste e-mail.

    - **Map verwijderde items :** de e-mail bevindt zich in de map Verwijderde items van een gebruiker.

    - **Quarantaine** : de e-mail in quarantaine en niet in het postvak van een gebruiker.

    - **Mislukt** : de e-mail kan het postvak niet bereiken.

    - **Dropped** - De e-mail gaat ergens verloren in de e-mailstroom.

     ##### <a name="view-the-timeline-of-your-email"></a>De tijdlijn van uw e-mail weergeven
  
     **E-mailtijdlijn** is een veld in Threat Explorer dat de jacht eenvoudiger maakt voor uw beveiligingsteam. Wanneer meerdere gebeurtenissen op of in de buurt van dezelfde tijd op een e-mail plaatsvinden, worden deze gebeurtenissen weergegeven in een tijdlijnweergave. Sommige gebeurtenissen die plaatsvinden na levering aan e-mail worden vastgelegd in de kolom **Speciale acties.** Het combineren van informatie uit de tijdlijn van een e-mailbericht met speciale acties die na de levering zijn uitgevoerd, geeft beheerders inzicht in beleid en bedreigingsafhandeling (zoals waar de e-mail is gerouteerd en, in sommige gevallen, wat de uiteindelijke beoordeling was).

<!-- Reference material

1. **Navigate to Threat Explorer**: Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center. 

2. In the left navigation quick-launch, choose **Threat management** \> **Explorer**.

3. Click on the subject of an email message, and then click **Email timeline**. (It appears among other headings on the panel like **Summary** or **Details**.)

    Once you've opened the email timeline, you should see a table that tells you the post-delivery events for that mail. In the case of no further events for the email, you should see a single event for the original delivery that states a result like **Blocked** with a verdict like **Phish**. The tab also has the option to export the entire email timeline, and this exports all the details on the tab and details on the email (things like Subject, Sender, Recipient, Network, and Message ID).

    The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived. When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view. 
    
    Some events that happen post-delivery to your mail are captured in the **Special actions** column. Combining the information from the email timeline along with special actions taken on email post-delivery gives admins insight into how their policies work, where the email was finally routed, and, in some cases, what the final assessment was. 

4. In the **View** menu, choose **All email**.

    ![Use the View menu to choose between Email and Content reports](../../media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
    Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.

    ![Threat Explorer showing data for all email](../../media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)
    
    (Depending on the actions that were taken on email messages for your organization, you might see other labels, such as **Blocked** or **Replaced**.)
    
5. In the report, choose **Delivered** to view only email messages that ended up in users' inboxes.

    ![Clicking "Delivered to junk" removes that data from view](../../media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Below the chart, review the **Email** list below the chart.

    ![Below the chart, view a list of email messages that were detected](../../media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.

    ![You can view additional information about an item](../../media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. After viewing information about email messages, select one or more items in the list to activate **+ Actions**.
    
9. Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This deletes the selected messages from the recipients' mailboxes.

    ![When you select one or more email messages, you can choose from several available actions](../../media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)

## Dealing with suspicious email messages

Malicious attackers might be sending mail to people in your organization in an attempt to phish their credentials and gain access to your corporate secrets. To help prevent this, you use the threat protection services in Office 365, including [Exchange Online Protection](exchange-online-protection-overview.md) and [Advanced Threat Protection](office-365-atp.md). However, it occasionally happens that an attacker sends email that contains a link (URL) that only later points to malicious content (such as malware). Or, you might realize too late that someone in your organization has been compromised, and while they were compromised, an attacker used their account to send email to other people in your organization. As part of dealing with either of these scenarios, you can remove suspicious email messages from user inboxes. To do that, you can use [Threat Explorer](threat-explorer.md).

## Finding re-routed email messages after actions are taken

Threat Explorer provides your security operations team with the details they need to investigate suspicious email. Your security operations team can:

- [View the email headers and download the email body](#view-the-email-headers-and-download-the-email-body) 

- [Check the delivery action and location](#check-the-delivery-action-and-location)

- [View the timeline of your email](#view-the-timeline-of-your-email)

### View the email headers and download the email body

The ability to preview email headers and download the body of an email body are powerful capabilities in Threat Explorer. Appropriate [permissions](permissions-in-the-security-and-compliance-center.md) must be assigned. See [Preview role permissions](#preview-role-permissions).

To access your message header and email download options, follow these steps: 

1. Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center. 
    
2. In the left navigation, choose **Threat management** \> **Explorer**.

3. Click on a subject in the Threat Explorer table. 

    This opens the flyout, where both header preview and email download links are positioned.

    ![Threat Explorer flyout with download and preview links on the page.](../../media/ThreatExplorerDownloadandPreview.PNG)

> [!IMPORTANT]
> This capability doesn't show up for email messages that were never found in a user's mailbox, which can happen if an email was dropped or its delivery failed. In cases where email messages were deleted from users' mailboxes, admins see a "Mail not found" error message.
-->

## <a name="related-topics"></a>Verwante onderwerpen

[Office 365 Advanced Threat Protection](office-365-ti.md)
  
[Beschermen tegen bedreigingen in Office 365](protect-against-threats.md)
  
[Rapporten weergeven voor geavanceerde bedreigingsbeveiliging van Office 365](view-reports-for-atp.md)
