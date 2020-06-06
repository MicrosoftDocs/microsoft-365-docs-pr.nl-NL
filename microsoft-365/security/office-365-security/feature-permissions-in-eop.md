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
ms.openlocfilehash: 0c3074789e439c3923667d37446733665fa79d88
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588250"
---
# <a name="permissions-in-standalone-eop"></a>Machtigingen in standalone EOP

Standalone Exchange Online Protection (EOP) zonder Exchange Online-postvakken gebruikt het machtigingenmodel Role Based Access Control (RBAC) om eenvoudig machtigingen aan uw beheerders te verlenen. U de machtigingsfuncties in standalone EOP gebruiken om uw nieuwe organisatie snel operationeel te krijgen.

Zie [Beheerdersrolgroepen beheren in EOP als](manage-admin-role-group-permissions-in-eop.md)u machtigingen wilt verlenen aan gebruikers.

Zie [Over beheerdersrollen voor](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)meer informatie over machtigingen in Microsoft 365.

## <a name="role-based-permissions"></a>Machtigingen op basis van rollen

De beheerdersmachtigingen die u aan gebruikers verleent, zijn gebaseerd op beheerrollen. Een beheerrol definieert de cmdlets die beschikbaar zijn voor een bepaalde taak. Omdat het Exchange-beheercentrum (EAC) en de zelfstandige EOP PowerShell beide cmdlets gebruiken, geeft het verlenen van toegang tot een cmdlet de gebruiker toestemming om de gerelateerde taken in de EAC of in standalone EOP PowerShell uit te voeren. De functie E-mailontvangers definieert bijvoorbeeld de cmdlets die nodig zijn om e-mailgebruikers te wijzigen.

In standalone EOP zijn beheerdersrollen het enige type beheerrol dat beschikbaar is (er zijn geen rollen voor eindgebruikers of taaktoewijzingsbeleid).

## <a name="role-groups"></a>Rolgroepen

Om het eenvoudiger te maken om rollen aan gebruikers toe te wijzen, maakt standalone EOP gebruik van rolgroepen. Beheerrollen worden toegewezen aan rolgroepen en de leden van de rolgroep krijgen de machtigingen die aan de rollen zijn gekoppeld. Met andere woorden, beheerrollen worden niet rechtstreeks toegewezen aan gebruikers; ze zijn toegewezen aan de rolgroep. Met dit model u veel rollen toewijzen aan veel leden van de rolgroep tegelijk. Leden van de functiegroep kunnen e-mailgebruikers, beveiligingsgroepen met e-mail, gebruikers van het Microsoft 365-beheercentrum en andere rolgroepen zijn.

De volgende afbeelding toont de relatie tussen gebruikers, rolgroepen en rollen.

![Relatie tussen rol, rollengroep en lid](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

De beschikbare rolgroepen in standalone EOP worden beschreven in de volgende tabel.

||||
|---|---|---|
|**Rolgroep**|**Beschrijving**|**Standaardrollen toegewezen**|
|ComplianceManagement|De nalevingsinstellingen binnen de organisatie configureren en beheren, waaronder DLP (Data Loss Prevention) als uw abonnement DLP-mogelijkheden heeft. <br/><br/> Leden van de functie [Compliance administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) in Azure AD krijgen automatisch de machtigingen van deze rolgroep.|Controlelogboeken <br/><br/> Nalevingsbeheer <br/><br/> Information Rights Management <br/><br/> Retentiebeheer <br/><br/> Controlelogboeken met alleen weergeven <br/><br/> Configuratie alleen weergeven <br/><br/> Ontvangers alleen weergeven|
|ContentExplorerContentViewer|Niet gebruikt.|Inhoudsviewer voor gegevensclassificatie|
|ContentExplorerListViewer|Niet gebruikt.|Viewer voor lijst met gegevensclassificatie|
|Helpdesk|E-mailgebruikers weergeven en beheren.|Wachtwoord opnieuw instellen <br/><br/> Gebruikersopties <br/><br/> Ontvangers alleen weergeven|
|HygieneManagement|Beveiligingsfuncties beheren (anti-spam, anti-malware, enz.).|Transporthygiëne <br/><br/> Configuratie alleen weergeven <br/><br/> Ontvangers alleen weergeven|
|MailFlowAdministrator|Geaccepteerde domeinen en connectoren weergeven en beheren|Externe en geaccepteerde domeinen <br/><br/> Ontvangers alleen weergeven|
|OrganisatieManagement|Admin toegang tot de hele organisatie en de mogelijkheid om bijna elke taak uit te voeren. <br/><br/> Leden van de rol [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) in Azure AD krijgen automatisch de machtigingen van deze rolgroep. <br/><br/> **Belangrijk**: Omdat de rolgroep Organisatiebeheer een krachtige rol is, moeten alleen gebruikers die administratieve taken op organisatieniveau uitvoeren, lid zijn van deze rolgroep.|Antimalware <br/><br/> Antispam <br/><br/> Controlelogboeken <br/><br/> Compliance-beheerder <br/><br/> Distributiegroepen <br/><br/> Information Rights Management <br/><br/> Aanmaak van e-mailontvanger <br/><br/> E-mailontvangers <br/><br/> Bericht bijhouden <br/><br/> Migratie <br/><br/> Toegang tot client van organisatie <br/><br/> Organisatieconfiguratie <br/><br/> Organisatietransportinstellingen <br/><br/> Quarantaine <br/><br/> Beleid voor geadresseerden <br/><br/> Externe en geaccepteerde domeinen <br/><br/> Wachtwoord opnieuw instellen <br/><br/> Retentiebeheer <br/><br/> Rolbeheer <br/><br/> Beveiligingsbeheerder <br/><br/> Creatie en lidmaatschap van beveiligingsgroepen <br/><br/> Beveiligingslezer <br/><br/> Gevoeligheidslabelbeheerder <br/><br/> Toezicht <br/><br/> Transporthygiëne <br/><br/> Vervoersregels <br/><br/> Gebruikersopties <br/><br/> Alleen-weergeven AntiMalware <br/><br/> AntiSpam alleen weergeven <br/><br/> Controlelogboeken met alleen weergeven <br/><br/> Configuratie alleen weergeven <br/><br/> Quarantaine alleen weergeven <br/><br/> Ontvangers alleen weergeven <br/><br/> Alleen-bekijkende bedreigingsinformatie|
|QuarantaineAdministratie|Berichten in quarantaine beheren voor alle ontvangers.|Quarantaine|
|Beheer van de ontvanger|Objecten van geadresseerden in de organisatie maken, beheren en verwijderen.|Distributiegroepen <br/><br/> Aanmaak van e-mailontvanger <br/><br/> E-mailontvangers <br/><br/> Bericht bijhouden <br/><br/> Migratie <br/><br/> Beleid voor geadresseerden <br/><br/> Wachtwoord opnieuw instellen|
|RecordsManagement|Nalevingsfuncties configureren, zoals retentiebeleidstags, berichtclassificaties en regels voor e-mailstroom (ook wel transportregels genoemd).|Bericht bijhouden <br/><br/> Retentiebeheer <br/><br/> Vervoersregels|
|SecurityAdministrator|Configureer alle aspecten van de bescherming in de organisatie (anti-spam, anti-malware, anti-spoofing, quarantaine, enz.). <br/><br/> Leden van de rol [Beveiligingsbeheerder](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) in Azure AD krijgen automatisch de machtigingen van deze rolgroep.|Antimalware <br/><br/> Antispam <br/><br/> Controlelogboeken <br/><br/> Quarantaine <br/><br/> Beveiligingsbeheerder <br/><br/> Gevoeligheidslabelbeheerder <br/><br/> Alleen-weergeven AntiMalware <br/><br/> AntiSpam alleen weergeven <br/><br/> Controlelogboeken met alleen weergeven <br/><br/> Quarantaine alleen weergeven <br/><br/> Alleen-bekijkende bedreigingsinformatie|
|SecurityReader (SecurityReader)|Alleen-weergeven toegang tot alle aspecten van bescherming in de organisatie (anti-spam, anti-malware, anti-spoofing, quarantaine, enz.). <br/><br/> Leden van de rol [Beveiligingslezer](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) in Azure AD krijgen automatisch de machtigingen van deze rolgroep.|Beveiligingslezer <br/><br/> Alleen-weergeven AntiMalware <br/><br/> AntiSpam alleen weergeven <br/><br/> Quarantaine alleen weergeven <br/><br/> Alleen-bekijkende bedreigingsinformatie|
|TenantAdmins|Het lidmaatschap van deze rolgroep wordt gesynchroniseerd tussen services en centraal beheerd. Standaard krijgt deze rolgroep geen rollen toegewezen. Het zal echter lid zijn van de rolgroep Organisatiebeheer en deze machtigingen erven.|geen|
|ViewOnlyOrganizationManagement|Objecten voor geadresseerden, beveiliging en configuratie weergeven en hun eigenschappen in de organisatie.|Compliance-beheerder <br/><br/> Beveiligingsbeheerder <br/><br/> Beveiligingslezer <br/><br/> Gevoeligheidslabelbeheerder <br/><br/> Configuratie alleen weergeven <br/><br/> Ontvangers alleen weergeven|
|

Als u in een kleine organisatie werkt met slechts een paar beheerders, moet u deze gebruikers mogelijk alleen toevoegen aan de rolgroep Organisatiebeheer en hoeft u mogelijk nooit de andere rolgroepen te gebruiken. Als u in een grotere organisatie werkt, hebt u mogelijk beheerders die specifieke taken uitvoeren, zoals de configuratie van de geadresseerden. In die gevallen u één beheerder toevoegen aan de rolgroep Ontvangerbeheer en een andere beheerder aan de rolgroep Organisatiebeheer. Deze beheerders kunnen vervolgens hun specifieke gebieden beheren, maar ze hebben geen machtigingen om gebieden te beheren waarvoor ze niet verantwoordelijk zijn.

Als de ingebouwde rolgroepen in Exchange Online niet overeenkomen met de functie van uw beheerders, u rolgroepen maken en rollen aan hen toevoegen. Zie [Rolgroepen beheren in zelfstandige EOP voor](manage-admin-role-group-permissions-in-eop.md)meer informatie.

## <a name="roles"></a>Rollen

De ingebouwde rollen die beschikbaar zijn in standalone EOP worden beschreven in de volgende tabel.

||||
|---|---|---|
|**Rol**|**Beschrijving**|**Standaardrolgroeptoewijzingen**|
|Antimalware|Bekijk en wijzig de configuratie en rapporten voor anti-malwarefuncties.|OrganisatieManagement <br/><br/> SecurityAdministrator|
|Antispam|Bekijk en wijzig de configuratie en rapporten voor antispamfuncties.|OrganisatieManagement <br/><br/> SecurityAdministrator|
|Controlelogboeken|Zoek in het controlelogboek van de beheerder en bekijk de resultaten.|ComplianceManagement <br/><br/> OrganisatieManagement <br/><br/> SecurityAdministrator|
|Compliance-beheerder<sup>\*</sup>||ComplianceManagement <br/><br/> OrganisatieManagement <br/><br/> ViewOnlyOrganizationManagement|
|Inhoudsviewer voor gegevensclassificatie<sup>\*</sup>||ContentExplorerContentViewer|
|Viewer voor lijst met gegevensclassificatie<sup>\*</sup>||
|Distributiegroepen|Maak en beheer alle distributiegroepen, beveiligingsgroepen met e-mail en leden.|OrganisatieManagement <br/><br/> Beheer van de ontvanger|
|Beheer van informatierechten<sup>\*</sup>||ComplianceManagement <br/><br/> OrganisatieManagement|
|Aanmaak van e-mailontvanger|E-mailgebruikers maken en verwijderen.|OrganisatieManagement <br/><br/> Beheer van de ontvanger|
|E-mailontvangers|Bestaande e-mailgebruikers wijzigen.|OrganisatieManagement <br/><br/> Beheer van de ontvanger|
|Bericht bijhouden<sup>\*</sup>||OrganisatieManagement <br/><br/> Beheer van de ontvanger <br/><br/> Records Management|
|Migratie<sup>\*</sup>||OrganisatieManagement <br/><br/> Beheer van de ontvanger|
|MyBaseOptions|Hiermee kunnen gebruikers hun eigen berichten in quarantaine bekijken. <br/><br/> Deze rol wordt automatisch toegewezen aan gebruikers en u deze niet handmatig toewijzen.|geen|
|Toegang tot client van organisatie<sup>\*</sup>||OrganisatieManagement|
|Organisatieconfiguratie|Rapporten bekijken.|OrganisatieManagement|
|Organisatietransportinstellingen<sup>\*</sup>||OrganisatieManagement|
|Quarantaine|Alle typen in quarantaine geplaatste berichten voor alle ontvangers beheren.|OrganisatieManagement <br/><br/> QuarantaineAdministratie <br/><br/> SecurityAdministrator|
|Beleid voor geadresseerden<sup>\*</sup>||OrganisatieManagement <br/><br/> Beheer van de ontvanger|
|Externe en geaccepteerde domeinen|Externe domeinen, geaccepteerde domeinen en connectoren beheren.|MailFlowAdministrator <br/><br/> OrganisatieManagement|
|Wachtwoord opnieuw instellen<sup>\*</sup>||Helpdesk <br/><br/> OrganisatieManagement <br/><br/> Beheer van de ontvanger|
|Retentiebeheer<sup>\*</sup>||ComplianceManagement <br/><br/> OrganisatieManagement <br/><br/> RecordsManagement|
|Rolbeheer|Rolgroepen maken en beheren.|OrganisatieManagement|
|Beveiligingsbeheerder|Beheer de configuratie en rapporten voor alle beveiligings- en beveiligingsfuncties.|OrganisatieManagement <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|Creatie en lidmaatschap van beveiligingsgroepen|Beveiligingsgroepen met e-mail maken en beheren.|OrganisatieManagement|
|Beveiligingslezer|Bekijk de configuratie en rapporten voor beveiligings- en beveiligingsfuncties.|Organisatiebeheer <br/><br/> SecurityReader (SecurityReader) <br/><br/> ViewOnlyOrganizationManagement|
|Gevoeligheidslabelbeheerder<sup>\*</sup>||OrganisatieManagement <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|Toezicht<sup>\*</sup>||OrganisatieManagement|
|Transporthygiëne|Beheer anti-malware, anti-spam functies en anti-spoofing functies.|HygieneManagement <br/><br/> OrganisatieManagement|
|Vervoersregels|Regels voor e-mailstroom maken en beheren (ook wel transportregels genoemd).|OrganisatieManagement <br/><br/> RecordsManagement|
|Gebruikersopties|Bestaande e-mailgebruikers wijzigen.|Helpdesk <br/><br/> OrganisatieManagement|
|Alleen-weergeven AntiMalware|Bekijk de configuratie en rapporten voor anti-malware functies.|OrganisatieManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader (SecurityReader)|
|AntiSpam alleen weergeven|Bekijk de configuratie en rapporten voor antispamfuncties.|OrganisatieManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader (SecurityReader)|
|Controlelogboeken met alleen weergeven|Zoek in het controlelogboek van de beheerder en bekijk de resultaten.|ComplianceManagement <br/><br/> OrganisatieManagement <br/><br/> SecurityAdministrator|
|Configuratie alleen weergeven|Alle instellingen voor organisatie en e-mailstroom (niet-geadresseerden) in de organisatie weergeven.|ComplianceManagement <br/><br/> HygieneManagement <br/><br/> OrganisatieManagement <br/><br/> ViewOnlyOrganizationManagement|
|Quarantaine alleen weergeven|Alle in quarantaine geplaatste berichten voor alle ontvangers weergeven.|OrganisatieManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader (SecurityReader)|
|Ontvangers alleen weergeven|De eigenschappen van geadresseerden weergeven en berichttracering uitvoeren.|ComplianceManagement <br/><br/> Helpdesk <br/><br/> HygieneManagement <br/><br/> MailFlowAdministrator <br/><br/>  OrganisatieManagement <br/><br/> ViewOnlyOrganizationManagement|
|Alleen-bekijkende bedreigingsinformatie<sup>\*</sup>||OrganisatieManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader (SecurityReader)|
|

<sup>\*</sup>Hoewel deze rol beschikbaar is, doet het in principe niets nuttigs in standalone EOP.

## <a name="microsoft-365-permissions-in-standalone-eop"></a>Microsoft 365-machtigingen in standalone EOP

Wanneer u een gebruiker maakt in het Microsoft 365-beheercentrum, u kiezen of u verschillende beheerdersrollen, zoals Global admin, Servicebeheer, Wachtwoordbeheerder enzovoort, aan de gebruiker wilt toewijzen. Sommige, maar niet alle, Microsoft 365-rollen verlenen de gebruikers beheerdersrechten in EOP.

> [!NOTE]
> Het account dat u hebt gebruikt om uw zelfstandige EOP-organisatie te maken, wordt automatisch toegewezen aan de algemene beheerdersrol.

In de volgende tabel worden de Microsoft 365-rollen en de zelfstandige EOP-rolgroepen weergegeven waarmee ze overeenkomen. Zie [Over beheerdersrollen voor](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)meer informatie over deze rollen.

|||
|---|---|
|**Microsoft 365 rol**|**EOP-rolgroep**|
|Exchange-beheerder|OrganisatieManagement|
|Algemene beheerder|OrganisatieManagement <br/><br/> **Opmerking:** de rol Global admin en de rolgroep Organisatiebeheer zijn aan elkaar gekoppeld met behulp van een speciale rolgroep bedrijfsbeheerder. De rolgroep Bedrijfsbeheerder wordt intern beheerd en kan niet rechtstreeks worden gewijzigd.|
|Wachtwoordbeheerder|Helpdesk|
|Algemene lezer|ViewOnlyOrganizationManagement|
|Beveiligingsbeheerder|SecurityAdministrator|
|Beveiligingslezer|SecurityReader (SecurityReader)|
|

Andere Microsoft 365-rollen hebben geen overeenkomstige EOP-rolgroep en verlenen geen beheerdersmachtigingen in EOP. Zie [Beheerdersrollen toewijzen](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)voor meer informatie over het toewijzen van een Microsoft 365-rol aan een gebruiker.

Gebruikers kunnen administratieve rechten krijgen in EOP zonder ze toe te voegen aan Microsoft 365-rollen. Dit doe je door de gebruiker toe te voegen als lid van een EOP-rolgroep. De gebruiker krijgt machtigingen in EOP, maar krijgt geen machtigingen in andere Microsoft 365-workloads.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u een rolgroep hebt gekopieerd, voert u een van de volgende stappen uit:

- Ga in de EAC naar **Beheerdersrollen machtigingen** \> **Admin Roles**en controleer of de rolgroep wordt vermeld (of niet wordt vermeld). Selecteer de rolgroep en verifieer de instellingen in het deelvenster Details of **klik** op pictogram Bewerken bewerken ![ om de instellingen te ](../../media/ITPro-EAC-EditIcon.png) verifiëren.

- Vervang in Exchange Online PowerShell \<Role Group Name\> de naam van de rolgroep en voer de volgende opdracht uit om te controleren of de rolgroep bestaat (of niet bestaat) en controleer de instellingen:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
