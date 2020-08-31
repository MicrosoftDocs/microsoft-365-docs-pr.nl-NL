---
title: Instellingen voor Office-scripts beheren
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Meer informatie over het beheren van de instellingen van Office-scripts voor gebruikers in uw organisatie.
ms.openlocfilehash: 12a80f277f6d17a8e7f5228f6948e70b7a93be11
ms.sourcegitcommit: 97ef8f846939c3d31bb0638edf07bb89463ace0b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300829"
---
# <a name="manage-office-scripts-settings"></a>Instellingen voor Office-scripts beheren

Met Office-scripts kunnen gebruikers taken automatiseren door scripts op te nemen, te bewerken en uit te voeren in de webversie van Excel. Office-scripts werken met geautomatiseerde gebruikersfuncties en gebruikers uitvoeren scripts voor werkmappen met behulp van de Business-Connector (Business) van Excel online. Microsoft 365-beheerders kunnen instellingen voor Office-scripts beheren via het Microsoft 365-Beheercentrum.

## <a name="before-you-begin"></a>Voordat u begint

- Voor het beheren van instellingen voor Office-scripts moet u een globale beheerder zijn. Zie voor meer informatie [beheerdersrollen](../add-users/about-admin-roles.md).

- Zorg ervoor dat gebruikers in uw organisatie een geldige licentie hebben voor een commercieel of onderwijs abonnement voor Microsoft 365 of Office 365 dat toegang heeft tot Office-bureaubladtoepassingen, zoals een van de volgende abonnementen:

    - Microsoft 365 Business Standard
    - Microsoft 365-apps voor bedrijven
    - Microsoft 365-apps voor ondernemingen
    - Office 365 E3
    - Office 365 E5
    - Office 365 a3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>De beschikbaarheid van Office-scripts en het delen van scripts beheren

1. Ga in het Microsoft 365-Beheercentrum naar **het** \> tabblad Services van de organisatie- **instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> .

2. Selecteer **Office-scripts**.

3. Office-scripts is standaard ingeschakeld en iedereen in uw organisatie kan de functie openen en gebruiken en scripts delen. Als u Office-scripts voor uw organisatie wilt uitschakelen, schakelt u het selectievakje **gebruikers hun taken laten automatiseren in Excel op het web** uit.

4. Als u Office-scripts eerder voor uw organisatie hebt uitgeschakeld en u deze weer wilt inschakelen, selecteert u **gebruikers toestaan hun taken te laten automatiseren in de webversie van Excel**en geeft u vervolgens de personen die de functie kunnen openen en gebruiken:

    - Als u alle gebruikers in uw organisatie in staat wilt stellen Office-scripts te openen en gebruiken, laat u **iedereen** (de standaardinstelling) geselecteerd. 

    - Als u wilt dat alleen leden van een bepaalde groep Office-scripts kunnen openen en gebruiken, selecteert u **specifieke groep**en voert u de naam of e-mail alias van de groep in om deze toe te voegen aan de lijst toestaan. U kunt slechts één groep toevoegen aan de toegestane lijst en moet een van de volgende typen zijn:
        - Microsoft 365-groep
        - Distributiegroep
        - Beveiligingsgroep
        - Beveiligingsgroep met e-mail
    
        Zie [Groepen vergelijken](../create-groups/compare-groups.md)voor meer informatie over de verschillende soorten groepen.

5. Als u wilt dat gebruikers toegang hebben tot Office-scripts waarmee hun scripts met andere personen in uw organisatie kunnen worden gedeeld, schakelt u **gebruikers met toegang tot Office-scripts toestaan hun scripts met andere personen in de organisatie**te delen. Het delen van scripts buiten een organisatie is niet toegestaan.
 
    > [!NOTE]
    > Als u het delen van scripts later uitschakelt voor uw organisatie, kunnen gebruikers eerder eerder gedeelde scripts uitvoeren.
 
6. Opgeven welke gebruikers toegang hebben tot Office-scripts hun scripts kunnen delen:
    
    - Als u wilt dat alle gebruikers met toegang tot Office-scripts hun scripts kunnen delen, laat u **iedereen** (de standaardinstelling) geselecteerd.

    - Als u wilt dat alleen leden van een bepaalde groep toegang hebben tot Office-scripts om hun scripts te delen, selecteert u **specifieke groep**en voert u de naam of het e-mail alias van de groep in om deze toe te voegen aan de lijst toestaan. U kunt slechts één groep toevoegen aan de toegestane lijst en moet een van de volgende typen zijn:
        - Microsoft 365-groep
        - Distributiegroep
        - Beveiligingsgroep
        - Beveiligingsgroep met e-mail
    
        Zie [Groepen vergelijken](../create-groups/compare-groups.md)voor meer informatie over de verschillende soorten groepen.

7. Kies **Opslaan**.

    Het kan tot 48 uur duren voordat wijzigingen in de instellingen van het Office-script worden doorgevoerd.

## <a name="next-steps"></a>Volgende stappen

Aangezien Office-scripts met automatisering werken, is het raadzaam om uw bestaande DLP-beleidsregels (preventie van gegevensverlies) te controleren om ervoor te zorgen dat de gegevens van uw organisatie worden beveiligd wanneer gebruikers Office-scripts gebruiken. Zie [DLP-beleid (preventie van gegevensverlies)](/power-automate/prevent-data-loss)voor meer informatie.

## <a name="related-content"></a>Verwante onderwerpen

[Technische documentatie voor Office-scripts](/office/dev/scripts/) (koppelings pagina) \
[Inleiding tot Office-scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artikel) \
[Office-scripts delen in Excel voor het web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artikel) \
[Office-scripts opnemen, bewerken en maken in de webversie van Excel](/office/dev/scripts/tutorials/excel-tutorial) (artikel)