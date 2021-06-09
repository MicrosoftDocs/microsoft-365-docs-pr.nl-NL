---
title: Machtigingen - Beveiligingscentrum & compliancecentrum
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.AdminRoleGroups
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
description: Beheerders kunnen meer informatie krijgen over de machtigingen die beschikbaar zijn in het & compliancecentrum in Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a2be234805977dd1efce10032e36113a460f3d96
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769879"
---
# <a name="permissions-in-the-security--compliance-center"></a>Machtigingen in het beveiligings- en compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Met het & Compliancecentrum voor beveiliging kunt u machtigingen verlenen aan personen die compliancetaken uitvoeren, zoals apparaatbeheer, preventie van gegevensverlies, eDiscovery, bewaring, en ga zo maar door. Deze personen kunnen alleen de taken uitvoeren die u hen expliciet toegang verleent. Als u toegang wilt tot & compliancecentrum, moeten gebruikers een globale beheerder of lid zijn van een of meer rollengroepen & beveiligingscentrum.

Machtigingen in het Beveiligings- & compliancecentrum zijn gebaseerd op het RBAC-machtigingsmodel (Role Based Access Control). RBAC is hetzelfde machtigingsmodel dat wordt gebruikt door Exchange, dus als u bekend bent met Exchange, is het verlenen van machtigingen in het Compliancecentrum voor beveiliging & vergelijkbaar. Het is echter belangrijk om te onthouden dat Exchange rollengroepen en & compliancecentrum geen lidmaatschap of machtigingen delen. Hoewel beide een rollengroep Organisatiebeheer hebben, zijn ze niet hetzelfde. De machtigingen die ze verlenen en de leden van de rollengroepen, zijn verschillend. Hieronder vindt u een lijst met & beveiligingscentrum.

![Pagina Machtigingen in het beveiligings- & compliancecentrum](../../media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)

## <a name="relationship-of-members-roles-and-role-groups"></a>Relatie van leden, rollen en rollengroepen

Een **rol** verleent machtigingen om een set taken uit te voeren. Met de rol Case Management kunnen personen bijvoorbeeld met eDiscovery-zaken werken.

Een **rollengroep** is een set rollen waarmee personen hun werk kunnen doen in het beveiligings- & compliancecentrum. De rollengroep Compliancebeheerder bevat bijvoorbeeld (onder andere rollen) de rollen voor Case Management, Inhoud zoeken en Organisatieconfiguratie (plus anderen), omdat iemand die een compliancebeheerder is, de machtigingen voor deze taken nodig heeft om zijn of haar taak uit te voeren.

Het Beveiligings- & compliancecentrum bevat standaardrolgroepen voor de meest voorkomende taken en functies die u nodig hebt om personen toe te wijzen. Het is raadzaam om alleen afzonderlijke gebruikers als **leden toe te** voegen aan de standaardrolgroepen.

![Diagram met de relatie van rollengroepen met rollen en leden](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="role-groups-in-the-security--compliance-center"></a>Rollengroepen in het beveiligings- & compliancecentrum

De volgende tabel bevat de standaardrolgroepen die beschikbaar zijn in het Beveiligings- & Compliancecentrum en de rollen die standaard aan de rollengroepen zijn toegewezen. Als u machtigingen wilt verlenen aan een gebruiker om een compliancetaak uit te voeren, voegt u deze toe aan de juiste rollengroep & beveiligingscentrum.

Het beheren van machtigingen in & compliancecentrum biedt gebruikers alleen toegang tot de compliancefuncties die beschikbaar zijn in het beveiligings- & compliancecentrum zelf. Als u machtigingen wilt verlenen voor andere compliancefuncties die zich niet in het Beveiligings- & Compliancecentrum, zoals Exchange-regels voor e-mailstroom (ook wel transportregels genoemd), moet u het Exchange-beheercentrum gebruiken.

Als u wilt zien hoe u toegang verleent tot het Beveiligings- & Compliancecentrum, raadpleegt u Gebruikers toegang geven [tot Microsoft 365 Compliance-beheercentrum.](grant-access-to-the-security-and-compliance-center.md)

> [!NOTE]
> Als u het **tabblad Machtigingen** wilt weergeven in het beveiligings- & compliancecentrum, moet u een beheerder zijn. U moet in het bijzonder  de rol Rollenbeheer krijgen toegewezen en  deze rol wordt standaard alleen toegewezen aan de rollengroep Organisatiebeheer in het Beveiligings- & Compliancecentrum. Bovendien kunnen gebruikers met **de rol** rolbeheer rollengroepen bekijken, maken en wijzigen.

<br>

****

|Rollengroep|Beschrijving|Standaardrollen toegewezen|
|---|---|---|
|**Naleving van communicatie**|Geeft machtigingen voor alle communicatie compliancerollen: beheerder, analist, onderzoeker en viewer.|Case Management <p> Communicatie compliancebeheerder <p> Communicatie compliance-analyse <p> Communicatie compliance case management <p> Communicatie compliance-onderzoek <p> Viewer voor communicatie compliance <p> Feedbackprovider voor gegevensclassificatie <p> View-Only Case|
|**Communicatie compliancebeheerders**|Beheerders van communicatie compliance die beleidsregels kunnen maken/bewerken en globale instellingen kunnen definiëren.|Communicatie compliancebeheerder <p> Communicatie compliance case management|
|**Communicatie-complianceanalisten**|Analisten van communicatie compliance die beleidsafdy's kunnen onderzoeken, metagegevens van berichten kunnen bekijken en herstelacties kunnen uitvoeren.|Communicatie compliance-analyse <p> Communicatie compliance case management|
|**Communicatie compliance-onderzoeker**|Analisten van communicatie compliance die beleidscondy's kunnen onderzoeken, berichtinhoud kunnen bekijken en herstelacties kunnen uitvoeren.|Case Management <p> Communicatie compliance-analyse <p> Communicatie compliance case management <p> Communicatie compliance-onderzoek <p> Feedbackprovider voor gegevensclassificatie <p> View-Only Case|
|**Communicatie compliance viewers**|Viewer of communication compliance that can access the available reports and widgets.|Communicatie compliance case management <p> Viewer voor communicatie compliance|
|**Compliancebeheerder**<sup>1</sup>|Leden kunnen instellingen voor apparaatbeheer, preventie van gegevensverlies, rapporten en bewaring beheren.|Case Management <p> Compliancebeheerder <p> Compliancezoekactie <p> Feedbackprovider voor gegevensclassificatie <p> Feedbackrecensor voor gegevensclassificatie <p> Apparaatbeheer <p> Disposition Management <p> DLP-compliancebeheer <p> Wacht houden <p> IB Compliance Management <p> Waarschuwingen beheren <p> Organisatieconfiguratie <p> RecordManagement <p> Bewaarbeheer <p> View-Only auditlogboeken <p> View-Only Case <p> View-Only Apparaatbeheer <p> View-Only DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Waarschuwingen beheren <p> View-Only Geadresseerden <p> View-Only recordbeheer <p> View-Only Bewaarbeheer|
|**Compliancegegevensbeheerder**|Leden kunnen instellingen voor apparaatbeheer, gegevensbescherming, preventie van gegevensverlies, rapporten en bewaring beheren.|Compliancebeheerder <p> Compliancezoekactie <p> Apparaatbeheer <p> DLP-compliancebeheer <p> Disposition Management <p> IB Compliance Management <p> Waarschuwingen beheren <p> Organisatieconfiguratie <p> RecordManagement <p> Bewaarbeheer <p> Gevoeligheidslabelbeheerder <p> View-Only auditlogboeken <p> View-Only Apparaatbeheer <p> View-Only DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Waarschuwingen beheren <p> View-Only Geadresseerden <p> View-Only recordbeheer <p> View-Only Bewaarbeheer|
|**Beheerders van compliancebeheer**|Het maken en wijzigen van sjabloon beheren.|Beheer van compliancebeheer <p> Compliance manager-evaluatie <p> Bijdrage compliancebeheer <p> Compliancebeheer - Lezer|
|**Compliance manager-beoordelaars**|Maak evaluaties, implementeert verbeteracties en werk de teststatus bij voor verbeteracties.|Compliance manager-evaluatie <p> Bijdrage compliancebeheer <p> Compliancebeheer - Lezer|
|**Inzenders van Compliance Manager**|Maak evaluaties en voer werk uit om verbeteracties te implementeren.|Bijdrage compliancebeheer <p> Compliancebeheer - Lezer|
|**Lezers van Compliance Manager**|Alle inhoud van Compliance Manager weergeven, behalve beheerdersfuncties.|Compliancebeheer - Lezer|
|**Inhoudsverkenner Inhoudsviewer**|Bekijk de inhoudsbestanden in Inhoudsverkenner.|Inhoudsviewer voor gegevensclassificatie|
|**Inhoudsverkenner-lijstviewer**|Alle items in Inhoudsverkenner alleen weergeven in lijstindeling.|Gegevensclassificatielijstviewer|
|**eDiscovery Manager**|Leden kunnen zoekopdrachten uitvoeren en postvakken, SharePoint onlinesites en OneDrive voor Bedrijven plaatsen. Leden kunnen ook eDiscovery-zaken maken en beheren, leden toevoegen en verwijderen aan een zaak, inhoudszoekingen maken en bewerken die zijn gekoppeld aan een zaak en toegang krijgen tot casegegevens in Advanced eDiscovery. <p> Een eDiscovery-beheerder is lid van de rollengroep eDiscovery Manager die extra machtigingen heeft gekregen. Naast de taken die een eDiscovery Manager kan uitvoeren, kan een eDiscovery-beheerder het volgende doen:<ul><li>Bekijk alle eDiscovery-zaken in de organisatie.</li><li>Beheer een eDiscovery-zaak nadat ze zichzelf hebben toevoegen als lid van de zaak.</li></ul> <p> Het primaire verschil tussen een eDiscovery Manager en een eDiscovery-beheerder is dat een eDiscovery-beheerder toegang heeft tot alle zaken die worden vermeld op de **pagina eDiscovery-zaken** in het beveiligings- & compliancecentrum. Een eDiscovery-manager heeft alleen toegang tot de zaken waar hij of zij lid van is. Zie eDiscovery-machtigingen toewijzen in het beveiligings- & compliancecentrum voor meer informatie over het maken van een gebruiker [als eDiscovery-beheerder.](../../compliance/assign-ediscovery-permissions.md)|Case Management <p> Communicatie <p> Compliancezoekactie <p> Bewaarder <p> Exporteren <p> Wacht houden <p> Voorbeeld <p> Beoordelen <p> RMS Decrypt|
|**Algemene lezer**|Leden hebben alleen-lezen toegang tot rapporten, waarschuwingen en kunnen alle configuraties en instellingen zien.<p> Het primaire verschil tussen globale lezer en beveiligingslezer is dat een globale lezer toegang heeft tot **configuratie en instellingen.**|Beveiligingslezer <p> Gevoeligheidslabellezer <p> Servicecontroleweergave <p> View-Only auditlogboeken <p> View-Only Apparaatbeheer <p> View-Only DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Waarschuwingen beheren <p> View-Only Geadresseerden <p> View-Only recordbeheer <p> View-Only Bewaarbeheer|
|**Insider Risk Management**|Gebruik deze rollengroep om insiderrisicobeheer voor uw organisatie in één groep te beheren. Door alle gebruikersaccounts toe te voegen voor aangewezen beheerders, analisten en onderzoeker, kunt u machtigingen voor insiderrisicobeheer configureren in één groep. Deze rollengroep bevat alle machtigingsrollen voor insiderrisicobeheer. Dit is de eenvoudigste manier om snel aan de slag te gaan met insider risk management en is een goede manier voor organisaties die geen afzonderlijke machtigingen nodig hebben die zijn gedefinieerd voor afzonderlijke groepen gebruikers.|Case Management <p> Insider Risk Management Admin <p> Insider-risicobeheeranalyse <p> Insider Risk Management Investigation <p> View-Only Case|
|**Insider-beheerders van risicobeheer**|Gebruik deze rollengroep om in eerste instantie insiderrisicobeheer te configureren en later om beheerders van insiderrisico's te scheiden in een gedefinieerde groep. Gebruikers in deze rollengroep kunnen beleidsregels voor insiderrisicobeheer, globale instellingen en rollengroeptoewijzingen maken, lezen, bijwerken en verwijderen.|Case Management <p> Insider Risk Management Admin <p> View-Only Case|
|**Analist intern risicobeheer**|Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die fungeren als insiderrisicocaseanalisten. Gebruikers in deze rollengroep hebben toegang tot alle insider-risicobeheerwaarschuwingen, -gevallen- en kennisgevingssjablonen. Ze hebben geen toegang tot inhoudsverkenner voor insiderrisico's.|Case Management <p> Insider-risicobeheeranalyse <p> View-Only Case|
|**Insider Risk Management Auditors**|Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die activiteiten voor insiderrisicobeheer controleren. Gebruikers in deze rollengroep hebben toegang tot het auditlogboek voor insiderrisico's.|Insider Risk Management Audit|
|**Onderzoeker intern risicobeheer**|Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die fungeren als insider-risicogegevensonderzoekers. Gebruikers in deze rollengroep hebben toegang tot alle waarschuwingen voor insiderrisicobeheer, cases, kennisgevingssjablonen en de Inhoudsverkenner voor alle gevallen.|Case Management <p> Insider Risk Management Investigation <p> View-Only Case|
|**IRM-medewerkers**|Deze rollengroep is zichtbaar, maar wordt alleen gebruikt door achtergrondservices.|Permanente bijdrage voor Insider Risk Management <p> Tijdelijke bijdrage voor Insider Risk Management|
|**MailFlow-beheerder**|Leden kunnen e-mailstroominzichten en -rapporten in het beveiligings- & bekijken. Globale beheerders kunnen gewone gebruikers toevoegen aan deze groep, maar als de gebruiker geen lid is van de groep Exchange-beheerder, heeft de gebruiker geen toegang tot Exchange beheerderstaken.|View-Only Geadresseerden|
|**Organisatiebeheer**<sup>1</sup>|Leden kunnen machtigingen voor toegang tot functies in het Beveiligings- & Compliancecentrum beheren en ook instellingen beheren voor apparaatbeheer, preventie van gegevensverlies, rapporten en bewaring. <p> Gebruikers die geen globale beheerders zijn, moeten Exchange-beheerders zijn om te zien en actie te ondernemen op apparaten die worden beheerd door Basismobiliteit en Beveiliging voor Microsoft 365 (voorheen bekend als Mobile Device Management of MDM). <p> Globale beheerders worden automatisch toegevoegd als leden van deze rollengroep.|Auditlogboeken <p> Case Management <p> Compliancebeheerder <p> Compliancezoekactie <p> Apparaatbeheer <p> DLP-compliancebeheer <p> Wacht houden <p> IB Compliance Management <p> Waarschuwingen beheren <p> Organisatieconfiguratie <p> Quarantaine <p> RecordManagement <p> Bewaarbeheer <p> Rollenbeheer <p> Zoeken en zuiveren <p> Beveiligingsbeheerder <p> Beveiligingslezer <p> Gevoeligheidslabelbeheerder <p> Gevoeligheidslabellezer <p> Servicecontroleweergave <p> Inzender taggen <p> Tag Manager <p> Taglezer <p> View-Only auditlogboeken <p> View-Only Apparaatbeheer <p> View-Only DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Case <p> View-Only Waarschuwingen beheren <p> View-Only Geadresseerden <p> View-Only recordbeheer <p> View-Only Bewaarbeheer|
|**Quarantainebeheerder**|Leden hebben toegang tot alle quarantaineacties. Zie Berichten en bestanden in quarantaine beheren als [beheerder in EOP](manage-quarantined-messages-and-files.md) voor meer informatie.|Quarantaine|
|**Recordbeheer**|Leden kunnen alle aspecten van recordbeheer configureren, inclusief bewaarlabels en dispositiebeoordelingen.|Disposition Management <p> RecordManagement <p> Bewaarbeheer|
|**Revisor**|Leden hebben toegang tot revisiesets in [Advanced eDiscovery](../../compliance/overview-ediscovery-20.md) gevallen. Leden van deze rollengroep kunnen de lijst met zaken bekijken en openen op de **pagina eDiscovery > Geavanceerd** in het Microsoft 365 compliancecentrum waar ze lid van zijn. Nadat de gebruiker toegang heeft tot een Advanced eDiscovery, kunnen ze Sets **controleren** selecteren om toegang te krijgen tot casegegevens. Met deze rol kan de gebruiker geen voorbeeld bekijken van de resultaten van een verzamelingszoekactie die is gekoppeld aan de zaak of andere zoek- of casebeheertaken uitvoeren. Leden van deze rollengroep hebben alleen toegang tot de gegevens in een revisieset.|Beoordelen|
|**Beveiligingsbeheerder**|Leden hebben toegang tot een aantal beveiligingsfuncties van het Identity Protection Center, Privileged Identity Management, Monitor Microsoft 365 Service Health en Security & Compliance Center. <p> Deze rollengroep lijkt standaard geen leden te hebben. De rol Beveiligingsbeheerder van Azure Active Directory is echter toegewezen aan deze rollengroep. Daarom neemt deze rollengroep de mogelijkheden en het lidmaatschap van de rol Beveiligingsbeheerder over van Azure Active Directory. <p> Als u machtigingen centraal wilt beheren, voegt u groepsleden toe en verwijdert u deze in het Azure Active Directory beheercentrum. Zie Beheerdersrolmachtigingen [in](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)Azure Active Directory. Als u deze rollengroep bewerkt in het Beveiligings- & Compliancecentrum (lidmaatschap of rollen), zijn deze wijzigingen alleen van toepassing op het Beveiligings- & Compliancecentrum en niet op andere services. <p> Deze rollengroep bevat alle alleen-lezen machtigingen van de rol Beveiligingslezer, plus een aantal extra beheerdersmachtigingen voor dezelfde services: Azure Information Protection, Identity Protection Center, Privileged Identity Management, Monitor Microsoft 365 Service Health en Security & Compliance Center.|Auditlogboeken <p> Apparaatbeheer <p> DLP-compliancebeheer <p> IB Compliance Management <p> Waarschuwingen beheren <p> Quarantaine <p> Beveiligingsbeheerder <p> Gevoeligheidslabelbeheerder <p> Inzender taggen <p> Tag Manager <p> Taglezer <p> View-Only auditlogboeken <p> View-Only Apparaatbeheer <p> View-Only DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Waarschuwingen beheren|
|**Beveiligingsoperator**|Leden kunnen beveiligingswaarschuwingen beheren en ook rapporten en instellingen van beveiligingsfuncties bekijken.|Compliancezoekactie <p> Waarschuwingen beheren <p> Beveiligingslezer <p> Inzender taggen <p> Taglezer <p> View-Only auditlogboeken <p> View-Only Apparaatbeheer <p> View-Only DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Waarschuwingen beheren|
|**Beveiligingslezer**|Leden hebben alleen-lezen toegang tot een aantal beveiligingsfuncties van het Identity Protection Center, Privileged Identity Management, Monitor Microsoft 365 Service Health en Security & Compliance Center. <p> Deze rollengroep lijkt standaard geen leden te hebben. De rol Beveiligingslezer van Azure Active Directory is echter toegewezen aan deze rollengroep. Daarom neemt deze rollengroep de mogelijkheden en het lidmaatschap van de rol Beveiligingslezer over van Azure Active Directory. <p> Als u machtigingen centraal wilt beheren, voegt u groepsleden toe en verwijdert u deze in het Azure Active Directory beheercentrum. Zie Beheerdersrolmachtigingen [in](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)Azure Active Directory. Als u deze rollengroep bewerkt in het Beveiligings- & Compliancecentrum (lidmaatschap of rollen), zijn deze wijzigingen alleen van toepassing op het Beveiligings- & Compliancecentrum en niet op andere services.|Beveiligingslezer <p> Gevoeligheidslabellezer <p> Taglezer <p> View-Only Apparaatbeheer <p> View-Only DLP Compliance Management <p> View-Only IB Compliance Management <p> View-Only Waarschuwingen beheren|
|**Service Assurance-gebruiker**|Leden hebben toegang tot de sectie Servicecontrole in het beveiligings- & Compliancecentrum. Servicecontrole biedt rapporten en documenten waarin de beveiligingspraktijken van Microsoft worden beschreven voor klantgegevens die zijn opgeslagen in Microsoft 365. Het bevat ook onafhankelijke auditrapporten van derden over Microsoft 365. Zie Servicecontrole [in het Beveiligings- & compliancecentrum voor meer informatie.](../../compliance/service-assurance.md)|Servicecontroleweergave|
|**Controle van toezicht**|Leden kunnen het beleid maken en beheren waarmee wordt bepaald welke communicatie in een organisatie moet worden beoordeeld. Zie Communicatie compliancebeleid [configureren voor uw organisatie voor meer informatie.](../../compliance/communication-compliance-configure.md)|Controlebeheerder|
|

> [!NOTE]
> <sup>1</sup> Met deze rollengroep worden leden niet de machtigingen toegewezen die nodig zijn om het auditlogboek te doorzoeken of om rapporten te gebruiken die mogelijk Exchange-gegevens bevatten, zoals de DLP- of Defender voor Office 365-rapporten. Als u het auditlogboek wilt doorzoeken of alle rapporten wilt weergeven, moet aan een gebruiker machtigingen zijn toegewezen in Exchange Online. Dat komt omdat de onderliggende cmdlet voor het doorzoeken van het auditlogboek een Exchange Online-cmdlet is. Globale beheerders kunnen zoeken in het auditlogboek en alle rapporten weergeven omdat ze automatisch worden toegevoegd als leden van de rollengroep Organisatiebeheer in Exchange Online. Zie Het auditlogboek doorzoeken in het beveiligings- & [compliancecentrum voor meer informatie.](../../compliance/search-the-audit-log-in-security-and-compliance.md)

## <a name="roles-in-the-security--compliance-center"></a>Rollen in het beveiligings- & compliancecentrum

De volgende tabel bevat de beschikbare rollen en de rollengroepen aan welke rollen ze standaard zijn toegewezen.

De volgende rollen zijn standaard niet toegewezen aan de rollengroep Organisatiebeheer:

- Attack Simulator Admin
- Auteur van Attack Simulator Payload
- Communicatie
- Communicatie compliancebeheerder
- Communicatie compliance-analyse
- Communicatie compliance case management
- Communicatie compliance-onderzoek
- Viewer voor communicatie compliance
- Beheer van compliancebeheer
- Compliance manager-evaluatie
- Bijdrage compliancebeheer
- Compliancebeheer - Lezer
- Bewaarder
- Inhoudsviewer voor gegevensclassificatie
- Feedbackprovider voor gegevensclassificatie
- Feedbackrecensor voor gegevensclassificatie
- Gegevensclassificatielijstviewer
- Disposition Management
- Exporteren
- Insider Risk Management Admin
- Insider-risicobeheeranalyse
- Insider Risk Management Audit
- Insider Risk Management Investigation
- Permanente bijdrage voor Insider Risk Management
- Tijdelijke bijdrage voor Insider Risk Management
- Voorbeeld
- Beoordelen
- RMS Decrypt
- Controlebeheerder

<br>

****

|Rol|Beschrijving|Standaardtoewijzingen voor rollengroep|
|---|---|---|
|**Attack Simulator Admin**|Wordt gebruikt om alle aspecten van aanvalssimulatiecampagnes te maken en te beheren.||
|**Auteur van Attack Simulator Payload**|Wordt gebruikt voor het maken en beheren van aanvalsladingen die kunnen worden geïmplementeerd door de beheerder van de aanvalssimulator.||
|**Auditlogboeken**|Schakel auditing voor de organisatie in en configureer deze, bekijk de controlerapporten van de organisatie en exporteert deze rapporten naar een bestand.|Organisatiebeheer <p> Beveiligingsbeheerder|
|**Case Management**|Maak, bewerk, verwijder en beheer de toegang tot eDiscovery-zaken.|Communicatiecompliance <p> Communicatie compliance-onderzoeker <p> Compliancebeheerder <p>eDiscovery Manager <p> Intern risicobeheer <p> Insider-beheerders van risicobeheer <p> Analist intern risicobeheer <p> Onderzoeker intern risicobeheer <p> Organisatiebeheer|
|**Communicatie**|Beheer alle communicatie met de bewaarders die zijn geïdentificeerd in Advanced eDiscovery geval.  Maak wachtmeldingen, houd herinneringen vast en escaleert naar beheer. Houd bewaarheidsbevestiging bij van wachtbevestigingen en beheer de toegang tot de bewaarportal die door elke bewaarder in een zaak wordt gebruikt om de communicatie bij te houden voor de gevallen waarin ze zijn geïdentificeerd als een bewaarder.|eDiscovery Manager|
|**Communicatie compliancebeheerder**|Wordt gebruikt voor het beheren van beleidsregels in de functie Communicatie compliance.|Communicatiecompliance <p> Communicatie compliancebeheerders|
|**Communicatie compliance-analyse**|Wordt gebruikt voor het uitvoeren van onderzoek, het herstellen van de berichtovertredingen in de functie Communicatie compliance. Kan alleen metagegevens van berichten weergeven.|Communicatiecompliance <p> Communicatie-complianceanalisten <p> Communicatie compliance-onderzoeker|
|**Communicatie compliance case management**|Wordt gebruikt om toegang te krijgen tot communicatie compliance-zaken.|Communicatiecompliance <p> Communicatie compliancebeheerders <p> Communicatie-complianceanalisten <p> Communicatie compliance-onderzoeker <p> Communicatie compliance viewers|
|**Communicatie compliance-onderzoek**|Wordt gebruikt voor het uitvoeren van onderzoek, herstel en het controleren van berichtovertredingen in de functie Communicatie compliance. Kan metagegevens en berichten van berichten weergeven.|Communicatiecompliance <p> Communicatie compliance-onderzoeker|
|**Viewer voor communicatie compliance**|Wordt gebruikt voor toegang tot rapporten en widgets in de functie Communicatie compliance.|Communicatiecompliance <p> Communicatie compliance viewers|
|**Compliancebeheerder**|Instellingen en rapporten voor compliancefuncties weergeven en bewerken.|Compliancebeheerder <p> Compliancegegevensbeheerder <p> Organisatiebeheer|
|**Beheer van compliancebeheer**|Het maken en wijzigen van sjabloon beheren.|Beheerders van compliancebeheer|
|**Compliance manager-evaluatie**|Maak evaluaties, implementeert verbeteracties en werk de teststatus bij voor verbeteracties.|Beheerders van compliancebeheer <p> Compliance manager-beoordelaars|
|**Bijdrage compliancebeheer**|Maak evaluaties en voer werk uit om verbeteracties te implementeren.|Beheerders van compliancebeheer <p> Compliance manager-beoordelaars <p> Inzenders van Compliance Manager|
|**Compliancebeheer - Lezer**|Alle inhoud van Compliance Manager weergeven, behalve beheerdersfuncties.|Beheerders van compliancebeheer <p> Compliance manager-beoordelaars <p> Inzenders van Compliance Manager <p> Lezers van Compliance Manager|
|**Compliancezoekactie**|Voer zoekopdrachten uit in postvakken en krijg een schatting van de resultaten.|Compliancebeheerder <p> Compliancegegevensbeheerder <p>eDiscovery Manager <p> Organisatiebeheer <p> Beveiligingsoperator|
|**Bewaarder**|Identificeer en beheer bewaarders voor Advanced eDiscovery zaken en gebruik de informatie uit Azure Active Directory en andere bronnen om gegevensbronnen te vinden die zijn gekoppeld aan bewaarders. Koppel andere gegevensbronnen, zoals postvakken, SharePoint sites en Teams in een zaak aan bewaarders.  Plaats een juridische greep op de gegevensbronnen die zijn gekoppeld aan bewaarders om inhoud in de context van een zaak te behouden.|eDiscovery Manager|
|**Inhoudsviewer voor gegevensclassificatie**|Weergave in-place weergave van bestanden in Inhoudsverkenner.|Inhoudsverkenner Inhoudsviewer|
|**Feedbackprovider voor gegevensclassificatie**|Hiermee kunt u feedback geven aan classificaties in inhoudsverkenner.|Communicatiecompliance <p> Communicatie compliance-onderzoeker <p> Compliancebeheerder|
|**Feedbackrecensor voor gegevensclassificatie**|Hiermee kunt u feedback van classificaties in feedbackverkenner bekijken.|Compliancebeheerder|
|**Gegevensclassificatielijstviewer**|Bekijk de lijst met bestanden in inhoudsverkenner.|Inhoudsverkenner-lijstviewer|
|**Apparaatbeheer**|Instellingen en rapporten voor apparaatbeheerfuncties weergeven en bewerken.|Compliancebeheerder <p> Compliancegegevensbeheerder <p> Organisatiebeheer <p> Beveiligingsbeheerder|
|**Disposition Management**|Beheermachtigingen voor het openen van Handmatige beschikking in het & Compliancecentrum.|Compliancebeheerder <p> Compliancegegevensbeheerder <p> Recordbeheer|
|**DLP-compliancebeheer**|Instellingen en rapporten voor DLP-beleid (Data Loss Prevention) weergeven en bewerken.|Compliancebeheerder <p> Compliancegegevensbeheerder <p> Organisatiebeheer <p> Beveiligingsbeheerder|
|**Exporteren**|Postvak en site-inhoud exporteren die wordt geretourneerd uit zoekopdrachten.|eDiscovery Manager|
|**Wacht houden**|Plaats inhoud in postvakken, sites en openbare mappen in de wacht. Wanneer u in de wacht staat, wordt een kopie van de inhoud op een veilige locatie opgeslagen. Inhoudseigenaren kunnen de oorspronkelijke inhoud nog steeds wijzigen of verwijderen.|Compliancebeheerder <p>eDiscovery Manager <p> Organisatiebeheer|
|**IB Compliance Management**|Beleidsregels voor informatiebarrière weergeven, maken, verwijderen, wijzigen en testen.|Compliancebeheerder <p> Compliancegegevensbeheerder <p> Organisatiebeheer <p> Beveiligingsbeheerder|
|**Insider Risk Management Admin**|Toegang tot insiderrisicobeheer maken, bewerken, verwijderen en beheren.|Intern risicobeheer <p> Insider-beheerders van risicobeheer|
|**Insider-risicobeheeranalyse**|Toegang tot alle insider risk management alerts, cases en notices templates.|Intern risicobeheer <p> Analist intern risicobeheer|
|**Insider Risk Management Audit**|Toestaan dat auditpaden voor Insider Risk worden bekeken.|Insider Risk Management Auditors|
|**Insider Risk Management Investigation**|Toegang tot alle waarschuwingen voor insider-risicobeheer, cases, kennisgevingssjablonen en de Inhoudsverkenner voor alle gevallen.|Intern risicobeheer <p> Onderzoeker intern risicobeheer|
|**Permanente bijdrage voor Insider Risk Management**|Deze rollengroep is zichtbaar, maar wordt alleen gebruikt door achtergrondservices.|IRM-medewerkers|
|**Tijdelijke bijdrage voor Insider Risk Management**|Deze rollengroep is zichtbaar, maar wordt alleen gebruikt door achtergrondservices.|IRM-medewerkers|
|**Waarschuwingen beheren**|Instellingen en rapporten voor waarschuwingen weergeven en bewerken.|Compliancebeheerder <p> Compliancegegevensbeheerder <p> Organisatiebeheer <p> Beveiligingsbeheerder <p> Beveiligingsoperator|
|**Organisatieconfiguratie**|Controlerapporten uitvoeren, weergeven en exporteren en compliancebeleid beheren voor DLP, apparaten en bewaring.|Compliancebeheerder <p> Compliancegegevensbeheerder <p> Organisatiebeheer|
|**Voorbeeld**|Bekijk een lijst met items die worden geretourneerd uit inhoudszoekingen en open elk item uit de lijst om de inhoud ervan weer te geven.|eDiscovery Manager|
|**Quarantaine**|Hiermee kunt u in quarantaine geplaatste e-mail weergeven en vrijgeven.|Quarantainebeheerder <p> Beveiligingsbeheerder <p> Organisatiebeheer|
|**RecordManagement**|Bekijk en bewerk de configuratie van de functie voor recordbeheer.|Compliancebeheerder <p> Compliancegegevensbeheerder <p> Organisatiebeheer <p> Recordbeheer|
|**Bewaarbeheer**|Bewaarbeleid, bewaarlabels en bewaarlabelbeleid beheren.|Compliancebeheerder <p> Compliancegegevensbeheerder <p> Organisatiebeheer <p> Recordbeheer|
|**Controle**|Met deze rol hebben gebruikers toegang tot revisiesets in Advanced eDiscovery gevallen. Gebruikers aan wie deze rol is toegewezen, kunnen de lijst met zaken zien en openen op de **pagina eDiscovery > Advanced** in het Microsoft 365 compliancecentrum waar ze lid van zijn. Nadat de gebruiker toegang heeft tot een Advanced eDiscovery, kunnen ze Sets **controleren** selecteren om toegang te krijgen tot casegegevens. Met deze rol kan de gebruiker geen voorbeeld bekijken van de resultaten van een verzamelingszoekactie die is gekoppeld aan de zaak of andere zoek- of casebeheertaken uitvoeren. Gebruikers met deze rol hebben alleen toegang tot de gegevens in een revisieset.|eDiscovery Manager <p> Revisor|
|**RMS Decrypt**|Ontsleutel RMS-beveiligde inhoud bij het exporteren van zoekresultaten.|eDiscovery Manager|
|**Rollenbeheer**|Beheer het lidmaatschap van rollengroepen en maak of verwijder aangepaste rollengroepen.|Organisatiebeheer|
|**Zoeken en zuiveren**|Hiermee kunnen personen gegevens bulksgewijs verwijderen die voldoen aan de criteria van een inhoudszoekactie.|Organisatiebeheer|
|**Beveiligingsbeheerder**|Bekijk en bewerk de configuratie en rapporten voor beveiligingsfuncties.|Organisatiebeheer <p> Beveiligingsbeheerder|
|**Beveiligingslezer**|Bekijk de configuratie en rapporten voor beveiligingsfuncties.|Algemene lezer <p> Organisatiebeheer <p> Beveiligingsoperator <p> Beveiligingslezer|
|**Gevoeligheidslabelbeheerder**|Gevoeligheidslabels weergeven, maken, wijzigen en verwijderen.|Compliancegegevensbeheerder <p> Organisatiebeheer <p> Beveiligingsbeheerder|
|**Gevoeligheidslabellezer**|Bekijk de configuratie en het gebruik van gevoeligheidslabels.|Algemene lezer <p> Organisatiebeheer <p> Beveiligingslezer|
|**Servicecontroleweergave**|Download de beschikbare documenten in de sectie Servicecontrole. Inhoud bevat onafhankelijke controle, compliancedocumentatie en vertrouwensgerelateerde richtlijnen voor het gebruik van Microsoft 365 functies voor het beheren van nalevings- en beveiligingsrisico's van regelgeving.|Algemene lezer <p> Organisatiebeheer <p> Service Assurance-gebruiker|
|**Controlebeheerder**|Beheer beleidsregels voor toezichtsbeoordeling, waaronder welke communicatie moet worden beoordeeld en wie de controle moet doen.|Controle van toezicht|
|**Inzender taggen**|Het lidmaatschap van bestaande gebruikerslabels weergeven en bijwerken.|Organisatiebeheer <p> Beveiligingsbeheerder <p> Beveiligingsoperator|
|**Tag Manager**|Gebruikerslabels weergeven, bijwerken, maken en verwijderen.|Organisatiebeheer <p> Beveiligingsbeheerder|
|**Taglezer**|Alleen-lezen toegang tot bestaande gebruikerslabels.|Beveiligingslezer|
|**Alleen-weergeven auditlogboeken**|Controlerapporten weergeven en exporteren. Omdat deze rapporten mogelijk gevoelige informatie bevatten, moet u deze rol alleen toewijzen aan personen met een expliciete noodzaak om deze informatie te bekijken.|Compliancebeheerder <p> Compliancegegevensbeheerder <p> Algemene lezer <p> Organisatiebeheer <p> Beveiligingsbeheerder <p> Beveiligingsoperator|
|**Alleen-weergeven-case**||Communicatiecompliance <p> Communicatie compliance-onderzoeker <p> Compliancebeheerder <p> Intern risicobeheer <p> Insider-beheerders van risicobeheer <p> Analist intern risicobeheer <p> Insider RiskManagement-onderzoeker <p> Organisatiebeheer|
|**Alleen-weergeven apparaatbeheer**|Bekijk de configuratie en rapporten voor de functie Apparaatbeheer.|Compliancebeheerder <p> Compliancegegevensbeheerder <p> Algemene lezer <p> Organisatiebeheer <p> Beveiligingsbeheerder <p> Beveiligingsoperator <p> Beveiligingslezer|
|**View-Only DLP Compliance Management**|Bekijk de instellingen en rapporten voor DLP-beleid (Data Loss Prevention).|Compliancebeheerder <p> Compliancegegevensbeheerder <p> Algemene lezer <p> Organisatiebeheer <p> Beveiligingsbeheerder <p> Beveiligingsoperator <p> Beveiligingslezer|
|**View-Only IB Compliance Management**|Bekijk de configuratie en rapporten voor de functie Informatiebarrières.|Compliancebeheerder <p> Compliancegegevensbeheerder <p> Algemene lezer <p> Organisatiebeheer <p> Beveiligingsbeheerder <p> Beveiligingsoperator <p> Beveiligingslezer|
|**Alleen-weergeven waarschuwingen beheren**|Bekijk de configuratie en rapporten voor de functie Waarschuwingen beheren.|Compliancebeheerder <p> Compliancegegevensbeheerder <p> Algemene lezer <p> Organisatiebeheer <p> Beveiligingsbeheerder <p> Beveiligingsoperator <p> Beveiligingslezer|
|**Alleen-weergeven geadresseerden**|Informatie over gebruikers en groepen weergeven.|Compliancebeheerder <p> Compliancegegevensbeheerder <p> Algemene lezer <p> MailFlow-beheerder <p> Organisatiebeheer|
|**Alleen-weergeven recordbeheer**|Bekijk de configuratie van de functie voor recordbeheer.|Compliancebeheerder <p> Compliancegegevensbeheerder <p> <p> Algemene lezer <p> Organisatiebeheer|
|**Alleen-weergeven bewaarbeheer**|Bekijk de configuratie van bewaarbeleid, bewaarlabels en bewaarlabelbeleid.|Compliancebeheerder <p> Compliancegegevensbeheerder <p> Globale beheerder <p> Organisatiebeheer|
|
