---
title: Licenties van gebruikers verwijderen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Meer informatie over het verwijderen van licenties van gebruikersaccounts.
ms.date: 07/01/2020
ms.openlocfilehash: 858daaf0069ecba3e6ff65ce957462764b45c22c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915192"
---
# <a name="unassign-licenses-from-users"></a>Licenties van gebruikers verwijderen

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

::: moniker range="o365-worldwide"

U kunt licenties van gebruikers op  de pagina Actieve gebruikers of op de pagina **Licenties verwijderen.** De methode die u gebruikt, is afhankelijk van of u productlicenties van specifieke gebruikers wilt inleveren of gebruikerslicenties van een bepaald product wilt inleveren.

::: moniker-end

## <a name="before-you-begin"></a>Voordat u begint

- U moet een globale, licentie- en gebruikersbeheerder zijn om licenties te ontlenen. Zie [Over beheerdersrollen in Microsoft 365](../add-users/about-admin-roles.md) voor meer informatie.
- U kunt [licenties van gebruikersaccounts intrekken met Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).
- U kunt ook [gebruikersaccounts verwijderen](../add-users/delete-a-user.md) die aan een licentie zijn toegewezen om hun licentie beschikbaar te maken voor andere gebruikers. Wanneer u een gebruikersaccount verwijdert, is de licentie direct beschikbaar om aan iemand anders toe te wijzen.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Gebruik de pagina Licenties om licenties niet toe te staan

Wanneer u de pagina **Licenties** gebruikt om licenties niet toe te staan, kunt u licenties voor een specifiek product voor maximaal 20 gebruikers verwijderen.

1. Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenties</a>.
2. Selecteer het product waarvoor u licenties wilt inleveren.
3. Selecteer de gebruikers waarvoor u licenties wilt inleveren.
4. Selecteer **Licenties niet toewijzen.**
5. Selecteer in **het vak Licenties niet** toewijzen de optie Niet **toewijzen.**

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>De pagina Actieve gebruikers gebruiken om licenties niet toe te staan

Wanneer u de pagina **Actieve gebruikers gebruikt** om licenties niet toe te staan, ontsiert u productlicenties van gebruikers.

### <a name="unassign-licenses-from-one-user"></a>Licenties van één gebruiker niet toewijzen
  
1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.
2. Selecteer de rij van de gebruiker voor wie u een licentie wilt ontlenen.
3. Selecteer in het rechterdeelvenster **Licenties en apps**.
4. Vouw de **sectie Licenties** uit, schakel de vakken uit voor de licenties die u niet wilt toewijzen en selecteer Vervolgens **Wijzigingen opslaan.**

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>Licenties van één gebruiker niet toewijzen

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.
2. Kies de gebruiker voor wie u de licentie wilt ontlenen.
3. Selecteer aan de rechterkant in de **rij Productlicenties** de optie **Bewerken.**
4. Schakel in **het deelvenster Productlicenties** de wisselknop over naar de **uit-positie** voor de licentie die u wilt opmaken voor de gebruiker. Als u bijvoorbeeld de Office 365 Enterprise E3-licentie uitschakelt, worden deze licentie en alle services onder die licentie voor die gebruiker niet meer toekend.
5. Selecteer onderaan het deelvenster **Productlicenties** de opties **Opslaan** \> **Sluiten** \> **Sluiten**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>Licenties van één gebruiker niet toewijzen

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.
2. Kies de gebruiker voor wie u de licentie wilt ontlenen.
3. Selecteer aan de rechterkant in de **rij Productlicenties** de optie **Bewerken.**
4. Schakel in **het deelvenster Productlicenties** de wisselknop over naar de **uit-positie** voor de licentie die u wilt opmaken voor de gebruiker. Als u bijvoorbeeld de Office 365 Enterprise E3-licentie uitschakelt, worden deze licentie en alle services onder die licentie voor die gebruiker niet meer toekend.
5. Selecteer onderaan het deelvenster **Productlicenties** de opties **Opslaan** \> **Sluiten** \> **Sluiten**.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>Licenties van meerdere gebruikers niet toewijzen

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.
2. Selecteer de cirkels naast de namen van de gebruikers voor wie u licenties wilt ontlenen.
3. Selecteer bovenaan **Meer opties (...)** en selecteer vervolgens **Productlicenties beheren**.
4. Selecteer in het deelvenster **Productlicenties beheren** **Bestaande productlicentietoewijzingen vervangen** \> **Volgende**.
5. Schakel onder in het deelvenster **Bestaande** producten vervangen het selectievakje **Alle productlicenties** verwijderen uit de geselecteerde gebruikers in en selecteer **vervolgens Sluiten** \> **vervangen.**

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>Licenties van meerdere gebruikers niet toewijzen

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.
2. Selecteer de vakken naast de namen van de gebruikers voor wie u alle licenties wilt ontlenen.
3. Selecteer in het deelvenster **Bulkacties** de optie **Productlicenties bewerken**.
4. Selecteer in het deelvenster **Bestaande producten vervangen** **Huidige licentietoewijzingen vervangen** \> **Volgende**.
5. Schakel onder in het deelvenster **Bestaande** producten vervangen het selectievakje Alle **productlicenties** verwijderen uit de geselecteerde gebruikers in en selecteer **sluiten** \>  \> **sluiten vervangen.**

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>Licenties van meerdere gebruikers niet toewijzen
  
1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.
2. Selecteer de vakken naast de namen van de gebruikers voor wie u alle licenties wilt ontlenen.
3. Selecteer in het deelvenster **Bulkacties** de optie **Productlicenties bewerken**.
4. Selecteer in het deelvenster **Bestaande producten vervangen** **Huidige licentietoewijzingen vervangen** \> **Volgende**.
5. Schakel onder in het deelvenster **Bestaande** producten vervangen het selectievakje Alle **productlicenties** verwijderen uit de geselecteerde gebruikers in en selecteer **sluiten** \>  \> **sluiten vervangen.**

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>Wat gebeurt er met de gegevens van een gebruiker wanneer u de licentie verwijdert?

- Wanneer een licentie van een gebruiker wordt verwijderd, worden gegevens die aan dat account zijn gekoppeld, 30 dagen in bezit gehouden. Na de respijtperiode van 30 dagen worden de gegevens verwijderd en kunnen ze niet meer worden hersteld.
- Bestanden die zijn opgeslagen in OneDrive voor Bedrijven, worden niet verwijderd, tenzij de gebruiker wordt verwijderd uit het Microsoft 365-beheercentrum of wordt verwijderd via Active Directory-synchronisatie. Zie [OneDrive-bewaring en -verwijdering voor meer informatie.](/onedrive/retention-and-deletion)
- Wanneer de licentie wordt verwijderd, kan het postvak van de gebruiker niet meer worden doorzocht met behulp van een eDiscovery-hulpprogramma, zoals Zoeken naar inhoud of Geavanceerd eDiscovery. Zie 'Verbroken of niet-gelicentieerde postvakken zoeken' in Inhoud zoeken [in Microsoft 365](../../compliance/content-search.md#searching-disconnected-or-de-licensed-mailboxes)voor meer informatie.
- Als u een Enterprise-abonnement hebt, zoals Office 365 Enterprise E3, kunt u met Exchange Online de postvakgegevens van een verwijderd gebruikersaccount behouden met [inactieve postvakken.](../../compliance/inactive-mailboxes-in-office-365.md) Zie Inactieve postvakken maken en beheren in Exchange Online voor [meer informatie.](../../compliance/create-and-manage-inactive-mailboxes.md)
- Zie Een voormalige werknemer verwijderen voor informatie over het blokkeren van de toegang van een gebruiker tot Microsoft 365-gegevens nadat de licentie is verwijderd en hoe u daarna toegang tot de gegevens [kunt krijgen.](../add-users/remove-former-employee.md)
- Als u de licentie van een gebruiker verwijdert en er nog Steeds Office-apps zijn geïnstalleerd, zien ze product- en [activeringsfouten](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) zonder licentie in Office wanneer ze Office-apps gebruiken.

## <a name="next-steps"></a>Volgende stappen

Als u de ongebruikte licenties niet opnieuw wilt toewijzen aan [](../../commerce/licenses/buy-licenses.md) andere [gebruikers,](../../managed-desktop/get-started/assign-licenses.md)kunt u overwegen om de licenties uit uw abonnement te verwijderen, zodat u niet meer licenties betaalt dan u nodig hebt.

## <a name="related-content"></a>Verwante onderwerpen

[Licenties verwijderen uit uw abonnement](../../commerce/licenses/buy-licenses.md) (artikel)\
[Licenties toewijzen aan gebruikers](assign-licenses-to-users.md) (artikel)\
[Meer informatie over abonnementen en licenties in Microsoft 365 voor Bedrijven](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)