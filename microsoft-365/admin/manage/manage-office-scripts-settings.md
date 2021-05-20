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
description: Meer informatie over het beheren van Office scriptsinstellingen voor gebruikers in uw organisatie.
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572307"
---
# <a name="manage-office-scripts-settings"></a>Instellingen voor Office-scripts beheren

[met Office Scripts](/office/dev/scripts)kunnen gebruikers taken automatiseren door scripts op te nemen, te bewerken en uit te voeren in Excel op het web. Office Scripts werken met Power Automate en gebruikers voeren scripts uit op werkmappen met behulp van de connector Excel Online (Business). Microsoft 365 beheerders kunnen Office scripts beheren vanuit het Microsoft 365-beheercentrum.

## <a name="before-you-begin"></a>Voordat u begint

- Als u Office scripts wilt beheren, moet u een globale beheerder zijn. Zie [Beheerdersrollen voor](../add-users/about-admin-roles.md)meer informatie.

- Zorg ervoor dat gebruikers in uw organisatie een geldige licentie hebben voor een Microsoft 365 of Office 365 commercieel of EDU-abonnement dat toegang bevat tot Office bureaublad-apps, zoals een van de volgende abonnementen:

    - Microsoft 365 Business Standard
    - Microsoft 365-apps voor bedrijven
    - Microsoft 365-apps voor ondernemingen
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>De beschikbaarheid van Office scripts beheren en scripts delen

1. Ga in het Microsoft 365-beheercentrum naar het tabblad **Instellingen** \> **Organisatie-instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services.</a>

2. Selecteer **Office scripts**.

3. Office Scripts zijn standaard ingeschakeld en iedereen in uw organisatie heeft toegang tot en kan de functie gebruiken en scripts delen. Als u Office scripts voor uw organisatie wilt uitschakelen, schakelt u het selectievakje **Gebruikers hun taken automatiseren in webversie van Excel** uit.

4. Als u eerder Office scripts voor uw organisatie hebt uitgeschakeld en u deze weer wilt inschakelen, selecteert u **Gebruikers hun taken laten automatiseren in webversie van Excel** en geeft u vervolgens op wie toegang heeft tot de functie en deze kan gebruiken:

    - Als u wilt dat alle gebruikers in uw organisatie toegang hebben tot en Office scripts gebruiken, laat u **Iedereen** (de standaardinstelling) geselecteerd.

    - Als u alleen leden van een specifieke groep toegang wilt geven tot en Office scripts wilt gebruiken, selecteert u **Specifieke groep** en voert u vervolgens de naam of e-mailalias van de groep in om deze toe te voegen aan de lijst met toegestane groepen. U kunt slechts één groep toevoegen aan de lijst met toegestane groepen en dit moet een van de volgende typen zijn:
        - Microsoft 365 groep
        - Distributiegroep
        - Beveiligingsgroep
        - Beveiligingsgroep met e-mail
    
        Zie Groepen vergelijken voor meer informatie over de verschillende typen [groepen.](../create-groups/compare-groups.md)

5. Als u gebruikers met toegang tot Office scripts hun scripts wilt laten delen met anderen in uw organisatie, selecteert u **Gebruikers met toegang tot Office scripts hun scripts delen met anderen in de organisatie**. Het delen van scripts buiten een organisatie is niet toegestaan.
 
    > [!NOTE]
    > Als u later het delen van scripts voor uw organisatie uitschakelt, kunnen gebruikers nog steeds eerder gedeelde scripts uitvoeren.
 
6. Geef op welke gebruikers met toegang tot Office scripts hun scripts kunnen delen:
    
    - Als u wilt dat alle gebruikers met toegang tot Office scripts hun scripts kunnen delen, laat u **Iedereen** (de standaardinstelling) geselecteerd.

    - Als u alleen leden van een specifieke groep met toegang tot Office scripts wilt toestaan hun scripts te delen, selecteert u **Specifieke groep** en voert u vervolgens de naam of e-mailalias van de groep in om deze toe te voegen aan de lijst met toegestane scripts. U kunt slechts één groep toevoegen aan de lijst met toegestane groepen en dit moet een van de volgende typen zijn:
        - Microsoft 365 groep
        - Distributiegroep
        - Beveiligingsgroep
        - Beveiligingsgroep met e-mail
    
        Zie Groepen vergelijken voor meer informatie over de verschillende typen [groepen.](../create-groups/compare-groups.md)

7. Als u wilt dat gebruikers hun Office scripts binnen Power Automate stromen kunnen uitvoeren, selecteert u **Gebruikers met toegang tot Office scripts hun scripts laten uitvoeren met Power Automate**. Hierdoor kunnen gebruikers stroomstappen toevoegen met de **scriptoptie** [Excel Online (Business) Connector.](/connectors/excelonlinebusiness)

    - Als u wilt dat alle gebruikers met toegang tot Office scripts hun scripts in stromen kunnen gebruiken, laat u **Iedereen** (de standaardinstelling) geselecteerd.

    - Als u alleen leden van een specifieke groep met toegang tot Office scripts wilt toestaan hun scripts in stromen te gebruiken, selecteert u **Specifieke groep** en voert u vervolgens de naam of e-mailalias van de groep in om deze toe te voegen aan de lijst met toegestane scripts. U kunt slechts één groep toevoegen aan de lijst met toegestane groepen en dit moet een van de volgende typen zijn:
        - Microsoft 365 groep
        - Distributiegroep
        - Beveiligingsgroep
        - Beveiligingsgroep met e-mail

        Zie Groepen vergelijken voor meer informatie over de verschillende typen [groepen.](../create-groups/compare-groups.md)

    - Zie Office scripts uitvoeren met Power Automate voor meer informatie over het gebruik [van Office scripts met Power Automate.](/office/dev/scripts/develop/power-automate-integration)

8. Selecteer **Opslaan**.

    Het kan tot 48 uur duren voordat wijzigingen in Office scripts-instellingen van kracht worden.

## <a name="next-steps"></a>Volgende stappen

Omdat Office Scripts met Power Automate werkt, raden we u aan uw bestaande DLP-beleid (Data Loss Prevention) te bekijken om ervoor te zorgen dat de gegevens van uw organisatie beschermd blijven terwijl gebruikers Office scripts gebruiken. Zie beleid voor [het voorkomen van gegevensverlies (DLP)](/power-automate/prevent-data-loss)voor meer informatie.

## <a name="related-content"></a>Verwante onderwerpen

[Office Scripts technische documentatie](/office/dev/scripts/) (linkpagina)\
[Inleiding tot Office scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artikel)\
[Office scripts delen in Excel voor het web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artikel)\
[Office scripts opnemen, bewerken en maken in webversie van Excel](/office/dev/scripts/tutorials/excel-tutorial) (artikel)
