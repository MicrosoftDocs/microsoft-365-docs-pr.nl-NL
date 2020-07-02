---
title: Licenties van gebruikers verwijderen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
description: Meer informatie over het losmaken van licenties van gebruikersaccounts.
ms.date: 07/01/2020
ms.openlocfilehash: 29dbdb89550d5bd9bd13071b184ffe1ca340f2a6
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015933"
---
# <a name="unassign-licenses-from-users"></a>Licenties van gebruikers verwijderen

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

::: moniker range="o365-worldwide"

U licenties van gebruikers niet-verrijzen op de pagina **Actieve gebruikers** of op de pagina **Licenties.** De methode die u gebruikt, is afhankelijk van de vraag of u productlicenties van specifieke gebruikers wilt onttekenen of licenties van gebruikers van een specifiek product wilt toewijzen.

::: moniker-end

## <a name="before-you-begin"></a>Voordat u begint

- U moet een globale, licentie, gebruikersbeheerder zijn om licenties niet te vertekenen. Zie [Informatie over beheerdersrollen in Microsoft 365](../add-users/about-admin-roles.md) voor meer informatie.
- U kunt [licenties van gebruikersaccounts intrekken met Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).
- U ook [gebruikersaccounts verwijderen](../add-users/delete-a-user.md) waaraan een licentie is toegewezen om hun licentie beschikbaar te maken voor andere gebruikers. Wanneer u een gebruikersaccount verwijdert, is de licentie onmiddellijk beschikbaar om aan iemand anders toe te wijzen.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>De pagina Licenties gebruiken om licenties niet te plaatsen

Wanneer u de pagina **Licenties** gebruikt om licenties niet te plaatsen, u licenties voor een specifiek product voor maximaal 20 gebruikers onttekenen.

1. Ga in het beheercentrum **Billing** naar de pagina > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Factureringslicenties.</a>
2. Selecteer het product waarvoor u licenties wilt toewijzen.
3. Selecteer de gebruikers waarvoor u licenties wilt toewijzen.
4. Selecteer **Licenties voor ondestekenen**.
5. Selecteer Onteken in het vak **Licenties voor ondestekenen.** **Unassign**

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>De pagina Actieve gebruikers gebruiken om licenties niet te plaatsen

Wanneer u de pagina **Actieve gebruikers** gebruikt om licenties niet te plaatsen, u productlicenties van gebruikers onttekenen.

### <a name="unassign-licenses-from-one-user"></a>Licenties van één gebruiker niet toewijzen
  
1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.
2. Selecteer de rij van de gebruiker waarvoor u een licentie wilt onttekenen.
3. Selecteer in het rechterdeelvenster **Licenties en apps**.
4. Vouw de sectie **Licenties** uit, schakel de vakken uit voor de licenties die u wilt toewijzen en selecteer **Wijzigingen opslaan**.

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>Licenties van één gebruiker niet toewijzen

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.
2. Kies de gebruiker waarvoor u de licentie wilt onttekenen.
3. Selecteer Rechts in de rij **Productlicenties** de optie **Bewerken**.
4. Schakel in het deelvenster **Productlicenties** de schakelaar in op de **positie Uit** voor de licentie die u niet wilt toewijzen voor de gebruiker. Als u bijvoorbeeld de Office 365 Enterprise E3-licentie uitschakelt, worden de licentie en alle services onder die licentie voor die gebruiker niet ondertekend.
5. Selecteer onderaan het deelvenster **Productlicenties** de opties **Opslaan** \> **Sluiten** \> **Sluiten**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>Licenties van één gebruiker niet toewijzen

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.
2. Kies de gebruiker waarvoor u de licentie wilt onttekenen.
3. Selecteer Rechts in de rij **Productlicenties** de optie **Bewerken**.
4. Schakel in het deelvenster **Productlicenties** de schakelaar in op de **positie Uit** voor de licentie die u niet wilt toewijzen voor de gebruiker. Als u bijvoorbeeld de Office 365 Enterprise E3-licentie uitschakelt, worden de licentie en alle services onder die licentie voor die gebruiker niet ondertekend.
5. Selecteer onderaan het deelvenster **Productlicenties** de opties **Opslaan** \> **Sluiten** \> **Sluiten**.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>Licenties van meerdere gebruikers niet toewijzen

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.
2. Selecteer de kringen naast de namen van de gebruikers waarvoor u licenties wilt toewijzen.
3. Selecteer bovenaan **Meer opties (...)** en selecteer vervolgens **Productlicenties beheren**.
4. Selecteer in het deelvenster **Productlicenties beheren** **Bestaande productlicentietoewijzingen vervangen** \> **Volgende**.
5. Schakel onder aan het deelvenster **Bestaande producten vervangen** de optie Alle **productlicenties verwijderen uit het selectievakje Geselecteerde gebruikers** in en schakel Sluiten **Replace** \> **vervangen**in.

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>Licenties van meerdere gebruikers niet toewijzen

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.
2. Selecteer de vakken naast de namen van de gebruikers waarvoor u alle licenties wilt onttekenen.
3. Selecteer in het deelvenster **Bulkacties** de optie **Productlicenties bewerken**.
4. Selecteer in het deelvenster **Bestaande producten vervangen** **Huidige licentietoewijzingen vervangen** \> **Volgende**.
5. Schakel onder aan het deelvenster **Bestaande producten vervangen** de optie Alle **productlicenties verwijderen uit het selectievakje Geselecteerde gebruikers** in en schakel Sluiten sluiten **vervangen** \> **Close** \> **Close**in.

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>Licenties van meerdere gebruikers niet toewijzen
  
1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.
2. Selecteer de vakken naast de namen van de gebruikers waarvoor u alle licenties wilt onttekenen.
3. Selecteer in het deelvenster **Bulkacties** de optie **Productlicenties bewerken**.
4. Selecteer in het deelvenster **Bestaande producten vervangen** **Huidige licentietoewijzingen vervangen** \> **Volgende**.
5. Schakel onder aan het deelvenster **Bestaande producten vervangen** de optie Alle **productlicenties verwijderen uit het selectievakje Geselecteerde gebruikers** in en schakel Sluiten sluiten **vervangen** \> **Close** \> **Close**in.

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>Wat gebeurt er met de gegevens van een gebruiker wanneer u de licentie verwijdert?

- Wanneer een licentie van een gebruiker wordt verwijderd, worden gegevens die aan dat account zijn gekoppeld, gedurende 30 dagen bewaard. Na de respijtperiode van 30 dagen worden de gegevens verwijderd en kunnen ze niet worden hersteld.
- Bestanden die zijn opgeslagen in OneDrive voor Bedrijven worden niet verwijderd, tenzij de gebruiker wordt verwijderd uit het Microsoft 365-beheercentrum of wordt verwijderd via Active Directory-synchronisatie. Zie [Retentie en verwijdering](https://docs.microsoft.com/onedrive/retention-and-deletion)van OneDrive voor meer informatie.
- Wanneer de licentie wordt verwijderd, is het postvak van de gebruiker niet langer doorzoekbaar met behulp van een eDiscovery-tool, zoals Content Search of Advanced eDiscovery. Zie 'Zoeken naar gekoppelde of gedelicentieerde postvakken' in [Content Search in Microsoft 365 voor](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes)meer informatie.
- Als u een Enterprise-abonnement hebt, zoals Office 365 Enterprise E3, u met Exchange Online de postvakgegevens van een verwijderd gebruikersaccount bewaren met behulp van [inactieve postvakken](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365). Zie [Inactieve postvakken maken en beheren in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)voor meer informatie.
- [Zie Een voormalige werknemer](../add-users/remove-former-employee.md)verwijderen voor meer informatie over het blokkeren van de toegang van een gebruiker tot Microsoft 365-gegevens nadat de licentie is verwijderd en hoe u daarna toegang tot de gegevens krijgen.
- Als u de licentie van een gebruiker verwijdert en Office-apps nog steeds zijn geïnstalleerd, worden [er in Office product- en activeringsfouten zonder licentie](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) weergegeven wanneer deze Office-apps gebruiken.

## <a name="next-steps"></a>Volgende stappen

Als u [de ongebruikte licenties](../../managed-desktop/get-started/assign-licenses.md)niet opnieuw wilt toewijzen aan andere gebruikers, u overwegen [de licenties uit uw abonnement](../../commerce/licenses/buy-licenses.md) te verwijderen, zodat u niet voor meer licenties betaalt dan u nodig hebt.

## <a name="related-content"></a>Gerelateerde inhoud

[Licenties verwijderen uit uw abonnement](../../commerce/licenses/remove-licenses-from-subscription.md) (artikel)\
[Licenties toewijzen aan gebruikers](assign-licenses-to-users.md) (artikel)\
[Abonnementen en licenties begrijpen in Microsoft 365 voor bedrijven](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)