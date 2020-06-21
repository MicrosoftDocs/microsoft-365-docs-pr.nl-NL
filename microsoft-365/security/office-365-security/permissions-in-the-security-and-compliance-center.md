---
title: Machtigingen - Microsoft 365 Security & Compliance Center
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 02/14/2020
audience: Admin
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.AdminRoleGroups
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
description: Beheerders kunnen meer te weten komen over de machtigingen die beschikbaar zijn in het Microsoft 365 Security & Compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e236278fbfaf2ff3c696e294e429cdaf895bbb3a
ms.sourcegitcommit: 3119b2246001ba06af8264508785352dfb894166
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44820570"
---
# <a name="permissions-in-the-security--compliance-center"></a>Rapporten in het beveiligings- en compliancecentrum

Met het Security & Compliance Center u machtigingen verlenen aan mensen die nalevingstaken uitvoeren, zoals apparaatbeheer, preventie van gegevensverlies, eDiscovery, retentie, enzovoort. Deze mensen kunnen alleen de taken uitvoeren waartoe u hen expliciet toegang verleent. Om toegang te krijgen tot het Security & Compliance Center, moeten gebruikers een globale beheerder of lid zijn van een of meer beveiligings- & compliance center-rolgroepen.

Machtigingen in het Security & Compliance Center zijn gebaseerd op het machtigingenmodel Role Based Access Control (RBAC). Dit is hetzelfde machtigingenmodel dat wordt gebruikt door Exchange, dus als u bekend bent met Exchange, zullen machtigingen verlenen in het Security & Compliance Center zeer vergelijkbaar zijn. Het is echter belangrijk om te onthouden dat Exchange-rolgroepen en Security-&-functiegroepen van het Compliance Center geen lidmaatschap of machtigingen delen. Hoewel beide een rolgroep organisatiebeheer hebben, zijn ze niet hetzelfde. De machtigingen die ze verlenen, en de leden van de rolgroepen, zijn verschillend. Hieronder vindt u een lijst met rolgroepen security & Compliance Center.

![Pagina Machtigingen in het Security & Compliance Center](../../media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)

## <a name="relationship-of-members-roles-and-role-groups"></a>Relatie van leden, rollen en rolgroepen

Een **rol** verleent machtigingen voor het uitvoeren van een reeks taken; Met de functie Casemanagement kunnen mensen bijvoorbeeld werken met eDiscovery-aanvragen.

Een **rolgroep** is een set rollen waarmee mensen hun taak kunnen uitvoeren in het Security & Compliance Center; De rolgroep Compliancebeheerder bevat bijvoorbeeld de rollen voor Case Management, Content Search en Organisatieconfiguratie (plus anderen), omdat iemand die een compliancebeheerder is, de machtigingen nodig heeft om deze taken te kunnen uitvoeren.

Het Security & Compliance Center bevat standaardrolgroepen voor de meest voorkomende taken en functies waaraan u personen moet toewijzen. We raden u aan om individuele gebruikers als **leden** toe te voegen aan de standaardrolgroepen.

![Diagram met relatie van rolgroepen met rollen en leden](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-security--compliance-center"></a>Machtigingen die nodig zijn om functies te gebruiken in het Security & Compliance Center

In de volgende tabel worden de standaardrolgroepen weergegeven die beschikbaar zijn in het Security & Compliance Center en de rollen die standaard aan de rolgroepen zijn toegewezen. Als u een gebruiker machtigingen wilt verlenen om een nalevingstaak uit te voeren, voegt u deze toe aan de desbetreffende rolgroep Security & Compliance Center.

Het beheren van machtigingen in het Security & Compliance Center geeft gebruikers alleen toegang tot de compliancefuncties die beschikbaar zijn in het Security & Compliance Center zelf. Als u machtigingen wilt verlenen aan andere nalevingsfuncties die niet in het Security & Compliance Center staan, zoals Exchange-mailstroomregels (ook wel transportregels genoemd), moet u het Exchange-beheercentrum gebruiken.

Als u wilt zien hoe u toegang verlenen tot het Security & Compliance Center, [raadpleegt u Gebruikers toegang geven tot het Microsoft 365 Compliance-beheercentrum.](grant-access-to-the-security-and-compliance-center.md)

||||
|---|---|---|
|**Rolgroep**|**Beschrijving**|**Standaardrollen toegewezen**|
|**Compliance Administrator**<sup>1</sup>|Leden kunnen instellingen beheren voor apparaatbeheer, preventie van gegevensverlies, rapporten en bewaring.|Casemanagement <br/><br/> Beheerder van communicatienaleving <br/><br/> Analyse van communicatienaleving <br/><br/> Communicatie Compliance Case Management <br/><br/> Onderzoek naar naleving van communicatie <br/><br/> Nalevingsviewer voor communicatie <br/><br/> Feedbackprovider voor gegevensclassificatie <br/><br/> Beoordelingsrecensent voor gegevensclassificatie <br/><br/> Beheer van gegevensonderzoek <br/><br/> Compliance-beheerder <br/><br/> Nalevingszoekopdracht <br/><br/> Apparaatbeheer <br/><br/> Beheer van de dispositie <br/><br/> DLP Compliance Management <br/><br/> Houden <br/><br/> IB Compliance Management <br/><br/> Waarschuwingen beheren <br/><br/> Organisatieconfiguratie <br/><br/> RecordManagement <br/><br/> Retentiebeheer <br/><br/> Controlelogboeken met alleen weergeven <br/><br/> Apparaatbeheer alleen weergeven <br/><br/> DLP-compliancebeheer met alleen weergeven <br/><br/> Alleen-overzicht IB Compliance Management <br/><br/> Alleen weergeven Waarschuwingen beheren <br/><br/> Ontvangers alleen weergeven <br/><br/> Recordbeheer alleen weergeven <br/><br/> Alleen-weergeven retentiebeheer <br/><br/> |
|**Beheerder van compliancegegevens**|Leden kunnen instellingen beheren voor apparaatbeheer, gegevensbescherming, preventie van gegevensverlies, rapporten en bewaring.|Compliance-beheerder <br/><br/> Nalevingszoekopdracht <br/><br/> DLP Compliance Management <br/><br/> Apparaatbeheer <br/><br/> Beheer van de dispositie <br/><br/> IB Compliance Management <br/><br/> Waarschuwingen beheren <br/><br/> Organisatieconfiguratie <br/><br/> RecordManagement <br/><br/> Retentiebeheer <br/><br/> Gevoeligheidslabelbeheerder <br/><br/> Controlelogboeken met alleen weergeven <br/><br/> DLP-compliancebeheer met alleen weergeven <br/><br/> Apparaatbeheer alleen weergeven <br/><br/> Alleen-overzicht IB Compliance Management <br/><br/> Alleen weergeven Waarschuwingen beheren <br/><br/> Ontvangers alleen weergeven <br/><br/> Recordbeheer alleen weergeven <br/><br/> Alleen-weergeven retentiebeheer|
|**Content Explorer-inhoudsviewer**|Bekijk de inhoudsbestanden in Content explorer.|Inhoudsviewer voor gegevensclassificatie|
|**Lijstviewer voor inhoudsverkenner**|Alleen alle items in Content explorer weergeven in lijstindeling.|Viewer voor lijst met gegevensclassificatie|
|**Data-onderzoeker**|Leden kunnen zoekopdrachten uitvoeren op postvakken, SharePoint-sites en OneDrive-accounts.|Communicatie <br/><br/> Nalevingszoekopdracht <br/><br/> Voogd <br/><br/> Beheer van gegevensonderzoek <br/><br/> Exporteren<br/><br/> Voorbeeld <br/><br/> RMS decoderen <br/><br/> Review<br/><br/> Zoeken en zuiveren|
|**eDiscovery Manager**|Leden kunnen zoekopdrachten uitvoeren en wachtruimtes plaatsen op postvakken, SharePoint Online-sites en OneDrive voor Bedrijven-locaties. Leden kunnen ook eDiscovery-aanvragen maken en beheren, leden toevoegen en verwijderen aan een aanvraag, inhoudszoekopdrachten maken en bewerken die aan een aanvraag zijn gekoppeld en toegang krijgen tot casegegevens in Advanced eDiscovery. <br/><br/> Een eDiscovery-beheerder is lid van de rolgroep eDiscovery Manager die aanvullende machtigingen heeft gekregen. Naast de taken die een eDiscovery Manager kan uitvoeren, kan een eDiscovery-beheerder: <br/>* Bekijk alle eDiscovery-aanvragen in de organisatie. <br/>* Beheer een eDiscovery-aanvraag nadat ze zichzelf hebben toegevoegd als lid van de aanvraag. <br/><br/> Het belangrijkste verschil tussen een eDiscovery Manager en een eDiscovery-beheerder is dat een eDiscovery-beheerder toegang heeft tot alle aanvragen die worden vermeld op de pagina **eDiscovery-aanvragen** in het Security & Compliance Center. Een eDiscovery-manager heeft alleen toegang tot de aanvragen waarvan ze zijn gemaakt of aanvragen waarvan ze lid zijn. Zie [eDiscovery-machtigingen toewijzen in het Security & Compliance Center](../../compliance/assign-ediscovery-permissions.md)voor meer informatie over het maken van een gebruiker als eDiscovery-beheerder.|Casemanagement <br/><br/> Communicatie <br/><br/> Nalevingszoekopdracht <br/><br/> Voogd <br/><br/> Exporteren <br/><br/> Houden <br/><br/> Voorbeeld <br/><br/> RMS decoderen <br/><br/> Review|
|**Global Reader**|Leden hebben alleen-lezen toegang tot rapporten, waarschuwingen en kunnen alle configuraties en instellingen zien.<br/><br/> Het belangrijkste verschil tussen Global Reader en Security Reader is dat een Global Reader toegang heeft tot **configuratie en instellingen.**|Beveiligingslezer <br/><br/> Gevoeligheidslabellezer <br/><br/> Serviceborgingsweergave <br/><br/> Controlelogboeken met alleen weergeven <br/><br/> DLP-compliancebeheer met alleen weergeven <br/><br/> Apparaatbeheer alleen weergeven <br/><br/> Alleen-overzicht IB Compliance Management <br/><br/> Alleen weergeven Waarschuwingen beheren <br/><br/> Ontvangers alleen weergeven <br/><br/> Recordbeheer alleen weergeven <br/><br/> Alleen-weergeven retentiebeheer|
|**Insider-risicobeheer**|Gebruik deze rolgroep om insider-risicobeheer voor uw organisatie in één groep te beheren. Door alle gebruikersaccounts toe te voegen voor aangewezen beheerders, analisten en onderzoekers, u machtigingen voor insiderrisicobeheer configureren in één groep. Deze rolgroep bevat alle insider risk management permission-rollen. Dit is de eenvoudigste manier om snel aan de slag te gaan met insider-risicobeheer en past goed bij organisaties die geen afzonderlijke machtigingen nodig hebben die zijn gedefinieerd voor afzonderlijke groepen gebruikers.|Casemanagement <br/><br/> Insider Risk Management Admin <br/><br/> Analyse van insiderrisicobeheer <br/><br/> Onderzoek naar insiderrisicobeheer <br/><br/> Tijdelijke bijdrage van Insider Risk Management|
|**Insider Risk Management Admins**|Gebruik deze rolgroep om in eerste instantie insider-risicobeheer te configureren en later insiderrisicobeheerders te scheiden in een gedefinieerde groep. Gebruikers in deze rolgroep kunnen beleid voor risicobeheer voorkennis, globale instellingen en toewijzingen van rolgroepen maken, lezen, bijwerken en verwijderen.|Casemanagement <br/><br/> Insider Risk Management Admin|
|**Insider Risk Management Analisten**|Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die fungeren als insider risk case-analisten. Gebruikers in deze rolgroep hebben toegang tot alle insider-waarschuwingen voor risicobeheer, aanvragen en sjablonen voor meldingen. Ze hebben geen toegang tot het insiderrisico Content Explorer.|Casemanagement <br/><br/> Analyse van insiderrisicobeheer|
|**Insider Risk Management Onderzoekers**|Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die fungeren als insider risicogegevens onderzoekers. Gebruikers in deze rolgroep hebben toegang tot alle insider risk management waarschuwingen, gevallen, notices templates en de Content Explorer voor alle gevallen.|Casemanagement <br/><br/> Onderzoek naar insiderrisicobeheer|
|**IRM-bijdragers**|Deze rolgroep is zichtbaar, maar wordt alleen gebruikt door achtergrondservices.|Tijdelijke bijdrage van Insider Risk Management|
|**MailFlow-beheerder**|Leden kunnen de inzichten en rapporten van de e-mailstroom controleren en bekijken in het Security & Compliance Center. Globale beheerders kunnen gewone gebruikers aan deze groep toevoegen, maar als de gebruiker geen lid is van de Exchange-groep, heeft de gebruiker geen toegang tot Exchange-beheergerelateerde taken.|Ontvangers alleen weergeven|
|**Organisatiebeheer**<sup>1</sup>|Leden kunnen machtigingen beheren voor toegang tot functies in het Security & Compliance Center en ook instellingen beheren voor apparaatbeheer, preventie van gegevensverlies, rapporten en bewaring. <br/><br/> Houd er rekening mee dat de gebruiker, die geen globale beheerder is, de lijst met apparaten die worden beheerd door MDM voor Microsoft 365 en acties op deze apparaten wilt uitvoeren, zoals het terugtrekken van een apparaat van MDM voor Microsoft 365, een Exchange-beheerder moet zijn. <br/><br/> Globale beheerders worden automatisch toegevoegd als leden van deze rolgroep.|Controlelogboeken <br/><br/> Casemanagement <br/><br/> Compliance-beheerder <br/><br/> Nalevingszoekopdracht <br/><br/> Apparaatbeheer <br/><br/> DLP Compliance Management <br/><br/> Houden <br/><br/> IB Compliance Management <br/><br/> Waarschuwingen beheren <br/><br/> Organisatieconfiguratie <br/><br/> Quarantaine <br/><br/> RecordManagement <br/><br/> Retentiebeheer <br/><br/> Rolbeheer <br/><br/> Zoeken en zuiveren <br/><br/> Beveiligingsbeheerder <br/><br/> Beveiligingslezer <br/><br/> Gevoeligheidslabelbeheerder <br/><br/> Gevoeligheidslabellezer <br/><br/> Serviceborgingsweergave <br/><br/> Controlelogboeken met alleen weergeven <br/><br/> DLP-compliancebeheer met alleen weergeven <br/><br/> Apparaatbeheer alleen weergeven <br/><br/> Alleen-overzicht IB Compliance Management <br/><br/> Alleen weergeven Waarschuwingen beheren <br/><br/> Ontvangers alleen weergeven <br/><br/> Recordbeheer alleen weergeven <br/><br/> Alleen-weergeven retentiebeheer|
|**Quarantainebeheerder**|Leden hebben toegang tot alle quarantaineacties. Zie [In quarantaine geplaatste berichten en bestanden beheren als beheerder in OEOP voor](manage-quarantined-messages-and-files.md) meer informatie|Quarantaine|
|**Records Management**|Leden kunnen recordinhoud beheren en verwijderen.|RecordManagement|
|**Revisor**|Leden kunnen alleen de lijst met aanvragen bekijken op de pagina eDiscovery-aanvragen in het Security & Compliance Center. Ze kunnen geen eDiscovery-aanvraag maken, openen of beheren. Het primaire doel van deze rolgroep is om leden in staat te stellen casegegevens te bekijken en te openen in [Advanced eDiscovery (klassiek)](../../compliance/office-365-advanced-ediscovery.md) (ook bekend als *Advanced eDiscovery v1).* <br/><br/> Deze rolgroep heeft de meest beperkende eDiscovery-gerelateerde machtigingen.<br/><br/>**Let op:** Op dit moment hebben gebruikers die lid zijn van de functiegroep Reviewer geen toegang tot gegevens in [Advanced eDiscovery in Microsoft 365](../../compliance/overview-ediscovery-20.md) (ook bekend als *Advanced eDiscovery v2*). Als u leden wilt toevoegen aan een aanvraag in Advanced eDiscovery v2, zodat ze de aanvraaggegevens kunnen bekijken, moet een gebruiker lid zijn van de rolgroep eDiscovery Manager.|Review|
|**Beveiligingsbeheerder**|Leden van deze rolgroep kunnen cross-servicebeheerders zijn, evenals externe partnergroepen en Microsoft Support. Standaard kan deze groep geen rollen toegewezen krijgen. Het is echter lid van de rol Beveiligingsbeheerders in Azure Active Directory en erft de mogelijkheden van die rol over. Als u machtigingen centraal wilt beheren, brengt u wijzigingen aan in deze rol in het Azure Active Directory-beheercentrum. Zie [machtigingen voor beheerdersrol in Azure Active Directory voor](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)meer informatie. <br/><br/> Als u deze rolgroep bewerkt in het Security & Compliance Center, zijn deze wijzigingen alleen van toepassing op het Security & Compliance Center en geen andere services, terwijl wijzigingen die zijn aangebracht in het Azure Active Directory-beheercentrum van invloed zijn op alle services. <br/><br/> Alle alleen-lezen machtigingen van de beveiligingslezerrol, plus een aantal extra beheerdersmachtigingen voor dezelfde services: Azure Information Protection, Identity Protection Center, Privileged Identity Management, Monitor Microsoft 365 Service Health en Security & Compliance Center.|Controlelogboeken <br/><br/> DLP Compliance Management <br/><br/> Apparaatbeheer <br/><br/> IB Compliance Management <br/><br/> Waarschuwingen beheren <br/><br/> Quarantaine <br/><br/> Beveiligingsbeheerder <br/><br/> Gevoeligheidslabelbeheerder <br/><br/> Controlelogboeken met alleen weergeven <br/><br/> DLP-compliancebeheer met alleen weergeven <br/><br/> Apparaatbeheer alleen weergeven <br/><br/> Alleen-overzicht IB Compliance Management <br/><br/> Alleen weergeven Waarschuwingen beheren|
|**Beveiligingsoperator**|Leden kunnen beveiligingswaarschuwingen beheren en ook rapporten en instellingen van beveiligingsfuncties bekijken.|Nalevingszoekopdracht <br/><br/> Waarschuwingen beheren <br/><br/> Beveiligingslezer <br/><br/> Controlelogboeken met alleen weergeven <br/><br/> DLP-compliancebeheer met alleen weergeven <br/><br/> Apparaatbeheer alleen weergeven <br/><br/> Alleen-overzicht IB Compliance Management <br/><br/> Alleen weergeven Waarschuwingen beheren|
|**Beveiligingslezer**|Leden hebben alleen-lezen toegang tot een aantal beveiligingsfuncties van Identity Protection Center, Privileged Identity Management, Monitor Microsoft 365 Service Health en Security & Compliance Center. <br/><br/> Het lidmaatschap van deze rolgroep wordt gesynchroniseerd tussen services en centraal beheerd. Leden van deze rolgroep kunnen cross-servicebeheerders zijn, evenals externe partnergroepen en Microsoft Support. Standaard kan deze groep geen rollen toegewezen krijgen. Het is echter lid van de rol Beveiligingslezers in Azure Active Directory en erft de mogelijkheden van die rol over. Als u machtigingen centraal wilt beheren, brengt u wijzigingen aan in deze rol in het Azure Active Directory-beheercentrum - zie [beheerdersrolmachtigingen voor](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)meer informatie in Azure Active Directory . Als u deze rolgroep bewerkt in het Security & Compliance Center, zijn deze wijzigingen alleen van toepassing op het Security & Compliance Center en geen andere services, terwijl wijzigingen in het Azure Active Directory-beheercentrum van invloed zijn op alle services|Beveiligingslezer <br/><br/> Gevoeligheidslabellezer <br/><br/> DLP-compliancebeheer met alleen weergeven <br/><br/> Apparaatbeheer alleen weergeven <br/><br/> Alleen-overzicht IB Compliance Management <br/><br/> Alleen weergeven Waarschuwingen beheren|
|**Service Assurance-gebruiker**|Leden hebben toegang tot de sectie Service assurance in het Security & Compliance Center. Servicebeveiliging biedt rapporten en documenten waarin de beveiligingspraktijken van Microsoft worden beschreven voor klantgegevens die zijn opgeslagen in Microsoft 365. Het biedt ook onafhankelijke externe auditrapporten over Microsoft 365. Zie [Servicegarantie in het Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)voor meer informatie.|Serviceborgingsweergave|
|**Toezicht review**|Leden kunnen het beleid maken en beheren dat bepaalt welke communicatie in een organisatie moet worden gecontroleerd. Zie [Communicatienalevingsbeleid configureren voor uw organisatie voor](../../compliance/communication-compliance-configure.md)meer informatie.|Beheerder van toezichtcontrole|
|

> [!NOTE]
> <sup>1.</sup> Deze rolgroep geeft leden niet de machtigingen die nodig zijn om in het controlelogboek te zoeken of om rapporten te gebruiken die Exchange-gegevens kunnen bevatten, zoals de DLP- of ATP-rapporten. Als u in het controlelogboek wilt zoeken of alle rapporten wilt bekijken, moet een gebruiker machtigingen krijgen toegewezen in Exchange Online. Dit komt omdat de onderliggende cmdlet die wordt gebruikt om het controlelogboek te doorzoeken een Exchange Online-cmdlet is. Globale beheerders kunnen in het controlelogboek zoeken en alle rapporten bekijken omdat ze automatisch worden toegevoegd als leden van de rolgroep Organisatiebeheer in Exchange Online. [Zie Zoeken in het controlelogboek in het Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)voor meer informatie.

## <a name="roles-in-the-security--compliance-center"></a>Rollen in het Security & Compliance Center

In de volgende tabel worden de beschikbare rollen en de rolgroepen weergegeven waaraan ze standaard zijn toegewezen.

Houd er rekening mee dat de volgende rollen standaard niet zijn toegewezen aan de rolgroep Organisatiebeheer:

- Communicatie
- Beheerder van communicatienaleving
- Analyse van communicatienaleving
- Communicatie Compliance Case Management
- Onderzoek naar naleving van communicatie
- Nalevingsviewer voor communicatie
- Voogd
- Inhoudsviewer voor gegevensclassificatie
- Feedbackprovider voor gegevensclassificatie
- Beoordelingsrecensent voor gegevensclassificatie
- Viewer voor lijst met gegevensclassificatie
- Beheer van gegevensonderzoek
- Beheer van de dispositie
- Exporteren
- Insider Risk Management Admin
- Analyse van insiderrisicobeheer
- Onderzoek naar insiderrisicobeheer
- Tijdelijke bijdrage van Insider Risk Management
- Voorbeeld
- Review
- RMS decoderen
- Beheerder van toezichtcontrole

||||
|---|---|---|
|**Rol**|**Beschrijving**|**Standaardrolgroeptoewijzingen**|
|**Controlelogboeken**|Schakel controle voor de organisatie in en configureer deze, bekijk de controlerapporten van de organisatie en exporteer deze rapporten naar een bestand.|Organisatiebeheer <br/><br/> Beveiligingsbeheerder|
|**Casemanagement**|Maak, bewerk, verwijder en beheer de toegang tot eDiscovery-aanvragen.|Compliance-beheerder <br/><br/> eDiscovery Manager <br/><br/> Intern risicobeheer <br/><br/> Insider Risk Management Admins <br/><br/> Insider Risk Management Analisten <br/><br/> Insider Risk Management Onderzoekers <br/><br/> Organisatiebeheer|
|**Communicatie**|Beheer alle communicatie met de bewaarders die zijn geïdentificeerd in een Advanced eDiscovery-aanvraag.  Maak wachtmeldingen, houd herinneringen vast en escaleert naar beheer. Volg de erkenning van de bewaarder van hold-meldingen en beheer de toegang tot het beheerdersportaal dat door elke bewaarder wordt gebruikt in een geval om de communicatie bij te houden voor de gevallen waarin ze als bewaarder zijn geïdentificeerd.|eDiscovery Manager|
|**Beheerder van communicatienaleving**|Wordt gebruikt om beleid te beheren in de functie Communicatienaleving.|Compliance-beheerder|
|**Analyse van communicatienaleving**|Wordt gebruikt voor het uitvoeren van onderzoek, het herstellen van de berichtschendingen in de functie Communicatienaleving. Kan alleen bericht metagegevens bekijken.|Compliance-beheerder|
|**Communicatie Compliance Case Management**|Wordt gebruikt om toegang te krijgen tot communicatiecompliance-aanvragen.|Compliance-beheerder|
|**Onderzoek naar naleving van communicatie**|Wordt gebruikt voor het uitvoeren van schendingen van onderzoek, herstel en beoordeling van berichten in de functie Naleving van communicatie. Kan bericht metagegevens en berichten bekijken.|Compliance-beheerder|
|**Nalevingsviewer voor communicatie**|Wordt gebruikt om toegang te krijgen tot rapporten en widgets in de functie Naleving van communicatie.||
|**Compliance-beheerder**|Instellingen en rapporten voor nalevingsfuncties weergeven en bewerken.|Compliance-beheerder <br/><br/> Beheerder van compliancegegevens <br/><br/> Organisatiebeheer|
|**Nalevingszoekopdracht**|Voer zoekopdrachten uit in verschillende postvakken en ontvang een schatting van de resultaten.|Compliance-beheerder <br/><br/> Beheerder van compliancegegevens <br/><br/> eDiscovery Manager <br/><br/> Organisatiebeheer <br/><br/> Beveiligingsoperator|
|**Voogd**|Identificeer en beheer bewaarders voor geavanceerde eDiscovery-aanvragen en gebruik de informatie uit Azure Active Directory en andere bronnen om gegevensbronnen te vinden die zijn gekoppeld aan bewaarders. Koppel andere gegevensbronnen zoals postvakken, SharePoint-sites en Teams aan bewaarders in een aanvraag.  Plaats een wettelijke greep op de gegevensbronnen die zijn gekoppeld aan bewaarders om inhoud te bewaren in de context van een zaak.|eDiscovery Manager|
|**Inhoudsviewer voor gegevensclassificatie**|Weergave op zijn plaats van bestanden weergeven in Content explorer.|Content Explorer-inhoudsviewer|
|**Feedbackprovider voor gegevensclassificatie**|Hiermee kunnen classificeerders feedback geven in content explorer.|Compliance-beheerder|
|**Beoordelingsrecensent voor gegevensclassificatie**|Hiermee u feedback van classificaties in feedback explorer bekijken.|Compliance-beheerder|
|**Viewer voor lijst met gegevensclassificatie**|Bekijk de lijst met bestanden in content explorer.|Lijstviewer voor inhoudsverkenner|
|**Beheer van gegevensonderzoek**|Maak, bewerk, verwijder en beheer de toegang tot gegevensonderzoeken.|Compliance-beheerder <br/><br/> Data-onderzoeker|
|**Apparaatbeheer**|Instellingen en rapporten voor apparaatbeheerfuncties weergeven en bewerken.|Compliance-beheerder <br/><br/> Beheerder van compliancegegevens <br/><br/> Organisatiebeheer <br/><br/> Beveiligingsbeheerder|
|**Beheer van de dispositie**|Besturingselementmachtigingen voor handmatige dispositie in het Security & Compliance Center.|Compliance-beheerder <br/><br/> Beheerder van compliancegegevens|
|**DLP Compliance Management**|Instellingen en rapporten weergeven en bewerken voor het DLP-beleid (Data Loss Prevention).|Compliance-beheerder <br/><br/> Beheerder van compliancegegevens <br/><br/> Organisatiebeheer <br/><br/> Beveiligingsbeheerder|
|**Exporteren**|Exporteer postvak- en site-inhoud die is geretourneerd uit zoekopdrachten.|eDiscovery Manager|
|**Houden**|Plaats inhoud in postvakken, sites en openbare mappen in de wachtstand. Wanneer in de wacht staat, wordt een kopie van de inhoud op een veilige locatie opgeslagen. Eigenaren van inhoud kunnen de oorspronkelijke inhoud nog steeds wijzigen of verwijderen.|Compliance-beheerder <br/><br/> eDiscovery Manager <br/><br/> Organisatiebeheer|
|**IB Compliance Management**|Informatiebarrièrebeleid weergeven, maken, verwijderen, wijzigen en testen.|Compliance-beheerder <br/><br/> Beheerder van compliancegegevens <br/><br/> Organisatiebeheer <br/><br/> Beveiligingsbeheerder|
|**Insider Risk Management Admin**|Maak, bewerk, verwijder en beheer de toegang tot de functie Insider-risicobeheer.|Intern risicobeheer <br/><br/> Insider Risk Management Admins|
|**Analyse van insiderrisicobeheer**|Krijg toegang tot alle insider risk management alerts, cases en notices templates.|Intern risicobeheer <br/><br/> Insider Risk Management Analisten|
|**Onderzoek naar insiderrisicobeheer**|Krijg toegang tot alle insider risk management alerts, cases, notices templates en de Content Explorer voor alle cases.|Intern risicobeheer <br/><br/> Insider Risk Management Onderzoekers|
|**Tijdelijke bijdrage van Insider Risk Management**|Deze rolgroep is zichtbaar, maar wordt alleen gebruikt door achtergrondservices.|IRM-bijdragers|
|**Waarschuwingen beheren**|Instellingen en rapporten voor waarschuwingen weergeven en bewerken.|Compliance-beheerder <br/><br/> Beheerder van compliancegegevens <br/><br/> Organisatiebeheer <br/><br/> Beveiligingsbeheerder <br/><br/> Beveiligingsoperator|
|**Organisatieconfiguratie**|Voer controlerapporten uit, bekijk en exporteer en beheer nalevingsbeleid voor DLP, apparaten en bewaring.|Compliance-beheerder <br/><br/> Beheerder van compliancegegevens <br/><br/> Organisatiebeheer|
|**Voorbeeld**|Bekijk een lijst met items die zijn geretourneerd uit zoekopdrachten in inhoud en open elk item uit de lijst om de inhoud ervan weer te geven.|eDiscovery Manager|
|**Quarantaine**|Hiermee u in quarantaine geplaatste e-mail bekijken en vrijgeven.|Quarantainebeheerder <br/><br/> Beveiligingsbeheerder <br/><br/> Organisatiebeheer|
|**RecordManagement**|De configuratie en rapporten voor de functie Recordbeheer weergeven en bewerken.|Compliance-beheerder <br/><br/> Beheerder van compliancegegevens <br/><br/> Organisatiebeheer <br/><br/> Records Management|
|**Retentiebeheer**|Bewaarbeleid beheren.|Compliance-beheerder <br/><br/> Beheerder van compliancegegevens <br/><br/> Organisatiebeheer|
|**Review**|Gebruik Advanced eDiscovery om documenten bij te houden, te taggen, analyseren en te testen die aan hen zijn toegewezen.|eDiscovery Manager <br/><br/> Revisor|
|**RMS decoderen**|Ontsleutel rms-beveiligde inhoud bij het exporteren van zoekresultaten.|eDiscovery Manager|
|**Rolbeheer**|Het lidmaatschap van de rolgroep beheren en aangepaste rolgroepen maken of verwijderen.|Organisatiebeheer|
|**Zoeken en zuiveren**|Hiermee kunnen mensen gegevens die overeenkomen met de criteria van een inhoudszoekopdracht in bulk verwijderen.|Organisatiebeheer|
|**Beveiligingsbeheerder**|De configuratie en rapporten voor beveiligingsfuncties weergeven en bewerken.|Organisatiebeheer <br/><br/> Beveiligingsbeheerder|
|**Beveiligingslezer**|Bekijk de configuratie en rapporten voor beveiligingsfuncties.|Organisatiebeheer <br/><br/> Beveiligingsoperator <br/><br/> Beveiligingslezer|
|**Gevoeligheidslabelbeheerder**|Gevoeligheidslabels weergeven, maken, wijzigen en verwijderen.|Beheerder van compliancegegevens <br/><br/> Organisatiebeheer <br/><br/> Beveiligingsbeheerder|
|**Gevoeligheidslabellezer**|Bekijk de configuratie en het gebruik van gevoeligheidslabels.|Global Reader <br/><br/> Organisatiebeheer <br/><br/> Beveiligingslezer|
|**Serviceborgingsweergave**|Download de beschikbare documenten in de sectie Service Assurance. Inhoud omvat onafhankelijke controle, nalevingsdocumentatie en vertrouwensgerelateerde richtlijnen voor het gebruik van Microsoft 365-functies om naleving van de regelgeving en beveiligingsrisico's te beheren.|Service Assurance-gebruiker <br/><br/> Organisatiebeheer|
|**Beheerder van toezichtcontrole**|Beheer toezichtbeoordelingsbeleid, inclusief welke communicatie moet worden gecontroleerd en wie de beoordeling moet uitvoeren.|Toezicht review|
|**Controlelogboeken met alleen weergeven**|Controlerapporten weergeven en exporteren. Omdat deze rapporten mogelijk gevoelige informatie bevatten, moet u deze rol alleen toewijzen aan mensen met een expliciete behoefte om deze informatie te bekijken.|Compliance-beheerder <br/><br/> Beheerder van compliancegegevens <br/><br/> Organisatiebeheer <br/><br/> Beveiligingsbeheerder <br/><br/> Beveiligingsoperator|
|**Apparaatbeheer alleen weergeven**|Bekijk de configuratie en rapporten voor de functie Apparaatbeheer.|Compliance-beheerder <br/><br/> Beheerder van compliancegegevens <br/><br/> Organisatiebeheer <br/><br/> Beveiligingsbeheerder <br/><br/> Beveiligingsoperator <br/><br/> Beveiligingslezer|
|**DLP-compliancebeheer met alleen weergeven**|Bekijk de instellingen en rapporten voor het DLP-beleid (Data Loss Prevention).|Compliance-beheerder <br/><br/> Beheerder van compliancegegevens <br/><br/> Organisatiebeheer <br/><br/> Beveiligingsbeheerder <br/><br/> Beveiligingsoperator <br/><br/> Beveiligingslezer|
|**Alleen-overzicht IB Compliance Management**|Bekijk de configuratie en rapporten voor de functie Informatiebarrières.|Compliance-beheerder <br/><br/> Beheerder van compliancegegevens <br/><br/> Organisatiebeheer <br/><br/> Beveiligingsbeheerder <br/><br/> Beveiligingsoperator <br/><br/> Beveiligingslezer|
|**Alleen weergeven Waarschuwingen beheren**|Bekijk de configuratie en rapporten voor de functie Waarschuwingen beheren.|Beveiligingsbeheerder <br/><br/> Beveiligingsoperator <br/><br/> Beveiligingslezer <br/><br/> Compliance-beheerder <br/><br/> Beheerder van compliancegegevens <br/><br/> Organisatiebeheer|
|**Ontvangers alleen weergeven**|Informatie over gebruikers en groepen weergeven.|MailFlow-beheerder <br/><br/> Compliance-beheerder <br/><br/> Beheerder van compliancegegevens <br/><br/> Organisatiebeheer|
|**Recordbeheer alleen weergeven**|Bekijk de configuratie en rapporten voor de functie Recordbeheer.|Compliance-beheerder <br/><br/> Beheerder van compliancegegevens <br/><br/> Organisatiebeheer|
|**Alleen-weergeven retentiebeheer**|Bekijk de configuratie en rapporten voor de functie Retentiebeheer.|Beheerder van compliancegegevens <br/><br/> Organisatiebeheer <br/><br/> Compliance-beheerder|
|
