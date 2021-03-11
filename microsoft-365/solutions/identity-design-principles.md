---
title: Planning van ondernemingsresources in Microsoft 365 - Beveiligingsarchitectuur
description: Meer informatie over de belangrijkste ontwerpstrategieën voor de Microsoft Enterprise-architectuur van Alex Shteynberg, Technical Principal Architect bij Microsoft.
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
- M365solutions
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: b2ea85190aeda74efc25a7088a01365132caad30
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712508"
---
# <a name="to-identity-and-beyondone-architects-viewpoint"></a>Naar identiteit en verder - het werk van één architect

In dit artikel bespreekt [Alex Shteynberg,](https://www.linkedin.com/in/alex-shteynberg/)Principal Technical Architect bij Microsoft, de belangrijkste ontwerpstrategieën voor ondernemingen die Microsoft 365 en andere Microsoft-cloudservices gebruiken.

## <a name="about-the-author"></a>Over de auteur

![Foto van Alex Shteynberg](../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg)

Ik ben een principal Technical Architect van het New York [Microsoft Technology Center.](https://www.microsoft.com/mtc?rtc=1) Ik werk voornamelijk met grote klanten en complexe vereisten. Mijn mening en mening zijn gebaseerd op deze interacties en zijn mogelijk niet van toepassing op elke situatie. In mijn ervaring kunnen we echter alle klanten helpen met de meest complexe uitdagingen.

Ik werk meestal met meer dan 100 klanten per jaar. Hoewel elke organisatie unieke kenmerken heeft, is het interessant om trends en overeenkomsten te zien. Eén trend is bijvoorbeeld de interesse in verschillende bedrijfstaken voor veel klanten. Een bankvertakking kan tenslotte ook een café en een communitycentrum zijn.

In mijn rol richt ik mij op het helpen van klanten om de beste technische oplossing te vinden om hun unieke set zakelijke doelen te bereiken. Officieel focus ik op Identiteit, Beveiliging, Privacy en Naleving. Ik vind het leuk dat dit alles aanraakt wat we doen. Het geeft mij de mogelijkheid betrokken te zijn bij de meeste projecten. Zo blijf ik druk en geniet ik van deze rol.

Ik woon in New York City (de beste!) en geniet van de diversiteit van de cultuur, het eten en de mensen (niet de verkeersdrukte). Ik ben dol op reizen als dat kan en hopen de meeste van de wereld in mijn leven te zien. Ik onderzoek momenteel een reis naar Afrika om meer te weten te komen over het wild.

## <a name="guiding-principles"></a>Uitgangspunten

- **Eenvoudig is vaak beter:** u kunt (bijna) alles met technologie doen, maar het betekent niet dat u dat moet doen. Met name in de beveiligingsruimte hebben veel klanten veel te veel oplossingen nodig. Ik vind [deze video van](https://www.youtube.com/watch?v=SOQgABDSYZE) google's Stripe-vergadering leuk om dit punt te onderstrepen.
- **Personen, processen, technologie:** ontwerp voor [personen om](https://en.wikipedia.org/wiki/Human-centered_design) het proces te verbeteren, niet eerst technische informatie. Er zijn geen perfecte oplossingen. We moeten verschillende risicofactoren in balans brengen en beslissingen zullen voor elk bedrijf verschillend zijn. Te veel klanten ontwerpen een benadering die hun gebruikers later vermijden.
- **Focus eerst op 'waarom' en 'hoe' later:** Wees het hinderlijke, 7-yr oude kind met een miljoen vragen. We kunnen niet op het juiste antwoord komen als we niet weten wat de juiste vragen zijn. Veel klanten gaan ervan uit dat zaken moeten werken in plaats van het bedrijfsprobleem te definiëren. Er zijn altijd meerdere paden die u kunt volgen.
- **Lange eind van best practices uit het verleden:** beken dat de beste werkwijzen snel veranderen. Als u Azure AD meer dan drie maanden geleden hebt bekeken, bent u waarschijnlijk verouderd. Alles hier kan na publicatie worden gewijzigd. De optie 'Beste' over zes maanden is mogelijk niet hetzelfde.

## <a name="baseline-concepts"></a>Basislijnconcepten

Sla deze sectie niet over. Ik vind vaak dat ik terug moet naar deze onderwerpen, zelfs voor klanten die al jaren cloudservices gebruiken.
Helaas, taal is geen heel nauwkeurig hulpmiddel. Vaak gebruiken we hetzelfde woord om verschillende concepten of andere woorden te gebruiken om hetzelfde concept te betekenen. Ik gebruik dit diagram vaak hieronder voor het maken van enkele basislijnterminologie en 'hiërarchiemodel'.
<br><br>

![Afbeelding van tenant, abonnement, service en gegevens](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)  

<br>

Wanneer u leert zwemmen, is het beter om in het pool te beginnen en niet in het midden van de oceaan. Ik probeer technisch gezien niet nauwkeurig te zijn met dit diagram. Het is een model om enkele basisconcepten te bespreken.

In het diagram:

- Tenant = een exemplaar van Azure AD. Deze staat boven aan een hiërarchie of op niveau 1 in het diagram. We kunnen dit beschouwen als de "[grens](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-directory-independence)" waar alles anders gebeurt[(Azure AD B2B apart).](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) Alle cloudservices van Microsoft Enterprise maken deel uit van een van deze tenants. Consumentenservices zijn gescheiden. 'Tenant' wordt in de documentatie weergegeven als Office 365-tenant, Azure-tenant, WVD-tenant, en meer. Deze variaties zorgen vaak voor verwarring bij klanten.
- Services/abonnementen, niveau 2 in het diagram, behoren tot één tenant. De meeste SaaS-services zijn 1:1 en kunnen niet zonder migratie worden verplaatst. Azure is anders, u kunt [facturering en/of](https://docs.microsoft.com/azure/cost-management-billing/manage/billing-subscription-transfer) een [abonnement naar](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) een andere tenant verplaatsen. Er zijn veel klanten die Azure-abonnementen moeten verplaatsen. Dit heeft verschillende gevolgen. Objecten die buiten het abonnement aanwezig zijn, worden niet verplaatst (bijvoorbeeld toegangsbeheer op basis van rollen of Azure RBAC- en Azure AD-objecten, waaronder groepen, apps, beleidsregels, etc.). Sommige services (zoals Azure Key Vault, Gegevenssteens, etc.) Mier geen services zonder een goede zakelijke behoefte. Sommige scripts die handig kunnen zijn voor migratie, [worden gedeeld op GitHub.](https://github.com/lwajswaj/azure-tenant-migration)
- Een bepaalde service heeft meestal een bepaalde soort grens op het subniveau of niveau 3 (L3). Dit is handig om te weten voor de scheiding van beveiliging, beleid, beheer, en meer. Er is helaas geen uniforme naam die ik ken. Enkele voorbeelden van namen voor L3 zijn: Azure Subscription = [resource](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resources-portal); Dynamics 365 CE = [instance](https://docs.microsoft.com/dynamics365/admin/new-instance-management); Power BI = [werkruimte](https://docs.microsoft.com/power-bi/service-create-the-new-workspaces); Power Apps = [omgeving](https://docs.microsoft.com/power-platform/admin/environments-overview); en zo verder.
- Niveau 4 is waar de werkelijke gegevens zich opslaan. Dit 'gegevensvlak' is een complex onderwerp. Sommige services maken gebruik van Azure AD voor RBAC, andere niet. Ik bespreekt het even als we bij de delegatieonderwerpen zijn.

Enkele andere concepten waar ik veel klanten (en Microsoft-werknemers) van vind, zijn onder meer:

- Iedereen kan [zonder](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) kosten veel tenants [maken.](https://azure.microsoft.com/pricing/details/active-directory/) U hebt een service binnen deze service niet nodig. Ik heb er tientallen. Elke tenantnaam is uniek in de wereldwijde cloudservice van Microsoft (met andere woorden: twee tenants mogen niet dezelfde naam hebben). Ze hebben allemaal de indeling van TenantName.onmicrosoft.com. Er zijn ook processen die tenants automatisch[(onmanaged tenants) maken.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup) Dit kan bijvoorbeeld gebeuren wanneer een gebruiker zich voor een enterprise-service meldt met een e-maildomein dat niet in een andere tenant aanwezig is.
- In een beheerde tenant kunnen veel [DNS-domeinen](https://docs.microsoft.com/azure/active-directory/fundamentals/add-custom-domain) in de tenant worden geregistreerd. Hiermee wordt de naam van de oorspronkelijke tenant niet gewijzigd. Het is op dit moment niet eenvoudig om de naam van een tenant te wijzigen (anders dan migratie). Hoewel de naam van de tenant technisch gezien niet kritiek is tegenwoordig, kunnen sommigen dit beperkend vinden.
- Reserveer een tenantnaam voor uw organisatie, zelfs als u nog niet van plan bent om services te implementeren. Anders kan iemand het van u af halen en is er geen eenvoudig proces om het terug te nemen (hetzelfde probleem als dns-namen). Ik hoor dit te vaak van klanten. Wat de naam van uw tenant moet zijn, is ook een discussieonderwerp.
- Als u eigenaar bent van DNS-naamruimten, moet u deze allemaal aan uw tenant(s) toevoegen. Anders zou er een [onmanagede tenant met](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup) deze naam kunnen worden aangeslagen, waardoor de tenant [niet kan worden beheerd.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)
- DNS-naamruimte (zoals contoso.com) kan bij één tenant horen. Dit heeft gevolgen voor verschillende scenario's (bijvoorbeeld het delen van een e-maildomein tijdens een fusie of overname, etc.). Er is een manier om een DNS-sub (zoals div.contoso.com) te registreren in een andere tenant, maar dat moet u vermijden. Als u een domeinnaam op het hoogste niveau registreert, wordt ervan uitgegaan dat alle subdomeinen deel uitmaken van dezelfde tenant. In scenario's met meerdere tenants (zie hieronder) zou ik normaal gesproken een andere domeinnaam op het hoogste niveau gebruiken (zoals contoso.ch of ch-contoso.com).
- Wie moet 'eigenaar' zijn van een tenant? Ik zie vaak klanten die niet weten wie de eigenaar is van hun tenant. Dit is een grote rode vlag. Bel zo snel mogelijk met Microsoft Ondersteuning. Even problematisch is wanneer een service-eigenaar (vaak een Exchange-beheerder) is aangewezen voor het beheren van een tenant. De tenant bevat in de toekomst alle services die u mogelijk wilt gebruiken. De tenant-eigenaar moet een groep zijn die kan beslissen of alle cloudservices in een organisatie moeten worden ingeschakeld. Een ander probleem is dat een groep tenanteigenaars wordt gevraagd alle services te beheren. De schaal is niet groot voor grote organisaties.
- Er is geen concept van een sub-/super-tenant. Om een of andere reden blijft deze myth zich herhalen. Dit geldt ook [voor B2C-tenants van Azure AD.](https://docs.microsoft.com/azure/active-directory-b2c/) Ik hoor te vaak 'Mijn B2C-omgeving staat in mijn XYZ-tenant' of 'Hoe verplaats ik mijn Azure-tenant naar mijn Office 365-tenant?'
- Dit document is voornamelijk gericht op de commerciële wereldwijde cloud, omdat dit is wat de meeste klanten gebruiken. Soms is het handig om te weten over [soevereine wolken.](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud) Soevereine clouds hebben aanvullende gevolgen om te bespreken welke buiten het bereik voor deze discussie vallen.

## <a name="baseline-identity-topics"></a>Basislijnidentiteitsonderwerpen

Er is veel documentatie over Het identiteitsplatform van Microsoft: Azure Active Directory (Azure AD). Voor degenen die nog maar net beginnen, voelt dit vaak overweldigend. Zelfs nadat u erover hebt geleerd, kan het lastig zijn om voortdurend innovatie en veranderingen te behouden. In mijn interacties met klanten vind ik vaak dat ik dienst moet doen als 'vertaler' tussen zakelijke doelen en 'Goed, beter, beste' benaderingen om deze (en menselijke 'klippen' voor deze onderwerpen aan te pakken). Er is zelden een perfect antwoord en de 'juiste' beslissing is een balans tussen verschillende risicofactoren. Hieronder vindt u enkele veelvoorkomende vragen en verwarrende zaken die ik vaak met klanten bespreekt.

### <a name="provisioning"></a>Inrichting

Azure AD lost niet op bij een gebrek aan beheermodel in uw identiteits wereld! [Identiteitsbeheer](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) moet een kritiek element zijn, onafhankelijk van cloudbeslissingen. De beheervereisten veranderen in de tijd, daarom is het een programma en niet een hulpmiddel.

[Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect) versus [Microsoft Identity Manager](https://docs.microsoft.com/microsoft-identity-manager/microsoft-identity-manager-2016) (MIM) versus iets anders (derden of aangepast)? Bespaar uzelf nu en in de toekomst een hoop kop en ga aan de hand van Azure AD Connect. Dit hulpprogramma biedt allerlei soorten smarts om specifieke klantconfiguraties en continue innovaties aan te pakken.

Sommige rand gevallen die leiden tot een complexere architectuur:

- Ik heb meerdere AD-forests zonder netwerkverbinding tussen deze forests. Er is een nieuwe optie met de [naam Cloud provisioning.](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning)
- Ik heb geen Active Directory en wil het ook niet installeren. Azure AD Connect kan worden geconfigureerd voor [synchronisatie vanuit LDAP](https://docs.microsoft.com/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) (partner is mogelijk vereist).
- Ik moet dezelfde objecten inrichten voor meerdere tenants. Dit wordt technisch gezien niet ondersteund, maar is afhankelijk van de definitie van 'hetzelfde'.

Moet ik standaardsynchronisatieregels aanpassen[(filterobjecten,](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering)kenmerken wijzigen, [alternatieve aanmeldings-id,](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-userprincipalname)en meer)? [](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) Vermijd het! Een identiteitsplatform is net zo waardevol als de services die het gebruiken. U kunt allerlei typen configuraties maken, maar als u deze vraag wilt beantwoorden, moet u kijken wat de gevolgen zijn voor toepassingen. Als u objecten met e-mail filtert, is de gal voor onlineservices onvolledig. als de toepassing afhankelijk is van specifieke kenmerken, kan het filteren van deze kenmerken onvoorspelbare gevolgen hebben. en zo verder. Het is geen beslissing van het identiteitsteam.

XYZ SaaS ondersteunt Just-in-Time (JIT)-inrichting. Waarom moet ik synchroniseren? Zie het bovenstaande. Veel toepassingen hebben profielinformatie nodig voor functionaliteit. U kunt geen gal hebben als niet alle objecten met e-mail beschikbaar zijn. Hetzelfde geldt voor [gebruikers provisioning](https://docs.microsoft.com/azure/active-directory/app-provisioning/user-provisioning) in toepassingen die zijn geïntegreerd met Azure AD.

### <a name="authentication"></a>Verificatie

[Wachtwoord-hashsynchronisatie](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) versus [Pass Through-verificatie](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) (PTA) versus [federatie.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility)

Meestal is er een betrokken [discussie](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) over federatie. Eenvoudiger is meestal beter en gebruik daarom PHS, tenzij u een goede reden hebt om dat niet te doen. Het is ook mogelijk om verschillende verificatiemethoden te configureren voor verschillende DNS-domeinen in dezelfde tenant. 

Sommige klanten gebruiken federatie en PHS voornamelijk voor:

- Een optie om [op terug te](https://docs.microsoft.com/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) vallen (voor herstel na noodherstel) als de federatieservice niet beschikbaar is.
- Extra mogelijkheden (bijvoorbeeld: [Azure AD DS)](https://docs.microsoft.com/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)en beveiligingsservices (bijvoorbeeld: [gelekte referenties)](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials)
- Ondersteuning voor services in Azure die geen inzicht hebben in federatieverificatie (bijvoorbeeld [Azure-bestanden).](https://docs.microsoft.com/azure/storage/files/storage-files-active-directory-overview)

Ik doorloop klanten vaak door de clientverificatiestroom om enkele misconcepten te verduidelijken. Het resultaat lijkt op de onderstaande afbeelding, die niet zo goed is als het interactieve proces om er te komen.

![Voorbeeld van whiteboardgesprek](../media/solutions-architecture-center/identity-beyond-whiteboard-example.png)

Dit type whiteboardtekening illustreert waar beveiligingsbeleid wordt toegepast binnen de stroom van een verificatieaanvraag. In dit voorbeeld worden beleidsregels die worden afgedwongen via Active Directory Federation Service (AD FS), toegepast op de eerste serviceaanvraag, maar niet op de volgende serviceaanvragen. Dit is ten minste één reden om beveiligingsbesturingselementen zo veel mogelijk naar de cloud te verplaatsen.

We hebben de droom [](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) van eenmalige aanmelding (SSO) al zo lang gehad als ik me kan herinneren. Sommige klanten denken dit te kunnen bereiken door de 'juiste' federatieprovider (STS) te kiezen. Azure AD kan aanzienlijk helpen bij [het inschakelen van SSO-mogelijkheden,](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-sso-deployment) maar geen STS is magische. Er zijn te veel 'verouderde' verificatiemethoden die nog worden gebruikt voor essentiële toepassingen. Veel van deze [scenario's kunnen worden uitgebreid](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) met Azure AD met partneroplossingen. Eenmalige aanmelding is een strategie en een reis. U komt er alleen als u standaarden [voor toepassingen gaat gebruiken.](https://docs.microsoft.com/azure/active-directory/develop/v2-app-types) Gerelateerd aan dit onderwerp is een reis [naar](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless) wachtwoordloze verificatie, die ook geen magische antwoord heeft.

[Meervoudige verificatie (Multi-Factor Authentication,](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) MFA) is vandaag[(hier voor](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) meer) essentieel. Voeg er een [analyse van gebruikersgedrag aan](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) toe en je hebt een oplossing die de meeste veelvoorkomende cyberaanvallen voorkomt. Zelfs consumentenservices willen MFA vereisen. Toch ontmoet ik nog steeds veel klanten die geen gebruik willen maken van moderne [verificatiemethoden.](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview) Het grootste argument dat ik hoor, is dat dit van invloed is op gebruikers en oudere toepassingen. Soms kan een goede start helpen om de overstap te maken : Exchange Online [heeft de wijzigingen aangekondigd.](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282) Er zijn [](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) nu veel Azure AD-rapporten beschikbaar om klanten te helpen bij deze overgang.

### <a name="authorization"></a>Autorisatie

Per [Wikipedia](https://en.wikipedia.org/wiki/Authorization)is "to authorize" het definiëren van een toegangsbeleid. Veel personen zien het als de mogelijkheid om toegangsbesturingselementen voor een object (bestand, service, etc.) te definiëren. In de huidige wereld van cyberaanvallen ontwikkelt dit concept zich snel naar een dynamisch beleid dat kan reageren op verschillende bedreigingsvectoren en snel de toegangsbesturingselementen hierop kan aanpassen. Als ik bijvoorbeeld vanaf een ongebruikelijke locatie toegang tot mijn bankrekening krijg, krijg ik extra bevestigingsstappen. Om dit te kunnen aanpakken, moeten we niet alleen rekening houden met het beleid zelf, maar ook met het ecosysteem voor bedreigingsdetectie en signaal correlatiemethodiek.

De beleidsen engine van Azure AD wordt geïmplementeerd met behulp van [beleidsregels voor voorwaardelijke toegang.](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) Dit systeem is afhankelijk van gegevens uit diverse andere systemen voor bedreigingsdetectie om dynamische beslissingen te nemen. Een eenvoudige weergave zou er als volgt uit zien:

![Beleidsen engine in Azure AD](../media/solutions-architecture-center/identity-and-beyond-illustration-3.png)

Als u al deze signalen combineert, is er een dynamisch beleid zoals dit:

- Als er een bedreiging wordt gedetecteerd op uw apparaat, wordt uw toegang tot gegevens alleen beperkt tot internet, zonder dat u deze kunt downloaden.
- Als u een ongebruikelijk grote hoeveelheid gegevens downloadt, wordt alles wat u downloadt versleuteld en beperkt.
- Als u toegang krijgt tot een service vanaf een onmand apparaat, wordt u geblokkeerd voor zeer gevoelige gegevens, maar hebt u toegang tot niet-beperkte gegevens zonder de mogelijkheid om deze naar een andere locatie te kopiëren.

Als u akkoord gaat met deze uitgebreide autorisatiedefinitie, moet u aanvullende oplossingen implementeren. Welke oplossingen u implementeert, is afhankelijk van hoe dynamisch het beleid moet zijn en van welke bedreigingen u prioriteit wilt geven. Enkele voorbeelden van dergelijke systemen zijn:

- [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/) 
- [Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/)
- [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/) (MCAS)
- [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/mem/intune/)
- [Microsoft Information Protection](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) (MIP)
- [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/)

Naast Azure AD hebben verschillende services en toepassingen natuurlijk hun eigen specifieke autorisatiemodellen. Sommige van deze onderwerpen worden later besproken in de sectie delegatie.

### <a name="audit"></a>Controle

Azure AD heeft uitgebreide [controle- en rapportagemogelijkheden.](https://docs.microsoft.com/azure/active-directory/reports-monitoring/) Meestal is dit echter niet de enige bron van informatie die nodig is om beveiligingsbeslissingen te nemen. Zie de sectie Delegatie voor meer informatie over dit onderwerp.

## <a name="theres-no-exchange"></a>Er is geen Exchange

Geen paniek! Dit betekent niet dat Exchange wordt afgeschaft (of SharePoint, etc.). Het is nog steeds een kernservice. Wat ik wil zeggen, is dat technologieproviders al enige tijd gebruikservaringen (UX) gebruiken die onderdeel zijn van meerdere services. In Microsoft 365 is een eenvoudig voorbeeld['moderne](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)bijlagen' waarbij bijlagen bij e-mail worden opgeslagen in SharePoint Online of OneDrive voor Bedrijven.

![Een bestand als bijlage aan een e-mailbericht toevoegen](../media/solutions-architecture-center/modern-attachments.png)

Als u naar de Outlook-client kijkt, ziet u veel services die zijn 'verbonden' als onderdeel van deze ervaring, niet alleen Exchange. Dit geldt voor Azure AD, Microsoft Search, Apps, Profiel, Compliance en Office 365-groepen. 

![Outlook-interface met bijroepen](../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png)

Lees meer [over Microsoft Fluid Framework voor](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) een preview van komende mogelijkheden. In de voorbeeldweergave kan ik Teams-gesprekken rechtstreeks in Outlook lezen en beantwoorden. De [Teams-client](https://products.office.com/microsoft-teams/download-app) is in feite een van de prominente voorbeelden van deze strategie. 

Over het algemeen wordt het steeds moeilijker om een duidelijke lijn te trekken tussen Office 365 en andere services in Microsoft Clouds. Ik bekijk het als een groot voordeel voor klanten, omdat ze kunnen profiteren van totale innovatie voor alles wat we doen, zelfs als ze één onderdeel gebruiken. Dit heeft grote gevolgen voor veel klanten.

Tegenwoordig vind ik dat veel IT-groepen van klanten zijn gestructureerd rond 'producten'. Het is logisch voor een on-premises wereld, omdat u voor elk specifiek product een expert nodig hebt. Ik ben echter helemaal blij dat ik een Active Directory- of Exchange-database nooit meer hoef op te sporen als deze services naar de cloud zijn verplaatst. Automatisering (het type cloud) verwijdert bepaalde terugkerende handmatige taken (kijk wat er is gebeurd). Deze zijn echter vervangen door complexere vereisten om inzicht te krijgen in interactie tussen services, invloed, bedrijfsbehoeften, en dergelijke. Als u bereid bent om [te leren,](https://docs.microsoft.com/learn/)zijn er grote mogelijkheden die mogelijk worden gemaakt door de cloudtransformatie. Voordat ik over technologie ga, praat ik vaak met klanten over het beheren van de veranderingen in IT-vaardigheden en teamstructuren.

Voor alle SharePoint-fan-personen en ontwikkelaars hoeft u niet meer te vragen: 'Hoe kan ik XYZ in SharePoint Online doen?' Gebruik [Power Automate](https://docs.microsoft.com/power-automate/) (of Flow) voor werkstromen, het is een veel krachtiger platform. Gebruik [Azure Bot Framework om](https://docs.microsoft.com/azure/bot-service/?view=azure-bot-service-4.0) een betere UX te maken voor uw itemlijst van 500 K. Gebruik [Microsoft Graph in](https://developer.microsoft.com/graph/) plaats van CSOM. [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview) bevat SharePoint, maar ook nog een hele wereld. Er zijn nog veel meer voorbeelden die ik kan noemen. Er is een groot en geweldig universum. Open de deur en [begin te verkennen.](https://docs.microsoft.com)

De overige algemene impact heeft te maken met het nalevingsgebied. Deze benadering voor meerdere services is een benadering die een groot aantal nalevingsbeleidsregels volledig met elkaar verwart. Ik blijf organisaties zien met deze status: 'Ik wil alle e-mailcommunicatie naar een eDiscovery-systeem in het logboek bewaren'. Wat betekent dit wanneer e-mail niet meer alleen e-mail is maar een venster in andere services? Office 365 heeft een uitgebreide benadering voor [naleving,](https://docs.microsoft.com/microsoft-365/compliance/)maar veranderende personen en processen zijn vaak veel moeilijker dan technologie.

Er zijn veel andere personen en gevolgen voor het proces. Naar mijn mening is dit een kritiek en onderbediscusseerd gebied. Misschien meer informatie in een ander artikel.

## <a name="tenant-structure-options"></a>Opties tenantstructuur

### <a name="single-tenant-vs-multi-tenant"></a>Eén tenant versus meerdere tenants

Over het algemeen hebben de meeste klanten slechts één productie-tenant. Er zijn veel redenen waarom meerdere tenants moeilijk zijn (door ze een [Bing-zoekopdracht](https://www.bing.com/search?q=office%20365%20multiple%20tenants)te geven) of deze [whitepaper te lezen.](https://aka.ms/multi-tenant-user) Tegelijkertijd hebben veel zakelijke klanten met mij een andere (kleine) tenant voor it-leren, testen en experimenteren. Azure-toegang tussen tenants wordt gemakkelijker gemaakt met [Azure Lighthouse.](https://azure.microsoft.com/services/azure-lighthouse/) Office 365 en vele andere SaaS-services hebben limieten voor scenario's tussen tenants. Er is veel om rekening mee te houden in B2B-scenario's voor [Azure AD.](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)

Veel klanten hebben meerdere productieten tenants na een fusie en overname (M&A) en willen samenvoegen. Dat is niet eenvoudig en vereist microsoft Consulting Services (MCS) of een partner plus software van derden. Er is doorlopend technisch werk nodig om in de toekomst verschillende scenario's met klanten met meerdere tenants aan te pakken.

Sommige klanten kiezen voor meer dan één tenant. Dit moet een zeer voorzichtige beslissing zijn en bijna altijd op het goede werk. Enkele voorbeelden:

- Een bedrijfsstructuur van het type bedrijf, waarin eenvoudig samenwerken tussen verschillende entiteiten niet is vereist en er sprake is van sterk administratief en andere isolatiebehoeften.
- Na een aanschaf wordt besloten om twee entiteiten gescheiden te houden.
- Het gebruik van een omgeving van een klant die de productieomgeving van de klant niet wijzigt. 
- De ontwikkeling van software voor klanten.

In deze scenario's met meerdere tenants willen klanten vaak de configuratie voor tenants hetzelfde houden of over configuratiewijzigingen en aanpassingen rapporteren. Dit betekent vaak dat u moet overgeschakeld van handmatige wijzigingen naar configuratie als code. De ondersteuning voor Microsoft Doornen biedt een workshop voor dit soort vereisten op basis van dit openbare [https://Microsoft365dsc.com](https://Microsoft365dsc.com) IP-adres:

### <a name="multi-geo"></a>Multi-Geo

Voor [Multi-Geo](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-multi-geo) of niet voor Multi-Geo is dat de vraag. Met Office 365 Multi-Geo kunt u gegevens inrichten en opslaan in de [](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations) geografische locaties die u hebt gekozen om te voldoen aan de vereisten voor gegevensopslag. Er zijn veel misconcepten over deze mogelijkheid. Houd het volgende in gedachten:

- Dit levert geen prestatievoordelen op. Dit kan de prestaties slechter maken als [het netwerkontwerp](https://aka.ms/office365networking) niet juist is. Laat apparaten 'sluiten' bij het Microsoft-netwerk, niet per se uw gegevens.
- Het is geen oplossing voor [avg-naleving.](https://www.microsoft.com/trust-center/privacy/gdpr-overview) De AVG richt zich niet op het opslaan van gegevens of opslaglocaties. Er zijn andere nalevingskaders voor.
- De delegatie van beheer (zie hieronder) of informatiebarrières worden [niet opgelost.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)
- Het is niet hetzelfde als de meervoudige tenant en hiervoor zijn extra gebruikers [inrichtingswerkstromen](https://github.com/MicrosoftDocs/azure-docs-pr/blob/master/articles/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation.md) vereist.
- Uw tenant [(Azure](https://docs.microsoft.com/microsoft-365/enterprise/moving-data-to-new-datacenter-geos) AD) wordt niet naar een andere geografie verplaatst. 

## <a name="delegation-of-administration"></a>Beheerdelegering

In de meeste grote organisaties is een scheiding van taken en toegangsbeheer op basis van rollen (RBAC) noodzakelijk. Ik ga mijn excuses van tevoren aanbieden. Dit is niet zo eenvoudig als sommige klanten willen. Klant-, juridische, nalevings- en andere vereisten verschillen en conflicteren soms over de hele wereld. Eenvoud en flexibiliteit liggen vaak tegenover elkaar. Be begrijp me niet verkeerd, we kunnen hier iets beters aan doen. Er zijn (en zullen) aanzienlijke verbeteringen zijn geweest in de tijd. Ga naar uw lokale [Microsoft Technology Center om](https://www.microsoft.com/mtc) het model uit te werken dat past bij uw bedrijfsvereisten zonder dat u 379230 documenten moet lezen. Hier ga ik me richten op wat u moet bedenken en niet waarom het op deze manier gebeurt. Hieronder vindt u vijf verschillende gebieden waar u enkele veelvoorkomende vragen kunt plannen.

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Azure AD- en Microsoft 365-beheercentra

Er is een lange en groeiende lijst met [ingebouwde rollen.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Elke rol bestaat uit een lijst met rollenmachtigingen die zijn gegroepeerd zodat specifieke acties kunnen worden uitgevoerd. U kunt deze machtigingen zien op het tabblad Beschrijving binnen elke rol. U kunt ook een beter leesbare versie van deze versies bekijken in het Microsoft 365-beheercentrum. De definities voor ingebouwde rollen kunnen niet worden gewijzigd. Over het algemeen groeper ik deze in drie categorieën:

- **Globale beheerder:** deze 'alle krachtige' rol moet sterk worden [beschermd,](https://docs.microsoft.com/microsoft-365/enterprise/protect-your-global-administrator-accounts) net als in andere systemen. Gebruikelijke aanbevelingen zijn: geen permanente toewijzing en gebruik Azure AD Privileged Identity Management (PIM); sterke verificatie; en zo verder. Het is ook mogelijk dat u met deze rol niet standaard toegang krijgt tot alles. Meestal zie ik verwarring over toegang tot naleving en Azure-toegang, die later worden besproken. Deze rol kan echter altijd toegang toewijzen aan andere services in de tenant. 
- **Specifieke servicebeheerders:** sommige services (Exchange, SharePoint, Power BI, e.d.) gebruiken beheerrollen op hoog niveau van Azure AD. Dit is niet in alle services consistent en er zijn meer servicespecifieke rollen die later worden besproken.
- **Functioneel:** er is een lange (en groeiende) lijst met rollen die zijn gericht op specifieke bewerkingen (gast genodigde, etc.). Regelmatig worden er meer toegevoegd op basis van de behoeften van de klant.

Het is niet mogelijk om alles te delegeren (hoewel de tussenruimte afneemt), wat betekent dat de globale beheerdersrol soms moet worden gebruikt. Bij deze rol moet rekening worden gehouden met configuratie als code en automatisering, in plaats van het lidmaatschap van personen.

**Opmerking:** Het Microsoft 365-beheercentrum heeft een gebruiksvriendelijkere interface, maar heeft een subset van mogelijkheden in vergelijking met de Azure AD-beheerervaring. Beide portals gebruiken dezelfde rollen voor Azure AD, dus vinden wijzigingen plaats op dezelfde plaats. Tip: als u een op identiteitsbeheer gerichte gebruikersinterface voor beheerders wilt zonder al het onbelangrijke Azure, gebruik dan [https://aad.portal.azure.com](https://aad.portal.azure.com) . 

Wat staat er in de naam? Ga niet uit van de naam van de rol. Taal is niet erg nauwkeurig. Het doel is om bewerkingen te definiëren die moeten worden gedelegeerd voordat wordt gekeken welke rollen er nodig zijn. Als u iemand toevoegt aan de rol 'Beveiligingslezer', zien ze niet overal de beveiligingsinstellingen.

De mogelijkheid om aangepaste [rollen te maken](https://docs.microsoft.com/azure/active-directory/users-groups-roles/roles-custom-overview) is een veelvoorkomende vraag. Dit is momenteel beperkt in Azure AD (zie hieronder), maar zal in de tijd steeds meer mogelijkheden krijgen. Ik denk dat deze van toepassing zijn op functies in Azure AD en die mogelijk niet 'omlaag' gaan in het hiërarchiemodel (hierboven besproken). Wanneer ik 'aangepast' ga doen, ga ik meestal terug naar de principal van 'eenvoudig is beter'.

Een andere veelvoorkomende vraag is de mogelijkheid om het bereik van rollen te bepalen tot een subset van een adreslijst. Een voorbeeld is zoiets als 'Helpdeskbeheerder alleen voor gebruikers in de EU'. [Administratieve eenheden](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-administrative-units) (AU) zijn bedoeld om dit probleem op te pakken. Net als hierboven denk ik dat deze van toepassing zijn op functies in Azure AD en mogelijk niet 'omlaag' gaan. Bepaalde rollen hebben natuurlijk geen zin in het bereik (globale beheerders, servicebeheerders, etc.).

Voor al deze rollen is direct lidmaatschap vereist (of dynamische toewijzing als u [Azure AD PIM gebruikt).](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/) Dit betekent dat klanten deze rechtstreeks in Azure AD moeten beheren en dat deze niet kunnen worden gebaseerd op het lidmaatschap van een beveiligingsgroep. Ik ben geen fan van het maken van scripts om deze te beheren, omdat het met verhoogde rechten moet worden uitgevoerd. Ik adviseer over het algemeen API-integratie met processystemen zoals ServiceNow of het gebruik van partnerbeheerhulpprogramma's zoals Saviynt. Er is een technisch werk aan de hand om dit in de weg te staan.

Ik heb [Azure AD PIM een paar](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/) keer vermeld. Er is een bijbehorende MICROSOFT Identity Manager -oplossing (MIM) [Privileged Access Management](https://docs.microsoft.com/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) (PAM) voor on-premises besturingselementen. U kunt ook de paws-werkstations [(Privileged Access Workstations)](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) en [Azure AD Identity Governance bekijken.](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) Er zijn ook verschillende hulpprogramma's van derden waarmee u op tijd, net voldoende en dynamisch rolverheffing kunt inschakelen. Dit maakt meestal deel uit van een grotere discussie over het beveiligen van een omgeving. 

Soms is het nodig om een externe gebruiker toe te voegen aan een rol (zie het gedeelte met meerdere tenants hierboven). Dit werkt prima. [Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/) is een ander groot en leuk onderwerp om klanten door te lopen, misschien in een ander artikel.

### <a name="security-and-compliance-center-scc"></a>Beveiligings- en compliancecentrum (SCC)

[Machtigingen in het Office 365-beveiligings- & compliancecentrum](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) zijn een verzameling 'rollengroepen', die afzonderlijk en verschillen van de rollen van Azure AD. Dit kan verwarrend zijn omdat sommige van deze rollengroepen dezelfde naam hebben als Azure AD-rollen (bijvoorbeeld Beveiligingslezer), maar ze kunnen wel een ander lidmaatschap hebben. Ik geef de voorkeur aan het gebruik van Azure AD-rollen. Elke rollengroep bestaat uit een of meer 'rollen' (zie wat ik bedoel met het hergebruik van hetzelfde woord?) en leden uit Azure AD, die e-mailobjecten zijn. U kunt ook een rollengroep maken met dezelfde naam als een rol, die al dan niet deze rol bevat (vermijd deze verwarring).

In de zin van deze zijn dit een ontwikkeling van het Exchange-rollengroepenmodel. Exchange Online heeft echter een eigen interface [voor rollengroepsbeheer.](https://docs.microsoft.com/exchange/permissions-exo) Sommige rollengroepen in Exchange Online worden vergrendeld en beheerd vanuit Azure AD of het &-compliancecentrum voor beveiliging, maar anderen hebben mogelijk dezelfde of vergelijkbare namen en worden beheerd in Exchange Online (wat tot verwarring leidt). Het is raadzaam de gebruikersinterface van Exchange Online niet te gebruiken, tenzij u een bereik nodig hebt voor Exchange-beheer.

U kunt geen aangepaste rollen maken. Rollen worden gedefinieerd door services die door Microsoft zijn gemaakt en worden steeds groter naarmate er nieuwe services worden geïntroduceerd. Dit is in concept vergelijkbaar met [rollen die zijn gedefinieerd door toepassingen](https://docs.microsoft.com/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) in Azure AD. Wanneer nieuwe services zijn ingeschakeld, moeten er vaak nieuwe rollengroepen worden gemaakt om toegang te verlenen of te delegeren tot deze groepen (bijvoorbeeld [insider-risicobeheer).](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure?view=o365-worldwide#step-1-required-enable-permissions-for-insider-risk-management)

Deze rollengroepen vereisen ook direct lidmaatschap en kunnen geen Azure AD-groepen bevatten. Helaas worden deze rollengroepen momenteel niet ondersteund door Azure AD PIM. Net zoals bij rollen in Azure AD, ben ik geneigd deze te beheren via API's of een partnerbeheerproduct zoals 'Zwaarste' of andere.

Rollen & compliancecentrum in Microsoft 365 en u kunt deze rollengroepen niet beperken tot een subset van de omgeving (zoals dat kan met beheereenheden in Azure AD). Veel klanten vragen hoe ze subdelegate kunnen maken. U kunt bijvoorbeeld 'alleen DLP-beleid maken voor gebruikers in de EU'. Als u op dit moment rechten hebt voor een bepaalde functie in het beveiligings- & compliancecentrum, hebt u de rechten op alles wat wordt gedekt door deze functie in de tenant. Veel beleidsregels hebben echter mogelijkheden om zich te richten op een subset van de omgeving (bijvoorbeeld 'deze labels alleen beschikbaar [maken](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy) voor deze gebruikers'). Een correct beheer en communicatie vormen een belangrijk onderdeel om conflicten te voorkomen. Sommige klanten kiezen ervoor om een 'configuratie als code'-benadering te implementeren om subdelegatie aan te pakken in het & compliancecentrum. Sommige specifieke services ondersteunen subdelegatie (zie hieronder).

De besturingselementen die momenteel worden beheerd via het beveiligings &- en compliancecentrum (protection.office.com), worden gemigreerd naar twee afzonderlijke beheerportals: security.microsoft.com en compliance.microsoft.com. Wijziging is de enige constante.

### <a name="service-specific"></a>Service specifiek

Zoals eerder is gezegd, willen veel klanten een model voor gedetailleerdere delegatie bereiken. Een veelvoorkomende voorbeeld: 'XYZ-service alleen beheren voor Division X-gebruikers en -locaties' (of een andere dimensie). De mogelijkheid om dit te doen is afhankelijk van elke service en is niet consistent voor de services en mogelijkheden. Daarnaast kan elke service een afzonderlijk en uniek RBAC-model hebben. In plaats van deze allemaal te bespreken (het duurt eeuwen), voeg ik relevante koppelingen toe voor elke service. Dit is geen volledige lijst, maar u kunt hiermee aan de slag.

- **Exchange Online** - [https://docs.microsoft.com/exchange/permissions-exo/permissions-exo](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- **SharePoint Online** - [https://docs.microsoft.com/sharepoint/manage-site-collection-administrators](https://docs.microsoft.com/sharepoint/manage-site-collection-administrators) 
- **Microsoft Teams**  -  [https://docs.microsoft.com/microsoftteams/itadmin-readiness](https://docs.microsoft.com/microsoftteams/itadmin-readiness )
- **eDiscovery** - [https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions](https://docs.microsoft.com/microsoft-365/compliance/) 
  + **Machtigingen filteren**  -  [https://docs.microsoft.com/microsoft-365/compliance/permissions-filtering-for-content-search](https://docs.microsoft.com/microsoft-365/compliance/)
  + **Nalevingsgrenzen**  -  [https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries )
  + **Advanced eDiscovery**  -  [https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20 )
- **Yammer** - [https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins) 
- **Multi-geo** - [https://docs.microsoft.com/microsoft-365/enterprise/add-a-sharepoint-geo-admin](https://docs.microsoft.com/microsoft-365/enterprise/add-a-sharepoint-geo-admin) 
- **Dynamics 365** – [https://docs.microsoft.com/dynamics365/](https://docs.microsoft.com/dynamics365/) <br>
  Opmerking: deze koppeling is naar de hoofdmap van de documentatie. Er zijn meerdere soorten services met variaties in het beheer-/delegeringsmodel.
- **Power Platform**  -  [https://docs.microsoft.com/power-platform/admin/admin-documentation](https://docs.microsoft.com/power-platform/admin/admin-documentation )
  + **Power Apps**  -  [https://docs.microsoft.com/power-platform/admin/wp-security](https://docs.microsoft.com/power-platform/admin/wp-security ) <br>
    Opmerking: er zijn meerdere typen met variaties in de beheer-/delegatiemodellen.
  + **Power Automate**  -  [https://docs.microsoft.com/power-automate/environments-overview-admin](https://docs.microsoft.com/power-automate/environments-overview-admin )
  + **Power BI**  -  [https://docs.microsoft.com/power-bi/service-admin-governance](https://docs.microsoft.com/power-bi/service-admin-governance ) <br>
Opmerking: beveiliging en delegatie van gegevensplatforms (Power BI is een onderdeel) is een complex gebied.
- **MEM/Intune**  -  [https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control )
- **Microsoft Defender voor eindpunt**  -  [https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles )
- **Microsoft 365 Defender** - [https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions)
- **Beveiliging van Microsoft Cloud-apps** - [https://docs.microsoft.com/cloud-app-security/manage-admins](https://docs.microsoft.com/cloud-app-security/manage-admins)
- **Streamen**  -  [https://docs.microsoft.com/stream/assign-administrator-user-role](https://docs.microsoft.com/stream/assign-administrator-user-role )
- **Informatiebarrières**  -  [https://docs.microsoft.com/microsoft-365/compliance/information-barriers](https://docs.microsoft.com/microsoft-365/compliance/information-barriers )

Verder was het zoeken in Docs de laatste tijd heel [https://docs.microsoft.com/](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) goed. 

### <a name="activity-logs"></a>Activiteitslogboeken

Office 365 heeft een [geïntegreerd auditlogboek.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) Het is een zeer [gedetailleerd logboek,](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)maar lees niet te veel in de naam. Het bevat mogelijk niet alles wat u nodig hebt of nodig hebt voor uw behoeften op het gebied van beveiliging en naleving. Sommige klanten zijn ook zeer geïnteresseerd in [Geavanceerde controle.](https://docs.microsoft.com/microsoft-365/compliance/advanced-audit)

Voorbeelden van Microsoft 365-logboeken die worden gebruikt via andere API's zijn:

- [Azure AD](https://docs.microsoft.com/azure/azure-monitor/platform/diagnostic-settings) (activiteiten die niet gerelateerd zijn aan Office 365)
- [Berichten bijhouden in Exchange](https://docs.microsoft.com/powershell/module/exchange/get-messagetrace)
- Bedreigings-/UEBA-systemen die hierboven zijn besproken (bijvoorbeeld Azure AD Identity Protection, Microsoft Cloud App Security, Microsoft Defender voor eindpunt, en meer)
- [Microsoft-gegevensbescherming](https://docs.microsoft.com/microsoft-365/compliance/data-classification-activity-explorer?view=o365-worldwide)
- [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft Graph](https://graph.microsoft.com)

Het is belangrijk om eerst alle logboekbronnen te identificeren die nodig zijn voor een beveiligings- en nalevingsprogramma. Houd er ook rekening mee dat verschillende logboeken verschillende bewaarlimieten per regel hebben. 

Vanuit het beheerdelegerings perspectief hebben de meeste Activiteitenlogboeken van Microsoft 365 geen ingebouwd RBAC-model. Als u bent machtigingen hebt om een logboek te bekijken, kunt u alles in het logboek zien. Een veelvoorkomende voorbeeld van klantvereiste is: "Ik wil alleen een query kunnen uitvoeren op activiteiten van de EU-gebruikers" (of een andere dimensie). Hiervoor moeten logboeken naar een andere service worden overdraagd. In de Microsoft-cloud wordt u aangeraden deze over te brengen naar [Azure Eerst](https://docs.microsoft.com/azure/sentinel/overview) of [Logboekanalyse.](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) 

Diagram op hoog niveau:

![diagram van logboekbronnen voor een beveiligings- en nalevingsprogramma](../media/solutions-architecture-center/identity-beyond-illustration-4.png)  

Het bovenstaande diagram vertegenwoordigt ingebouwde mogelijkheden voor het verzenden van logboeken naar de Event Hub en/of Azure Storage en/of Azure Log Analytics. Nog niet in alle systemen is deze gebruiks klaar. Er zijn echter andere methoden om deze logboeken naar dezelfde opslagplaats te verzenden. Zie bijvoorbeeld [Uw Teams beschermen met Azure Azure Azure.](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761)

Als u alle logboeken op één opslaglocatie combineert, omvat dit extra voordeel, zoals correlaties, aangepaste bewaartijden, aanvulling met gegevens die nodig zijn om het RBAC-model te ondersteunen, en dergelijke. Als de gegevens in dit opslagsysteem zijn opgeslagen, kunt u een Power BI-dashboard (of een ander type visualisatie) maken met een geschikt RBAC-model.

Logboeken hoeft niet alleen naar één plek te worden doorgestuurd. Het kan ook nuttig zijn om [Office 365-logboeken](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) te integreren met Microsoft Cloud App Security of een aangepast RBAC-model in [Power BI.](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics?view=o365-worldwide) Verschillende opslagplaatsen hebben verschillende voordelen en doelgroepen.

Het is de moeite waard om te vermelden dat er een zeer uitgebreid ingebouwd analysesysteem is voor beveiliging, bedreigingen, beveiligingsproblemen, en meer in een service met de naam [Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)

Veel grote klanten willen deze logboekgegevens overbrengen naar een systeem van derden (bijvoorbeeld SIEM). Hiervoor zijn verschillende benaderingen beschikbaar, maar over het algemeen [zijn Azure Event Hub](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) en [Graph](https://docs.microsoft.com/graph/security-integration) een goed uitgangspunt.

### <a name="azure"></a>Azure

Mij wordt vaak gevraagd of er een manier is om rollen met hoge bevoegdheden te scheiden tussen Azure AD, Azure en SaaS (bijvoorbeeld: globale beheerder voor Office 365, maar niet Azure).  Niet echt.  Architectuur met meerdere tenants is nodig als een volledige beheerscheiding is vereist, maar die de complexiteit wel aanzienlijk complex [maakt](https://aka.ms/multi-tenant-user) (zie boven). Al deze services maken deel uit van dezelfde beveiligings-/identiteitsgrens (kijk naar het bovenstaande hiërarchiemodel).  

Het is belangrijk om de relaties tussen verschillende services in dezelfde tenant te begrijpen. Ik werk met veel klanten die bedrijfsoplossingen bouwen voor Azure, Office 365 en Power Platform (en vaak ook on-premises cloudservices en externe cloudservices). Een veelvoorkomende voorbeeld:

1. Ik wil samenwerken aan een set documenten/afbeeldingen/enzovoort (Office 365)
2. Elk van deze verzenden via een goedkeuringsproces (Power Platform)
3.  Nadat alle onderdelen zijn goedgekeurd, kunt u deze samenstellen tot een geïntegreerde Microsoft [Graph API](https://docs.microsoft.com/azure/active-directory/develop/microsoft-graph-intro) (Deliverable(s) die u het best kunt gebruiken.  Niet onmogelijk, maar aanzienlijk ingewikkelder om een oplossing te ontwerpen die meerdere [tenants omspant.](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)

Azure Role-Based Access Control (RBAC) maakt fijnac-toegangsbeheer voor Azure mogelijk. Met toegangsstructuur kunt u de toegang tot resources beheren door gebruikers de minste machtigingen te verlenen die nodig zijn om hun taken uit te voeren. Details van dit document zijn buiten het bereik, maar zie Wat is toegangsbeheer op basis van rollen in Azure voor meer informatie over toegangsbeheer op basis van [rollen?](https://docs.microsoft.com/azure/role-based-access-control/overview) Beheerstructuur is belangrijk, maar maakt slechts deel uit van de beheeroverwegingen voor Azure. [Cloud Adoption Framework](https://docs.microsoft.com/azure/cloud-adoption-framework/govern/) is een goed uitgangspunt voor meer informatie. Ik vind het leuk hoe mijn vriend AndresInet klanten stap voor stap door diverse onderdelen laat lopen om de aanpak te bepalen. De weergave op hoog niveau voor verschillende elementen (niet zo goed als het proces om het werkelijke klantmodel te krijgen) is zoiets als:

![Weergave op hoog niveau van Azure-onderdelen voor gedelegeerd beheer](../media/solutions-architecture-center/identity-beyond-illustration-5.png)

Zoals u in de bovenstaande afbeelding ziet, moeten veel andere services [](https://docs.microsoft.com/azure/governance/policy/overview)worden beschouwd als onderdeel van het ontwerp (bijvoorbeeld: Azure-beleid, [Azure Blauwdrukken,](https://docs.microsoft.com/azure/governance/blueprints/overview) [Beheergroepen,](https://docs.microsoft.com/azure/governance/management-groups/)etc.).

## <a name="conclusion"></a>Conclusie

Gestart als een kort overzicht, maar het duurt langer dan verwacht.  Ik hopen dat u er alles aan kunt doen om een delegatiemodel voor uw organisatie te maken.  Dit gesprek is zeer gebruikelijk bij klanten. Er is geen model dat voor iedereen werkt. Wacht op een paar geplande verbeteringen van Microsoft Engineering voordat u gemeenschappelijke patronen documenteert die we bij klanten zien. Ondertussen kunt u samen met uw Microsoft-accountteam een bezoek brengen aan het [dichtstbijzijnde Microsoft Technology Center.](https://www.microsoft.com/mtc)  Tot daar!
