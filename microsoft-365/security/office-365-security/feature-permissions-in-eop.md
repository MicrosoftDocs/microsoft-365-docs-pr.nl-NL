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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Meer informatie over de machtigingen die vereist zijn voor taken op zelfstandige Exchange Online Protection
ms.openlocfilehash: f9c0f0549ba5a0a65fa3bbe3af1afbfddc6e735c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826623"
---
# <a name="permissions-in-standalone-eop"></a>Machtigingen in standalone EOP

Standalone Exchange Online Protection (EOP) en Exchange Online-postvakken gebruiken het machtigings model voor rollen gebaseerd toegangsbeheer. U kunt de machtigings functies van zelfstandige EOP gebruiken om snel aan de slag te gaan met uw nieuwe organisatie.

Zie [groepen met beheerdersrollen beheren in EOP](manage-admin-role-group-permissions-in-eop.md)als u machtigingen wilt verlenen aan gebruikers.

Zie [informatie over beheerders](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)voor meer informatie over machtigingen in microsoft 365.

## <a name="role-based-permissions"></a>Machtigingen op basis van rollen

De beheerdersmachtigingen die u aan gebruikers toewijst, zijn gebaseerd op management rollen. Een management functie definieert welke cmdlets beschikbaar zijn voor een set bepaalde taken. Aangezien het Exchange-Beheercentrum en zelfstandige EOP met behulp van cmdlets, het verlenen van toegang aan een cmdlet, gebruikers machtigen voor het uitvoeren van de gerelateerde taken in het Exchange-Beheercentrum of in een zelfstandige EOP-PowerShell. De rol e-mail geadresseerden definieert bijvoorbeeld de cmdlets die zijn vereist voor het wijzigen van e-mail gebruikers.

Bij zelfstandige EOP zijn beheerdersrollen het enige type Management-rol dat beschikbaar is (er zijn geen rollen voor eindgebruikers of beleidstoewijzingen voor rollen).

## <a name="role-groups"></a>Rollen groepen

Om het gemakkelijker te maken om rollen aan gebruikers toe te wijzen, maakt zelfstandige EOP gebruik van rollen groepen. Er worden management rollen toegewezen aan rollen groepen en de leden van de rollen groep krijgen de machtigingen die aan de rollen zijn gekoppeld. Met andere woorden worden management rollen niet rechtstreeks aan gebruikers toegewezen; de persoon wordt toegewezen aan een rollen groep. Met dit model kunt u een groot aantal rollen toewijzen aan een groot aantal leden van rollen groepen tegelijk. Leden van rollen groepen kunnen e-mail gebruikers zijn, beveiligingsgroepen met e-mail, gebruikers van het Microsoft 365-Beheercentrum en andere rollen groepen.

In de volgende afbeelding ziet u de relatie tussen gebruikers, rollen groepen en rollen.

![Relatie tussen rol, rollengroep en lid](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

In de volgende tabel vindt u een beschrijving van de beschikbare groepen met rollen in zelfstandige EOP.

****

|Rollen groep|Beschrijving|Standaardrollen toegewezen|
|---|---|---|
|ComplianceManagement|Compliance Settings binnen de organisatie configureren en beheren, waaronder preventie van gegevensverlies (DLP) als uw abonnement DLP-mogelijkheden heeft. <br/><br/> Leden van de rol [beheerder voor compliance](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) in azure AD krijgen automatisch de machtigingen van deze rollen groep.|Controlelogboeken <br/><br/> Nalevings beheer <br/><br/> Information Rights Management <br/><br/> Bewaar beheer <br/><br/> Alleen-lezen audit logboeken <br/><br/> Alleen-weergeven configuratie <br/><br/> Geadresseerden voor alleen weergeven|
|ContentExplorerContentViewer|Niet gebruikt.|Inhoudsweergave van gegevens classificaties|
|ContentExplorerListViewer|Niet gebruikt.|Gegevensclassificatie lijst viewer|
|Desk|E-mail gebruikers weergeven en beheren.|Wachtwoord opnieuw instellen <br/><br/> Gebruikersopties <br/><br/> Geadresseerden voor alleen weergeven|
|HygieneManagement|Beveiligingsfuncties beheren (antispam, anti-malware, enzovoort).|Vervoers hygiëne <br/><br/> Alleen-weergeven configuratie <br/><br/> Geadresseerden voor alleen weergeven|
|MailFlowAdministrator|Geaccepteerde domeinen en connectors weergeven en beheren|Externe en geaccepteerde domeinen <br/><br/> Geadresseerden voor alleen weergeven|
|De organizationmanagement|Beheerderstoegang tot de hele organisatie en de mogelijkheid om vrijwel alle taken uit te voeren. <br/><br/> Leden van de [globale beheerdersrol](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) in azure AD krijgen automatisch de machtigingen van deze rolgroep. <br/><br/> **Belangrijk**: aangezien de rollen groep de organizationmanagement een krachtige rol is, kunnen alleen gebruikers die beheertaken op de organisatie toepassen, lid worden van deze rollen groep.|AntiMalware <br/><br/> Spam <br/><br/> Controlelogboeken <br/><br/> Beheerder voor naleving <br/><br/> Distributiegroepen <br/><br/> Information Rights Management <br/><br/> E-mail adressen maken <br/><br/> Geadresseerden voor e-mail <br/><br/> Berichten traceren <br/><br/> Migratie <br/><br/> Client toegang voor organisatie <br/><br/> Organisatie configuratie <br/><br/> Instellingen voor organisatie transport <br/><br/> Quarantaine <br/><br/> Beleidsregels voor geadresseerden <br/><br/> Externe en geaccepteerde domeinen <br/><br/> Wachtwoord opnieuw instellen <br/><br/> Bewaar beheer <br/><br/> Rollenbeheer <br/><br/> Beveiligingsbeheerder <br/><br/> Maken en lidmaatschap van beveiligingsgroepen <br/><br/> Beveiligings lezer <br/><br/> De beheerder van het vertrouwelijkheids label <br/><br/> Op <br/><br/> Vervoers hygiëne <br/><br/> Transport regels <br/><br/> Gebruikersopties <br/><br/> Alleen-lezen antimalware <br/><br/> Alleen-weergeven-spam <br/><br/> Alleen-lezen audit logboeken <br/><br/> Alleen-weergeven configuratie <br/><br/> Alleen-weergeven, Quarantine <br/><br/> Geadresseerden voor alleen weergeven <br/><br/> Voorbeeld van bedreigings informatie|
|QuarantineAdministrator|Berichten in quarantaine beheren voor alle geadresseerden.|Quarantaine|
|RecipientManagement|U kunt objecten van de geadresseerde maken, beheren en verwijderen in de organisatie.|Distributiegroepen <br/><br/> E-mail adressen maken <br/><br/> Geadresseerden voor e-mail <br/><br/> Berichten traceren <br/><br/> Migratie <br/><br/> Beleidsregels voor geadresseerden <br/><br/> Wachtwoord opnieuw instellen|
|RecordsManagement|Functies voor compliance configureren, zoals bewaarbeleid-Tags, bericht classificaties en e-mail stroom regels (ook wel een transportregel genoemd).|Berichten traceren <br/><br/> Bewaar beheer <br/><br/> Transport regels|
|SecurityAdministrator|Alle aspecten van bescherming in de organisatie configureren (antispam, anti-malware, anti-spoofing, Quarantine, enzovoort). <br/><br/> Leden van de rol [beveiligingsbeheerder](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) in azure AD krijgen automatisch de machtigingen van deze rolgroep.|AntiMalware <br/><br/> Spam <br/><br/> Controlelogboeken <br/><br/> Quarantaine <br/><br/> Beveiligingsbeheerder <br/><br/> De beheerder van het vertrouwelijkheids label <br/><br/> Alleen-lezen antimalware <br/><br/> Alleen-weergeven-spam <br/><br/> Alleen-lezen audit logboeken <br/><br/> Alleen-weergeven, Quarantine <br/><br/> Voorbeeld van bedreigings informatie|
|SecurityReader|Alleen-lezen toegang tot alle aspecten van bescherming binnen de organisatie (antispam, anti-malware, en dergelijke). <br/><br/> Leden van de rol [beveiligings lezer](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) in azure AD krijgen automatisch de machtigingen van deze rollen groep.|Beveiligings lezer <br/><br/> Alleen-lezen antimalware <br/><br/> Alleen-weergeven-spam <br/><br/> Alleen-weergeven, Quarantine <br/><br/> Voorbeeld van bedreigings informatie|
|TenantAdmins|Lidmaatschap van deze rollen groep wordt gesynchroniseerd in Services en centraal beheerd. Aan deze rollen groep is standaard geen rollen toegewezen. Het is echter lid van de rollen groep Organisatiebeheer en neemt deze machtigingen over.|geen|
|ViewOnlyOrganizationManagement|De instellingen voor de ontvanger, de bescherming en de configuratie van objecten en hun eigenschappen in de organisatie weergeven.|Beheerder voor naleving <br/><br/> Beveiligingsbeheerder <br/><br/> Beveiligings lezer <br/><br/> De beheerder van het vertrouwelijkheids label <br/><br/> Alleen-weergeven configuratie <br/><br/> Geadresseerden voor alleen weergeven|
|

Als u in een kleine organisatie werkt die slechts een paar beheerders bevat, moet u die gebruikers mogelijk alleen toevoegen aan de rollen groep voor Organisatiebeheer en hoeft u de andere rollen groepen wellicht nooit te gebruiken. Als u in een grotere organisatie werkt, hebt u mogelijk beheerders die specifieke taken uitvoeren, zoals de configuratie van de ontvanger. In deze gevallen voegt u één beheerder toe aan de rollen groep beheerder van de ontvanger en een andere beheerder aan de rollen groep Organisatiebeheer. Deze beheerders kunnen vervolgens hun specifieke gebieden beheren, maar ze hebben geen machtigingen voor het beheren van gebieden waarvan ze niet verantwoordelijk zijn.

Als de ingebouwde Rolgroepen in Exchange Online niet overeenkomen met de taakfunctie van de beheerders, kunt u Rolgroepen maken en rollen toevoegen aan de groepen. Zie [rollen groepen beheren in zelfstandige EOP](manage-admin-role-group-permissions-in-eop.md)voor meer informatie.

## <a name="roles"></a>Vervullen

In de volgende tabel worden de ingebouwde rollen beschreven die beschikbaar zijn in een zelfstandige EOP.

****

|Rollen * *|Beschrijving|Standaardtoewijzingen van rollen groepen|
|---|---|---|
|AntiMalware|De configuratie en rapporten voor functies met anti-malware weergeven en wijzigen.|De organizationmanagement <br/><br/> SecurityAdministrator|
|Spam|De configuratie en rapporten voor antispam functies weergeven en wijzigen.|De organizationmanagement <br/><br/> SecurityAdministrator|
|Controlelogboeken|Zoek het controlelogboek van de beheerder en Bekijk de resultaten.|ComplianceManagement <br/><br/> De organizationmanagement <br/><br/> SecurityAdministrator|
|Beheerder voor naleving<sup>\*</sup>||ComplianceManagement <br/><br/> De organizationmanagement <br/><br/> ViewOnlyOrganizationManagement|
|Inhoudsweergave van gegevens classificaties<sup>\*</sup>||ContentExplorerContentViewer|
|Gegevensclassificatie lijst viewer<sup>\*</sup>||
|Distributiegroepen|U kunt alle distributiegroepen, beveiligingsgroepen met e-mail en leden maken en beheren.|De organizationmanagement <br/><br/> RecipientManagement|
|IRM (Information Rights Management)<sup>\*</sup>||ComplianceManagement <br/><br/> De organizationmanagement|
|E-mail adressen maken|E-mail gebruikers maken en verwijderen.|De organizationmanagement <br/><br/> RecipientManagement|
|Geadresseerden voor e-mail|Bestaande e-mail gebruikers wijzigen.|De organizationmanagement <br/><br/> RecipientManagement|
|Berichten traceren<sup>\*</sup>||De organizationmanagement <br/><br/> RecipientManagement <br/><br/> Recordbeheer|
|Livemigraties<sup>\*</sup>||De organizationmanagement <br/><br/> RecipientManagement|
|MyBaseOptions|Gebruikers in staat stellen hun eigen berichten in quarantaine weer te geven. <br/><br/> Deze rol wordt automatisch toegewezen aan gebruikers en u kunt deze niet handmatig toewijzen.|geen|
|Client toegang voor organisatie<sup>\*</sup>||De organizationmanagement|
|Organisatie configuratie|Rapporten bekijken.|De organizationmanagement|
|Instellingen voor organisatie transport<sup>\*</sup>||De organizationmanagement|
|Quarantaine|Alle typen quarantaine berichten beheren voor alle geadresseerden.|De organizationmanagement <br/><br/> QuarantineAdministrator <br/><br/> SecurityAdministrator|
|Beleidsregels voor geadresseerden<sup>\*</sup>||De organizationmanagement <br/><br/> RecipientManagement|
|Externe en geaccepteerde domeinen|Beheer externe domeinen, geaccepteerde domeinen en connectors.|MailFlowAdministrator <br/><br/> De organizationmanagement|
|Wachtwoord opnieuw instellen<sup>\*</sup>||Desk <br/><br/> De organizationmanagement <br/><br/> RecipientManagement|
|Bewaar beheer<sup>\*</sup>||ComplianceManagement <br/><br/> De organizationmanagement <br/><br/> RecordsManagement|
|Rollenbeheer|Rollen groepen maken en beheren.|De organizationmanagement|
|Beveiligingsbeheerder|Beheer de configuratie en rapporten voor alle functies voor beveiliging en beveiliging.|De organizationmanagement <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|Maken en lidmaatschap van beveiligingsgroepen|Beveiligingsgroepen met e-mail maken en beheren.|De organizationmanagement|
|Beveiligings lezer|De configuratie en rapporten voor beveiligings-en beveiligingsfuncties weergeven.|Organisatiebeheer <br/><br/> SecurityReader <br/><br/> ViewOnlyOrganizationManagement|
|De beheerder van het vertrouwelijkheids label<sup>\*</sup>||De organizationmanagement <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|Op<sup>\*</sup>||De organizationmanagement|
|Vervoers hygiëne|U kunt anti malware, antispam functies en anti-spoofings functies beheren.|HygieneManagement <br/><br/> De organizationmanagement|
|Transport regels|Het maken en beheren van e-mail stroom regels (ook wel een zogenaamde transportregels genoemd).|De organizationmanagement <br/><br/> RecordsManagement|
|Gebruikersopties|Bestaande e-mail gebruikers wijzigen.|Desk <br/><br/> De organizationmanagement|
|Alleen-lezen antimalware|De configuratie en rapporten voor functies met anti-malware weergeven.|De organizationmanagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|Alleen-weergeven-spam|De configuratie en rapporten voor antispam functies weergeven.|De organizationmanagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|Alleen-lezen audit logboeken|Zoek het controlelogboek van de beheerder en Bekijk de resultaten.|ComplianceManagement <br/><br/> De organizationmanagement <br/><br/> SecurityAdministrator|
|Alleen-weergeven configuratie|Bekijk de instellingen voor de organisatie en de e-mail stroom (geen geadresseerden) in de organisatie.|ComplianceManagement <br/><br/> HygieneManagement <br/><br/> De organizationmanagement <br/><br/> ViewOnlyOrganizationManagement|
|Alleen-weergeven, Quarantine|Alle berichten in quarantaine weergeven voor alle geadresseerden.|De organizationmanagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|Geadresseerden voor alleen weergeven|De eigenschappen van de geadresseerde bekijken en de bericht tracering uitvoeren.|ComplianceManagement <br/><br/> Desk <br/><br/> HygieneManagement <br/><br/> MailFlowAdministrator <br/><br/>  De organizationmanagement <br/><br/> ViewOnlyOrganizationManagement|
|Voorbeeld van bedreigings informatie<sup>\*</sup>||De organizationmanagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|

<sup>\*</sup> Hoewel deze functie beschikbaar is, kunt u de functie eigenlijk niet gebruiken in een zelfstandige EOP.

## <a name="microsoft-365-permissions-in-standalone-eop"></a>Microsoft 365-machtigingen in zelfstandige EOP

Wanneer u een gebruiker maakt in het Microsoft 365-Beheercentrum, kunt u kiezen of u verschillende beheerdersrollen, zoals globale beheerder, service beheerder, wachtwoordbeheerder, enzovoort, aan de gebruiker wilt toewijzen. Met een aantal, maar niet alle Microsoft 365-rollen beschikt u over de beheerdersmachtigingen voor de gebruiker in EOP.

> [!NOTE]
> Het account dat u hebt gebruikt voor het maken van een zelfstandige EOP organisatie, wordt automatisch toegewezen aan de rol van globale beheerder.

In de volgende tabel vindt u de Microsoft 365-rollen en de EOP van de zelfstandige rollen waarmee ze corresponderen. Zie voor meer informatie over deze rollen [beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

****

|Microsoft 365-rol|Rollen groep EOP|
|---|---|
|Exchange-beheerder|De organizationmanagement|
|Algemene beheerder|De organizationmanagement <br/><br/> **Opmerking**: de rol van globale beheerder en de rollen groep de organizationmanagement zijn samen gekoppeld met behulp van een speciale rollen groep voor bedrijfsbeheerders. De rollen groep bedrijfsbeheerder wordt intern beheerd en kan niet rechtstreeks worden gewijzigd.|
|Wachtwoordbeheerder|Desk|
|Algemene lezer|ViewOnlyOrganizationManagement|
|Beveiligingsbeheerder|SecurityAdministrator|
|Beveiligingslezer|SecurityReader|
|

Andere Microsoft 365-rollen hebben geen bijbehorende rollen groep voor EOP en geven geen beheerdersmachtigingen in EOP. Zie [beheerdersrollen toewijzen](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)voor meer informatie over het toewijzen van een microsoft 365-rol aan een gebruiker.

Gebruikers kunnen beheerdersrechten krijgen in EOP zonder ze toe te voegen aan Microsoft 365-rollen. Dit doet u door de gebruiker toe te voegen als lid van een EOP-rollen groep. De gebruiker krijgt machtigingen in EOP, maar krijgt geen toegang via andere Microsoft 365-belastingen.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Voer een van de volgende stappen uit om te controleren of u een rollen groep hebt gekopieerd:

- Ga in het Exchange-Beheercentrum naar **machtigingen** \> **beheerders**en controleer of de rollen groep wel of niet wordt weergegeven. Selecteer de groep rollen, Controleer de instellingen in het detailvenster of klik op **Edit** ![ bewerkingspictogram bewerken ](../../media/ITPro-EAC-EditIcon.png) om de instellingen te controleren.

- In Exchange Online PowerShell vervangt u \<Role Group Name\> de naam van de rolgroep en voert u de volgende opdracht uit om te controleren of de rollen groep bestaat (of niet bestaat) en controleert u de instellingen:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
