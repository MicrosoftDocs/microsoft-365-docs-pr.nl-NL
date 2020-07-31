---
title: Naar identiteit en daarbuiten — Het gezichtspunt van één architect
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
ms.openlocfilehash: 0a4dd8c3c93402409863b18b400184d4e60eeee6
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/29/2020
ms.locfileid: "46521039"
---
# <a name="to-identity-and-beyond--one-architects-viewpoint"></a>Naar identiteit en daarbuiten — Het gezichtspunt van één architect

In dit artikel bespreekt [Alex Shteynberg](https://www.linkedin.com/in/alex-shteynberg/), Principal Technical Architect bij Microsoft, topontwerpstrategieën voor bedrijfsorganisaties die Microsoft 365 en andere Microsoft-cloudservices adopteren.

## <a name="about-the-author"></a>Over de auteur

:::image type="content" source="../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg" alt-text="Foto Alex Shteynberg":::

Ik ben een Principal Technical Architect bij het New York [Microsoft Technology Center](https://www.microsoft.com/mtc?rtc=1). Ik werk vooral met grote klanten en complexe eisen. Mijn standpunt en meningen zijn gebaseerd op deze interacties en kunnen niet op elke situatie van toepassing zijn. Echter, in mijn ervaring, als we klanten kunnen helpen met de meest complexe uitdagingen, kunnen we alle klanten helpen. 

Ik werk meestal met meer dan 100 klanten per jaar. Hoewel elke organisatie unieke kenmerken heeft, is het interessant om trends en overeenkomsten te zien. Een trend is bijvoorbeeld brancheoverschrijdende interesse voor veel klanten. Een bankfiliaal kan immers ook een koffieshop en een buurthuis zijn. 

In mijn rol richt ik me op het helpen van klanten om tot de beste technische oplossing te komen om hun unieke set van zakelijke doelen aan te pakken. Officieel richt ik me op identiteit, beveiliging, privacy en compliance. Ik hou van het feit dat deze raken alles wat we doen. Het geeft me de kans om betrokken te zijn bij de meeste projecten. Dit houdt me heel druk en genieten van deze rol. 

Ik woon in New York City ( de beste!) en echt genieten van de diversiteit van de cultuur, eten en mensen ( niet verkeer). Ik hou van reizen wanneer ik kan en hoop het grootste deel van de wereld te zien in mijn leven. Ik ben momenteel onderzoek naar een reis naar Afrika om te leren over wilde dieren.

## <a name="guiding-principles"></a>Richtsnoeren 

- **Eenvoudig is vaak beter** - U (bijna) alles doen met technologie. Dat betekent niet dat je dat moet doen. Vooral in de beveiligingsruimte, veel klanten overengineer oplossingen. Ik hou van [deze video](https://www.youtube.com/watch?v=SOQgABDSYZE) van Google's Stripe conferentie om dit punt te onderstrepen.
- **Mensen, proces, technologie** - [Ontwerp voor mensen](https://en.wikipedia.org/wiki/Human-centered_design) om het proces te verbeteren, niet eerst tech. Er zijn geen "perfecte" oplossingen. We moeten verschillende risicofactoren in evenwicht brengen en beslissingen zullen voor elk bedrijf verschillend zijn. Te veel klanten ontwerpen een aanpak die hun gebruikers later vermijden.
- **Focus op 'waarom' eerste en 'hoe' later** - Wees de vervelende 7 jaar oude jongen met een miljoen vragen. We kunnen niet tot het juiste antwoord komen als we niet de juiste vragen weten. Veel klanten maken veronderstellingen over hoe dingen moeten werken in plaats van het definiëren van het zakelijke probleem. Er zijn altijd meerdere paden die kunnen worden genomen.
- **Lange staart van aanbevolen procedures uit het verleden** - Erken dat best practices veranderen bij lichtsnelheid. Als u azure AD meer dan 3 maanden geleden hebt bekeken, bent u waarschijnlijk verouderd. Alles is hier onder voorbehoud van verandering na publicatie. "Beste" optie vandaag kan niet dezelfde 6 maanden vanaf nu.

## <a name="baseline-concepts"></a>Basislijnconcepten

Sla deze sectie niet over. Ik vind vaak dat ik een stap terug moet doen naar deze onderwerpen, zelfs voor klanten die al jaren cloudservices gebruiken.
Helaas, taal is niet een nauwkeurig instrument. We gebruiken vaak hetzelfde woord om verschillende concepten of verschillende woorden te betekenen om hetzelfde concept te betekenen. Ik gebruik dit diagram hieronder vaak om een aantal basislijnterminologie en 'hiërarchiemodel' vast te stellen.
<br><br>

![Illustratie van tenant, abonnement, service en gegevens](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)  

<br>

Wanneer je leert zwemmen is het beter om te beginnen in het zwembad en niet in het midden van de oceaan. Ik probeer niet technisch nauwkeurig te zijn met dit diagram. Het is een model om een aantal basisconcepten te bespreken. 

In het diagram:
- Tenant = een exemplaar van Azure AD. Het is aan de "top" van een hiërarchie, of niveau 1 in het diagram. We kunnen dit beschouwen als de "[grens](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-directory-independence)" waar al het andere gebeurt ([Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) opzij). Alle Cloudservices voor Microsoft-ondernemingen maken deel uit van een van deze tenants. Consumentendiensten staan los van elkaar. 'Tenant' wordt weergegeven in documentatie als Office 365-tenant, Azure-tenant, WVD-tenant, enz. Ik vind vaak deze variaties verwarring veroorzaken voor klanten.
- Services/abonnementen, niveau 2 in het diagram, behoren tot één en slechts één tenant. De meeste SaaS-services zijn 1:1 en kunnen niet bewegen zonder migratie. Azure is anders, u facturering en/of een [abonnement](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) [verplaatsen](https://docs.microsoft.com/azure/cost-management-billing/manage/billing-subscription-transfer) naar een andere tenant. Er zijn veel klanten die Azure-abonnementen moeten verplaatsen. Dit heeft verschillende implicaties. Objecten die buiten het abonnement bestaan (bijvoorbeeld RBAC- en Azure AD-objecten, waaronder groepen, apps, beleidsregels, enz.) worden niet verplaatst. Sommige services (Azure Key Vault, Data Bricks, enz.) worden ook in een niet-functionele status verplaatst. Migreer geen services zonder een goede zakelijke behoefte. Sommige scripts die nuttig kunnen zijn voor migratie worden [gedeeld op GitHub.](https://github.com/lwajswaj/azure-tenant-migration) 
- Een bepaalde service heeft meestal een soort van "sub-level" grens, of Niveau 3 (L3). Dit is handig om te begrijpen voor segregatie van veiligheid, beleid, governance, enz. Helaas is er geen uniforme naam die ik ken. Enkele voorbeelden namen voor L3 zijn: Azure Subscription = [resource](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resources-portal); Dynamics 365 CE = [instance](https://docs.microsoft.com/dynamics365/admin/new-instance-management); Power BI = [werkruimte](https://docs.microsoft.com/power-bi/service-create-the-new-workspaces); Power Apps = [omgeving](https://docs.microsoft.com/power-platform/admin/environments-overview); Enz.
- Niveau 4 is waar de werkelijke gegevens leven. Dit 'datavlak' is een complex onderwerp. Sommige services gebruiken Azure AD voor RBAC, andere niet. Ik zal het een beetje bespreken als we bij de delegatie onderwerpen.

Enkele aanvullende concepten die ik veel klanten (en Microsoft-medewerkers) vind, zijn verward over of hebben vragen over zijn de volgende:


- Iedereen kan veel huurders [maken](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) [zonder kosten.](https://azure.microsoft.com/pricing/details/active-directory/) U hebt geen dienst nodig die erin is ingericht. Ik heb er tientallen. Elke tenantnaam is uniek in de wereldwijde cloudservice van Microsoft (dat wil zeggen dat geen twee tenants dezelfde naam kunnen hebben). Ze zijn allemaal in het formaat van TenantName.onmicrosoft.com. Er zijn ook processen die automatisch tenants maken[(onbeheerde tenants).](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup) Dit kan bijvoorbeeld gebeuren wanneer een gebruiker zich aanmeldt voor een bedrijfsservice met een e-maildomein dat niet in een andere tenant bestaat. 
- In een beheerde tenant kunnen veel [DNS-domeinen](https://docs.microsoft.com/azure/active-directory/fundamentals/add-custom-domain) daarin worden geregistreerd. Dit verandert niets aan de oorspronkelijke tenantnaam. Er is momenteel geen eenvoudige manier om de naam van een tenant te wijzigen (anders dan migratie). Hoewel de naam van de huurder tegenwoordig technisch niet kritisch is, kunnen sommigen dit beperkend vinden.
- U moet een tenantnaam reserveren voor uw organisatie, zelfs als u nog niet van plan bent services te implementeren. Anders kan iemand het van u afnemen en is er geen eenvoudig proces om het terug te nemen (hetzelfde probleem als DNS-namen). Ik hoor dit veel te vaak van klanten. Wat uw huurder naam moet worden is een debat onderwerp ook.
- Als u eigenaar bent van DNS-naamruimte(en), moet u deze allemaal toevoegen aan uw tenant(s). Anders zou men een [onbeheerde huurder](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup) met deze naam kunnen creëren die dan verstoring veroorzaakt om het beheerd te [maken.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)
- DNS-naamruimte (bijvoorbeeld contoso.com) kan tot één en slechts één tenant behoren. Dit heeft implicaties voor verschillende scenario's (bijvoorbeeld het delen van een e-maildomein tijdens een fusie of overname, enz.) Er is een manier om een DNS-sub (bijvoorbeeld div.contoso.com) te registreren in een andere tenant, maar dat moet worden vermeden. Door een domeinnaam op het hoogste niveau te registreren, worden alle subdomeinen verondersteld tot dezelfde tenant te behoren. In multi-tenant scenario's (zie hieronder) zou ik normaal gesproken aanraden om een andere domeinnaam op het hoogste niveau te gebruiken (bijvoorbeeld contoso.ch of ch-contoso.com).
- Wie moet een huurder "bezitten"? Ik zie vaak klanten die niet weten wie momenteel eigenaar is van hun huurder. Dit is een grote rode vlag. Bel Microsoft-ondersteuning zo snel mogelijk. Net zo problematisch is wanneer een service-eigenaar (vaak een Exchange-beheerder) is aangewezen om een tenant te beheren. De huurder bevat alle services die u in de toekomst wilt. De eigenaar van de huurder moet een groep zijn die een beslissing kan nemen voor het inschakelen van alle cloudservices in een organisatie. Een ander probleem is wanneer een tenant-eigenaargroep wordt gevraagd om alle services te beheren. Dit schaalt niet voor grote organisaties.
- Er is geen concept van een sub / super huurder. Om de een of andere reden blijft deze mythe zich herhalen. Dit geldt ook voor [Azure AD B2C-tenants.](https://docs.microsoft.com/azure/active-directory-b2c/) Ik hoor te vaak: 'Mijn B2C-omgeving bevindt zich in mijn XYZ-tenant' of 'Hoe verplaats ik mijn Azure-tenant naar mijn Office 365-tenant?'
- Dit document richt zich voornamelijk op de commerciële wereldwijde cloud, omdat dit is wat de meeste klanten gebruiken. Het is soms handig om te weten over [soevereine wolken](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud). Soevereine wolken hebben extra implicaties om te bespreken welke buiten de mogelijkheden voor deze discussie.


## <a name="baseline-identity-topics"></a>Identiteitsonderwerpen basislijn

Er is veel documentatie over het identiteitsplatform van Microsoft : Azure Active Directory (Azure AD). Voor degenen die net beginnen, voelt het vaak overweldigend. Zelfs nadat je er meer over te weten bent, kan het een uitdaging zijn om constant te innoveren en te veranderen. In mijn klantinteracties vind ik mezelf vaak als "vertaler" tussen zakelijke doelen en "Goede, Betere, Beste" benaderingen om deze (evenals menselijke "cliff notes" voor deze onderwerpen aan te pakken). Er is zelden een perfect antwoord en de "juiste" beslissing is een balans van verschillende risicofactoren. Hieronder staan enkele van de gemeenschappelijke vragen en verwarring gebieden die ik de neiging om te bespreken met klanten.

### <a name="provisioning"></a>Provisioning
Azure AD lost niet op bij gebrek aan governance in uw identiteitswereld! [Identiteitsbeheer](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) moet een cruciaal element zijn, onafhankelijk van eventuele cloudbeslissingen. Governance vereisten veranderen in de tijd dat is waarom het een programma en niet een instrument. 

[Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect) vs. [Microsoft Identity Manager](https://docs.microsoft.com/microsoft-identity-manager/microsoft-identity-manager-2016) (MIM) vs. iets anders (3rd party of custom)? Bespaar jezelf een hoop hoofdpijn nu en in de toekomst en ga met Azure AD Connect. Er zijn allerlei smarts in deze tool om eigenaardige klantconfiguraties en voortdurende innovaties aan te pakken. 

Enkele randcases die naar een complexere architectuur kunnen leiden:
- Ik heb meerdere AD-bossen zonder netwerkconnectiviteit tussen deze. Er is een nieuwe optie genaamd [Cloud Provisioning](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning).
- Ik heb geen Active Directory, noch wil ik het installeren. Azure AD Connect kan worden geconfigureerd om te [synchroniseren vanaf LDAP](https://docs.microsoft.com/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) (partner is mogelijk vereist).
- Ik moet dezelfde objecten aan meerdere huurders leveren. Dit wordt niet technisch ondersteund, maar hangt af van de definitie van 'hetzelfde'.

Moet ik standaardsynchronisatieregels aanpassen[(filterobjecten,](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering)kenmerken wijzigen, [alternatieve aanmeldings-ID,](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-userprincipalname)enz.)? [change attributes](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) Vermijd het! Een identiteitsplatform is slechts zo waardevol als de services die het gebruiken. Terwijl u allerlei gekke configuraties doen, moet u om deze vraag te beantwoorden de impact op toepassingen bekijken. Als u objecten met e-mail filtert, is de GAL voor online services onvolledig. als de toepassing afhankelijk is van specifieke kenmerken, zal het filteren van deze onvoorspelbare gevolgen hebben; Enz. Het is geen beslissing van het identiteitsteam.

XYZ SaaS ondersteunt Just-in-Time (JIT) provisioning, waarom moet ik synchroniseren? Zie het bovenstaande. Veel toepassingen hebben "profiel" informatie nodig voor functionaliteit. U geen GAL hebben als niet alle objecten met e-mail beschikbaar zijn. Hetzelfde geldt voor [gebruikersinrichting](https://docs.microsoft.com/azure/active-directory/app-provisioning/user-provisioning) in toepassingen die zijn geïntegreerd met Azure AD.


### <a name="authentication"></a>Verificatie

[Password hash sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) (PHS) vs. [pass-through authentication](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) (PTA) vs. [federation](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility).

Gewoonlijk is er een hartstochtelijk [debat](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) rond federatie. Eenvoudiger is meestal beter en daarom gebruik maken van PHS, tenzij je een goede reden om niet te doen. Het is ook mogelijk om verschillende verificatiemethoden te configureren voor verschillende DNS-domeinen in dezelfde tenant. 

Sommige klanten maken federatie + PHS voornamelijk mogelijk voor:
- Een optie om terug te [vallen](https://docs.microsoft.com/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) naar (voor noodherstel) als de federatieservice niet beschikbaar is.
- Aanvullende mogelijkheden (bijvoorbeeld [Azure AD DS)](https://docs.microsoft.com/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)en beveiligingsservices (bijvoorbeeld [gelekte referenties)](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials)
- Ondersteuning voor services in Azure die geen inzicht krijgen in federatieverificatie (bijvoorbeeld [Azure Files).](https://docs.microsoft.com/azure/storage/files/storage-files-active-directory-overview)

Ik loop vaak klanten door client authenticatie stroom om een aantal misvattingen te verduidelijken. Het resultaat lijkt op de foto hieronder, die niet zo goed als het interactieve proces om er te komen.

:::image type="content" source="../media/solutions-architecture-center/identity-beyond-whiteboard-example.png" alt-text="voorbeeld whiteboardgesprek":::

Dit type whiteboardtekening illustreert waar beveiligingsbeleid wordt toegepast binnen de stroom van een verificatieverzoek. In dit voorbeeld worden beleidsregels die worden afgedwongen via Ad FS (Active Directory Federation Service) toegepast op de eerste serviceaanvraag, maar niet op latere serviceaanvragen. Dit is ten minste één reden om beveiligingscontroles zoveel mogelijk naar de cloud te verplaatsen.

We jagen al zo lang als ik me kan herinneren aan de droom van [single sign-on](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) (SSO). Sommige klanten geloven dat ze dit kunnen bereiken door te kiezen voor de "juiste" federatie (STS) provider. Azure AD kan aanzienlijk helpen om [SSO-mogelijkheden in](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-sso-deployment) te schakelen, maar geen STS is magisch. Er zijn te veel "legacy" authenticatie methoden die nog steeds worden gebruikt voor kritieke toepassingen. Door Azure AD uit te breiden met [partneroplossingen](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) kunnen veel van deze scenario's worden aangepakt. SSO is een strategie en een reis. Je er niet komen zonder te bewegen in de richting van [normen voor toepassingen.](https://docs.microsoft.com/azure/active-directory/develop/v2-app-types) Gerelateerd aan dit onderwerp is een reis naar [wachtwoordloze](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless) authenticatie die ook niet over een magisch antwoord. 

[Multi-factor authenticatie](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) is essentieel vandaag[(hier](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) voor meer). Voeg toe aan het [gebruikersgedrag analytics](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) en je hebt een oplossing die de meerderheid van de gemeenschappelijke cyber-aanvallen voorkomt. Zelfs consumentendiensten verhuizen naar MFA vereisen. Toch ontmoet ik nog steeds veel klanten die niet willen overstappen naar [moderne authenticatiebenaderingen.](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) Het grootste argument dat ik hoor is dat het van invloed zal zijn op gebruikers en oudere toepassingen. Soms kan een goede kick klanten helpen mee te gaan - Exchange Online [kondigde wijzigingen aan.](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282) Veel Azure [AD-rapporten](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) zijn nu beschikbaar om klanten te helpen met deze overgang.



### <a name="authorization"></a>Vergunning

Per [Wikipedia](https://en.wikipedia.org/wiki/Authorization)is "autoriseren" het definiëren van een toegangsbeleid. Veel mensen zien het als de mogelijkheid om toegangscontroles tot een object te definiëren (bestand, service, enz.). In de huidige wereld van cyberbedreigingen evolueert dit concept snel naar een dynamisch beleid dat kan reageren op verschillende bedreigingsvectoren en de toegangscontroles snel kan aanpassen als reactie hierop. Als ik bijvoorbeeld mijn bankrekening vanaf een ongebruikelijke locatie open, krijg ik extra bevestigingsstappen. Om dit te benaderen, moeten we niet alleen rekening houden met het beleid zelf, maar ook naar het ecosysteem van methodologieën voor bedreigingsdetectie en signaalcorrelatie.

De beleidsengine van Azure AD wordt geïmplementeerd met [het beleid voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview). Dit systeem is afhankelijk van informatie van verschillende andere systemen voor bedreigingsdetectie om dynamische beslissingen te nemen. Een eenvoudige mening zou iets als de volgende illustratie zijn.

:::image type="content" source="../media/solutions-architecture-center/identity-and-beyond-illustration-3.png" alt-text="Beleidsengine in Azure AD":::

Het combineren van al deze signalen zorgt voor dynamisch beleid als deze:
- Als een bedreiging wordt gedetecteerd op uw apparaat, wordt uw toegang tot gegevens beperkt tot het web alleen zonder de mogelijkheid om te downloaden.
- Als u een ongewoon hoog volume aan gegevens downloadt, wordt alles wat u downloadt versleuteld en beperkt.
- Als u een service opent vanaf een onbeheerd apparaat, wordt u geblokkeerd voor zeer gevoelige gegevens, maar hebt u toegang tot niet-beperkte gegevens zonder de mogelijkheid om deze naar een andere locatie te kopiëren.

Als u akkoord gaat met deze uitgebreide definitie van autorisatie, moet u aanvullende oplossingen implementeren. Welke oplossingen u implementeert, hangt af van hoe dynamisch u het beleid wilt hebben en welke bedreigingen u prioriteit wilt geven. Enkele voorbeelden van dergelijke systemen zijn:
- [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/) 
- [Azure Advanced Threat Protection](https://docs.microsoft.com/azure-advanced-threat-protection/) (Azure ATP)
- [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) (Microsoft Defender ATP)
- [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (AtP voor Office 365)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/) (MCAS)
- [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide) (MTP)
- [Microsoft Intune](https://docs.microsoft.com/mem/intune/)
- [Microsoft Information Protection](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) (MIP)
- [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/) 

Naast Azure AD hebben verschillende services en toepassingen natuurlijk ook hun eigen specifieke autorisatiemodellen. Sommige daarvan worden later in de delegatiesectie besproken.

### <a name="audit"></a>Audit
Azure AD heeft gedetailleerde [controle- en rapportagemogelijkheden.](https://docs.microsoft.com/azure/active-directory/reports-monitoring/) Dit is echter meestal niet de enige bron van informatie die nodig is om beveiligingsbeslissingen te nemen. Zie meer discussie hierover in de afdeling delegatie.

## <a name="there-is-no-exchange"></a>Er is geen Exchange

Raak niet in paniek! Dit betekent niet dat Exchange wordt afgeschaft (of SharePoint, enz.) Het is nog steeds een kernservice. Wat ik bedoel is, al geruime tijd, technologie providers zijn de overgang van gebruikerservaringen (UX) om componenten van meerdere diensten omvatten. In Microsoft 365 is een eenvoudig voorbeeld "[moderne bijlagen](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)" waar bijlagen voor e-mail worden opgeslagen in SharePoint Online of OneDrive voor Bedrijven. 

:::image type="content" source="../media/solutions-architecture-center/modern-attachments.png" alt-text="een bestand aan een e-mail koppelen":::


Als u naar de Outlook-client kijkt, ziet u veel services die als onderdeel van deze ervaring zijn "verbonden", niet alleen Exchange. Dit omvat Azure AD-, Microsoft Search-, Apps-, Profiel-, nalevings- en Office 365-groepen. 

:::image type="content" source="../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png" alt-text="Outlook-interface met bijschriften":::

Lees meer over [Microsoft Fluid Framework](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) voor een voorbeeld van aankomende mogelijkheden. In preview nu, kan ik lezen en beantwoorden aan Teams gesprekken rechtstreeks in Outlook. In feite is de [Teams-client](https://products.office.com/microsoft-teams/download-app) een van de meest prominente voorbeelden van deze strategie. 

Over het algemeen wordt het steeds moeilijker om een duidelijke lijn te trekken tussen Office 365 en andere services in Microsoft-clouds. Ik beschouw het als een groot voordeel voor klanten, omdat ze kunnen profiteren van totale innovatie in alles wat we doen, zelfs als ze gebruik maken van een component. Pretty cool en heeft verregaande gevolgen voor veel klanten.

Vandaag vind ik veel it-groepen van klanten zijn gestructureerd rond "producten." Het is logisch voor een on-premises wereld, omdat je een expert nodig hebt voor elk specifiek product. Ik ben echter helemaal blij dat ik nooit meer een Active Directory- of Exchange-database hoef te debuggen, omdat deze services naar de cloud zijn verhuisd. Automatisering (die cloud soort is) verwijdert bepaalde repetitieve handmatige taken (kijk wat er gebeurd is met fabrieken). Deze worden echter vervangen door complexere vereisten om inzicht te krijgen in interactie tussen services, impact, bedrijfsbehoeften, enz. Als u bereid bent om te [leren,](https://docs.microsoft.com/learn/)zijn er grote mogelijkheden ingeschakeld door cloud transformatie. Voordat ik in technologie spring, praat ik vaak met klanten over het managen van verandering in IT-vaardigheden en teamstructuren.

Voor alle SharePoint-fans en ontwikkelaars u stoppen met vragen :Hoe kan ik XYZ online in SharePoint doen? Gebruik [Power Automate](https://docs.microsoft.com/power-automate/) (aka Flow) voor workflow, het is een veel krachtiger platform. Gebruik [Azure Bot Framework](https://docs.microsoft.com/azure/bot-service/?view=azure-bot-service-4.0) om een betere UX te maken voor uw 500K-itemslijst. Start met [Microsoft Graph](https://developer.microsoft.com/graph/) in plaats van CSOM. [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview) bevat SharePoint, maar ook een wereld meer. Er zijn vele andere voorbeelden die ik kan noemen. Er is een uitgestrekt en prachtig universum daarbuiten. Open de deur en [begin met het verkennen.](https://docs.microsoft.com)

De andere gemeenschappelijke impact is in het nalevingsgebied. Deze cross-services benadering lijkt veel nalevingsbeleid volledig in verwarring te brengen. Ik blijf organisaties zien die zeggen: "Ik moet alle e-mailcommunicatie naar een eDiscovery-systeem in dagboeken." Wat betekent dit eigenlijk wanneer e-mail niet langer alleen e-mail is, maar een venster op andere services? Office 365 heeft een uitgebreide benadering voor [compliance,](https://docs.microsoft.com/microsoft-365/compliance/)maar het veranderen van mensen en processen is vaak veel moeilijker dan technologie.

Er zijn veel andere mensen en proces implicaties. Naar mijn mening is dit een kritisch en onderbeoordeeld gebied. Misschien meer in een ander artikel.

## <a name="tenant-structure-options"></a>Opties voor tenantstructuur

### <a name="single-tenant-vs-multi-tenant"></a>Eén tenant versus multi-tenant

Over het algemeen zouden de meeste klanten slechts één productiehuurder moeten hebben. Er zijn vele redenen waarom meerdere huurders zijn uitdagend (geef het een [Bing zoeken)](https://www.bing.com/search?q=office%20365%20multiple%20tenants)of lees deze [whitepaper](https://aka.ms/multi-tenant-user). Tegelijkertijd hebben veel zakelijke klanten waarmee ik werk een andere (kleine) tenant voor IT-leren, testen en experimenteren. Azure-toegang voor meerdere tenanten wordt eenvoudiger gemaakt met [Azure Lighthouse](https://azure.microsoft.com/services/azure-lighthouse/). Office 365 en veel andere SaaS-services hebben beperkingen voor cross-tenant scenario's. Er is veel om rekening mee te houden in [Azure AD B2B-scenario's.](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)

Veel klanten eindigen na een fusie en overname bij meerdere productiehuurders (M&A) en willen consolideren. Vandaag de dag is dat niet eenvoudig en zou microsoft Consulting Services (MCS) of een partner plus software van derden vereisen. Er is een lopende engineering werk om verschillende scenario's met multi-tenant klanten in de toekomst aan te pakken. 

Sommige klanten kiezen ervoor om met meer dan één tenant te gaan. Dit moet een zeer zorgvuldige beslissing en bijna altijd zakelijke reden gedreven! Enkele voorbeelden zijn:
- Een holding type bedrijf structuur waar een gemakkelijke samenwerking tussen verschillende entiteiten niet nodig is en er sterke administratieve en andere isolatie behoeften.
- Na een overname wordt een zakelijke beslissing genomen om twee entiteiten gescheiden te houden.
- Simulatie van de omgeving van een klant die de productieomgeving van de klant niet verandert. 
- Ontwikkeling van software voor klanten.

In deze scenario's met meerdere tenants willen klanten sommige configuraties vaak hetzelfde houden voor tenants, of rapporteren over configuratiewijzigingen en drifts. Dit betekent vaak dat u van handmatige wijzigingen naar de configuratie als code moet worden verplaatst. Microsoft Premiere-ondersteuning biedt een workshop voor dit soort vereisten op basis van dit openbare IP-adres: [https://Microsoft365dsc.com](https://Microsoft365dsc.com) .


### <a name="multi-geo"></a>Multi-Geo 

Om [Multi-Geo](https://docs.microsoft.com/office365/enterprise/office-365-multi-geo) of niet naar Multi-Geo, dat is de vraag. Met Office 365 Multi-Geo u gegevens in rust inrichten en opslaan op de geolocaties die u hebt gekozen om te voldoen aan de vereisten voor [gegevensresidentie.](https://docs.microsoft.com/office365/enterprise/o365-data-locations) Er zijn veel misvattingen over dit vermogen. Houd het volgende in gedachten: 
- Het biedt geen prestatievoordelen. Het kan de prestaties verslechteren als het [netwerkontwerp](https://aka.ms/office365networking) niet correct is. Laat apparaten 'dicht' bij het Microsoft-netwerk komen, niet per se bij uw gegevens.
- Het is geen oplossing voor [GDPR-naleving.](https://www.microsoft.com/trust-center/privacy/gdpr-overview) Gdpr richt zich niet op gegevenssoevereiniteit of opslaglocaties. Daar zijn andere nalevingskaders voor.
- Het lost de delegatie van administratie (zie hieronder) of [informatiebarrières](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)niet op .
- Het is niet hetzelfde als multi-tenant en vereist extra [workflows voor het inrichten van gebruikers.](https:/docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation)
- Uw [tenant (uw](https://docs.microsoft.com/office365/enterprise/moving-data-to-new-datacenter-geos) Azure AD) wordt niet verplaatst naar een andere geografie. 

## <a name="delegation-of-administration"></a>Delegatie van de administratie

In de meeste grote organisaties is scheiding van taken en role-based access control (RBAC) een noodzakelijke realiteit. Ik ga me van tevoren verontschuldigen. Dit is niet zo eenvoudig als sommige klanten willen dat het is. Klant,juridische, naleving, en andere eisen zijn verschillend en soms tegenstrijdig over de hele wereld. Eenvoud en flexibiliteit zijn vaak aan tegenovergestelde kanten van elkaar. Begrijp me niet verkeerd, we kunnen dit beter doen. Er zijn (en zal) aanzienlijke verbeteringen in de tijd. Bezoek uw lokale [Microsoft Technology Center](https://www.microsoft.com/mtc) om het model uit te werken dat aan uw zakelijke vereisten voldoet zonder 379230-documenten te lezen! Hier zal ik me concentreren op waar je aan moet denken en niet waarom het zo is. Hieronder zijn vijf verschillende gebieden te plannen voor en een aantal van de gemeenschappelijke vragen die ik ben tegengekomen.

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Azure AD- en Microsoft 365-beheercentra

Er is een lange en groeiende lijst van [ingebouwde rollen.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Elke rol bestaat uit een lijst met functiemachtigingen die zijn gegroepeerd om specifieke acties uit te voeren. U deze machtigingen in elke rol bekijken op het tabblad Beschrijving. U ook een meer menselijke leesbare versie van deze in het Microsoft 365 Admin Center. De definities voor ingebouwde rollen kunnen niet worden gewijzigd. Ik in het algemeen, groepeer deze in drie categorieën:

- **Global administrator** - Deze "alle krachtige" rol moet sterk worden [beschermd,](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) net als in andere systemen. Typische aanbevelingen zijn: geen permanente toewijzing en gebruik Azure AD Privileged Identity Management (PIM); sterke verificatie; Enz. Interessant is dat deze rol u niet standaard toegang geeft tot alles. Meestal zie ik verwarring over nalevingstoegang en Azure-toegang, die later worden besproken. Deze rol kan echter altijd toegang toewijzen tot andere services in de tenant. 
- **Specifieke servicebeheerders** : sommige services (Exchange, SharePoint, Power BI, enz.) gebruiken beheerrollen op hoog niveau van Azure AD. Dit is niet consistent voor alle services en er worden later meer servicespecifieke rollen besproken.
- **Functioneel** - Er is een lange (en groeiende) lijst van rollen gericht op specifieke bewerkingen (gastuitnodiger, enz.). Periodiek worden er meer toegevoegd op basis van de behoeften van de klant.

Het is niet mogelijk om alles te delegeren (hoewel de kloof afneemt), wat betekent dat de globale beheerrol soms moet worden gebruikt. Configuratie-as-code en automatisering moeten worden beschouwd in plaats van mensen die lid zijn van deze rol.

**Opmerking**: Het Microsoft 365-beheercentrum heeft een gebruiksvriendelijkere interface, maar heeft een subset van mogelijkheden in vergelijking met de Azure AD-beheerervaring. Beide portalen gebruiken dezelfde Azure AD-rollen, zodat er op dezelfde plaats wijzigingen plaatsvinden. Tip: als u een beheer-op identiteitsbeheer gerichte beheer-gebruik wilt zonder alle Azure-rommel, gebruikt u [https://aad.portal.azure.com](https://aad.portal.azure.com) . 

Wat staat er in de naam? Maak geen veronderstellingen van de naam van de rol. Taal is niet een zeer nauwkeurig instrument. Het doel moet zijn om bewerkingen te definiëren die moeten worden gedelegeerd voordat wordt gekeken welke rollen nodig zijn. Als u iemand toevoegt aan de rol 'Beveiligingslezer', ziet u deze niet overal beveiligingsinstellingen. 

De mogelijkheid om [aangepaste rollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/roles-custom-overview) te maken is een veel voorkomende vraag. Dit is beperkt in Azure AD vandaag (zie hieronder), maar zal groeien in mogelijkheden in de tijd. Ik denk dat deze van toepassing zijn op functies in Azure AD en mag niet overspannen "down" de hiërarchie model (hierboven besproken). Wanneer ik te maken heb met "custom", heb ik de neiging om terug te gaan naar mijn opdrachtgever van "eenvoudig is beter."

Een andere veel voorkomende vraag is de mogelijkheid om rollen te scopen naar een subset van een map. Een voorbeeld is zoiets als "Helpdesk Administrator voor gebruikers in de EU alleen." [Administratieve eenheden](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-administrative-units) (AU) zijn bedoeld om dit aan te pakken. Zoals hierboven, ik denk dat deze van toepassing zijn op functies in Azure AD en kan niet span 'down'. Natuurlijk hebben bepaalde rollen geen zin om te scopen (globale beheerders, servicebeheerders, enz.)

Tegenwoordig vereisen al deze rollen een direct lidmaatschap (of dynamische toewijzing als u [Azure AD PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/)gebruikt). Dit betekent dat klanten deze rechtstreeks in Azure AD moeten beheren en deze kunnen niet worden gebaseerd op een lidmaatschap van een beveiligingsgroep. Ik ben geen fan van het creëren van scripts om deze te beheren als het zou moeten draaien met verhoogde rechten. Ik adviseer over het algemeen API-integratie met processystemen zoals ServiceNow of het gebruik van partner governance tools zoals Saviynt. Er is technische werkzaamheden gaande om dit in de loop van de tijd aan te pakken.

Ik noemde [Azure AD PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/) een paar keer. Er is een overeenkomstige Microsoft Identity Manager (MIM) [Privileged Access Management](https://docs.microsoft.com/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) (PAM) oplossing voor on-premises besturingselementen. U ook kijken naar [Privileged Access Workstations (PAWs)](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) en [Azure AD Identity Governance](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview). Er zijn ook verschillende tools van derden die just-in-time, just-enough en dynamische rolverhoging mogelijk kunnen maken. Dit is meestal onderdeel van een grotere discussie voor het beveiligen van een omgeving. 

Soms vragen scenario's om een externe gebruiker aan een rol toe te voegen (zie de sectie multi-tenant, hierboven). Dit werkt prima. [Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/) is een ander groot en leuk onderwerp om klanten door te laten lopen, misschien in een ander artikel.

### <a name="security-and-compliance-center-scc"></a>Security and Compliance Center (SCC)

[Machtigingen in het Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) zijn een verzameling van 'rolgroepen' die gescheiden zijn van Azure AD-rollen. Dit kan verwarrend zijn omdat sommige van deze rolgroepen dezelfde naam hebben als Azure AD-rollen (bijvoorbeeld Security Reader), maar ze kunnen een ander lidmaatschap hebben. Ik geef de voorkeur aan het gebruik van Azure AD-rollen. Elke rolgroep bestaat uit een of meer "rollen" (zie wat ik bedoel met het hergebruiken van hetzelfde woord?) en hebben leden van Azure AD die objecten met e-mail zijn ingeschakeld. U ook een rolgroep met dezelfde naam maken als een rol die die rol al dan niet bevat (voorkom deze verwarring).

In zekere zin zijn deze een evolutie van het Exchange-rolgroepenmodel. Exchange Online heeft echter een eigen [interface voor groepsbeheer.](https://docs.microsoft.com/exchange/permissions-exo) Sommige rolgroepen in Exchange Online worden vergrendeld en beheerd vanuit Azure AD of het Security & Compliance Center, maar andere hebben mogelijk dezelfde of vergelijkbare namen en worden beheerd in Exchange Online (toevoegen aan de verwarring). Ik raad u aan de gebruikersinterface van Exchange Online niet te gebruiken, tenzij u scopes nodig hebt voor Exchange-beheer.

U geen aangepaste rollen maken. Rollen worden gedefinieerd door services die door Microsoft zijn gemaakt en zullen groeien naarmate nieuwe services worden geïntroduceerd. Dit is qua concept vergelijkbaar met [rollen die worden gedefinieerd door toepassingen](https://docs.microsoft.com/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) in Azure AD. Wanneer nieuwe diensten zijn ingeschakeld, moeten vaak nieuwe rolgroepen worden gemaakt om toegang tot deze diensten te verlenen of te delegeren (bijvoorbeeld risicobeheer met [voorkennis).](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure?view=o365-worldwide#step-1-required-enable-permissions-for-insider-risk-management)

Deze rolgroepen vereisen ook een direct lidmaatschap en kunnen geen Azure AD-groepen bevatten. Helaas worden deze rolgroepen vandaag de dag niet ondersteund door Azure AD PIM. Net als Azure AD-rollen heb ik de neiging om het beheer van deze rollen aan te bevelen via API's of een partnergovernanceproduct zoals Saviynt of anderen.

De rollen van security & Compliance Center omvatten Microsoft 365 en u deze rolgroepen niet beperken tot een subset van de omgeving (zoals u met beheerderseenheden in Azure AD). Veel klanten vragen hoe ze kunnen sub-delegeren. Bijvoorbeeld 'maak een DLP-beleid alleen voor EU-gebruikers'. Als u vandaag de dag rechten hebt op een specifieke functie in het Security & Compliance Center, hebt u rechten op alles wat onder deze functie valt in de tenant. Veel beleidsregels hebben echter mogelijkheden om een subset van de omgeving te targeten (bijvoorbeeld 'deze [labels](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy) alleen beschikbaar maken voor deze gebruikers'). Goed bestuur en communicatie zijn een belangrijk onderdeel om conflicten te voorkomen. Sommige klanten kiezen ervoor om een "configuration as code"-benadering te implementeren om subdelegatie aan te pakken in het Security & Compliance Center. Sommige specifieke diensten ondersteunen subdelegatie (zie hieronder). 

Het is vermeldenswaard dat besturingselementen die momenteel worden beheerd via het Security & Compliance Center (protection.office.com) momenteel worden gemigreerd naar twee afzonderlijke beheerportals: security.microsoft.com en compliance.microsoft.com. Verandering is de enige constante!

### <a name="service-specific"></a>Servicespecifiek

Zoals eerder vermeld, zijn veel klanten op zoek naar een meer gedetailleerde delegatie model te bereiken. Een veelvoorkomend voorbeeld: "XYZ-service alleen beheren voor gebruikers en locaties van divisie X" (of een andere dimensie). De mogelijkheid om dit te doen is afhankelijk van elke service en is niet consistent voor alle services en mogelijkheden. Bovendien kan elke service een apart en uniek RBAC-model hebben. In plaats van het bespreken van al deze (het zal eeuwig duren), ben ik het toevoegen van relevante links voor elke dienst. Dit is geen volledige lijst, maar het zal je op weg helpen.

- **Online ruilen** - [https://docs.microsoft.com/exchange/permissions-exo/permissions-exo](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- **SharePoint Online** - [https://docs.microsoft.com/sharepoint/manage-site-collection-administrators](https://docs.microsoft.com/sharepoint/manage-site-collection-administrators) 
- **Microsoft Teams**  -  [https://docs.microsoft.com/microsoftteams/itadmin-readiness ](https://docs.microsoft.com/microsoftteams/itadmin-readiness )
- **eDiscovery** - [https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions](https://docs.microsoft.com/microsoft-365/compliance/) 
  + **Machtigingsfiltering**  -  [https://docs.microsoft.com/microsoft-365/compliance/permissions-filtering-for-content-search ](https://docs.microsoft.com/microsoft-365/compliance/)
  + **Nalevingsgrenzen**  -  [https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries ](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries )
  + **Geavanceerde eDiscovery**  -  [https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20 ](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20 )
- **Yammer** - [https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins) 
- **Multi-geo** - [https://docs.microsoft.com/office365/enterprise/add-a-sharepoint-geo-admin](https://docs.microsoft.com/office365/enterprise/add-a-sharepoint-geo-admin) 
- **Dynamiek 365** –[https://docs.microsoft.com/dynamics365/](https://docs.microsoft.com/dynamics365/) <br>
  Let op: deze link is de wortel van documentatie. Er zijn meerdere soorten services met variaties in het beheer/delegeren model.
- **Power platform**  -  [https://docs.microsoft.com/power-platform/admin/admin-documentation ](https://docs.microsoft.com/power-platform/admin/admin-documentation )
  + **Power-apps**  -  [https://docs.microsoft.com/power-platform/admin/wp-security ](https://docs.microsoft.com/power-platform/admin/wp-security ) <br>
    Opmerking: er zijn meerdere typen met variaties in de admin/delegatiemodellen.
  + **Energie automatiseren**  -  [https://docs.microsoft.com/power-automate/environments-overview-admin ](https://docs.microsoft.com/power-automate/environments-overview-admin )
  + **PowerBI (PowerBI)**  -  [https://docs.microsoft.com/power-bi/service-admin-governance ](https://docs.microsoft.com/power-bi/service-admin-governance ) <br>
Opmerking: beveiliging en overdracht van gegevensplatforms (die Power BI onderdeel is) is een complex gebied.
- **MEM/Intune**  -  [https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control ](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control )
- **Microsoft Defender ATP**  -  [https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles )
- **Microsoft-bedreigingsbeveiliging** - [https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions)
- **Beveiliging van Microsoft Cloud-app** - [https://docs.microsoft.com/cloud-app-security/manage-admins](https://docs.microsoft.com/cloud-app-security/manage-admins)
- **Streamen**  -  [https://docs.microsoft.com/stream/assign-administrator-user-role ](https://docs.microsoft.com/stream/assign-administrator-user-role )
- **Informatiebarrières**  -  [https://docs.microsoft.com/microsoft-365/compliance/information-barriers ](https://docs.microsoft.com/microsoft-365/compliance/information-barriers )

Voor de rest, zoeken in Docs is echt goed de laatste tijd - [https://docs.microsoft.com/](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) . 


### <a name="activity-logs"></a>Activiteitslogboeken
Office 365 heeft een [uniform controlelogboek](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance). Het is een zeer [gedetailleerd logboek,](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)maar lees niet te veel in de naam. Het bevat mogelijk niet alles wat u wilt of nodig hebt voor uw beveiligings- en nalevingsbehoeften. Ook zijn sommige klanten echt geïnteresseerd in [Advanced Audit.](https://docs.microsoft.com/microsoft-365/compliance/advanced-audit) 

Voorbeelden van Microsoft 365-logboeken die via andere API's worden geopend, zijn de volgende:
- [Azure AD](https://docs.microsoft.com/azure/azure-monitor/platform/diagnostic-settings) (activiteiten die geen verband houden met Office 365)
- [Het bijhouden van exchange-berichten](https://docs.microsoft.com/powershell/module/exchange/get-messagetrace?view=exchange-ps)
- Threat/UEBA-systemen hierboven besproken (bijvoorbeeld Azure AD Identity Protection, Microsoft Cloud App Security, Microsoft Defender ATP, enz.)
- [Microsoft-informatiebeveiliging](https://docs.microsoft.com/microsoft-365/compliance/data-classification-activity-explorer?view=o365-worldwide)
- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft-grafiek](https://graph.microsoft.com)

Het is belangrijk om eerst alle logboekbronnen te identificeren die nodig zijn voor een beveiligings- en nalevingsprogramma. Houd er ook rekening mee dat verschillende logboeken verschillende on-line bewaarlimieten hebben. 

Vanuit het oogpunt van admindelegatie hebben de meeste Microsoft 365-activiteitslogboeken geen ingebouwd RBAC-model. Als u toestemming hebt om een logboek te zien, dan u alles in het zien. Een veelvoorkomend voorbeeld van een klantvereiste is: "Ik wil activiteit alleen kunnen opvragen voor EU-gebruikers" (of een andere dimensie). Om aan deze eis te voldoen, moeten we logboeken overzetten naar een andere service. In de Microsoft-cloud raden we u aan deze over te dragen naar [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview) of [Log Analytics.](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) 

Diagram op hoog niveau:

![diagram op hoog niveau van logstroom](../media/solutions-architecture-center/identity-beyond-illustration-4.png)  

Het bovenstaande diagram vertegenwoordigt ingebouwde mogelijkheden om logboeken naar Gebeurtenishub en/of Azure Storage en/of Azure Log Analytics te verzenden. Nog niet alle systemen bevatten deze out-of-the-box. Maar er zijn andere benaderingen om deze logboeken naar dezelfde opslagplaats te sturen. Zie Bijvoorbeeld [Uw teams beveiligen met Azure Sentinel](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761).

Het combineren van alle logboeken in één opslaglocatie omvat extra voordeel, zoals kruiscorrelaties, aangepaste bewaartijden, vergroten met gegevens die nodig zijn om rbac-model te ondersteunen, enz. Zodra de gegevens zich in dit opslagsysteem bevindt, u een PowerBI-dashboard (of een ander type visualisatie) maken met een geschikt RBAC-model.

Logboeken hoeven niet alleen naar één plaats te worden geleid. Het kan ook nuttig zijn om [Office 365-logboeken](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) te integreren met Microsoft Cloud App Security of een aangepast RBAC-model in [Power BI.](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics?view=o365-worldwide) Verschillende repositories hebben verschillende voordelen en doelgroepen.

Het is vermeldenswaard dat er een zeer rijk ingebouwd analysesysteem voor beveiliging, bedreigingen, kwetsbaarheden, [enz.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)

Veel grote klanten willen deze loggegevens overzetten naar een systeem van derden (bijvoorbeeld SIEM). Er zijn verschillende benaderingen voor dit, maar in-general [Azure Event Hub](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) en [Graph](https://docs.microsoft.com/graph/security-integration) zijn goede uitgangspunten.


### <a name="azure"></a>Azure 
Ik wordt vaak gevraagd of er een manier is om rollen met hoge bevoegdheden te scheiden tussen Azure AD, Azure en SaaS (bijvoorbeeld Globale beheerder voor Office 365, maar niet Azure).  Niet echt.  Multi-tenant architectuur is nodig als volledige administratieve scheiding nodig is, maar dat voegt aanzienlijke [complexiteit](https://aka.ms/multi-tenant-user) (zie hierboven). Al deze services maken deel uit van dezelfde beveiligings-/identiteitsgrens (bekijk het hiërarchiemodel hierboven).  

Het is belangrijk om relaties tussen verschillende diensten in dezelfde tenant te begrijpen. Ik werk samen met veel klanten die bedrijfsoplossingen bouwen die Azure, Office 365 en Power Platform omvatten (en vaak ook on-premises en cloudservices van derden). Een veelvoorkomend voorbeeld: 
-   Ik wil samenwerken aan een reeks documenten/afbeeldingen/etc (Office 365)
-   stuur elk van hen door middel van een goedkeuringsproces (Power Platform)
-   zodra alle componenten zijn goedgekeurd, assembleren deze in een unified deliverable (Azure) [Microsoft Graph API](https://docs.microsoft.com/azure/active-directory/develop/microsoft-graph-intro) is uw beste vriend voor deze.  Niet onmogelijk, maar aanzienlijk complexer om een oplossing te ontwerpen die [meerdere huurders](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)beslaat.

Azure Role-Based Access Control (RBAC) maakt fijnmazig toegangsbeheer voor Azure mogelijk. Met RBAC u de toegang tot resources beheren door gebruikers de minste machtigingen te verlenen die nodig zijn om hun taken uit te voeren. Details zijn buiten het bereik van dit document, maar zie [Wat is ROLE-based access control (RBAC) in Azure voor](https://docs.microsoft.com/azure/role-based-access-control/overview) meer informatie over RBAC? RBAC is belangrijk, maar slechts een deel van de governance overwegingen voor Azure. [Cloud Adoption Framework](https://docs.microsoft.com/azure/cloud-adoption-framework/govern/) is een geweldig startpunt om meer te weten te komen. Ik hou van hoe mijn vriend, Andres Ravinet loopt klanten stap-voor-stap hoewel verschillende componenten om te beslissen over de aanpak. High-level view voor verschillende elementen (niet zo goed als het proces om tot de werkelijke klant model) is zoiets als volgt:

:::image type="content" source="../media/solutions-architecture-center/identity-beyond-illustration-5.png" alt-text="weergave op hoog niveau van Azure-componenten voor gedelegeerd beheer":::

Zoals u zien op bovenstaande afbeelding, moeten veel andere services worden beschouwd als onderdeel van het ontwerp (bijvoorbeeld [Azure-beleid,](https://docs.microsoft.com/azure/governance/policy/overview) [Azure-blauwdrukken,](https://docs.microsoft.com/azure/governance/blueprints/overview) [beheergroepen,](https://docs.microsoft.com/azure/governance/management-groups/)enz.)

## <a name="conclusion"></a>Conclusie
Begonnen als een korte samenvatting, eindigde langer dan ik had verwacht.  Ik hoop dat u nu klaar bent om zich te wagen in een diepe zien van het creëren van delegatie model voor uw organisatie.  Dit gesprek is heel gebruikelijk bij klanten. Er is geen enkel model dat voor iedereen werkt. Wachten op een paar geplande verbeteringen van Microsoft engineering voordat het documenteren van gemeenschappelijke patronen zien we tussen klanten. In de tussentijd u met uw Microsoft-accountteam werken om een bezoek aan het dichtstbijzijnde [Microsoft Technology Center](https://www.microsoft.com/mtc)te regelen.  Tot ziens!


