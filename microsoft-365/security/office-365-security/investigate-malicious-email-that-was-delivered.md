---
title: Kwaadaardige e-mail onderzoeken die is geleverd in Office 365, Schadelijke e-mail zoeken en onderzoeken
keywords: TIMailData-Inline, Security Incident, incident, ATP PowerShell, e-mail malware, gecompromitteerde gebruikers, e-mail phish, e-mail malware, lees e-mail headers, lees headers, open e-mail headers
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 07/09/2020
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
description: Meer informatie over het gebruik van mogelijkheden voor dreigingsonderzoek en -respons om schadelijke e-mail te vinden en te onderzoeken.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 747b6b875a3b7ebc8125ac27ed00c9a300845427
ms.sourcegitcommit: a4926e98b6594bbee68bfca90438c9c764499255
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2020
ms.locfileid: "45091957"
---
# <a name="investigate-malicious-email-that-was-delivered-in-office-365"></a>Kwaadaardige e-mail onderzoeken die is geleverd in Office 365

[Met Office 365 Advanced Threat Protection](office-365-atp.md) u activiteiten onderzoeken die mensen in uw organisatie in gevaar brengen en actie ondernemen om uw organisatie te beschermen. Als u bijvoorbeeld deel uitmaakt van het beveiligingsteam van uw organisatie, u verdachte e-mailberichten vinden en onderzoeken die zijn bezorgd. U dit doen met [Threat Explorer (of real-time detecties).](threat-explorer.md)

> [!NOTE]
> Ga naar de sanering artikel [hier](https://docs.microsoft.com/microsoft-365/security/mtp/article-submission/remediate-malicious-email-delivered-office-365?view=o365-21vianet&branch=pr-en-us-4258).
  
## <a name="before-you-begin"></a>Voordat u begint

Controleer of aan de volgende voorwaarden wordt voldaan:
  
- Uw organisatie heeft [Geavanceerde bedreigingsbeveiliging van Office 365](office-365-atp.md) en [licenties worden toegewezen aan gebruikers.](../../admin/manage/assign-licenses-to-users.md)
    
- [controlelogboekregistratie](../../compliance/turn-audit-log-search-on-or-off.md) is ingeschakeld voor uw organisatie. 
    
- Uw organisatie heeft beleid gedefinieerd voor anti-spam, anti-malware, anti-phishing, enzovoort. Zie [Beschermen tegen bedreigingen in Office 365](protect-against-threats.md).
    
- U bent een globale beheerder of u hebt de beveiligingsbeheerder of de rol Zoeken en zuiveren toegewezen in het Security &amp; Compliance Center. Zie [Machtigingen in het Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md). Voor sommige acties moet u ook een nieuwe voorbeeldrol hebben toegewezen. 

#### <a name="preview-role-permissions"></a>Voorbeeld van functiemachtigingen

Als u bepaalde acties wilt uitvoeren, zoals het bekijken van berichtkoppen of het downloaden van inhoud van e-mailberichten, moet u een nieuwe rol met de naam *Voorbeeld* hebben toegevoegd aan een andere geschikte rolgroep. In de volgende tabel worden vereiste rollen en machtigingen verduidelijkt.

|Activiteit  |Rolgroep |Voorbeeld rol nodig?  |
|---------|---------|---------|
|Threat Explorer (en realtime detecties) gebruiken om bedreigingen te analyseren     |Globale beheerder <br> Beveiligingsbeheerder <br> Beveiligingslezer     | Nee   |
|Gebruik Threat Explorer (en realtime detecties) om kopteksten voor e-mailberichten weer te geven en e-mailberichten in quarantaine te bekijken en te downloaden    |Globale beheerder <br> Beveiligingsbeheerder <br>Beveiligingslezer   |       Nee  |
|Threat Explorer gebruiken om kopteksten weer te geven en e-mailberichten te downloaden die aan postvakken worden bezorgd     |Globale beheerder <br>Beveiligingsbeheerder <br> Beveiligingslezer <br> Voorbeeld   |   Ja      |

> [!NOTE]
> *Voorbeeld* is een rol en geen rolgroep; de voorbeeldrol moet worden toegevoegd aan een bestaande rolgroep voor Office 365. De rol Global Administrator krijgt het Microsoft 365-beheercentrum [https://admin.microsoft.com](https://admin.microsoft.com) toegewezen en de rollen Beveiligingsbeheerder en beveiligingslezer worden toegewezen in het Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) ). Zie [Machtigingen in het Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over rollen en machtigingen.

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>Verdachte e-mail zoeken en verwijderen die is bezorgd

Threat Explorer is een krachtig rapport dat meerdere doeleinden kan dienen, zoals het vinden en verwijderen van berichten, het identificeren van het IP-adres van een kwaadwillende e-mailverzender of het starten van een incident voor verder onderzoek. De volgende procedure is gericht op het gebruik van Explorer om schadelijke e-mail uit de postvakken van de ontvanger te zoeken en te verwijderen.

> [!NOTE]
> Standaardzoekopdrachten in Explorer bevatten momenteel geen zapped-items.  Dit geldt voor alle weergaven, bijvoorbeeld malware of phish views. Als je Zapped items wilt toevoegen, moet je een 'Delivery action' toevoegen die is ingesteld om 'Verwijderd door ZAP' op te nemen. Als je alle opties opneemt, zie je alle resultaten van de leveringsactie, inclusief Zapped-items.

1. **Navigeren naar Threat Explorer**: ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw werk- of schoolaccount voor Office 365. Dit brengt u naar het Security &amp; Compliance Center.

2. Kies in de snelle lancering van de navigatie in de linkernavigatie de optie **Bedreigingsbeheer** \> **Explorer**.

    ![Explorer met velden Leveringsactie en Leveringslocatie.](../../media/ThreatExFields.PNG)

    <!-- You may notice the new **Special actions** column. This feature is aimed at telling admins the outcome of processing an email. The **Special actions** column can be accessed in the same place as **Delivery action** and **Delivery location**. Special actions might be updated at the end of Threat Explorer's email timeline, which is a new feature aimed at making the hunting experience better for admins.-->

3. **Weergaven in Threat Explorer:** kies in het menu **Weergave** **Alle e-mail**.

    ![Threat explorer View menu, en E-mail - Malware, Phish, Inzendingen en alle e-mail opties, ook Inhoud - Malware.](../../media/tp-InvestigateMalEmail-viewmenu.png)

    De *malware* weergave is momenteel de standaard, en vangt e-mails waar een malware bedreiging wordt gedetecteerd. De *Phish-weergave* werkt op dezelfde manier, voor Phish.

    Alle *e-mailweergave* bevat echter elke e-mail die door de organisatie is ontvangen, ongeacht of er bedreigingen zijn gedetecteerd of niet. Zoals u zich voorstellen, dit is veel gegevens, dat is de reden waarom deze weergave toont een tijdelijke aanduiding die vraagt een filter worden toegepast. (Deze weergave is alleen beschikbaar voor ATP P2-klanten.)

    *Inzendingen* weergave toont alle e-mails ingediend door admin of gebruiker die zijn gemeld aan Microsoft.

4. **Zoeken en filteren in Threat Explorer:** Filters worden boven aan de pagina in de zoekbalk weergegeven om beheerders te helpen bij hun onderzoeken. U ziet dat meerdere filters tegelijkertijd kunnen worden toegepast en dat er meerdere door komma's gescheiden waarden aan een filter kunnen worden toegevoegd om de zoekopdracht te beperken. Herinneren:
    - Filters doen exacte matching op de meeste filtervoorwaarden.
    - Onderwerpfilter maakt gebruik van een CONTAINS-query.
    - URL-filters werken met of zonder protocollen (bijvoorbeeld. https).
    - URL-domein, URL-pad en URL-domein- en padfilters vereisen geen protocol om te filteren.
    - U moet op het pictogram Vernieuwen klikken telkens wanneer u de filterwaarden wijzigt om relevante resultaten te krijgen.

5. **Geavanceerde filters:** met deze filters u complexe query's bouwen en uw gegevensset filteren. Als u op *Geavanceerde filters klikt,* opent u een flyout met opties.

   Geavanceerde filtering is een geweldige aanvulling op zoekmogelijkheden. Er is een booleaan **NOT-filter** geïntroduceerd op het domein *Ontvanger,* *Afzender* en *afzender,* zodat beheerders dit kunnen onderzoeken door waarden uit te sluiten. Deze optie wordt weergegeven onder *selectieparameter Bevat geen van*. **NOT** laat beheerders waarschuwingspostvakken uitsluiten, standaard antwoordpostvakken van hun onderzoeken en is handig voor gevallen waarin beheerders zoeken naar een specifiek onderwerp (subject="Aandacht") waarbij de ontvanger kan worden ingesteld op *geen van de \@ standaardmailpost contoso.com*. Dit is een exacte waarde zoeken.

   ![De ontvangers - 'Bevat geen van' Geavanceerd filter.](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   *Door uren te filteren,* kan het beveiligingsteam van uw organisatie snel inzoomen. De kortste toegestane tijdsduur is 30 minuten. Als u de verdachte actie beperken op tijdskader (bijvoorbeeld het gebeurde 3 uur geleden), zal dit de context beperken en helpen bij het lokaliseren van het probleem.

  ![De optie filteren op uren om de hoeveelheid gegevensbeveiligingsteams te verkleinen en waarvan de kortste duur 30 minuten is.](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. **Velden in threat explorer**: Threat Explorer onthult veel meer beveiligingsgerelateerde e-mailinformatie, zoals *leveringsactie,* *leveringslocatie,* *speciale actie,* *directionaliteit,* *overschrijvingen*en *URL-bedreiging*. Het stelt ook het beveiligingsteam van uw organisatie in staat om met een hogere zekerheid te onderzoeken. 

    *Leveringsactie* is de actie die wordt ondernomen op een e-mail vanwege bestaand beleid of detecties. Dit zijn de mogelijke acties die een e-mail kan ondernemen:
    - **Geleverd** – e-mail is geleverd in de inbox of map van een gebruiker en de gebruiker kan er rechtstreeks toegang toe krijgen.
    - **Junked** (Geleverd aan ongewenste e-mail)- e-mail is verzonden naar de ongewenste map of verwijderde map van de gebruiker en de gebruiker heeft toegang tot e-mailberichten in de map Ongewenste e-mail of verwijderd.
    - **Geblokkeerd** : e-mailberichten die in quarantaine zijn geplaatst, die zijn mislukt of zijn verwijderd. (Dit is volledig ontoegankelijk voor de gebruiker.)
    - **Vervangen** - elke e-mail waar kwaadaardige bijlagen worden vervangen door .txt-bestanden waarin de bijlage is kwaadaardig

    **Leveringslocatie:** het filter Locatie voor levering is beschikbaar om beheerders te helpen begrijpen waar vermoedelijke schadelijke e-mail is begeopt en welke acties erop zijn uitgevoerd. De resulterende gegevens kunnen worden geëxporteerd naar spreadsheet. Mogelijke bezorglocaties zijn:
    - **Postvak IN of map** : de e-mail bevindt zich in het Postvak IN of een specifieke map, volgens uw e-mailregels.
    - **On-prem of extern** : het postvak bestaat niet in de cloud, maar is on-premises.
    - **Ongewenste map** : de e-mail bevindt zich in de map Ongewenste e-mail van een gebruiker.
    - **Map Verwijderde items** : de e-mail bevindt zich in de map Verwijderde items van een gebruiker.
    - **Quarantaine** : de e-mail in quarantaine en niet in het postvak van een gebruiker.
    - **Mislukt:** de e-mail kan het postvak niet bereiken.
    - **Verwijderd** - De e-mail is ergens in de e-mailstroom verloren gegaan.

    **Directionaliteit**: Met deze optie kan uw beveiligingsteam filteren op de 'richting' waar een e-mail vandaan komt of gaat. Directionaliteitswaarden zijn *Inbound,* *Outbound*en Intra-org (wat overeenkomt met *e-mail* die van buitenaf naar uw organisatie komt, wordt verzonden vanuit uw organisatie of intern naar uw organisatie wordt verzonden). Deze informatie kan beveiligingsteams helpen spoofing en imitatie te herkennen, omdat er een mismatch is tussen de directionaliteitswaarde (ex. *Inbound*), en het domein van de afzender (die een intern domein *lijkt* te zijn) zal duidelijk zijn! De waarde Van directionaliteit is gescheiden en kan afwijken van de Berichttracering. Resultaten kunnen worden geëxporteerd naar spreadsheet.

    **Overschrijvingen**: Dit filter neemt informatie die wordt weergegeven op het tabblad details van de e-mail en *overridden*gebruikt deze om aan te geven waar het organisatie- of gebruikersbeleid is ingeschakeld voor het toestaan en blokkeren van e-mails. Het belangrijkste aan dit filter is dat het beveiligingsteam van uw organisatie helpt te zien hoeveel verdachte e-mails zijn geleverd als gevolg van configuratie. Dit geeft hen de mogelijkheid om te wijzigen maakt en blokken als dat nodig is. Deze resultatenset van dit filter kan worden geëxporteerd naar spreadsheet.

|Threat Explorer overschrijft  | Wat ze bedoelen  |
|---------|---------|
|Toegestaan door org beleid     |   E-mail was toegestaan in de mailbox, zoals aangegeven door het organisatiebeleid.       |
|Geblokkeerd door org beleid      |  E-mail is geblokkeerd voor levering aan het postvak, zoals aangegeven door het organisatiebeleid.    |
|Bestandsextensie geblokkeerd door Org Policy     | Het bestand is geblokkeerd voor levering aan het postvak, zoals aangegeven door het organisatiebeleid.        |
|Toegestaan op gebruikersbeleid     | E-mail was toegestaan in het postvak, zoals aangegeven door het gebruikersbeleid.        |
|Geblokkeerd door gebruikersbeleid     | E-mail is geblokkeerd voor levering aan het postvak, zoals aangegeven door het gebruikersbeleid.        |

**URL-bedreiging:** het veld URL-dreiging is opgenomen op het *tabblad details* van een e-mail om de dreiging aan te geven die wordt weergegeven door een URL. Bedreigingen die door een URL worden weergegeven, kunnen *malware,* *phish*of *spam*bevatten en een URL *zonder bedreiging* zal *geen* zeggen in de sectie bedreigingen.

7. **E-mailtijdlijnweergave**: Uw beveiligingsteam moet mogelijk dieper ingaan op e-maildetails om verder onderzoek te doen. Met de tijdlijn van de e-mail kunnen beheerders acties bekijken die zijn uitgevoerd op een e-mail van levering tot na levering. Als u een e-mailtijdlijn wilt weergeven, klikt u op het onderwerp van een e-mailbericht en klikt u vervolgens op Tijdlijn e-mail. (Het verschijnt onder andere koppen op het paneel zoals Samenvatting of Details.) Deze resultaten kunnen worden geëxporteerd naar spreadsheet.

    De tijdlijn van de e-mail wordt geopend voor een tabel met alle leverings- en postleveringsgebeurtenissen voor de e-mail. Als er geen verdere acties op de e-mail, moet u een enkele gebeurtenis voor de oorspronkelijke levering die een resultaat, zoals *Geblokkeerd,* met een vonnis als *Phish*staten . Beheerders kunnen de volledige e-mailtijdlijn exporteren, inclusief alle details op het tabblad en e-mail (zoals Onderwerp, afzender, ontvanger, netwerk en bericht-id). De tijdlijn van de e-mail vermindert randomisatie omdat er minder tijd wordt besteed aan het controleren van verschillende locaties om te proberen gebeurtenissen te begrijpen die zijn gebeurd sinds de e-mail is aangekomen. Wanneer meerdere gebeurtenissen plaatsvinden op of in de buurt van hetzelfde tijdstip in een e-mail, worden deze gebeurtenissen weergegeven in een tijdlijnweergave.

8. **Preview / download**: Threat Explorer geeft uw security operations team de details die ze nodig hebben om verdachte e-mail te onderzoeken. Uw beveiligingsteam kan:

    - [Controleer de leveringsactie en locatie](#check-the-delivery-action-and-location).

    - [Bekijk de tijdlijn van uw e-mail](#view-the-timeline-of-your-email).

    ##### <a name="check-the-delivery-action-and-location"></a>Controleer de leveringsactie en locatie

    In [Threat Explorer (en real-time detecties)](threat-explorer.md)hebt u nu kolommen **Met leveringsactie** en **leveringslocatie** in plaats van de voormalige kolom **Leveringsstatus.** Dit resulteert in een completer beeld van waar uw e-mailberichten landen. Een deel van het doel van deze wijziging is om onderzoeken gemakkelijker te maken voor beveiligingsteams, maar het nettoresultaat is het in één oogopslag kennen van de locatie van probleeme-mailberichten.

    De leveringsstatus is nu onderverdeeld in twee kolommen:

    - **Leveringsactie** - Wat is de status van deze e-mail?

    - **Leveringslocatie** - Waar is deze e-mail als gevolg hiervan gerouteerd?

    Leveringsactie is de actie die wordt ondernomen op een e-mail vanwege bestaand beleid of detecties. Dit zijn de mogelijke acties die een e-mail kan ondernemen:

    - **Geleverd** – e-mail is geleverd in de inbox of map van een gebruiker en de gebruiker kan er rechtstreeks toegang toe krijgen.

    - **Ongewenste e-mail** is verzonden naar de ongewenste map of verwijderde map van de gebruiker en de gebruiker heeft toegang tot e-mailberichten in de map Ongewenste e-mail of verwijderd.

    - **Geblokkeerd** : e-mailberichten die in quarantaine zijn geplaatst, die zijn mislukt of zijn verwijderd. (Dit is volledig ontoegankelijk voor de gebruiker.)

    - **Vervangen** - elke e-mail waar kwaadaardige bijlagen worden vervangen door .txt-bestanden waarin de bijlage is vermeld, was kwaadaardig.
 
    De leveringslocatie toont de resultaten van beleid en detecties die na levering worden uitgevoerd. Het is gekoppeld aan een leveringsactie. Dit veld is toegevoegd om inzicht te geven in de actie die is ondernomen wanneer een probleemmail wordt gevonden. Hier zijn de mogelijke waarden van de levering locatie:

    - **Postvak IN of map** : de e-mail bevindt zich in het postvak IN of in een map (volgens uw e-mailregels).

    - **On-prem of extern** : het postvak bestaat niet in de cloud, maar is on-premises.

    - **Ongewenste map** : de e-mail bevindt zich in de map Ongewenste e-mail van een gebruiker.

    - **Map Verwijderde items** : de e-mail bevindt zich in de map Verwijderde items van een gebruiker.

    - **Quarantaine** : de e-mail in quarantaine en niet in het postvak van een gebruiker.

    - **Mislukt:** de e-mail kan het postvak niet bereiken.

    - **Verwijderd** - De e-mail gaat ergens verloren in de e-mailstroom.

     ##### <a name="view-the-timeline-of-your-email"></a>De tijdlijn van uw e-mail weergeven
  
     **E-mailtijdlijn** is een veld in Threat Explorer dat het jagen gemakkelijker maakt voor uw beveiligingsteam. Wanneer meerdere gebeurtenissen op of in de buurt van hetzelfde tijdstip in een e-mail plaatsvinden, worden deze gebeurtenissen weergegeven in een tijdlijnweergave. Sommige gebeurtenissen die na levering aan e-mail plaatsvinden, worden vastgelegd in de kolom **Speciale acties.** Het combineren van informatie uit de tijdlijn van een e-mailbericht met speciale acties die na de levering zijn uitgevoerd, geeft beheerders inzicht in beleid en bedreigingsafhandeling (zoals waar de e-mail is doorgestuurd en, in sommige gevallen, wat de eindbeoordeling was).

> [!IMPORTANT]
> Ga naar een sanering onderwerp [hier](https://docs.microsoft.com/microsoft-365/security/mtp/article-submission/remediate-malicious-email-delivered-office-365?view=o365-worldwide).

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

[Schadelijke e-mail herstellen die in Office 365 wordt bezorgd](https://docs.microsoft.com/microsoft-365/security/mtp/article-submission/remediate-malicious-email-delivered-office-365?view=o365-worldwide)

[Office 365 Advanced Threat Protection](office-365-ti.md)
  
[Beschermen tegen bedreigingen in Office 365](protect-against-threats.md)
  
[Rapporten voor geavanceerde bedreigingsbeveiliging van Office 365 weergeven](view-reports-for-atp.md)
