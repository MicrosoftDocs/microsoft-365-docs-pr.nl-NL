---
title: Aanvragen voor klantenvergrendeling
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
description: Meer informatie over klantvergrendelingsaanvragen waarmee u kunt bepalen hoe een ondersteuningsmedewerker van Microsoft toegang heeft tot uw gegevens wanneer er een probleem is.
ms.openlocfilehash: 6a6a1d45bfbc8b7c65d9ac8d58eb246643505c4f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162088"
---
# <a name="customer-lockbox-in-office-365"></a>Klanten lockbox in Office 365

Dit artikel bevat implementatie- en configuratie-richtlijnen voor Customer Lockbox. Customer Lockbox ondersteunt aanvragen voor toegang tot gegevens in Exchange Online, SharePoint Online en OneDrive voor Bedrijven. Als u ondersteuning voor andere services wilt aanbevelen, dient u een aanvraag in [Office 365 UserVoice.](https://office365.uservoice.com/)

Zie de richtlijnen voor Microsoft 365-licentieverlening voor beveiligings- en compliance Microsoft 365 als u de opties wilt bekijken voor het gebruik van Microsoft 365-complianceaanbiedingen, waaronder [deze,](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)&.

Customer Lockbox zorgt ervoor dat Microsoft geen toegang heeft tot uw inhoud om een servicebewerking uit te voeren zonder uw expliciete goedkeuring. Customer Lockbox brengt u in de goedkeuringswerkstroom voor aanvragen voor toegang tot uw inhoud.

Af en toe helpen Microsoft-technici bij het oplossen en oplossen van problemen met klanten die zijn gerapporteerd in het ondersteuningsproces. Meestal worden problemen opgelost via uitgebreide telemetrie- en debugprogramma's die Microsoft voor haar services heeft. In sommige gevallen moet een Microsoft-technicus echter toegang hebben tot klantinhoud om de hoofdoorzaak te bepalen en het probleem op te lossen. Voor Customer Lockbox moet de technicus toegang aanvragen bij de klant als laatste stap in de goedkeuringswerkstroom. Dit biedt organisaties de mogelijkheid om deze aanvragen goed te keuren of te weigeren en directe toegangsbeheer te bieden aan de klant.

### <a name="customer-lockbox-overview-video"></a>Overzichtsvideo klantenvergrendeling

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

## <a name="customer-lockbox-workflow"></a>Werkstroom Klantenvergrendeling

In de volgende stappen wordt een overzicht van de gebruikelijke werkstroom beschreven wanneer een Microsoft-engineer een klantvergrendelingsaanvraag start:

1. Iemand bij een organisatie ervaart een probleem met zijn Microsoft 365 postvak.

2. Nadat de gebruiker het probleem heeft opgelost, maar het probleem niet kan oplossen, wordt er een ondersteuningsaanvraag geopend met Microsoft Support.

3. Een ondersteuningsmedewerker van Microsoft controleert de serviceaanvraag en bepaalt of u toegang moet krijgen tot de tenant van de organisatie om het probleem in de Exchange Online.

4. De ondersteuningstechnicus van Microsoft meldt zich aan bij het aanvraagprogramma Customer Lockbox en doet een aanvraag voor gegevenstoegang met de tenantnaam van de organisatie, het serviceaanvraagnummer en de geschatte tijd dat de technicus toegang nodig heeft tot de gegevens.

5. Nadat een Microsoft Support Manager de aanvraag heeft goedgekeurd, stuurt Customer Lockbox de aangewezen goedkeurder bij de organisatie een e-mailmelding over de in behandeling zijnde toegangsaanvraag van Microsoft.

    ![Voorbeeld van een e-mailmelding voor klantenvergrendeling](../media/CustomerLockbox1.png)

   Iedereen aan wie de rol van beheerder van [customer lockbox access](/office365/admin/add-users/about-admin-roles) is toegewezen in Microsoft 365 beheercentrum, kan aanvragen voor Klantenvergrendeling goedkeuren.

6. De goedkeurder meldt zich aan bij het Microsoft 365 en keurt de aanvraag goed. Met deze stap wordt een auditrecord gemaakt die beschikbaar is door in het auditlogboek te zoeken. Zie Aanvragen voor klantenvergrendeling controleren voor [meer informatie.](#auditing-customer-lockbox-requests)

   Als de klant de aanvraag binnen 12 uur weigert of de aanvraag niet goedkeurt, verloopt de aanvraag en wordt er geen toegang verleend aan de Microsoft-engineer.

   > [!IMPORTANT]
   > Microsoft bevat geen koppelingen in e-mailmeldingen van Customer Lockbox waarvoor u zich moet aanmelden bij Office 365.

7. Nadat de goedkeurder van de organisatie de aanvraag heeft goedgekeurd, ontvangt de Microsoft-engineer het goedkeuringsbericht, meldt hij zich aan bij de tenant in Exchange Online en lost hij het probleem van de klant op. Microsoft-technici hebben de gevraagde duur om het probleem op te lossen waarna de toegang automatisch wordt ingetrokken.

> [!NOTE]
> Alle acties die door een Microsoft-technicus worden uitgevoerd, worden geregistreerd in het auditlogboek. U kunt deze auditrecords zoeken en controleren.

## <a name="turn-customer-lockbox-requests-on-or-off"></a>Klantenvergrendelingsverzoeken in- of uitschakelen

U kunt de besturingselementen voor het Klantenvergrendelingsvak in het Microsoft 365 in. Wanneer u Customer Lockbox in- of uitstijt, moet Microsoft de goedkeuring van uw organisatie verkrijgen voordat u toegang krijgt tot de inhoud van uw tenant.

1. Ga naar en meld u aan met  een werk- of schoolaccount dat is toegewezen aan de globale beheerder of de rol van de klantverbinder voor toegang tot Het postvak [https://admin.microsoft.com](https://admin.microsoft.com) IN.

2. Kies **Instellingen > Org Instellingen.**

3. Selecteer **Beveiligingsfunctie & Privacy** Customer  >  **Lockbox** Bewerken en verplaats de schakelknop naar Aan of Uit om de functie in of uit te  >  schakelen.  

    ![Require approval for Customer Lockbox](../media/CustomerLockbox4.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a>Een aanvraag voor klantenvergrendeling goedkeuren of weigeren

1. Ga naar en meld u aan met  een werk- of schoolaccount dat is toegewezen aan de globale beheerder of de rol van de klantverbinder voor toegang tot Het postvak [https://admin.microsoft.com](https://admin.microsoft.com) IN.

2. Kies **Ondersteuning voor > Klantenvergrendelingsverzoeken.**

    ![Klik op Ondersteuning en klik vervolgens op Klantvergrendelingsaanvragen](../media/CustomerLockbox5.png)

    Er wordt een lijst met klantvergrendelingsaanvragen weergegeven.

    ![Lijst met klantvergrendelingsaanvragen](../media/CustomerLockbox6.png)

3. Selecteer een klantvergrendelingsaanvraag en kies **goedkeuren of** **Weigeren.**

    ![Klanten lockbox-aanvragen goedkeuren of weigeren](../media/CustomerLockbox7.png)

    Er wordt een bevestigingsbericht weergegeven over de goedkeuring van de aanvraag voor het Klantenvergrendelingsvak.

    ![Klanten lockbox-aanvragen goedkeuren of weigeren](../media/CustomerLockbox8.png)

> [!NOTE]
> Gebruik de Set-AccessToCustomerDataRequest cmdlet voor het goedkeuren, weigeren of annuleren van Microsoft 365 klantenvergrendelingsverzoeken die de toegang tot uw gegevens bepalen door ondersteuningstechnici van Microsoft. Zie [Set-AccessToCustomerDataRequest](/powershell/module/exchange/set-accesstocustomerdatarequest)voor meer informatie.


## <a name="auditing-customer-lockbox-requests"></a>Aanvragen voor klantenvergrendeling controleren

Auditrecords die overeenkomen met de aanvragen voor Klantenvergrendeling worden geregistreerd in het auditlogboek. U kunt deze logboeken openen met behulp van het [zoekprogramma voor auditlogboeken](search-the-audit-log-in-security-and-compliance.md) in & compliancecentrum. Acties met betrekking tot het accepteren of weigeren van een aanvraag voor het Klantenvergrendelingsvak en acties die worden uitgevoerd door Microsoft-technici (wanneer toegangsaanvragen worden goedgekeurd) worden ook geregistreerd in het auditlogboek. U kunt deze auditrecords zoeken en controleren.

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a>In het auditlogboek zoeken naar activiteiten met betrekking tot klantvergrendelingsaanvragen

Voordat u het auditlogboek kunt gebruiken om aanvragen voor Klantenvergrendeling bij te houden, moet u enkele stappen uitvoeren om auditlogboekregistratie in te stellen. Zie Het auditlogboek doorzoeken in het beveiligings- & [compliancecentrum voor meer informatie.](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin) Nadat u de installatie hebt voltooid, gebruikt u deze stappen om een zoekquery voor auditlogboek te maken om auditrecords met betrekking tot Customer Lockbox te retourneren:

1. Ga naar [https://protection.office.com](https://protection.office.com).
  
2. Meld u aan met uw werk- of schoolaccount.

3. Kies in het linkerdeelvenster van het & Compliancecentrum de optie **Zoeken & zoeken in** het  >  **auditlogboek.**

    De **zoekpagina Auditlogboek** wordt weergegeven.

    ![Zoekpagina auditlogboek](../media/auditlogsearch1.png)
  
4. De volgende zoekcriteria configureren:

    1. **Activiteiten:** Laat dit veld leeg zodat de zoekopdracht auditrecords retourneert voor alle activiteiten. Dit is nodig om controlerecords te retourneren die betrekking hebben op aanvragen voor Klantenvergrendeling en bijbehorende activiteiten die door Microsoft-technici zijn uitgevoerd.

    1. **Begindatum** en **einddatum:** selecteer een datum en tijdbereik om de gebeurtenissen weer te geven die binnen die periode hebben plaatsgevonden.

    1. **Gebruikers:** laat dit veld leeg.

    1. **Bestand, map of site:** laat dit veld leeg.

5. Klik **op Zoeken** om de zoekopdracht uit te voeren met behulp van uw zoekcriteria.

    De zoekresultaten worden geladen en na enkele ogenblikken worden ze weergegeven onder Resultaten **op** de **zoekpagina** auditlogboek.

6. Klik **op Resultaten filteren** op de pagina met zoekresultaten en ga op een van de volgende dingen te werk:

   - Als u auditrecords wilt weergeven die betrekking hebben op een goedkeurder in uw  organisatie, waarmee u een aanvraag voor klantenvergrendeling goedkeurt of weigert: Typ in het vak onder de kolom **Activiteit Set-AccessToCustomerDataRequest**.

   - Als u auditrecords wilt weergeven die betrekking hebben op een Microsoft-technicus  die acties uitwerkt in reactie op een goedgekeurde aanvraag voor klantenvergrendeling: Typ Microsoft Operator in het vak onder de kolom **Gebruiker.** In **de kolom** Activiteit wordt de actie weergegeven die door de technicus is uitgevoerd.

      ![Filteren op 'Microsoft Operator' om auditrecords weer te geven](../media/CustomerLockbox10.png)

7. Klik in de lijst met resultaten op een auditrecord om deze weer te geven.

### <a name="audit-record-for-a-customer-lockbox-access-request"></a>Auditrecord voor een toegangsaanvraag voor Klantenvergrendeling

Wanneer een persoon in uw organisatie een aanvraag voor klantenvergrendeling goedkeurt of ontkent, wordt er een auditrecord geregistreerd in het auditlogboek. Deze record bevat de volgende informatie.

| De eigenschap Auditrecord| Beschrijving|
|:---------- |:----------|
| Datum       | De datum en tijd waarop de aanvraag voor het Klantenvergrendelingsvak is goedgekeurd of geweigerd.
| IP-adres | Het IP-adres van de computer die de goedkeurder heeft gebruikt om een aanvraag goed te keuren of te weigeren. |
| Gebruiker       | Het serviceaccount BOXServiceAccount@ \[ customerforest \] .prod.outlook.com.            |
| Activiteit   | Set-AccessToCustomerDataRequest; Dit is de controleactiviteit die wordt geregistreerd wanneer u een aanvraag voor klantenvergrendeling goedkeurt of weigert.                                |
| Item       | De Guid van de aanvraag voor het klantenvergrendelingsvak                             |

In de volgende schermafbeelding ziet u een voorbeeld van een auditlogboekrecord die overeenkomt met een goedgekeurde aanvraag voor klantenvergrendeling. Als een klantvergrendelingsaanvraag is geweigerd, is de waarde van de parameter **ApprovalDecision** **Weigeren**.

![Auditrecord voor een goedgekeurde aanvraag voor klantenvergrendeling](../media/CustomerLockbox9.png)

> [!TIP]
> Als u meer gedetailleerde informatie wilt weergeven in een auditrecord, klikt u op **Meer informatie.**

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a>Auditrecord voor een actie uitgevoerd door een Microsoft-engineer

De acties die door een Microsoft-technicus worden uitgevoerd nadat een aanvraag voor klantenvergrendeling is goedgekeurd (en die kunnen leiden tot toegang tot klantinhoud) worden geregistreerd in het auditlogboek. Deze records bevatten de volgende informatie.

| De eigenschap Auditrecord| Beschrijving|
|:---------- |:----------|
| Datum       | Datum waarop de actie is uitgevoerd. Houd er rekening mee dat de tijd dat deze actie is uitgevoerd binnen 4 uur na de goedkeuring van de aanvraag voor het Klantenvergrendelingsvak is uitgevoerd.              |
| IP-adres | Het IP-adres van de computer die Door Microsoft is gebruikt. |
| Gebruiker       | Microsoft Operator; deze waarde geeft aan dat deze record is gerelateerd aan een aanvraag voor klantenvergrendeling.                                  |
| Activiteit   | Naam van de activiteit die is uitgevoerd door de Microsoft-engineer.|
| Item       | \<empty\>                                             |

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

#### <a name="which-microsoft-365-services-does-customer-lockbox-apply-to"></a>Op Microsoft 365 services is Customer Lockbox van toepassing?

Customer Lockbox wordt momenteel ondersteund in Exchange Online, SharePoint Online en OneDrive voor Bedrijven.

#### <a name="is-customer-lockbox-available-to-all-customers"></a>Is Customer Lockbox beschikbaar voor alle klanten?

Customer Lockbox is opgenomen in Microsoft 365- of Office 365 E5-abonnementen en kan worden toegevoegd aan andere abonnementen met een invoegabonnement voor informatiebescherming en naleving of een advanced compliance-invoegabonnement. Zie [Abonnementen en prijzen voor](https://products.office.com/business/office-365-enterprise-e5-business-software) meer informatie.

#### <a name="what-is-customer-content"></a>Wat is klantinhoud?

Klantinhoud is de gegevens die zijn gemaakt door gebruikers van Microsoft 365 services en toepassingen. Voorbeelden van klantinhoud zijn:

- E-mailbijlagen of e-mailbijlagen

- SharePoint site-inhoud

- Informatie in de body van een SharePoint bestand

- Skype voor Bedrijven de bestandsindeling van de presentatie

- Chatberichten (chatberichten) of spraakgesprekken

- Door klanten gegenereerde blob- of gestructureerde opslaggegevens (bijvoorbeeld SQL Containers)

- Beveiligingsgegevens van klanten (bijvoorbeeld certificaten, versleutelingssleutels en wachtwoorden)

- Gevolgtrekkingen en alle daaropvolgende gevolgtrekkingen, als klantinhoud blijft bestaan

Zie het Office 365 vertrouwenscentrum voor [meer Office 365 klantinhoud in Office 365.](https://products.office.com/business/office-365-trust-center-privacy/)

#### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a>Wie wordt een melding ontvangen wanneer er een verzoek is om toegang te krijgen tot mijn inhoud?

Globale beheerders en iedereen die de rol klantvergrendeling voor toegangstoegang heeft toegewezen, wordt op de hoogte gesteld. Dit zijn ook dezelfde gebruikers die aanvragen voor Klantenvergrendeling kunnen goedkeuren.

#### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a>Wie kan ik deze aanvragen in mijn organisatie goedkeuren of weigeren?

Globale beheerders en iedereen die de rol klantvergrendeling voor toegangstoegang heeft toegewezen, kan aanvragen voor Klantenvergrendeling goedkeuren. Klanten bepalen deze roltoewijzingen in hun organisatie.

#### <a name="how-do-i-opt-in-to-customer-lockbox"></a>Hoe kan ik me bij Customer Lockbox aan?

Een globale beheerder kan het postvak Klantvergrendeling inschakelen en configureren in het Microsoft 365 of Microsoft 365 beheercentrum.

#### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a>Als ik een aanvraag voor klantenvergrendeling goedkeur, wat kan de technicus dan doen en hoe weet ik wat de Microsoft-engineer heeft gedaan?

Nadat u een klantvergrendelingsaanvraag hebt goedgekeurd, heeft de Microsoft-engineer deze benodigde bevoegdheden verleend voor toegang tot klantinhoud met behulp van vooraf goedgekeurde cmdlets. Acties die door Microsoft-technici zijn uitgevoerd in reactie op aanvragen voor klantenvergrendeling, worden geregistreerd en toegankelijk in het auditlogboek in het beveiligings- & Compliancecentrum.

#### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a>Hoe weet ik of Microsoft het goedkeuringsproces volgt?

U kunt de e-mailgoedkeuringsmeldingen die naar beheerders en goedkeurders in uw organisatie zijn verzonden, kruisen met de aanvraaggeschiedenis klantvergrendeling in het Microsoft 365 beheercentrum.

Customer Lockbox is opgenomen in het meest recente [SOC 1 SSAE 16-auditrapport.](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports) Voor meer informatie vindt u de meest recente rapporten in de [Microsoft Service Trust Portal.](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)

#### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a>Kan Microsoft de lijst met goedkeurders voor mijn tenant wijzigen? Zo niet, hoe wordt dit voorkomen?

Alleen een globale beheerder in uw organisatie kan opgeven wie klantvergrendelingsaanvragen kan goedkeuren. Dat betekent dat alleen de leden van de groep globale beheerders in Azure Active Directory kunnen opgeven wie de aanvraag kan goedkeuren. Lidmaatschap van de groep Globale beheerder in Azure Active Directory wordt alleen beheerd door uw organisatie.

#### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a>Wat moet ik doen als ik meer informatie nodig heb over een aanvraag voor inhoudstoegang om het goed te keuren?

Elke klantvergrendelingsaanvraag bevat een Microsoft 365 serviceaanvraagnummer. U kunt contact opnemen met Microsoft Support en naar dit servicenummer verwijzen voor meer informatie over de aanvraag.

#### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a>Wanneer een aanvraag voor klantenvergrendeling is goedgekeurd, hoe lang zijn de machtigingen geldig?

Momenteel is de maximumperiode voor de toegangsmachtigingen die aan de Microsoft-engineer zijn verleend, 4 uur. De Microsoft-engineer kan ook een kortere periode aanvragen.

#### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a>Hoe kan ik een geschiedenis krijgen van alle klantvergrendelingsaanvragen?

Alle klantvergrendelingsaanvragen worden bekeken in het Microsoft 365 beheercentrum.

#### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a>Hoe correleer ik de aanvragen voor inhoudstoegang met de gerelateerde auditlogboeken?

De compliancecentrumactiviteitsfeed bevat logboekactiviteiten van Customer Lockbox. Klanten kunnen de logboekactiviteiten van Customer Lockbox uit de activiteitsfeed kruisen aan de e-mailaanvraag die ze ontvangen.

#### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a>Wat gebeurt er als een klant niet reageert op een klantvergrendelingsaanvraag?

Klantenvergrendelingsaanvragen hebben een standaardduur van 12 uur. Als u niet binnen 12 uur op een aanvraag reageert, verloopt de aanvraag.

#### <a name="what-does-microsoft-do-when-a-customer-rejects-a-customer-lockbox-request"></a>Wat doet Microsoft als een klant een aanvraag voor klantenvergrendeling weigert?

Als een klant een aanvraag voor klantenvergrendeling weigert, vindt er geen toegang tot klantinhoud plaats. Als een gebruiker in uw organisatie nog steeds te maken krijgt met een serviceprobleem waarbij Microsoft toegang heeft tot klantinhoud om het probleem op te lossen, kan het serviceprobleem zich voordoen en zal Microsoft de gebruiker hiervan op de hoogte stellen.

#### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a>Beschermt Customer Lockbox zich tegen gegevensaanvragen van rechtshandhavingsinstanties of andere derden?

Nee. Microsoft neemt verzoeken van derden voor klantgegevens serieus. Als cloudserviceprovider is Microsoft altijd voorstander van de privacy van klantgegevens. In het geval we een dagvaarding krijgen, probeert Microsoft altijd de derde partij om te leiden naar de klant om de informatie te verkrijgen. (Lees Brad Smith's blog: [Bescherm klantgegevens tegen overheidsinkijkers).](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/) We publiceren regelmatig gedetailleerde [informatie over](https://www.microsoft.com/corporate-responsibility/lerr) de verzoeken om de wetshandhaving die Microsoft ontvangt.

Zie het [Microsoft Trust Center met](https://www.microsoft.com/trustcenter/default.aspx) betrekking tot gegevensaanvragen van derden en de sectie 'Openbaarmaking van klantgegevens' in de Voorwaarden voor [onlineservices](https://www.microsoft.com/Licensing/product-licensing/products.aspx) voor meer informatie.

#### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a>Hoe zorgt Microsoft ervoor dat een lid van zijn personeel geen permanente toegang heeft tot klantinhoud in Office 365 toepassingen?

Microsoft implementeert uitgebreide, preventieve maatregelen via toegangscontrolesystemen en maatregelen om pogingen om deze toegangscontrolesystemen te omzeilen te identificeren en aan te pakken. Microsoft 365 werkt met de principes van de minste bevoegdheden en just-in-time toegang. Daarom hebben geen microsoft-medewerkers toestemming om doorlopend toegang te krijgen tot klantinhoud. Als er toestemming wordt verleend, is dit voor een beperkte duur. 

Microsoft 365 gebruikt een toegangsbesturingselementsysteem genaamd *Lockbox* om aanvragen voor machtigingen te verwerken die de mogelijkheid bieden om operationele en beheerfuncties binnen de service uit te voeren. Een operator moet toegang tot klantinhoud aanvragen met Lockbox, waarna een tweede persoon actie moet ondernemen op de aanvraag (bijvoorbeeld goedkeuren) voordat toegang wordt verleend. Die tweede persoon kan de aanvraaggever niet zijn en moet worden aangewezen om toegang tot klantinhoud goed te keuren. Alleen als de aanvraag is goedgekeurd, krijgt de operator tijdelijke toegang tot klantinhoud. Nadat de hoogteperiode is verlopen, wordt de toegang ingetrokken door Lockbox.

Raadpleeg de Voorwaarden voor [onlineservices voor](https://www.microsoft.com/licensing/product-licensing/products) meer informatie over algemene beveiligingspraktijken van Microsoft.

#### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a>In welke omstandigheden hebben Microsoft-technici toegang nodig tot mijn inhoud?

Het meest voorkomende scenario waarbij Microsoft-technici toegang tot klantinhoud nodig hebben, is wanneer de klant een ondersteuningsaanvraag indient die toegang vereist voor probleemoplossing. Een basisprincipe van Microsoft 365 is dat de service werkt zonder microsoft-toegang tot klantinhoud. Bijna alle servicebewerkingen die door Microsoft worden uitgevoerd, zijn volledig geautomatiseerd en de betrokkenheid van mensen wordt sterk gecontroleerd en verwijderd van klantinhoud. Het doel voor Microsoft 365 is toegang tot klantinhoud om de service te ondersteunen, is pas nodig als de klant een specifieke aanvraag voor Microsoft-toegang goedkeurt.

#### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a>Ik dacht al dat mijn gegevens veilig waren met de Microsoft-cloud, dus waarom heb ik Customer Lockbox nodig?

Customer Lockbox biedt een extra controlelaag door klanten de mogelijkheid te bieden expliciete toegang te verlenen voor servicebewerkingen. Door aan te tonen dat procedures zijn ingevoerd voor expliciete machtiging voor gegevenstoegang, helpt Customer Lockbox klanten ook om te voldoen aan bepaalde nalevingsverplichtingen, zoals HIPAA en FEDRAMP.