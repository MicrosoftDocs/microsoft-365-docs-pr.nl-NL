---
title: Machtigingen - & Compliancecentrum
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
ms.openlocfilehash: 170183cd31a770812f8bf59153123ffc66c8640c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288835"
---
# <a name="permissions-in-the-security--compliance-center"></a>Machtigingen in het beveiligings- en compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In het & beveiligingscentrum kunt u machtigingen verlenen aan personen die nalevingstaken uitvoeren, zoals apparaatbeheer, preventie van gegevensverlies, eDiscovery, bewaarbeleid, en meer. Deze personen kunnen alleen de taken uitvoeren die u hen expliciet toegang verleent. Voor toegang tot het & compliancecentrum moeten gebruikers een globale beheerder of lid zijn van een of meer rollengroepen & beveiligings- en compliancecentrum.

Machtigingen in het & compliancecentrum zijn gebaseerd op het model voor toegangsbeheer op basis van rollen. Toegangsstructuur is hetzelfde machtigingenmodel dat door Exchange wordt gebruikt, dus als u bekend bent met Exchange, zullen het verlenen van machtigingen in het beveiligings- & compliancecentrum sterk lijken. Het is echter belangrijk om te onthouden dat Exchange-rollengroepen en & compliancecentrum geen lidmaatschap of machtigingen delen. Hoewel beide een rollengroep Organisatiebeheer hebben, zijn ze niet hetzelfde. De machtigingen die ze verlenen en de leden van de rollengroepen zijn verschillend. Hieronder vindt u een lijst met & beveiligingsgroepen voor compliancecentrum.

![Pagina Machtigingen in het beveiligings- & compliancecentrum](../../media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)

## <a name="relationship-of-members-roles-and-role-groups"></a>Relatie van leden, rollen en rollengroepen

Een **rol** verleent machtigingen voor het uitvoeren van een reeks taken; Met de rol Case Management kunnen mensen bijvoorbeeld werken met eDiscovery-zaken.

Een **rollengroep** is een set rollen waarmee personen hun werk kunnen doen in het & compliancecentrum. De rollengroep Compliancebeheerder bevat bijvoorbeeld (onder andere) de rollen voor Case Management, Content Search en Organization Configuration (plus andere rollen), omdat iemand die een compliancebeheerder is, de machtigingen voor die taken nodig heeft om zijn of haar taak uit te voeren.

Het beveiligings & compliancecentrum bevat standaardrolgroepen voor de meest voorkomende taken en functies die u moet toewijzen aan personen. Het is raadzaam om alleen individuele gebruikers als leden **toe te voegen** aan de standaardrolgroepen.

![Diagram waarin de relatie van rollengroepen met rollen en leden wordt weergegeven](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-security--compliance-center"></a>Machtigingen die nodig zijn voor het gebruik van functies in het & Compliancecentrum

De volgende tabel bevat de standaardrolgroepen die beschikbaar zijn in het beveiligings- & compliancecentrum en de rollen die standaard aan de rollengroepen zijn toegewezen. Als u een gebruiker machtigingen wilt verlenen om een nalevingstaak uit te voeren, voegt u deze toe aan de juiste rollengroep & beveiligings- en compliancecentrum.

Het beheer van machtigingen in het & compliancecentrum geeft gebruikers alleen toegang tot de nalevingsfuncties die beschikbaar zijn in het beveiligings- & compliancecentrum zelf. Als u machtigingen wilt verlenen aan andere nalevingsfuncties die niet in het beveiligings- & Compliancecentrum staan, zoals Exchange-regels voor de e-mailstroom (ook wel transportregels genoemd), moet u het Exchange-beheercentrum gebruiken.

Als u wilt zien hoe u toegang verleent tot het & compliancecentrum, raadpleegt u Gebruikers toegang geven tot het [Microsoft 365-compliancebeheerderscentrum.](grant-access-to-the-security-and-compliance-center.md)

> [!NOTE]
> Als u het **tabblad Machtigingen** wilt weergeven in het & compliancecentrum, moet u een beheerder zijn. U moet de rol Rollenbeheer toegewezen krijgen en deze rol is  standaard alleen toegewezen aan de rollengroep Organisatiebeheer in het beveiligings- & compliancecentrum.  Daarnaast kunnen gebruikers **met de rol** Rolbeheer rollengroepen weergeven, maken en wijzigen.

<br><br>

****

|Rollengroep|Beschrijving|Standaardrollen toegewezen|
|---|---|---|
|**Communicatie compliance**|Verleent machtigingen aan alle communicatie compliancerollen: beheerder, analist, aandurf en viewer.|Case Management <p> Beheerder voor communicatie compliance <p> Communicatie compliance-analyse <p> Communication Compliance Case Management <p> Onderzoek naar communicatie compliance <p> Viewer voor communicatie compliance <p> Gegevensclassificatiefeedbackprovider <p> View-Only|
|**Beheerders voor communicatie compliance**|Beheerders van communicatie compliance die beleidsregels kunnen maken/bewerken en globale instellingen kunnen definiëren.|Beheerder voor communicatie compliance <p> Communication Compliance Case Management|
|**Communicatieve complianceanalisten**|Analisten van communicatie compliance die beleids matches kunnen onderzoeken, de metagegevens van berichten kunnen bekijken en herstelacties kunnen ondernemen.|Communicatie compliance-analyse <p> Communication Compliance Case Management|
|**Communicatie compliance-normen**|Analisten van communicatie compliance die beleidsvoorwaarden kunnen onderzoeken, berichtinhoud kunnen bekijken en herstelacties kunnen ondernemen.|Case Management <p> Communicatie compliance-analyse <p> Communication Compliance Case Management <p> Onderzoek naar communicatie compliance <p> Gegevensclassificatiefeedbackprovider <p> View-Only|
|**Viewers voor communicatie compliance**|Viewer voor communicatie compliance die toegang heeft tot de beschikbare rapporten en widgets.|Communication Compliance Case Management <p> Viewer voor communicatie compliance|
|**Compliancebeheerder**<sup>1</sup>|Leden kunnen instellingen beheren voor apparaatbeheer, preventie van gegevensverlies, rapporten en behoud.|Case Management <p> Compliancebeheerder <p> Compliance Search <p> Gegevensclassificatiefeedbackprovider <p> Feedback revisor voor gegevensclassificatie <p> Apparaatbeheer <p> Beheer van positie <p> DLP-compliancebeheer <p> Wacht zetten <p> IB-compliancebeheer <p> Waarschuwingen beheren <p> Organisatieconfiguratie <p> RecordManagement <p> Bewaarbeheer <p> View-Only auditlogboeken maken <p> View-Only <p> View-Only Apparaatbeheer <p> View-Only DLP-compliancebeheer <p> View-Only IB-compliancebeheer <p> View-Only waarschuwingen beheren <p> View-Only geadresseerden <p> View-Only recordbeheer <p> View-Only bewaarbeheer|
|**Beheerder van nalevingsgegevens**|Leden kunnen instellingen beheren voor apparaatbeheer, gegevensbescherming, preventie van gegevensverlies, rapporten en behoud.|Compliancebeheerder <p> Compliance Search <p> Apparaatbeheer <p> DLP-compliancebeheer <p> Beheer van positie <p> IB-compliancebeheer <p> Waarschuwingen beheren <p> Organisatieconfiguratie <p> RecordManagement <p> Bewaarbeheer <p> Beheerder van gevoeligheidslabel <p> View-Only auditlogboeken maken <p> View-Only Apparaatbeheer <p> View-Only DLP-compliancebeheer <p> View-Only IB-compliancebeheer <p> View-Only waarschuwingen beheren <p> View-Only geadresseerden <p> View-Only recordbeheer <p> View-Only bewaarbeheer|
|**Beheerders van Compliancebeheer**|Het maken en wijzigen van sjablonen beheren.|Beheer van Compliancebeheer <p> Beoordeling compliancebeheer <p> Bijdrage van Compliancemanager <p> Lezer voor Compliancebeheer|
|**Assessors voor Compliancebeheer**|Beoordelingen maken, acties ter verbetering implementeren en de teststatus voor acties ter verbetering bijwerken.|Beoordeling compliancebeheer <p> Bijdrage van Compliancemanager <p> Lezer voor Compliancebeheer|
|**Medewerkers compliancebeheer**|Beoordelingen maken en werkzaamheden uitvoeren om acties voor verbetering te implementeren.|Bijdrage van Compliancemanager <p> Lezer voor Compliancebeheer|
|**Lezers van Compliancebeheer**|Alle inhoud van Compliancebeheer weergeven, met uitzondering van beheerdersfuncties.|Lezer voor Compliancebeheer|
|**Inhoudsverkenner voor inhoudsviewer**|Bekijk de inhoudsbestanden in Inhoudsverkenner.|Gegevensclassificatie-inhoudsviewer|
|**Lijstviewer voor Inhoudsverkenner**|Alle items in Inhoudsverkenner alleen weergeven in lijstindeling.|Viewer voor gegevensclassificatielijst|
|**eDiscovery-beheerder**|Leden kunnen zoeken en in postvakken, SharePoint Online-sites en OneDrive voor Bedrijven-locaties plaatsen. Leden kunnen ook eDiscovery-zaken maken en beheren, leden toevoegen aan en verwijderen uit een zaak, inhoudszoek zoekopdrachten maken en bewerken die zijn gekoppeld aan een zaak, en toegang krijgen tot zaakgegevens in Advanced eDiscovery. <p> Een eDiscovery-beheerder is lid van de rollengroep van eDiscovery Manager aan wie aanvullende machtigingen zijn toegewezen. Naast de taken die een eDiscovery-beheerder kan uitvoeren, kan een eDiscovery-beheerder het volgende doen:<ul><li>Bekijk alle eDiscovery-zaken in de organisatie.</li><li>Beheer een eDiscovery-zaak nadat ze zichzelf hebben toevoegd als lid van de zaak.</li></ul> <p> Het belangrijkste verschil tussen een eDiscovery-beheerder en een eDiscovery-beheerder is dat een eDiscovery-beheerder toegang heeft tot alle zaken die worden vermeld op de **pagina met eDiscovery-zaken** in het beveiligings- & compliancecentrum. Een eDiscovery-manager heeft alleen toegang tot de zaken die hij heeft gemaakt of zaken waar hij lid van is. Zie eDiscovery-machtigingen toewijzen in het beveiligings- & compliancecentrum voor meer informatie over het maken van een gebruiker [als eDiscovery-beheerder.](../../compliance/assign-ediscovery-permissions.md)|Case Management <p> Communicatie <p> Compliance Search <p> Uit den 2010 <p> Exporteren <p> Wacht zetten <p> Voorbeeld <p> Controleren <p> RMS Ontsleutelen|
|**Globale lezer**|Leden hebben alleen-lezen toegang tot rapporten en waarschuwingen en kunnen alle configuratie en instellingen zien.<p> Het belangrijkste verschil tussen een globale lezer en een beveiligingslezer is dat een globale lezer toegang heeft tot **configuratie en instellingen.**|Beveiligingslezer <p> Gevoeligheidslabellezer <p> Weergave Servicecontrole <p> View-Only auditlogboeken maken <p> View-Only Apparaatbeheer <p> View-Only DLP-compliancebeheer <p> View-Only IB-compliancebeheer <p> View-Only waarschuwingen beheren <p> View-Only geadresseerden <p> View-Only recordbeheer <p> View-Only bewaarbeheer|
|**Insider-risicobeheer**|Gebruik deze rollengroep om insider-risicobeheer voor uw organisatie in één groep te beheren. Door alle gebruikersaccounts toe te voegen voor aangewezen beheerders, analisten en delen, kunt u machtigingen voor insider-risicobeheer configureren in één groep. Deze rollengroep bevat alle machtigingen voor insider-risicobeheer. Dit is de eenvoudigste manier om snel aan de slag te gaan met insider-risicobeheer en is geschikt voor organisaties die geen afzonderlijke machtigingen nodig hebben die zijn gedefinieerd voor afzonderlijke groepen gebruikers.|Case Management <p> Insider-beheerder risicobeheer <p> Insider-analyse van risicobeheer <p> Onderzoek naar Insider-risicobeheer <p> View-Only|
|**Insider-beheerders voor risicobeheer**|Gebruik deze rollengroep om in eerste instantie insider-risicobeheer te configureren en later om beheerders van insider-risico's te scheiden in een gedefinieerde groep. Gebruikers in deze rollengroep kunnen beleidsregels voor insider-risicobeheer, globale instellingen en rolgroeptoewijzingen maken, lezen, bijwerken en verwijderen.|Case Management <p> Insider-beheerder risicobeheer <p> View-Only|
|**Analist intern risicobeheer**|Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die fungeren als insider-risicoanalyseanalisten. Gebruikers in deze rollengroep hebben toegang tot alle sjablonen voor insider-risicobeheer, zaken en aankondigingen. Ze hebben geen toegang tot Inhoudsverkenner voor insider-risico's.|Case Management <p> Insider-analyse van risicobeheer <p> View-Only|
|**Insider Risk Management Auditors**|Auditors van insider-risicobeheer die de auditlogboeken kunnen bekijken van acties die zijn uitgevoerd door analisten, aandelen en beheerders.|Insider-risicobeheercontrole|
|**Onderzoeker intern risicobeheer**|Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die fungeren als insider-risicogegevens. Gebruikers in deze rollengroep hebben voor alle gevallen toegang tot alle waarschuwingen voor insider-risicobeheer, zaken, sjablonen voor meldingen en de Inhoudsverkenner.|Case Management <p> Onderzoek naar Insider-risicobeheer <p> View-Only|
|**IRM-medewerkers**|Deze rollengroep is zichtbaar, maar wordt alleen gebruikt door achtergrondservices.|Permanente bijdrage van Insider-risicobeheer <p> Tijdelijke bijdrage van Insider-risicobeheer|
|**MailFlow-beheerder**|Leden kunnen inzichten in e-mailstromen en rapporten controleren en bekijken in het & compliancecentrum. Globale beheerders kunnen gewone gebruikers aan deze groep toevoegen, maar als de gebruiker geen lid is van de Exchange-beheerdersgroep, heeft de gebruiker geen toegang tot beheertaken in verband met Exchange.|View-Only geadresseerden|
|**Organisatiebeheer**<sup>1</sup>|Leden kunnen machtigingen beheren voor toegang tot functies in het beveiligings- & compliancecentrum en kunnen ook instellingen beheren voor apparaatbeheer, preventie van gegevensverlies, rapporten en behoud. <p> Gebruikers die geen globale beheerder zijn, moeten Exchange-beheerders zijn om apparaten te zien en actie te ondernemen die worden beheerd door Basic Mobility and Security voor Microsoft 365 (voorheen Mobile Device Management of MDM genoemd). <p> Globale beheerders worden automatisch toegevoegd als leden van deze rollengroep.|Auditlogboeken <p> Case Management <p> Compliancebeheerder <p> Compliance Search <p> Apparaatbeheer <p> DLP-compliancebeheer <p> Wacht zetten <p> IB-compliancebeheer <p> Waarschuwingen beheren <p> Organisatieconfiguratie <p> Quarantaine <p> RecordManagement <p> Bewaarbeheer <p> Rollenbeheer <p> Zoeken en purge <p> Beveiligingsbeheerder <p> Beveiligingslezer <p> Beheerder van gevoeligheidslabel <p> Gevoeligheidslabellezer <p> Weergave Servicecontrole <p> Inzender voor tags <p> Labelbeheer <p> Labellezer <p> View-Only auditlogboeken maken <p> View-Only Apparaatbeheer <p> View-Only DLP-compliancebeheer <p> View-Only IB-compliancebeheer <p> View-Only <p> View-Only waarschuwingen beheren <p> View-Only geadresseerden <p> View-Only recordbeheer <p> View-Only bewaarbeheer|
|**Quarantainebeheerder**|Leden hebben toegang tot alle quarantaineacties. Zie Berichten en bestanden in quarantaine beheren [als beheerder in EOP](manage-quarantined-messages-and-files.md) voor meer informatie|Quarantaine|
|**Recordbeheer**|Leden kunnen alle aspecten van recordbeheer configureren, inclusief labels voor bewaren en beoordeling van het beheer van het beheer.|Beheer van positie <p> RecordManagement <p> Bewaarbeheer|
|**Revisor**|Leden hebben toegang tot controlesets in [Advanced eDiscovery-zaken.](../../compliance/overview-ediscovery-20.md) Leden van deze rollengroep kunnen de lijst met zaken bekijken en openen op de **pagina eDiscovery > Advanced** in het Microsoft 365-compliancecentrum waar ze lid van zijn. Nadat de gebruiker een Advanced eDiscovery-zaak heeft gebruikt, kan deze **Sets** controleren selecteren om toegang te krijgen tot de zaakgegevens. Met deze rol kan de gebruiker geen voorbeeld bekijken van de resultaten van een verzamelingszoekactie die is gekoppeld aan de zaak of andere zoek- of casemanagementtaken uitvoeren. Leden van deze rollengroep hebben alleen toegang tot de gegevens in een revisieset.|Controleren|
|**Beveiligingsbeheerder**|Leden hebben toegang tot een aantal beveiligingsfuncties van het Identity Protection Center, Privileged Identity Management, Service Health controleren van Microsoft 365 en & Compliancecentrum. <p> Het is standaard mogelijk dat deze rollengroep geen leden heeft. De rol Beveiligingsbeheerder uit Azure Active Directory is echter toegewezen aan deze rollengroep. Deze rollengroep neemt daarom de mogelijkheden en het lidmaatschap van de rol Beveiligingsbeheerder over van Azure Active Directory. <p> Als u machtigingen centraal wilt beheren, kunt u groepsleden toevoegen en verwijderen in het Azure Active Directory-beheercentrum. Zie Beheerdersrolmachtigingen [in Azure Active Directory voor meer informatie.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Als u deze rollengroep bewerkt in het & Compliancecentrum voor beveiliging (lidmaatschap of rollen), zijn deze wijzigingen alleen van toepassing op het beveiligings- & compliancecentrum en niet op andere services. <p> Deze rollengroep bevat alle alleen-lezenmachtigingen van de rol Beveiligingslezer, plus een aantal extra beheerdersmachtigingen voor dezelfde services: Azure Information Protection, Identity Protection Center, Privileged Identity Management, Microsoft 365 Service Health bewaken en Beveiligings & Compliancecentrum.|Auditlogboeken <p> Apparaatbeheer <p> DLP-compliancebeheer <p> IB-compliancebeheer <p> Waarschuwingen beheren <p> Quarantaine <p> Beveiligingsbeheerder <p> Beheerder van gevoeligheidslabel <p> Inzender voor tags <p> Labelbeheer <p> Labellezer <p> View-Only auditlogboeken maken <p> View-Only Apparaatbeheer <p> View-Only DLP-compliancebeheer <p> View-Only IB-compliancebeheer <p> View-Only waarschuwingen beheren|
|**Beveiligingsoperator**|Leden kunnen beveiligingswaarschuwingen beheren en ook rapporten en instellingen van beveiligingsfuncties bekijken.|Compliance Search <p> Waarschuwingen beheren <p> Beveiligingslezer <p> Inzender voor tags <p> Labellezer <p> View-Only auditlogboeken maken <p> View-Only Apparaatbeheer <p> View-Only DLP-compliancebeheer <p> View-Only IB-compliancebeheer <p> View-Only waarschuwingen beheren|
|**Beveiligingslezer**|Leden hebben alleen-lezen toegang tot een aantal beveiligingsfuncties van het Identity Protection Center, Privileged Identity Management, Service Health controleren van Microsoft 365 en & Compliancecentrum. <p> Het is standaard mogelijk dat deze rollengroep geen leden heeft. De rol Beveiligingslezer uit Azure Active Directory is echter toegewezen aan deze rollengroep. Daarom neemt deze rollengroep de mogelijkheden en het lidmaatschap van de rol Beveiligingslezer over van Azure Active Directory. <p> Als u machtigingen centraal wilt beheren, kunt u groepsleden toevoegen en verwijderen in het Azure Active Directory-beheercentrum. Zie Beheerdersrolmachtigingen [in Azure Active Directory voor meer informatie.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Als u deze rollengroep bewerkt in het & Compliancecentrum voor beveiliging (lidmaatschap of rollen), zijn deze wijzigingen alleen van toepassing op het beveiligings- & compliancecentrum en niet op andere services.|Beveiligingslezer <p> Gevoeligheidslabellezer <p> Labellezer <p> View-Only Apparaatbeheer <p> View-Only DLP-compliancebeheer <p> View-Only IB-compliancebeheer <p> View-Only waarschuwingen beheren|
|**Gebruiker van Servicecontrole**|Leden hebben toegang tot de sectie Servicecontrole in het & compliancecentrum. Servicecontrole biedt rapporten en documenten waarin de beveiligingsprocedures van Microsoft voor klantgegevens worden beschreven die zijn opgeslagen in Microsoft 365. Daarnaast worden er onafhankelijke auditrapporten van derden over Microsoft 365 verstrekt. Zie Servicecontrole in het beveiligings- en & [voor meer informatie.](../../compliance/service-assurance.md)|Weergave Servicecontrole|
|**Beoordeling door supervisor**|Leden kunnen het beleid maken en beheren waarmee wordt bepaald welke communicatie in een organisatie moet worden beoordeeld. Zie Communicatie compliancebeleid [configureren voor uw organisatie voor meer informatie.](../../compliance/communication-compliance-configure.md)|Beheerder van beoordeling door supervisor|
|

> [!NOTE]
> <sup>1</sup> Aan deze rollengroep worden geen leden de machtigingen toegewezen die nodig zijn om het auditlogboek te doorzoeken of om rapporten te gebruiken die Exchange-gegevens kunnen bevatten, zoals de DLP- of Defender voor Office 365-rapporten. Als u in het auditlogboek wilt zoeken of alle rapporten wilt weergeven, moet aan een gebruiker machtigingen zijn toegewezen in Exchange Online. Dit komt omdat de onderliggende cmdlet die wordt gebruikt voor het doorzoeken van het auditlogboek een Exchange Online-cmdlet is. Globale beheerders kunnen zoeken in het auditlogboek en alle rapporten weergeven omdat ze automatisch worden toegevoegd als leden van de rollengroep Organisatiebeheer in Exchange Online. Zie Zoeken in het [auditlogboek in het](../../compliance/search-the-audit-log-in-security-and-compliance.md)& compliancecentrum voor meer informatie.

## <a name="roles-in-the-security--compliance-center"></a>Rollen in het beveiligings- & compliancecentrum

De volgende tabel bevat de beschikbare rollen en de rollengroepen aan welke rollen standaard zijn toegewezen.

Houd er rekening mee dat de volgende rollen niet standaard zijn toegewezen aan de rollengroep Organisatiebeheer:

- Attack Simulator Admin
- Auteur van attack Simulator Payload
- Communicatie
- Beheerder voor communicatie compliance
- Communicatie compliance-analyse
- Communication Compliance Case Management
- Onderzoek naar communicatie compliance
- Viewer voor communicatie compliance
- Beheer van Compliancebeheer
- Beoordeling compliancebeheer
- Bijdrage van Compliancemanager
- Lezer voor Compliancebeheer
- Uit den 2010
- Gegevensclassificatie-inhoudsviewer
- Gegevensclassificatiefeedbackprovider
- Feedback revisor voor gegevensclassificatie
- Viewer voor gegevensclassificatielijst
- Beheer van positie
- Exporteren
- Insider-beheerder risicobeheer
- Insider-analyse van risicobeheer
- Insider-risicobeheercontrole
- Onderzoek naar Insider-risicobeheer
- Permanente bijdrage van Insider-risicobeheer
- Tijdelijke bijdrage van Insider-risicobeheer
- Voorbeeld
- Controleren
- RMS Ontsleutelen
- Beheerder van beoordeling door supervisor

<br><br>

****

|Rol|Beschrijving|Standaardtoewijzingen voor rollengroep|
|---|---|---|
|**Attack Simulator Admin**|Wordt gebruikt voor het maken en beheren van alle aspecten van campagnes voor aanvalscampagnes voor aanvallen.||
|**Auteur van attack Simulator Payload**|Wordt gebruikt om nettolading voor aanvallen te maken en te beheren die kunnen worden geïmplementeerd door de beheerder van de aanvalsbeheerders.||
|**Auditlogboeken**|Schakel de controle voor de organisatie in en configureer deze, bekijk de controlerapporten van de organisatie en exporteert deze rapporten naar een bestand.|Organisatiebeheer <p> Beveiligingsbeheerder|
|**Case Management**|Maak, bewerk, verwijder en beheer de toegang tot eDiscovery-zaken.|Communicatiecompliance <p> Communicatie compliance-normen <p> Compliancebeheerder <p>eDiscovery-beheerder <p> Intern risicobeheer <p> Insider-beheerders voor risicobeheer <p> Analist intern risicobeheer <p> Onderzoeker intern risicobeheer <p> Organisatiebeheer|
|**Communicatie**|Beheer alle communicatie met de beheerders die zijn geïdentificeerd in een Advanced eDiscovery-zaak.  Maak meldingen voor in de wacht zetten, houd herinneringen in de wacht en escalatie naar het beheer. Houd meebevestiging van wachtberichten bij en beheer de toegang tot de beheerportal die door elke beheerder in een zaak wordt gebruikt om de communicatie bij te houden voor de gevallen waarin ze zijn geïdentificeerd als een beheerder.|eDiscovery-beheerder|
|**Beheerder voor communicatie compliance**|Wordt gebruikt voor het beheren van beleid in de functie Communicatie compliance.|Communicatiecompliance <p> Beheerders voor communicatie compliance|
|**Communicatie compliance-analyse**|Wordt gebruikt voor het uitvoeren van onderzoek en herstel van de berichtovertredingen in de functie Communicatie compliance. Kan alleen metagegevens van berichten weergeven.|Communicatiecompliance <p> Communicatieve complianceanalisten <p> Communicatie compliance-normen|
|**Communication Compliance Case Management**|Wordt gebruikt voor toegang tot communicatie compliance-zaken.|Communicatiecompliance <p> Beheerders voor communicatie compliance <p> Communicatieve complianceanalisten <p> Communicatie compliance-normen <p> Viewers voor communicatie compliance|
|**Onderzoek naar communicatie compliance**|Wordt gebruikt voor het uitvoeren van onderzoek, herstellen en controleren van berichtovertredingen in de functie Communicatie compliance. Kan metagegevens en berichten van berichten weergeven.|Communicatiecompliance <p> Communicatie compliance-normen|
|**Viewer voor communicatie compliance**|Wordt gebruikt voor toegang tot rapporten en widgets in de functie Communicatie compliance.|Communicatiecompliance <p> Viewers voor communicatie compliance|
|**Compliancebeheerder**|Bekijk en bewerk instellingen en rapporten voor nalevingsfuncties.|Compliancebeheerder <p> Beheerder van nalevingsgegevens <p> Organisatiebeheer|
|**Beheer van Compliancebeheer**|Het maken en wijzigen van sjablonen beheren.|Beheerders van Compliancebeheer|
|**Beoordeling compliancebeheer**|Beoordelingen maken, acties ter verbetering implementeren en de teststatus voor acties ter verbetering bijwerken.|Beheerders van Compliancebeheer <p> Assessors voor Compliancebeheer|
|**Bijdrage van Compliancemanager**|Beoordelingen maken en werkzaamheden uitvoeren om acties voor verbetering te implementeren.|Beheerders van Compliancebeheer <p> Assessors voor Compliancebeheer <p> Medewerkers compliancebeheer|
|**Lezer voor Compliancebeheer**|Alle inhoud van Compliancebeheer weergeven, met uitzondering van beheerdersfuncties.|Beheerders van Compliancebeheer <p> Assessors voor Compliancebeheer <p> Medewerkers compliancebeheer <p> Lezers van Compliancebeheer|
|**Compliance Search**|Zoek in postvakken en krijg een schatting van de resultaten.|Compliancebeheerder <p> Beheerder van nalevingsgegevens <p>eDiscovery-beheerder <p> Organisatiebeheer <p> Beveiligingsoperator|
|**Uit den 2010**|Identificeer en beheer beheerders voor Advanced eDiscovery-zaken en gebruik de informatie uit Azure Active Directory en andere bronnen om gegevensbronnen te vinden die zijn gekoppeld aan beheerders. Koppel andere gegevensbronnen, zoals postvakken, SharePoint-sites en Teams, aan beheerders in een zaak.  Houd de gegevensbronnen die zijn gekoppeld aan beheerders wettelijk in de wacht om inhoud in de context van een zaak te behouden.|eDiscovery-beheerder|
|**Gegevensclassificatie-inhoudsviewer**|Weergave in-place weergave van bestanden in Inhoudsverkenner.|Inhoudsverkenner voor inhoudsviewer|
|**Gegevensclassificatiefeedbackprovider**|Hiermee kunt u feedback geven aan classificaties in Inhoudsverkenner.|Communicatiecompliance <p> Communicatie compliance-normen <p> Compliancebeheerder|
|**Feedback revisor voor gegevensclassificatie**|Hiermee kunt u feedback van classificaties in feedbackverkenner beoordelen.|Compliancebeheerder|
|**Viewer voor gegevensclassificatielijst**|Bekijk de lijst met bestanden in Inhoudsverkenner.|Lijstviewer voor Inhoudsverkenner|
|**Apparaatbeheer**|Bekijk en bewerk instellingen en rapporten voor apparaatbeheerfuncties.|Compliancebeheerder <p> Beheerder van nalevingsgegevens <p> Organisatiebeheer <p> Beveiligingsbeheerder|
|**Beheer van positie**|Beheermachtigingen voor toegang tot Handmatige disposition in het & compliancecentrum.|Compliancebeheerder <p> Beheerder van nalevingsgegevens <p> Recordbeheer|
|**DLP-compliancebeheer**|Bekijk en bewerk instellingen en rapporten voor beleidsregels voor preventie van gegevensverlies (DLP).|Compliancebeheerder <p> Beheerder van nalevingsgegevens <p> Organisatiebeheer <p> Beveiligingsbeheerder|
|**Exporteren**|Postvak en site-inhoud exporteren die wordt geretourneerd uit zoekopdrachten.|eDiscovery-beheerder|
|**Wacht zetten**|Inhoud in postvakken, sites en openbare mappen in de wacht zetten. Wanneer de inhoud in de wacht staat, wordt deze op een veilige locatie opgeslagen. Eigenaren van inhoud kunnen de oorspronkelijke inhoud nog wel wijzigen of verwijderen.|Compliancebeheerder <p>eDiscovery-beheerder <p> Organisatiebeheer|
|**IB-compliancebeheer**|Beleidsregels voor informatiebarrière bekijken, maken, verwijderen, wijzigen en testen.|Compliancebeheerder <p> Beheerder van nalevingsgegevens <p> Organisatiebeheer <p> Beveiligingsbeheerder|
|**Insider-beheerder risicobeheer**|Toegang tot de functie Risicobeheer voor Insider maken, bewerken, verwijderen en beheren.|Intern risicobeheer <p> Insider-beheerders voor risicobeheer|
|**Insider-analyse van risicobeheer**|Krijg toegang tot alle sjablonen voor insider-risicobeheer, -zaken en -aankondigingen.|Intern risicobeheer <p> Analist intern risicobeheer|
|**Insider-risicobeheercontrole**|Toestaan dat audittrails voor Insider-risico's worden bekeken.|Insider Risk Management Auditors|
|**Onderzoek naar Insider-risicobeheer**|Krijg toegang tot alle waarschuwingen voor insider-risicobeheer, zaken, sjablonen voor meldingen en de Inhoudsverkenner voor alle gevallen.|Intern risicobeheer <p> Onderzoeker intern risicobeheer|
|**Permanente bijdrage van Insider-risicobeheer**|Deze rollengroep is zichtbaar, maar wordt alleen gebruikt door achtergrondservices.|IRM-medewerkers|
|**Tijdelijke bijdrage van Insider-risicobeheer**|Deze rollengroep is zichtbaar, maar wordt alleen gebruikt door achtergrondservices.|IRM-medewerkers|
|**Waarschuwingen beheren**|Instellingen en rapporten voor waarschuwingen weergeven en bewerken.|Compliancebeheerder <p> Beheerder van nalevingsgegevens <p> Organisatiebeheer <p> Beveiligingsbeheerder <p> Beveiligingsoperator|
|**Organisatieconfiguratie**|Controlerapporten uitvoeren, weergeven en exporteren en nalevingsbeleid voor DLP, apparaten en behoud beheren.|Compliancebeheerder <p> Beheerder van nalevingsgegevens <p> Organisatiebeheer|
|**Voorbeeld**|Bekijk een lijst met items die worden geretourneerd uit inhoudszoek zoekopdrachten en open elk item in de lijst om de inhoud ervan weer te geven.|eDiscovery-beheerder|
|**Quarantaine**|Hiermee kunt u in quarantaine geplaatste e-mail weergeven en vrijgeven.|Quarantainebeheerder <p> Beveiligingsbeheerder <p> Organisatiebeheer|
|**RecordManagement**|Bekijk en bewerk de configuratie van de functie recordbeheer.|Compliancebeheerder <p> Beheerder van nalevingsgegevens <p> Organisatiebeheer <p> Recordbeheer|
|**Bewaarbeheer**|Bewaarbeleid, bewaarlabels en bewaarlabelbeleid beheren.|Compliancebeheerder <p> Beheerder van nalevingsgegevens <p> Organisatiebeheer <p> Recordbeheer|
|**Controleren**|Met deze rol hebben gebruikers toegang tot sets in Advanced eDiscovery-zaken. Gebruikers aan wie deze rol is toegewezen, kunnen de lijst met zaken zien en openen op de pagina **eDiscovery > Advanced** in het Microsoft 365-compliancecentrum waar ze lid van zijn. Nadat de gebruiker een Advanced eDiscovery-zaak heeft gebruikt, kan deze **Sets** controleren selecteren om toegang te krijgen tot de zaakgegevens. Met deze rol kan de gebruiker geen voorbeeld bekijken van de resultaten van een verzamelingszoekactie die is gekoppeld aan de zaak of andere zoek- of casemanagementtaken uitvoeren. Gebruikers met deze rol hebben alleen toegang tot de gegevens in een revisieset.|eDiscovery-beheerder <p> Revisor|
|**RMS Ontsleutelen**|Met RMS beveiligde inhoud ontsleutelen bij het exporteren van zoekresultaten.|eDiscovery-beheerder|
|**Rollenbeheer**|Beheer lidmaatschap van rollengroepen en maak of verwijder aangepaste rollengroepen.|Organisatiebeheer|
|**Zoeken en purge**|Hiermee kunnen personen gegevens die voldoen aan de criteria van een inhoudszoekactie bulksgewijs verwijderen.|Organisatiebeheer|
|**Beveiligingsbeheerder**|Bekijk en bewerk de configuratie en rapporten voor beveiligingsfuncties.|Organisatiebeheer <p> Beveiligingsbeheerder|
|**Beveiligingslezer**|Bekijk de configuratie en rapporten voor beveiligingsfuncties.|Algemene lezer <p> Organisatiebeheer <p> Beveiligingsoperator <p> Beveiligingslezer|
|**Beheerder van gevoeligheidslabel**|Gevoeligheidslabels weergeven, maken, wijzigen en verwijderen.|Beheerder van nalevingsgegevens <p> Organisatiebeheer <p> Beveiligingsbeheerder|
|**Gevoeligheidslabellezer**|Bekijk de configuratie en het gebruik van gevoeligheidslabels.|Algemene lezer <p> Organisatiebeheer <p> Beveiligingslezer|
|**Weergave Servicecontrole**|Download de beschikbare documenten in de sectie Servicecontrole. Inhoud bevat onafhankelijke controle, documentatie over naleving en vertrouwensgerelateerde richtlijnen voor het gebruik van Microsoft 365-functies voor het beheren van regelgeving en beveiligingsrisico's.|Algemene lezer <p> Organisatiebeheer <p> Gebruiker van Servicecontrole|
|**Beheerder van beoordeling door supervisor**|Beheer beleidsregels voor beoordeling door supervisors, inclusief de communicatie die moet worden beoordeeld en wie de beoordeling moet doen.|Beoordeling door supervisor|
|**Inzender voor tags**|Bekijk en werk het lidmaatschap van bestaande gebruikerslabels bij.|Organisatiebeheer <p> Beveiligingsbeheerder <p> Beveiligingsoperator|
|**Labelbeheer**|Gebruikerstags weergeven, bijwerken, maken en verwijderen.|Organisatiebeheer <p> Beveiligingsbeheerder|
|**Labellezer**|Alleen-lezen toegang tot bestaande gebruikerslabels.|Beveiligingslezer|
|**Auditlogboeken voor alleen-weergeven**|Controlerapporten weergeven en exporteren. Omdat deze rapporten gevoelige informatie kunnen bevatten, moet u deze rol alleen toewijzen aan personen die deze informatie expliciet moeten bekijken.|Compliancebeheerder <p> Beheerder van nalevingsgegevens <p> Algemene lezer <p> Organisatiebeheer <p> Beveiligingsbeheerder <p> Beveiligingsoperator|
|**Alleen-weergeven**||Communicatiecompliance <p> Communicatie compliance-normen <p> Compliancebeheerder <p> Intern risicobeheer <p> Insider-beheerders voor risicobeheer <p> Analist intern risicobeheer <p> Insider RiskManagement-10-1-2 <p> Organisatiebeheer|
|**View-Only Device Management**|Bekijk de configuratie en rapporten voor de functie Apparaatbeheer.|Compliancebeheerder <p> Beheerder van nalevingsgegevens <p> Algemene lezer <p> Organisatiebeheer <p> Beveiligingsbeheerder <p> Beveiligingsoperator <p> Beveiligingslezer|
|**View-Only DLP-compliancebeheer**|Bekijk de instellingen en rapporten voor beleidsregels voor preventie van gegevensverlies (DLP).|Compliancebeheerder <p> Beheerder van nalevingsgegevens <p> Algemene lezer <p> Organisatiebeheer <p> Beveiligingsbeheerder <p> Beveiligingsoperator <p> Beveiligingslezer|
|**View-Only IB Compliance Management**|Bekijk de configuratie en rapporten voor de functie Informatiebarrières.|Compliancebeheerder <p> Beheerder van nalevingsgegevens <p> Algemene lezer <p> Organisatiebeheer <p> Beveiligingsbeheerder <p> Beveiligingsoperator <p> Beveiligingslezer|
|**Waarschuwingen beheren met alleen weergeven**|Bekijk de configuratie en rapporten voor de functie Waarschuwingen beheren.|Compliancebeheerder <p> Beheerder van nalevingsgegevens <p> Algemene lezer <p> Organisatiebeheer <p> Beveiligingsbeheerder <p> Beveiligingsoperator <p> Beveiligingslezer|
|**Alleen-weergeven geadresseerden**|Informatie over gebruikers en groepen weergeven.|Compliancebeheerder <p> Beheerder van nalevingsgegevens <p> Algemene lezer <p> MailFlow-beheerder <p> Organisatiebeheer|
|**Recordbeheer voor alleen-weergeven**|Bekijk de configuratie van de functie voor recordbeheer.|Compliancebeheerder <p> Beheerder van nalevingsgegevens <p> <p> Algemene lezer <p> Organisatiebeheer|
|**View-Only Retention Management**|Bekijk de configuratie van bewaarbeleid, bewaarlabels en bewaarlabelbeleid.|Compliancebeheerder <p> Beheerder van nalevingsgegevens <p> Globale beheerder <p> Organisatiebeheer|
|
