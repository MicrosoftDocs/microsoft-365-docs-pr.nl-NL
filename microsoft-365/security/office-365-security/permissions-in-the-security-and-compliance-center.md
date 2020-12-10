---
title: Machtigingen-beveiliging & nalevings centrum
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
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
description: Beheerders krijgen de machtigingen die beschikbaar zijn in het beveiligings & nalevings centrum in Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cb0cbb3d04132f0bb053c7da080b7fb90c210fe8
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616234"
---
# <a name="permissions-in-the-security--compliance-center"></a>Machtigingen in het beveiligings- en compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Met de beveiligings & compliance Center kunt u machtigingen verlenen aan personen die nalevings taken uitvoeren, zoals Apparaatbeheer, preventie van gegevensverlies, eDiscovery, bewaren, enzovoort. Deze personen kunnen alleen de taken uitvoeren waartoe u ze expliciet toegang wilt geven. Voor toegang tot de beveiligings & nalevings centrum moeten gebruikers een globale beheerder of een lid zijn van een of meer & beveiligingsgroepen van het nalevings centrum voor compliance.

Machtigingen in het nalevings centrum voor de & beveiliging zijn gebaseerd op het machtigings model voor toegangsbeheer op basis van rollen. RBAC is hetzelfde machtigings model dat wordt gebruikt door Exchange, dus als u bekend bent met Exchange, zijn machtigingen in de beveiligings & nalevings centrum zeer vergelijkbaar. Het is belangrijk dat u dit echter wel moet onthouden, dat Exchange-Rolgroepen en beveiligings & rollen groepen voor nalevings centrum geen lidmaatschap of machtigingen kunnen delen. Hoewel beide rollen een organisatie hebben, zijn ze niet hetzelfde. De machtigingen die ze verlenen en de leden van de rollen groepen verschillen. Hieronder ziet u een lijst van beveiligings & rollen groepen compliance Center.

![Pagina machtigingen in het Beveiligingscentrum beveiligings &](../../media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)

## <a name="relationship-of-members-roles-and-role-groups"></a>Relatie van leden, rollen en rollen groepen

Een **rol** verkent machtigingen voor het uitvoeren van een set taken. met de rol van hoofdletter beheer kunnen personen bijvoorbeeld werken met eDiscovery-aanvragen.

Een **rollen groep** is een reeks rollen waarmee personen hun functie kunnen uitvoeren via het nalevings centrum voor beveiliging &. De rollen groep compliance beheerder bevat bijvoorbeeld onder andere rollen de functies voor het gebruik van hoofdletters en kleine letters, en de configuratie van de organisatie (samen met andere rollen), omdat iemand die een compliance beheerder is, de machtigingen voor die taken nodig heeft.

Het nalevings centrum voor beveiligings & bevat groepen met standaardrollen voor de meest voorkomende taken en functies waaraan u personen moet toewijzen. We raden u aan om afzonderlijke gebruikers als **leden** toe te voegen aan de standaardrol groepen.

![Diagram met de relatie van rollen groepen met rollen en leden](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-security--compliance-center"></a>Machtigingen vereist voor het gebruik van functies in het nalevings centrum voor beveiligings &

In de volgende tabel vindt u de standaardrol groepen die beschikbaar zijn in het beveiligings & nalevings centrum en de rollen die standaard zijn toegewezen aan de rollen groepen. Als u machtigingen voor een gebruiker wilt verlenen om een compliance-taak uit te voeren, voegt u deze toe aan de juiste beveiligings & rollen groep compliance Center.

Door machtigingen te beheren in het nalevings centrum voor de & beveiliging, kunnen gebruikers alleen toegang krijgen tot de nalevings functies die beschikbaar zijn in het beveiligings & nalevings centrum zelf. Als u machtigingen wilt verlenen aan andere compliance-functies die niet beschikbaar zijn in het nalevings centrum voor & beveiliging, zoals Exchange-e-mail stroom regels (ook wel wel transport-regels genoemd), moet u het Exchange-Beheercentrum gebruiken.

Als u wilt weten hoe u toegang verleent tot de beveiligings & nalevings centrum, raadpleegt [u gebruikers toegang geven tot het Beheercentrum van Microsoft 365](grant-access-to-the-security-and-compliance-center.md).

****

|Rollen groep|Beschrijving|Standaardrollen toegewezen|
|---|---|---|
|**Nalevings beheerder**<sup>1</sup>|Leden kunnen instellingen beheren voor Apparaatbeheer, preventie van gegevensverlies, rapporten en behoud.|Case beheer <p> Beheerder van communicatie naleving <p> Analyse van communicatie naleving <p> Communicatiebeleid voor compliance <p> Communicatie nalevings onderzoek <p> Viewer voor communicatie naleving <p> Feedback provider van gegevensclassificatie <p> Revisor feedback van gegevensclassificatie <p> Gegevens onderzoek beheer <p> Beheerder voor naleving <p> Zoekopdracht voor compliance <p> Apparaatbeheer <p> Dispositie beheer <p> DLP-beleid voor naleving <p> Stellen <p> IB-nalevings beheer <p> Waarschuwingen beheren <p> Organisatie configuratie <p> RecordManagement <p> Bewaar beheer <p> Controlelogboeken View-Only <p> Apparaten beheren in View-Only <p> DLP-nalevings beheer View-Only <p> View-Only IB-beheer voor naleving <p> View-Only waarschuwingen beheren <p> Geadresseerden View-Only <p> Record beheer View-Only <p> Bewaar beheer View-Only|
|**Gegevensbeheerder voor naleving**|Leden kunnen instellingen beheren voor Apparaatbeheer, gegevensbeveiliging, preventie van gegevensverlies, rapporten en behoud.|Beheerder voor naleving <p> Zoekopdracht voor compliance <p> Apparaatbeheer <p> DLP-beleid voor naleving <p> Dispositie beheer <p> IB-nalevings beheer <p> Waarschuwingen beheren <p> Organisatie configuratie <p> RecordManagement <p> Bewaar beheer <p> De beheerder van het vertrouwelijkheids label <p> Controlelogboeken View-Only <p> Apparaten beheren in View-Only <p> DLP-nalevings beheer View-Only <p> View-Only IB-beheer voor naleving <p> View-Only waarschuwingen beheren <p> Geadresseerden View-Only <p> Record beheer View-Only <p> Bewaar beheer View-Only|
|**Inhouds viewer van inhouds Verkenner**|De inhoud van de inhoud van inhouds Verkenner weergeven.|Inhoudsweergave van gegevens classificaties|
|**Inhouds Verkenner lijst viewer**|Alle items in de inhouds Verkenner alleen weergeven in de lijstopmaak.|Gegevensclassificatie lijst viewer|
|**Gegevens onderzoeker**|Leden kunnen zoekopdrachten uitvoeren in postvakken, SharePoint-sites en OneDrive-accounts.|Communicatie <p> Zoekopdracht voor compliance <p> Bewaard <p> Gegevens onderzoek beheer <p> Voeren<p> Voorbeeld <p> RMS ontsleutelen <p> Gereviseerd<p> Zoeken en wissen|
|**eDiscovery-Manager**|Leden kunnen zoekopdrachten uitvoeren en bewaren voor postvakken, SharePoint Online-sites en OneDrive voor bedrijven-locaties. Leden kunnen ook eDiscovery-aanvragen maken en beheren, leden toevoegen aan of verwijderen uit een zaak, inhouds zoekopdrachten maken en bewerken die met een zaak zijn geassocieerd, en toegang krijgen tot de gegevens van een zaak in Advanced eDiscovery. <p> Een eDiscovery-beheerder is een lid van de rollen groep van de eDiscovery-beheerder waaraan extra machtigingen zijn toegewezen. Naast de taken die een eDiscovery-beheerder kan uitvoeren, kan een eDiscovery-beheerder het volgende doen:<ul><li>Alle eDiscovery-aanvragen in de organisatie weergeven.</li><li>Het beheren van eDiscovery-zaak na het toevoegen van een zaak als lid van de zaak.</li></ul> <p> Het belangrijkste verschil tussen een eDiscovery-Manager en een eDiscovery-beheerder is dat een eDiscovery-beheerder toegang heeft tot alle cases die worden weergegeven op de pagina **eDiscovery-aanvragen** in het beveiligings & nalevings centrum. Een eDiscovery-Manager kan alleen toegang krijgen tot de aanvragen die ze hebben gemaakt of zaken waarvan ze lid zijn. Zie [eDiscovery-machtigingen toewijzen in het beveiligings & nalevings centrum](../../compliance/assign-ediscovery-permissions.md)voor meer informatie over het instellen van een eDiscovery-beheerder.|Case beheer <p> Communicatie <p> Zoekopdracht voor compliance <p> Bewaard <p> Voeren <p> Stellen <p> Voorbeeld <p> RMS ontsleutelen <p> Gereviseerd|
|**Algemene lezer**|Leden hebben alleen-lezen toegang tot rapporten, waarschuwingen en kunnen alle configuraties en instellingen bekijken.<p> Het belangrijkste verschil tussen algemene lezer en beveiligings lezer is dat een globale lezer toegang heeft tot **configuratie en instellingen**.|Beveiligings lezer <p> Vertrouwelijkheids label lezer <p> Service Assurance-weergave <p> Controlelogboeken View-Only <p> Apparaten beheren in View-Only <p> DLP-nalevings beheer View-Only <p> View-Only IB-beheer voor naleving <p> View-Only waarschuwingen beheren <p> Geadresseerden View-Only <p> Record beheer View-Only <p> Bewaar beheer View-Only|
|**Insider Risk Management**|Met deze functiegroep kunt u Insider Risk Management voor uw organisatie in één groep beheren. Door alle gebruikersaccounts toe te voegen voor aangewezen beheerders, analisten en onderzoekers, kunt u Insider Risk Management-machtigingen in één groep configureren. Deze groep rollen bevat alle machtigingen van het Insider-risicobeheer. Dit is de eenvoudigste manier om snel aan de slag te gaan met Insider Risk Management en geschikt voor organisaties waarvoor geen aparte machtigingen nodig zijn voor afzonderlijke groepen gebruikers.|Case beheer <p> Insider Risk Management-beheerder <p> Insider Risk Management-analyse <p> Insider Risk Management-onderzoek <p> Tijdelijke bijdrage Insider Risk Management|
|**Insider Risk Management-beheerders**|Gebruik deze groep voor het eerst Insider Risk Management en later om Insider Risk-beheerders te scheiden in een gedefinieerde groep. Gebruikers in deze rollen groep kunnen Insider Risk Management Policies, globale instellingen en toewijzingen van rollen groepen maken, lezen, bijwerken en verwijderen.|Case beheer <p> Insider Risk Management-beheerder|
|**Insider Risk Management-analisten**|Met deze groep kunt u machtigingen toewijzen aan gebruikers die fungeren als insider Risk-scenario analisten. Gebruikers in deze rollen groep hebben toegang tot alle meldingen, kwesties en kennisgevingen van insider Risk Management. Ze hebben geen toegang tot de inhouds Verkenner voor insider Risk.|Case beheer <p> Insider Risk Management-analyse|
|**Insider Risk Management onderzoeker**|Met deze groep kunt u machtigingen toewijzen aan gebruikers die fungeren als insider Risk data onderzoeker. Gebruikers in deze rollen groep hebben toegang tot alle meldingen, gevallen, meldingen en meldingen van insider Risk Management, en de inhouds Verkenner voor alle zaken.|Case beheer <p> Insider Risk Management-onderzoek|
|**IRM-medewerkers**|Deze rolgroep is zichtbaar, maar wordt alleen gebruikt door de Achtergrondservices.|Tijdelijke bijdrage Insider Risk Management|
|**Beheerder van de mailflow**|Leden kunnen e-mail stroom inzichten en rapporten in het beveiligings & nalevings centrum controleren en bekijken. Globale beheerders kunnen gewone gebruikers toevoegen aan deze groep, maar als de gebruiker geen lid is van de Exchange-beheergroep, heeft de gebruiker geen toegang tot Exchange-beheertaken.|Geadresseerden View-Only|
|**Organisatiebeheer**<sup>1</sup>|Leden kunnen machtigingen voor toegang tot functies in de beveiligings & nalevings centrum en ook de instellingen voor het beheren van apparaten, preventie van gegevensverlies, rapporten en behoud. <p> Gebruikers die geen globale beheerder zijn, moeten lid zijn van de Exchange-beheerder voor het weergeven en uitvoeren van acties op apparaten die worden beheerd met basis mobiliteit en beveiliging voor Microsoft 365 (voorheen bekend als Mobile Device Management of MDM). <p> Globale beheerders worden automatisch toegevoegd als leden van deze rollen groep.|Controlelogboeken <p> Case beheer <p> Beheerder voor naleving <p> Zoekopdracht voor compliance <p> Apparaatbeheer <p> DLP-beleid voor naleving <p> Stellen <p> IB-nalevings beheer <p> Waarschuwingen beheren <p> Organisatie configuratie <p> Quarantaine <p> RecordManagement <p> Bewaar beheer <p> Rollenbeheer <p> Zoeken en wissen <p> Beveiligingsbeheerder <p> Beveiligings lezer <p> De beheerder van het vertrouwelijkheids label <p> Vertrouwelijkheids label lezer <p> Service Assurance-weergave <p> Controlelogboeken View-Only <p> Apparaten beheren in View-Only <p> DLP-nalevings beheer View-Only <p> View-Only IB-beheer voor naleving <p> View-Only waarschuwingen beheren <p> Geadresseerden View-Only <p> Record beheer View-Only <p> Bewaar beheer View-Only|
|**Quarantaine beheerder**|Leden hebben toegang tot alle quarantaine acties. Zie voor meer informatie geplaatste [berichten en bestanden beheren als beheerder in EOP](manage-quarantined-messages-and-files.md)|Quarantaine|
|**Recordbeheer**|Leden kunnen record inhoud beheren en verwijderen.|RecordManagement|
|**Revisor**|Leden kunnen de lijst met aanvragen alleen weergeven op de pagina eDiscovery-aanvragen in het Beveiligingscentrum beveiligings &. Ze kunnen geen eDiscovery-zaak maken, openen of beheren. Het primaire doel van deze groep is de mogelijkheid te bieden dat leden gegevens kunnen bekijken en openen in [Advanced eDiscovery (Classic)](../../compliance/office-365-advanced-ediscovery.md) (ook wel *Advanced eDiscovery v1*). <p> Deze groep heeft de meest beperkte eDiscovery-gerelateerde machtigingen.<p>**Opmerking:** Momenteel hebben gebruikers die lid zijn van de gegevensbeheerderrol, geen toegang tot gegevens in [Advanced eDiscovery in Microsoft 365](../../compliance/overview-ediscovery-20.md) (ook wel *Advanced eDiscovery v2* genoemd). Als u leden wilt toevoegen aan een zaak in Advanced eDiscovery v2, zodat ze aanvraaggegevens kunnen bekijken, moet een gebruiker lid zijn van de functiegroep eDiscovery-beheerder.|Gereviseerd|
|**Beveiligingsbeheerder**|Leden hebben toegang tot een aantal beveiligingsfuncties van identiteits beschermings centrum, compatibiliteit met geprivilegieerde identiteiten, monitoring Microsoft 365-service status en beveiliging & nalevings centrum. <p> Standaard lijken deze rollen groep geen leden te hebben. De rol Beveiligingsbeheerder van Azure Active Directory is echter toegewezen aan deze rollen groep. Deze rollen groep neemt daarom de mogelijkheden en het lidmaatschap van de beveiligingsrol beveiligingsbeheerder uit Azure Active Directory. <p> Als u machtigingen centraal wilt beheren, kunt u groepsleden toevoegen en verwijderen in het Azure Active Directory-Beheercentrum. Zie [machtigingen voor beheerdersrollen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)voor meer informatie. Als u deze rollen groep in het beveiligings & nalevings centrum bewerkt (lidmaatschap of rollen), zijn deze wijzigingen alleen van toepassing op de beveiligings & nalevings centrum en niet voor andere services. <p> Deze rolgroep bevat alle alleen-lezen machtigingen van de rol van beveiligings lezer, plus een aantal extra beheerdersmachtigingen voor dezelfde services: Azure Information Protection, Identity Protection Center, Microsoft 365-service status en beveiliging & nalevings centrum.|Controlelogboeken <p> Apparaatbeheer <p> DLP-beleid voor naleving <p> IB-nalevings beheer <p> Waarschuwingen beheren <p> Quarantaine <p> Beveiligingsbeheerder <p> De beheerder van het vertrouwelijkheids label <p> Controlelogboeken View-Only <p> Apparaten beheren in View-Only <p> DLP-nalevings beheer View-Only <p> View-Only IB-beheer voor naleving <p> View-Only waarschuwingen beheren|
|**Beveiligings operator**|Leden kunnen beveiligingswaarschuwingen beheren en ook rapporten en instellingen van beveiligingsfuncties weergeven.|Zoekopdracht voor compliance <p> Waarschuwingen beheren <p> Beveiligings lezer <p> Controlelogboeken View-Only <p> Apparaten beheren in View-Only <p> DLP-nalevings beheer View-Only <p> View-Only IB-beheer voor naleving <p> View-Only waarschuwingen beheren|
|**Beveiligings lezer**|Leden hebben alleen-lezen toegang tot een aantal beveiligingsfuncties in Identity Protection Center, identiteitsbeheer van Microsoft 365, de service status van Microsoft en beveiliging & nalevings centrum. <p> Standaard lijken deze rollen groep geen leden te hebben. De beveiligingsrol beveiligings lezer van Azure Active Directory is echter toegewezen aan deze rollen groep. Deze rollen groep neemt daarom de mogelijkheden en het lidmaatschap van de rol van beveiligings lezer over van Azure Active Directory. <p> Als u machtigingen centraal wilt beheren, kunt u groepsleden toevoegen en verwijderen in het Azure Active Directory-Beheercentrum. Zie [machtigingen voor beheerdersrollen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)voor meer informatie. Als u deze rollen groep in het beveiligings & nalevings centrum bewerkt (lidmaatschap of rollen), zijn deze wijzigingen alleen van toepassing op de beveiligings & nalevings centrum en niet voor andere services.|Beveiligings lezer <p> Vertrouwelijkheids label lezer <p> Apparaten beheren in View-Only <p> DLP-nalevings beheer View-Only <p> View-Only IB-beheer voor naleving <p> View-Only waarschuwingen beheren|
|**Service controle-gebruiker**|Leden hebben toegang tot de sectie Service controle in het beveiligings & compliance Center. Service controle biedt rapporten en documenten die de beveiligingsprocedures van Microsoft beschrijven voor klantgegevens die zijn opgeslagen in Microsoft 365. Het biedt ook onafhankelijke controlerapporten van derden voor Microsoft 365. Zie voor meer informatie [service controle in het artikel beveiligings & nalevings centrum](https://docs.microsoft.com/microsoft-365/compliance/service-assurance).|Service Assurance-weergave|
|**Beoordeling door toezicht**|Leden kunnen de beleidsregels maken en beheren om te bepalen welke communicatie onderworpen is aan de beoordeling van een organisatie. Zie [beleid voor communicatie naleving voor uw organisatie configureren](../../compliance/communication-compliance-configure.md)voor meer informatie.|Toezicht beheerder van de beoordeling|
|

> [!NOTE]
> <sup>1</sup> deze rollen groep kent geen leden de benodigde machtigingen voor het zoeken in het auditlogboek of het gebruik van rapporten die mogelijk Exchange-gegevens bevatten, zoals de DLP-of Defender for Office 365-rapporten. Als u wilt zoeken in het auditlogboek of alle rapporten wilt weergeven, moet een gebruiker zijn toegewezen machtigingen in Exchange Online. Dit komt doordat de onderliggende cmdlet die wordt gebruikt voor het zoeken in het auditlogboek een Exchange Online-cmdlet is. Globale beheerders kunnen het controlelogboek doorzoeken en alle rapporten weergeven omdat ze automatisch worden toegevoegd als leden van de rollen groep Organisatiebeheer in Exchange Online. Zie voor meer informatie [het controlelogboek zoeken in het beveiligings & nalevings centrum](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

## <a name="roles-in-the-security--compliance-center"></a>Rollen in het nalevings centrum voor beveiligings &

In de volgende tabel ziet u de beschikbare rollen en groepen rollen waaraan deze standaard zijn toegewezen.

Houd er rekening mee dat de volgende rollen niet standaard zijn toegewezen aan de rollen groep Organisatiebeheer:

- Communicatie
- Beheerder van communicatie naleving
- Analyse van communicatie naleving
- Communicatiebeleid voor compliance
- Communicatie nalevings onderzoek
- Viewer voor communicatie naleving
- Bewaard
- Inhoudsweergave van gegevens classificaties
- Feedback provider van gegevensclassificatie
- Revisor feedback van gegevensclassificatie
- Gegevensclassificatie lijst viewer
- Gegevens onderzoek beheer
- Dispositie beheer
- Voeren
- Insider Risk Management-beheerder
- Insider Risk Management-analyse
- Insider Risk Management-onderzoek
- Tijdelijke bijdrage Insider Risk Management
- Voorbeeld
- Gereviseerd
- RMS ontsleutelen
- Toezicht beheerder van de beoordeling

****

|Rol|Beschrijving|Standaardtoewijzingen van rollen groepen|
|---|---|---|
|**Controlelogboeken**|Schakel controle in en configureer deze voor de organisatie, Bekijk de controlerapporten van de organisatie en exporteer deze rapporten naar een bestand.|Organisatiebeheer <p> Beveiligingsbeheerder|
|**Case beheer**|Het maken, bewerken, verwijderen en beheren van toegang tot eDiscovery-aanvragen.|Beheerder voor naleving <p> eDiscovery-Manager <p> Intern risicobeheer <p> Insider Risk Management-beheerders <p> Insider Risk Management-analisten <p> Insider Risk Management onderzoeker <p> Organisatiebeheer|
|**Communicatie**|Alle communicatie met de aangemerkte medewerkers beheren in een geavanceerde eDiscovery-zaak.  Maak meldingen voor bewaring, houd herinneringen en escalaties aan het beheer. Houd de ontvangst van meldingen van de bewaring van meldingen bij en beheer de toegang tot de portal voor beheerders die door elke beheerder in een zaak wordt gebruikt om de communicatie te traceren voor de gevallen waarin ze zijn aangewezen als een beheerder.|eDiscovery-Manager|
|**Beheerder van communicatie naleving**|Wordt gebruikt voor het beheer van beleid in de functie communicatie naleving.|Beheerder voor naleving|
|**Analyse van communicatie naleving**|Wordt gebruikt voor het uitvoeren van onderzoek, herstel van de schendingen van het bericht in de functie communicatie naleving. Kan alleen metagegevens van een bericht weergeven.|Beheerder voor naleving|
|**Communicatiebeleid voor compliance**|Wordt gebruikt voor toegang tot aanvragen voor communicatie naleving.|Beheerder voor naleving|
|**Communicatie nalevings onderzoek**|Wordt gebruikt voor het uitvoeren van onderzoek, herbemiddeling en de schendingen van berichten in de functie communicatie naleving. Kan de metagegevens en het bericht van een bericht bekijken.|Beheerder voor naleving|
|**Viewer voor communicatie naleving**|Wordt gebruikt voor toegang tot rapporten en widgets in de functie communicatie naleving.||
|**Beheerder voor naleving**|Instellingen en rapporten voor compliance-functies weergeven en bewerken.|Beheerder voor naleving <p> Gegevensbeheerder voor naleving <p> Organisatiebeheer|
|**Zoekopdracht voor compliance**|Zoekopdrachten uitvoeren in postvakken en een schatting van de resultaten weergeven.|Beheerder voor naleving <p> Gegevensbeheerder voor naleving <p> eDiscovery-Manager <p> Organisatiebeheer <p> Beveiligings operator|
|**Bewaard**|Identificeer en beheer de beheerder voor geavanceerde eDiscovery-aanvragen en gebruik de informatie uit Azure Active Directory en andere bronnen om gegevensbronnen te zoeken die zijn gekoppeld aan de beheerder. U kunt andere gegevensbronnen, zoals postvakken, SharePoint-sites en teams, met de beheerder in een zaak koppelen.  Plaats een juridische bewaring op de gegevensbronnen die zijn gekoppeld aan de beheerder om inhoud in de context van een zaak te beschermen.|eDiscovery-Manager|
|**Inhoudsweergave van gegevens classificaties**|In-place weergave van bestanden in inhouds Verkenner weergeven.|Inhouds viewer van inhouds Verkenner|
|**Feedback provider van gegevensclassificatie**|Hiermee kunt u feedback geven aan classificaties in inhouds Verkenner.|Beheerder voor naleving|
|**Revisor feedback van gegevensclassificatie**|Hiermee kunt u feedback van classificaties in feedback Verkenner bekijken.|Beheerder voor naleving|
|**Gegevensclassificatie lijst viewer**|Bekijk de lijst met bestanden in inhouds Verkenner.|Inhouds Verkenner lijst viewer|
|**Gegevens onderzoek beheer**|Het maken, bewerken, verwijderen en beheren van toegang tot gegevens onderzoek.|Beheerder voor naleving <p> Gegevens onderzoeker|
|**Apparaatbeheer**|Instellingen en rapporten voor functies voor Apparaatbeheer weergeven en bewerken.|Beheerder voor naleving <p> Gegevensbeheerder voor naleving <p> Organisatiebeheer <p> Beveiligingsbeheerder|
|**Dispositie beheer**|Machtigingen beheren voor het openen van de handmatige vernietiging in de beveiligings & nalevings centrum.|Beheerder voor naleving <p> Gegevensbeheerder voor naleving|
|**DLP-beleid voor naleving**|Instellingen en rapporten voor preventie van gegevensverlies (DLP)-beleid bekijken en bewerken.|Beheerder voor naleving <p> Gegevensbeheerder voor naleving <p> Organisatiebeheer <p> Beveiligingsbeheerder|
|**Voeren**|Postvak en site-inhoud exporteren die het resultaat is van zoekopdrachten.|eDiscovery-Manager|
|**Stellen**|Inhoud in postvakken, sites en openbare mappen in de wacht zetten. Wanneer het in de wachtstand staat, wordt een kopie van de inhoud opgeslagen op een veilige locatie. Inhouds eigenaren kunnen de oorspronkelijke inhoud nog steeds wijzigen of verwijderen.|Beheerder voor naleving <p> eDiscovery-Manager <p> Organisatiebeheer|
|**IB-nalevings beheer**|U kunt beleidsregels voor informatie hindernis weergeven, maken, verwijderen, wijzigen en testen.|Beheerder voor naleving <p> Gegevensbeheerder voor naleving <p> Organisatiebeheer <p> Beveiligingsbeheerder|
|**Insider Risk Management-beheerder**|Maken, bewerken, verwijderen en beheren van toegang tot de functie Insider Risk Management.|Intern risicobeheer <p> Insider Risk Management-beheerders|
|**Insider Risk Management-analyse**|Toegang krijgen tot alle meldingen, kwesties en kennisgevingen van het Insider Risk Management.|Intern risicobeheer <p> Insider Risk Management-analisten|
|**Insider Risk Management-onderzoek**|Toegang krijgen tot alle insider Risk Management-waarschuwingen,-aanvragen,-kennisgevings sjablonen en de inhouds Verkenner voor alle zaken.|Intern risicobeheer <p> Insider Risk Management onderzoeker|
|**Tijdelijke bijdrage Insider Risk Management**|Deze rolgroep is zichtbaar, maar wordt alleen gebruikt door de Achtergrondservices.|IRM-medewerkers|
|**Waarschuwingen beheren**|Instellingen en rapporten voor waarschuwingen weergeven en bewerken.|Beheerder voor naleving <p> Gegevensbeheerder voor naleving <p> Organisatiebeheer <p> Beveiligingsbeheerder <p> Beveiligings operator|
|**Organisatie configuratie**|Controlerapporten uitvoeren, weergeven en exporteren, en nalevingsbeleid beheren voor DLP, apparaten en behoud.|Beheerder voor naleving <p> Gegevensbeheerder voor naleving <p> Organisatiebeheer|
|**Voorbeeld**|Een lijst weergeven met de items die worden geretourneerd van inhouds zoekopdrachten, en elk item in de lijst openen om de inhoud ervan weer te geven.|eDiscovery-Manager|
|**Quarantaine**|Hiermee kunt u gequarantinede e-mail weergeven en vrijgeven.|Quarantaine beheerder <p> Beveiligingsbeheerder <p> Organisatiebeheer|
|**RecordManagement**|De configuratie en rapporten voor de functie voor record beheer weergeven en bewerken.|Beheerder voor naleving <p> Gegevensbeheerder voor naleving <p> Organisatiebeheer <p> Recordbeheer|
|**Bewaar beheer**|Bewaarbeleid beheren.|Beheerder voor naleving <p> Gegevensbeheerder voor naleving <p> Organisatiebeheer|
|**Gereviseerd**|Gebruik Advanced eDiscovery voor het bijhouden, markeren, analyseren en testen van documenten die aan hen zijn toegewezen.|eDiscovery-Manager <p> Revisor|
|**RMS ontsleutelen**|Met RMS beveiligde inhoud ontsleutelen bij het exporteren van zoekresultaten.|eDiscovery-Manager|
|**Rollenbeheer**|Lidmaatschap van rollen groepen beheren en aangepaste Rolgroepen maken of verwijderen.|Organisatiebeheer|
|**Zoeken en wissen**|Hiermee kunnen mensen bulksgewijs gegevens verwijderen die voldoen aan de criteria van een inhoud zoeken.|Organisatiebeheer|
|**Beveiligingsbeheerder**|De configuratie en rapporten voor beveiligingsfuncties weergeven en bewerken.|Organisatiebeheer <p> Beveiligingsbeheerder|
|**Beveiligings lezer**|De configuratie en rapporten van beveiligingsfuncties weergeven.|Organisatiebeheer <p> Beveiligings operator <p> Beveiligings lezer|
|**De beheerder van het vertrouwelijkheids label**|U kunt palletlabels weergeven, maken, wijzigen en verwijderen.|Gegevensbeheerder voor naleving <p> Organisatiebeheer <p> Beveiligingsbeheerder|
|**Vertrouwelijkheids label lezer**|De configuratie en het gebruik van de palletlabels weergeven.|Algemene lezer <p> Organisatiebeheer <p> Beveiligings lezer|
|**Service Assurance-weergave**|Download de beschikbare documenten in de sectie Service Assurance. Inhoud omvat onafhankelijke controle, documentatie voor compliance en vertrouwde informatie over het gebruik van Microsoft 365-functies om de naleving van compliance en beveiligingsrisico's te beheren.|Service controle-gebruiker <p> Organisatiebeheer|
|**Toezicht beheerder van de beoordeling**|Beleidsregels voor beoordeling van toezicht beheren, waaronder welke berichten moeten worden gereviseerd en wie de beoordeling moet uitvoeren.|Beoordeling door toezicht|
|**Alleen-lezen audit logboeken**|Controlerapporten weergeven en exporteren. Omdat deze rapporten gevoelige informatie bevatten, moet u deze functie alleen toewijzen aan personen die een expliciete behoefte hebben om deze informatie te bekijken.|Beheerder voor naleving <p> Gegevensbeheerder voor naleving <p> Organisatiebeheer <p> Beveiligingsbeheerder <p> Beveiligings operator|
|**Alleen-lezen apparaten beheer**|De configuratie en rapporten voor de functie Apparaatbeheer weergeven.|Beheerder voor naleving <p> Gegevensbeheerder voor naleving <p> Organisatiebeheer <p> Beveiligingsbeheerder <p> Beveiligings operator <p> Beveiligings lezer|
|**View-only DLP compliance beheren**|Bekijk de instellingen en rapporten voor preventie van gegevensverlies (DLP-beleid).|Beheerder voor naleving <p> Gegevensbeheerder voor naleving <p> Organisatiebeheer <p> Beveiligingsbeheerder <p> Beveiligings operator <p> Beveiligings lezer|
|**View-only Compliance Management**|Bekijk de configuratie en rapporten voor de functie voor informatie barrières.|Beheerder voor naleving <p> Gegevensbeheerder voor naleving <p> Organisatiebeheer <p> Beveiligingsbeheerder <p> Beveiligings operator <p> Beveiligings lezer|
|**Alleen-lezen waarschuwingen beheren**|Bekijk de configuratie en rapporten voor de functie waarschuwingen beheren.|Beveiligingsbeheerder <p> Beveiligings operator <p> Beveiligings lezer <p> Beheerder voor naleving <p> Gegevensbeheerder voor naleving <p> Organisatiebeheer|
|**Geadresseerden voor alleen weergeven**|Informatie over gebruikers en groepen weergeven.|Beheerder van de mailflow <p> Beheerder voor naleving <p> Gegevensbeheerder voor naleving <p> Organisatiebeheer|
|**Record beheer alleen weergeven**|De configuratie en rapporten voor de functie voor record beheer weergeven.|Beheerder voor naleving <p> Gegevensbeheerder voor naleving <p> Organisatiebeheer|
|**Voorbeeld van Bewaar beheer**|Bekijk de configuratie en rapporten voor de functie Bewaar beheer.|Gegevensbeheerder voor naleving <p> Organisatiebeheer <p> Beheerder voor naleving|
|
