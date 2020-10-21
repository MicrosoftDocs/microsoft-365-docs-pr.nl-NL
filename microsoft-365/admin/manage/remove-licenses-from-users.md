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
description: Leer hoe u licenties van gebruikersaccounts intrekken.
ms.date: 07/01/2020
ms.openlocfilehash: 455348e7dba20913e54e5a4059755f9391644e03
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645093"
---
# <a name="unassign-licenses-from-users"></a>Licenties van gebruikers verwijderen

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

::: moniker range="o365-worldwide"

U kunt licenties toewijzen aan gebruikers op de pagina **actieve gebruikers** of op de pagina **licenties** . Welke methode u gebruikt, is afhankelijk van de vraag of u productlicenties wilt intrekken voor specifieke gebruikers of gebruikerslicenties wilt intrekken voor een specifiek product.

::: moniker-end

## <a name="before-you-begin"></a>Voordat u begint

- U moet een globale, licentie, gebruikersbeheerder zijn om licenties op te heffen. Zie [Over beheerdersrollen in Microsoft 365](../add-users/about-admin-roles.md) voor meer informatie.
- U kunt [licenties van gebruikersaccounts intrekken met Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).
- U kunt ook [gebruikersaccounts verwijderen](../add-users/delete-a-user.md) waaraan een licentie is toegewezen om de licentie beschikbaar te maken voor andere gebruikers. Wanneer u een gebruikersaccount verwijdert, is de licentie direct beschikbaar om aan iemand anders toe te wijzen.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>De pagina licenties gebruiken om licenties op te heffen

Wanneer u de pagina **licenties** gebruikt om licenties te detoewijzen, schaft u de toewijzingen voor een specifiek product aan voor maximaal 20 gebruikers.

1. Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenties</a>.
2. Selecteer het product waarvoor u licenties wilt intrekken.
3. Selecteer de gebruikers voor wie u de licenties wilt intrekken.
4. Selecteer **licenties intrekken**.
5. Selecteer in het vak **licenties intrekken** de optie **intrekken**.

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>De pagina actieve gebruikers gebruiken om licenties op te heffen

Wanneer u de pagina **actieve gebruikers** gebruikt om licenties op te heffen, moet u productlicenties van gebruikers intrekken.

### <a name="unassign-licenses-from-one-user"></a>Licenties intrekken voor één gebruiker
  
1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.
2. Selecteer de rij van de gebruiker voor wie u een licentie wilt intrekken.
3. Selecteer in het rechterdeelvenster **Licenties en apps**.
4. Vouw de sectie **licenties** uit, schakel de vakjes uit voor de licenties die u wilt intrekken en selecteer vervolgens **wijzigingen opslaan**.

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>Licenties intrekken voor één gebruiker

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.
2. Selecteer de gebruiker voor wie u de licentie wilt intrekken.
3. Selecteer aan de rechterkant in de rij **product licenties** de optie **bewerken**.
4. Zet in het deelvenster **product licenties** de wisselknop op **uit** voor de licentie die u wilt intrekken voor de gebruiker. Als u bijvoorbeeld de Office 365 Enterprise E3-licentie uitschakelt, wordt die licentie en alle services onder die licentie voor die gebruiker opheffen.
5. Selecteer onderaan het deelvenster **Productlicenties** de opties **Opslaan** \> **Sluiten** \> **Sluiten**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>Licenties intrekken voor één gebruiker

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.
2. Selecteer de gebruiker voor wie u de licentie wilt intrekken.
3. Selecteer aan de rechterkant in de rij **product licenties** de optie **bewerken**.
4. Zet in het deelvenster **product licenties** de wisselknop op **uit** voor de licentie die u wilt intrekken voor de gebruiker. Als u bijvoorbeeld de Office 365 Enterprise E3-licentie uitschakelt, wordt die licentie en alle services onder die licentie voor die gebruiker opheffen.
5. Selecteer onderaan het deelvenster **Productlicenties** de opties **Opslaan** \> **Sluiten** \> **Sluiten**.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>Licenties intrekken voor meerdere gebruikers

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.
2. Schakel de vakjes in naast de namen van de gebruikers voor wie u een licentie wilt intrekken.
3. Selecteer bovenaan **Meer opties (...)** en selecteer vervolgens **Productlicenties beheren**.
4. Selecteer in het deelvenster **Productlicenties beheren** **Bestaande productlicentietoewijzingen vervangen** \> **Volgende**.
5. Schakel onder aan het deelvenster **bestaande producten vervangen** het selectievakje **alle productlicenties van de geselecteerde gebruikers verwijderen** in en selecteer vervolgens sluiten **vervangen** \> **Close**.

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>Licenties intrekken voor meerdere gebruikers

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.
2. Schakel de selectievakjes in naast de namen van de gebruikers waarvoor u alle licenties wilt intrekken.
3. Selecteer in het deelvenster **Bulkacties** de optie **Productlicenties bewerken**.
4. Selecteer in het deelvenster **Bestaande producten vervangen** **Huidige licentietoewijzingen vervangen** \> **Volgende**.
5. Schakel onder aan het deelvenster **bestaande producten vervangen** het selectievakje **alle productlicenties van de geselecteerde gebruikers verwijderen** in **en selecteer vervolgens sluiten** \> **Close** \> **Close**.

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>Licenties intrekken voor meerdere gebruikers
  
1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.
2. Schakel de selectievakjes in naast de namen van de gebruikers waarvoor u alle licenties wilt intrekken.
3. Selecteer in het deelvenster **Bulkacties** de optie **Productlicenties bewerken**.
4. Selecteer in het deelvenster **Bestaande producten vervangen** **Huidige licentietoewijzingen vervangen** \> **Volgende**.
5. Schakel onder aan het deelvenster **bestaande producten vervangen** het selectievakje **alle productlicenties van de geselecteerde gebruikers verwijderen** in **en selecteer vervolgens sluiten** \> **Close** \> **Close**.

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>Wat gebeurt er met de gegevens van een gebruiker wanneer u de licentie verwijdert?

- Wanneer een licentie van een gebruiker wordt verwijderd, worden de gegevens die aan dat account zijn gekoppeld, 30 dagen lang bewaard. Na de termijn van 30 dagen worden de gegevens verwijderd en kunnen ze niet meer worden hersteld.
- Bestanden die zijn opgeslagen in OneDrive voor bedrijven, worden niet verwijderd, tenzij de gebruiker wordt verwijderd uit het Microsoft 365-Beheercentrum of wordt verwijderd via Active Directory-synchronisatie. Zie voor meer informatie [OneDrive-behoud en-verwijdering](https://docs.microsoft.com/onedrive/retention-and-deletion).
- Wanneer de licentie is verwijderd, kunt u het postvak van de gebruiker niet meer doorzoeken met behulp van een eDiscovery-hulpprogramma, zoals inhoud zoeken of Geavanceerd eDiscovery. Zie voor meer informatie het artikel over het zoeken in een verbinding met een verbinding met de postvakken in [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).
- Als u een Enterprise-abonnement hebt, zoals Office 365 Enterprise E3, kunt u in Exchange Online de postvakgegevens van een verwijderd gebruikersaccount bewaren met [inactieve postvakken](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365). Zie [inactieve postvakken in Exchange Online maken en beheren](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)voor meer informatie.
- Zie [een voormalige werknemer verwijderen](../add-users/remove-former-employee.md)voor informatie over het blokkeren van toegang van een gebruiker tot microsoft 365-gegevens na verwijdering van de licentie en over hoe u later toegang krijgt tot de gegevens.
- Als u de licentie van een gebruiker verwijdert en er nog steeds Office-apps zijn geïnstalleerd, zien ze de [fouten met producten zonder licentie en activeringen in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) wanneer ze Office-apps gebruiken.

## <a name="next-steps"></a>Volgende stappen

Als u niet [de ongebruikte licenties opnieuw wilt toewijzen aan andere gebruikers](../../managed-desktop/get-started/assign-licenses.md), kunt u overwegen om [de licenties van uw abonnement te verwijderen](../../commerce/licenses/buy-licenses.md) zodat u niet meer licenties betaalt dan u nodig hebt.

## <a name="related-content"></a>Verwante onderwerpen

[Licenties verwijderen uit uw abonnement](../../commerce/licenses/remove-licenses-from-subscription.md) (artikel) \
[Licenties toewijzen aan gebruikers](assign-licenses-to-users.md) (artikel) \
Meer [informatie over abonnementen en licenties in Microsoft 365 voor bedrijven](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)