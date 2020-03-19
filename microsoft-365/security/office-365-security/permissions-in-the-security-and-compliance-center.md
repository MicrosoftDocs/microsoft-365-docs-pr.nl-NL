---
title: Machtigingen in het Office 365 Security & Compliance Center
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
description: Beheerders kunnen meer informatie vinden over de machtigingen die beschikbaar zijn in het Office 365 Security & Compliance Center.
ms.openlocfilehash: e45a9b369e127ca29de23f308f2d28808571cc42
ms.sourcegitcommit: cc3b64a91e16ccdaa9c338b9a9056dbe3963ba9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/10/2020
ms.locfileid: "42806307"
---
# <a name="permissions-in-the-office-365-security--compliance-center"></a>Machtigingen in het Office 365 Security & Compliance Center

Met het Office 365 Security & Compliance Center u machtigingen verlenen aan mensen die nalevingstaken uitvoeren, zoals apparaatbeheer, preventie van gegevensverlies, eDiscovery, retentie enzovoort. Deze mensen kunnen alleen de taken uitvoeren waartoe u hen expliciet toegang geeft. Als u toegang wilt krijgen tot het Security & Compliance Center, moeten gebruikers een globale office 365-beheerder of lid zijn van een of meer rolgroepen van het Security & Compliance Center.

Machtigingen in het Security & Compliance Center zijn gebaseerd op het RBAC-machtigingenmodel (Role Based Access Control). Dit is hetzelfde machtigingsmodel dat door Exchange wordt gebruikt, dus als u bekend bent met Exchange, zal het verlenen van machtigingen in het Security & Compliance Center zeer vergelijkbaar zijn. Het is echter belangrijk om te onthouden dat Exchange-rolgroepen en beveiligings- &-nalevingscentrum-rolgroepen geen lidmaatschap of machtigingen delen. Hoewel beide een rolgroep organisatiebeheer hebben, zijn ze niet hetzelfde. De machtigingen die zij verlenen, en de leden van de rolgroepen, zijn verschillend. Hieronder vindt u een lijst met rolgroepen van het Security & Compliance Center.

![Pagina Machtigingen in het Office 365 Security & Compliance Center](../../media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)

## <a name="relationship-of-members-roles-and-role-groups"></a>Relatie van leden, rollen en rolgroepen

Een **rol** verleent machtigingen om een reeks taken uit te voeren; Met de rol Case Management kunnen mensen bijvoorbeeld werken met eDiscovery-aanvragen.

Een **rolgroep** is een reeks rollen waarmee mensen hun werk kunnen uitvoeren in het Security & Compliance Center; De rolgroep Compliance Administrator bevat bijvoorbeeld de rollen voor Case Management, Content Search en Organization Configuration (plus anderen), omdat iemand die een compliancebeheerder is, de machtigingen voor die taken nodig heeft om zijn werk te kunnen doen.

Het Security & Compliance Center bevat standaardrolgroepen voor de meest voorkomende taken en functies waaraan u mensen moet toewijzen. We raden u aan afzonderlijke gebruikers als **lid** gewoon toe te voegen aan de standaardrolgroepen.

![Diagram met relatie tussen rolgroepen en rollen en leden](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

U de bestaande rolgroepen bewerken of verwijderen, maar we raden dit niet aan. In plaats van een standaardrolgroep te bewerken, u deze kopiëren, wijzigen en vervolgens opslaan met een andere naam.

## <a name="permissions-needed-to-use-features-in-the-security--compliance-center"></a>Machtigingen die nodig zijn om functies te gebruiken in het Security & Compliance Center

In de volgende tabel worden de standaardrolgroepen weergegeven die beschikbaar zijn in het Security & Compliance Center en de rollen die standaard aan de rolgroepen zijn toegewezen. Als u machtigingen wilt verlenen aan een gebruiker om een nalevingstaak uit te voeren, voegt u deze toe aan de juiste rolgroep Security & Compliance Center.

Het beheren van machtigingen in het Security & Compliance Center geeft gebruikers alleen toegang tot de compliancefuncties die beschikbaar zijn in het Security & Compliance Center zelf. Als u machtigingen wilt verlenen voor andere nalevingsfuncties die niet in het Security & Compliance Center staan, zoals exchange-mailstroomregels (ook wel transportregels genoemd), moet u het Exchange-beheercentrum gebruiken.

Als u wilt zien hoe u toegang verlenen tot het Security & Compliance Center, raadpleegt u [Gebruikers toegang geven tot het Office 365 Compliance-beheercentrum](grant-access-to-the-security-and-compliance-center.md).

|**Rolgroep**|**Beschrijving**|**Standaardrollen toegewezen**|
|:-----|:-----|:-----|
|**Compliance-beheerder**<sup>1</sup>|Leden kunnen instellingen beheren voor apparaatbeheer, preventie van gegevensverlies, rapporten en bewaring.|Case Management <br/><br/> Compliance-beheerder <br/><br/> Zoeken naar naleving <br/><br/> DLP Compliance Management <br/><br/> Apparaatbeheer <br/><br/> Dispositiebeheer <br/><br/> Houden <br/><br/> IB Compliance Management <br/><br/> Waarschuwingen beheren <br/><br/> Organisatieconfiguratie <br/><br/> RecordManagement <br/><br/> Retentiebeheer <br/><br/> Controlelogboeken alleen-weergeven <br/><br/> Alleen-weergaveretentiebeheer <br/><br/> Alleen-View-Beheer van DLP-compliance <br/><br/> Apparaatbeheer alleen-weergave <br/><br/> Alleen IB-compliancebeheer voor weergave <br/><br/> Alleen-weergave waarschuwingen beheren <br/><br/> Ontvangers die alleen voor weergave zijn <br/><br/> Alleen-weergaverecordbeheer|
|**Beheerder van nalevingsgegevens**|Leden kunnen instellingen beheren voor apparaatbeheer, gegevensbescherming, preventie van gegevensverlies, rapporten en bewaring.|Compliance-beheerder <br/><br/> Zoeken naar naleving <br/><br/> DLP Compliance Management <br/><br/> Apparaatbeheer <br/><br/> Dispositiebeheer <br/><br/> IB Compliance Management <br/><br/> Waarschuwingen beheren <br/><br/> Organisatieconfiguratie <br/><br/> RecordManagement <br/><br/> Retentiebeheer <br/><br/> Beheerder van gevoeligheidslabel <br/><br/> Controlelogboeken alleen-weergeven <br/><br/> Alleen-View-Beheer van DLP-compliance <br/><br/> Apparaatbeheer alleen-weergave <br/><br/> Alleen IB-compliancebeheer voor weergave <br/><br/> Alleen-weergave waarschuwingen beheren <br/><br/> Ontvangers die alleen voor weergave zijn <br/><br/> Alleen-weergaverecordbeheer <br/><br/> Alleen-weergaveretentiebeheer|
|**Gegevensonderzoeker**|Leden kunnen zoekopdrachten uitvoeren in postvakken, SharePoint-sites en OneDrive-accounts.|Communicatie <br/><br/> Zoeken naar naleving <br/><br/> Voogd <br/><br/> Data Investigation Management <br/><br/> Exporteren<br/><br/> Voorbeeld <br/><br/> RMS decoderen <br/><br/> Review<br/><br/> Zoeken en wissen|
|**eDiscovery-beheer**|Leden kunnen zoekopdrachten en plaatsen uitvoeren op postvakken, SharePoint Online-sites en OneDrive voor Bedrijven-locaties. Leden kunnen ook eDiscovery-aanvragen maken en beheren, leden toevoegen aan een aanvraag, Inhoudszoekopdrachten maken en bewerken die aan een aanvraag zijn gekoppeld en toegang krijgen tot casegegevens in Office 365 Advanced eDiscovery. <br/><br/> Een eDiscovery-beheerder is lid van de rolgroep eDiscovery-beheer en heeft aanvullende machtigingen gekregen. Naast de taken die een eDiscovery Manager kan uitvoeren, kan een eDiscovery-beheerder: <br/>* Bekijk alle eDiscovery-aanvragen in de organisatie. <br/>* Beheer een eDiscovery-aanvraag nadat ze zichzelf toevoegen als lid van de zaak. <br/><br/> Het belangrijkste verschil tussen een eDiscovery-beheer en een eDiscovery-beheerder is dat een eDiscovery-beheerder toegang heeft tot alle aanvragen die worden vermeld op de pagina **eDiscovery-aanvragen** in het Security & Compliance Center. Een eDiscovery-manager heeft alleen toegang tot de aanvragen waarvan ze hebben gemaakt of hoe ze lid zijn. Zie [EDiscovery-machtigingen toewijzen in het Office 365 Security & Compliance Center](../../compliance/assign-ediscovery-permissions.md)voor meer informatie over het maken van een gebruiker een eDiscovery-beheerder.|Case Management <br/><br/> Communicatie <br/><br/> Zoeken naar naleving <br/><br/> Voogd <br/><br/> Exporteren <br/><br/> Houden <br/><br/> Voorbeeld <br/><br/> RMS decoderen <br/><br/> Review|
|**Globale lezer**|Leden hebben alleen-lezen toegang tot rapporten, waarschuwingen en kunnen alle configuratie en instellingen zien.<br/><br/> Het belangrijkste verschil tussen Global Reader en Security Reader is dat een Global Reader toegang heeft tot **configuratie en instellingen.**|Beveiligingslezer <br/><br/> Gevoeligheidlabellezer <br/><br/> Serviceassurance-weergave <br/><br/> Controlelogboeken alleen-weergeven <br/><br/> Alleen-View-Beheer van DLP-compliance <br/><br/> Apparaatbeheer alleen-weergave <br/><br/> Alleen IB-compliancebeheer voor weergave <br/><br/> Alleen-weergave waarschuwingen beheren <br/><br/> Ontvangers die alleen voor weergave zijn <br/><br/> Alleen-weergaverecordbeheer <br/><br/> Alleen-weergaveretentiebeheer|
|**MailFlow-beheerder**|Leden kunnen de inzichten en rapporten van de e-mailstroom in het Security & Compliance Center controleren en bekijken. Globale beheerders kunnen gewone gebruikers aan deze groep toevoegen, maar als de gebruiker geen lid is van de Exchange-beheergroep, heeft de gebruiker geen toegang tot exchange-beheergerelateerde taken.|Ontvangers die alleen voor weergave zijn|
|**Organisatiebeheer**<sup>1</sup>|Leden kunnen machtigingen beheren voor toegang tot functies in het Security & Compliance Center en ook instellingen beheren voor apparaatbeheer, preventie van gegevensverlies, rapporten en bewaring. <br/><br/> Houd er rekening mee dat de gebruiker die geen globale beheerder is, de lijst met apparaten die door MDM voor Office 365 worden beheerd en acties uitvoert op deze apparaten, zoals het terugtrekken van een apparaat van MDM voor Office 365, een Exchange-beheerder moet zijn. <br/><br/> Globale office 365-beheerders worden automatisch toegevoegd als lid van deze rolgroep.|Controlelogboeken <br/><br/> Case Management <br/><br/> Compliance-beheerder <br/><br/> Zoeken naar naleving <br/><br/> DLP Compliance Management <br/><br/> Apparaatbeheer <br/><br/> Dispositiebeheer <br/><br/> Houden <br/><br/> IB Compliance Management <br/><br/> Waarschuwingen beheren <br/><br/> Organisatieconfiguratie <br/><br/> Quarantaine <br/><br/> RecordManagement <br/><br/> Retentiebeheer <br/><br/> Rolbeheer <br/><br/> Zoeken en wissen <br/><br/> Beveiligingsbeheerder <br/><br/> Beveiligingslezer <br/><br/> Beheerder van gevoeligheidslabel <br/><br/> Gevoeligheidlabellezer <br/><br/> Serviceassurance-weergave <br/><br/> Controlelogboeken alleen-weergeven <br/><br/> Alleen-View-Beheer van DLP-compliance <br/><br/> Apparaatbeheer alleen-weergave <br/><br/> Alleen IB-compliancebeheer voor weergave <br/><br/> Alleen-weergave waarschuwingen beheren <br/><br/> Ontvangers die alleen voor weergave zijn <br/><br/> Alleen-weergaverecordbeheer <br/><br/> Alleen-weergaveretentiebeheer|
|**Quarantainebeheerder**|Leden hebben toegang tot alle quarantaineacties. Zie [Berichten en bestanden in quarantaine beheren als beheerder in Office 365](manage-quarantined-messages-and-files.md) voor meer informatie|Quarantaine|
|**Beheer van records**|Leden kunnen inhoud beheren en verwijderen.|Controlelogboeken <br/><br/> RecordManagement <br/><br/> Retentiebeheer|
|**Revisor**|Leden kunnen alleen de lijst met aanvragen bekijken op de pagina eDiscovery-aanvragen in het Security & Compliance Center. Ze kunnen een eDiscovery-aanvraag niet maken, openen of beheren. Het primaire doel van deze rolgroep is om leden in staat te stellen casegegevens te bekijken en te openen in [Advanced eDiscovery (klassiek)](../../compliance/office-365-advanced-ediscovery.md) (ook bekend als *Advanced eDiscovery v1).* <br/><br/> Deze rolgroep heeft de meest beperkende eDiscovery-gerelateerde machtigingen.<br/><br/>**Let op:** Op dit moment hebben gebruikers die lid zijn van de rolgroep Reviewer geen toegang tot gegevens in [Geavanceerde eDiscovery in Microsoft 365](../../compliance/overview-ediscovery-20.md) (ook bekend als *Advanced eDiscovery v2).* Als u leden wilt toevoegen aan een aanvraag in Advanced eDiscovery v2, zodat ze casegegevens kunnen bekijken, moet een gebruiker lid zijn van de rolgroep eDiscovery Manager.|Review|
|**Beveiligingsbeheerder**|Leden van deze rolgroep kunnen crossservicebeheerders zijn, evenals externe partnergroepen en Microsoft-ondersteuning. Standaard wordt deze groep mogelijk niet toegewezen aan rollen. Het is echter lid van de rol Beveiligingsbeheerders in Azure Active Directory en overneemt de mogelijkheden van die rol. Als u machtigingen centraal wilt beheren, voert u wijzigingen aan in deze rol in het Azure Active Directory-beheercentrum. Zie [Beheerdersrolmachtigingen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)voor meer informatie. <br/><br/> Als u deze rolgroep bewerkt in het Security & Compliance Center, zijn deze wijzigingen alleen van toepassing op het Security & Compliance Center en niet op andere services, terwijl wijzigingen in het Azure Active Directory-beheercentrum van invloed zijn op alle services. <br/><br/> Alle alleen-lezen machtigingen van de rol Beveiligingslezer, plus een aantal extra beheerdersmachtigingen voor dezelfde services: Azure Information Protection, Identity Protection Center, Privileged Identity Management, Monitor Office 365 Service Health en Office 365 Security & Compliance Center.|Controlelogboeken <br/><br/> DLP Compliance Management <br/><br/> Apparaatbeheer <br/><br/> IB Compliance Management <br/><br/> Waarschuwingen beheren <br/><br/> Quarantaine <br/><br/> Beveiligingsbeheerder <br/><br/> Beheerder van gevoeligheidslabel <br/><br/> Controlelogboeken alleen-weergeven <br/><br/> Alleen-View-Beheer van DLP-compliance <br/><br/> Apparaatbeheer alleen-weergave <br/><br/> Alleen IB-compliancebeheer voor weergave <br/><br/> Alleen-weergave waarschuwingen beheren|
|**Beveiligingsoperator**|Leden kunnen beveiligingswaarschuwingen beheren en ook rapporten en instellingen van beveiligingsfuncties bekijken.|Zoeken naar naleving <br/><br/> Waarschuwingen beheren <br/><br/> Beveiligingslezer <br/><br/> Controlelogboeken alleen-weergeven <br/><br/> Alleen-View-Beheer van DLP-compliance <br/><br/> Apparaatbeheer alleen-weergave <br/><br/> Alleen IB-compliancebeheer voor weergave <br/><br/> Alleen-weergave waarschuwingen beheren|
|**Beveiligingslezer**|Leden hebben alleen-lezen toegang tot een aantal beveiligingsfuncties van Identity Protection Center, Privileged Identity Management, Monitor Office 365 Service Health en Office 365 Security & Compliance Center. <br/><br/> Het lidmaatschap van deze rolgroep wordt gesynchroniseerd tussen services en centraal beheerd. Leden van deze rolgroep kunnen crossservicebeheerders zijn, evenals externe partnergroepen en Microsoft-ondersteuning. Standaard wordt deze groep mogelijk niet toegewezen aan rollen. Het is echter lid van de rol Beveiligingslezers in Azure Active Directory en overneemt de mogelijkheden van die rol. Als u machtigingen centraal wilt beheren, voert u wijzigingen aan in deze rol in het Azure Active Directory-beheercentrum - zie [beheerdersrolmachtigingen voor](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)meer informatie in Azure Active Directory. Als u deze rolgroep bewerkt in het Security & Compliance Center, zijn deze wijzigingen alleen van toepassing op het Security & Compliance Center en niet op andere services, terwijl wijzigingen in het Azure Active Directory-beheercentrum van invloed zijn op alle services|Beveiligingslezer <br/><br/> Gevoeligheidlabellezer <br/><br/> Alleen-View-Beheer van DLP-compliance <br/><br/> Apparaatbeheer alleen-weergave <br/><br/> Alleen IB-compliancebeheer voor weergave <br/><br/> Alleen-weergave waarschuwingen beheren|
|**Service Assurance-gebruiker**|Leden hebben toegang tot de sectie Serviceassurance in het Office 365 Security & Compliance Center. Serviceassurance biedt rapporten en documenten waarin de beveiligingspraktijken van Microsoft worden beschreven voor klantgegevens die zijn opgeslagen in Office 365. Het biedt ook onafhankelijke auditrapporten van derden over Office 365. Zie [Servicegarantie in het Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)voor meer informatie.|Serviceassurance-weergave|
|**Toezichtbeoordeling**|Leden kunnen het beleid maken en beheren dat bepaalt welke communicatie in een organisatie moet worden beoordeeld. Zie [Beleid voor naleving van communicatievoor uw organisatie configureren voor](../../compliance/communication-compliance-configure.md)meer informatie.|Beheerder van de controlebeoordeling|

> [!NOTE]
> <sup>1.</sup> Deze rolgroep wijst leden niet de machtigingen toe die nodig zijn om het controlelogboek van Office 365 te doorzoeken of om rapporten te gebruiken die Exchange-gegevens kunnen bevatten, zoals de DLP- of ATP-rapporten. Als u in het controlelogboek wilt zoeken of om alle rapporten wilt bekijken, moet een gebruiker machtigingen krijgen in Exchange Online. Dit komt omdat de onderliggende cmdlet die wordt gebruikt om het controlelogboek te doorzoeken, een Exchange Online-cmdlet is. Globale office 365-beheerders kunnen in het controlelogboek zoeken en alle rapporten bekijken omdat ze automatisch worden toegevoegd als leden van de rolgroep Organisatiebeheer in Exchange Online. Zie [Het controlelogboek doorzoeken in het Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)voor meer informatie.

## <a name="roles-in-the-security--compliance-center"></a>Rollen in het Security & Compliance Center

In de volgende tabel worden standaard de beschikbare rollen en de rolgroepen weergegeven waaraan ze zijn toegewezen.

Houd er rekening mee dat de volgende rollen standaard niet zijn toegewezen aan de rolgroep Organisatiebeheer:

- Communicatie

- Voogd

- Data Investigation Management

- Exporteren

- Voorbeeld

- Review

- RMS decoderen

- Beheerder van de controlebeoordeling

|**Rol**|**Beschrijving**|**Standaardtaaktoewijzingen**|
|:-----|:-----|:-----|
|**Controlelogboeken**|Schakel de controle voor de Office 365-organisatie in en configureer deze, bekijk de controlerapporten van de organisatie en exporteer deze rapporten naar een bestand.|Organisatiebeheer <br/><br/> Beheer van records <br/><br/> Beveiligingsbeheerder|
|**Case Management**|Toegang tot eDiscovery-aanvragen maken, bewerken, verwijderen en beheren.|Compliance-beheerder <br/><br/> eDiscovery-beheer <br/><br/> Organisatiebeheer|
|**Communicatie**|Beheer alle communicatie met de bewaarders die zijn geïdentificeerd in een Advanced eDiscovery-aanvraag.  Maak wachtmeldingen, houd herinneringen vast en escalaties naar het management. Volg de bevestiging van de bewaarder van hold-meldingen en beheer de toegang tot de bewaarderportal die door elke bewaarder wordt gebruikt in een geval om communicatie bij te houden voor de gevallen waarin ze werden geïdentificeerd als een bewaarder.|eDiscovery-beheer|
|**Compliance-beheerder**|Instellingen en rapporten voor nalevingsfuncties weergeven en bewerken.|Compliance-beheerder <br/><br/> Beheerder van nalevingsgegevens <br/><br/> Organisatiebeheer|
|**Zoeken naar naleving**|Voer zoekopdrachten uit in postvakken en krijg een schatting van de resultaten.|Compliance-beheerder <br/><br/> Beheerder van nalevingsgegevens <br/><br/> eDiscovery-beheer <br/><br/> Organisatiebeheer <br/><br/> Beveiligingsoperator|
|**Voogd**|Identificeer en beheer beheerders voor geavanceerde eDiscovery-aanvragen en gebruik de informatie uit Azure Active Directory en andere bronnen om gegevensbronnen te vinden die zijn gekoppeld aan bewaarders. Koppel andere gegevensbronnen zoals postvakken, SharePoint-sites en Teams in een aanvraag aan bewaarders.  Plaats een wettelijke greep op de gegevensbronnen die zijn gekoppeld aan bewaarders om inhoud in de context van een zaak te bewaren.|eDiscovery-beheer|
|**Data Investigation Management**|Toegang tot gegevensonderzoeken maken, bewerken, verwijderen en beheren.|Gegevensonderzoeker|
|**Apparaatbeheer**|Instellingen en rapporten voor apparaatbeheerfuncties weergeven en bewerken.|Compliance-beheerder <br/><br/> Beheerder van nalevingsgegevens <br/><br/> Organisatiebeheer <br/><br/> Beveiligingsbeheerder|
|**Dispositiebeheer**|Bedien machtigingen voor toegang tot handmatige dispositie in het Security & Compliance Center.|Compliance-beheerder <br/><br/> Beheerder van nalevingsgegevens <br/><br/> Organisatiebeheer|
|**DLP Compliance Management**|Instellingen en rapporten voor het preventie (DLP)-beleid (data loss prevention) weergeven en bewerken.|Compliance-beheerder <br/><br/> Beheerder van nalevingsgegevens <br/><br/> Organisatiebeheer <br/><br/> Beveiligingsbeheerder|
|**Exporteren**|Postvak- en site-inhoud exporteren die is geretourneerd uit zoekopdrachten.|eDiscovery-beheer|
|**Houden**|Inhoud in postvakken, sites en openbare mappen in de wachtstand plaatsen. Wanneer u in de wacht stand staat, wordt een kopie van de inhoud op een veilige locatie opgeslagen. Eigenaren van inhoud kunnen de oorspronkelijke inhoud nog steeds wijzigen of verwijderen.|Compliance-beheerder <br/><br/> eDiscovery-beheer <br/><br/> Organisatiebeheer|
|**IB Compliance Management**|Het beleid voor informatiebarrière weergeven, maken, verwijderen, wijzigen en testen.|Compliance-beheerder <br/><br/> Beheerder van nalevingsgegevens <br/><br/> Organisatiebeheer <br/><br/> Beveiligingsbeheerder|
|**Waarschuwingen beheren**|Instellingen en rapporten voor waarschuwingen weergeven en bewerken.|Compliance-beheerder <br/><br/> Beheerder van nalevingsgegevens <br/><br/> Organisatiebeheer <br/><br/> Beveiligingsbeheerder <br/><br/> Beveiligingsoperator|
|**Organisatieconfiguratie**|Voer auditrapporten uit, weer en exporteer en beheer nalevingsbeleid voor DLP, apparaten en behoud.|Compliance-beheerder <br/><br/> Beheerder van nalevingsgegevens <br/><br/> Organisatiebeheer|
|**Voorbeeld**|Bekijk een lijst met items die worden geretourneerd uit zoekopdrachten naar inhoud en open elk item uit de lijst om de inhoud ervan weer te geven.|eDiscovery-beheer|
|**Quarantaine**|Hiermee u in quarantaine geplaatste e-mail bekijken en vrijgeven.|Quarantainebeheerder <br/><br/> Beveiligingsbeheerder <br/><br/> Organisatiebeheer|
|**RecordManagement**|Bekijk en bewerk de configuratie en rapporten voor de functie Recordbeheer.|Compliance-beheerder <br/><br/> Beheerder van nalevingsgegevens <br/><br/> Organisatiebeheer <br/><br/> Beheer van records|
|**Retentiebeheer**|Bewaarbeleid beheren.|Beheer van records <br/><br/> Compliance-beheerder <br/><br/> Beheerder van nalevingsgegevens <br/><br/> Organisatiebeheer|
|**Review**|Gebruik Office 365 Advanced eDiscovery om documenten die aan hen zijn toegewezen, bij te houden, te taggen, te analyseren en te testen.|eDiscovery-beheer <br/><br/> Revisor|
|**RMS decoderen**|Decoderen van met RMS beveiligde inhoud bij het exporteren van zoekresultaten.|eDiscovery-beheer|
|**Rolbeheer**|Het lidmaatschap van de rolgroep beheren en aangepaste rolgroepen maken of verwijderen.|Organisatiebeheer|
|**Zoeken en wissen**|Hiermee kunnen mensen gegevens bulkverwijderen die overeenkomen met de criteria van een inhoudszoekopdracht.|Organisatiebeheer|
|**Beveiligingsbeheerder**|Bekijk en bewerk de configuratie en rapporten voor beveiligingsfuncties.|Organisatiebeheer <br/><br/> Beveiligingsbeheerder|
|**Beveiligingslezer**|Bekijk de configuratie en rapporten voor beveiligingsfuncties.|Organisatiebeheer <br/><br/> Beveiligingsoperator <br/><br/> Beveiligingslezer|
|**Beheerder van gevoeligheidslabel**|Gevoeligheidslabels weergeven, maken, wijzigen en verwijderen.|Beheerder van nalevingsgegevens <br/><br/> Organisatiebeheer <br/><br/> Beveiligingsbeheerder|
|**Gevoeligheidlabellezer**|Bekijk de configuratie en het gebruik van gevoeligheidslabels.|Globale lezer <br/><br/> Organisatiebeheer <br/><br/> Beveiligingslezer|
|**Serviceassurance-weergave**|Download de beschikbare documenten in de sectie Serviceassurance. Inhoud omvat onafhankelijke controle, nalevingsdocumentatie en vertrouwensrichtlijnen voor het gebruik van Office 365-functies om nalevings- en beveiligingsrisico's op naleving van de regelgeving te beheren.|Service Assurance-gebruiker <br/><br/> Organisatiebeheer|
|**Beheerder van de controlebeoordeling**|Beheer het beleid voor toezichtscontrole, inclusief welke communicatie moet worden beoordeeld en wie de beoordeling moet uitvoeren.|Toezichtbeoordeling|
|**Controlelogboeken alleen-weergeven**|Controlerapporten weergeven en exporteren. Omdat deze rapporten gevoelige informatie kunnen bevatten, moet u deze rol alleen toewijzen aan mensen met een expliciete noodzaak om deze informatie te bekijken.|Compliance-beheerder <br/><br/> Beheerder van nalevingsgegevens <br/><br/> Organisatiebeheer <br/><br/> Beveiligingsbeheerder <br/><br/> Beveiligingsoperator|
|**Apparaatbeheer alleen-weergave**|Bekijk de configuratie en rapporten voor de functie Apparaatbeheer.|Compliance-beheerder <br/><br/> Beheerder van nalevingsgegevens <br/><br/> Organisatiebeheer <br/><br/> Beveiligingsbeheerder <br/><br/> Beveiligingsoperator <br/><br/> Beveiligingslezer|
|**Alleen-View-Beheer van DLP-compliance**|Bekijk de instellingen en rapporten voor het DLP-beleid (Data Loss Prevention).|Compliance-beheerder <br/><br/> Beheerder van nalevingsgegevens <br/><br/> Organisatiebeheer <br/><br/> Beveiligingsbeheerder <br/><br/> Beveiligingsoperator <br/><br/> Beveiligingslezer|
|**Alleen IB-compliancebeheer voor weergave**|Bekijk de configuratie en rapporten voor de functie Informatiebarrières.|Compliance-beheerder <br/><br/> Beheerder van nalevingsgegevens <br/><br/> Organisatiebeheer <br/><br/> Beveiligingsbeheerder <br/><br/> Beveiligingsoperator <br/><br/> Beveiligingslezer|
|**Alleen-weergave waarschuwingen beheren**|Bekijk de configuratie en rapporten voor de functie Waarschuwingen beheren.|Beveiligingsbeheerder <br/><br/> Beveiligingsoperator <br/><br/> Beveiligingslezer <br/><br/> Compliance-beheerder <br/><br/> Beheerder van nalevingsgegevens <br/><br/> Organisatiebeheer|
|**Ontvangers die alleen voor weergave zijn**|Informatie over gebruikers en groepen weergeven.|MailFlow-beheerder <br/><br/> Compliance-beheerder <br/><br/> Beheerder van nalevingsgegevens <br/><br/> Organisatiebeheer|
|**Alleen-weergaverecordbeheer**|Bekijk de configuratie en rapporten voor de functie Recordbeheer.|Compliance-beheerder <br/><br/> Beheerder van nalevingsgegevens <br/><br/> Organisatiebeheer|
|**Alleen-weergaveretentiebeheer**|Bekijk de configuratie en rapporten voor de functie Retentiebeheer.|Beheerder van nalevingsgegevens <br/><br/> Organisatiebeheer <br/><br/> Compliance-beheerder|
