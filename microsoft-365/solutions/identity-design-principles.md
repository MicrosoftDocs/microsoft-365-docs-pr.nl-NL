---
title: 'Om de identiteit en verder te leren lopen: één gezichtspunt van een architect'
description: Beschrijving.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 427d266ea46c184a87b8b0b4fbe242adfb8deff1
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597541"
---
# <a name="to-identity-and-beyond--one-architects-viewpoint"></a>Om de identiteit en verder te leren lopen: één gezichtspunt van een architect

In dit artikel wordt [Alex Shteynberg](https://www.linkedin.com/in/alex-shteynberg/), de belangrijkste technische architect van Microsoft, besproken de beste ontwerp strategieën voor Enterprise-organisaties die microsoft 365 en andere Microsoft-cloudservices aannemen.

## <a name="about-the-author"></a>Info over de auteur

![Alex Shteynberg foto](../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg)

Ik ben een hoofd technische architect op het [Microsoft-technologie centrum](https://www.microsoft.com/mtc?rtc=1)van New York. Ik werk meestal met grote klanten en ingewikkelde vereisten. Mijn standpunten en meningen zijn gebaseerd op deze interacties en zijn mogelijk niet van toepassing op elke situatie. Maar als we klanten kunnen helpen met de meest ingewikkelde uitdagingen, kunnen we in het programma van mijn ervaring onze klanten helpen. 

Ik gebruik meestal elk jaar met 100 + klanten. Hoewel elke organisatie unieke kenmerken heeft, is het interessant om trends en commonalities te zien. Eén trend voor een groot aantal klanten is bijvoorbeeld de belangen van de sector. Na alles kan een bankfiliaal ook een horeca winkel en een communautair centrum zijn. 

In mijn rol ben ik geconcentreerd op het helpen van klanten tegen de beste technische oplossing, zodat ze hun unieke serie zakelijke doelstellingen kunnen adresseren. Officieel, ik richt op identiteit, beveiliging, privacy en compliance. Ik ben gek op dit raak alles. Het maakt niet uit of u bij de meeste projecten kunt zorgen. Dit houdt me te veel bezet en profiteert van deze rol. 

Ik woont in New York City (de beste!) en is nu zeer geschikt voor de diversiteit van zijn cultuur, voedsel en personen (niet verkeer). Ik ben geweldig als ik en hopelijk de wereld van de wereld in mijn leven kan zien. Ik zoek momenteel een reis naar Afrika voor meer informatie over wild.

## <a name="guiding-principles"></a>Verrichtings principes 

- **Eenvoudig** : u kunt (bijna) overal met technologie werken. Het maakt niet uit. Met name in de ruimte voor beveiliging zijn veel klanten van functie oplossingen. Deze [video](https://www.youtube.com/watch?v=SOQgABDSYZE) bevindt zich nu in de vergadering van Google Stripe om dit punt te onderstrepen.
- **Personen, proces, technologie** - [ontwerp voor mensen](https://en.wikipedia.org/wiki/Human-centered_design) om proces te verbeteren, niet eerst te techen. Er zijn geen ' perfecte ' oplossingen. We moeten diverse risicofactoren en besluiten voor elk bedrijf verschillend verdelen. Te veel klanten ontwikkelen een benadering die hun gebruikers later vermijden.
- **Richt u eerst op ' waarom ', en ' hoe later** ' het vervelende 7 jaar oud is met miljoenen vragen. We kunnen niet aan het juiste antwoord beantwoorden, en we weten niet de juiste vragen om te vragen. Veel klanten maken hypothesen op de manier waarop zaken moeten werken in plaats van het zakelijke probleem te definiëren. Er zijn altijd meerdere paden die kunnen worden gemaakt.
- **Lange staart van nabest practices** : u weet dat de aanbevolen procedures van invloed zijn op de lichtsnelheid. Als u Azure AD langer dan drie maanden geleden hebt bekeken, bent u waarschijnlijk niet op de hoogte. Alles wat u hier kunt wijzigen, is afhankelijk van de publicatie. De optie ' beste ' mag momenteel niet gelijk zijn aan zes maanden.

## <a name="baseline-concepts"></a>Basisbeginselen voor basisbeginselen

Sla deze sectie niet over. Ik weet vaak dat ik moet overstappen op deze onderwerpen, zelfs voor klanten die cloudservices voor jaren gebruiken.
Alas, taal is geen nauwkeurig programma. We gebruiken vaak hetzelfde woord om verschillende concepten of andere woorden te gebruiken om hetzelfde concept te betekenen. Ik gebruik dit onderstaande diagram vaak om een aantal terminologie van de basislijn en hiërarchiemodel te maken.
<br><br>

![Afbeelding van een Tenant, abonnement, service en gegevens](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)  

<br>

Wanneer u meer weet over zwemmen, is het beter om te beginnen in de groep en niet in het midden van de Oceaan. Ik wil niet technisch nauwkeurig met dit diagram proberen. Het is een model voor de bespreking van enkele basisconcepten. 

In het diagram:
- Tenant = een exemplaar van Azure AD. Het bevindt zich boven aan een hiërarchie of niveau 1 in het diagram. We kunnen dit als '[boundary](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-directory-independence)' beschouwen, waar alle andere zaken plaatsvinden ([Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) ). Alle Microsoft Enterprise Cloud-Services maken deel uit van een van deze tenants. Consumenten Services zijn apart. ' Tenant ' wordt weergegeven in de documentatie als Office 365-Tenant, Azure-Tenant, WVD-Tenant, etc. Dit kan vaak leiden tot verwarring voor klanten.
- Services/abonnementen, niveau 2 in het diagram, behoren tot één Tenant en maar één Tenant. De meeste SaaS-Services zijn 1:1 en kunnen niet worden verplaatst zonder migratie. Azure is verschillend, u kunt [facturering](https://docs.microsoft.com/azure/cost-management-billing/manage/billing-subscription-transfer) en/of een [abonnement](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) naar een andere Tenant verplaatsen. Er zijn veel klanten die Azure-abonnementen moeten overzetten. Dit heeft verschillende implicaties. Objecten die zich buiten het abonnement bevinden (bijvoorbeeld het object RBAC en Azure AD, waaronder groepen, apps, beleidsregels, enzovoort), worden niet verplaatst. Ook kunnen sommige services (Azure Key-kluis, gegevens bakstenen, etc.) in een niet-functionele status bewegen. Migreer geen services zonder een goede zakelijke behoefte. Sommige scripts die handig kunnen zijn voor migratie, worden [gedeeld op github](https://github.com/lwajswaj/azure-tenant-migration). 
- Een bepaalde service heeft meestal een deel van de rand van ' subniveau ' of niveau 3 (L3). Dit is handig als u wilt begrijpen voor de scheiding van beveiliging, beleidsregels, beheer, enzovoort. Er is helaas geen uniform naam waarvan ik bekend ben. Enkele voorbeelden van namen voor N3 zijn: Azure-abonnement = [resource](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resources-portal); Dynamics 365 CE = [exemplaar](https://docs.microsoft.com/dynamics365/admin/new-instance-management); Power BI = [werkruimte](https://docs.microsoft.com/power-bi/service-create-the-new-workspaces); Power apps = [omgeving](https://docs.microsoft.com/power-platform/admin/environments-overview); enzovoort.
- Niveau 4 is de plek waar de werkelijke gegevens zich bebereiken. Dit ' gegevens vlak ' is een complex onderwerp. Sommige services gebruiken Azure AD voor RBAC, anderen zijn niet. Ik bespreek het een beetje wanneer we de delegatie-onderwerpen raadplegen.

Voor enkele extra concepten die ik zoek naar veel klanten (en Microsoft-werknemers) is het niet mogelijk om het volgende te doen:


- Iedereen kan een groot aantal tenants tegen [geen kosten](https://azure.microsoft.com/pricing/details/active-directory/) [maken](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) . U hebt geen service nodig binnen de dienst. Ik heb tientallen. Elke Tenant naam is uniek in de wereldwijde cloudservice van Microsoft (dat wil zeggen dat u de naam van de ene tenants niet hoeft te hebben). Ze hebben allemaal een indeling van TenantName.onmicrosoft.com. Er zijn ook processen die automatisch tenants maken (niet-[beheerde tenants](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup)). Dit kan bijvoorbeeld gebeuren wanneer een gebruiker zich registreert voor een Enterprise-service met een e-mail domein dat niet voorkomt in een andere Tenant. 
- U kunt in een beheerde Tenant veel [DNS-domeinen](https://docs.microsoft.com/azure/active-directory/fundamentals/add-custom-domain) registreren. De oorspronkelijke naam van de Tenant wordt niet gewijzigd. U kunt op dit moment geen eenvoudige manier de naam van een Tenant wijzigen (anders dan migratie). Hoewel de naam van de Tenant technisch niet van belang is, is het mogelijk dat de naam van de Tenant moeilijk te beperken is.
- U moet de naam van een Tenant voor uw organisatie verkoopprijsnen, ook als u nog geen services plant. U kunt er ook voor zorgen dat iemand de naam van u kan overnemen en dat u geen eenvoudige procedure hoeft te maken (hetzelfde probleem als DNS-namen). Ik hoor te vaak van klanten. De naam van de Tenant moet ook een discussieonderwerp zijn.
- Als u eigenaar bent van de DNS-naamruimte (s), moet u deze allemaal toevoegen aan uw Tenant (s). U kunt er ook voor zorgen dat een niet- [beheerde Tenant](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup) met deze naam kan worden [beheerd](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover).
- DNS-naamruimte (bijvoorbeeld contoso.com) kan lid zijn van een en slechts één Tenant. Dit heeft gevolgen voor verschillende scenario's (bijvoorbeeld voor het delen van een e-mail domein tijdens een fusie of verwerving, etc.) U kunt een DNS-sub, bijvoorbeeld div.contoso.com) registreren in een andere Tenant, maar dat moet worden vermeden. Als u de domeinnaam op het hoogste niveau registreert, worden alle subdomeinen ervan uitgekeerd dat ze deel uitmaken van dezelfde Tenant. In scenario's met meerdere tenants (zie hieronder) wordt u geadviseerd gebruik te maken van een andere topniveaudomein naam, bijvoorbeeld contoso.ch of ch-contoso.com.
- Wie moet een Tenant ' eigenaar ' zijn? Ik zie vaak klanten die niet weten welke persoon de Tenant is van die persoon. Dit is een grote rode vlag. Neem contact op met Microsoft ondersteuning ZSM. Als het probleem zich voordoet als een service-eigenaar (vaak een Exchange-beheerder) is aangewezen voor het beheren van een Tenant. De Tenant bevat alle services die u in de toekomst mogelijk wilt hebben. De eigenaar van de Tenant moet een groep zijn die een beslissing kan nemen voor de activering van alle cloudservices in een organisatie. Een ander probleem treedt op wanneer een Tenant-eigenaar groep alle services moet beheren. Dit wordt niet schaal voor grote organisaties.
- Er is geen concept van een sub/Super-Tenant. Om een of andere reden blijft deze Myth zichzelf herhalen. Dit geldt ook voor [Azure AD B2C](https://docs.microsoft.com/azure/active-directory-b2c/) -tenants. Ik hoor te veel tijd ' mijn B2C-omgeving bevindt zich in mijn XYZ-Tenant ' of ' hoe verplaats ik mijn Azure-Tenant naar mijn Office 365-Tenant? '
- Dit document bevat vooral de nadruk op de commerciële wereldwijde wolk, aangezien dit de meeste klanten gebruiken. Het is soms handig om te weten over [soevereine wolken](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud). Soevereine wolken hebben aanvullende gevolgen voor het bespreken van deze discussie.


## <a name="baseline-identity-topics"></a>Onderwerpen over de basislijn

Er is veel meer informatie over het identiteits platform van Microsoft-Azure Active Directory (Azure AD). Voor personen die net beginnen, voelt het vaak overweldigd. Ook als u hier meer informatie over maakt, is het raadzaam de constante innovatie te beschermen en te wijzigen. In de interacties van mijn klant vind ik vaak mijzelf als ' vertaler ' tussen zakelijke doelstellingen en ' goede, betere en beste manieren om te zoeken naar deze onderwerpen (en over de Cliff-notities. Er is geen perfecte oplossing en het ' recht ' beslissing is een saldo van diverse risicofactoren. Hieronder vindt u enkele veelvoorkomende vragen en verwarring gebieden die ik vaak met klanten wil bespreken.

### <a name="provisioning"></a>Inrichtings
Azure AD biedt geen oplossing voor het ontbreken van beheer van uw identiteit wereld. [Identiteits](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) beheer moet een essentieel element zijn, onafhankelijk van eventuele Cloud beslissingen. De vereisten voor het beheer van het beheer van de periode waarin dit een programma is en geen hulpmiddel. 

[Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect) versus [Microsoft Identity Manager](https://docs.microsoft.com/microsoft-identity-manager/microsoft-identity-manager-2016) (MIM) versus. iets anders (derden of aangepast)? Bespaar nu en in de toekomst en ga verder met Azure AD Connect. Dit hulpmiddel bevat allerlei soorten smarters waarmee u op de gangbare klant configuraties en voortdurend vernieuwingen kunt vinden. 

Sommige grenzen met een enkele rand die schijven kunnen betreffen met een complexere architectuur:
- Ik heb meerdere advertenties zonder netwerkverbinding. Er is een nieuwe optie genaamd [Cloud inrichting](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning).
- Ik heb geen Active Directory, en ik wil deze niet installeren. Azure AD Connect kan worden geconfigureerd voor [synchronisatie van LDAP](https://docs.microsoft.com/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) (partner is vereist).
- Ik moet dezelfde objecten inrichten voor meerdere tenants. Dit wordt niet technisch ondersteund, maar is afhankelijk van de definitie van ' zelfde '.

Moet ik standaardsynchronisatie regels aanpassen ([objecten filteren](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering), [kenmerken wijzigen](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized), [alternatieve aanmeldings-id](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-userprincipalname), enzovoort)? Voorkomen! Een identiteits platform is alleen waardevol als de services die dit gebruiken. U kunt alle soorten Nutty-configuraties doen om deze vraag te beantwoorden, maar u moet de gevolgen voor de toepassingen bekijken. Als u objecten met een e-mail filtert, is de GAL voor Online Services onvolledig. Als de toepassing gebruikmaakt van specifieke kenmerken, kan het filteren hiervan geen gevolgen hebben voor het onvoorspelbare effect. enzovoort. Het is geen beslissing van een identiteits team.

XYZ SaaS ondersteunt ondersteuning voor Just-in-time (JIT), waarom wordt u gevraagd om te synchroniseren? Zie het bovenstaande. Veel toepassingen willen informatie over de functionaliteit van een profiel. U kunt geen GAL hebben als alle objecten met e-mail beschikbaar zijn. Dit geldt ook voor [Gebruikers inrichten](https://docs.microsoft.com/azure/active-directory/app-provisioning/user-provisioning) in toepassingen die zijn geïntegreerd met Azure AD.


### <a name="authentication"></a>Verificatie

[Wachtwoord hash-synchronisatie](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) (PHS) en. [Pass Through-verificatie](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) (PTA) versus [Federatie](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility).

Meestal is er een hart ligt- [debat](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) rond Federatie. Eenvoudiger en daarom is het gemakkelijker om PHS te gebruiken, tenzij u een goede reden hebt. U kunt ook verschillende verificatiemethoden configureren voor verschillende DNS-domeinen in dezelfde Tenant. 

Sommige klanten activeren Federatie + PHS hoofdzakelijk voor:
- Een optie om [terug te vallen](https://docs.microsoft.com/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) (voor herstel na noodgevallen) als de Federation service niet beschikbaar is.
- Extra mogelijkheden (ex.: [Azure AD DS](https://docs.microsoft.com/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)) en beveiligingsservices (ex.: [gelekte referenties](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials))
- Ondersteuning voor services in azure waarbij geen federatieve verificatie (ex.: Azure- [bestanden](https://docs.microsoft.com/azure/storage/files/storage-files-active-directory-overview)) wordt uitgelegd.

Ik vervaak klanten via clientverificatie stroom om enkele veelvoorkomende concepten te verduidelijken. Het resultaat lijkt op de onderstaande afbeelding, wat niet de goede manier is om daar de afbeelding te zien.


![Voorbeeld van een whiteboard-discussie](../media/solutions-architecture-center/identity-beyond-whiteboard-example.png)

Dit type whiteboard-tekening laat zien waar beveiligingsbeleid in de stroom van een authenticatieaanvraag wordt toegepast. In dit voorbeeld worden de beleidsregels die worden afgedwongen via Active Directory Federation service (AD FS) op de eerste serviceaanvraag toegepast, maar niet volgende serviceaanvragen. Dit is minimaal één reden om beveiligings besturing zo veel mogelijk te verplaatsen naar de Cloud.

We hebben Chasing de dromen van [eenmalige aanmelding](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) (SSO) voor wat u kunt onthouden. Sommige klanten geloven dat ze dit kunnen bereiken door de STS-provider (' rechts ' Federatie) te kiezen. Azure AD kan u helpen om [eenmalige SSO-functies in te schakelen](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-sso-deployment) , maar geen STS is magische. Er zijn te veel verouderde Authenticatiemethoden die nog voor kritieke toepassingen worden gebruikt. Azure AD verlengen met [Partneroplossingen](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) kan veel van deze scenario's bepakken. Eenmalige aanmelding is een strategie en een rit. U kunt geen [van de standaarden voor toepassingen](https://docs.microsoft.com/azure/active-directory/develop/v2-app-types)vinden zonder dat dit van toepassing is op de normen. Dit onderwerp is een rit met een [wacht woordloze](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless) verificatie die ook geen magische-antwoord heeft. 

[Multi-factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) [(MFA](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) ) is vandaag de essentieel. Toevoegen aan de [gebruikers werking van de gebruikers werking](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) en u hebt een oplossing waarmee u kunt voorkomen dat u vaak vaak Cyber-aanvallen kunt uitvoeren. Zelfs voor de consumenten dienst is MFA vereist. Daarom ben ik nog steeds bijeen met veel klanten die niet naar [moderne verificatie](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) methoden willen overstappen. Het grootste argument dat ik hoor, is van invloed op gebruikers en oudere toepassingen. Soms kunnen klanten met een goede weg helpen om on-Exchange Online- [wijzigingen](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282)door te gaan. Er zijn nu veel Azure AD- [rapporten](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) beschikbaar waarmee klanten met deze overgang kunnen werken.



### <a name="authorization"></a>Bevoegdheid

Per [Wikipedia](https://en.wikipedia.org/wiki/Authorization), ' om in te schrijven ', is een toegangsbeleid te definiëren. Veel mensen kijken naar de mogelijkheid om besturingselementen voor Access te definiëren voor een object (bestand, service, enzovoort). In de huidige wereld van een Cyber-Threat wordt dit concept snel tot een dynamisch beleid dat kan reageren op diverse bedreigings vectoren en snel besturingselementen voor Access in antwoord hierop aanpassen. Als ik mijn bankrekening via een ongebruikelijke locatie krijg, krijg ik dan extra bevestigings stappen. Om dit te kunnen doen, dient u niet alleen maar het beleid zelf te overwegen, maar de ecosysteme detectie-en signaal correlatie methoden.

De beleidsengine van Azure AD wordt geïmplementeerd met behulp van [beleidsregels voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview). Dit systeem hangt af van de informatie van diverse andere Threat Detection systemen om dynamische beslissingen te maken. Een eenvoudige weergave zou iets lijken op de volgende afbeelding.

![Beleidsengine in azure AD](../media/solutions-architecture-center/identity-and-beyond-illustration-3.png)

Als u al deze signalen combineert, wordt het volgende toegestaan voor dynamische beleidsregels:
- Als u op uw apparaat een bedreiging ontvangt, wordt uw toegang tot de gegevens beperkt tot de webversie, maar alleen de mogelijkheid om het bestand te downloaden.
- Als u een niet-vaak hoog deel van de gegevens downloadt, wordt alles wat u downloadt, versleuteld en beperkt.
- Als u een service van een niet-beheerd apparaat opent, wordt u geblokkeerd voor zeer gevoelige gegevens maar mag u geen toegang krijgen tot niet-beperkte gegevens zonder de mogelijkheid om het bestand naar een andere locatie te kopiëren.

Als u akkoord gaat met deze uitgebreide definitie van autorisatie, moet u extra oplossingen implementeren. Welke oplossingen u implementeert, hangt af van de manier waarop dynamische beleidsregels moeten worden verwerkt en welke bedreigingen u prioriteit wilt geven. Enkele voorbeelden van dergelijke systemen zijn:
- [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/) 
- [Azure Advanced Threat Protection](https://docs.microsoft.com/azure-advanced-threat-protection/) (Azure ATP)
- [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) (Microsoft Defender ATP)
- [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP)
- [Microsoft Cloud-app-beveiliging](https://docs.microsoft.com/cloud-app-security/) (MCAS)
- MTP ( [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide) )
- [Microsoft Intune](https://docs.microsoft.com/mem/intune/)
- [Microsoft Information Protection](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) (MIP)
- [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/) 

Naast Azure AD zijn verschillende services en toepassingen hun eigen afzonderlijke autorisatie modellen. Sommige van deze worden later besproken in de sectie overdracht.

### <a name="audit"></a>Oordeel
Azure AD bevat uitgebreide functies voor [audit en rapportage](https://docs.microsoft.com/azure/active-directory/reports-monitoring/) . Dit is echter meestal niet de enige broninformatie die nodig is voor het maken van beveiligings beslissingen. Meer discussie over dit onderwerp vindt u in de sectie overdracht.

## <a name="there-is-no-exchange"></a>Er is geen Exchange

Geen paniek! Dit betekent niet dat Exchange wordt afgeschaft (of SharePoint, etc.) Het is nog steeds een kern service. Wat ik voor u ben, gedurende enige tijd, zijn technologieaanbieders de gebruikerservaring (UX) voor onderdelen van meerdere services overgezet. In Microsoft 365 is een eenvoudig voorbeeld '[moderne bijlagen](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)' waarbij bijlagen met e-mailberichten worden opgeslagen in SharePoint Online of OneDrive voor bedrijven. 

![Een bestand als bijlage aan een e-mailbericht toevoegen](../media/solutions-architecture-center/modern-attachments.png)

Als u de Outlook-client bekijkt, ziet u een groot aantal services als onderdeel van deze ervaring, dus niet alleen Exchange. Dit omvat de groepen Azure AD, Microsoft Search, apps, profiel, compliance en Office 365 groepen. 

![Outlook-interface met bijschriften](../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png)

Lees meer over [Microsoft Hydraulic Framework](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) voor preview van aanstaande mogelijkheden. In de preview-versie kan ik team gesprekken rechtstreeks in Outlook lezen en beantwoorden. Eigenlijk is de [teams-client](https://products.office.com/microsoft-teams/download-app) een van de duidelijkere voorbeelden van deze strategie. 

In het algemeen is het moeilijker om een duidelijke lijn te trekken tussen Office 365 en andere services in Microsoft-wolken. Ik Bekijk het als een geweldig voordeel van klanten omdat ze een totaal van de innovatie van alles kunnen benutten. Tamelijk cool en heeft veel gevolgen voor veel klanten.

Op dit moment vinden de groepen klant IT gestructureerd rond ' producten '. Het is logisch voor een on-premises wereld, aangezien u een expert voor elk specifiek product nodig hebt. Ik hoef echter niet meer in een Active Directory-of Exchange-database te worden opgespoord wanneer deze services zijn verplaatst naar de Cloud. Automatisering (voor wat in de Cloud) worden bepaalde herhaalde handmatige taken verwijderd (wat is er gebeurd met factor). Deze worden echter vervangen door complexere voorwaarden om de cross-service interactie, impact, zakelijke behoeften, etc te begrijpen. Als u [meer wilt weten](https://docs.microsoft.com/learn/), zijn er goede verkoopkansen ingeschakeld via de Cloud-transformatie. Voordat u naar technologie gaat, communiceer ik vaak met klanten over het beheren van wijzigingen in IT-vaardigheden en team structuren.

Voor alle deelnemers aan de SharePoint-app, kunt u niet meer vragen ' Hoe kan ik XYZ in SharePoint Online? ' [Power Automatiseer](https://docs.microsoft.com/power-automate/) (aka-stroom) voor werkstroom gebruiken is een veel krachtig platform. Gebruik [Azure bot Framework](https://docs.microsoft.com/azure/bot-service/?view=azure-bot-service-4.0) om een betere UX voor de lijst met 500K-items te maken. Begin met [Microsoft Graph](https://developer.microsoft.com/graph/) in plaats van CSOM. [Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview) bevat SharePoint, maar ook nog een wereld. Er zijn nog enkele andere voorbeelden die kunnen worden weergegeven. Daar is er een groot en geweldig universum. Open de deur en kijk hoe u [gaat verkennen](https://docs.microsoft.com).

Het andere veelvoorkomende effect ligt in het gebied naleving. Deze cross-service aanpak lijkt veel op nalevings beleidsregels te verwarren. Ik blijf een organisatie met de status ' Ik wil alle e-mailberichten van een eDiscovery-systeem vastleggen '. Wat betekent dit eigenlijk als e-mail niet langer e-mail is, maar een venster in andere services? Office 365 biedt een uitgebreide aanpak voor [naleving](https://docs.microsoft.com/microsoft-365/compliance/), maar het wijzigen van personen en processen is vaak veel moeilijker dan de technologie.

Er zijn veel andere mensen en proces implicaties. Dit is een belangrijk en onderbesproken gebied in mijn mening. Misschien nog meer in een ander artikel.

## <a name="tenant-structure-options"></a>Opties voor Tenant structuur

### <a name="single-tenant-vs-multi-tenant"></a>Eén Tenant versus meerdere tenants

In het algemeen kunnen de meeste klanten slechts één productie Tenant hebben. Er zijn verschillende redenen waarom meerdere tenants moeilijk zijn (een [zoekopdracht voor Bing](https://www.bing.com/search?q=office%20365%20multiple%20tenants)) of dit [White Paper](https://aka.ms/multi-tenant-user)lezen. Tegelijkertijd kunnen veel ondernemings klanten met een andere (kleine) Tenant samenwerken, testen en experimenteren. Toegang tot Azure Azure Access wordt gemakkelijker gemaakt met [Azure Lighthouse](https://azure.microsoft.com/services/azure-lighthouse/). In Office 365 en vele andere SaaS-Services gelden beperkingen voor de cross-Tenant scenario's. U dient veel te overwegen in [Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) -scenario's.

Veel klanten beëindigen met meerdere productie tenants na een fusie en verwerving (M&A) en willen samenvoegen. Dat is nog niet eenvoudig en vereist Microsoft Consulting Services (MCS) of een partner plus software van derden. Er is een voortdurende technische oplossing voor het oplossen van diverse scenario's met klanten met meerdere tenants in de toekomst. 

Sommige klanten kiezen er met meer dan één Tenant. Dit is een zeer zorgvuldige beslissing en bijna altijd een goede bedrijfs reden. Enkele voorbeelden hiervan zijn:
- Een bedrijfsstructuur van het bedrijf waar geen gemakkelijke samenwerking tussen verschillende entiteiten is vereist, en er een zware administratieve en andere isolatie behoeften bestaan.
- Na een verwerving wordt een bedrijfsbeslissing gebracht, zodat er twee instanties apart worden gehouden.
- Simulatie van een omgeving van een klant die de productieomgeving van de klant niet wijzigt. 
- Ontwikkeling van software voor klanten.

In deze scenario's met meerdere tenants kunnen klanten vaak bepaalde configuraties voor de tenants wijzigen, of rapporteren over wijzigingen en drijfers van de configuratie. Dit betekent meestal dat de configuratie van handmatige wijzigingen als code overgaat. Microsoft Premiere Support biedt een workshop voor deze typen vereisten op basis van dit openbare IP-adres: [https://Microsoft365dsc.com](https://Microsoft365dsc.com) .


### <a name="multi-geo"></a>Meerdere geografische 

Naar [meerdere geografische](https://docs.microsoft.com/office365/enterprise/office-365-multi-geo) of niet naar meerdere geografische gebieden, dat wil zeggen de vraag. Met Office 365 multi-geo kunt u gegevens in de geo-locaties richten en bewaren die u hebt gekozen om te voldoen aan de vereisten voor [Data-woonplaats](https://docs.microsoft.com/office365/enterprise/o365-data-locations) . Er zijn veel mishaalbaarheiden voor deze functie. Houd het volgende in gedachten: 
- Het biedt geen prestatievoordelen. Dit kan de prestaties nadelig beïnvloeden als het [netwerkontwerp](https://aka.ms/office365networking) niet klopt. Zorg dat u de apparaten ' Sluit ' naar het Microsoft-netwerk verzorgt, niet noodzakelijkerwijs voor uw gegevens.
- Het is geen oplossing voor [AVG compliance](https://www.microsoft.com/trust-center/privacy/gdpr-overview). AVG is niet op de focus van gegevens soevereiniteit of opslaglocaties. Er zijn andere compliance frameworks.
- Het delegeren van de beheerder (zie hieronder) of [informatie barrières](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)wordt niet opgelost.
- Het is niet hetzelfde als een meervoudige Tenant en de werkstroom extra [inrichten van gebruikers](https:/docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) is vereist.
- [Uw Tenant](https://docs.microsoft.com/office365/enterprise/moving-data-to-new-datacenter-geos) (Azure AD) wordt niet verplaatst naar een andere geografie. 

## <a name="delegation-of-administration"></a>Delegatie van beheer

In de meeste grote organisaties is scheiding van rechten en toegangsbeheer op basis van rollen een vereiste werkelijkheid. Ik ga op de tijd voor onze excuses. Dat is zo eenvoudig als sommige klanten willen. Klant-, juridische, compliance-en andere vereisten zijn verschillend en treden soms overal ter wereld een conflict op. Eenvoud en flexibiliteit liggen vaak op tegenoverliggende kanten van elkaar. Ga niet mis, we kunnen op dit moment een betere taak doen. Er zijn (en) belangrijke verbeteringen in de loop van de tijd. Bezoek uw lokale [Microsoft-technologie centrum](https://www.microsoft.com/mtc) om het model te laten voldoen aan uw bedrijfsbehoeften, zonder 379230-documenten te lezen. Hier is het belangrijk dat u op de hoogte bent van wat u ervan moet opvolgen en waarom het dan ook is. Hieronder vindt u vijf verschillende gebieden waarop u kunt inplannen en enkele bekende vragen die ik heb vond.

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Azure AD en Microsoft 365-beheer centra

Er is een lang en toenemende lijst met [ingebouwde rollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Elke rol bestaat uit een lijst met rolmachtigingen gegroepeerd, zodat specifieke acties kunnen worden uitgevoerd. U vindt deze machtigingen in het tabblad ' Beschrijving ' binnen elke rol. U kunt ook een meer menselijke leesbare versie van deze personen zien in het Microsoft 365-Beheercentrum. De definities voor ingebouwde rollen kunnen niet worden gewijzigd. Ik Groepeer deze in drie categorieën:

- **Globale beheerder** : deze functie ' alles krachtig ' moet [zeer veilig](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) zijn, net zoals in andere systemen. Typische aanbevelingen zijn: geen permanente toewijzing en gebruik van Azure AD bevoorrechte Identity Management (PIM). sterke verificatie; enzovoort. Deze rol biedt u niet standaard toegang tot alles. Normaalgesproken wordt er verwarring weergegeven over nalevings toegang en Azure Access, dat later wordt besproken. Deze rol kan echter altijd toegang tot andere services toewijzen aan de Tenant. 
- **Specifieke servicebeheerders** : sommige services (Exchange, SharePoint, Power bi, etc.) verbruiken op hoog niveau van beheerdersrollen via Azure AD. Dit is niet consistent voor alle services en er worden later meer service-specifieke rollen besproken.
- **Functioneel** : er is een lange (en groeiende) lijst met rollen die zijn gericht aan specifieke bewerkingen (gast uitnodiging, enzovoort). Deze worden regelmatig toegevoegd, op basis van klantbehoeften.

Het is niet mogelijk om alles te delegeren (hoewel de leemte afneemt), wat betekent dat de rol van globale beheerder soms soms moet worden gebruikt. In plaats van personen lidmaatschap van deze rol, moet u als code en automatisering worden beschouwd.

**Opmerking**: het microsoft 365-Beheercentrum heeft een gebruiksvriendelijke interface, maar biedt een subset van mogelijkheden vergeleken met de Azure AD-beheer ervaring. Beide portals gebruiken dezelfde functies van Azure AD, zodat de wijzigingen op dezelfde plaats plaatsvinden. Tip: als u wilt dat er een beheerder is van de GEBRUIKERSINTERFACE met een identiteits beheerder zonder dat u alle Azure onbelangrijke e-mail hoeft te gebruiken [https://aad.portal.azure.com](https://aad.portal.azure.com) . 

Wat is de naam van de persoon? Maak geen hypothesen van de naam van de rol. Taal is geen zeer nauwkeurig gereedschap. Het doel is om bewerkingen te definiëren die moeten worden gedelegeerd voordat u kunt kijken welke rollen u nodig hebt. Wanneer u iemand toevoegt aan de rol van beveiligings lezer, worden de beveiligingsinstellingen voor alles niet weergegeven. 

De mogelijkheid om [aangepaste rollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/roles-custom-overview) te maken is een gemeenschappelijke vraag. Dit is beperkt in azure AD vandaag (zie hieronder), maar zal in de loop van de tijd toenemen. Ik denk dat ze van toepassing zijn op functies in azure AD en mogelijk niet het ' omlaag ' hiërarchiemodel (besproken hierboven). Wanneer ik een ' aangepast ' heb, ben ik kort terug naar de hoofd van ' simpel ' is beter.

Een andere algemene vraag is de mogelijkheid om rollen te bereiken bij een subset van een adreslijst. Een voorbeeld is een voorbeeld van de beheerders beheerder voor gebruikers in EU. Au ( [Administrative Unit](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-administrative-units) ) is bedoeld om dit op te lossen. Zoals hierboven, beschouw ik dit als die van toepassing is op functies in azure AD en mogelijk niet ' lager '. Bepaalde rollen maken uiteraard niet in bereik (globale beheerders, servicebeheerders, etc.)

Voor deze rollen is direct lidmaatschap (of dynamische toewijzing vereist als u [Azure AD PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/)gebruikt). Dat betekent dat klanten deze rechtstreeks in azure AD moeten beheren en dat niet kan worden gebaseerd op het lidmaatschap van een beveiligingsgroep. Ik ben geen waaier van het maken van scripts om deze te beheren, aangezien deze met verhoogde rechten moet worden uitgevoerd. Ik adviseer de API-integratie algemeen met proces systemen zoals ServiceNow of met behulp van partner beheerprogramma's, zoals Saviynt. Er is technische werkzaamheden aan te doen om dit in de loop van de tijd te verhelpen.

Ik heb een paar keer [Azure AD PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/) genoemd. Er is een bijbehorende pam-oplossing (Microsoft Identity Manager) voor [geprivilegieerde toegang tot](https://docs.microsoft.com/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) on-premises besturingselementen. U kunt ook de [geprivilegieerde toegangs werkstations](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) en [Azure AD Identity governance](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)raadplegen. Er zijn diverse hulpprogramma's voor van derden en de mogelijkheid om tegelijkertijd bevoegdheden te bieden aan een dynamische rol. Dit maakt meestal deel uit van een grotere discussie voor het beveiligen van een omgeving. 

Soms wordt de scenario-oproep weergegeven voor het toevoegen van een externe gebruiker aan een rol (Zie de sectie meervoudige Tenant hierboven). Dit werkt alleen goed. [Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/) is een andere grote en leuke beschrijving voor het doorvoeren van klanten, bijvoorbeeld in een ander artikel.

### <a name="security-and-compliance-center-scc"></a>SCC (Security and Compliance Center)

[Machtigingen in het Office 365-beveiligings & nalevings centrum](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) maken deel uit van rollen groepen, die afzonderlijke en onderscheiden zijn van Azure AD roles. Dit kan lastig zijn omdat sommige van deze rollen groepen dezelfde naam hebben als Azure AD-rollen (bijvoorbeeld beveiligings lezer), maar ze kunnen een ander lidmaatschap hebben. Ik maak gebruik van functies van Azure AD. Elke rollen groep bestaat uit een of meer ' rollen ' (zie wat ik wil voor het hergebruik van hetzelfde woord?) en hebben leden van Azure AD die objecten met een e-mail zijn ingeschakeld. U kunt ook een rolgroep maken met dezelfde naam als een rol die deze functie al dan niet kan bevatten (voorkomen van deze verwarring).

Dit zijn de evolutie van het model voor rollen groepen van Exchange. Exchange Online heeft echter wel een eigen interface voor [rollen groepen](https://docs.microsoft.com/exchange/permissions-exo) . Sommige rollen groepen in Exchange Online worden vergrendeld en beheerd via Azure AD of de beveiligings & nalevings centrum, maar andere kunnen dezelfde of vergelijkbare namen hebben en worden beheerd in Exchange Online (toevoegen aan de verwarring). U wordt aangeraden gebruik te maken van de gebruikersinterface van Exchange Online tenzij u een bereik nodig hebt voor Exchange-beheer.

U kunt geen aangepaste rollen maken. Rollen worden gedefinieerd door services die door Microsoft zijn gemaakt en zullen toenemen wanneer nieuwe services worden geïntroduceerd. Dit is vergelijkbaar met het concept van rollen die zijn [gedefinieerd door toepassingen](https://docs.microsoft.com/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) in azure AD. Wanneer nieuwe services zijn ingeschakeld, moeten er vaak nieuwe Rolgroepen worden gemaakt om toegang te verlenen aan of gemachtigden, bijvoorbeeld [Insider Risk Management](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure?view=o365-worldwide#step-1-required-enable-permissions-for-insider-risk-management).

Voor deze rollen groepen is ook directe lidmaatschap vereist en er kunnen geen Azure AD-groepen worden opgenomen. Deze rollen groepen worden helaas niet ondersteund door Azure AD PIM. Net als de functies van Azure AD, raden we u aan een beheer van deze via Api's of een partner beheer product zoals Saviynt of anderen te aanbevelen.

Beveiligings & rollencentrum rollen gelden voor Microsoft 365 en u kunt deze rollen groepen niet bereiken op een subset van de omgeving (zoals met Administrative Unit in azure AD). Veel klanten vragen hoe ze een delegering kunnen krijgen. Voorbeeld: "Maak een DLP-beleid voor EU-gebruikers." Als u de rechten hebt voor een bepaalde functie in de beveiligings & nalevings centrum, hebt u rechten voor alles wat onder deze functie valt in de Tenant. Een groot aantal beleidsregels bevat echter functies voor het aanbrengen van een subset van de omgeving (u kunt bijvoorbeeld de volgende [labels](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy) alleen beschikbaar maken voor deze gebruikers). Deugdelijk beheer en communicatie zijn een belangrijke component om conflicten te voorkomen. Sommige klanten kiezen voor het implementeren van de aanpak van een ' configuratie als code ' voor het uitvoeren van subdelegatie in de beveiligings & nalevings centrum. Sommige specifieke services ondersteunen delegering (zie hieronder). 

Het maakt niet uit of de besturingselementen die momenteel zijn beheerd via het beveiligings & compliance Center (protection.office.com), worden gemigreerd naar twee afzonderlijke portals: security.microsoft.com en compliance.microsoft.com. Wijziging is de enige constante.

### <a name="service-specific"></a>Service specifiek

Zoals eerder is vermeld, willen veel klanten een meer granulair delegerings model bereiken. Een gemeenschappelijk voorbeeld: ' Manage XYZ service only for afdelingen X gebruikers en locaties ' (of een andere dimensie). De mogelijkheid om dit te doen, is afhankelijk van elke service en is niet consistent in de services en functies. Daarnaast heeft elke service mogelijk een apart en uniek RBAC-model. In plaats van alles te bespreken (dit duurt altijd wel), ik voeg de relevante koppelingen voor elke service toe. Dit is geen volledige lijst, maar u gaat aan de slag.

- **Exchange Online** - [https://docs.microsoft.com/exchange/permissions-exo/permissions-exo](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- **SharePoint Online** - [https://docs.microsoft.com/sharepoint/manage-site-collection-administrators](https://docs.microsoft.com/sharepoint/manage-site-collection-administrators) 
- **Microsoft teams**  -  [https://docs.microsoft.com/microsoftteams/itadmin-readiness ](https://docs.microsoft.com/microsoftteams/itadmin-readiness )
- **eDiscovery** - [https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions](https://docs.microsoft.com/microsoft-365/compliance/) 
  + **Machtigingen filteren**  -  [https://docs.microsoft.com/microsoft-365/compliance/permissions-filtering-for-content-search ](https://docs.microsoft.com/microsoft-365/compliance/)
  + **Nalevings grenzen**  -  [https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries ](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries )
  + **Geavanceerd eDiscovery**  -  [https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20 ](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20 )
- **Yammer** - [https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins) 
- **Meerdere geografische** - [https://docs.microsoft.com/office365/enterprise/add-a-sharepoint-geo-admin](https://docs.microsoft.com/office365/enterprise/add-a-sharepoint-geo-admin) 
- **Dynamics 365** –[https://docs.microsoft.com/dynamics365/](https://docs.microsoft.com/dynamics365/) <br>
  Opmerking: deze koppeling gaat naar de hoofdsite van de documentatie. Er bestaan meerdere soorten services met variaties in het model voor de beheerder/overdracht.
- **Power platform**  -  [https://docs.microsoft.com/power-platform/admin/admin-documentation ](https://docs.microsoft.com/power-platform/admin/admin-documentation )
  + **Power-apps**  -  [https://docs.microsoft.com/power-platform/admin/wp-security ](https://docs.microsoft.com/power-platform/admin/wp-security ) <br>
    Opmerking: er zijn verschillende typen met variaties in de beheer-en delegerings modellen.
  + Automatisch aan de **macht**  -  [https://docs.microsoft.com/power-automate/environments-overview-admin ](https://docs.microsoft.com/power-automate/environments-overview-admin )
  + **PowerBI**  -  [https://docs.microsoft.com/power-bi/service-admin-governance ](https://docs.microsoft.com/power-bi/service-admin-governance ) <br>
Opmerking: beveiliging en delegering van het gegevens platform is een complex gebied, wat Power BI is.
- **Mem/intune**  -  [https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control ](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control )
- **Microsoft Defender ATP**  -  [https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles )
- **Microsoft Threat Protection** - [https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions)
- **Microsoft Cloud-app-beveiliging** - [https://docs.microsoft.com/cloud-app-security/manage-admins](https://docs.microsoft.com/cloud-app-security/manage-admins)
- **Gegevensstroom**  -  [https://docs.microsoft.com/stream/assign-administrator-user-role ](https://docs.microsoft.com/stream/assign-administrator-user-role )
- **Informatie belemmeringen**  -  [https://docs.microsoft.com/microsoft-365/compliance/information-barriers ](https://docs.microsoft.com/microsoft-365/compliance/information-barriers )

Voor de rest is zoeken in documenten echt helemaal goed [https://docs.microsoft.com/](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) . 


### <a name="activity-logs"></a>Activiteitenlogboeken
Office 365 heeft een [Uniform auditlogboek](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance). Het is een zeer [gedetailleerd logboek](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema), maar kan niet te veel in de naam worden gelezen. Dit bevat mogelijk niet alles wat u nodig hebt of die u nodig hebt voor uw beveiliging en naleving. Daarnaast zijn sommige klanten echt geïnteresseerd in de [geavanceerde controle](https://docs.microsoft.com/microsoft-365/compliance/advanced-audit). 

Hier volgen enkele voorbeelden van de logboeken van Microsoft 365 die worden weergegeven via de andere API:
- [Azure AD](https://docs.microsoft.com/azure/azure-monitor/platform/diagnostic-settings) (activiteiten die niet gerelateerd zijn aan Office 365)
- [Exchange-berichten traceren](https://docs.microsoft.com/powershell/module/exchange/get-messagetrace?view=exchange-ps)
- Threat/UEBA Systems hierboven besproken (bijvoorbeeld Azure AD Identity Protection, Microsoft Cloud app Security, Microsoft Defender ATP, etc.)
- [Microsoft-informatiebescherming](https://docs.microsoft.com/microsoft-365/compliance/data-classification-activity-explorer?view=o365-worldwide)
- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft Graph](https://graph.microsoft.com)

Het is belangrijk dat u eerst alle benodigde logboek bronnen identificeert voor een beveiligings-en compliance-programma. Houd er rekening mee dat verschillende logboeken een afwijkende Bewaar limiet hebben. 

In het perspectief van de beheerder is de meeste Microsoft 365-activiteitenlogboeken niet uitgerust met een ingebouwd RBAC-model. Als u gemachtigd bent om een logboek te bekijken, kunt u alles erin zien. Een veelvoorkomend voorbeeld van een klantbehoeften is: "Ik wil alleen een query uitvoeren voor EU-gebruikers" (of een andere dimensie). Om dit vereiste te bereiken, moeten we logboeken overzetten naar een andere service. In de Microsoft-Cloud wordt u aangeraden dit te deoverbrengen naar de [Azure-Sentinel](https://docs.microsoft.com/azure/sentinel/overview) of de [logboekanalyse](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace). 

Diagram op hoog niveau:

![diagram op hoog niveau van de logboek stroom](../media/solutions-architecture-center/identity-beyond-illustration-4.png)  

Het bovenstaande diagram bevat ingebouwde mogelijkheden voor het verzenden van logboeken naar Event hub en/of Azure Storage en/of Azure log Analytics. Niet alle systemen bevatten deze kant-en-klare box nog. U kunt deze logboeken ook op andere manieren verzenden naar dezelfde bibliotheek. Zie bijvoorbeeld [uw teams beschermen met Azure Sentinel](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761).

Als u alle logboeken in één opslaglocatie combineert, wordt er een extra voordeel van het extra voordeel opgenomen, zoals bijsnijders, een aangepaste bewaarperiode, zodat de gegevens die nodig zijn voor de ondersteuning van het RBAC-model, enz. Wanneer gegevens zich in dit opslagsysteem bevindt, kunt u een PowerBI-dashboard (of een ander type visualisatie) maken met een geschikt RBAC-model.

Logboeken hoeven niet naar één plaats te worden doorgestuurd. Het kan ook handig zijn om [Office 365-logboeken met de Microsoft Cloud-app-beveiliging](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) of een aangepast RBAC-model in [Power bi](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics?view=o365-worldwide)te integreren. Verschillende opslaglocaties hebben verschillende voordelen en doelgroepen.

Er wordt aangegeven dat er een zeer uitgebreid ingebouwd Analytics-systeem is voor beveiliging, bedreigingen en beveiligingslekken, etc. in een service genaamd [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide).

Veel grote klanten willen deze logboekgegevens overbrengen naar een systeem van derden (bijvoorbeeld SIEM). Er zijn verschillende manieren waarop u dit kunt doen, maar in-algemene [Azure Event hub](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) en [Graph](https://docs.microsoft.com/graph/security-integration) goede beginpunten zijn.


### <a name="azure"></a>Azure 
Ik krijg vaak een vraag of er een manier bestaat om rollen met een hoge bevoegdheid te onderscheiden van Azure AD, Azure en SaaS (ex.: globale beheerder voor Office 365, maar niet Azure).  Niet echt.  De architectuur voor meervoudige Tenant is nodig als volledige beheer scheidings scheiding vereist is, maar die een belangrijke [complexiteit](https://aka.ms/multi-tenant-user) toevoegt (zie hierboven). Al deze services maken deel uit van dezelfde boundary voor de beveiligings-en identiteits grenzen (Bekijk het bovenstaande hiërarchiemodel).  

Het is belangrijk dat u de relaties tussen verschillende services in dezelfde Tenant begrijpt. Ik werk met veel klanten die bedrijfsoplossingen bouwen die van Azure, Office 365 en Power platform (en vaak ook on-premises en cloudservices van derden) zijn. Een gemeenschappelijk voorbeeld: 
-   Ik wil samenwerken aan een set documenten/afbeeldingen/etc (Office 365)
-   Stuur elk een van deze via een goedkeuringsproces (Power platform).
-   Wanneer alle onderdelen zijn goedgekeurd, kunt u deze samenvoegen tot een uitgesplitste product (s) (Azure) [Microsoft Graph API](https://docs.microsoft.com/azure/active-directory/develop/microsoft-graph-intro) de beste vriend voor u zijn.  Is niet mogelijk, maar u kunt een oplossing voor [meerdere tenants](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)niet ontwerpen.

Azure-toegangsbeheer op basis van rollen (RBAC) maakt ondersteuning voor het verkrijgen van toegang tot het detail beheer van Azure. Met behulp van RBAC kunt u de toegang tot bronnen beheren door gebruikers de minste machtigingen te verlenen die nodig zijn om hun taken uit te voeren. De gegevens bevinden zich buiten de reikwijdte van dit document, maar Zie [Wat is op rollen gebaseerd toegangsbeheer voor rollen in azure?](https://docs.microsoft.com/azure/role-based-access-control/overview) voor meer informatie. RBAC is belangrijk, maar slechts een deel van de aandachtspunten voor Azure. [Cloud acceptatie raamwerk](https://docs.microsoft.com/azure/cloud-adoption-framework/govern/) is een geweldig uitgangspunt voor meer informatie. Ik vind het leuk voor mijn vriend, Andres Ravinett klanten stapsgewijs stapsgewijs door verschillende onderdelen te kiezen. Een weergave op het hoogste niveau voor verschillende elementen (niet zo goed als de procedure om het werkelijke klantmodel te bereiken) is een soortgelijke manier:

![Algemeen overzicht van Azure-onderdelen voor gedelegeerd beheer](../media/solutions-architecture-center/identity-beyond-illustration-5.png)

Zoals u kunt zien in de bovenstaande afbeelding, moet u een deel van het ontwerp als onderdeel van het ontwerp (bijvoorbeeld: [Azure-beleidsregels](https://docs.microsoft.com/azure/governance/policy/overview), [Azure-blauwdrukken](https://docs.microsoft.com/azure/governance/blueprints/overview), [beheergroepen](https://docs.microsoft.com/azure/governance/management-groups/)enzovoort) als onderdeel van de ontwerpfuncties volgen.

## <a name="conclusion"></a>Conclusie
Een korte samenvatting is beëindigd, langer dan verwacht.  Ik hoop dat u nu een diepgaande kant-en-klare kant-en-klare organisatie voor uw organisatie kunt maken.  Dit gesprek is veel gebruikelijk met klanten. Er is niet één model voor iedereen. Wachten op een aantal geplande verbeteringen van Microsoft engineering voordat veelgebruikte patronen in documenten worden weergegeven. Ondertussen kunt u met uw Microsoft-accountteam een bezoek brengen aan het dichtstbijzijnde [Microsoft-technologie centrum](https://www.microsoft.com/mtc).  U kunt hier kijken!


