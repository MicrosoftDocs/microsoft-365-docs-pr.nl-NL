---
title: Plan voor groepen governance
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BSA160
description: Meer informatie over het plannen van microsoft 365-groepenbeheer.
ms.openlocfilehash: 37d243b56de363985ecb9463dfe5eb182d9e40b1
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780491"
---
# <a name="plan-for-governance-in-groups"></a>Plan voor governance in groepen

Microsoft 365 Groups heeft een uitgebreide reeks tools om alle beheermogelijkheden te implementeren die uw organisatie nodig heeft. Dit artikel begeleidt IT-professionals om de juiste vragen te stellen om hun vereisten voor governance te bepalen en hoe ze hieraan kunnen voldoen op basis van hun organisatieprofiel.

## <a name="why-microsoft-365-groups"></a>Waarom Microsoft 365-groepen?
![afbeelding desc](../../media/01.png)

We weten dat organisaties vandaag de dag gebruik maken van een diverse toolset. Er is het team van ontwikkelaars met behulp van team chat, de leidinggevenden het verzenden van e-mail, en de hele organisatie verbinding over enterprise social. Er zijn meerdere samenwerkingstools in gebruik omdat elke groep uniek is en zijn eigen functionele behoeften en werkstijl heeft. Sommigen zullen alleen e-mail gebruiken, terwijl anderen voornamelijk in chat zullen leven. 

Als gebruikers het gevoel hebben dat de it-tools niet aan hun behoeften voldoen, zullen ze waarschijnlijk hun favoriete consumentenapp downloaden die hun scenario's ondersteunt. Hoewel dit proces gebruikers in staat stelt om snel aan de slag te gaan, leidt dit tot een frustrerende gebruikerservaring in de hele organisatie met meerdere aanmeldingen, moeite met delen en geen enkele plek om inhoud te bekijken. Dit concept wordt aangeduid als "Shadow IT" en vormt een aanzienlijk risico voor organisaties. Het vermindert de mogelijkheid om gebruikerstoegang uniform te beheren, beveiligings- en servicecompliancebehoeften te garanderen.

Microsoft 365 Groups stelt gebruikers in staat en vermindert het risico op schaduw-IT door in één stap veel van de tools te bieden die nodig zijn om samen te werken. Met Microsoft 365-groepen u een groep mensen kiezen met wie u wilt samenwerken en eenvoudig een verzameling resources instellen die deze personen kunnen delen. Het handmatig toewijzen van machtigingen aan resources behoort tot het verleden, omdat het toevoegen van leden aan de groep automatisch de benodigde machtigingen verleent aan alle activa die door de groep worden geleverd.

## <a name="technical-architecture"></a>Technische architectuur

Er zijn drie belangrijke communicatiemethoden die worden ondersteund door Microsoft 365-groepen. Groepen kunnen worden gemaakt binnen deze ervaringen en worden gebruikt in Microsoft 365:
- Outlook: samenwerken via e-mail met een postvak IN voor gedeelde groep en agenda
- Microsoft Teams: een permanente chatwerkruimte waar u informele, real-time gesprekken voeren over verschillende onderwerpen, georganiseerd door specifieke subgroepen
- Yammer: sociale bedrijfservaring voor samenwerking

> [!NOTE]
> Als u een nieuwe groep maakt via andere teamworktoepassingen - zoals SharePoint, Planner of Stream - wordt een groep gemaakt met een Outlook-postvak IN en de mogelijkheid om verbinding te maken met Microsoft Teams.

Afhankelijk van waar een groep wordt gemaakt, worden bepaalde resources automatisch ingericht, zoals:
- [Inbox](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) - Voor e-mailgesprekken tussen groepsleden. Deze inbox heeft een e-mailadres en kan worden ingesteld om berichten te accepteren van mensen buiten de groep en zelfs buiten uw organisatie, net als een traditionele distributielijst.
 - [Agenda](https://support.microsoft.com/office/0cf1ad68-1034-4306-b367-d75e9818376a) – Voor het plannen van gebeurtenissen met betrekking tot de groep
- [SharePoint-teamsite](https://support.microsoft.com/office/75545757-36c3-46a7-beed-0aaa74f0401e) – Een centrale opslagplaats voor informatie, links en inhoud met betrekking tot uw groep
- [SharePoint-documentbibliotheek](https://support.microsoft.com/office/749bc73b-90c9-4760-9b6f-9aa1cf01b403) – Een centrale plaats voor de groep om bestanden op te slaan en te delen
- [OneNote-notitieblok](https://support.microsoft.com/office/e768fafa-8f9b-4eac-8600-65aa10b2fe97) – Voor het verzamelen van ideeën, onderzoek en informatie
- [Planner](https://support.microsoft.com/office/4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) – Voor het toewijzen en beheren van projecttaken onder uw groepsleden
- [Yammer-groep](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2) : een gemeenschappelijke plaats om gesprekken te voeren en informatie te delen
- Microsoft Teams – Een chatwerkruimte in Microsoft 365

Ga voor meer informatie over welke bronnen voor elke groep worden gemaakt [naar Meer informatie over Microsoft 365-groepen](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).

> [!NOTE]
> Wanneer een nieuwe Microsoft 365-groep wordt gemaakt via Yammer of Teams, is de groep niet zichtbaar in Outlook of het adresboek omdat de primaire communicatie tussen deze gebruikers plaatsvindt in hun respectievelijke clients. Yammer-groepen kunnen niet worden verbonden met Microsoft Teams.

## <a name="where-to-start-a-conversation"></a>Waar een gesprek beginnen
Er zijn meerdere plaatsen om een gesprek te voeren binnen Microsoft 365. Als u begrijpt waar u een gesprek moet starten, kunnen organisaties een communicatiestrategie definiëren.

![afbeelding desc](../../media/03.png)

- Teams: chat-gebaseerde werkruimte (high velocity collaboration) – inner loop
   - Gebouwd voor samenwerking met de mensen met wie je elke dag werkt
  - Geeft informatie binnen handbereik van gebruikers in één ervaring
  - Tabbladen, connectoren en bots toevoegen
  - Live chat, audio/videoconferencing, opgenomen vergaderingen

- Yammer: verbinding maken in de hele organisatie (enterprise social) – buitenste lus
  - Praktijkgemeenschappen - Crossfunctionele groepen mensen die een gemeenschappelijk belang of deskundigheid hebben, maar niet noodzakelijkerwijs dagelijks samenwerken
  - Leiderschapsverbinding, leergemeenschappen, op rollen gebaseerde gemeenschappen

- Outlook-groepen: moderne DL (e-mailgebaseerde samenwerking)
  - Alomtegenwoordig voor gerichte communicatie
  - DLs upgraden naar Microsoft 365-groepen – [Waarom moet u upgraden?](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

- SharePoint – Samenwerkingservaring voor kerninhoud voor alle Microsoft 365-groepen
  - Elke groep krijgt een verbonden SharePoint-teamsite
  - Inhoud delen, aangepaste pagina's maken en auteursnieuws
  - [Bestaande](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview) SharePoint-teamsites verbinden met nieuwe Microsoft 365-groepen

##  <a name="managing-and-governing-microsoft-365-at-scale"></a>Microsoft 365 op schaal beheren en besturen

Microsoft 365 Groups heeft een uitgebreide reeks tools om alle beheermogelijkheden te implementeren die uw organisatie nodig heeft. In het volgende gedeelte worden de mogelijkheden beschreven, aanbevolen procedures aanbevolen en wordt u voorzien van richtlijnen om de juiste vragen te stellen om de vereisten voor governance te bepalen en hoe u daaraan voldoen.

**In deze rubriek**:
- [Bepalen wie Microsoft 365-groepen kan maken](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#control-who-can-create-office-365-groups)
- [Zachte verwijderen en herstellen groeperen](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-soft-delete-and-restore)
- [Beleid voor groepsnaamgeving](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-naming-policy)
- [Beleid voor het verlopen van groepen](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-expiration-policy)
- [Toegang tot groepsgasten](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-guest-access)
- [Groepsbeleid & informatiebeveiliging](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-policies--information-protection)
- [Traditionele samenwerkingstools upgraden](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#upgrade-traditional-collaboration-tools)
- [Groepsrapportage](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#groups-reporting)

### <a name="control-who-can-create-microsoft-365-groups"></a><a name="control-who-can-create-office-365-groups"></a>Bepalen wie Microsoft 365-groepen kan maken
Groepen kunnen worden gemaakt door eindgebruikers van meerdere eindpunten, waaronder Outlook, SharePoint, Teams en andere omgevingen.

![afbeelding desc](../../media/04.png)
> [!Tip]
>- Neem sterk rekening met selfservice om groepseigenaren sterker te maken.
>- Documenteren en communiceren hoe u een groep aanvraagt.
>- Bekijk wie tijdens uw cloudreis groepen kan maken.
>- Overweeg dynamisch lidmaatschap te gebruiken om leden van de beveiligingsgroep te configureren om groepscreatie te beheren.
>- Beoordeel welke groepen scenario's kunnen worden beheerd via een dynamisch lidmaatschap en maak selfservice voor de rest mogelijk.

Er zijn drie primaire inrichtingsmodellen in groepen: open, IT-led en gecontroleerd. In de volgende tabel worden de voordelen van elk model beschreven.

| Model          | Voordelen                                                   |
| -------------- | ------------------------------------------------------------ |
| Openen (standaard) | Gebruikers kunnen hun eigen groepen maken als dat nodig is zonder te hoeven wachten, of de moeite IT. |
| IT-geleid         | Gebruikers vragen een groep van IT. IT kan hen begeleiden bij het selecteren van de beste samenwerkingstools voor hun behoeften. |
| Gecontroleerd     | Groepscreatie beperkt tot specifieke personen, teams of services. Zie [Beheren wie Microsoft 365-groepen kan maken](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups)voor meer informatie. |

Uw organisatie heeft mogelijk specifieke vereisten om strikte controles uit te voeren over wie groepen kan maken. Gebruik de volgende tabel om de beslissing te nemen over welk inrichtingsmodel bij uw organisatie past.

|         |         |         |
|---------|---------|---------|
|![afbeelding desc](../../media/decision_point.png)|Beslissingspunten|<ul><li>Welk inrichtingsmodel past bij uw organisatievereisten?</li><li>Vereist uw organisatie het beperken van groepscreatie tot beheerders?</li><li>Vereist uw organisatie het beperken van groepscreatie tot leden van de beveiligingsgroep?</li><li>Vereist uw organisatie dat sommige groepen dynamisch worden gemaakt op basis van gebruikerskenmerken, zoals afdeling?</li></ul>|
|![afbeelding desc](../../media/next_steps.png)|Volgende stappen|<ul><li>Documenteer de vereisten van uw organisatie voor groeps- en teamcreatie.</li><li>Plan om deze vereisten uit te voeren als onderdeel van de implementatie van uw groepen.</li><li>Communiceer en publiceer uw beleid om gebruikers te informeren over het gedrag dat ze kunnen verwachten</li><li>Plan om dynamisch lidmaatschap te implementeren waar van toepassing.</li></ul>|

> [!Important]
> Het beperken van groep en teamcreatie kan de productiviteit van gebruikers vertragen omdat veel Microsoft 365-services vereisen dat groepen worden gemaakt om de service te laten functioneren. Zie [Waarom bepalen wie Microsoft 365-groepen maakt voor](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide%23why-control-who-creates-office-365-groups) meer informatie?

#### <a name="resources"></a>*Resources*
- [Beheren wie Microsoft 365-groepen kan maken](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide)
- [Groepen dynamisch vullen op basis van objectkenmerken](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-with-advanced-rules)
- [De standaardinstelling van Microsoft 365-groepen voor Outlook wijzigen in openbaar of privé](https://support.microsoft.com/office/36236e39-26d3-420b-b0ac-8072d2d2bedc)
- [Beveiligingsgroepen synchroniseren met teamlidmaatschap](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Syncing-Security-Groups-with-team-membership/ba-p/241959)

### <a name="group-soft-delete-and-restore"></a><a name="group-soft-delete-and-restore"></a>Zachte verwijderen en herstellen groeperen
Als u een Microsoft 365-groep hebt verwijderd, wordt deze standaard 30 dagen bewaard. Tijdens deze periode van 30 dagen kunt u de groep nog steeds herstellen. Na 30 dagen worden de groep en de bijbehorende inhoud definitief verwijderd en kunnen deze niet worden hersteld.

> [!Tip]
>- Communiceer het herstelproces naar uw gebruikers.
>- Train je helpdeskteam.
>- Volg komende groepen die worden verwijderd met behulp van PowerShell-script.

|         |         |         |
|---------|---------|---------|
|![afbeelding desc](../../media/decision_point.png)|Beslissingspunten|<ul><li>Wilt u dat bepaalde activa worden gearchiveerd voor langdurige opslag?</li><li>Heeft u bepaalde bewaarvereisten voor uw organisatie?</li></ul>|
|![afbeelding desc](../../media/next_steps.png)|Volgende stappen|<ul><li>Communiceer en publiceer het beleid voor verwijderen en herstellen om gebruikers te informeren over het gedrag dat ze kunnen verwachten </li><li> Documenteer de vereisten van uw organisaties voor het bewaken van verwijderde groepen.</li><li>Plan om deze vereisten uit te voeren als onderdeel van de implementatie van uw groepen.</li></ul>|

> [!Important]
>During the "soft-delete" period if a user tries to access the site they will get a 403 forbidden message. After this period if the user tries to access the site they will get a 404 not found message.

#### <a name="resources"></a>*Resources*
- [Een verwijderde Microsoft 365-groep herstellen](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group?ui=en-US&rs=en-001&ad=US)
- [Een verwijderde Microsoft 365-groep herstellen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)
- [Delete groups using the Remove-UnifiedGroup cmdlet](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx) (Groepen verwijderen met de cmdlet Remove-UnifiedGroup)

### <a name="group-naming-policy"></a><a name="group-naming-policy"></a>Beleid voor groepsnaamgeving
Met een naamgevingsbeleid kunnen u en uw gebruikers de functie van de groep, het lidmaatschap, de geografische regio of de groep identificeren. Het naamgevingsbeleid kan ook helpen bij het categoriseren van groepen in het adresboek. U het beleid gebruiken om te voorkomen dat specifieke woorden worden gebruikt in groepsnamen en aliassen.

> [!Tip]
> - Gebruik korte snaren als achtervoegsel.
> - Gebruik kenmerken met waarden.
> - Wees niet te creatief, de totale naamlengte heeft maximaal 264 tekens.
> - Upload uw organisatie specifieke geblokkeerde woorden om het gebruik te beperken.


|         |         |         |
|---------|---------|---------|
|![afbeelding desc](../../media/decision_point.png)|Beslissingspunten|<ul><li>Heeft uw organisatie een specifieke naamgevingsconventie voor groepen nodig?</li><li>Heeft uw organisatie de naamgevingsconventie voor alle workloads vereist?</li><li>Heeft uw organisatie specifieke woorden die u wilt voorkomen dat gebruikers worden gebruikt?</li></ul>|
|![afbeelding desc](../../media/next_steps.png)|Volgende stappen|<ul><li>Documenteer de vereisten van uw organisatie voor het benoemen van groepen. </li><li> Plan om deze vereisten uit te voeren als onderdeel van de implementatie van uw groepen.</li><li> Communiceer en publiceer het naamgevingsbeleid en de richtlijnen om gebruikers te informeren.</li></ul>|

> [!Important]
>Het naamgevingsbeleid wordt toegepast op groepen die zijn gemaakt voor alle groepswerkbelastingen (zoals Outlook, Microsoft Teams, SharePoint, Planner, Yammer, enz.). Het wordt toegepast op zowel de groepsnaam als de groepsalias. Het wordt toegepast wanneer een gebruiker een groep maakt en wanneer groepsnaam of alias wordt bewerkt voor een bestaande groep.

#### <a name="resources"></a>*Resources*
- [Microsoft 365-beleid voor naamgeving van groepen](https://docs.microsoft.com/office365/admin/create-groups/groups-naming-policy)
- [Een naamgevingsbeleid voor Microsoft 365-groepen afdwingen in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=868340)
- [Azure Active Directory-cmdlets voor het configureren van groepsinstellingen](https://go.microsoft.com/fwlink/?linkid=868341)
- [Voorbeeld van functies voor groepsnaamgeving](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/NamingPolicy)

### <a name="group-expiration-policy"></a><a name="group-expiration-policy"></a>Beleid voor het verlopen van groepen
Beheerders kunnen een verloopperiode opgeven en elke groep die het einde van die periode bereikt en niet wordt verlengd, wordt verwijderd. De vervaldatum begint wanneer de groep wordt gemaakt of op de datum waarop deze voor het laatst is verlengd. Groepseigenaren ontvangen automatisch een e-mail vóór de vervaldatum waarmee ze de groep kunnen verlengen voor een ander verloopinterval. Actieve groepen worden automatisch vernieuwd.

Nadat u een groep hebt ingesteld om te verlopen:
- Eigenaren van de groep worden op de hoogte gesteld om de groep te vernieuwen als het verloop nadert
- Elke groep die niet wordt verlengd, wordt verwijderd
- Elke groep die wordt verwijderd, kan binnen 30 dagen worden hersteld door de groepseigenaren of de beheerder

> [!Tip]
> - Pilot met specifieke groepen in eerste instantie.
> - Kies inactieve groepen op basis van het activiteitenrapport in het Microsoft 365-beheercentrum.
> - Communiceer het vernieuwingsproces met groepseigenaren.
> - Aan boord van uw helpdeskteam.
> - Zorg ervoor dat groepen meerdere eigenaren hebben en configureer e-mail voor weesgroepen.


|         |         |         |
|---------|---------|---------|
|![afbeelding desc](../../media/decision_point.png)|Beslissingspunten|<ul><li>Vereist uw organisatie het opgeven van een vervaldatum voor teams?</li><li>Bepaal de strategie voor het omgaan met weesgroepen.</li></ul>|
|![afbeelding desc](../../media/next_steps.png)|Volgende stappen|<ul><li>Documenteer de vereisten van uw organisatie voor groepsverloop, gegevensbewaring en archivering.</li><li>Plan om deze vereisten uit te voeren als onderdeel van de implementatie van uw groepen.</li><li>Plan om een aangepaste taak te implementeren om te rapporteren over groepen die één eigenaar hebben of eigenaarloos zijn. </li></ul>|

> [!Important]
>Wanneer u het vervaldatumbeleid wijzigt, berekent de service de vervaldatum voor elke groep opnieuw. Het begint altijd te tellen vanaf de datum waarop de groep is gemaakt en past vervolgens het nieuwe vervaldatumsbeleid toe.

#### <a name="resources"></a>*Resources*
- [Verloopbeleid voor Microsoft 365-groep](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy)
- [Het verloopbeleid configureren voor Microsoft 365-groepen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)

### <a name="group-guest-access"></a><a name="group-guest-access"></a>Toegang tot groepsgasten
Beheerders kunnen bepalen of ze gasten toegang willen geven tot Microsoft 365-groepen voor hun hele organisatie of voor afzonderlijke Microsoft 365-groepen. Ze kunnen ook bepalen wie gasten aan groepen kan laten toevoegen.
>[!Tip]
>- Toegang tot gasten inschakelen op tenantniveau. Blokkeer indien nodig voor specifieke groepen.
>- Beheer gastdomeinen toestaan/blokkeren, rol gastuitnodigers, toegangsbeoordelingen, gebruiksvoorwaarden.
>- Volg de activiteit van de gastgebruikers via auditlogboeken.

|         |         |         |
|---------|---------|---------|
|![afbeelding desc](../../media/decision_point.png)|Beslissingspunten|<ul><li>Moet u de mogelijkheid beperken om gasten per groep aan teams toe te voegen?</li><li> Moet uw organisatie relevante disclaimers presenteren voor wettelijke of nalevingsvereisten?</li><li>Heeft uw organisatie de behoefte om administratieve over-head van het toevoegen en verwijderen van gebruikers te verminderen?</li><li>Verwacht uw organisatie controlecontroles voor gast/externe toegang?</li></ul>|
|![afbeelding desc](../../media/next_steps.png)|Volgende stappen|<ul><li>Documentvereisten voor gast/externe toegang voor bepaalde geclassificeerde groepen, inclusief de bewaartermijn en het voorkomen.</li><li>De vereisten van de documentorganisatie waarvoor groepen gebruiksvoorwaarden en toegangscontrole vereisen. </li><li>Voer beoordelingen uit om groepslidmaatschappen efficiënt te beheren voor zowel interne als gastgebruikers.</li></ul>|


#### <a name="resources"></a>*Resources*
- [Samenwerken met mensen buiten uw organisatie](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)
- [Gasttoegang beheren in Microsoft 365-groepen](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups)
- [Gasttoegang in Microsoft 365-groepen](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)
- [Azure AD-toegangsbeoordelingen](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)
- [Functie Azure Active Directory-gebruiksvoorwaarden](https://docs.microsoft.com/azure/active-directory/active-directory-tou)
- [Google-federatie](https://docs.microsoft.com/azure/active-directory/b2b/google-federation)

### <a name="group-policies--information-protection"></a><a name="group-policies--information-protection"></a>Groepsbeleid & informatiebeveiliging
Microsoft 365-groepen is gebouwd op de geavanceerde beveiligings- en nalevingsmogelijkheden van Microsoft 365 en ondersteunt classificaties, auditing en rapportage, het zoeken naar compliance-inhoud, e-discovery, Legal Hold en retentiebeleid.
>[!Tip]
>- Configureer classificaties, gebruiksrichtlijnen en labels die zijn afgestemd op de behoeften van uw organisatie.
>- Bewaarbeleid kan onafhankelijk van labels worden gedefinieerd.
>- Activiteiten van auditgroepen: maken, verwijderen, enz.
>- Beheer de groepsprivacy en de toegang tot gasten op basis van classificatie.

|         |         |         |
|---------|---------|---------|
|![afbeelding desc](../../media/decision_point.png)|Beslissingspunten|<ul><li>Heeft uw organisatie specifieke gebruiksvereisten die aan alle gebruikers moeten worden gecommuniceerd?</li><li>Heeft uw organisatie de classificaties van alle inhoud nodig?</li><li>Vereist uw organisatie dat inhoud gedurende een bepaalde periode wordt bewaard?</li><li>Vereist uw organisatie specifieke beleid voor het bewaren van gegevens op groepen?</li><li>Verwacht uw organisatie de mogelijkheid te vereisen om inactieve groepen te archiveren om de inhoud te behouden?</li><li>Hebben groepsmakers de mogelijkheid nodig om organisatiespecifieke classificaties aan teams toe te wijzen?</li></ul>|
|![afbeelding desc](../../media/next_steps.png)|Volgende stappen|<ul><li>De gebruiksrichtlijnen van uw organisatie voor groepen documenteren</li><li>Documenteer de vereisten van uw organisatie voor classificatie.</li><li>Bepaal het beleid dat moet worden afgedwongen op basis van de classificatie, bijvoorbeeld gevoeligheid, retentie, gasttoegang.</li><li>Definieer de gevoeligheidslabels voor uw organisatie en welke beveiligingsinstellingen u wilt toevoegen.</li><li>Definieer een labelbeleid om te bepalen welke gebruikers en groepen deze labels zien.</li><li>Configureer de [voorbeeldvoorbeeld van het gevoeligheidslabel Groepen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) en begin met het classificeren van de groepen in uw organisatie.</li><li>Plan om deze vereisten uit te voeren als onderdeel van de implementatie van uw groepen.</li></ul>|


#### <a name="resources"></a>*Resources*
- [Koppeling naar uw microsoft 365-richtlijnen voor groepen](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#link-to-your-office-365-groups-usage-guidelines)
- [Classificaties maken voor Office-groepen in uw organisatie](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)
- [Groepinstellingen configureren](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets)
- [Overzicht van het bewaarbeleid](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)
- [Overzicht van gevoeligheidslabels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)
- [Overzicht van labels](https://docs.microsoft.com/microsoft-365/compliance/labels)
- [Zoeken in het auditlogboek](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
- [Een legale blokkering op zijn plaats maken of verwijderen](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)
- [Een bewaarbeleid maken](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)
- [Een inhoudszoekopdracht uitvoeren in het Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/content-search)
- [Bulk maakt en publiceert bewaarlabels met PowerShell](https://docs.microsoft.com/microsoft-365/compliance/bulk-create-publish-labels-using-powershell)

### <a name="upgrade-traditional-collaboration-tools"></a><a name="upgrade-traditional-collaboration-tools"></a>Traditionele samenwerkingstools upgraden
Al jaren vertrouwen organisaties op distributiegroepen om te communiceren en samen te werken met groepen mensen, zowel binnen als buiten het bedrijf. Nu bieden Microsoft 365-groepen in Outlook echter een krachtigere oplossing voor samenwerking. Bovendien is het belangrijk om een Microsoft 365-groep aan te sluiten op een bestaande SharePoint-site als u die site wilt moderniseren.

>[!Tip]
>- Upgrade eenvoudig al uw in aanmerking komende distributielijsten in enkele seconden via het Exchange-beheercentrum of met PowerShell-cmdlets.
>- Bestaande SharePoint-teamsites verbinden met nieuwe Microsoft 365-groepen.

|         |         |         |
|---------|---------|---------|
|![afbeelding desc](../../media/decision_point.png)|Beslissingspunten|<ul><li>Heeft uw organisatie distributielijsten die [niet in aanmerking komen](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists#how-do-i-check-which-dls-are-eligible-for-upgrade) voor een upgrade?<li>Bepaal naar welk type groep de distributielijst het best gemigreerd is.</li></ul>|
|![afbeelding desc](../../media/next_steps.png)|Volgende stappen|<ul><li>Bepaal welke distributielijsten kandidaten zijn voor een upgrade naar Microsoft 365-groepen.</li><li>Analyseer uw bestaande SharePoint-teamsites om te zien welke sites klaar zijn om te worden verbonden.</li><li>Laat andere teams in uw bedrijf weten dat u uw distributiegroep hebt geüpgraded en welke stappen u hebt genomen om het succesvol te maken!</li></ul>|


#### <a name="resources"></a>*Resources*
- [Distributielijsten (DL) upgraden naar groepen in Outlook](https://aka.ms/whyupgradedls)
- Upgrade met één klik via Exchange-beheercentrum of via [PowerShell-scripts](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists)
- [Distributielijsten migreren naar Microsoft 365-groepen - Help voor beheerders](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)
- [Bestaande SharePoint-sites verbinden met Microsoft 365-groepen:](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group)
- [De scannergegevens analyseren en gebruiken](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group-scanner)
- [SharePoint-moderniseringsscanner](https://github.com/SharePoint/sp-dev-modernization/tree/master/Tools/SharePoint.Modernization) (een hulpmiddel op GitHub)

### <a name="groups-reporting"></a><a name="groups-reporting"></a>Groepsrapportage
Het dashboard Microsoft 365-rapporten toont u het activiteitenoverzicht voor de Microsoft-producten in uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product.
> [!TIP]
>- U de rapporten Groepen gebruiken om inzicht te krijgen in de activiteit van Microsoft 365-groepen in uw organisatie en te zien hoeveel groepen er worden gemaakt en gebruikt.
>-Het rapport Microsoft 365-groepen kan worden bekeken voor trends in de afgelopen 7 dagen, 30 dagen, 90 dagen of 180 dagen.
>- Houd groepsactiviteiten in groepspostvakgesprekken, groepssite/bestandenactiviteit, details rond groepslidmaatschap, inclusief externe ledentellingen, in de gaten.
>- Controleer regelmatig om groepseigenaren van actieve groepen te bereiken om use cases te leren en deze intern te versterken.
>- Maak gebruik van Power BI-contentpakketten voor aanvullende inzichten.


|         |         |         |
|---------|---------|---------|
|![afbeelding desc](../../media/decision_point.png)|Beslissingspunten|<ul><li>Heeft uw organisatie regelmatig rapporten nodig om inzicht te krijgen in het gebruik van Microsoft 365-groepen?<li>Vereist uw organisatie rapportage over alle groepen met externe leden?</li></ul>|
|![afbeelding desc](../../media/next_steps.png)|Volgende stappen|<ul><li>Documenteer de vereisten van uw organisatie voor het regelmatig controleren van activiteitenrapporten van groepen.</li></ul>|


#### <a name="resources"></a>*Resources*
- [Microsoft 365-overzichten in het beheercentrum](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)
- [Office 365-inhoudspakket voor adoptie](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics)
- [Azure AD-inhoudspakket](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-power-bi-content-pack-how-to)
- [Microsoft Graph-activiteits-API](https://developer.microsoft.com/graph/docs/api-reference/v1.0/resources/office_365_groups_activity_reports)
- [Rapport Microsoft 365-groepen (uniforme groepen)](https://gallery.technet.microsoft.com/office/Office-365-Groups-Report-7e3e161b)
- [Rapporten over controleactiviteit in de Azure Active Directory-portal](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-audit-logs)
- [Microsoft Graph - Deltaquery gebruiken om wijzigingen bij te houden](https://docs.microsoft.com/graph/delta-query-overview)

## <a name="getting-started-based-on-your-cloud-adoption-journey"></a>Aan de slag op basis van uw cloudadoptietraject

Microsoft 365 Groups biedt een uitgebreide set governancemogelijkheden die uw organisatie mogelijk nodig heeft. Beschouw de volgende organisatieprofielen als leidraad om best practices te begrijpen, de juiste vragen te stellen om de vereisten voor governance te bepalen en hoe u daaraan voldoen.

**Houd rekening met de volgende organisatieprofielen:**
- Kleine bedrijven
- Middelgrote bedrijven
- Gereglementeerd of onderneming

### <a name="small-business"></a>Kleine bedrijven
Overweeg een organisatie die Microsoft 365 heeft geïmplementeerd met ten minste Exchange Online- en SharePoint Online-licenties die de Business Essentials- en Business Premium-abonnementen bevatten, en de Enterprise E1-, E3- en E5-abonnementen zonder Azure Active Director Premium-licenties.

| Fase | Beschrijving |
| --------------- | ------------------------------------------------------------ |
| Begeleiding |<ul><li>Overweeg een selfservice provisioning model.</li><li> Groepen in Outlook & SharePoint-sites zijn [standaard privé](https://techcommunity.microsoft.com/t5/Office-365-Groups/Groups-in-Outlook-and-Group-connected-team-sites-are-now-private/m-p/186395).</li><li> Groepen kunnen worden gemaakt door bestaande distributielijsten (DLs) één voor één of in bulk te upgraden via PowerShell. Zie [Distributielijsten voor upgrades naar Microsoft 365-groepen](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists).</li><li> Gasttoegang inschakelen, maar beheers het gebruik van gastdomeinen toestaan/blokkeren.</li><li> Gebruik groepsrapportage om inzicht te krijgen in hoe gebruikers groepen gebruiken.</li><li> Overweeg om een team voor microsoft Teams-team voor een hele organisatie op te maken als een manier voor iedereen om deel uit te maken van één team voor samenwerking. </li></ul>|
| Volgende stappen      |<ul><li>Overweeg [siteontwerpen en sitescripts](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview) te gebruiken om het standaardontwerp voor besturingselementen te definiëren met behulp van de acties die zijn gedefinieerd in de referentie van het [JSON-schema](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema).</li><li>[Beoordelingsgroepen die rapporteren](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups).</li><li>Houd het totaal aantal groepen en inactieve/actieve groepen bij.</li><li>Bijhouden van zowel Exchange- als SharePoint-opslag.</li><li>Groepsactiviteit weergeven in groepspostvakgesprekken, groepssite/bestandenactiviteit, enz.</li></ul> |

### <a name="medium-sized-business"></a>Middelgrote bedrijven
Naast de bovenstaande aanbevelingen moet u rekening houden met het volgende voor middelgrote bedrijven die Microsoft 365 hebben geïmplementeerd met ten minste een Enterprise E3/E5 met Azure Active Directory Premium P1-licenties.

| Fase | Beschrijving |
| --------------- | ------------------------------------------------------------ |
| Begeleiding |<ul><li>Bepaal een open of IT-geleid inrichtingsmodel.</li><li> Overweeg bepaalde groepen te maken die zijn gekoppeld aan [dynamische lidmaatschapsregels](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) op basis van Azure AD-kenmerken zoals Afdeling</li><li> Definieer classificaties binnen uw organisatie bijvoorbeeld, Zeer vertrouwelijk, Vertrouwelijk (standaard), Algemeen.</li><li>  Definieer het beleid op basis van classificatie, zoals retentie en gevoeligheid.</li><li> SharePoint is de inhoudsservice voor elke Microsoft 365-groep. Overweeg [sharepoint online-sites](https://docs.microsoft.com/office365/enterprise/deploy-sharepoint-online-sites-for-three-tiers-of-protection) te ontwerpen en te implementeren voor drie beveiligingsniveaus (basislijn, gevoelige en zeer vertrouwelijke). Zie Sites en bestanden beveiligen van [SharePoint Online voor](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)meer informatie over deze drie beveiligingsniveaus.</li><li> Zowel openbare als private groepen worden standaard in de GAL vermeld. Bepaal welke groepen u wilt weergeven in de specifiek GAL-groepen die buiten Microsoft Teams zijn gemaakt.  Gebruik de cmdlet 'HiddenFromAddressListsEnabled' van de [set-UnifiedGroup-cmdlet](https://technet.microsoft.com/library/mt238274(v=exchg.160).aspx) om specifieke groepen te verbergen.</li></ul> |
| Volgende stappen      |<ul><li>Definieer [gebruiksrichtlijnen](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets) om uw gebruikers te informeren over aanbevolen procedures die hun groepen effectief houden en hen informeren over intern inhoudsbeleid. Bijvoorbeeld het begrijpen van classificaties, beleid en procedures. </li><li>Definieer de levenscyclusperiode van de groep waarin groepen moeten worden verlengd of die moeten worden verwijderd - het verloopbeleid.</li><li>Overweeg de volgende aangepaste taken te maken om beleid uit te voeren op basis van classificaties.</li><li>Stel Privacy in op Privé.</li><li>Extern lidmaatschap/delen uitschakelen. </li><li>E-mails om groepsleden op de hoogte te stellen van groepen [zonder eigenaar.](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)</li><li>Afdwingen eigendomsbeleid (min. 2 eigenaren).</li><li> Definieer bewaarbeleid voor groepen op basis van classificatie. </li><li>Overzicht van het bewaarbeleid.</li><li>Powershell gebruiken om groepen te identificeren met een classificatie en [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy?view=exchange-ps).</li><li>Overweeg siteontwerpen en sitescripts te gebruiken om de besturingselementen te definiëren met behulp van de acties die zijn gedefinieerd in de referentie van het [JSON-schema](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema).</li><li>Overweeg [een eenvoudige sitemap te](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-trigger-flow-tutorial) maken met behulp van een siteontwerp en Microsoft Flow. Wanneer een site wordt gemaakt met behulp van deze site ontwerp, details van de site worden vastgelegd en geschreven naar een lijst. </li></ul>|

### <a name="regulated-or-enterprise"></a>Gereglementeerd of onderneming
Naast de bovenstaande aanbevelingen wordt rekening gehouden met de volgende gegevens voor sterk gereguleerde of grote enter-prises zoals de overheid, financiële services of gezondheidszorg die Office 365 heeft geïmplementeerd met ten minste een Enterprise E3/E5 met Azure Active Directory Premium P1/P2-licenties.

| Fase | Beschrijving |
| --------------- | ------------------------------------------------------------ |
| Begeleiding |<ul><li> Definieer beleid voor gegevensbeheer van de SharePoint-site die aan de groep is gekoppeld op basis van classificatie.</li><li>[SharePoint Online-bestanden beveiligen met labels en DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</li><li>[SharePoint Online-bestanden beveiligen met Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</li><li> Groepsite ingericht in regio's die zijn gekoppeld aan de voorkeursgegevenslocatie[(multi-geo)](https://docs.microsoft.com/office365/enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-office-365)van de gebruiker.</li><li> Lidmaatschapsbeoordelingen voor groepen met externe leden[(toegangsbeoordelingen).](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-access-reviews-overview)</li><li>Zorg ervoor dat werknemers of gastgebruikers relevante disclaimers zien voor wettelijke of nalevingsvereisten voordat ze toegang krijgen. ([gebruiksvoorwaarden](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou)).</li><li>Identificeer en rapporteer over Microsoft 365-groepen met een bepaalde [classificatie die ook externe gebruikers hebben.](https://techcommunity.microsoft.com/t5/Office-365-Groups/Sample-Powershell-to-identify-groups-with-HBI-classification-and/m-p/215561)</li><li>Geheime groepen waar lidmaatschappen moesten worden verborgen, moeten worden gemaakt met behulp van de cmdlet [New-UnifiedGroup](https://technet.microsoft.com/library/mt219359(v=exchg.160).aspx) (met behulp van de switch HiddenGroup-MembershipEnabled) bij groepscreatie.</li><li>Definieer de [gevoeligheidslabels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) voor de organisatie om de [toegang tot inhoud te beperken met behulp van versleuteling](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) en publiceer naar specifieke Microsoft 365-groepen.</li><li>Voorkom dat gevoelige inhoud uw organisatie verlaat op apparaten waarop Windows wordt uitgevoerd met [gevoeligheidslabels met Windows Information Protection](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553). |
| Volgende stappen      | <ul><li> Gebruik siteontwerp- en sitescripts om de [standaardacties](https://developer.microsoft.com/office/blogs/site-scripts-site-designs-summer-2018-update/) te definiëren die plaatsvinden wanneer een nieuwe site wordt gemaakt. Configureer bijvoorbeeld [de instelling voor extern delen](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-apply-external-sharing-setting) of [activeer een Microsoft Flow om een Azure-functie aan te roepen](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-azure-function) om configuraties toe te passen die niet native worden ondersteund. </li><li> Documentvereisten voor [SharePoint Online-bestanden met labels en DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) beveiligen voor sites die zijn gekoppeld aan Microsoft 365-groepen.</li><li>Vereisten voor documentorganisatie voor [Secure SharePoint Online-sites en -bestanden](https://docs.microsoft.com/microsoft-365/security/office-365-security/secure-sharepoint-online-sites-and-files) die zijn verbonden met Microsoft 365-groepen. </li><li>Vereisten voor documentorganisatie voor het publiceren [van gevoeligheidslabels](hhttps://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) voor specifieke gebruikers of groepen om inhoud te beschermen.</li></ul> |

## <a name="groups-management-capability-planning-checklist"></a>Checklist voor de planning van groepsbeheermogelijkheden

Een aantal groepsgerelateerde besturingselementen kan worden beheerd via Azure Active Directory. Zie [Azure Active Directory-cmdlets voor het configureren van groepsinstellingen voor het configureren van groepsinstellingen voor](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)meer informatie over het configureren van groepsinstellingen.

Gebruik de volgende tabel om te bepalen welke mogelijkheden u nodig hebt om de vereisten van uw organisaties te implementeren. Het zal u helpen bepalen welke licenties u nodig hebt, zodat u vooruit plannen.

| **Vermogen**      | **Details**                                    | **Azure AD Premium-licentie vereist** | **Besluit** |
| ------------------- | ---------------------------------------------- | ------------------------------------- | ------------ |
| Beleid voor groepsnaamgeving | Gebruik op basis van voorvoegselgebaseerde, aangepaste geblokkeerde woorden. | P1                                    |      Tbd     |
| Groepsclassificatie | Classificaties toewijzen aan teams. | P1                                    |   Tbd        |
| Toegang tot groepsgasten | Laat of voorkom dat gasten aan groepen worden toegevoegd. | Nee                                    |  Tbd        |
| Groepscreatie | Beperk het maken van teams tot beheerders. | Nee                                    |   Tbd        |
| Groepscreatie | Beperk het maken van teams tot leden van de beveiligingsgroep. | P1                                    |     Tbd      |
| Richtlijnen voor groepsgebruik | Stel een koppeling in met de richtlijnen voor groepsgebruik die zichtbaar zijn op alle eindpunten voor groepscreatie. | P1                                    |   Tbd        |
| Verborgen lidmaatschap | De leden van de Microsoft 365-groep verbergen voor gebruikers die geen lid zijn van de groep | Nee                                    |   Tbd        |
| Expiratiebeleid | Beheer de levenscyclus van Microsoft 365-groepen door een vervaldatumbeleid in te stellen. | P1                                    |  Tbd        |
| Activiteitenrapporten groeperen | Krijg inzicht in de activiteit van Microsoft 365-groepen in uw organisatie en bekijk hoeveel Microsoft 365-groepen worden gemaakt en gebruikt. | Nee                                    |    Tbd       |
| Bewaarbeleid | Gegevens bewaren of verwijderen voor een bepaalde periode door bewaarbeleid in te stellen voor Microsoft 365-groepen in het Security & Compliance Center. **Let op:** Voor het gebruik van deze functie is een licentie voor Office 365 Enterprise E3 of hoger vereist. | Nee                                    |    Tbd       |
| Preventiebeleid voor gegevensverlies | Identificeer gevoelige informatie op verbonden sites van Microsoft 365 en voorkom het per ongeluk delen. **Let op:** Voor het gebruik van deze functie is een licentie voor Office 365 Enterprise E3 of hoger vereist. | Nee                                    |     Tbd      |
| Archiveren en herstellen | Archiveer een team wanneer het niet meer actief is, maar u wilt het bewaren voor referentie of om in de toekomst opnieuw te activeren. | Nee                                    |   Tbd        |
| Toegangsbeoordelingen | Beoordelingen uitvoeren om groepslidmaatschappen efficiënt te beheren voor zowel interne als gastgebruikers | P2                                    |   Tbd       |
| Gebruiksvoorwaarden | Een eenvoudige methode die organisaties kunnen gebruiken om informatie aan eindgebruikers te presenteren. Deze presentatie zorgt ervoor dat gebruikers relevante disclaimers zien voor wettelijke of nalevingsvereisten. | P1                                    |         Tbd  |

