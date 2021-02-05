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
description: Lees hoe u licenties van gebruikersaccounts kunt in- en verwijderen.
ms.date: 07/01/2020
ms.openlocfilehash: 6fb07883fdfd4f4a837890e3e8c4c04b2411772b
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114475"
---
# <a name="unassign-licenses-from-users"></a>Licenties van gebruikers verwijderen

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

::: moniker range="o365-worldwide"

U kunt licenties van gebruikers in  verwijderen op de pagina Actieve gebruikers of op **de pagina** Licenties. De methode die u gebruikt, is afhankelijk van of u de productlicenties van specifieke gebruikers wilt in- of de gebruikerslicenties van een specifiek product wilt in- of in- of weer in te stellen.

::: moniker-end

## <a name="before-you-begin"></a>Voordat u begint

- U moet een globale, licentie- en gebruikersbeheerder zijn om het toewijzen van licenties op te zeggen. Zie [Over beheerdersrollen in Microsoft 365](../add-users/about-admin-roles.md) voor meer informatie.
- U kunt [licenties van gebruikersaccounts intrekken met Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).
- U kunt ook [gebruikersaccounts](../add-users/delete-a-user.md) verwijderen aan wie een licentie is toegewezen om de licentie beschikbaar te stellen aan andere gebruikers. Wanneer u een gebruikersaccount verwijdert, is de licentie direct beschikbaar om aan iemand anders toe te wijzen.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Gebruik de pagina Licenties om licenties in te verwijderen

Wanneer u de **pagina Licenties** gebruikt om licenties in te verwijderen, worden licenties voor een specifiek product in gebruik gemaakt voor maximaal 20 gebruikers.

1. Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenties</a>.
2. Selecteer het product waarvoor u licenties wilt inleveren.
3. Selecteer de gebruikers waarvoor u licenties wilt inleveren.
4. Selecteer **Licenties in- en uitleveren in.**
5. Selecteer In **het vak Licenties in niet toewijzen** de optie Niet **toewijzen.**

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>De pagina Actieve gebruikers gebruiken om licenties in te verwijderen

Wanneer u de pagina **Actieve gebruikers** gebruikt om licenties in te verwijderen, worden productlicenties van gebruikers in gebruik gemaakt.

### <a name="unassign-licenses-from-one-user"></a>Licenties van één gebruiker in licentie toewijzen
  
1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.
2. Selecteer de rij van de gebruiker voor wie u de licentie wilt inleveren.
3. Selecteer in het rechterdeelvenster **Licenties en apps**.
4. Vouw de **sectie Licenties** uit, schakel de selectievakjes uit voor de licenties die u wilt inleveren en selecteer **Wijzigingen opslaan.**

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>Licenties van één gebruiker in licentie toewijzen

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.
2. Kies de gebruiker voor wie u de licentie wilt inleveren.
3. Selecteer Bewerken in de **rij Productlicenties** **aan de rechterkant.**
4. Zet in **het deelvenster Productlicenties** de  wisselknop op Uit voor de licentie die u wilt inschakelen voor de gebruiker. Als u bijvoorbeeld de Office 365 Enterprise E3-licentie uitschakelt, worden die licentie en alle services onder die licentie voor die gebruiker in gebruik gemaakt.
5. Selecteer onderaan het deelvenster **Productlicenties** de opties **Opslaan** \> **Sluiten** \> **Sluiten**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>Licenties van één gebruiker in licentie toewijzen

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.
2. Kies de gebruiker voor wie u de licentie wilt inleveren.
3. Selecteer Bewerken in de **rij Productlicenties** **aan de rechterkant.**
4. Zet in **het deelvenster Productlicenties** de  wisselknop op Uit voor de licentie die u wilt inschakelen voor de gebruiker. Als u bijvoorbeeld de Office 365 Enterprise E3-licentie uitschakelt, worden die licentie en alle services onder die licentie voor die gebruiker in gebruik gemaakt.
5. Selecteer onderaan het deelvenster **Productlicenties** de opties **Opslaan** \> **Sluiten** \> **Sluiten**.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>Licenties van meerdere gebruikers in licentie geven

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.
2. Selecteer de cirkels naast de namen van de gebruikers voor wie u licenties wilt inleveren.
3. Selecteer bovenaan **Meer opties (...)** en selecteer vervolgens **Productlicenties beheren**.
4. Selecteer in het deelvenster **Productlicenties beheren** **Bestaande productlicentietoewijzingen vervangen** \> **Volgende**.
5. Schakel onder in het deelvenster **Bestaande** producten vervangen het selectievakje Alle **productlicenties** verwijderen van de geselecteerde gebruikers in en selecteer **vervolgens Sluiten** \> **vervangen.**

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>Licenties van meerdere gebruikers in licentie geven

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.
2. Schakel de selectievakjes in naast de namen van de gebruikers voor wie u alle licenties wilt inleveren.
3. Selecteer in het deelvenster **Bulkacties** de optie **Productlicenties bewerken**.
4. Selecteer in het deelvenster **Bestaande producten vervangen** **Huidige licentietoewijzingen vervangen** \> **Volgende**.
5. Schakel onder in het deelvenster **Bestaande** producten vervangen het selectievakje Alle **productlicenties** verwijderen uit de geselecteerde gebruikers in en selecteer **vervolgens** Sluiten \>  \> vervangen.

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>Licenties van meerdere gebruikers in licentie geven
  
1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.
2. Schakel de selectievakjes in naast de namen van de gebruikers voor wie u alle licenties wilt inleveren.
3. Selecteer in het deelvenster **Bulkacties** de optie **Productlicenties bewerken**.
4. Selecteer in het deelvenster **Bestaande producten vervangen** **Huidige licentietoewijzingen vervangen** \> **Volgende**.
5. Schakel onder in het deelvenster **Bestaande** producten vervangen het selectievakje Alle **productlicenties** verwijderen uit de geselecteerde gebruikers in en selecteer **vervolgens** Sluiten \>  \> vervangen.

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>Wat gebeurt er met de gegevens van een gebruiker wanneer u de licentie verwijdert?

- Wanneer een licentie van een gebruiker wordt ingetrokken, worden gegevens die aan dat account zijn gekoppeld, 30 dagen in het bezit gehouden. Na deze respijtperiode van 30 dagen worden de gegevens verwijderd en kunnen ze niet meer worden hersteld.
- Bestanden die zijn opgeslagen in OneDrive voor Bedrijven worden niet verwijderd, tenzij de gebruiker wordt verwijderd uit het Microsoft 365-beheercentrum of wordt verwijderd via Active Directory-synchronisatie. Zie Het bewaren en verwijderen [van OneDrive voor meer informatie.](https://docs.microsoft.com/onedrive/retention-and-deletion)
- Wanneer de licentie wordt verwijderd, kan het postvak van de gebruiker niet meer worden doorzocht met een eDiscovery-hulpprogramma zoals Inhoud zoeken of Geavanceerd eDiscovery. Zie 'Verbroken of niet-gelicentieerde postvakken zoeken' in Inhoud zoeken [in Microsoft 365 voor meer informatie.](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes)
- Als u een Enterprise-abonnement hebt, zoals Office 365 Enterprise E3, kunt u in Exchange Online de postvakgegevens van een verwijderd gebruikersaccount behouden door inactieve postvakken [te gebruiken.](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365) Zie Inactieve postvakken maken en beheren [in Exchange Online voor meer informatie.](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)
- Zie Een voormalige werknemer verwijderen voor informatie over het blokkeren van de toegang van een gebruiker tot Microsoft 365-gegevens nadat de licentie is verwijderd en hoe u later toegang krijgt tot de [gegevens.](../add-users/remove-former-employee.md)
- Als u de licentie van een gebruiker verwijdert en er nog Steeds Office-apps zijn geïnstalleerd, zien ze fouten met producten zonder licentie en activeringsfouten [in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) wanneer ze Office-apps gebruiken.

## <a name="next-steps"></a>Volgende stappen

Als u de niet-gebruikte licenties niet opnieuw aan andere [](../../commerce/licenses/buy-licenses.md) gebruikers wilt [toewijzen,](../../managed-desktop/get-started/assign-licenses.md)kunt u de licenties uit uw abonnement verwijderen, zodat u niet voor meer licenties betaalt dan nodig is.

## <a name="related-content"></a>Verwante onderwerpen

[Licenties verwijderen uit uw abonnement](../../commerce/licenses/remove-licenses-from-subscription.md) (artikel)\
[Licenties toewijzen aan gebruikers](assign-licenses-to-users.md) (artikel)\
[Informatie over abonnementen en licenties in Microsoft 365 voor Bedrijven](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)