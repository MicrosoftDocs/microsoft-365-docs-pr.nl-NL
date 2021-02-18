---
title: Functiemachtigingen in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Meer informatie over de machtigingen die zijn vereist voor taken in de zelfstandige Exchange Online Protection
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9c24c6f57ea9a7c0e1b3332d2f4b518b232ec0c2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288297"
---
# <a name="permissions-in-standalone-eop"></a>Machtigingen in standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
-  [Zelfstandige versie van Exchange Online Protection](exchange-online-protection-overview.md)

Voor zelfstandige Exchange Online Protection (EOP) zonder Exchange Online-postvakken wordt het model voor toegangsbeheer op basis van rollen gebruikt om eenvoudig machtigingen aan uw beheerders te verlenen. U kunt de machtigingsfuncties in de zelfstandige EOP gebruiken om uw nieuwe organisatie snel op weg te helpen.

Zie Beheerdersrolgroepen beheren in EOP als u gebruikers [machtigingen wilt verlenen.](manage-admin-role-group-permissions-in-eop.md)

Zie Informatie over beheerdersrollen voor meer informatie over machtigingen [in](../../admin/add-users/about-admin-roles.md)Microsoft 365.

## <a name="role-based-permissions"></a>Machtigingen op basis van rollen

De beheerdersmachtigingen die u aan gebruikers verleent, zijn gebaseerd op beheerrollen. Een beheerrol definieert de cmdlets die beschikbaar zijn voor een reeks gegeven taken. Omdat het Exchange-beheercentrum (EAC) en de zelfstandige EOP PowerShell beide cmdlets gebruiken, geeft het verlenen van toegang tot een cmdlet de gebruiker toestemming om de gerelateerde taken uit te voeren in het EAC of in zelfstandige EOP PowerShell. Zo definieert de rol Mail Recipients de cmdlets die nodig zijn om e-mailgebruikers te wijzigen.

In zelfstandige EOP zijn beheerdersrollen het enige type beheerrol dat beschikbaar is (er zijn geen rollen voor eindgebruikers of beleidsregels voor roltoewijzing).

## <a name="role-groups"></a>Rollengroepen

Om het gemakkelijker te maken om rollen toe te wijzen aan gebruikers, maakt zelfstandige EOP gebruik van rollengroepen. Beheerrollen worden toegewezen aan rollengroepen en de leden van de rollengroep krijgen de machtigingen die aan de rollen zijn gekoppeld. Met andere woorden, beheerrollen zijn niet rechtstreeks toegewezen aan gebruikers; deze zijn toegewezen aan de rollengroep. Met dit model kunt u veel rollen tegelijk toewijzen aan veel leden van de rollengroep. Leden van rollengroep kunnen e-mailgebruikers, beveiligingsgroepen met e-mail, gebruikers van het Microsoft 365-beheercentrum en andere rollengroepen zijn.

In de volgende afbeelding ziet u de relatie tussen gebruikers, rollengroepen en rollen.

![Relatie tussen rol, rollengroep en lid](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

De beschikbare rollengroepen in zelfstandige EOP worden in de volgende tabel beschreven.

****

|Rollengroep|Beschrijving|Standaardrollen toegewezen|
|---|---|---|
|ComplianceManagement|Configureer en beheer nalevingsinstellingen binnen de organisatie, inclusief preventie van gegevensverlies (DLP) als uw abonnement DLP-mogelijkheden heeft. <p> Leden van de [rol Compliancebeheerder](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) in Azure AD krijgen automatisch de machtigingen van deze rollengroep.|Auditlogboeken <p> Compliancebeheer <p> Information Rights Management <p> Bewaarbeheer <p> View-Only auditlogboeken maken <p> View-Only configureren <p> View-Only geadresseerden|
|ContentExplorerContentViewer|Niet gebruikt.|Gegevensclassificatie-inhoudsviewer|
|ContentExplorerListViewer|Niet gebruikt.|Viewer voor gegevensclassificatielijst|
|HelpDesk|E-mailgebruikers weergeven en beheren.|Wachtwoord opnieuw instellen <p> Gebruikersopties <p> View-Only geadresseerden|
|Bijenmanagement|Beveiligingsfuncties (antispam, malware, enzovoort) beheren.|Transport-overden <p> View-Only configureren <p> View-Only geadresseerden|
|MailFlowAdministrator|Geaccepteerde domeinen en connectors weergeven en beheren|Externe en geaccepteerde domeinen <p> View-Only geadresseerden|
|OrganizationManagement|Beheerderstoegang tot de hele organisatie en de mogelijkheid om vrijwel elke taak uit te voeren. <p> Leden van de [rol globale beheerder](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) in Azure AD krijgen automatisch de machtigingen van deze rollengroep. <p> **Belangrijk:** omdat de rollengroep OrganizationManagement een krachtige rol is, mogen alleen gebruikers die beheertaken op organisatieniveau uitvoeren, lid zijn van deze rollengroep.|AntiMalware <p> AntiSpam <p> Auditlogboeken <p> Compliancebeheerder <p> Distributiegroepen <p> Information Rights Management <p> E-mailontvanger maken <p> E-mailontvangers <p> Berichten bijhouden <p> Migratie <p> Clienttoegang van organisatie <p> Organisatieconfiguratie <p> Organisatie transportinstellingen <p> Quarantaine <p> Beleid voor geadresseerden <p> Externe en geaccepteerde domeinen <p> Wachtwoord opnieuw instellen <p> Bewaarbeheer <p> Rollenbeheer <p> Beveiligingsbeheerder <p> Maken en lidmaatschap van beveiligingsgroep <p> Beveiligingslezer <p> Beheerder van gevoeligheidslabel <p> Toezicht <p> Transport-overden <p> Transportregels <p> Gebruikersopties <p> View-Only AntiMalware <p> View-Only AntiSpam <p> View-Only auditlogboeken maken <p> View-Only configureren <p> View-Only quarantaine <p> View-Only geadresseerden <p> View-Only Bedreigingsinformatie|
|QuarantineAdministrator|In quarantaine geplaatste berichten voor alle geadresseerden beheren.|Quarantaine|
|RecipientManagement|Geadresseerdenobjecten in de organisatie maken, beheren en verwijderen.|Distributiegroepen <p> E-mailontvanger maken <p> E-mailontvangers <p> Berichten bijhouden <p> Migratie <p> Beleid voor geadresseerden <p> Wachtwoord opnieuw instellen|
|RecordsManagement|U kunt nalevingsfuncties configureren, zoals labels voor bewaarbeleid, berichtclassificaties en regels voor de e-mailstroom (ook wel transportregels genoemd).|Berichten bijhouden <p> Bewaarbeheer <p> Transportregels|
|SecurityAdministrator|Configureer alle beschermingsaspecten in de organisatie (antispam, anti-malware, anti-spoofing, quarantaine, enzovoort). <p> Leden van de [rol Beveiligingsbeheerder](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) in Azure AD krijgen automatisch de machtigingen van deze rollengroep.|AntiMalware <p> AntiSpam <p> Auditlogboeken <p> Quarantaine <p> Beveiligingsbeheerder <p> Beheerder van gevoeligheidslabel <p> View-Only AntiMalware <p> View-Only AntiSpam <p> View-Only auditlogboeken maken <p> View-Only quarantaine <p> View-Only Bedreigingsinformatie|
|SecurityReader|Alleen-weergeven toegang tot alle aspecten van bescherming in de organisatie (antispam, anti-malware, anti-spoofing, quarantaine, enzovoort). <p> Leden van de [rol Beveiligingslezer](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) in Azure AD krijgen automatisch de machtigingen van deze rollengroep.|Beveiligingslezer <p> View-Only AntiMalware <p> View-Only AntiSpam <p> View-Only quarantaine <p> View-Only Bedreigingsinformatie|
|TenantAdmins|Lidmaatschap van deze rollengroep wordt gesynchroniseerd tussen services en wordt centraal beheerd. Aan deze rollengroep worden standaard geen rollen toegewezen. De groep wordt echter lid van de rollengroep Organisatiebeheer en neemt deze machtigingen over.|geen|
|ViewOnlyOrganizationManagement|Geadresseerden, beveiligings- en configuratieobjecten en hun eigenschappen in de organisatie weergeven.|Compliancebeheerder <p> Beveiligingsbeheerder <p> Beveiligingslezer <p> Beheerder van gevoeligheidslabel <p> View-Only configureren <p> View-Only geadresseerden|
|

Als u werkt in een kleine organisatie met slechts enkele beheerders, moet u deze gebruikers mogelijk alleen toevoegen aan de rollengroep Organisatiebeheer en hoeft u de andere rollengroepen mogelijk nooit te gebruiken. Als u in een grotere organisatie werkt, zijn er mogelijk beheerders die specifieke taken uitvoeren, zoals de configuratie van geadresseerden. In dat geval kunt u een beheerder toevoegen aan de rollengroep Recipient Management en een andere beheerder aan de rollengroep Organisatiebeheer. Deze beheerders kunnen dan hun specifieke gebieden beheren, maar ze zijn niet bevoegd om gebieden te beheren waar ze niet verantwoordelijk voor zijn.

Als de ingebouwde rollengroepen in Exchange Online niet overeenkomen met de taakfunctie van uw beheerders, kunt u rollengroepen maken en hieraan rollen toevoegen. Zie Rollengroepen beheren [in zelfstandige EOP](manage-admin-role-group-permissions-in-eop.md)voor meer informatie.

## <a name="roles"></a>Rollen

In de volgende tabel worden de ingebouwde rollen beschreven die beschikbaar zijn in de zelfstandige EOP.

****

|Rol**|Beschrijving|Standaardtoewijzingen voor rollengroep|
|---|---|---|
|AntiMalware|Bekijk en wijzig de configuratie en rapporten voor antimalwarefuncties.|OrganizationManagement <p> SecurityAdministrator|
|AntiSpam|Bekijk en wijzig de configuratie en rapporten voor antispamfuncties.|OrganizationManagement <p> SecurityAdministrator|
|Auditlogboeken|Zoek in het auditlogboek voor beheerders en bekijk de resultaten.|ComplianceManagement <p> OrganizationManagement <p> SecurityAdministrator|
|Compliancebeheerder<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement <p> ViewOnlyOrganizationManagement|
|Gegevensclassificatie-inhoudsviewer<sup>\*</sup>||ContentExplorerContentViewer|
|Viewer voor gegevensclassificatielijst<sup>\*</sup>||
|Distributiegroepen|Alle distributiegroepen, beveiligingsgroepen met e-mail en leden maken en beheren.|OrganizationManagement <p> RecipientManagement|
|Information Rights Management<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement|
|E-mailontvanger maken|E-mailgebruikers maken en verwijderen.|OrganizationManagement <p> RecipientManagement|
|E-mailontvangers|Bestaande e-mailgebruikers wijzigen.|OrganizationManagement <p> RecipientManagement|
|Berichten bijhouden<sup>\*</sup>||OrganizationManagement <p> RecipientManagement <p> Recordbeheer|
|Migratie<sup>\*</sup>||OrganizationManagement <p> RecipientManagement|
|MyBaseOptions|Hiermee kunnen gebruikers hun eigen in quarantaine geplaatste berichten weergeven. <p> Deze rol wordt automatisch toegewezen aan gebruikers en u kunt deze niet handmatig toewijzen.|geen|
|Clienttoegang van organisatie<sup>\*</sup>||OrganizationManagement|
|Organisatieconfiguratie|Rapporten bekijken.|OrganizationManagement|
|Organisatie transportinstellingen<sup>\*</sup>||OrganizationManagement|
|Quarantaine|Alle typen in quarantaine geplaatste berichten voor alle geadresseerden beheren.|OrganizationManagement <p> QuarantineAdministrator <p> SecurityAdministrator|
|Beleid voor geadresseerden<sup>\*</sup>||OrganizationManagement <p> RecipientManagement|
|Externe en geaccepteerde domeinen|Externe domeinen, geaccepteerde domeinen en connectors beheren.|MailFlowAdministrator <p> OrganizationManagement|
|Wachtwoord opnieuw instellen<sup>\*</sup>||HelpDesk <p> OrganizationManagement <p> RecipientManagement|
|Bewaarbeheer<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement <p> RecordsManagement|
|Rollenbeheer|Rollengroepen maken en beheren.|OrganizationManagement|
|Beveiligingsbeheerder|Beheer de configuratie en rapporten voor alle beveiligings- en beveiligingsfuncties.|OrganizationManagement <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|Maken en lidmaatschap van beveiligingsgroep|Beveiligingsgroepen met e-mail maken en beheren.|OrganizationManagement|
|Beveiligingslezer|Bekijk de configuratie en rapporten voor beveiligings- en beveiligingsfuncties.|Organisatiebeheer <p> SecurityReader <p> ViewOnlyOrganizationManagement|
|Beheerder van gevoeligheidslabel<sup>\*</sup>||OrganizationManagement <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|Toezicht<sup>\*</sup>||OrganizationManagement|
|Transport-overden|Beheer functies voor antimalware, antispamfuncties en antivervalsingsfuncties.|Bijenmanagement <p> OrganizationManagement|
|Transportregels|Regels voor de e-mailstroom maken en beheren (ook wel transportregels genoemd).|OrganizationManagement <p> RecordsManagement|
|Gebruikersopties|Bestaande e-mailgebruikers wijzigen.|HelpDesk <p> OrganizationManagement|
|View-Only AntiMalware|Bekijk de configuratie en rapporten voor antimalwarefuncties.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|View-Only AntiSpam|Bekijk de configuratie en rapporten voor antispamfuncties.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|View-Only auditlogboeken maken|Zoek in het auditlogboek voor beheerders en bekijk de resultaten.|ComplianceManagement <p> OrganizationManagement <p> SecurityAdministrator|
|View-Only configureren|Alle instellingen voor de organisatie en de e-mailstroom (niet-geadresseerde) in de organisatie weergeven.|ComplianceManagement <p> Bijenmanagement <p> OrganizationManagement <p> ViewOnlyOrganizationManagement|
|View-Only quarantaine|Alle in quarantaine geplaatste berichten voor alle geadresseerden weergeven.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|View-Only geadresseerden|Eigenschappen van geadresseerden weergeven en bericht traceren.|ComplianceManagement <p> HelpDesk <p> Bijenmanagement <p> MailFlowAdministrator <p>  OrganizationManagement <p> ViewOnlyOrganizationManagement|
|View-Only Bedreigingsinformatie<sup>\*</sup>||OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|

<sup>\*</sup> Hoewel deze rol beschikbaar is, heeft deze in feite niets nuttigs in de zelfstandige EOP.

## <a name="microsoft-365-permissions-in-standalone-eop"></a>Microsoft 365-machtigingen in zelfstandige EOP

Wanneer u een gebruiker maakt in het Microsoft 365-beheercentrum, kunt u kiezen of u verschillende beheerdersrollen, zoals globale beheerder, servicebeheerder, wachtwoordbeheerder, en dergelijke, wilt toewijzen aan de gebruiker. Sommige, maar niet alle Microsoft 365-rollen verlenen de gebruiker beheerdersmachtigingen in EOP.

> [!NOTE]
> Aan het account dat u hebt gebruikt om uw zelfstandige EOP-organisatie te maken, wordt automatisch de globale beheerdersrol toegewezen.

De volgende tabel bevat de Microsoft 365-rollen en de zelfstandige EOP-rollengroepen met welke ze corresponderen. Zie Over beheerdersrollen voor meer informatie [over deze rollen.](../../admin/add-users/about-admin-roles.md)

****

|Microsoft 365-rol|EOP-rollengroep|
|---|---|
|Exchange-beheerder|OrganizationManagement|
|Algemeen beheerder|OrganizationManagement <p> **Opmerking:** De rol van globale beheerder en de rollengroep OrganizationManagement zijn met behulp van een speciale rollengroep Bedrijfsbeheerder aan elkaar gekoppeld. De rollengroep Bedrijfsbeheerder wordt intern beheerd en kan niet rechtstreeks worden gewijzigd.|
|Wachtwoordbeheerder|HelpDesk|
|Algemene lezer|ViewOnlyOrganizationManagement|
|Beveiligingsbeheerder|SecurityAdministrator|
|Beveiligingslezer|SecurityReader|
|

Andere Microsoft 365-rollen hebben geen bijbehorende EOP-rollengroep en verlenen geen beheerdersmachtigingen in EOP. Zie Beheerdersrollen toewijzen voor meer informatie over het toewijzen van een Microsoft 365-rol [aan een gebruiker.](../../admin/add-users/assign-admin-roles.md)

Gebruikers kunnen beheerdersrechten in EOP worden verleend zonder ze toe te voegen aan Microsoft 365-rollen. U doet dit door de gebruiker toe te voegen als lid van een EOP-rollengroep. De gebruiker krijgt machtigingen in EOP, maar ze krijgen geen machtigingen in andere Microsoft 365-werkbelastingen.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Ga op een van de volgende stappen te werk om te controleren of u een rollengroep hebt gekopieerd:

- Ga in het Exchange-beheercentrum naar **Beheerdersrollen** voor machtigingen en controleer of de rollengroep wordt vermeld \> (of niet wordt weergegeven). Selecteer de rollengroep en controleer de instellingen  in het deelvenster Details of klik op het ![ pictogram Bewerken om de instellingen te ](../../media/ITPro-EAC-EditIcon.png) controleren.

- Vervang in Exchange Online PowerShell door de naam van de rollengroep en voer de volgende opdracht uit om te controleren of de rollengroep bestaat (of bestaat niet) en controleer de \<Role Group Name\> instellingen:

  ```PowerShell
  Get-RoleGroup -Identity "<Role Group Name>" | Format-List
  ```
