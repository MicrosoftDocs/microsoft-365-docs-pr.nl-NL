---
title: Functiemachtigingen in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Meer informatie over de machtiging die vereist is voor taken in zelfstandige Exchange Online Protection
ms.openlocfilehash: 0138bd4716d831a33fa4b5a0fbdce0f154d62776
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208872"
---
# <a name="permissions-in-standalone-eop"></a>Machtigingen in zelfstandige EOP

Standalone Exchange Online Protection (EOP) zonder Exchange Online-postvakken maakt gebruik van het RBAC-machtigingenmodel (Role Based Access Control) om eenvoudig machtigingen toe te kennen aan uw beheerders. U de machtigingsfuncties in standalone EOP gebruiken om uw nieuwe organisatie snel operationeel te krijgen.

Zie [Beheerdersrolgroepen beheren in EOP](manage-admin-role-group-permissions-in-eop.md)als u machtigingen wilt verlenen aan gebruikers.

Zie [Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)voor meer informatie over machtigingen in Microsoft 365.

## <a name="role-based-permissions"></a>Op rollen gebaseerde machtigingen

De beheerdersmachtigingen die u aan gebruikers verleent, zijn gebaseerd op beheerrollen. Een beheerrol definieert de cmdlets die beschikbaar zijn voor een reeks bepaalde taken. Omdat het Exchange-beheercentrum (EAC) en standalone EOP PowerShell beide cmdlets gebruiken, geeft het verlenen van toegang tot een cmdlet de gebruiker toestemming om de gerelateerde taken in de EAC of in standalone EOP PowerShell uit te voeren. De rol E-mailgeadresseerden definieert bijvoorbeeld de cmdlets die nodig zijn om e-mailgebruikers te wijzigen.

In zelfstandige EOP zijn administratieve rollen het enige type beheerrol dat beschikbaar is (er zijn geen rollen voor eindgebruikers of rollentoewijzingsbeleid).

## <a name="role-groups"></a>Rolgroepen

Om het eenvoudiger te maken om rollen aan gebruikers toe te wijzen, gebruikt standalone EOP rolgroepen. Beheerrollen worden toegewezen aan rolgroepen en de leden van de rolgroep krijgen de machtigingen die aan de rollen zijn gekoppeld. Met andere woorden, beheerrollen worden niet rechtstreeks toegewezen aan gebruikers; ze zijn toegewezen aan de rolgroep. Met dit model u veel rollen tegelijk aan veel rolgroepsleden toewijzen. Leden van rolgroepen kunnen e-mailgebruikers, beveiligingsgroepen met e-mail, gebruikers uit het Microsoft 365-beheercentrum en andere rolgroepen zijn.

In de volgende afbeelding ziet u de relatie tussen gebruikers, rolgroepen en rollen.

![Relatie tussen rol, rollengroep en lid](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

De beschikbare rolgroepen in standalone EOP worden beschreven in de volgende tabel.

||||
|---|---|---|
|**Rolgroep**|**Beschrijving**|**Toegewezen standaardrollen**|
|ComplianceManagement|Configureer en beheer nalevingsinstellingen binnen de organisatie, inclusief preventie van gegevensverlies (DLP) als uw abonnement dlp-mogelijkheden heeft. <br/><br/> Leden van de functie [Compliance Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) in Azure AD krijgen automatisch de machtigingen van deze rolgroep.|Controlelogboeken <br/><br/> Compliance Administration <br/><br/> Information Rights Management <br/><br/> Retentiebeheer <br/><br/> Alleen-weergave-controlelogboeken <br/><br/> Alleen-weergeven-configuratie <br/><br/> Alleen-weergaveontvangers|
|ContentExplorerContentViewer|Niet gebruikt.|Inhoudsviewer voor gegevensclassificatie|
|ContentExplorerListViewer|Niet gebruikt.|Lijstviewer voor gegevensclassificatie|
|Helpdesk|E-mailgebruikers weergeven en beheren.|Wachtwoord opnieuw instellen <br/><br/> Gebruikersopties <br/><br/> Alleen-weergaveontvangers|
|HygiëneBeheer|Beheer beveiligingsfuncties (anti-spam, anti-malware, enz.).|Transporthygiëne <br/><br/> Alleen-weergeven-configuratie <br/><br/> Alleen-weergaveontvangers|
|MailFlowAdministrator|Geaccepteerde domeinen en connectoren weergeven en beheren|Externe en geaccepteerde domeinen <br/><br/> Alleen-weergaveontvangers|
|OrganisatieManagement|Beheer toegang tot de hele organisatie en de mogelijkheid om bijna elke taak uit te voeren. <br/><br/> Leden van de rol [Globale beheerder](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) in Azure AD krijgen automatisch de machtigingen van deze rolgroep. <br/><br/> **Belangrijk**: Omdat de rolgroep OrganizationManagement een krachtige rol heeft, moeten alleen gebruikers die administratieve taken op organisatieniveau uitvoeren, lid zijn van deze rolgroep.|Antimalware <br/><br/> Antispam <br/><br/> Controlelogboeken <br/><br/> Complianceadministrator <br/><br/> Distributiegroepen <br/><br/> Information Rights Management <br/><br/> Het maken van e-mailontvangers <br/><br/> Geadresseerden voor e-mail <br/><br/> Bericht bijhouden <br/><br/> Migratie <br/><br/> Clienttoegang voor de organisatie <br/><br/> Organisatieconfiguratie <br/><br/> Instellingen voor organisatievervoer <br/><br/> Quarantaine <br/><br/> Beleid voor geadresseerden <br/><br/> Externe en geaccepteerde domeinen <br/><br/> Wachtwoord opnieuw instellen <br/><br/> Retentiebeheer <br/><br/> Rolbeheer <br/><br/> Beveiligingsbeheerder <br/><br/> Creatie en lidmaatschap van beveiligingsgroepen <br/><br/> Beveiligingslezer <br/><br/> Beheerder van gevoeligheidslabel <br/><br/> Toezicht <br/><br/> Transporthygiëne <br/><br/> Vervoersregels <br/><br/> Gebruikersopties <br/><br/> View-Only AntiMalware <br/><br/> Alleen weergeven antispam <br/><br/> Alleen-weergave-controlelogboeken <br/><br/> Alleen-weergeven-configuratie <br/><br/> Alleen weergeven quarantaine <br/><br/> Alleen-weergaveontvangers <br/><br/> Alleen-weergave bedreigingsinformatie|
|Quarantainebeheerder|In quarantaine geplaatste berichten voor alle ontvangers beheren.|Quarantaine|
|RecipientManagement|Geadresseerde objecten in de organisatie maken, beheren en verwijderen.|Distributiegroepen <br/><br/> Het maken van e-mailontvangers <br/><br/> Geadresseerden voor e-mail <br/><br/> Bericht bijhouden <br/><br/> Migratie <br/><br/> Beleid voor geadresseerden <br/><br/> Wachtwoord opnieuw instellen|
|RecordsManagement RecordsManagement|Nalevingsfuncties configureren, zoals bewaarbeleidtags, berichtclassificaties en regels voor e-mailstromen (ook wel transportregels genoemd).|Bericht bijhouden <br/><br/> Retentiebeheer <br/><br/> Vervoersregels|
|SecurityAdministrator (SecurityAdministrator)|Configureer alle aspecten van de bescherming in de organisatie (anti-spam, anti-malware, anti-spoofing, quarantaine, enz.). <br/><br/> Leden van de rol [Beveiligingsbeheerder](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) in Azure AD krijgen automatisch de machtigingen van deze rolgroep.|Antimalware <br/><br/> Antispam <br/><br/> Controlelogboeken <br/><br/> Quarantaine <br/><br/> Beveiligingsbeheerder <br/><br/> Beheerder van gevoeligheidslabel <br/><br/> View-Only AntiMalware <br/><br/> Alleen weergeven antispam <br/><br/> Alleen-weergave-controlelogboeken <br/><br/> Alleen weergeven quarantaine <br/><br/> Alleen-weergave bedreigingsinformatie|
|SecurityReader (SecurityReader)|View-only toegang tot alle aspecten van bescherming in de organisatie (anti-spam, anti-malware, anti-spoofing, quarantaine, enz.). <br/><br/> Leden van de rol [Beveiligingslezer](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) in Azure AD krijgen automatisch de machtigingen van deze rolgroep.|Beveiligingslezer <br/><br/> View-Only AntiMalware <br/><br/> Alleen weergeven antispam <br/><br/> Alleen weergeven quarantaine <br/><br/> Alleen-weergave bedreigingsinformatie|
|TenantAdmins|Het lidmaatschap van deze rolgroep wordt gesynchroniseerd tussen services en centraal beheerd. Standaard krijgt deze rolgroep geen rollen toegewezen. Het zal echter lid zijn van de rolgroep Organisatiebeheer en deze machtigingen overnemen.|geen|
|ViewOnlyOrganizationManagement|Bekijk geadresseerde, beveiliging en configuratieobjecten en hun eigenschappen in de organisatie.|Complianceadministrator <br/><br/> Beveiligingsbeheerder <br/><br/> Beveiligingslezer <br/><br/> Beheerder van gevoeligheidslabel <br/><br/> Alleen-weergeven-configuratie <br/><br/> Alleen-weergaveontvangers|
|

Als u werkt in een kleine organisatie met slechts een paar beheerders, moet u deze gebruikers mogelijk alleen toevoegen aan de rolgroep Organisatiebeheer en hoeft u de andere rolgroepen mogelijk nooit te gebruiken. Als u in een grotere organisatie werkt, hebt u mogelijk beheerders die specifieke taken uitvoeren, zoals de configuratie van geadresseerden. In die gevallen u één beheerder toevoegen aan de rolgroep Geadresseerdbeheer en een andere beheerder aan de rolgroep Organisatiebeheer. Deze beheerders kunnen vervolgens hun specifieke gebieden beheren, maar ze hebben geen machtigingen om gebieden te beheren waarvoor ze niet verantwoordelijk zijn.

Als de ingebouwde rolgroepen in Exchange Online niet overeenkomen met de functie van uw beheerders, u rolgroepen maken en er rollen aan toevoegen. Zie [Rolgroepen beheren in zelfstandige EOP](manage-admin-role-group-permissions-in-eop.md)voor meer informatie.

## <a name="roles"></a>Rollen

De ingebouwde rollen die beschikbaar zijn in standalone EOP worden beschreven in de volgende tabel.

||||
|---|---|---|
|**Rol**|**Beschrijving**|**Standaardtoewijzingen voor rollengroepen**|
|Antimalware|Bekijk en wijzig de configuratie en rapporten voor anti-malwarefuncties.|OrganisatieManagement <br/><br/> SecurityAdministrator (SecurityAdministrator)|
|Antispam|Bekijk en wijzig de configuratie en rapporten voor antispamfuncties.|OrganisatieManagement <br/><br/> SecurityAdministrator (SecurityAdministrator)|
|Controlelogboeken|Zoek in het controlelogboek van de beheerder en bekijk de resultaten.|ComplianceManagement <br/><br/> OrganisatieManagement <br/><br/> SecurityAdministrator (SecurityAdministrator)|
|Complianceadministrator<sup>\*</sup>||ComplianceManagement <br/><br/> OrganisatieManagement <br/><br/> ViewOnlyOrganizationManagement|
|Inhoudsviewer voor gegevensclassificatie<sup>\*</sup>||ContentExplorerContentViewer|
|Lijstviewer voor gegevensclassificatie<sup>\*</sup>||
|Distributiegroepen|Maak en beheer alle distributiegroepen, beveiligingsgroepen met e-mail en leden.|OrganisatieManagement <br/><br/> RecipientManagement|
|Beheer van informatierechten<sup>\*</sup>||ComplianceManagement <br/><br/> OrganisatieManagement|
|Het maken van e-mailontvangers|E-mailgebruikers maken en verwijderen.|OrganisatieManagement <br/><br/> RecipientManagement|
|Geadresseerden voor e-mail|Bestaande e-mailgebruikers wijzigen.|OrganisatieManagement <br/><br/> RecipientManagement|
|Bericht bijhouden<sup>\*</sup>||OrganisatieManagement <br/><br/> RecipientManagement <br/><br/> Records beheer|
|Migratie<sup>\*</sup>||OrganisatieManagement <br/><br/> RecipientManagement|
|MyBaseOpties|Hiermee kunnen gebruikers hun eigen in quarantaine geplaatste berichten bekijken. <br/><br/> Deze rol wordt automatisch toegewezen aan gebruikers en u deze niet handmatig toewijzen.|geen|
|Clienttoegang voor de organisatie<sup>\*</sup>||OrganisatieManagement|
|Organisatieconfiguratie|Rapporten bekijken.|OrganisatieManagement|
|Instellingen voor organisatievervoer<sup>\*</sup>||OrganisatieManagement|
|Quarantaine|Alle typen in quarantaine geplaatst bericht voor alle ontvangers beheren.|OrganisatieManagement <br/><br/> Quarantainebeheerder <br/><br/> SecurityAdministrator (SecurityAdministrator)|
|Beleid voor geadresseerden<sup>\*</sup>||OrganisatieManagement <br/><br/> RecipientManagement|
|Externe en geaccepteerde domeinen|Beheer externe domeinen, geaccepteerde domeinen en connectoren.|MailFlowAdministrator <br/><br/> OrganisatieManagement|
|Wachtwoord opnieuw instellen<sup>\*</sup>||Helpdesk <br/><br/> OrganisatieManagement <br/><br/> RecipientManagement|
|Retentiebeheer<sup>\*</sup>||ComplianceManagement <br/><br/> OrganisatieManagement <br/><br/> RecordsManagement RecordsManagement|
|Rolbeheer|Rolgroepen maken en beheren.|OrganisatieManagement|
|Beveiligingsbeheerder|Beheer de configuratie en rapporten voor alle beveiligings- en beveiligingsfuncties.|OrganisatieManagement <br/><br/> SecurityAdministrator (SecurityAdministrator) <br/><br/> ViewOnlyOrganizationManagement|
|Creatie en lidmaatschap van beveiligingsgroepen|Beveiligingsgroepen maken en beheren.|OrganisatieManagement|
|Beveiligingslezer|Bekijk de configuratie en rapporten voor beveiligings- en beveiligingsfuncties.|Organisatiebeheer <br/><br/> SecurityReader (SecurityReader) <br/><br/> ViewOnlyOrganizationManagement|
|Beheerder van gevoeligheidslabel<sup>\*</sup>||OrganisatieManagement <br/><br/> SecurityAdministrator (SecurityAdministrator) <br/><br/> ViewOnlyOrganizationManagement|
|Toezicht<sup>\*</sup>||OrganisatieManagement|
|Transporthygiëne|Beheer anti-malware, anti-spam functies, en anti-spoofing functies.|HygiëneBeheer <br/><br/> OrganisatieManagement|
|Vervoersregels|Regels voor e-mailstroom maken en beheren (ook wel transportregels genoemd).|OrganisatieManagement <br/><br/> RecordsManagement RecordsManagement|
|Gebruikersopties|Bestaande e-mailgebruikers wijzigen.|Helpdesk <br/><br/> OrganisatieManagement|
|View-Only AntiMalware|Bekijk de configuratie en rapporten voor anti-malware functies.|OrganisatieManagement <br/><br/> SecurityAdministrator (SecurityAdministrator) <br/><br/> SecurityReader (SecurityReader)|
|Alleen weergeven antispam|Bekijk de configuratie en rapporten voor antispamfuncties.|OrganisatieManagement <br/><br/> SecurityAdministrator (SecurityAdministrator) <br/><br/> SecurityReader (SecurityReader)|
|Alleen-weergave-controlelogboeken|Zoek in het controlelogboek van de beheerder en bekijk de resultaten.|ComplianceManagement <br/><br/> OrganisatieManagement <br/><br/> SecurityAdministrator (SecurityAdministrator)|
|Alleen-weergeven-configuratie|Bekijk alle instellingen voor de organisatie en e-mailstroom (niet-ontvanger) in de organisatie.|ComplianceManagement <br/><br/> HygiëneBeheer <br/><br/> OrganisatieManagement <br/><br/> ViewOnlyOrganizationManagement|
|Alleen weergeven quarantaine|Bekijk alle in quarantaine geplaatste berichten voor alle ontvangers.|OrganisatieManagement <br/><br/> SecurityAdministrator (SecurityAdministrator) <br/><br/> SecurityReader (SecurityReader)|
|Alleen-weergaveontvangers|Eigenschappen van geadresseerden weergeven en berichttracering uitvoeren.|ComplianceManagement <br/><br/> Helpdesk <br/><br/> HygiëneBeheer <br/><br/> MailFlowAdministrator <br/><br/>  OrganisatieManagement <br/><br/> ViewOnlyOrganizationManagement|
|Alleen-weergave bedreigingsinformatie<sup>\*</sup>||OrganisatieManagement <br/><br/> SecurityAdministrator (SecurityAdministrator) <br/><br/> SecurityReader (SecurityReader)|
|

<sup>\*</sup>Hoewel deze rol beschikbaar is, doet het in principe niets nuttigs in standalone EOP.

## <a name="microsoft-365-permissions-in-standalone-eop"></a>Microsoft 365-machtigingen in standalone EOP

Wanneer u een gebruiker maakt in het Microsoft 365-beheercentrum, u kiezen of u verschillende beheerdersrollen wilt toewijzen, zoals globale beheerder, servicebeheerder, wachtwoordbeheerder, enzovoort, aan de gebruiker. Sommige, maar niet alle, Microsoft 365-rollen verlenen de gebruiker beheerdersmachtigingen in EOP.

> [!NOTE]
> Het account dat u hebt gebruikt om uw zelfstandige EOP-organisatie te maken, wordt automatisch toegewezen aan de globale beheerrol.

In de volgende tabel worden de Microsoft 365-rollen en de zelfstandige EOP-rolgroepen weergegeven waarmee ze overeenkomen. Zie [Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)voor meer informatie over deze rollen .

|||
|---|---|
|**Microsoft 365-rol**|**EOP-rolgroep**|
|Exchange-beheerder|OrganisatieManagement|
|Algemene beheerder|OrganisatieManagement <br/><br/> **Opmerking:** De rol Globale beheerder en de rolgroep OrganizationManagement zijn met elkaar verbonden met behulp van een speciale rolgroep bedrijfsbeheerder. De rolgroep Bedrijfsbeheerder wordt intern beheerd en kan niet direct worden gewijzigd.|
|Wachtwoordbeheerder|Helpdesk|
|Algemene lezer|ViewOnlyOrganizationManagement|
|Beveiligingsbeheerder|SecurityAdministrator (SecurityAdministrator)|
|Beveiligingslezer|SecurityReader (SecurityReader)|
|

Andere Microsoft 365-rollen hebben geen bijbehorende EOP-rolgroep en verlenen geen administratieve machtigingen in EOP. Zie [Beheerdersrollen toewijzen](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles)voor meer informatie over het toewijzen van een Microsoft 365-rol aan een gebruiker.

Gebruikers kunnen beheerdersrechten krijgen in EOP zonder ze toe te voegen aan Microsoft 365-rollen. Dit doe je door de gebruiker toe te voegen als lid van een EOP-rolgroep. De gebruiker krijgt machtigingen in EOP, maar krijgt geen machtigingen in andere Microsoft 365-workloads.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Ga op een van de volgende stappen te werk om te controleren of u een rolgroep hebt gekopieerd:

- Ga in de EAC naar **Permissions** \> **Machtigingenbeheerdersrollen**en controleer of de rolgroep wordt weergegeven (of niet wordt vermeld). Selecteer de rolgroep en controleer de instellingen **Edit** in het deelvenster Details of klik op ![ Pictogram Bewerken bewerken om de instellingen te ](../../media/ITPro-EAC-EditIcon.png) verifiëren.

- Vervang in Exchange Online PowerShell \< de naam van de rolgroep door de naam van de \> rolgroep en voer de volgende opdracht uit om te controleren of de rolgroep bestaat (of bestaat niet) en controleer de instellingen:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
