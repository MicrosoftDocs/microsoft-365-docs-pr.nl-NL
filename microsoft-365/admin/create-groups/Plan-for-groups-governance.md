---
title: Plan voor het bestuur van groepen
ms.reviewer: johasand
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BSA160
description: Meer informatie over het plannen van de governance van Microsoft 365-groepen.
ms.openlocfilehash: c37f88cbd3f41f22c1effdd7ba482033012aff01
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351837"
---
# <a name="plan-for-governance-in-groups"></a>Plan voor bestuur in groepen

Microsoft 365-groepen heeft een uitgebreide set tools om alle beheermogelijkheden te implementeren die uw organisatie nodig heeft. Dit artikel begeleidt IT-professionals om de juiste vragen te stellen om hun vereisten voor governance te bepalen en hoe ze hieraan te voldoen op basis van hun organisatieprofiel.

## <a name="why-microsoft-365-groups"></a>Waarom Microsoft 365-groepen?
![afbeelding desc](../../media/01.png)

We weten dat organisaties tegenwoordig een diverse toolset gebruiken. Er is het team van ontwikkelaars met behulp van team chat, de leidinggevenden verzenden van e-mail, en de hele organisatie verbinding via enterprise social. Er zijn meerdere samenwerkingstools in gebruik omdat elke groep uniek is en zijn eigen functionele behoeften en werkstijl heeft. Sommigen gebruiken alleen e-mail, terwijl anderen voornamelijk in de chat zullen leven. 

Als gebruikers het gevoel hebben dat de door IT geleverde tools niet aan hun behoeften voldoen, zullen ze waarschijnlijk hun favoriete consumentenapp downloaden die hun scenario's ondersteunt. Hoewel dit proces gebruikers in staat stelt om snel aan de slag te gaan, leidt dit tot een frustrerende gebruikerservaring in de hele organisatie met meerdere aanmeldingen, moeite met delen en geen enkele plaats om inhoud te bekijken. Dit concept wordt "Shadow IT" genoemd en vormt een aanzienlijk risico voor organisaties. Het vermindert de mogelijkheid om gebruikerstoegang uniform te beheren, beveiliging en servicecompliance-behoeften te garanderen.

Microsoft 365 Groups stelt gebruikers in staat en vermindert het risico op schaduw-IT door in één stap veel van de tools te bieden die nodig zijn om samen te werken. Met Microsoft 365-groepen u een groep mensen kiezen met wie u wilt samenwerken en eenvoudig een verzameling bronnen instellen die deze mensen kunnen delen. Het handmatig toewijzen van machtigingen aan resources behoort tot het verleden, omdat het toevoegen van leden aan de groep automatisch de benodigde machtigingen verleent aan alle assets die door de groep worden geleverd.

## <a name="technical-architecture"></a>Technische architectuur

Er zijn drie belangrijke communicatiemethoden die worden ondersteund door Microsoft 365-groepen. Groepen kunnen worden gemaakt binnen deze ervaringen en worden gebruikt in Microsoft 365:
- Outlook: samenwerken via e-mail met een postvak IN en agenda voor gedeelde groepen
- Microsoft Teams: een werkruimte op basis van permanente chatwaar u informele, realtime gesprekken voeren rond verschillende onderwerpen, georganiseerd door specifieke subgroepen
- Yammer: sociale ervaring voor samenwerking

> [!NOTE]
> Als u een nieuwe groep maakt via andere toepassingen voor teamwork - zoals SharePoint, Planner of Stream - wordt een groep gemaakt met een Postvak IN van Outlook en de mogelijkheid om verbinding te maken met Microsoft Teams.

Afhankelijk van waar een groep wordt gemaakt, worden bepaalde resources automatisch ingericht, zoals:
- [Postvak IN](https://support.microsoft.com/en-us/office/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22) - Voor e-mailgesprekken tussen groepsleden. Deze inbox heeft een e-mailadres en kan worden ingesteld om berichten te accepteren van mensen buiten de groep en zelfs buiten uw organisatie, net als een traditionele distributielijst.
 - [Agenda](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a) : voor het plannen van afspraken met betrekking tot de groep
- [SharePoint-teamsite](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e) – Een centrale opslagplaats voor informatie, koppelingen en inhoud met betrekking tot uw groep
- [SharePoint-documentbibliotheek](https://support.microsoft.com/en-us/office/share-group-files-in-outlook-749bc73b-90c9-4760-9b6f-9aa1cf01b403) : een centrale plek voor de groep om bestanden op te slaan en te delen
- [OneNote-notitieblok](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97) – Voor het verzamelen van ideeën, onderzoek en informatie
- [Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) – Voor het toewijzen en beheren van projecttaken onder uw groepsleden
- [Yammer-groep](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2) – Een gemeenschappelijke plaats om gesprekken te voeren en informatie te delen
- Microsoft Teams – Een werkruimte op basis van chatin Microsoft 365

Ga naar [Meer informatie over Microsoft 365-groepen](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)voor meer informatie over welke bronnen voor elke groep worden gemaakt.

> [!NOTE]
> Wanneer een nieuwe Microsoft 365-groep wordt gemaakt via Yammer of Teams, is de groep niet zichtbaar in Outlook of het adresboek omdat de primaire communicatie tussen deze gebruikers plaatsvindt in hun respectievelijke clients. Yammer-groepen kunnen niet worden verbonden met Microsoft Teams.

## <a name="where-to-start-a-conversation"></a>Waar een gesprek te beginnen
Er zijn meerdere plaatsen om een gesprek te voeren binnen Microsoft 365. Als u begrijpt waar ze een gesprek moeten starten, kunnen organisaties een communicatiestrategie definiëren.

![afbeelding desc](../../media/03.png)

- Teams: chat-based workspace (high velocity collaboration) – inner loop
   - Gebouwd voor samenwerking met de mensen met wie je elke dag werkt
  - Zet informatie binnen handbereik van gebruikers in één ervaring
  - Tabbladen, connectors en bots toevoegen
  - Live chat, audio/video conferencing, opgenomen vergaderingen

- Yammer: verbinding maken via de organisatie (sociaal ondernemen) – externe lus
  - Praktijkgemeenschappen - Crossfunctionele groepen mensen die een gemeenschappelijk belang of expertise delen, maar niet noodzakelijkerwijs dagelijks samenwerken
  - Leiderschapsverbinding, leergemeenschappen, op rollen gebaseerde gemeenschappen

- Outlook-groepen: moderne DL (e-mailgebaseerde samenwerking)
  - Alomtegenwoordig voor gerichte communicatie
  - DLs upgraden naar Microsoft 365-groepen - [Waarom moet u upgraden?](https://support.microsoft.com/office/why-you-should-upgrade-your-distribution-lists-to-groups-in-outlook-7fb3d880-593b-4909-aafa-950dd50ce188)

- SharePoint – Core-ervaring met contentsamenwerking voor alle Microsoft 365-groepen
  - Elke groep krijgt een verbonden SharePoint-teamsite
  - Inhoud delen, aangepaste pagina's maken en nieuws over auteurs
  - [Bestaande](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview) SharePoint-teamsites koppelen aan nieuwe Microsoft 365-groepen

##  <a name="managing-and-governing-microsoft-365-at-scale"></a>Microsoft 365 beheren en besturen op schaal

Microsoft 365-groepen heeft een uitgebreide set tools om alle beheermogelijkheden te implementeren die uw organisatie nodig heeft. In het volgende gedeelte worden de mogelijkheden beschreven, aanbevolen, aanbevolen en worden richtlijnen gegeven om de juiste vragen te stellen om de vereisten voor governance te bepalen en hoe daaraan te voldoen.

**In deze rubriek**:
- [Bepalen wie Microsoft 365-groepen kan maken](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#control-who-can-create-office-365-groups)
- [Zachte verwijderen en herstellen groeperen](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-soft-delete-and-restore)
- [Groepsnaamgevingsbeleid](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-naming-policy)
- [Verloopbeleid voor groep](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-expiration-policy)
- [Toegang tot groepsgasten](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-guest-access)
- [Groepsbeleid & informatiebescherming](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-policies--information-protection)
- [Traditionele samenwerkingstools upgraden](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#upgrade-traditional-collaboration-tools)
- [Groepsrapportage](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#groups-reporting)

### <a name="control-who-can-create-microsoft-365-groups"></a><a name="control-who-can-create-office-365-groups"></a>Bepalen wie Microsoft 365-groepen kan maken
Groepen kunnen worden gemaakt door eindgebruikers van meerdere eindpunten, waaronder Outlook, SharePoint, Teams en andere omgevingen.

![afbeelding desc](../../media/04.png)
> [!Tip]
>- Overweeg sterk self-service om groepseigenaren te machtigen.
>- Documenteer en communiceer hoe u een groep aanvraagt.
>- Bekijk opnieuw wie groepen kan maken tijdens uw cloudreis.
>- Overweeg dynamisch lidmaatschap te gebruiken om de leden van de beveiligingsgroep te configureren om het maken van groepen te beheren.
>- Beoordeel welke groepen scenario's kunnen worden beheerd via een dynamisch lidmaatschap en laat self-service voor de rest.

Er zijn drie primaire modellen van inrichting in groepen: open, IT-led, en gecontroleerd. In de volgende tabel worden de voordelen van elk model beschreven.

| Model          | Voordelen                                                   |
| -------------- | ------------------------------------------------------------ |
| Openen (standaard) | Gebruikers kunnen hun eigen groepen maken als dat nodig is zonder te hoeven wachten op, of lastig IT. |
| IT-geleide         | Gebruikers vragen een groep van IT. IT kan hen begeleiden bij het selecteren van de beste samenwerkingstools voor hun behoeften. |
| Gecontroleerd     | Groepscreatie beperkt tot specifieke personen, teams of services. Zie [Beheren wie Microsoft 365-groepen kan maken](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups)voor meer informatie. |

Uw organisatie heeft mogelijk specifieke vereisten om strenge controles uit te voeren op wie groepen kan maken. Gebruik de volgende tabel om te helpen bij het maken van de beslissing over welk inrichtingsmodel bij uw organisatie past.

|         |         |         |
|---------|---------|---------|
|![afbeelding desc](../../media/decision_point.png)|Beslissingspunten|<ul><li>Welk inrichtingsmodel past bij de eisen van uw organisatie?</li><li>Vereist uw organisatie het beperken van het maken van groepen tot beheerders?</li><li>Vereist uw organisatie het beperken van groepscreatie tot leden van beveiligingsgroepen?</li><li>Vereist uw organisatie dat sommige groepen dynamisch worden gemaakt op basis van gebruikerskenmerken, zoals afdeling?</li></ul>|
|![afbeelding desc](../../media/next_steps.png)|Volgende stappen|<ul><li>Documenteer de vereisten van uw organisatie voor het maken van groepen en teams.</li><li>Plan om deze vereisten te implementeren als onderdeel van de implementatie van uw groepen.</li><li>Communiceer en publiceer uw beleid om gebruikers te informeren over het gedrag dat ze kunnen verwachten</li><li>Plan om dynamisch lidmaatschap te implementeren waar van toepassing.</li></ul>|

> [!Important]
> Het beperken van het maken van groepen en teams kan de productiviteit van gebruikers vertragen omdat veel Microsoft 365-services vereisen dat groepen worden gemaakt om de service te laten functioneren. Zie [Waarom bepalen wie Microsoft 365-groepen maakt voor](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide%23why-control-who-creates-office-365-groups) meer informatie?

#### <a name="resources"></a>*Resources*
- [Beheren wie Microsoft 365-groepen kan maken](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide)
- [Groepen dynamisch invullen op basis van objectkenmerken](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-with-advanced-rules)
- [De standaardinstelling van Microsoft 365-groepen voor Outlook wijzigen in openbaar of privé](https://support.office.com/article/office-365-groups-in-outlook-private-by-default-36236e39-26d3-420b-b0ac-8072d2d2bedc)
- [Beveiligingsgroepen synchroniseren met een teamlidmaatschap](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Syncing-Security-Groups-with-team-membership/ba-p/241959)

### <a name="group-soft-delete-and-restore"></a><a name="group-soft-delete-and-restore"></a>Zachte verwijderen en herstellen groeperen
Als u een Microsoft 365-groep hebt verwijderd, blijft deze standaard 30 dagen behouden. Tijdens deze periode van 30 dagen kunt u de groep nog steeds herstellen. Na 30 dagen worden de groep en de bijbehorende inhoud definitief verwijderd en kunnen deze niet worden hersteld.

> [!Tip]
>- Communiceer het herstelproces naar uw gebruikers.
>- Train je helpdeskteam.
>- Volg komende groepen die worden verwijderd met PowerShell-script.

|         |         |         |
|---------|---------|---------|
|![afbeelding desc](../../media/decision_point.png)|Beslissingspunten|<ul><li>Wilt u dat bepaalde activa worden gearchiveerd voor langdurige opslag?</li><li>Heeft u bepaalde bewaarvereisten voor uw organisatie?</li></ul>|
|![afbeelding desc](../../media/next_steps.png)|Volgende stappen|<ul><li>Communiceer en publiceer het beleid voor verwijderen en herstellen om gebruikers te informeren over het gedrag dat ze kunnen verwachten </li><li> Documenteer de vereisten van uw organisatie voor het bewaken van verwijderde groepen.</li><li>Plan om deze vereisten te implementeren als onderdeel van de implementatie van uw groepen.</li></ul>|

> [!Important]
>Als een gebruiker tijdens de 'bewaarperiode' toegang probeert te krijgen tot de site, verschijnt de melding 403 verboden bericht. Als de gebruiker na deze periode toegang probeert te krijgen tot de site, verschijnt de melding 404 bericht niet gevonden.

#### <a name="resources"></a>*Resources*
- [Een verwijderde Microsoft 365-groep herstellen](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group?ui=en-US&rs=en-001&ad=US)
- [Een verwijderde Microsoft 365-groep herstellen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)
- [Delete groups using the Remove-UnifiedGroup cmdlet](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx) (Groepen verwijderen met de cmdlet Remove-UnifiedGroup)

### <a name="group-naming-policy"></a><a name="group-naming-policy"></a>Groepsnaamgevingsbeleid
Met een naamgevingsbeleid kunnen u en uw gebruikers de functie van de groep, het lidmaatschap, de geografische regio of de groep identificeren. Het naamgevingsbeleid kan ook helpen bij het categoriseren van groepen in het adresboek. U het beleid gebruiken om te voorkomen dat specifieke woorden worden gebruikt in groepsnamen en aliassen.

> [!Tip]
> - Gebruik korte tekenreeksen als achtervoegsel.
> - Gebruik kenmerken met waarden.
> - Wees niet te creatief, de totale naamlengte heeft een maximum van 264 tekens.
> - Upload uw organisatie specifieke geblokkeerde woorden om het gebruik te beperken.


|         |         |         |
|---------|---------|---------|
|![afbeelding desc](../../media/decision_point.png)|Beslissingspunten|<ul><li>Heeft uw organisatie een specifieke naamgevingsconventie voor groepen nodig?</li><li>Heeft uw organisatie de naamgevingsconventie nodig voor alle workloads?</li><li>Heeft uw organisatie specifieke woorden die u wilt voorkomen dat gebruikers worden gebruikt?</li></ul>|
|![afbeelding desc](../../media/next_steps.png)|Volgende stappen|<ul><li>Documenteer de vereisten van uw organisatie voor het benoemen van groepen. </li><li> Plan om deze vereisten te implementeren als onderdeel van de implementatie van uw groepen.</li><li> Communiceer en publiceer het naamgevingsbeleid en de richtlijnen om gebruikers te informeren.</li></ul>|

> [!Important]
>Het naamgevingsbeleid wordt toegepast op groepen die zijn gemaakt voor alle groepenworkloads (zoals Outlook, Microsoft Teams, SharePoint, Planner, Yammer, enz.). Het wordt toegepast op zowel de groepsnaam als de groepsalias. Het wordt toegepast wanneer een gebruiker een groep maakt en wanneer groepsnaam of alias wordt bewerkt voor een bestaande groep.

#### <a name="resources"></a>*Resources*
- [Naamgevingsbeleid voor Microsoft 365-groepen](https://docs.microsoft.com/office365/admin/create-groups/groups-naming-policy)
- [Een naamgevingsbeleid afdwingen voor Microsoft 365-groepen in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=868340)
- [Azure Active Directory-cmdlets voor het configureren van groepsinstellingen](https://go.microsoft.com/fwlink/?linkid=868341)
- [Voorbeeld van functies voor groepsnaamgeving](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/NamingPolicy)

### <a name="group-expiration-policy"></a><a name="group-expiration-policy"></a>Verloopbeleid voor groep
Beheerders kunnen een vervaldatum opgeven en elke groep die het einde van die periode bereikt en niet wordt verlengd, wordt verwijderd. De vervaldatum begint wanneer de groep wordt gemaakt of op de datum waarop de groep voor het laatst is verlengd. Groepseigenaren ontvangen automatisch een e-mail vóór het verstrijken, zodat ze de groep opnieuw kunnen verlengen voor een ander verloopinterval. Actieve groepen worden automatisch vernieuwd.

Zodra u hebt ingesteld dat een groep verloopt:
- Eigenaren van de groep worden op de hoogte gesteld om de groep te vernieuwen als de vervaldatum nadert
- Elke groep die niet wordt vernieuwd, wordt verwijderd
- Elke groep die wordt verwijderd, kan binnen 30 dagen worden hersteld door de groepseigenaren of de beheerder

> [!Tip]
> - Pilot met specifieke groepen in eerste instantie.
> - Kies inactieve groepen op basis van het activiteitenrapport in het Microsoft 365-beheercentrum.
> - Communiceer het vernieuwingsproces met groepseigenaren.
> - Aan boord van uw helpdeskteam.
> - Zorg ervoor dat groepen meerdere eigenaren hebben en configureer e-mail voor weesgroepen.


|         |         |         |
|---------|---------|---------|
|![afbeelding desc](../../media/decision_point.png)|Beslissingspunten|<ul><li>Heeft uw organisatie een vervaldatum voor teams nodig?</li><li>Bepaal de strategie voor het omgaan met weesgroepen.</li></ul>|
|![afbeelding desc](../../media/next_steps.png)|Volgende stappen|<ul><li>Documenteer de vereisten van uw organisatie voor het verlopen, bewaren en archiveren van gegevens van uw organisatie.</li><li>Plan om deze vereisten te implementeren als onderdeel van de implementatie van uw groepen.</li><li>Plan om een aangepaste taak te implementeren om te rapporteren over groepen die afzonderlijke eigenaren hebben of zonder eigenaar zijn. </li></ul>|

> [!Important]
>Wanneer u het verloopbeleid wijzigt, berekent de service de vervaldatum voor elke groep opnieuw. Het begint altijd te tellen vanaf de datum waarop de groep is gemaakt en past vervolgens het nieuwe verloopbeleid toe.

#### <a name="resources"></a>*Resources*
- [Verloopbeleid voor Microsoft 365-groep](https://support.office.com/article/Office-365-Group-Expiration-Policy-8d253fe5-0e09-4b3c-8b5e-f48def064733?ui=en-US&rs=en-US&ad=US)
- [Het verloopbeleid configureren voor Microsoft 365-groepen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)

### <a name="group-guest-access"></a><a name="group-guest-access"></a>Toegang tot groepsgasten
Beheerders kunnen bepalen of gasten toegang moeten krijgen tot Microsoft 365-groepen voor hun hele organisatie of voor afzonderlijke Microsoft 365-groepen. Ze kunnen ook bepalen wie gasten aan groepen kan toevoegen.
>[!Tip]
>- Gasttoegang inschakelen op tenantniveau. Blokkeer indien nodig voor specifieke groepen.
>- Regel het gebruik van gastdomeinen toestaan/blokkeren, gastinviterrol, toegangsbeoordelingen, gebruiksvoorwaarden.
>- Houd de activiteit van gastgebruikers bij via auditlogs.

|         |         |         |
|---------|---------|---------|
|![afbeelding desc](../../media/decision_point.png)|Beslissingspunten|<ul><li>Moet u de mogelijkheid beperken om gasten per groep toe te voegen aan teams?</li><li> Moet uw organisatie relevante disclaimers presenteren voor wettelijke of nalevingsvereisten?</li><li>Heeft uw organisatie de behoefte om de administratieve over-head van het toevoegen en verwijderen van gebruikers te verminderen?</li><li>Verwacht uw organisatie controlecontroles voor gast/externe toegang?</li></ul>|
|![afbeelding desc](../../media/next_steps.png)|Volgende stappen|<ul><li>Documentvereisten voor gast/externe toegang voor bepaalde geclassificeerde groepen, waaronder de bewaartermijn en het optreden.</li><li>De vereisten van documentorganisatie waarvoor groepen gebruiksvoorwaarden en toegangscontrole vereisen. </li><li>Voer beoordelingen uit om groepslidmaatschappen efficiënt te beheren voor zowel interne als gastgebruikers.</li></ul>|


#### <a name="resources"></a>*Resources*
- [Samenwerken met mensen buiten uw organisatie](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)
- [Gasttoegang beheren in Microsoft 365-groepen](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups)
- [Gasttoegang in Microsoft 365-groepen](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)
- [Azure AD-toegangsbeoordelingen](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)
- [Functie gebruiksvoorwaarden voor Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-tou)
- [Google Federatie](https://docs.microsoft.com/azure/active-directory/b2b/google-federation)

### <a name="group-policies--information-protection"></a><a name="group-policies--information-protection"></a>Groepsbeleid & informatiebescherming
Microsoft 365-groepen is gebouwd op de geavanceerde beveiligings- en nalevingsmogelijkheden van Microsoft 365 en ondersteunt classificaties, controle en rapportage, zoeken naar nalevingsinhoud, e-discovery, juridische blokkering en bewaarbeleid.
>[!Tip]
>- Configureer classificatie, gebruiksrichtlijnen en labels die zijn afgestemd op de behoeften van uw organisatie.
>- Bewaarbeleid kan onafhankelijk van labels worden gedefinieerd.
>- Auditgroepen activiteiten: creatie, verwijdering, enz.
>- Beheer groepsprivacy en gasttoegang op basis van classificatie.

|         |         |         |
|---------|---------|---------|
|![afbeelding desc](../../media/decision_point.png)|Beslissingspunten|<ul><li>Heeft uw organisatie specifieke gebruiksvereisten die aan alle gebruikers moeten worden gecommuniceerd?</li><li>Heeft uw organisatie de classificaties van alle inhoud nodig?</li><li>Vereist uw organisatie dat inhoud voor een bepaalde periode wordt bewaard?</li><li>Vereist uw organisatie dat er specifieke beleid voor het bewaren van gegevens wordt toegepast op groepen?</li><li>Verwacht uw organisatie de mogelijkheid te vereisen om inactieve groepen te archiveren om de inhoud te bewaren?</li><li>Hebben groepsmakers de mogelijkheid nodig om organisatiespecifieke classificaties toe te wijzen aan teams?</li></ul>|
|![afbeelding desc](../../media/next_steps.png)|Volgende stappen|<ul><li>De gebruiksrichtlijnen van uw organisatie voor groepen documenteren</li><li>Documenteer de vereisten van uw organisatie voor classificatie.</li><li>Bepaal het af te dwingen beleid op basis van de classificatie, bijvoorbeeld gevoeligheid, retentie, gasttoegang.</li><li>Definieer de gevoeligheidslabels voor uw organisatie en welke beveiligingsinstellingen u wilt toevoegen.</li><li>Definieer een labelbeleid om te bepalen welke gebruikers en groepen deze labels zien.</li><li>Configureer het voorbeeld van het [gevoeligheidslabel Groepen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) en begin met het classificeren van de groepen in uw organisatie.</li><li>Plan om deze vereisten te implementeren als onderdeel van de implementatie van uw groepen.</li></ul>|


#### <a name="resources"></a>*Resources*
- [Koppeling naar de gebruiksrichtlijnen van uw Microsoft 365-groepen](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#link-to-your-office-365-groups-usage-guidelines)
- [Classificaties maken voor Office-groepen in uw organisatie](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)
- [Groepsinstellingen configureren](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets)
- [Overzicht van bewaarbeleid](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)
- [Overzicht van gevoeligheidslabels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)
- [Overzicht van labels](https://docs.microsoft.com/microsoft-365/compliance/labels)
- [Zoeken in het auditlogboek](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
- [Een in-place juridische wachtplaats maken of verwijderen](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)
- [Een behoudsbeleid maken](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)
- [Een inhoudszoekopdracht uitvoeren in het Beveiligings& Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/content-search)
- [Bulk maken en publiceren bewaarlabels met PowerShell](https://docs.microsoft.com/microsoft-365/compliance/bulk-create-publish-labels-using-powershell)

### <a name="upgrade-traditional-collaboration-tools"></a><a name="upgrade-traditional-collaboration-tools"></a>Traditionele samenwerkingstools upgraden
Al jaren vertrouwen organisaties op distributiegroepen om te communiceren en samen te werken met groepen mensen, zowel binnen als buiten het bedrijf. Nu bieden Microsoft 365-groepen in Outlook echter een krachtigere oplossing voor samenwerking. Bovendien is het belangrijk om een Microsoft 365-groep te kunnen verbinden met een bestaande SharePoint-site als u die site wilt moderniseren.

>[!Tip]
>- Upgrade eenvoudig al uw in aanmerking komende distributielijsten binnen enkele seconden via het Exchange-beheercentrum of met PowerShell-cmdlets.
>- Verbind bestaande SharePoint-teamsites met nieuwe Microsoft 365-groepen.

|         |         |         |
|---------|---------|---------|
|![afbeelding desc](../../media/decision_point.png)|Beslissingspunten|<ul><li>Heeft uw organisatie distributielijsten die [niet in aanmerking komen](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists#how-do-i-check-which-dls-are-eligible-for-upgrade) voor een upgrade?<li>Bepaal naar welk type groep de distributielijst het best kan worden gemigreerd.</li></ul>|
|![afbeelding desc](../../media/next_steps.png)|Volgende stappen|<ul><li>Bepaal welke distributielijsten kandidaten zouden zijn voor een upgrade naar Microsoft 365-groepen.</li><li>Analyseer uw bestaande SharePoint-teamsites om te zien welke sites klaar zijn om met groepen te worden verbonden.</li><li>Laat andere teams in uw bedrijf weten dat u uw distributiegroep hebt geüpgraded en welke stappen u hebt genomen om deze succesvol te maken!</li></ul>|


#### <a name="resources"></a>*Resources*
- [Distributielijsten (DL) bijwerken naar groepen in Outlook](https://aka.ms/whyupgradedls)
- Upgrade met één klik via Exchange-beheercentrum of via [PowerShell-scripts](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists)
- [Distributielijsten migreren naar Microsoft 365-groepen - Help voor beheerders](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)
- [Bestaande SharePoint-sites verbinden met Microsoft 365-groepen:](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group)
- [De scannergegevens analyseren en gebruiken](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group-scanner)
- [SharePoint-moderniseringsscanner](https://github.com/SharePoint/sp-dev-modernization/tree/master/Tools/SharePoint.Modernization) (een tool op GitHub)

### <a name="groups-reporting"></a><a name="groups-reporting"></a>Groepsrapportage
In het dashboard Microsoft 365 Rapporten ziet u het activiteitenoverzicht voor de Microsoft-producten in uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product.
> [!TIP]
>- U de rapporten Groepen gebruiken om inzicht te krijgen in de activiteit van Microsoft 365-groepen in uw organisatie en om te zien hoeveel groepen worden gemaakt en gebruikt.
>-Het rapport Microsoft 365-groepen kan worden bekeken voor trends in de afgelopen 7 dagen, 30 dagen, 90 dagen of 180 dagen.
>- Monitor groepsactiviteiten voor groepspostvakgesprekken, groepssite-/bestandenactiviteit, details rond groepslidmaatschap inclusief aantal externe leden.
>- Controleer regelmatig om groepseigenaren van actieve groepen te bereiken om te leren gebruiksaanvragen te gebruiken en intern te versterken.
>- Maak gebruik van Power BI-contentpacks voor aanvullende inzichten.


|         |         |         |
|---------|---------|---------|
|![afbeelding desc](../../media/decision_point.png)|Beslissingspunten|<ul><li>Heeft uw organisatie regelmatige rapporten nodig om inzicht te krijgen in het gebruik van Microsoft 365-groepen?<li>Vereist uw organisatie rapportage over alle groepen die externe leden hebben?</li></ul>|
|![afbeelding desc](../../media/next_steps.png)|Volgende stappen|<ul><li>Documenteer de vereisten van uw organisatie voor het regelmatig controleren van activiteitenrapporten van groepen.</li></ul>|


#### <a name="resources"></a>*Resources*
- [Microsoft 365-overzichten in het beheercentrum](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)
- [Inhoudspakket voor Office 365-adoptie](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics)
- [Azure AD-inhoudspakket](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-power-bi-content-pack-how-to)
- [Microsoft Graph groepeert activiteits-API](https://developer.microsoft.com/graph/docs/api-reference/v1.0/resources/office_365_groups_activity_reports)
- [Rapport microsoft 365-groepen (uniforme groepen)](https://gallery.technet.microsoft.com/office/Office-365-Groups-Report-7e3e161b)
- [Controleactiviteitsrapporten in de Azure Active Directory-portal](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-audit-logs)
- [Microsoft Graph - Delta query gebruiken om wijzigingen bij te houden](https://docs.microsoft.com/graph/delta-query-overview)

## <a name="getting-started-based-on-your-cloud-adoption-journey"></a>Aan de slag op basis van uw cloudadoptietraject

Microsoft 365-groepen bieden een uitgebreide reeks beheermogelijkheden die uw organisatie mogelijk nodig heeft. Beschouw de volgende organisatieprofielen als richtlijnen om best practices te begrijpen, stel de juiste vragen om de vereisten voor governance te bepalen en hoe u daaraan voldoen.

**Houd rekening met de volgende organisatieprofielen:**
- Kleine bedrijven
- Middelgrote bedrijven
- Gereguleerd of onderneming

### <a name="small-business"></a>Kleine bedrijven
Overweeg een organisatie die Microsoft 365 heeft geïmplementeerd met ten minste Exchange Online- en SharePoint Online-licenties die de business essentials- en Business Premium-abonnementen bevatten, en de Enterprise E1-, E3- en E5-abonnementen zonder Azure Active Director Premium-licenties.

| Fase | Beschrijving |
| --------------- | ------------------------------------------------------------ |
| Begeleiding |<ul><li>Overweeg een selfservice-inrichtingsmodel.</li><li> Groepen in Outlook & SharePoint-sites zijn [standaard privé](https://techcommunity.microsoft.com/t5/Office-365-Groups/Groups-in-Outlook-and-Group-connected-team-sites-are-now-private/m-p/186395).</li><li> Groepen kunnen worden gemaakt door bestaande distributielijsten (DLs) één voor één of in bulk te upgraden via PowerShell. Zie [Distributielijsten voor upgrade's naar Microsoft 365-groepen](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists).</li><li> Gasttoegang inschakelen, maar regelen met het toestaan/blokkeren van gastdomeinen.</li><li> Gebruik groepsrapportage om inzicht te krijgen in hoe gebruikers groepen gebruiken.</li><li> Overweeg om een organisatiebreed Microsoft Teams-team te maken als een manier voor iedereen om deel uit te maken van één team voor samenwerking. </li></ul>|
| Volgende stappen      |<ul><li>Overweeg [siteontwerpen en sitescripts](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview) te gebruiken om het standaardontwerp te definiëren voor besturingselementen met behulp van de acties die zijn gedefinieerd in de [verwijzing naar JSON-schema.](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema)</li><li>Rapportage [van groepen bekijken](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups).</li><li>Totale groepen en inactieve/actieve groepen bijhouden.</li><li>Houd zowel Exchange- als SharePoint-opslag bij.</li><li>Groepsactiviteit weergeven voor groepspostvakgesprekken, groepssite-/bestandenactiviteit, enz.</li></ul> |

### <a name="medium-sized-business"></a>Middelgrote bedrijven
Naast de bovenstaande aanbevelingen wordt rekening gehouden met het volgende voor middelgrote bedrijven die Microsoft 365 hebben geïmplementeerd met ten minste een Enterprise E3/E5 met Azure Active Directory Premium P1-licenties.

| Fase | Beschrijving |
| --------------- | ------------------------------------------------------------ |
| Begeleiding |<ul><li>Kies over een open of IT-led inrichtingsmodel.</li><li> Overweeg om bepaalde groepen te maken die zijn gekoppeld aan [dynamische lidmaatschapsregels](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) op basis van Azure AD-kenmerken zoals Afdeling</li><li> Definieer classificaties binnen uw organisatie, bijvoorbeeld Highly Confidential, Confidential (default), General.</li><li>  Definieer het beleid op basis van classificatie, zoals retentie en gevoeligheid.</li><li> SharePoint is de inhoudsservice voor elke Microsoft 365-groep. Overweeg [sharepoint online-sites te](https://docs.microsoft.com/office365/enterprise/deploy-sharepoint-online-sites-for-three-tiers-of-protection) ontwerpen en te implementeren voor drie beveiligingsniveaus (basislijn, gevoelig en zeer vertrouwelijk). Zie [Beveiligde SharePoint Online-sites en -bestanden voor](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)meer informatie over deze drie beschermingsniveaus.</li><li> Zowel openbare als particuliere groepen worden standaard in de GAL vermeld. Bepaal welke groepen u wilt weergeven in de GAL-specifieke groepen die buiten Microsoft Teams zijn gemaakt.  Gebruik de cmdlet 'HiddenFromAddressListsEnabled' of 'HidefromExchangeClients' van de [Set-UnifiedGroup](https://technet.microsoft.com/library/mt238274(v=exchg.160).aspx) om specifieke groepen te verbergen.</li></ul> |
| Volgende stappen      |<ul><li>Definieer [gebruiksrichtlijnen](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets) om uw gebruikers te informeren over aanbevolen procedures die hun groepen effectief houden en hen te informeren over intern inhoudsbeleid. Bijvoorbeeld het begrijpen van classificaties, beleid en procedures. </li><li>Definieer de levenscyclusperiode van groepen die moeten worden verlengd of worden verwijderd - vervaldatumbeleid.</li><li>Overweeg de volgende aangepaste taken te maken om beleid te implementeren op basis van classificaties.</li><li>Stel Privacy in op Privé.</li><li>Extern lidmaatschap/delen uitschakelen. </li><li>E-mails om groepsleden op de hoogte te stellen van groepen [zonder eigenaar.](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)</li><li>Eigendomsbeleid afdwingen (min. 2 eigenaren).</li><li> Bewaarbeleid voor groepen definiëren op basis van classificatie. </li><li>Overzicht van bewaarbeleid.</li><li>Powershell gebruiken om groepen te identificeren met een classificatie- en [setretentiecompliancebeleid](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy?view=exchange-ps).</li><li>Overweeg siteontwerpen en sitescripts te gebruiken om de besturingselementen te definiëren met behulp van de acties die zijn gedefinieerd in de [verwijzing naar json-schema.](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema)</li><li>Overweeg [een eenvoudige sitemap te](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-trigger-flow-tutorial) maken met behulp van een siteontwerp en Microsoft Flow. Wanneer een site wordt gemaakt met behulp van deze site ontwerp, details van de site worden vastgelegd en geschreven naar een lijst. </li></ul>|

### <a name="regulated-or-enterprise"></a>Gereguleerd of onderneming
Naast de bovenstaande aanbevelingen wordt rekening gehouden met het volgende voor sterk gereguleerde of grote ondernemingen zoals overheids-, financiële services of gezondheidszorg die Office 365 heeft geïmplementeerd met ten minste een Enterprise E3/E5 met Azure Active Directory Premium P1/P2-licenties.

| Fase | Beschrijving |
| --------------- | ------------------------------------------------------------ |
| Begeleiding |<ul><li> Definieer beleidsregels voor gegevensbeheer van de SharePoint-site die is gekoppeld aan de groep op basis van classificatie.</li><li>[Bescherm SharePoint Online-bestanden met labels en DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</li><li>[Bescherm SharePoint Online-bestanden met Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</li><li> Groepssite ingericht in regio die is gekoppeld aan de voorkeurslocatie van de gebruiker[(multigeo).](https://docs.microsoft.com/office365/enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-office-365)</li><li> Lidmaatschapsbeoordelingen voor groepen met externe leden[(toegangsbeoordelingen).](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-access-reviews-overview)</li><li>Zorg ervoor dat werknemers of gastgebruikers relevante disclaimers voor wettelijke of nalevingsvereisten zien voordat ze toegang krijgen. ([gebruiksvoorwaarden](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou)).</li><li>Identificeren en rapporteren over Microsoft 365-groepen met een bepaalde [classificatie die ook externe gebruikers hebben.](https://techcommunity.microsoft.com/t5/Office-365-Groups/Sample-Powershell-to-identify-groups-with-HBI-classification-and/m-p/215561)</li><li>Geheime groepen waar lidmaatschappen verborgen moesten worden gemaakt met de cmdlet [Nieuw-UnifiedGroup](https://technet.microsoft.com/library/mt219359(v=exchg.160).aspx) (met behulp van de schakelaar HiddenGroup-MembershipEnabled) bij het maken van groepen.</li><li>Definieer de [gevoeligheidslabels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) voor de organisatie om [de toegang tot inhoud te beperken met behulp van versleuteling](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) en publicatie naar specifieke Microsoft 365-groepen.</li><li>Voorkom dat gevoelige inhoud uw organisatie verlaat op apparaten waarop Windows wordt uitgevoerd met [gevoeligheidslabels met Windows Information Protection](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553). |
| Volgende stappen      | <ul><li> Gebruik siteontwerp- en sitescripts om de [standaardacties](https://developer.microsoft.com/office/blogs/site-scripts-site-designs-summer-2018-update/) te definiëren die plaatsvinden wanneer een nieuwe site wordt gemaakt. [Configureer](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-apply-external-sharing-setting) bijvoorbeeld de instelling voor extern delen of [activeer een Microsoft Flow om een Azure-functie](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-azure-function) aan te roepen om configuraties toe te passen die niet native worden ondersteund. </li><li> Documentvereisten om [SharePoint Online-bestanden met labels en DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) te beveiligen voor sites die zijn gekoppeld aan Microsoft 365-groepen.</li><li>Vereisten voor documentorganisatie voor [Secure SharePoint Online-sites en -bestanden](https://docs.microsoft.com/microsoft-365/security/office-365-security/secure-sharepoint-online-sites-and-files) die zijn verbonden met Microsoft 365-groepen. </li><li>Vereisten voor documentorganisatie om [gevoeligheidslabels](hhttps://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) te publiceren voor specifieke gebruikers of groepen om inhoud te beschermen.</li></ul> |

## <a name="groups-management-capability-planning-checklist"></a>Checklist voor het plannen van groepsbeheermogelijkheden

Een aantal groepengerelateerde besturingselementen kunnen worden beheerd via Azure Active Directory. Zie [Azure Active Directory-cmdlets voor het configureren van groepsinstellingen voor](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)meer informatie over het configureren van groepsinstellingen.

Gebruik de volgende tabel om te bepalen welke mogelijkheden u nodig hebt om de vereisten van uw organisatie te implementeren. Het zal u helpen bepalen welke licenties u nodig hebt, zodat u vooruit plannen.

| **Vermogen**      | **Details**                                    | **Azure AD Premium-licentie vereist** | **Besluit** |
| ------------------- | ---------------------------------------------- | ------------------------------------- | ------------ |
| Groepsnaamgevingsbeleid | Gebruik op basis van voorvoegsel gebaseerde aangepaste geblokkeerde woorden. | P1 P1                                    |      Tbd     |
| Groepsclassificatie | Classificaties toewijzen aan teams. | P1 P1                                    |   Tbd        |
| Toegang tot groepsgasten | Gasten toestaan of voorkomen dat ze aan groepen worden toegevoegd. | Nee                                    |  Tbd        |
| Groepscreatie | Beperk het maken van teams tot beheerders. | Nee                                    |   Tbd        |
| Groepscreatie | Beperk het maken van teams tot leden van beveiligingsgroepen. | P1 P1                                    |     Tbd      |
| Richtlijnen voor groepsgebruik | Stel een koppeling in de richtlijnen voor groepsgebruik die zichtbaar zijn op alle eindpunten voor het maken van groepen. | P1 P1                                    |   Tbd        |
| Verborgen lidmaatschap | De leden van de Microsoft 365-groep verbergen voor gebruikers die geen lid van de groep zijn | Nee                                    |   Tbd        |
| Verloopbeleid | Beheer de levenscyclus van Microsoft 365-groepen door een verloopbeleid in te stellen. | P1 P1                                    |  Tbd        |
| Rapporten over groepsactiviteiten | Krijg inzicht in de activiteit van Microsoft 365-groepen in uw organisatie en bekijk hoeveel Microsoft 365-groepen worden gemaakt en gebruikt. | Nee                                    |    Tbd       |
| Bewaarbeleid | Gegevens voor een bepaalde periode bewaren of verwijderen door bewaarbeleid voor Microsoft 365-groepen in te stellen in het Security & Compliance Center. **Let op:** Voor het gebruik van deze functie is een licentie vereist voor Office 365 Enterprise E3 of hoger. | Nee                                    |    Tbd       |
| Preventiebeleid voor gegevensverlies | Identificeer gevoelige informatie op sites met microsoft 365-groepen verbonden sites en voorkom het per ongeluk delen. **Let op:** Voor het gebruik van deze functie is een licentie vereist voor Office 365 Enterprise E3 of hoger. | Nee                                    |     Tbd      |
| Archiveren en herstellen | Archiveer een team wanneer het niet meer actief is, maar u wilt het in de toekomst bewaren voor referentie of om in de toekomst opnieuw te activeren. | Nee                                    |   Tbd        |
| Toegang tot beoordelingen | Beoordelingen uitvoeren om groepslidmaatschappen voor zowel interne als gastgebruikers efficiënt te beheren | P2                                    |   Tbd       |
| Gebruiksvoorwaarden | Een eenvoudige methode die organisaties kunnen gebruiken om informatie aan eindgebruikers te presenteren. Deze presentatie zorgt ervoor dat gebruikers relevante disclaimers zien voor wettelijke of nalevingsvereisten. | P1 P1                                    |         Tbd  |

