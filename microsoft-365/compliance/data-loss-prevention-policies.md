---
title: Referentie voor gegevensverliespreventie
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: low
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: referentiemateriaal ter voorkoming van gegevensverlies
ms.openlocfilehash: a6dc0b2702899e05f78c54331fb33b87495672d8
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572559"
---
# <a name="data-loss-prevention-reference"></a>Referentie voor preventie van gegevensverlies
 
> [!IMPORTANT]
> Dit is referentieonderwerp is niet langer de belangrijkste bron voor Microsoft 365 DLP-informatie (Data Loss Prevention). De DLP-inhoudsset wordt bijgewerkt en geherstructureerd. De onderwerpen die in dit artikel worden behandeld, worden verplaatst naar nieuwe, bijgewerkte artikelen. Zie Meer informatie over [preventie van gegevensverlies voor](dlp-learn-about-dlp.md)meer informatie over DLP.

<!-- this topic needs to be split into smaller, more coherent ones. It is confusing as it is. -->
<!-- move this note to a more appropriate place, no topic should start with a note -->
> [!NOTE]
> Mogelijkheden voor het voorkomen van gegevensverlies zijn onlangs toegevoegd aan Microsoft Teams chat- en kanaalberichten voor gebruikers die een licentie hebben voor Office 365 Advanced Compliance, die beschikbaar is als een zelfstandige optie en is opgenomen in Office 365 E5- en Microsoft 365 E5 Compliance. Zie [Microsoft 365 Tenant-Level Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)voor services voor meer informatie over licentievereisten.



<!-- MOVED TO LEARN ABOUT To comply with business standards and industry regulations, organizations must protect sensitive information and prevent its inadvertent disclosure. Sensitive information can include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records. With a data loss prevention (DLP) policy in the Office 365 Security &amp; Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.
  
With a DLP policy, you can:
  
- **Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.**
    
    For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.
    
- **Prevent the accidental sharing of sensitive information**. 
    
    For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.
    
- **Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.**
    
    Just like in Exchange Online, SharePoint Online, and OneDrive for Business, these Office desktop programs include the same capabilities to identify sensitive information and apply DLP policies. DLP provides continuous monitoring when people share content in these Office programs.
    
- **Help users learn how to stay compliant without interrupting their workflow.**
    
    You can educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification. The same policy tips also appear in Outlook on the web, Outlook, Excel, PowerPoint, and Word.
    
- **View DLP alerts and reports showing content that matches your organization’s DLP policies.**
    
    To view alerts and metadata related to your DLP policies you can use the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md). You can also view policy match reports to assess how your organization is complying with a DLP policy. If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported

-->    
## <a name="create-and-manage-dlp-policies"></a>DLP-beleid maken en beheren

U maakt en beheert DLP-beleid op de pagina Preventie van gegevensverlies in het Microsoft 365 Compliance Center.
  
![Pagina preventie gegevensverlies in het Office 365 Security &amp; Compliance Center](../media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
<!-- MOVED TO LEARN ABOUT ## What a DLP policy contains

A DLP policy contains a few basic things:
  
- Where to protect the content: **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chat and channel messages. 
    
- When and how to protect the content by enforcing **rules** comprised of: 
    
  - **Conditions** the content must match before the rule is enforced. For example, a rule might be configured to look only for content containing Social Security numbers that's been shared with people outside your organization. 
    
  - **Actions** that you want the rule to take automatically when content matching the conditions is found. For example, a rule might be configured to block access to a document and send both the user and compliance officer an email notification. -->
    
U kunt een regel gebruiken om aan een specifieke beveiligings vereiste te voldoen en vervolgens een DLP-beleid gebruiken om gemeenschappelijke beveiligings vereisten te groeperen, zoals alle regels die nodig zijn om aan een specifieke verordening te voldoen.
  
U hebt bijvoorbeeld een DLP-beleid waarmee u de aanwezigheid van informatie kunt detecteren die onder de Health Insurance Portability and Accountability Act (HIPAA) vallen. Dit DLP-beleid kan helpen bij het beschermen van HIPAA-gegevens (de wat) op alle SharePoint online sites en alle OneDrive voor Bedrijven sites (de waar) door een document te vinden dat deze gevoelige informatie bevat die wordt gedeeld met mensen buiten uw organisatie (de voorwaarden) en vervolgens de toegang tot het document te blokkeren en een melding (de acties) te verzenden. Deze vereisten worden opgeslagen als afzonderlijke regels en gegroepeerd als een DLP-beleid om het beheer en de rapportage te vereenvoudigen.
  
![Diagram laat zien dat DLP-beleid locaties en regels bevat](../media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
<!-- MOVED TO LEARN ABOUT ### Locations

DLP policies are applied to sensitive items across Microsoft 365 locations and can be further scoped as detailed in this table.


|Location | Include/exclude by|
|---------|---------|
|Exchange email| distribution groups|
|SharePoint sites |sites |
|OneDrive accounts |accounts |
|Teams chat and channel messages |accounts |
|Windows 10 devices |user or group |
|Microsoft Cloud App Security |instance |
 -->

Als u ervoor kiest om specifieke distributiegroepen op te nemen in Exchange, wordt het DLP-beleid alleen beperkt tot de leden van die groep. Als u een distributiegroep uitsluit, worden alle leden van die distributiegroep uitgesloten van beleidsevaluatie. U kunt ervoor kiezen om een beleid te beperken tot de leden van distributielijsten, dynamische distributiegroepen en beveiligingsgroepen. Een DLP-beleid mag niet meer dan 50 van dergelijke insluitsels en uitsluitingen bevatten.

Als u ervoor kiest om specifieke SharePoint sites op te nemen of uit te sluiten, mag een DLP-beleid niet meer dan 100 van dergelijke insluitsels en uitsluitingen bevatten. Hoewel deze limiet bestaat, kunt u deze limiet overschrijden door een organisatiebreed beleid of een beleid toe te passen dat van toepassing is op hele locaties.

Als u ervoor kiest om specifieke OneDrive accounts of groepen op te nemen of uit te sluiten, mag een DLP-beleid niet meer dan 100 gebruikersaccounts of 50 groepen bevatten als opname of uitsluiting.

> [!NOTE]
> OneDrive voor het zoeken naar bedrijfsbeleid met behulp van accounts of groepen is in de openbare preview-versie. Tijdens deze fase kunt u gebruikersaccounts en groepen opnemen of uitsluiten als onderdeel van een DLP-beleid. Zowel inclusie als uitsluiting als onderdeel van hetzelfde beleid wordt niet ondersteund.
  
### <a name="rules"></a>Regels

> [!NOTE]
> Het standaardgedrag van een DLP-beleid, wanneer er geen waarschuwing is geconfigureerd, is niet te waarschuwen of te activeren. Dit geldt alleen voor standaardinformatietypen. Voor aangepaste informatietypen wordt het systeem gewaarschuwd, zelfs als er geen actie is gedefinieerd in het beleid.

Regels zijn de vereisten van uw bedrijf op de inhoud van uw organisatie. Een beleid bevat een of meer regels en elke regel bestaat uit voorwaarden en acties. Voor elke regel, wanneer aan de voorwaarden is voldaan, worden de acties automatisch uitgevoerd. Regels worden opeenvolgend uitgevoerd, te beginnen met de regel met de hoogste prioriteit in elk beleid.
  
Een regel biedt ook opties om gebruikers (met beleidstips en e-mailmeldingen) en beheerders (met e-mailincidentrapporten) te informeren dat de inhoud overeenkomt met de regel.
  
Hier zijn de componenten van een regel, elk hieronder uitgelegd.
  
![Secties van de DLP-regeleditor](../media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a>Voorwaarden

Voorwaarden zijn belangrijk omdat ze bepalen welke soorten informatie u zoekt en wanneer u actie moet ondernemen. U kunt er bijvoorbeeld voor kiezen om inhoud met paspoortnummers te negeren, tenzij de inhoud meer dan 10 van dergelijke nummers bevat en wordt gedeeld met mensen buiten uw organisatie.
  
Voorwaarden zijn gericht op de **inhoud,** zoals welke typen gevoelige informatie u zoekt, en ook op de **context,** zoals met wie het document wordt gedeeld. U kunt voorwaarden gebruiken om verschillende acties toe te wijzen aan verschillende risiconiveaus. Gevoelige inhoud die intern wordt gedeeld, kan bijvoorbeeld een lager risico vormen en vereist minder acties dan gevoelige inhoud die wordt gedeeld met mensen buiten de organisatie. 
  
![Lijst met beschikbare DLP-voorwaarden](../media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
De voorwaarden die nu beschikbaar zijn, kunnen bepalen of:
  
- Inhoud bevat een type gevoelige informatie.
    
- Inhoud bevat een label. Zie de onderstaande sectie [Een bewaarlabel gebruiken als voorwaarde in een DLP-beleid](#using-a-retention-label-as-a-condition-in-a-dlp-policy)voor meer informatie.
    
- Inhoud wordt gedeeld met mensen buiten of binnen uw organisatie.

  > [!NOTE]
  > Gebruikers die niet-gastaccounts hebben in active directory of Azure Active Directory tenant van een hostorganisatie, worden beschouwd als personen binnen de organisatie.
    
#### <a name="types-of-sensitive-information"></a>Soorten gevoelige informatie

Met een DLP-beleid wordt gevoelige informatie beschermd, die is gedefinieerd als een **type gevoelige informatie**. Microsoft 365 bevat definities voor veel veelvoorkomende typen gevoelige informatie in veel verschillende regio's die klaar zijn voor gebruik, zoals een creditcardnummer, bankrekeningnummers, nationale ID-nummers en paspoortnummers. 
  
![Lijst met beschikbare typen gevoelige informatie](../media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
Wanneer een DLP-beleid zoekt naar een gevoelig informatietype, zoals een creditcardnummer, wordt niet alleen gezocht naar een 16-cijferig nummer. Elk gevoelig informatietype wordt gedefinieerd en gedetecteerd met behulp van een combinatie van:
  
- Zoekwoorden.
    
- Interne functies om controlesommen of samenstelling te valideren.
    
- Evaluatie van reguliere expressies om patroonmatches te vinden.
    
- Ander inhoudsonderzoek.
    
Dit helpt DLP-detectie een hoge mate van nauwkeurigheid te bereiken en tegelijkertijd het aantal valse positieven te verminderen dat het werk van mensen kan onderbreken.
  
#### <a name="actions"></a>Acties

Wanneer inhoud overeenkomt met een voorwaarde in een regel, kunt u acties toepassen om de inhoud automatisch te beveiligen.
  
![Lijst met beschikbare DLP-acties](../media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
Met de acties die nu beschikbaar zijn, kunt u:
  
- **De toegang tot de inhoud beperken** Afhankelijk van uw behoefte kunt u de toegang tot inhoud op drie manieren beperken:

  1. Beperk de toegang tot inhoud voor iedereen.
  2. Beperk de toegang tot inhoud voor mensen buiten de organisatie.
  3. Beperk de toegang tot 'Iedereen met de link'.

  Voor site-inhoud betekent dit dat machtigingen voor het document beperkt zijn voor iedereen, behalve de beheerder van de primaire siteverzameling, de eigenaar van het document en de persoon die het document voor het laatst heeft gewijzigd. Deze personen kunnen de gevoelige informatie uit het document verwijderen of andere corrigerende maatregelen nemen. Wanneer het document voldoet, worden de oorspronkelijke machtigingen automatisch hersteld. Wanneer de toegang tot een document wordt geblokkeerd, wordt het document weergegeven met een speciaal beleidstippictogram in de bibliotheek op de site. 
    
  ![Beleidstip met toegang tot document is geblokkeerd](../media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
  Voor e-mailinhoud blokkeert deze actie dat het bericht wordt verzonden. Afhankelijk van hoe de DLP-regel is geconfigureerd, ziet de afzender een NDR of (als de regel een melding gebruikt) een beleidstip en/of e-mailmelding.
    
  ![Waarschuwing dat onbevoegde geadresseerden uit het bericht moeten worden verwijderd](../media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a>Gebruikersmeldingen en gebruikersoverschrijvingen

U kunt meldingen en overschrijvingen gebruiken om uw gebruikers te informeren over DLP-beleid en hen te helpen compliant te blijven zonder hun werk te blokkeren. Als een gebruiker bijvoorbeeld probeert een document met gevoelige informatie te delen, kan een DLP-beleid hen zowel een e-mailmelding sturen als een beleidstip weergeven in de context van de documentbibliotheek waarmee ze het beleid kunnen overschrijven als ze een zakelijke rechtvaardiging hebben.
  
![Gebruikersmeldingen en gebruikersoverschrijvingen secties van DLP-regeleditor](../media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
De e-mail kan de persoon op de hoogte stellen die de inhoud heeft verzonden, gedeeld of voor het laatst heeft gewijzigd en, voor site-inhoud, de beheerder en documenteigenaar van de primaire siteverzameling. Bovendien kunt u toevoegen of verwijderen wie u maar wilt uit de e-mailmelding.
  
Naast het verzenden van een e-mailmelding, wordt in een gebruikersmelding een beleidstip weergegeven:
  
- In Outlook en Outlook op het web.
    
- Voor het document op een SharePoint Online of OneDrive voor Bedrijven site.
    
- In Excel, PowerPoint en Word wanneer het document wordt opgeslagen op een site die is opgenomen in een DLP-beleid.
    
In de e-mailmelding en beleidstip wordt uitgelegd waarom inhoud conflicteert met een DLP-beleid. Als u dit wilt, kunnen gebruikers met de e-mailmelding en beleidstip een regel overschrijven door een vals positief te melden of een zakelijke rechtvaardiging te geven. Dit kan u helpen gebruikers te informeren over uw DLP-beleid en ze af te dwingen zonder te voorkomen dat mensen hun werk doen. Informatie over overschrijvingen en valse positieven wordt ook geregistreerd voor rapportage (zie hieronder over de DLP-rapporten) en opgenomen in de incidentrapporten (volgende sectie), zodat de compliance officer deze informatie regelmatig kan controleren.
  
Zo ziet een beleidstip eruit in een OneDrive voor Bedrijven account.
  
![Beleidstip voor een document in een OneDrive account](../media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)

 Zie Meldingen en beleidstips gebruiken voor meer informatie over [gebruikersmeldingen en beleidstips in DLP-beleid.](use-notifications-and-policy-tips.md)

#### <a name="alerts-and-incident-reports"></a>Meldingen en incidentrapporten

Wanneer een regel is afgestemd, kunt u een waarschuwingsmail sturen naar uw compliance officer (of een persoon(en) die u kiest) met details van de waarschuwing. Deze waarschuwingsmail bevat een koppeling van het [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md) waarmee de compliance officer de details van waarschuwingen en gebeurtenissen kan bekijken. Het dashboard bevat details van de gebeurtenis die de waarschuwing heeft geactiveerd, samen met details van het DLP-beleid dat overeenkomt en de gedetecteerde gevoelige inhoud.

Daarnaast kunt u ook een incidentmelding sturen met details van de gebeurtenis. Dit rapport bevat informatie over het item dat is overeenkomend, de werkelijke inhoud die overeenkomt met de regel en de naam van de persoon die de inhoud voor het laatst heeft gewijzigd. Voor e-mailberichten bevat het rapport ook als bijlage het oorspronkelijke bericht dat overeenkomt met een DLP-beleid.

> [!div class="mx-imgBorder"]
> ![Pagina voor het configureren van incidentrapporten](../media/Alerts-and-incident-report.png)

DLP scant e-mail anders dan items in SharePoint Online of OneDrive voor Bedrijven. In SharePoint Online en OneDrive voor Bedrijven scant DLP zowel bestaande als nieuwe items en genereert een waarschuwings- en incidentrapport wanneer een overeenkomst wordt gevonden. In Exchange Online scant DLP alleen nieuwe e-mailberichten en genereert een rapport als er een beleids overeenkomst is. DLP ***scant*** of komt niet overeen met eerder bestaande e-mailitems die zijn opgeslagen in een postvak of archief.
  
## <a name="grouping-and-logical-operators"></a>Groepering en logische operatoren

Vaak heeft uw DLP-beleid een eenvoudige vereiste, zoals het identificeren van alle inhoud die een Amerikaans burgerservicenummer bevat. In andere scenario's moet uw DLP-beleid echter mogelijk meer los gedefinieerde gegevens identificeren.
  
Als u bijvoorbeeld inhoud wilt identificeren die onder de Amerikaanse Health Insurance Act (HIPAA) vallen, moet u zoeken naar:
  
- Inhoud die specifieke soorten gevoelige informatie bevat, zoals een Amerikaans burgerservicenummer of een DEA-nummer (Drug Enforcement Agency).
    
    en
    
- Inhoud die moeilijker te identificeren is, zoals communicatie over de zorg van een patiënt of beschrijvingen van medische diensten die worden aangeboden. Om deze inhoud te identificeren, moeten trefwoorden uit zeer grote trefwoordenlijsten worden gematcht, zoals de International Classification of Diseases (ICD-9-CM of ICD-10-CM).
    
U kunt dergelijke los gedefinieerde gegevens eenvoudig identificeren met behulp van groeperings- en logische operatoren (AND, OR). Wanneer u een DLP-beleid maakt, kunt u het aantal:
  
- Typen gevoelige informatie groeperen.
    
- Kies de logische operator tussen de gevoelige informatietypen binnen een groep en tussen de groepen zelf.
    
### <a name="choosing-the-operator-within-a-group"></a>De operator binnen een groep kiezen

Binnen een groep kunt u kiezen of aan een of alle voorwaarden in die groep moet worden voldaan om de inhoud aan de regel te laten voldoen.
  
![Groep met de operatoren binnen de groep](../media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a>Een groep toevoegen

U kunt snel een groep toevoegen, die zijn eigen voorwaarden en operator binnen die groep kan hebben.
  
![Knop Groep toevoegen](../media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a>De operator kiezen tussen groepen

Tussen groepen kunt u kiezen of aan de voorwaarden in slechts één groep of aan alle groepen moet worden voldaan om de inhoud aan de regel te laten voldoen.
  
Het ingebouwde **AMERIKAANSE HIPAA-beleid** heeft bijvoorbeeld een regel die een **AND-operator** tussen de groepen gebruikt, zodat deze inhoud identificeert die het volgende bevat: 
  
- van de **pii-id's** van de groep (ten minste één SSN-nummer **of** DEA-nummer) 
    
    **en**
    
- uit de groep **Medische Termen** (ten minste één ICD-9-CM trefwoord **OF** ICD-10-CM trefwoord) 
    
![Groepen die de operator tussen groepen weergeven](../media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a>De prioriteit waarmee regels worden verwerkt

Wanneer u regels in een beleid maakt, krijgt aan elke regel een prioriteit toegewezen in de volgorde waarin deze is gemaakt, wat betekent dat de regel die als eerste is gemaakt, de eerste prioriteit heeft, de regel die als tweede is gemaakt, de tweede prioriteit, enzovoort.

> [!div class="mx-imgBorder"]
> ![Regels in prioriteitsvolgorde](../media/dlp-rules-in-priority-order.png)
  
Nadat u meer dan één DLP-beleid hebt ingesteld, kunt u de prioriteit van een of meer beleidsregels wijzigen. Selecteer hiervoor een beleid, kies **Beleid bewerken** en gebruik de lijst **Prioriteit** om de prioriteit op te geven.

> [!div class="mx-imgBorder"]
> ![Prioriteit instellen voor een beleid](../media/dlp-set-policy-priority.png)

Wanneer inhoud wordt geëvalueerd aan de hand van regels, worden de regels in prioriteitsvolgorde verwerkt. Als inhoud overeenkomt met meerdere regels, worden de regels in prioriteitsvolgorde verwerkt en wordt de meest beperkende actie afgedwongen. Als inhoud bijvoorbeeld overeenkomt met alle volgende regels, wordt regel 3 afgedwongen omdat dit de hoogste prioriteit heeft, de meest beperkende regel:
  
- Regel 1: informeert gebruikers alleen
    
- Regel 2: waarschuwt gebruikers, beperkt de toegang en staat gebruikersoverschrijvingen toe
    
- Regel 3: waarschuwt gebruikers, beperkt de toegang en staat gebruikersoverschrijvingen niet toe
    
- Regel 4: informeert gebruikers alleen
    
- Regel 5: beperkt de toegang
    
- Regel 6: waarschuwt gebruikers, beperkt de toegang en staat gebruikersoverschrijvingen niet toe
    
Houd er in dit voorbeeld rekening mee dat overeenkomsten voor alle regels worden vastgelegd in de controlelogboeken en worden weergegeven in de DLP-rapporten, ook al wordt alleen de meest beperkende regel afgedwongen.
  
Wat betreft beleidstips, merk op dat:
  
- Alleen de beleidstip van de hoogste prioriteit, de meest beperkende regel wordt weergegeven. Een beleidstip van een regel die de toegang tot inhoud blokkeert, wordt bijvoorbeeld weergegeven via een beleidstip van een regel die alleen een melding verzendt. Dit voorkomt dat mensen een cascade van beleidstips zien.
    
- Als met de beleidstips in de meest beperkende regel mensen de regel kunnen overschrijven, worden bij het overschrijven van deze regel ook alle andere regels overschreven die overeenkomen met de inhoud.
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a>Tuningregels om ze gemakkelijker of moeilijker te matchen

Nadat mensen hun DLP-beleid hebben gemaakt en ingeschakeld, komen ze soms deze problemen tegen:
  
- Te veel inhoud die geen gevoelige informatie **is,** komt overeen met de regels, met andere woorden, te veel valse positieven. 
    
- Te weinig inhoud die gevoelige informatie **is,** komt overeen met de regels. Met andere woorden, de beschermende acties worden niet afgedwongen op de gevoelige informatie. 
    
Om deze problemen aan te pakken, kunt u uw regels afstemmen door het aantal exemplaren aan te passen en de nauwkeurigheid van de overeenkomst aan te passen, waardoor het voor inhoud moeilijker of gemakkelijker wordt om aan de regels te voldoen. Elk gevoelig informatietype dat in een regel wordt gebruikt, heeft zowel een aantal exemplaren als een overeenkomstnauwkeurigheid.
  
### <a name="instance-count"></a>Aantal instanties

Aantal exemplaren betekent simpelweg hoeveel exemplaren van een specifiek type gevoelige informatie aanwezig moeten zijn om inhoud aan te passen aan de regel. Inhoud komt bijvoorbeeld overeen met de onderstaande regel als deze zich tussen 1 en 9 unieke Amerikaanse of Britse regels voordeed. paspoortnummers worden geïdentificeerd.

> [!NOTE]
> Het aantal exemplaren bevat alleen **unieke** overeenkomsten voor gevoelige informatietypen en trefwoorden. Als een e-mail bijvoorbeeld 10 exemplaren van hetzelfde creditcardnummer bevat, tellen deze 10 exemplaren als één exemplaar van een creditcardnummer.
  
Als u het aantal exemplaren wilt gebruiken om regels af te stemmen, is de begeleiding eenvoudig:
  
- Om de regel gemakkelijker te matchen, verlaagt u het **aantal minuten** en/of verhoogt u het **maximum** aantal. U kunt ook **het maximum** instellen op **elke** door de numerieke waarde te verwijderen. 
    
- Om de regel moeilijker te matchen, verhoogt u het **aantal minuten.** 
    
Meestal gebruikt u minder beperkende acties, zoals het verzenden van gebruikersmeldingen, in een regel met een lager aantal exemplaren (bijvoorbeeld 1-9). En u gebruikt meer beperkende acties, zoals het beperken van de toegang tot inhoud zonder gebruikersoverschrijvingen toe te staan, in een regel met een hoger aantal exemplaren (bijvoorbeeld 10-any).
  
![Instantietellingen in de regeleditor](../media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a>Match nauwkeurigheid

Zoals hierboven beschreven, wordt een gevoelig informatietype gedefinieerd en gedetecteerd met behulp van een combinatie van verschillende soorten bewijsmateriaal. Gewoonlijk wordt een gevoelig informatietype gedefinieerd door meerdere van dergelijke combinaties, patronen genoemd. Een patroon dat minder bewijs vereist, heeft een lagere overeenkomstnauwkeurigheid (of betrouwbaarheidsniveau), terwijl een patroon dat meer bewijs vereist, een hogere overeenkomstnauwkeurigheid (of betrouwbaarheidsniveau) heeft. Zie Entiteitsdefinities voor gevoelige informatietype voor meer informatie over de werkelijke patronen en [betrouwbaarheidsniveaus die](sensitive-information-type-entity-definitions.md)door elk type gevoelige informatie worden gebruikt.
  
Het gevoelige informatietype met de naam Creditcardnummer wordt bijvoorbeeld gedefinieerd door twee patronen:
  
- Een patroon met 65% vertrouwen dat vereist:
    
  - Een nummer in de notatie van een creditcardnummer.
    
  - Een nummer dat de controlesom passeert.
    
- Een patroon met 85% vertrouwen dat vereist:
    
  - Een nummer in de notatie van een creditcardnummer.
    
  - Een nummer dat de controlesom passeert.
    
  - Een trefwoord of een vervaldatum in de juiste indeling.
    
U kunt deze betrouwbaarheidsniveaus (of overeenkomstnauwkeurigheid) gebruiken in uw regels. Meestal gebruikt u minder beperkende acties, zoals het verzenden van gebruikersmeldingen, in een regel met een lagere overeenkomstnauwkeurigheid. En u gebruikt meer beperkende acties, zoals het beperken van de toegang tot inhoud zonder gebruikersoverschrijvingen toe te staan, in een regel met een hogere overeenkomstnauwkeurigheid.
  
Het is belangrijk om te begrijpen dat wanneer een specifiek type gevoelige informatie, zoals een creditcardnummer, inhoudelijk wordt geïdentificeerd, slechts één betrouwbaarheidsniveau wordt geretourneerd:
  
- Als alle overeenkomsten voor één patroon zijn, wordt het betrouwbaarheidsniveau voor dat patroon geretourneerd.
    
- Als er overeenkomsten zijn voor meer dan één patroon (dat wil gezegd, er zijn overeenkomsten met twee verschillende vertrouwensniveaus), wordt een betrouwbaarheidsniveau geretourneerd dat hoger is dan een van de afzonderlijke patronen alleen. Dit is het lastige deel. Als bijvoorbeeld voor een creditcard zowel de patronen van 65% als die van 85% overeenkomen, is het betrouwbaarheidsniveau dat wordt geretourneerd voor dat gevoelige informatietype groter dan 90%, omdat meer bewijs meer vertrouwen betekent.
    
Dus als u twee wederzijds exclusieve regels voor creditcards wilt maken, één voor de 65% overeenkomstnauwkeurigheid en één voor de 85% matchnauwkeurigheid, zouden de bereiken voor matchnauwkeurigheid er als volgt uitzien. De eerste regel pikt alleen overeenkomsten op van het 65%-patroon. De tweede regel pikt wedstrijden op met **ten minste één** match van 85% en kan mogelijk andere wedstrijden met een lager vertrouwen **hebben.** 
  
![Twee regels met verschillende bereiken voor wedstrijdnauwkeurigheid](../media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
Om deze redenen zijn de richtlijnen voor het maken van regels met verschillende overeenkomstnauwkeurigheden:
  
- Het laagste betrouwbaarheidsniveau gebruikt meestal dezelfde waarde voor **min** en **max** (geen bereik). 
    
- Het hoogste betrouwbaarheidsniveau is meestal een bereik van net boven het lagere betrouwbaarheidsniveau tot 100.
    
- Alle tussenvertrouwensniveaus variëren meestal van net boven het lagere betrouwbaarheidsniveau tot net onder het hogere betrouwbaarheidsniveau.
    
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>Een retentielabel gebruiken als voorwaarde in een DLP-beleid

Wanneer u een eerder gemaakt en gepubliceerd [bewaarlabel](retention.md#retention-labels) gebruikt als voorwaarde in een DLP-beleid, zijn er enkele dingen waar u op moet letten:

- Het bewaarlabel moet worden gemaakt en gepubliceerd voordat u het probeert te gebruiken als voorwaarde in een DLP-beleid.
- Het synchroniseren van gepubliceerde bewaarlabels kan één tot zeven dagen duren. Zie [Wanneer bewaarlabels beschikbaar komen voor het aanvragen van bewaarlabels](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply) die zijn gepubliceerd in een bewaarbeleid, en [Hoe lang het duurt voordat bewaarlabels van kracht worden](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect) voor bewaarlabels die automatisch worden gepubliceerd, voor meer informatie.
- Het gebruik van een bewaarlabel in een beleid ** wordt alleen ondersteund voor items in SharePoint en OneDrive***.

  ![Labels als voorwaarde](../media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

  U kunt een bewaarlabel gebruiken in een DLP-beleid als u items hebt die onder retentie en dispositie staan, en u wilt er ook andere besturingselementen op toepassen, bijvoorbeeld:

  - U hebt een bewaarlabel met de naam **belastingjaar 2018** gepubliceerd, dat, wanneer toegepast op belastingdocumenten uit 2018 die zijn opgeslagen in SharePoint ze 10 jaar bewaart en vervolgens vervreemdt. U wilt ook niet dat deze items buiten uw organisatie worden gedeeld, wat u kunt doen met een DLP-beleid.

  > [!IMPORTANT]
  > U krijgt deze fout als u een bewaarlabel opgeeft als voorwaarde in een DLP-beleid en u ook Exchange en/of Teams als locatie opneemt: **'Het beveiligen van gelabelde inhoud in e-mail- en teamberichten wordt niet ondersteund. Verwijder het onderstaande label of schakel Exchange en Teams uit als locatie."** Dit komt omdat Exchange transport de metagegevens van het label niet evalueert tijdens het verzenden en bezorgen van berichten. 

### <a name="using-a-sensitivity-label-as-a-condition-in-a-dlp-policy"></a>Een gevoeligheidslabel gebruiken als voorwaarde in een DLP-beleid

[Meer informatie](./dlp-sensitivity-label-as-condition.md) over het gebruik van het gevoeligheids label als voorwaarde in DLP-beleid.
  
### <a name="how-this-feature-relates-to-other-features"></a>Hoe deze functie zich verhoudt tot andere functies

Verschillende functies kunnen worden toegepast op inhoud die gevoelige informatie bevat:
  
- Een [bewaarlabel en een bewaarbeleid](retention.md) kunnen beide **bewaaracties afdwingen** voor deze inhoud. 
    
- Een DLP-beleid kan **beveiligingsacties** voor deze inhoud afdwingen. En voordat u deze acties afdwingt, kan een DLP-beleid vereisen dat aan andere voorwaarden wordt voldaan naast de inhoud die een label bevat. 
    
![Diagram met functies die van toepassing kunnen zijn op gevoelige informatie](../media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
Houd er rekening mee dat een DLP-beleid een rijkere detectie mogelijkheid heeft dan een label of bewaar beleid dat wordt toegepast op gevoelige informatie. Een DLP-beleid kan beschermende acties afdwingen voor inhoud die gevoelige informatie bevat, en als de gevoelige informatie uit de inhoud wordt verwijderd, worden deze beschermende acties ongedaan gemaakt de volgende keer dat de inhoud wordt gescand. Maar als een bewaarbeleid of -label wordt toegepast op inhoud die gevoelige informatie bevat, is dat een eenmalige actie die niet ongedaan wordt gemaakt, zelfs niet als de gevoelige informatie wordt verwijderd.
  
Door een label als voorwaarde te gebruiken in een DLP-beleid, kunt u zowel bewaar- als beveiligingsacties afdwingen op inhoud met dat label. U kunt denken aan inhoud die een label bevat dat precies lijkt op inhoud die gevoelige informatie bevat - zowel een label als een gevoelig informatietype zijn eigenschappen die worden gebruikt om inhoud te classificeren, zodat u acties op die inhoud kunt afdwingen.
  
![Diagram van DLP-beleid met label als voorwaarde](../media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a>Eenvoudige instellingen versus geavanceerde instellingen

Wanneer u een DLP-beleid maakt, kunt u kiezen tussen eenvoudige of geavanceerde instellingen:
  
- **Eenvoudige instellingen** maken het eenvoudig om het meest voorkomende type DLP-beleid te maken zonder de regeleditor te gebruiken om regels te maken of te wijzigen. 
    
- **Geavanceerde instellingen** gebruiken de regeleditor om u volledige controle te geven over elke instelling voor uw DLP-beleid. 
    
Maak je geen zorgen, onder de covers werken eenvoudige instellingen en geavanceerde instellingen precies hetzelfde, door regels af te dwingen die bestaan uit voorwaarden en acties - alleen met eenvoudige instellingen zie je de regeleditor niet. Het is een snelle manier om een DLP-beleid te maken.
  
### <a name="simple-settings"></a>Eenvoudige instellingen

Verreweg het meest voorkomende DLP-scenario is het maken van een beleid om te voorkomen dat inhoud met gevoelige informatie wordt gedeeld met mensen buiten uw organisatie, en het uitvoeren van een automatische herstelactie, zoals het beperken van wie toegang heeft tot de inhoud, het verzenden van meldingen van eindgebruikers of beheerders en het controleren van de gebeurtenis voor later onderzoek. Mensen gebruiken DLP om onbedoelde openbaarmaking van gevoelige informatie te voorkomen.
  
Als u dit doel wilt vereenvoudigen, kunt u bij het maken van een DLP-beleid **eenvoudige instellingen** gebruiken kiezen. Deze instellingen bieden alles wat u nodig hebt om het meest voorkomende DLP-beleid te implementeren, zonder dat u naar de regeleditor hoeft te gaan.
  
![DLP-opties voor eenvoudige en geavanceerde instellingen](../media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a>Geavanceerde instellingen

Als u meer aangepast DLP-beleid wilt maken, kunt u **Geavanceerde instellingen gebruiken** kiezen.
  
De geavanceerde instellingen bieden u de regeleditor, waar u volledige controle hebt over elke mogelijke optie, inclusief het aantal exemplaren en de nauwkeurigheid van de overeenkomst (betrouwbaarheidsniveau) voor elke regel.
  
Als u snel naar een sectie wilt gaan, klikt u op een item in de bovenste navigatie van de regeleditor om naar die sectie hieronder te gaan.
  
![Bovenste navigatiemenu van DLP-regeleditor](../media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a>DLP-beleidssjablonen

De eerste stap bij het maken van een DLP-beleid is het kiezen van welke informatie moet worden beschermd. Door te beginnen met een DLP-sjabloon, slaat u het werk op van het helemaal opnieuw bouwen van een nieuwe set regels en het uitzoeken welke soorten informatie standaard moeten worden opgenomen. U kunt deze vereisten vervolgens toevoegen of wijzigen om de regel af te stemmen op de specifieke vereisten van uw organisatie.
  
Een vooraf geconfigureerde DLP-beleidssjabloon kan u helpen specifieke soorten gevoelige informatie te detecteren, zoals HIPAA-gegevens, PCI-DSS-gegevens, Gramm-Leach-Bliley Act-gegevens of zelfs landespecifieke persoonlijk identificeerbare informatie (P.I.). Om het u gemakkelijk te maken om veelvoorkomende typen gevoelige informatie te vinden en te beschermen, bevatten de beleidssjablonen in Microsoft 365 al de meest voorkomende typen gevoelige informatie die nodig zijn om aan de slag te gaan.
  
![Lijst met sjablonen voor beleid ter voorkoming van gegevensverlies met de focus op sjabloon voor de Amerikaanse Patriot Act](../media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
Uw organisatie kan ook zijn eigen specifieke vereisten hebben, in welk geval u een DLP-beleid helemaal opnieuw kunt maken door de optie **Aangepast beleid te** kiezen. Een aangepast beleid is leeg en bevat geen vooraf gemaakte regels. 
  
<!-- ## Roll out DLP policies gradually with test mode

rehomed to Plan for DLP

When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.
  
If you're creating DLP policies with a large potential impact, we recommend following this sequence:
  
1. **Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization. 
    
2. **Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules. 
    
3. **Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend. 

    ![Options for using test mode and turning on policy](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    You can turn off a DLP policy at any time, which affects all rules in the policy. However, each rule can also be turned off individually by toggling its status in the rule editor.

    ![Options for turning off a rule in a policy](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    You can also change the priority of multiple rules in a policy. To do that, open a policy for editing. In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.

    > [!div class="mx-imgBorder"]
    > ![Set rule priority](../media/dlp-set-rule-priority.png)-->
  
## <a name="dlp-reports"></a>DLP-rapporten

Nadat u uw DLP-beleid hebt gemaakt en ingeschakeld, wilt u controleren of ze werken zoals u hebt bedoeld en u helpen compliant te blijven. Met DLP-rapporten kunt u snel het aantal DLP-beleids- en regelovereenkomsten in de loop van de tijd bekijken, en het aantal valse positieven en overschrijvingen. Voor elk rapport kunt u deze overeenkomsten filteren op locatie, tijdsbestek en zelfs beperken tot een specifiek beleid, regel of actie.
  
Met de DLP-rapporten kunt u zakelijke inzichten krijgen en:
  
- Focus op specifieke tijdsperiodes en begrijp de redenen voor pieken en trends.
    
- Ontdek bedrijfsprocessen die in strijd zijn met het nalevingsbeleid van uw organisatie.
    
- Begrijp de zakelijke impact van het DLP-beleid.
    
Daarnaast kunt u de DLP-rapporten gebruiken om uw DLP-beleid te verfijnen terwijl u ze uitvoert.
  
![Rapportendashboard in beveiligings- en compliancecentrum](../media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a>Hoe DLP-beleid werkt

DLP detecteert gevoelige informatie met behulp van diepgaande inhoudsanalyse (niet alleen een eenvoudige tekstscan). Deze analyse van diepe inhoud maakt gebruik van trefwoordovereenkomsten, woordenboekovereenkomsten, de evaluatie van reguliere expressies, interne functies en andere methoden om inhoud te detecteren die overeenkomt met uw DLP-beleid. Mogelijk wordt slechts een klein percentage van uw gegevens als gevoelig beschouwd. Een DLP-beleid kan alleen die gegevens identificeren, bewaken en automatisch beschermen, zonder mensen te belemmeren of te beïnvloeden die met de rest van uw inhoud werken.
  
### <a name="policies-are-synced"></a>Beleid wordt gesynchroniseerd

Nadat u een DLP-beleid hebt gemaakt in het Security &amp; Compliance Center, wordt het opgeslagen in een centraal beleids archief en vervolgens gesynchroniseerd met de verschillende inhouds bronnen, waaronder:
  
- Exchange Online, en van daaruit naar Outlook op het web en Outlook.
    
- OneDrive voor Bedrijven sites.
    
- SharePoint Online sites.
    
- Office bureaubladprogramma's (Excel, PowerPoint en Word).

- Microsoft Teams kanalen en chatberichten.
    
Nadat het beleid is gesynchroniseerd met de juiste locaties, wordt de inhoud geëvalueerd en acties afgedwongen.
<!-- what is the time delay for first deployment of a policy and what is the sync schedule? -->
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a>Beleidsevaluatie in OneDrive voor Bedrijven en SharePoint Online sites

Op al uw SharePoint online sites en OneDrive voor Bedrijven sites veranderen documenten voortdurend - ze worden voortdurend gemaakt, bewerkt, gedeeld, enzovoort. Dit betekent dat documenten op elk gewenst moment conflicteren of compatibel worden met een DLP-beleid. Een persoon kan bijvoorbeeld een document uploaden dat geen gevoelige informatie bevat naar zijn teamsite, maar later kan een andere persoon hetzelfde document bewerken en er gevoelige informatie aan toevoegen.
  
Daarom controleren DLP-beleidsdocumenten regelmatig op beleidsovereenkomsten op de achtergrond. U kunt dit zien als asynchrone beleidsevaluatie.
<!-- what is the frequency? looks like it is tied to the search crawl schedule -->
  
#### <a name="how-it-works"></a>Hoe het werkt
 
Wanneer mensen documenten toevoegen of wijzigen op hun sites, scant de zoekmachine de inhoud, zodat u er later naar kunt zoeken. Terwijl dit gebeurt, wordt de inhoud ook gescand op gevoelige informatie en om te controleren of deze wordt gedeeld. Alle gevoelige informatie die wordt gevonden, wordt veilig opgeslagen in de zoekindex, zodat alleen het nalevingsteam er toegang toe heeft, maar geen typische gebruikers. Elk DLP-beleid dat u hebt ingeschakeld, wordt op de achtergrond uitgevoerd (asynchroon), controleert regelmatig zoekopdrachten naar inhoud die overeenkomt met een beleid en past acties toe om het te beschermen tegen onbedoelde lekken.
  
![Diagram met de manier waarop DLP-beleid inhoud asynchroon evalueert](../media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<!-- conflict with a DLP policy is bad wording -->
Ten slotte kunnen documenten conflicteren met een DLP-beleid, maar ze kunnen ook compatibel worden met een DLP-beleid. Als een persoon bijvoorbeeld creditcardnummers aan een document toevoegt, kan dit ertoe leiden dat een DLP-beleid de toegang tot het document automatisch blokkeert. Maar als de persoon later de gevoelige informatie verwijdert, wordt de actie (in dit geval blokkeren) automatisch ongedaan gemaakt de volgende keer dat het document wordt geëvalueerd aan de hand van het beleid.
  
DLP evalueert alle inhoud die kan worden geïndexeerd. Zie [Standaard verkende bestandsextensies en geparseerde bestandstypen in SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)voor meer informatie over welke bestandstypen standaard worden gecrawld.

> [!NOTE]
> Om te voorkomen dat documenten worden gedeeld voordat DLP-beleid de mogelijkheid had om ze te analyseren, kan het delen van nieuwe bestanden in SharePoint worden geblokkeerd totdat de inhoud ervan is geïndexeerd. Zie [nieuwe bestanden standaard als gevoelig markeren](/sharepoint/sensitive-by-default) voor gedetailleerde informatie. 
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a>Beleidsevaluatie in Exchange Online, Outlook en Outlook op het web

Wanneer u een DLP-beleid maakt dat Exchange Online als locatie bevat, wordt het beleid gesynchroniseerd van het Office 365 Security &amp; Compliance Center naar Exchange Online en vervolgens van Exchange Online naar Outlook op het web en Outlook.
  
Wanneer een bericht wordt samengesteld in Outlook, kan de gebruiker beleidstips zien wanneer de inhoud die wordt gemaakt, wordt geëvalueerd aan de hand van DLP-beleid. En nadat een bericht is verzonden, wordt het geëvalueerd aan de hand van DLP-beleid als een normaal onderdeel van de e-mail stroom, samen met Exchange e-mail stroom regels (ook wel transport regels) en DLP-beleid gemaakt in het Exchange beheer center. DLP-beleid scant zowel het bericht als eventuele bijlagen.
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a>Beleidsevaluatie in de Office desktopprogramma's

<!-- same capability to identify sensitive information line conflates sensitive information types and such -->
Excel, PowerPoint en Word bevatten dezelfde mogelijkheid om gevoelige informatie te identificeren en DLP-beleid toe te passen als SharePoint online en OneDrive voor Bedrijven. Deze Office programma's hun DLP-beleid rechtstreeks vanuit het centrale beleids archief synchroniseren en vervolgens de inhoud voortdurend evalueren ten opzichte van het DLP-beleid wanneer mensen werken met documenten die zijn geopend vanaf een site die is opgenomen in een DLP-beleid.
  
DLP-beleidsevaluatie in Office is ontworpen om geen invloed te hebben op de prestaties van de programma's of de productiviteit van mensen die aan inhoud werken. Als ze aan een groot document werken of als de computer van de gebruiker bezet is, kan het enkele seconden duren voordat een beleidstip wordt weergegeven.

### <a name="policy-evaluation-in-microsoft-teams"></a>Beleidsevaluatie in Microsoft Teams
 <!--what do you mean that it's synched to user accounts?  I thought DLP policies were applied to locations not users like sensitivity labels are  -->

Wanneer u een DLP-beleid maakt dat Microsoft Teams als locatie bevat, wordt het beleid gesynchroniseerd van het Office 365 Security &amp; Compliance Center naar gebruikersaccounts en Microsoft Teams kanalen en chatberichten. Afhankelijk van hoe DLP-beleid is geconfigureerd, kan het bericht worden geblokkeerd of ingetrokken wanneer iemand probeert gevoelige informatie te delen in een Microsoft Teams chat- of kanaalbericht. En documenten die gevoelige informatie bevatten en die worden gedeeld met gasten (externe gebruikers) worden niet geopend voor die gebruikers. Zie Preventie [van gegevensverlies en Microsoft Teams](dlp-microsoft-teams.md)voor meer informatie.
 
## <a name="permissions"></a>Machtigingen

Leden van uw nalevingsteam die DLP-beleid maken, hebben machtigingen nodig voor het Security &amp; Compliance Center. Uw Tenant beheerder heeft standaard toegang tot deze locatie en kan nalevings functionarissen en andere mensen toegang geven tot het Security &amp; Compliance Center, zonder hen alle machtigingen van een Tenant beheerder te geven. Om dit te doen, raden wij u aan:
  
1. Maak een groep in Microsoft 365 en voeg er nalevingsfunctionarissen aan toe.
    
2. Maak een rolgroep op de pagina **Machtigingen** van het Security &amp; Compliance Center. 

3. Gebruik tijdens het maken van de rolgroep de sectie **Rollen kiezen** om de volgende rol toe te voegen aan de rolgroep: **DLP Compliance Management**.
    
4. Gebruik de sectie **Leden kiezen** om de Microsoft 365 groep die u eerder hebt gemaakt, toe te voegen aan de rolgroep.

U kunt ook een rolgroep maken met alleen-weergeven bevoegdheden voor het DLP-beleid en DLP-rapporten door de rol **Alleen-weergeven DLP-nalevingsbeheer** toe te kennen.

Zie [Gebruikers toegang geven tot het Office 365 Compliance Center voor](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)meer informatie.
  
Deze machtigingen zijn alleen vereist om een DLP-beleid te maken en toe te passen. Voor beleidshandhaving is geen toegang tot de inhoud vereist.
  
## <a name="find-the-dlp-cmdlets"></a>Zoek de DLP cmdlets

Als u de meeste cmdlets voor het Security &amp; Compliance Center wilt gebruiken, moet u het als beste doen:
  
1. [Verbinding maken naar de Office 365 Beveiliging &amp; Compliance Center met behulp van externe PowerShell](/powershell/exchange/connect-to-scc-powershell).
    
2. Gebruik een van deze [beleids- en nalevings-dlp-cmdlets](/powershell/module/exchange/export-dlppolicycollection).
    
DLP-rapporten moeten echter gegevens uit Microsoft 365 halen, inclusief Exchange Online. Daarom zijn **de cmdlets voor de DLP-rapporten beschikbaar in Exchange Online Powershell - niet in &amp; Powershell van Security Compliance Center**. Als u de cmdlets voor de DLP-rapporten wilt gebruiken, moet u daarom het als u het eerst gebruiken:
  
1. [Maak verbinding met Exchange Online via externe PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
    
2. Gebruik een van deze cmdlets voor de DLP-rapporten:
    
    - [Get-DlpDetectionsRapport](/powershell/module/exchange/Get-DlpDetectionsReport)

    - [Get-DlpDetailRapport](/powershell/module/exchange/Get-DlpDetailReport)
    
## <a name="more-information"></a>Meer informatie

- [Een DLP-beleid maken vanuit een sjabloon](create-a-dlp-policy-from-a-template.md)
    
- [Meldingen verzenden en beleidstips voor DLP-beleid weergeven](use-notifications-and-policy-tips.md)
    
- [Een DLP-beleid maken om documenten te beveiligen met FCI of andere eigenschappen](protect-documents-that-have-fci-or-other-properties.md)
    
- [Wat zijn de DLP-beleidssjablonen?](what-the-dlp-policy-templates-include.md)
    
- [Definities van entiteiten van het type vertrouwelijke gegevens](sensitive-information-type-entity-definitions.md)
    
- [Doel van de DLP-functies](what-the-dlp-functions-look-for.md)
    
- [Een aangepast type gevoelige informatie maken](create-a-custom-sensitive-information-type.md)
