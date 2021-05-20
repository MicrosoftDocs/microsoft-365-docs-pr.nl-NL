---
title: Licenties van gebruikers verwijderen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: Meer informatie over het verwijderen van licenties van gebruikersaccounts.
ms.date: 07/01/2020
ms.openlocfilehash: 4ff6a0e5554117cd1fc2d818c04edabc9e33b2a1
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582906"
---
# <a name="unassign-licenses-from-users"></a>Licenties van gebruikers verwijderen

U kunt licenties van gebruikers op  de pagina Actieve gebruikers of op de pagina **Licenties verwijderen.** De methode die u gebruikt, is afhankelijk van of u productlicenties van specifieke gebruikers wilt inleveren of gebruikerslicenties van een bepaald product wilt inleveren.

> [!NOTE]
> Als beheerder kunt u geen licenties toewijzen of verwijderen voor een self-service aankoopabonnement dat door een gebruiker in uw organisatie is gekocht. U kunt [self-service aankoopabonnementen overnemen](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)en vervolgens licenties toewijzen of opheffen.

## <a name="before-you-begin"></a>Voordat u begint

- U moet een globale, licentie- en gebruikersbeheerder zijn om licenties te ontlenen. Zie [Over beheerdersrollen in Microsoft 365](../add-users/about-admin-roles.md) voor meer informatie.
- U kunt [licenties van gebruikersaccounts intrekken met Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).
- U kunt ook [gebruikersaccounts verwijderen](../add-users/delete-a-user.md) die aan een licentie zijn toegewezen om hun licentie beschikbaar te maken voor andere gebruikers. Wanneer u een gebruikersaccount verwijdert, is de licentie direct beschikbaar om aan iemand anders toe te wijzen.

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Gebruik de pagina Licenties om licenties niet toe te staan

Wanneer u de pagina **Licenties** gebruikt om licenties niet toe te staan, kunt u licenties voor een specifiek product voor maximaal 20 gebruikers verwijderen.

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenties</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenties</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenties</a>.

::: moniker-end

2. Selecteer het product waarvoor u licenties wilt inleveren.
3. Selecteer de gebruikers waarvoor u licenties wilt inleveren.
4. Selecteer **Licenties niet toewijzen.**
5. Selecteer in **het vak Licenties niet** toewijzen de optie Niet **toewijzen.**

## <a name="use-the-active-users-page-to-unassign-licenses"></a>De pagina Actieve gebruikers gebruiken om licenties niet toe te staan

Wanneer u de pagina **Actieve gebruikers gebruikt** om licenties niet toe te staan, ontsiert u productlicenties van gebruikers.

### <a name="unassign-licenses-from-one-user"></a>Licenties van één gebruiker niet toewijzen

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.

::: moniker-end

2. Selecteer de rij van de gebruiker voor wie u een licentie wilt ontlenen.
3. Selecteer in het rechterdeelvenster **Licenties en apps**.
4. Vouw de **sectie Licenties** uit, schakel de vakken uit voor de licenties die u niet wilt toewijzen en selecteer Vervolgens **Wijzigingen opslaan.**

### <a name="unassign-licenses-from-multiple-users"></a>Licenties van meerdere gebruikers niet toewijzen

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.

::: moniker-end

2. Selecteer de cirkels naast de namen van de gebruikers voor wie u licenties wilt ontlenen.
3. Selecteer bovenaan de drie puntjes (meer opties) en selecteer vervolgens **Productlicenties beheren**.
4. Selecteer in het deelvenster **Productlicenties beheren** **Bestaande productlicentietoewijzingen vervangen** \> **Volgende**.
5. Schakel onder in het deelvenster **Bestaande** producten vervangen het selectievakje **Alle productlicenties** verwijderen uit de geselecteerde gebruikers in en selecteer **vervolgens Sluiten** \> **vervangen.**

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>Wat gebeurt er met de gegevens van een gebruiker wanneer u de licentie verwijdert?

- Wanneer een licentie van een gebruiker wordt verwijderd, Exchange onlinegegevens die aan dat account zijn gekoppeld, 30 dagen lang worden opgehouden. Na de respijtperiode van 30 dagen worden de gegevens verwijderd en kunnen ze niet meer worden hersteld.
- Bestanden die in OneDrive voor Bedrijven zijn opgeslagen, worden niet verwijderd, tenzij de gebruiker wordt verwijderd uit het Microsoft 365-beheercentrum of wordt verwijderd via Active Directory-synchronisatie. Zie voor meer informatie [OneDrive bewaren en verwijderen.](/onedrive/retention-and-deletion)
- Wanneer de licentie wordt verwijderd, kan het postvak van de gebruiker niet meer worden doorzocht met behulp van een eDiscovery-hulpprogramma, zoals Zoeken naar inhoud of Advanced eDiscovery. Zie 'Verbroken of niet-gelicentieerde postvakken zoeken' in Inhoud zoeken [in](../../compliance/content-search.md)Microsoft 365.
- Als u een Enterprise-abonnement hebt, zoals Office 365 Enterprise E3, kunt u Exchange Online de postvakgegevens van een verwijderd gebruikersaccount behouden door inactieve postvakken [te gebruiken.](../../compliance/inactive-mailboxes-in-office-365.md) Zie Inactieve postvakken maken en beheren [in Exchange Online.](../../compliance/create-and-manage-inactive-mailboxes.md)
- Zie Een voormalige werknemer verwijderen voor informatie over het blokkeren van de toegang van een gebruiker tot Microsoft 365-gegevens nadat de licentie is verwijderd en hoe u daarna toegang tot de gegevens [kunt krijgen.](../add-users/remove-former-employee.md)
- Als u de licentie van een gebruiker verwijdert en er nog steeds Office-apps zijn geïnstalleerd, zien ze product- en [activeringsfouten](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) zonder licentie in Office wanneer ze Office gebruiken.

## <a name="next-steps"></a>Volgende stappen

Als u de ongebruikte licenties niet opnieuw wilt toewijzen aan [](../../commerce/licenses/buy-licenses.md) andere [gebruikers,](../../managed-desktop/get-started/assign-licenses.md)kunt u overwegen om de licenties uit uw abonnement te verwijderen, zodat u niet meer licenties betaalt dan u nodig hebt.

## <a name="related-content"></a>Verwante inhoud

[Licenties verwijderen uit uw abonnement](../../commerce/licenses/buy-licenses.md) (artikel)\
[Licenties toewijzen aan gebruikers](assign-licenses-to-users.md) (artikel)\
[Meer inzicht in abonnementen en licenties in Microsoft 365 voor Bedrijven](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)
