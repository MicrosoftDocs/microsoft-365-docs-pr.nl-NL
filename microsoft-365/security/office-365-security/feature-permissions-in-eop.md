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
description: Meer informatie over de machtigingen die zijn vereist voor taken in zelfstandige Exchange Online Protection
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 212a109c792522270b7e5000747bec950b7f4fe2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926980"
---
# <a name="permissions-in-standalone-eop"></a>Machtigingen in standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
-  [Zelfstandige Exchange Online Protection](exchange-online-protection-overview.md)

Standalone Exchange Online Protection (EOP) zonder Exchange Online-postvakken gebruikt het RBAC-machtigingsmodel (Role Based Access Control) om eenvoudig machtigingen te verlenen aan uw beheerders. U kunt de machtigingsfuncties in zelfstandige EOP gebruiken om uw nieuwe organisatie snel te laten werken.

Zie Beheerdersrollengroepen beheren [in EOP](manage-admin-role-group-permissions-in-eop.md)als u gebruikers machtigingen wilt verlenen.

Zie Over [beheerdersrollen](../../admin/add-users/about-admin-roles.md)voor meer informatie over machtigingen in Microsoft 365.

## <a name="role-based-permissions"></a>Machtigingen op basis van rollen

De beheerdersmachtigingen die u aan gebruikers verleent, zijn gebaseerd op beheerrollen. Een beheerrol definieert de cmdlets die beschikbaar zijn voor een set bepaalde taken. Omdat het Exchange-beheercentrum (EAC) en zelfstandige EOP PowerShell beide cmdlets gebruiken, geeft het verlenen van toegang tot een cmdlet de gebruiker toestemming om de gerelateerde taken in de EAC of in zelfstandige EOP PowerShell uit te voeren. De rol E-mailontvangers definieert bijvoorbeeld de cmdlets die nodig zijn om e-mailgebruikers te wijzigen.

In zelfstandige EOP zijn beheerdersrollen het enige type beheerrol dat beschikbaar is (er zijn geen rollen van eindgebruikers of beleidsregels voor roltoewijzingen).

## <a name="role-groups"></a>Rollengroepen

Om het gemakkelijker te maken om rollen toe te wijzen aan gebruikers, maakt zelfstandige EOP gebruik van rollengroepen. Managementrollen worden toegewezen aan rollengroepen en de leden van de rollengroep krijgen de machtigingen die aan de rollen zijn gekoppeld. Met andere woorden: managementrollen worden niet rechtstreeks toegewezen aan gebruikers. ze zijn toegewezen aan de rollengroep. Met dit model kunt u veel rollen tegelijk toewijzen aan veel leden van de rollengroep. Leden van rollengroepen kunnen e-mailgebruikers, beveiligingsgroepen met e-mail, gebruikers van het Microsoft 365-beheercentrum en andere rollengroepen zijn.

In de volgende afbeelding ziet u de relatie tussen gebruikers, rollengroepen en rollen.

![Relatie tussen rol, rollengroep en lid](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

De beschikbare rollengroepen in zelfstandige EOP worden beschreven in de volgende tabel.

****

|Rollengroep|Beschrijving|Standaardrollen toegewezen|
|---|---|---|
|Compliancemanagement|Configureer en beheer compliance-instellingen binnen de organisatie, inclusief preventie van gegevensverlies (DLP) als uw abonnement DLP-mogelijkheden heeft. <p> Leden van de [rol Compliancebeheerder](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) in Azure AD krijgen automatisch de machtigingen van deze rollengroep.|Auditlogboeken <p> Compliancebeheer <p> Information Rights Management <p> Bewaarbeheer <p> View-Only auditlogboeken <p> View-Only configuratie <p> View-Only Geadresseerden|
|ContentExplorerContentViewer|Niet gebruikt.|Inhoudsviewer voor gegevensclassificatie|
|ContentExplorerListViewer|Niet gebruikt.|Gegevensclassificatielijstviewer|
|HelpDesk|E-mailgebruikers weergeven en beheren.|Wachtwoord opnieuw instellen <p> Gebruikersopties <p> View-Only Geadresseerden|
|Hygiënemanagement|Beveiligingsfuncties beheren (antispam, anti-malware, enzovoort).|Transporthygiëne <p> View-Only configuratie <p> View-Only Geadresseerden|
|MailFlowAdministrator|Geaccepteerde domeinen en connectors weergeven en beheren|Externe en geaccepteerde domeinen <p> View-Only Geadresseerden|
|Organisatiebeheer|Beheerderstoegang tot de hele organisatie en de mogelijkheid om vrijwel elke taak uit te voeren. <p> Leden van de [rol Globale beheerder](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) in Azure AD krijgen automatisch de machtigingen van deze rollengroep. <p> **Belangrijk:** Omdat de rollengroep Organisatiebeheer een krachtige rol is, mogen alleen gebruikers die beheertaken op organisatieniveau uitvoeren, lid zijn van deze rollengroep.|AntiMalware <p> AntiSpam <p> Auditlogboeken <p> Compliancebeheerder <p> Distributiegroepen <p> Information Rights Management <p> Het maken van e-mailontvangers <p> Geadresseerden van e-mail <p> Bericht bijhouden <p> Migratie <p> Organization Client Access <p> Organisatieconfiguratie <p> Instellingen voor organisatietransport <p> Quarantaine <p> Beleid voor geadresseerden <p> Externe en geaccepteerde domeinen <p> Wachtwoord opnieuw instellen <p> Bewaarbeheer <p> Rollenbeheer <p> Beveiligingsbeheerder <p> Het maken en lidmaatschap van beveiligingsgroep <p> Beveiligingslezer <p> Gevoeligheidslabelbeheerder <p> Toezicht <p> Transporthygiëne <p> Transportregels <p> Gebruikersopties <p> View-Only AntiMalware <p> View-Only AntiSpam <p> View-Only auditlogboeken <p> View-Only configuratie <p> View-Only Quarantaine <p> View-Only Geadresseerden <p> View-Only Threat Intelligence|
|QuarantineAdministrator|In quarantaine geplaatste berichten beheren voor alle geadresseerden.|Quarantaine|
|RecipientManagement|Geadresseerdeobjecten in de organisatie maken, beheren en verwijderen.|Distributiegroepen <p> Het maken van e-mailontvangers <p> Geadresseerden van e-mail <p> Bericht bijhouden <p> Migratie <p> Beleid voor geadresseerden <p> Wachtwoord opnieuw instellen|
|RecordsManagement|Compliancefuncties configureren, zoals bewaarbeleidslabels, berichtclassificaties en regels voor e-mailstroom (ook wel transportregels genoemd).|Bericht bijhouden <p> Bewaarbeheer <p> Transportregels|
|SecurityAdministrator|Configureer alle aspecten van beveiliging in de organisatie (antispam, anti-malware, anti-spoofing, quarantaine, enzovoort). <p> Leden van de [rol Beveiligingsbeheerder](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) in Azure AD krijgen automatisch de machtigingen van deze rollengroep.|AntiMalware <p> AntiSpam <p> Auditlogboeken <p> Quarantaine <p> Beveiligingsbeheerder <p> Gevoeligheidslabelbeheerder <p> View-Only AntiMalware <p> View-Only AntiSpam <p> View-Only auditlogboeken <p> View-Only Quarantaine <p> View-Only Threat Intelligence|
|SecurityReader|View-only access to all aspects of protection in the organization (anti-spam, anti-malware, anti-spoofing, quarantine, etc.). <p> Leden van de [rol Beveiligingslezer](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) in Azure AD krijgen automatisch de machtigingen van deze rollengroep.|Beveiligingslezer <p> View-Only AntiMalware <p> View-Only AntiSpam <p> View-Only Quarantaine <p> View-Only Threat Intelligence|
|TenantAdmins|Lidmaatschap van deze rollengroep wordt gesynchroniseerd tussen services en centraal beheerd. Aan deze rollengroep zijn standaard geen rollen toegewezen. Het is echter een lid van de rollengroep Organisatiebeheer en neemt deze machtigingen over.|geen|
|ViewOnlyOrganizationManagement|Bekijk geadresseerde- en beveiligings- en configuratieobjecten en hun eigenschappen in de organisatie.|Compliancebeheerder <p> Beveiligingsbeheerder <p> Beveiligingslezer <p> Gevoeligheidslabelbeheerder <p> View-Only configuratie <p> View-Only Geadresseerden|
|

Als u werkt in een kleine organisatie met slechts een paar beheerders, moet u deze gebruikers mogelijk alleen toevoegen aan de rollengroep Organisatiebeheer en hoeft u de andere rollengroepen mogelijk nooit te gebruiken. Als u in een grotere organisatie werkt, hebt u mogelijk beheerders die specifieke taken uitvoeren, zoals de configuratie van de geadresseerde. In die gevallen kunt u één beheerder toevoegen aan de rollengroep Geadresseerdenbeheer en een andere beheerder aan de rollengroep Organisatiebeheer. Deze beheerders kunnen vervolgens hun specifieke gebieden beheren, maar ze hebben geen machtigingen voor het beheren van gebieden waar ze niet verantwoordelijk voor zijn.

Als de ingebouwde rollengroepen in Exchange Online niet overeenkomen met de taakfunctie van uw beheerders, kunt u rollengroepen maken en hieraan rollen toevoegen. Zie Rollengroepen beheren in zelfstandige EOP voor [meer informatie.](manage-admin-role-group-permissions-in-eop.md)

## <a name="roles"></a>Rollen

De ingebouwde rollen die beschikbaar zijn in zelfstandige EOP worden beschreven in de volgende tabel.

****

|Rol**|Beschrijving|Standaardtoewijzingen voor rollengroep|
|---|---|---|
|AntiMalware|Bekijk en wijzig de configuratie en rapporten voor anti-malwarefuncties.|Organisatiebeheer <p> SecurityAdministrator|
|AntiSpam|Bekijk en wijzig de configuratie en rapporten voor antispamfuncties.|Organisatiebeheer <p> SecurityAdministrator|
|Auditlogboeken|Zoek in het auditlogboek van de beheerder en bekijk de resultaten.|Compliancemanagement <p> Organisatiebeheer <p> SecurityAdministrator|
|Compliancebeheerder<sup>\*</sup>||Compliancemanagement <p> Organisatiebeheer <p> ViewOnlyOrganizationManagement|
|Inhoudsviewer voor gegevensclassificatie<sup>\*</sup>||ContentExplorerContentViewer|
|Gegevensclassificatielijstviewer<sup>\*</sup>||
|Distributiegroepen|Maak en beheer alle distributiegroepen, beveiligingsgroepen met e-mail en leden.|Organisatiebeheer <p> RecipientManagement|
|Information Rights Management<sup>\*</sup>||Compliancemanagement <p> Organisatiebeheer|
|Het maken van e-mailontvangers|E-mailgebruikers maken en verwijderen.|Organisatiebeheer <p> RecipientManagement|
|Geadresseerden van e-mail|Bestaande e-mailgebruikers wijzigen.|Organisatiebeheer <p> RecipientManagement|
|Bericht bijhouden<sup>\*</sup>||Organisatiebeheer <p> RecipientManagement <p> Recordbeheer|
|Migratie<sup>\*</sup>||Organisatiebeheer <p> RecipientManagement|
|MyBaseOptions|Hiermee kunnen gebruikers hun eigen in quarantaine geplaatste berichten bekijken. <p> Deze rol wordt automatisch toegewezen aan gebruikers en u kunt deze niet handmatig toewijzen.|geen|
|Organization Client Access<sup>\*</sup>||Organisatiebeheer|
|Organisatieconfiguratie|Rapporten bekijken.|Organisatiebeheer|
|Instellingen voor organisatietransport<sup>\*</sup>||Organisatiebeheer|
|Quarantaine|Beheer alle typen in quarantaine geplaatste berichten voor alle geadresseerden.|Organisatiebeheer <p> QuarantineAdministrator <p> SecurityAdministrator|
|Beleid voor geadresseerden<sup>\*</sup>||Organisatiebeheer <p> RecipientManagement|
|Externe en geaccepteerde domeinen|Beheer externe domeinen, geaccepteerde domeinen en connectors.|MailFlowAdministrator <p> Organisatiebeheer|
|Wachtwoord opnieuw instellen<sup>\*</sup>||HelpDesk <p> Organisatiebeheer <p> RecipientManagement|
|Bewaarbeheer<sup>\*</sup>||Compliancemanagement <p> Organisatiebeheer <p> RecordsManagement|
|Rollenbeheer|Rollengroepen maken en beheren.|Organisatiebeheer|
|Beveiligingsbeheerder|Beheer de configuratie en rapporten voor alle beveiligings- en beveiligingsfuncties.|Organisatiebeheer <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|Het maken en lidmaatschap van beveiligingsgroep|Beveiligingsgroepen met e-mail maken en beheren.|Organisatiebeheer|
|Beveiligingslezer|Bekijk de configuratie en rapporten voor beveiligings- en beveiligingsfuncties.|Organisatiebeheer <p> SecurityReader <p> ViewOnlyOrganizationManagement|
|Gevoeligheidslabelbeheerder<sup>\*</sup>||Organisatiebeheer <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|Toezicht<sup>\*</sup>||Organisatiebeheer|
|Transporthygiëne|Anti-malware, antispamfuncties en anti-spoofing-functies beheren.|Hygiënemanagement <p> Organisatiebeheer|
|Transportregels|Regels voor e-mailstroom maken en beheren (ook wel transportregels genoemd).|Organisatiebeheer <p> RecordsManagement|
|Gebruikersopties|Bestaande e-mailgebruikers wijzigen.|HelpDesk <p> Organisatiebeheer|
|View-Only AntiMalware|Bekijk de configuratie en rapporten voor anti-malwarefuncties.|Organisatiebeheer <p> SecurityAdministrator <p> SecurityReader|
|View-Only AntiSpam|Bekijk de configuratie en rapporten voor antispamfuncties.|Organisatiebeheer <p> SecurityAdministrator <p> SecurityReader|
|View-Only auditlogboeken|Zoek in het auditlogboek van de beheerder en bekijk de resultaten.|Compliancemanagement <p> Organisatiebeheer <p> SecurityAdministrator|
|View-Only configuratie|Bekijk alle instellingen voor organisatie en e-mailstroom (niet-geadresseerde) in de organisatie.|Compliancemanagement <p> Hygiënemanagement <p> Organisatiebeheer <p> ViewOnlyOrganizationManagement|
|View-Only Quarantaine|Bekijk alle in quarantaine geplaatste berichten voor alle geadresseerden.|Organisatiebeheer <p> SecurityAdministrator <p> SecurityReader|
|View-Only Geadresseerden|Eigenschappen van geadresseerden weergeven en bericht traceren uitvoeren.|Compliancemanagement <p> HelpDesk <p> Hygiënemanagement <p> MailFlowAdministrator <p>  Organisatiebeheer <p> ViewOnlyOrganizationManagement|
|View-Only Threat Intelligence<sup>\*</sup>||Organisatiebeheer <p> SecurityAdministrator <p> SecurityReader|
|

<sup>\*</sup> Hoewel deze rol beschikbaar is, is deze in feite niet nuttig in zelfstandige EOP.

## <a name="microsoft-365-permissions-in-standalone-eop"></a>Microsoft 365-machtigingen in zelfstandige EOP

Wanneer u een gebruiker maakt in het Microsoft 365-beheercentrum, kunt u kiezen of u verschillende beheerrollen, zoals Globale beheerder, Servicebeheerder, Wachtwoordbeheerder, en dergelijke, wilt toewijzen aan de gebruiker. Sommige, maar niet alle, Microsoft 365-rollen verlenen de gebruikers beheerdersmachtigingen in EOP.

> [!NOTE]
> Het account dat u hebt gebruikt om uw zelfstandige EOP-organisatie te maken, wordt automatisch toegewezen aan de rol globale beheerder.

De volgende tabel bevat de Microsoft 365-rollen en de zelfstandige EOP-rollengroepen waar ze aan voldoen. Zie Over beheerdersrollen voor [meer informatie over deze rollen.](../../admin/add-users/about-admin-roles.md)

****

|Microsoft 365-rol|EOP-rollengroep|
|---|---|
|Exchange-beheerder|Organisatiebeheer|
|Algemeen beheerder|Organisatiebeheer <p> **Opmerking:** De rol globale beheerder en de rollengroep Organisatiebeheer zijn gekoppeld met behulp van een speciale rollengroep bedrijfsbeheerder. De rollengroep Bedrijfsbeheerder wordt intern beheerd en kan niet rechtstreeks worden gewijzigd.|
|Wachtwoordbeheerder|HelpDesk|
|Algemene lezer|ViewOnlyOrganizationManagement|
|Beveiligingsbeheerder|SecurityAdministrator|
|Beveiligingslezer|SecurityReader|
|

Andere Microsoft 365-rollen hebben geen bijbehorende EOP-rollengroep en verlenen geen beheerdersmachtigingen in EOP. Zie Beheerdersrollen toewijzen voor meer informatie over het toewijzen van een Microsoft 365-rol aan [een gebruiker.](../../admin/add-users/assign-admin-roles.md)

Gebruikers kunnen beheerdersrechten krijgen in EOP zonder ze toe te voegen aan Microsoft 365-rollen. U doet dit door de gebruiker toe te voegen als lid van een EOP-rollengroep. De gebruiker krijgt machtigingen in EOP, maar ze krijgen geen machtigingen in andere Microsoft 365-werkbelastingen.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u een rollengroep hebt gekopieerd, gaat u als volgt te werk:

- Ga in het EAC naar **Machtigingenbeheerdersrollen** en controleer of de rollengroep \> wordt weergegeven (of niet wordt weergegeven). Selecteer de rollengroep en controleer de instellingen in het deelvenster Details of klik op **Pictogram** ![ Bewerken bewerken om de instellingen te ](../../media/ITPro-EAC-EditIcon.png) controleren.

- Vervang in Exchange Online PowerShell door de naam van de rollengroep en voer de volgende opdracht uit om te controleren of de rollengroep bestaat (of niet bestaat) en controleer de \<Role Group Name\> instellingen:

  ```PowerShell
  Get-RoleGroup -Identity "<Role Group Name>" | Format-List
  ```