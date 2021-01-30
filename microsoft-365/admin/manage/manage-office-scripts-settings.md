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
description: Informatie over het beheren van de instellingen voor Office-scripts voor gebruikers in uw organisatie.
ms.openlocfilehash: 75d0a9d9e98652fc11eab7e8a7d6c826be031f6e
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058421"
---
# <a name="manage-office-scripts-settings"></a>Instellingen voor Office-scripts beheren

Met Office-scripts kunnen gebruikers taken automatiseren door het opnemen, bewerken en uitvoeren van scripts in de webapp van Excel. Office-scripts werken met Power Automate en gebruikers voeren scripts uit op werkmappen met behulp van de connector van Excel Online (Bedrijven). Microsoft 365-beheerders kunnen de instellingen voor Office Scripts beheren vanuit het Microsoft 365-beheercentrum.

## <a name="before-you-begin"></a>Voordat u begint

- Als u de instellingen voor Office-scripts wilt beheren, moet u een globale beheerder zijn. Zie Informatie over [beheerdersrollen.](../add-users/about-admin-roles.md)

- Controleer of gebruikers in uw organisatie een geldige licentie hebben voor een commerciële of EDU-abonnement van Microsoft 365 of Office 365 met toegang tot Office-desktop-apps, zoals een van de volgende abonnementen:

    - Microsoft 365 Business Standard
    - Microsoft 365-apps voor bedrijven
    - Microsoft 365-apps voor ondernemingen
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>De beschikbaarheid van Office-scripts en het delen van scripts beheren

1. Ga in het Microsoft 365-beheercentrum naar het tabblad Instellingen  \> **organisatie-instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services.</a>

2. Selecteer **Office-scripts.**

3. Office-scripts is standaard ingeschakeld en iedereen in uw organisatie heeft toegang tot de functie en kan deze gebruiken en scripts delen. Als u Office-scripts voor uw organisatie wilt uitschakelen, schakel het selectievakje Gebruikers hun taken laten automatiseren **in de web-web-excel** uit.

4. Als u eerder Office-scripts hebt uitgeschakeld voor uw organisatie en u deze functie weer wilt in- of uitschakelen, selecteert u Gebruikers hun taken laten automatiseren **in de webwinkel** van Excel en geeft u op wie de functie kan openen en gebruiken:

    - Als u alle gebruikers in uw organisatie toegang wilt geven tot Office-scripts en deze wilt gebruiken, laat u **Iedereen** (de standaardinstelling) geselecteerd.

    - Als u wilt dat alleen leden van een bepaalde groep Office-scripts kunnen openen en gebruiken, selecteert u Specifieke groep en voert u de naam of e-mailalias van de groep in om deze toe te voegen aan de lijst toestaan. U mag slechts één groep toevoegen aan de toegestane lijst en dit moet een van de volgende typen zijn:
        - Microsoft 365-groep
        - Distributiegroep
        - Beveiligingsgroep
        - Beveiligingsgroep met e-mail
    
        Zie Groepen vergelijken voor meer informatie over de [verschillende typen groepen.](../create-groups/compare-groups.md)

5. Als u wilt dat gebruikers met toegang tot Office-scripts hun scripts kunnen delen met anderen in uw organisatie, selecteert u Toestaan dat gebruikers met toegang tot **Office-scripts** hun scripts delen met anderen in de organisatie. Scripts delen buiten een organisatie is niet toegestaan.
 
    > [!NOTE]
    > Als u het delen van scripts later uit schakelen voor uw organisatie, kunnen gebruikers nog steeds eerder gedeelde scripts uitvoeren.
 
6. Opgeven welke gebruikers met toegang tot Office-scripts hun scripts kunnen delen:
    
    - Als u wilt dat alle gebruikers met toegang tot Office-scripts hun scripts kunnen delen, laat u **Iedereen** (de standaardinstelling) geselecteerd.

    - Als u wilt dat alleen leden van een specifieke groep die toegang hebben tot Office-scripts hun scripts kunnen delen, selecteert u Groep Specifiek en voert u de naam of e-mailalias van de groep in om deze toe te voegen aan de lijst Toestaan. U mag slechts één groep toevoegen aan de toegestane lijst en dit moet een van de volgende typen zijn:
        - Microsoft 365-groep
        - Distributiegroep
        - Beveiligingsgroep
        - Beveiligingsgroep met e-mail
    
        Zie Groepen vergelijken voor meer informatie over de [verschillende typen groepen.](../create-groups/compare-groups.md)

7. Als u wilt dat gebruikers hun Office-scripts kunnen uitvoeren in Power Automate-stromen, selecteert u Toestaan dat gebruikers met toegang tot Office-scripts hun scripts uitvoeren **met Power Automate.** Hierdoor kunnen gebruikers stroomstappen toevoegen met de [scriptoptie](/connectors/excelonlinebusiness) Uitvoeren van de Excel **Online-connector** (Business).

    - Als u wilt dat alle gebruikers met toegang tot Office-scripts hun scripts kunnen gebruiken in stromen, laat u **Iedereen** (de standaardinstelling) geselecteerd.

    - Als u wilt dat alleen leden van een specifieke groep met toegang tot Office-scripts hun scripts kunnen gebruiken in stromen, selecteert u Groep Specifiek en voert u de naam of e-mailalias van de groep in om deze toe te voegen aan de lijst Toestaan. U mag slechts één groep toevoegen aan de toegestane lijst en dit moet een van de volgende typen zijn:
        - Microsoft 365-groep
        - Distributiegroep
        - Beveiligingsgroep
        - Beveiligingsgroep met e-mail

        Zie Groepen vergelijken voor meer informatie over de [verschillende typen groepen.](../create-groups/compare-groups.md)

    - Zie Office-scripts uitvoeren met Power Automate voor meer informatie over het gebruik van [Office-scripts met Power Automate,](/office/dev/scripts/develop/power-automate-integration)waaronder hoe uw beleid voor preventie van gegevensverlies kan worden beïnvloed.

8. Klik op **Opslaan**.

    Het kan tot 48 uur duren voordat wijzigingen in de instellingen voor Office-scripts zijn doorgevoerd.

## <a name="next-steps"></a>Volgende stappen

Omdat Office Scripts werkt met Power Automate, raden we u aan uw bestaande beleid voor preventie van gegevensverlies (DLP)-beleid te controleren om ervoor te zorgen dat de gegevens van uw organisatie beveiligd blijven wanneer gebruikers Office-scripts gebruiken. Zie het beleid voor preventie van [gegevensverlies (DLP-beleid) voor meer informatie.](/power-automate/prevent-data-loss)

## <a name="related-content"></a>Verwante onderwerpen

[Technische documentatie van Office Scripts](/office/dev/scripts/) (koppelingspagina)\
[Inleiding tot Office-scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artikel)\
[Office-scripts delen in excel voor het web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artikel)\
[Office-scripts opnemen, bewerken en maken in de webonderdeel Excel](/office/dev/scripts/tutorials/excel-tutorial) (artikel)
