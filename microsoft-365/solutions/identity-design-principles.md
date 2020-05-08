---
title: Naar identiteit en daarbuiten — Het standpunt van één architect
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
- M365solutions
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: c830e7f7b0366623520d7ba4e5a47a51e73f09ad
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160376"
---
# <a name="to-identity-and-beyond--one-architects-viewpoint"></a>Naar identiteit en daarbuiten — Het standpunt van één architect

In dit artikel bespreekt [Alex Shteynberg](https://www.linkedin.com/in/alex-shteynberg/), Principal Technical Architect bij Microsoft, topontwerpstrategieën voor bedrijfsorganisaties die Microsoft 365 en andere Microsoft-cloudservices gebruiken.

## <a name="about-the-author"></a>Over de auteur

:::image type="content" source="../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg" alt-text="Foto Alex Shteynberg":::

Ik ben een principal technical architect aan het New York [Microsoft Technology Center.](https://www.microsoft.com/mtc?rtc=1) Ik werk vooral met grote klanten en complexe eisen. Mijn standpunt en meningen zijn gebaseerd op deze interacties en zijn mogelijk niet voor elke situatie van toepassing. Echter, in mijn ervaring, als we klanten kunnen helpen met de meest complexe uitdagingen, kunnen we alle klanten helpen. 

Ik werk meestal met 100 + klanten per jaar. Hoewel elke organisatie unieke kenmerken heeft, is het interessant om trends en overeenkomsten te zien. Bijvoorbeeld, een trend is cross-industry belang voor veel klanten. Een bankfiliaal kan immers ook een koffiebar en een buurthuis zijn. 

In mijn rol richt ik me op het helpen van klanten om tot de beste technische oplossing te komen om hun unieke set bedrijfsdoelen aan te pakken. Officieel richt ik me op Identiteit, Beveiliging, Privacy en Compliance. Ik hou van het feit dat deze raken alles wat we doen. Het geeft me de kans om betrokken te zijn bij de meeste projecten. Dit houdt me heel druk en genieten van deze rol. 

Ik woon in New York City ( de beste!) en echt genieten van de diversiteit van haar cultuur, eten en mensen ( niet verkeer). Ik hou van reizen wanneer ik kan en hoop het grootste deel van de wereld te zien in mijn leven. Ik ben momenteel onderzoek naar een reis naar Afrika om te leren over wilde dieren.

## <a name="guiding-principles"></a>Richtsnoeren 

- **Eenvoudig is vaak beter** - U (bijna) alles doen met technologie. Dat betekent niet dat je dat moet doen. Vooral in de beveiligingsruimte overwerken veel klanten oplossingen. Ik hou van [deze video](https://www.youtube.com/watch?v=SOQgABDSYZE) van Google's Stripe conferentie om dit punt te onderstrepen.
- **Mensen, proces, technologie** - [Ontwerp voor mensen](https://en.wikipedia.org/wiki/Human-centered_design) om het proces te verbeteren, niet tech eerst. Er zijn geen "perfecte" oplossingen. We moeten verschillende risicofactoren in evenwicht brengen en beslissingen zullen voor elk bedrijf verschillend zijn. Te veel klanten ontwerpen een aanpak die hun gebruikers later vermijden.
- **Focus op 'waarom' eerste en 'hoe' later** - Wees de vervelende 7 jaar oude jongen met een miljoen vragen. We kunnen niet tot het juiste antwoord komen als we niet de juiste vragen weten. Veel klanten maken veronderstellingen over hoe dingen moeten werken in plaats van het definiëren van het zakelijke probleem. Er zijn altijd meerdere paden die kunnen worden genomen.
- **Lange staart van het verleden best practices** - Erkennen dat best practices veranderen bij lichte snelheid. Als u meer dan 3 maanden geleden naar Azure AD hebt gekeken, bent u waarschijnlijk verouderd. Alles hier is onderhevig aan verandering na publicatie. "Beste" optie vandaag kan niet dezelfde 6 maanden vanaf nu.

## <a name="baseline-concepts"></a>Basislijnconcepten

Sla deze sectie niet over. Ik vind vaak dat ik een stap terug moet doen naar deze onderwerpen, zelfs voor klanten die al jaren cloudservices gebruiken.
Helaas, taal is niet een nauwkeurig instrument. We gebruiken vaak hetzelfde woord om verschillende concepten of verschillende woorden te betekenen om hetzelfde concept te betekenen. Ik gebruik dit diagram hieronder vaak om een basislijnterminologie en 'hiërarchiemodel' vast te stellen.
<br><br>

![Illustratie van tenant, abonnement, service en gegevens](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)  

<br>

Als je leert zwemmen is het beter om te beginnen in het zwembad en niet in het midden van de oceaan. Ik probeer niet om technisch nauwkeurig te zijn met dit diagram. Het is een model om een aantal basisbegrippen te bespreken. 

In het diagram:
- Tenant = een exemplaar van Azure AD. Het is aan de "top" van een hiërarchie, of Niveau 1 in het diagram. We kunnen dit beschouwen als de "[grens](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-directory-independence)" waar al het andere zich voordoet[(Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) opzij). Alle Microsoft enterprise cloudservices maken deel uit van een van deze tenants. Consumentendiensten staan los van elkaar. 'Tenant' wordt in documentatie weergegeven als Office 365-tenant, Azure-tenant, WVD-tenant, enz. Ik vind vaak deze variaties verwarring veroorzaken voor klanten.
- Services/abonnementen, niveau 2 in het diagram, behoren tot één en slechts één tenant. De meeste SaaS-services zijn 1:1 en kunnen niet zonder migratie worden verplaatst. Azure is anders, u facturering en/of een [abonnement](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) [verplaatsen](https://docs.microsoft.com/azure/cost-management-billing/manage/billing-subscription-transfer) naar een andere tenant. Er zijn veel klanten die Azure-abonnementen moeten verplaatsen. Dit heeft verschillende implicaties. Objecten die buiten het abonnement bestaan (bijvoorbeeld RBAC- en Azure AD-objecten, waaronder groepen, apps, beleidsregels, enz.) worden niet verplaatst. Sommige services (Azure Key Vault, Data Bricks, enz.) worden ook in een niet-functionele status verplaatst. Migreer services niet zonder een goede zakelijke behoefte. Sommige scripts die nuttig kunnen zijn voor migratie, worden [gedeeld op GitHub.](https://github.com/lwajswaj/azure-tenant-migration) 
- Een bepaalde service heeft meestal een soort van "sub-level" grens, of Niveau 3 (L3). Dit is nuttig om te begrijpen voor de segregatie van veiligheid, beleid, bestuur, enz. Helaas is er geen uniforme naam die ik ken. Enkele voorbeelden namen voor L3 zijn: Azure Subscription = [resource](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resources-portal); Dynamics 365 CE = [instantie](https://docs.microsoft.com/dynamics365/admin/new-instance-management); Power BI = [werkruimte](https://docs.microsoft.com/power-bi/service-create-the-new-workspaces); Power Apps = [omgeving](https://docs.microsoft.com/power-platform/admin/environments-overview); Enz.
- Niveau 4 is waar de werkelijke gegevens leven. Dit 'dataplane' is een complex onderwerp. Sommige services gebruiken Azure AD voor RBAC, andere niet. Ik zal het een beetje bespreken als we aan de delegatie onderwerpen.

Enkele aanvullende concepten die ik vind veel klanten (en Microsoft-medewerkers) zijn verward over of hebben vragen over onder meer:


- Iedereen kan [maken](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) veel huurders [zonder kosten.](https://azure.microsoft.com/pricing/details/active-directory/) U hoeft geen service te verlenen die erin is voorzien. Ik heb er tientallen. Elke tenantnaam is uniek in de wereldwijde cloudservice van Microsoft (d.w.z. geen twee tenants mogen dezelfde naam hebben). Ze zijn allemaal in het formaat van TenantName.onmicrosoft.com. Er zijn ook processen die tenants automatisch maken[(onbeheerde tenants).](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup) Dit kan bijvoorbeeld gebeuren wanneer een gebruiker zich aanmeldt voor een bedrijfsservice met een e-maildomein dat niet bestaat in een andere tenant. 
- In een beheerde tenant kunnen veel [DNS-domeinen](https://docs.microsoft.com/azure/active-directory/fundamentals/add-custom-domain) worden geregistreerd. Dit verandert niets aan de oorspronkelijke tenantnaam. Er is momenteel geen eenvoudige manier om de naam van een tenant (andere dan migratie) te wijzigen. Hoewel de tenant naam is technisch niet kritisch deze dagen, sommigen kunnen vinden dit te beperken.
- U moet een tenantnaam reserveren voor uw organisatie, zelfs als u nog niet van plan bent om services te implementeren. Anders kan iemand het van u afnemen en is er geen eenvoudig proces om het terug te nemen (hetzelfde probleem als DNS-namen). Ik hoor dit veel te vaak van klanten. Wat uw huurder naam moet worden is een debat onderwerp ook.
- Als u eigenaar bent van DNS-naamruimte(s), moet u deze allemaal toevoegen aan uw tenant(s). Anders zou men een [onbeheerde tenant](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup) met deze naam kunnen maken, waardoor er een verstoring ontstaat om [deze te laten beheren.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)
- DNS-naamruimte (bijvoorbeeld contoso.com) kan tot één en slechts één tenant behoren. Dit heeft gevolgen voor verschillende scenario's (bijvoorbeeld het delen van een e-maildomein tijdens een fusie of overname, enz.) Er is een manier om een DNS-sub (bijvoorbeeld div.contoso.com) in een andere tenant te registreren, maar dat moet worden vermeden. Door het registreren van een domeinnaam op het hoogste niveau, worden alle subdomeinen verondersteld tot dezelfde tenant te behoren. In multi-tenant scenario's (zie hieronder) zou ik normaal gesproken aanraden om een andere top-level domeinnaam te gebruiken (bijvoorbeeld contoso.ch of ch-contoso.com).
- Wie moet een huurder "bezitten"? Ik zie vaak klanten die niet weten wie momenteel eigenaar is van hun huurder. Dit is een grote rode vlag. Bel Microsoft-ondersteuning zo snel mogelijk. Net zo problematisch is wanneer een service-eigenaar (vaak een Exchange-beheerder) wordt aangewezen om een tenant te beheren. De tenant bevat alle services die u in de toekomst wilt. De huurder moet een groep zijn die een beslissing kan nemen voor het inschakelen van alle cloudservices in een organisatie. Een ander probleem is wanneer een tenant-eigenaargroep wordt gevraagd om alle services te beheren. Dit schaalt niet op voor grote organisaties.
- Er is geen concept van een sub / super huurder. Om de een of andere reden blijft deze mythe zich herhalen. Dit geldt ook voor [Azure AD B2C-tenants.](https://docs.microsoft.com/azure/active-directory-b2c/) Ik hoor te vaak: 'Mijn B2C-omgeving bevindt zich in mijn XYZ-tenant' of 'Hoe verplaats ik mijn Azure-tenant naar mijn Office 365-tenant?'
- Dit document richt zich vooral op de commerciële wereldwijde cloud, omdat dit is wat de meeste klanten gebruiken. Het soms nuttig om te weten over [soevereine wolken](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud). Soevereine wolken hebben extra implicaties om te bespreken welke niet in de ruimte voor deze discussie.


## <a name="baseline-identity-topics"></a>Onderwerpen voor basislijnidentiteit

Er is veel documentatie over het identiteitsplatform van Microsoft : Azure Active Directory (Azure AD). Voor degenen die net beginnen, voelt het vaak overweldigend. Zelfs nadat je erover leert, kan het een uitdaging zijn om constant bij te blijven met innovatie en verandering. In mijn klantinteracties vind ik mezelf vaak werkzaam als "vertaler" tussen zakelijke doelen en "Good, Better, Best" benaderingen om deze aan te pakken (evenals menselijke "cliff notes" voor deze onderwerpen). Er is zelden een perfect antwoord en de "juiste" beslissing is een evenwicht tussen verschillende risicofactoren. Hieronder zijn enkele van de gemeenschappelijke vragen en verwarring gebieden die ik de neiging om te bespreken met klanten.

### <a name="provisioning"></a>Provisioning
Azure AD lost niet op bij gebrek aan governance in uw identiteitswereld! [Identiteitsbeheer](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) moet een cruciaal element zijn, onafhankelijk van cloudbeslissingen. Governance-vereisten veranderen in de loop van de tijd en daarom is het een programma en geen hulpmiddel. 

[Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect) vs. [Microsoft Identity Manager](https://docs.microsoft.com/microsoft-identity-manager/microsoft-identity-manager-2016) (MIM) vs. iets anders (3rd party of custom)? Bespaar uzelf nu en in de toekomst een hoop hoofdpijn en ga voor Azure AD Connect. Er zijn allerlei smarts in deze tool om eigenaardige klantconfiguraties en voortdurende innovaties aan te pakken. 

Sommige randgevallen die naar een complexere architectuur kunnen leiden:
- Ik heb meerdere AD-forests zonder netwerkverbinding tussen deze. Er is een nieuwe optie genaamd [Cloud Provisioning](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning).
- Ik heb geen Active Directory en wil deze ook niet installeren. Azure AD Connect kan worden geconfigureerd om te [synchroniseren vanuit LDAP](https://docs.microsoft.com/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) (partner kan nodig zijn).
- Ik moet dezelfde objecten aan meerdere huurders verstrekken. Dit wordt niet technisch ondersteund, maar hangt af van de definitie van "hetzelfde."

Moet ik standaardsynchronisatieregels aanpassen[(filterobjecten,](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering) [kenmerken wijzigen,](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) [alternatieve inlog-id,](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-userprincipalname)enz.)? Vermijd het! Een identiteitsplatform is net zo waardevol als de diensten die het gebruiken. Terwijl u allerlei nootachtige configuraties doen, moet u om deze vraag te beantwoorden kijken naar de impact op toepassingen. Als u objecten met e-mailfiltert, is de GAL voor onlineservices onvolledig. als de toepassing afhankelijk is van specifieke kenmerken, heeft het filteren hiervan een onvoorspelbare impact; Enz. Het is geen beslissing van het identiteitsteam.

XYZ SaaS ondersteunt Just-in-Time (JIT) provisioning, waarom verplicht u mij om te synchroniseren? Zie het bovenstaande. Veel toepassingen hebben "profiel" informatie nodig voor functionaliteit. U geen GAL hebben als niet alle objecten met e-mail beschikbaar zijn. Hetzelfde geldt voor [gebruikersvoorziening](https://docs.microsoft.com/azure/active-directory/app-provisioning/user-provisioning) in toepassingen die zijn geïntegreerd met Azure AD.


### <a name="authentication"></a>Verificatie

[Password hash sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) (PHS) vs. [pass-through authentication](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) (PTA) vs. [federation](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility).

Gewoonlijk is er een hartstochtelijk [debat](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) rond federatie. Eenvoudiger is meestal beter en dus gebruik PHS, tenzij je een goede reden om niet te doen. Het is ook mogelijk om verschillende verificatiemethoden voor verschillende DNS-domeinen in dezelfde tenant te configureren. 

Sommige klanten stellen federation + PHS vooral in staat voor:
- Een optie om terug te [vallen](https://docs.microsoft.com/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) op (voor herstel na noodgevallen) als de federatieservice niet beschikbaar is.
- Aanvullende mogelijkheden (bijvoorbeeld [Azure AD DS)](https://docs.microsoft.com/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)en beveiligingsservices (bijvoorbeeld [gelekte referenties)](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials)
- Ondersteuning voor services in Azure die geen federatieve verificatie begrijpen (bijvoorbeeld [Azure-bestanden](https://docs.microsoft.com/azure/storage/files/storage-files-active-directory-overview)).

Ik loop vaak klanten door client authenticatie stroom om een aantal misvattingen te verduidelijken. Het resultaat ziet eruit als de foto hieronder, die niet zo goed als het interactieve proces om er te komen.

:::image type="content" source="../media/solutions-architecture-center/identity-beyond-whiteboard-example.png" alt-text="voorbeeld whiteboardgesprek":::

Dit type whiteboardtekening illustreert waar beveiligingsbeleid wordt toegepast binnen de stroom van een verificatieaanvraag. In dit voorbeeld worden beleidsregels die via Active Directory Federation Service (AD FS) worden afgedwongen, toegepast op de eerste serviceaanvraag, maar niet op latere serviceaanvragen. Dit is ten minste één reden om beveiligingsbesturingselementen zoveel mogelijk naar de cloud te verplaatsen.

We jagen al zo lang als ik me kan herinneren op de droom van [single sign-on](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) (SSO). Sommige klanten geloven dat ze dit kunnen bereiken door te kiezen voor de "juiste" federatie (STS) provider. Azure AD kan aanzienlijk helpen om [SSO-mogelijkheden in](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-sso-deployment) te schakelen, maar geen STS is magisch. Er zijn te veel "legacy" authenticatie methoden die nog steeds worden gebruikt voor kritische toepassingen. Het uitbreiden van Azure AD met [partneroplossingen](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) kan veel van deze scenario's aanpakken. SSO is een strategie en een reis. Je er niet komen zonder te bewegen in de richting van [normen voor toepassingen.](https://docs.microsoft.com/azure/active-directory/develop/v2-app-types) Gerelateerd aan dit onderwerp is een reis naar [wachtwoordloze](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless) authenticatie die ook niet over een magisch antwoord. 

[Multi-factor authenticatie](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) is vandaag de dag essentieel[(hier](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) voor meer). Voeg aan het [gebruikersgedrag analytics](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) en je hebt een oplossing die de meerderheid van de gemeenschappelijke cyber-aanvallen voorkomt. Zelfs consumentendiensten zijn verhuizen naar MFA vereisen. Toch ontmoet ik nog steeds veel klanten die niet willen overstappen op [moderne authenticatiebenaderingen.](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) Het grootste argument dat ik hoor is dat het gebruikers en legacy applicaties zal beïnvloeden. Soms kan een goede kick klanten helpen om verder te gaan - Exchange Online [aangekondigde wijzigingen](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282). Veel Azure [AD-rapporten](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) zijn nu beschikbaar om klanten te helpen met deze overgang.



### <a name="authorization"></a>Vergunning

Per [Wikipedia](https://en.wikipedia.org/wiki/Authorization), "autoriseren" is het definiëren van een toegangsbeleid. Veel mensen zien het als de mogelijkheid om toegangscontroles tot een object te definiëren (bestand, service, enz.). In de huidige wereld van cyberdreigingen evolueert dit concept snel naar een dynamisch beleid dat kan reageren op verschillende dreigingsvectoren en snel toegangscontroles kan aanpassen als reactie hierop. Als ik bijvoorbeeld vanaf een ongebruikelijke locatie toegang krijg tot mijn bankrekening, krijg ik extra bevestigingsstappen. Om dit te benaderen, moeten we niet alleen rekening houden met het beleid zelf, maar ook met het ecosysteem van dreigingsdetectie en signaalcorrelatiemethoden.

De beleidsengine van Azure AD wordt geïmplementeerd met [het beleid voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview). Dit systeem is afhankelijk van informatie van een verscheidenheid van andere bedreiging detectie systemen om dynamische beslissingen te nemen. Een eenvoudige mening zou iets als de volgende illustratie zijn.

:::image type="content" source="../media/solutions-architecture-center/identity-and-beyond-illustration-3.png" alt-text="Beleidsengine in Azure AD":::

Het combineren van al deze signalen zorgt voor dynamisch beleid zoals deze:
- Als er een bedreiging wordt gedetecteerd op uw apparaat, wordt uw toegang tot gegevens alleen beperkt tot het web zonder de mogelijkheid om te downloaden.
- Als u een ongewoon hoog volume aan gegevens downloadt, wordt alles wat u downloadt versleuteld en beperkt.
- Als u een service opent vanaf een onbeheerd apparaat, wordt u geblokkeerd voor zeer gevoelige gegevens, maar hebt u toegang tot niet-beperkte gegevens zonder de mogelijkheid om deze naar een andere locatie te kopiëren.

Als u akkoord gaat met deze uitgebreide definitie van autorisatie, moet u aanvullende oplossingen implementeren. Welke oplossingen u implementeert, hangt af van hoe dynamisch u het beleid wilt hebben en welke bedreigingen u wilt prioriteren. Enkele voorbeelden van dergelijke systemen zijn:
- [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/) 
- [Azure Advanced Threat Protection](https://docs.microsoft.com/azure-advanced-threat-protection/) (Azure ATP)
- [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) (Microsoft Defender ATP)
- [Microsoft 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Microsoft 365 ATP)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/) (MCAS)
- [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide) (MTP)
- [Microsoft Intune](https://docs.microsoft.com/mem/intune/)
- [Microsoft Information Protection](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) (MIP)
- [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/) 

Natuurlijk hebben verschillende services en toepassingen naast Azure AD hun eigen specifieke autorisatiemodellen. Sommige daarvan worden later in de delegatiesectie besproken.

### <a name="audit"></a>Audit
Azure AD beschikt over gedetailleerde [controle- en rapportagemogelijkheden.](https://docs.microsoft.com/azure/active-directory/reports-monitoring/) Dit is echter meestal niet de enige bron van informatie die nodig is om beveiligingsbeslissingen te nemen. Zie meer discussie hierover in de delegatiesectie.

## <a name="there-is-no-exchange"></a>Er is geen Exchange

Geen paniek! Dit betekent niet dat Exchange wordt afgeschaft (of SharePoint, enz.) Het is nog steeds een kernservice. Wat ik bedoel is, al geruime tijd, technologie providers zijn de overgang user experiences (UX) om componenten van meerdere diensten omvatten. In Microsoft 365 is een eenvoudig voorbeeld "[moderne bijlagen](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)" waarbij bijlagen bij e-mail worden opgeslagen in SharePoint Online of OneDrive voor Bedrijven. 

:::image type="content" source="../media/solutions-architecture-center/modern-attachments.png" alt-text="een bestand aan een e-mail koppelen":::


Als u naar de Outlook-client kijkt, ziet u veel services die zijn "verbonden" als onderdeel van deze ervaring, niet alleen Exchange. Dit omvat Azure AD-, Microsoft-zoekopdrachten, apps, profielen, naleving en Office 365-groepen. 

:::image type="content" source="../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png" alt-text="Outlook-interface met afroepouts":::

Lees meer over [Microsoft Fluid Framework](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) voor een voorbeeld van de komende mogelijkheden. In preview nu kan ik teamsgesprekken rechtstreeks in Outlook lezen en beantwoorden. In feite is de [Teams-klant](https://products.office.com/microsoft-teams/download-app) een van de meest prominente voorbeelden van deze strategie. 

Over het algemeen wordt het steeds moeilijker om een duidelijke lijn te trekken tussen Office 365 en andere services in Microsoft-clouds. Ik zie het als een groot voordeel voor klanten, omdat ze kunnen profiteren van totale innovatie over alles wat we doen, zelfs als ze gebruik maken van een component. Pretty cool en heeft verstrekkende gevolgen voor veel klanten.

Vandaag de dag vind ik veel klant IT-groepen zijn gestructureerd rond "producten." Het is logisch voor een on-premises wereld, omdat je een expert nodig hebt voor elk specifiek product. Ik ben echter helemaal blij dat ik een Active Directory- of Exchange-database nooit meer hoef te debuggen, omdat deze services naar de cloud zijn verhuisd. Automatisering (die cloud soort is) verwijdert bepaalde repetitieve handmatige taken (kijk wat er gebeurd is met fabrieken). Deze worden echter vervangen door complexere vereisten om inzicht te krijgen in de interactie tussen services, impact, bedrijfsbehoeften, enz. Als u bereid bent om te [leren,](https://docs.microsoft.com/learn/)zijn er grote mogelijkheden mogelijk gemaakt door cloudtransformatie. Voordat ik in technologie ga, praat ik vaak met klanten over het managen van verandering in IT-vaardigheden en teamstructuren.

Stop met vragen 'Hoe kan ik XYZ in SharePoint online'. Gebruik [Power Automate](https://docs.microsoft.com/power-automate/) (ook bekend als Flow) voor workflow, het is een veel krachtiger platform. Gebruik [Azure Bot Framework](https://docs.microsoft.com/azure/bot-service/?view=azure-bot-service-4.0) om een betere UX te maken voor uw 500K-itemlijst. Microsoft [Graph](https://developer.microsoft.com/graph/) gebruiken in plaats van CSOM. [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview) bevat SharePoint, maar ook een wereld meer. Er zijn vele andere voorbeelden die ik kan noemen. Er is een uitgestrekt en prachtig universum daarbuiten. Open de deur en [begin met verkennen.](https://docs.microsoft.com)

De andere gemeenschappelijke impact is op het gebied van naleving. Deze cross-services aanpak lijkt veel nalevingsbeleid volledig te verwarren. Ik blijf organisaties zien die zeggen: "Ik moet alle e-mailcommunicatie naar een eDiscovery-systeem toeschrijven." Wat betekent dit eigenlijk wanneer e-mail niet langer alleen e-mail is, maar een venster in andere services? Office 365 heeft een uitgebreide aanpak voor [compliance,](https://docs.microsoft.com/microsoft-365/compliance/)maar het veranderen van mensen en processen is vaak veel moeilijker dan technologie.

Er zijn veel andere mensen en proces implicaties. Naar mijn mening is dit een kritisch en onderbesproken gebied. Misschien meer in een ander artikel.

## <a name="tenant-structure-options"></a>Opties voor tenantstructuur

### <a name="single-tenant-vs-multi-tenant"></a>Eén tenant vs. multi-tenant

In het algemeen zouden de meeste klanten slechts één productietenant moeten hebben. Er zijn vele redenen waarom meerdere huurders zijn uitdagend (geef het een [Bing zoeken)](https://www.bing.com/search?q=office%20365%20multiple%20tenants)of lees deze [whitepaper](https://aka.ms/multi-tenant-user). Tegelijkertijd hebben veel zakelijke klanten waarmee ik werk een andere (kleine) tenant voor IT-leren, testen en experimenteren. Azure-toegang met meerdere tenantwordt eenvoudiger gemaakt met [Azure Lighthouse.](https://azure.microsoft.com/services/azure-lighthouse/) Office 365 en vele andere SaaS-services hebben limieten voor scenario's voor meerdere tenant's. Er is veel te overwegen in [Azure AD B2B-scenario's.](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)

Veel klanten komen na een fusie en overname (M&A) met meerdere productiehuurders en willen consolideren. Vandaag dat is niet eenvoudig en zou vereisen Microsoft Consulting Services (MCS) of een partner plus 3rd party software. Er is een doorlopend engineeringwerk om verschillende scenario's met multi-tenant klanten in de toekomst aan te pakken. 

Sommige klanten kiezen ervoor om te gaan met meer dan een huurder. Dit moet een zeer zorgvuldige beslissing en bijna altijd zakelijke reden gedreven! Enkele voorbeelden zijn de volgende:
- Een holdingtype bedrijfsstructuur waar een gemakkelijke samenwerking tussen verschillende entiteiten niet nodig is en er sterke administratieve en andere isolatiebehoeften zijn.
- Na een overname wordt een zakelijke beslissing genomen om twee entiteiten gescheiden te houden.
- Simulatie van de omgeving van een klant die de productieomgeving van de klant niet verandert. 
- Ontwikkeling van software voor klanten.

In deze scenario's met meerdere tenants willen klanten vaak bepaalde configuratie voor tenants hetzelfde houden of rapporteren over configuratiewijzigingen en drifts. Dit betekent vaak dat u van handmatige wijzigingen naar configuratie als code moet gaan. Microsoft Premiere-ondersteuning biedt een workshop voor dit soort [https://Microsoft365dsc.com](https://Microsoft365dsc.com)vereisten op basis van deze openbare IP: .


### <a name="multi-geo"></a>Multi-Geo 

Aan [Multi-Geo](https://docs.microsoft.com/office365/enterprise/office-365-multi-geo) of niet aan Multi-Geo, dat is de vraag. Met Office 365 Multi-Geo u gegevens in- en rust inrichten en opslaan op de geolocaties die u hebt gekozen om te voldoen aan de vereisten [voor gegevensresidentie.](https://docs.microsoft.com/office365/enterprise/o365-data-locations) Er zijn veel misvattingen over deze mogelijkheid. Houd rekening met het volgende: 
- Het biedt geen prestatievoordelen. Het kan de prestaties verslechteren als het [netwerkontwerp](https://aka.ms/office365networking) niet correct is. Apparaten 'dicht' bij het Microsoft-netwerk krijgen, niet noodzakelijkerwijs bij uw gegevens.
- Het is geen oplossing voor [GDPR-naleving.](https://www.microsoft.com/trust-center/privacy/gdpr-overview) GDPR richt zich niet op gegevenssoevereiniteit of opslaglocaties. Daar zijn andere nalevingskaders voor.
- Het lost geen delegatie van administratie (zie hieronder) of [informatiebarrières op.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)
- Het is niet hetzelfde als multi-tenant en vereist extra [gebruikersinrichting](https:/docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) workflows.
- Uw tenant (uw Azure AD) [wordt](https://docs.microsoft.com/office365/enterprise/moving-data-to-new-datacenter-geos) niet verplaatst naar een andere geografie. 

## <a name="delegation-of-administration"></a>Delegatie van de administratie

In de meeste grote organisaties is scheiding van taken en op rollen gebaseerde toegangscontrole (RBAC) een noodzakelijke realiteit. Ik ga me van tevoren verontschuldigen. Dit is niet zo eenvoudig als sommige klanten willen dat het is. Klant, juridische, naleving, en andere eisen zijn verschillend en soms tegenstrijdig over de hele wereld. Eenvoud en flexibiliteit staan vaak tegenover elkaar. Begrijp me niet verkeerd, we kunnen dit beter doen. Er zijn (en zal) aanzienlijke verbeteringen in de tijd. Bezoek uw lokale [Microsoft Technology Center](https://www.microsoft.com/mtc) om het model uit te werken dat aan uw zakelijke vereisten voldoet zonder 379230-documenten te lezen! Hier zal ik me concentreren op wat je moet denken over en niet waarom het is op deze manier. Hieronder zijn vijf verschillende gebieden te plannen voor en een aantal van de gemeenschappelijke vragen die ik heb ondervonden.

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Azure AD- en Microsoft 365-beheercentra

Er is een lange en groeiende lijst van [ingebouwde rollen.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Elke rol bestaat uit een lijst met rolmachtigingen die zijn gegroepeerd om specifieke acties uit te voeren. U deze machtigingen in het tabblad Beschrijving in elke rol bekijken. U ook een meer menselijke leesbare versie hiervan zien in het Microsoft 365 Admin Center. De definities voor ingebouwde rollen kunnen niet worden gewijzigd. Ik over het algemeen, groepeer deze in drie categorieën:

- **Globale beheerder** - Deze "alle krachtige" rol moet zeer worden [beschermd,](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) net als in andere systemen. Typische aanbevelingen zijn: geen permanente toewijzing en gebruik Azure AD Privileged Identity Management (PIM); sterke authenticatie; Enz. Interessant is dat deze rol geeft je niet standaard toegang tot alles. Meestal zie ik verwarring over compliance-toegang en Azure-toegang, die later wordt besproken. Deze rol kan echter altijd toegang toewijzen tot andere services in de tenant. 
- **Specifieke servicebeheerders** : sommige services (Exchange, SharePoint, Power BI, enz.) gebruiken beheerrollen op hoog niveau vanuit Azure AD. Dit is niet consistent voor alle services en er worden later meer servicespecifieke rollen besproken.
- **Functioneel** - Er is een lange (en groeiende) lijst van rollen gericht op specifieke operaties (gast genodigde, enz.). Periodiek worden er meer van toegevoegd op basis van de behoeften van de klant.

Het is niet mogelijk om alles te delegeren (hoewel de kloof afneemt), wat betekent dat de globale beheerdersrol soms moet worden gebruikt. Configuratie-as-code en automatisering moeten worden overwogen in plaats van mensen die lid zijn van deze rol.

**Opmerking:** Het Microsoft 365-beheercentrum heeft een meer gebruiksvriendelijke interface, maar heeft subset van mogelijkheden in vergelijking met de Azure AD-beheerervaring. Beide portalen gebruiken dezelfde Azure AD-rollen, zodat er op dezelfde plaats wijzigingen plaatsvinden. Tip: als u een gebruikersinterface voor identiteitsbeheer wilt zonder [https://aad.portal.azure.com](https://aad.portal.azure.com)alle Azure-rommel, gebruikt u . 

Wat staat er in de naam? Maak geen veronderstellingen van de naam van de rol. Taal is niet een zeer nauwkeurig instrument. Het doel moet zijn om bewerkingen te definiëren die moeten worden gedelegeerd voordat wordt gekeken welke rollen nodig zijn. Als u iemand toevoegt aan de rol 'Beveiligingslezer' ziet u de beveiligingsinstellingen niet overal in. 

De mogelijkheid om [aangepaste rollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/roles-custom-overview) te maken is een veelvoorkomende vraag. Dit is vandaag beperkt in Azure AD (zie hieronder), maar zal in de loop van de tijd in mogelijkheden toenemen. Ik denk dat deze van toepassing zijn op functies in Azure AD en mag niet overspannen "down" het hiërarchiemodel (hierboven besproken). Wanneer ik omgaan met "custom," Ik heb de neiging om terug te gaan naar mijn opdrachtgever van "eenvoudig is beter."

Een andere veelvoorkomende vraag is de mogelijkheid om rollen te openen naar een subset van een map. Een voorbeeld is zoiets als "Helpdesk Beheerder voor gebruikers in de EU alleen." [Administratieve eenheden](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-administrative-units) (AU) zijn bedoeld om dit aan te pakken. Net als hierboven, ik denk dat deze van toepassing op functies in Azure AD en mag niet overspannen "down." Natuurlijk hebben bepaalde rollen geen zin om bereik (globale admins, service admins, enz.)

Tegenwoordig vereisen al deze rollen een direct lidmaatschap (of dynamische toewijzing als u [Azure AD PIM gebruikt).](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/) Dit betekent dat klanten deze rechtstreeks in Azure AD moeten beheren en deze kunnen niet gebaseerd zijn op een lidmaatschap van een beveiligingsgroep. Ik ben geen fan van het creëren van scripts om deze te beheren als het zou moeten draaien met verhoogde rechten. Ik raad api-integratie met processystemen zoals ServiceNow of het gebruik van partnergovernancetools zoals Saviynt over het algemeen aan. Er is engineering werk gaande om dit aan te pakken in de tijd.

Ik noemde [Azure AD PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/) een paar keer. Er is een bijbehorende PAM-oplossing (Microsoft Identity Manager) [(Privileged Access Management)](https://docs.microsoft.com/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) voor on-premises besturingselementen. U ook kijken naar [Privileged Access Workstations](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAW's) en [Azure AD Identity Governance.](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) Er zijn een verscheidenheid van 3rd party tools en die just-in-time, net genoeg, en dynamische rol hoogte mogelijk te maken. Dit is meestal onderdeel van een grotere discussie voor het beveiligen van een omgeving. 

Soms vragen scenario's om het toevoegen van een externe gebruiker aan een rol (zie de sectie multi-tenant hierboven). Dit werkt prima. [Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/) is een ander groot en leuk onderwerp om klanten doorheen te lopen, misschien in een ander artikel.

### <a name="security-and-compliance-center-scc"></a>Beveiligings- en compliancecentrum (SCC)

[Machtigingen in het Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) zijn een verzameling 'rolgroepen' die gescheiden zijn en zich onderscheiden van Azure AD-rollen. Dit kan verwarrend zijn omdat sommige van deze rolgroepen dezelfde naam hebben als Azure AD-rollen (bijvoorbeeld Security Reader), maar ze kunnen verschillende lidmaatschapsen hebben. Ik geef de voorkeur aan het gebruik van Azure AD-rollen. Elke rolgroep bestaat uit een of meer "rollen" (zie wat ik bedoel over het opnieuw gebruiken van hetzelfde woord?) en leden van Azure AD hebben die objecten met e-mail zijn. U ook een rolgroep maken met dezelfde naam als een rol die al dan niet die rol bevat (vermijd deze verwarring).

In zekere zin zijn deze een evolutie van het Exchange-rolgroepenmodel. Exchange Online heeft echter een eigen [interface voor groepsbeheer.](https://docs.microsoft.com/exchange/permissions-exo) Sommige rolgroepen in Exchange Online worden vergrendeld en beheerd vanuit Azure AD of het Security & Compliance Center, maar andere hebben mogelijk dezelfde of vergelijkbare namen en worden beheerd in Exchange Online (wat de verwarring vergroot). Ik raad u aan de gebruikersinterface van Exchange Online niet te gebruiken, tenzij u scopes nodig hebt voor Exchange-beheer.

U geen aangepaste rollen maken. Rollen worden gedefinieerd door services die door Microsoft zijn gemaakt en zullen toenemen naarmate nieuwe services worden geïntroduceerd. Dit is qua concept vergelijkbaar met [rollen die worden gedefinieerd door toepassingen](https://docs.microsoft.com/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) in Azure AD. Wanneer nieuwe services zijn ingeschakeld, moeten vaak nieuwe rolgroepen worden gecreëerd om deze toegang te verlenen of te delegeren (bijvoorbeeld [beheer van insiderrisico's).](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure?view=o365-worldwide#step-1-required-enable-permissions-for-insider-risk-management)

Deze rolgroepen vereisen ook direct lidmaatschap en kunnen geen Azure AD-groepen bevatten. Helaas worden deze rolgroepen tegenwoordig niet ondersteund door Azure AD PIM. Net als Azure AD-rollen heb ik de neiging om het beheer hiervan aan te bevelen via API's of een partnergovernanceproduct zoals Saviynt of anderen.

Beveiligings- & Compliance Center-rollen omvatten Microsoft 365 en u deze rolgroepen niet beperken tot een subset van de omgeving (zoals u met beheereenheden in Azure AD). Veel klanten vragen hoe ze kunnen sub-delegeren. Bijvoorbeeld: 'maak een DLP-beleid alleen voor EU-gebruikers'. Als u vandaag de dag rechten hebt op een specifieke functie in het Security & Compliance Center, heeft u rechten op alles waarop deze functie in de tenant valt. Veel beleidsregels hebben echter mogelijkheden om een subset van de omgeving te targeten (bijvoorbeeld 'maak deze [labels](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy) alleen beschikbaar voor deze gebruikers'). Goed bestuur en communicatie zijn een belangrijk onderdeel om conflicten te voorkomen. Sommige klanten kiezen ervoor om een "configuratie als code"-benadering te implementeren om subdelegatie aan te pakken in het Security & Compliance Center. Sommige specifieke diensten ondersteunen subdelegatie (zie hieronder). 

Het is vermeldenswaard dat besturingselementen die momenteel worden beheerd via het Security & Compliance Center (protection.office.com) worden gemigreerd naar twee afzonderlijke beheerportalen: security.microsoft.com en compliance.microsoft.com. Verandering is de enige constante!

### <a name="service-specific"></a>Servicespecifiek

Zoals eerder vermeld, zijn veel klanten op zoek naar een meer gedetailleerde delegatie model te bereiken. Een veelvoorkomend voorbeeld: "XYZ-service beheren alleen voor gebruikers en locaties van Divisie X" (of een andere dimensie). De mogelijkheid om dit te doen is afhankelijk van elke service en is niet consistent tussen services en mogelijkheden. Bovendien kan elke service een apart en uniek RBAC-model hebben. In plaats van het bespreken van al deze (het zal eeuwig duren), ben ik het toevoegen van relevante links voor elke dienst. Dit is geen volledige lijst, maar het zal je op weg helpen.

- **Exchange Online** - [https://docs.microsoft.com/exchange/permissions-exo/permissions-exo](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- **SharePoint Online** - [https://docs.microsoft.com/sharepoint/manage-site-collection-administrators](https://docs.microsoft.com/sharepoint/manage-site-collection-administrators) 
- **Microsoft Teams**  -  [ https://docs.microsoft.com/microsoftteams/itadmin-readiness](https://docs.microsoft.com/microsoftteams/itadmin-readiness )
- **eDiscovery** - [https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions](https://docs.microsoft.com/microsoft-365/compliance/) 
  + **Machtigingsfiltering**  -  [ https://docs.microsoft.com/microsoft-365/compliance/permissions-filtering-for-content-search](https://docs.microsoft.com/microsoft-365/compliance/)
  + **Nalevingsgrenzen**  -  [ https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries )
  + **Geavanceerde eDiscovery**  -  [ https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20 )
- **Yammer** - [https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins) 
- **Multi-geo** - [https://docs.microsoft.com/office365/enterprise/add-a-sharepoint-geo-admin](https://docs.microsoft.com/office365/enterprise/add-a-sharepoint-geo-admin) 
- **Dynamica 365** –[https://docs.microsoft.com/dynamics365/](https://docs.microsoft.com/dynamics365/) <br>
  Let op: deze link is naar de wortel van de documentatie. Er zijn meerdere soorten services met variaties in het beheer-/delegatiemodel.
- **Power Platform** -  [ Energieplatformhttps://docs.microsoft.com/power-platform/admin/admin-documentation](https://docs.microsoft.com/power-platform/admin/admin-documentation )
  + **Power Apps**  -  [ https://docs.microsoft.com/power-platform/admin/wp-security](https://docs.microsoft.com/power-platform/admin/wp-security ) <br>
    Opmerking: er zijn meerdere typen met variaties in de beheerders-/delegatiemodellen.
  + **Power automatiseren**  -  [ https://docs.microsoft.com/power-automate/environments-overview-admin](https://docs.microsoft.com/power-automate/environments-overview-admin )
  + **PowerBI (PowerBI)**  -  [ https://docs.microsoft.com/power-bi/service-admin-governance](https://docs.microsoft.com/power-bi/service-admin-governance ) <br>
Opmerking: beveiliging en delegatie van gegevensplatforms (welk Onderdeel van Power BI een onderdeel is) is een complex gebied.
- **MEM/Intune**  -  [ https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control )
- **Microsoft Defender ATP**  -  [ https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles )
- **Microsoft-bedreigingsbeveiliging** - [https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions)
- **Beveiliging van Microsoft Cloud-apps** - [https://docs.microsoft.com/cloud-app-security/manage-admins](https://docs.microsoft.com/cloud-app-security/manage-admins)
- **Stream** -  [ Streamenhttps://docs.microsoft.com/stream/assign-administrator-user-role](https://docs.microsoft.com/stream/assign-administrator-user-role )
- **Information barriers** -  [ Informatiebarrièreshttps://docs.microsoft.com/microsoft-365/compliance/information-barriers](https://docs.microsoft.com/microsoft-365/compliance/information-barriers )

Voor de rest, zoeken in Docs [https://docs.microsoft.com/](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)is echt goed de laatste tijd - . 


### <a name="activity-logs"></a>Activiteitslogboeken
Office 365 heeft een [uniform controlelogboek](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance). Het is een zeer [gedetailleerd logboek,](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)maar lees niet te veel in de naam. Het bevat mogelijk niet alles wat u wilt of nodig hebt voor uw beveiligings- en nalevingsbehoeften. Ook zijn sommige klanten echt geïnteresseerd in [Advanced Audit.](https://docs.microsoft.com/microsoft-365/compliance/advanced-audit) 

Voorbeelden van Microsoft 365-logboeken die via andere API's worden geopend, zijn de volgende:
- [Azure AD](https://docs.microsoft.com/azure/azure-monitor/platform/diagnostic-settings) (activiteiten die niet gerelateerd zijn aan Office 365)
- [Het bijhouden van berichten uitwisselen](https://docs.microsoft.com/powershell/module/exchange/mail-flow/get-messagetrace?view=exchange-ps)
- Hierboven besproken Threat/UEBA Systems (bijvoorbeeld Azure AD Identity Protection, Microsoft Cloud App Security, Microsoft Defender ATP, etc.)
- [Microsoft-informatiebescherming](https://docs.microsoft.com/microsoft-365/compliance/data-classification-activity-explorer?view=o365-worldwide)
- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft-grafiek](https://graph.microsoft.com)

Het is belangrijk om eerst alle logboekbronnen te identificeren die nodig zijn voor een beveiligings- en nalevingsprogramma. Houd er ook rekening mee dat verschillende logboeken verschillende on-line bewaarlimieten hebben. 

Vanuit het perspectief van de beheerdersdelegatie hebben de meeste Microsoft 365-activiteitslogboeken geen ingebouwd RBAC-model. Als u toestemming hebt om een logboek te zien, u alles erin zien. Een veelvoorkomend voorbeeld van een klantvereiste is: "Ik wil alleen activiteiten kunnen opvragen voor EU-gebruikers" (of een andere dimensie). Om aan deze eis te voldoen, moeten we logboeken overzetten naar een andere service. In de Microsoft-cloud raden we u aan deze over te zetten naar [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview) of [Log Analytics.](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) 

Diagram op hoog niveau:

![diagram op hoog niveau van logboekstroom](../media/solutions-architecture-center/identity-beyond-illustration-4.png)  

Het bovenstaande diagram vertegenwoordigt ingebouwde mogelijkheden om logboeken naar gebeurtenishub en/of Azure Storage en/of Azure Log Analytics te verzenden. Niet alle systemen bevatten deze out-of-the-box nog niet. Maar er zijn andere benaderingen om deze logs te sturen naar dezelfde repository. Zie Uw [teams beveiligen met Azure Sentinel.](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761)

Het combineren van alle logboeken in één opslaglocatie omvat extra voordelen, zoals cross-correlaties, aangepaste bewaartijden, vergroten met gegevens die nodig zijn om rbac-model te ondersteunen, enz. Zodra gegevens zich in dit opslagsysteem begeven, u een PowerBI-dashboard (of een ander type visualisatie) maken met een geschikt RBAC-model.

Logboeken hoeven niet alleen naar één plaats te worden gericht. Het kan ook nuttig zijn om [Office 365-logboeken](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) te integreren met Microsoft Cloud App Security of een aangepast RBAC-model in [Power BI.](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics?view=o365-worldwide) Verschillende repositories hebben verschillende voordelen en doelgroepen.

Het is vermeldenswaard dat er een zeer rijke ingebouwde analytics systeem voor beveiliging, bedreigingen, kwetsbaarheden, etc. in een dienst genaamd [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide).

Veel grote klanten willen deze loggegevens overdragen naar een systeem van derden (bijvoorbeeld SIEM). Er zijn verschillende benaderingen voor dit, maar in-general [Azure Event Hub](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) en [Graph](https://docs.microsoft.com/graph/security-integration) zijn goede uitgangspunten.


### <a name="azure"></a>Azure 
Ik word vaak gevraagd of er een manier is om functies met hoge bevoegdheden te scheiden tussen Azure AD, Azure en SaaS (bijvoorbeeld globale beheerder voor Office 365, maar niet Azure).  Niet echt.  Multi-tenant architectuur is nodig als volledige administratieve scheiding nodig is, maar dat voegt aanzienlijke [complexiteit](https://aka.ms/multi-tenant-user) (zie hierboven). Al deze services maken deel uit van dezelfde beveiligings-/identiteitsgrens (kijk naar het hiërarchiemodel hierboven).  

Het is belangrijk om relaties tussen verschillende diensten in dezelfde tenant te begrijpen. Ik werk met veel klanten die bedrijfsoplossingen bouwen die Azure, Office 365 en Power Platform omvatten (en vaak ook on-premises en cloudservices van derden). Een veelvoorkomend voorbeeld: 
-   Ik wil samenwerken aan een reeks documenten/afbeeldingen/etc (Office 365)
-   stuur elk van hen door middel van een goedkeuringsproces (Power Platform)
-   zodra alle componenten zijn goedgekeurd, monteer deze in een uniforme deliverable(s) (Azure) [Microsoft Graph API](https://docs.microsoft.com/azure/active-directory/develop/microsoft-graph-intro) is uw beste vriend voor deze.  Niet onmogelijk, maar aanzienlijk complexer om een oplossing te ontwerpen voor [meerdere huurders.](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)

Azure Role-Based Access Control (RBAC) maakt fijnkorrelig toegangsbeheer voor Azure mogelijk. Met RBAC u de toegang tot bronnen beheren door gebruikers de minste machtigingen te geven die nodig zijn om hun taken uit te voeren. Details zijn buiten het bereik van dit document, maar zie [Wat is role-based access control (RBAC) in Azure voor](https://docs.microsoft.com/azure/role-based-access-control/overview) meer informatie? RBAC is belangrijk, maar slechts een deel van de governanceoverwegingen voor Azure. [Cloud Adoption Framework](https://docs.microsoft.com/azure/cloud-adoption-framework/govern/) is een geweldig startpunt om meer te leren. Ik hou van hoe mijn vriend, Andres Ravinet loopt klanten stap-voor-stap al verschillende componenten om te beslissen over de aanpak. High-level view voor verschillende elementen (niet zo goed als het proces om naar het werkelijke klantmodel) is zoiets als dit:

:::image type="content" source="../media/solutions-architecture-center/identity-beyond-illustration-5.png" alt-text="weergave op hoog niveau van Azure-componenten voor gedelegeerd beheer":::

Zoals u zien op bovenstaande afbeelding, moeten veel andere services worden beschouwd als onderdeel van het ontwerp (bijvoorbeeld [Azure Policies](https://docs.microsoft.com/azure/governance/policy/overview), [Asure Blueprints,](https://docs.microsoft.com/azure/governance/blueprints/overview) [Management Groepen,](https://docs.microsoft.com/azure/governance/management-groups/)enz.)

## <a name="conclusion"></a>Conclusie
Begonnen als een korte samenvatting, eindigde langer dan ik had verwacht.  Ik hoop dat u nu klaar bent om zich te wagen aan een diepe visie van het creëren van delegatie model voor uw organisatie.  Dit gesprek is heel gebruikelijk bij klanten. Er is niet één model dat voor iedereen werkt. Wachten op een paar geplande verbeteringen van Microsoft engineering voordat we veelvoorkomende patronen documenteren die we bij klanten zien. In de tussentijd u samenwerken met uw Microsoft-accountteam om een bezoek te regelen aan het dichtstbijzijnde [Microsoft Technology Center.](https://www.microsoft.com/mtc)  Tot daar!


