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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid: MET150
description: Meer informatie over het beheren Office scripts voor gebruikers in uw organisatie.
ms.openlocfilehash: fea50838cf1089b73a6af5bbf86d490293831085
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392669"
---
# <a name="manage-office-scripts-settings"></a>Instellingen voor Office-scripts beheren

[Office scripts](/office/dev/scripts)kunnen gebruikers taken automatiseren door scripts op te nemen, te bewerken en uit te voeren in Excel web. Office Scripts werken met Power Automate en gebruikers voeren scripts uit op werkmappen met behulp van Excel onlineconnector (Business). Microsoft 365 beheerders kunnen de Office scripts beheren vanaf de Microsoft 365-beheercentrum.

## <a name="before-you-begin"></a>Voordat u begint

- Als u de Office scripts wilt beheren, moet u een globale beheerder zijn. Zie Over beheerdersrollen [voor meer informatie.](../add-users/about-admin-roles.md)

- Zorg ervoor dat gebruikers in uw organisatie een geldige licentie hebben voor een Microsoft 365- of Office 365-commercieel of EDU-abonnement met toegang tot Office-bureaublad-apps, zoals een van de volgende abonnementen:

    - Microsoft 365 Business Standard
    - Microsoft 365-apps voor bedrijven
    - Microsoft 365-apps voor ondernemingen
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Beschikbaarheid van scripts Office en delen van scripts beheren

1. Ga in Microsoft 365-beheercentrum naar het tabblad **Instellingen** \> **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">services.</a>

2. Selecteer **Office scripts.**

3. Office Scripts zijn standaard ingeschakeld en iedereen in uw organisatie kan de functie openen en gebruiken en scripts delen. Als u Office scripts voor uw organisatie wilt uitschakelen, schakelt u het selectievakje Gebruikers hun taken laten automatiseren **in** webversie van Excel uit.

4. Als u eerder Office Scripts voor uw organisatie hebt uitgeschakeld en u deze opnieuw wilt in schakelen, selecteert u Gebruikers hun taken laten automatiseren **in webversie van Excel** en geeft u vervolgens op wie de functie kan openen en gebruiken:

    - Als u wilt dat alle gebruikers in uw organisatie toegang hebben tot en Office scripts gebruiken, laat u **Iedereen** (de standaardinstelling) geselecteerd.

    - Als u wilt dat alleen leden van een specifieke groep Office Scripts kunnen openen en gebruiken, selecteert u Specifieke groep **en** voert u vervolgens de naam of e-mailalias van de groep in om deze toe te voegen aan de lijst toestaan. U mag slechts één groep toevoegen aan de lijst toestaan en dit moet een van de volgende typen zijn:
        - Microsoft 365 groep
        - Distributiegroep
        - Beveiligingsgroep
        - Beveiligingsgroep met e-mail
    
        Zie Groepen vergelijken voor meer informatie over de verschillende typen [groepen.](../create-groups/compare-groups.md)

5. Als u gebruikers met toegang tot Office Scripts wilt toestaan hun scripts te delen met anderen in uw organisatie, selecteert u Gebruikers met toegang tot Office Scripts toestaan hun scripts te delen met anderen in de **organisatie.** Scripts delen buiten een organisatie is niet toegestaan.
 
    > [!NOTE]
    > Als u later het delen van scripts voor uw organisatie uit zet, kunnen gebruikers nog steeds eerder gedeelde scripts uitvoeren.
 
6. Geef op welke gebruikers met toegang tot Office scripts hun scripts kunnen delen:
    
    - Als u wilt dat alle gebruikers met toegang Office scripts om hun scripts te delen, laat u **Iedereen** (de standaardinstelling) geselecteerd.

    - Als u wilt dat alleen leden van een specifieke groep met toegang tot Office Scripts hun scripts kunnen delen, selecteert u Specifieke groep **en** voert u vervolgens de naam of e-mailalias van de groep in om deze toe te voegen aan de lijst toestaan. U mag slechts één groep toevoegen aan de lijst toestaan en dit moet een van de volgende typen zijn:
        - Microsoft 365 groep
        - Distributiegroep
        - Beveiligingsgroep
        - Beveiligingsgroep met e-mail
    
        Zie Groepen vergelijken voor meer informatie over de verschillende typen [groepen.](../create-groups/compare-groups.md)

7. Als u wilt dat gebruikers hun Office scripts kunnen uitvoeren in Power Automate stromen, selecteert u Gebruikers met toegang tot Office Scripts hun scripts laten uitvoeren **met Power Automate.** Hierdoor kunnen gebruikers stroomstappen toevoegen met de optie uitvoeren [van Excel onlineconnector (Business)](/connectors/excelonlinebusiness) **Connector.**

    - Als u alle gebruikers met toegang tot Office scripts wilt toestaan om hun scripts in stromen te gebruiken, laat u **Iedereen** (de standaardinstelling) geselecteerd.

    - Als u wilt dat alleen leden van een specifieke groep met toegang tot Office Scripts hun scripts kunnen gebruiken in stromen, selecteert u Specifieke groep **en** voert u vervolgens de naam of e-mailalias van de groep in om deze toe te voegen aan de lijst toestaan. U mag slechts één groep toevoegen aan de lijst toestaan en dit moet een van de volgende typen zijn:
        - Microsoft 365 groep
        - Distributiegroep
        - Beveiligingsgroep
        - Beveiligingsgroep met e-mail

        Zie Groepen vergelijken voor meer informatie over de verschillende typen [groepen.](../create-groups/compare-groups.md)

    - Zie Office scripts uitvoeren met Power Automate voor meer informatie over het gebruik van Office [scripts met Power Automate](/office/dev/scripts/develop/power-automate-integration)scripts.

8. Kies **Opslaan**.

    Het kan tot 48 uur duren voordat wijzigingen in de Office scripts worden doorgevoerd.

## <a name="next-steps"></a>Volgende stappen

Omdat Office Scripts werkt met Power Automate, raden we u aan uw bestaande DLP-beleid (Data Loss Prevention) te bekijken om ervoor te zorgen dat de gegevens van uw organisatie beveiligd blijven terwijl gebruikers scripts Office gebruiken. Zie [DLP-beleid (Data Loss Prevention) voor meer informatie.](/power-automate/prevent-data-loss)

## <a name="related-content"></a>Verwante inhoud

[Office Scripts technische documentatie](/office/dev/scripts/) (koppelingspagina)\
[Inleiding tot Office scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artikel)\
[Scripts Office delen in Excel web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artikel)\
[Scripts opnemen, bewerken](/office/dev/scripts/tutorials/excel-tutorial) en Office maken in webversie van Excel (artikel)
