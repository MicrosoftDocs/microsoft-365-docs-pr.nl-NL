---
title: Uw account sluiten
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Meer informatie over het sluiten van uw account bij Microsoft.
ms.openlocfilehash: f399a1ba4d67abf5982c111e9b915f02324150a5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402176"
---
# <a name="close-your-account"></a>Uw account sluiten

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Wanneer u uw account bij Microsoft sluit, wordt alle informatie met betrekking tot uw account verwijderd. Deze informatie omvat abonnementen, licenties, betalingsmethoden, gebruikers en gebruikersgegevens. Voordat u dit proces start, moet u een back-up maken van alle gegevens die u wilt behouden.

## <a name="step-1-delete-users"></a>Stap 1: Gebruikers verwijderen

Verwijder alle gebruikers, behalve één globale beheerder die de stappen voltooit om het account te sluiten. Voordat u de map aan het einde van dit proces verwijderen, moet u alle andere gebruikers verwijderen.

Als gebruikers worden gesynchroniseerd vanuit on-premises, schakel je de synchronisatie eerst uit en verwijder je de gebruikers in de cloudmap met behulp van de Azure-portal of Azure PowerShell-cmdlets.

Als u gebruikers wilt verwijderen, raadpleegt <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">u Beheerder gebruikersbeheer: Een of meer gebruikers verwijderen</a>.

U ook de cmdlet <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell gebruiken om gebruikers in bulk te verwijderen.

Als uw organisatie Active Directory gebruikt die synchroniseert met Azure AD, verwijdert u in plaats daarvan het gebruikersaccount uit Active Directory. Zie <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulkgebruikers verwijderen in Azure Active Directory</a>voor instructies.

## <a name="step-2-cancel-all-active-subscriptions"></a>Stap 2: Alle actieve abonnementen opzeggen

1. Ga in het beheercentrum naar de pagina **Facturering**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten.</a>

2. Als de lijst met abonnementen zich in de **tabelweergave** bevindt, selecteert u **rechts Kaarten**.

3. Zoek een actief abonnement en selecteer in de sectie **Instellingen & Acties** de optie Abonnement **annuleren**.

4. Volg de aanwijzingen om het proces te voltooien.

5. Herhaal stap 1 tot en met 4 om alle actieve abonnementen op te zeggen.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Stap 3: Alle abonnementen voor uitgeschakelden verwijderen

1. Ga in het beheercentrum naar de pagina **Facturering**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten.</a>

2. Als de lijst met abonnementen zich in de **tabelweergave** bevindt, selecteert u **rechts Kaarten**.

3. Selecteer Uitgeschakeld naast **de status Abonnement**. **Disabled**

4. Zoek een uitgeschakeld abonnement en selecteer in de sectie **Instellingen & Acties** de optie **Verwijderen**.

5. Schakel in het dialoogvenster **Abonnement verwijderen** het selectievakje Ik **begrijp het** effect in en selecteer Abonnement **verwijderen**.

6. Herhaal stap 4 en 5 voor elk uitgeschakeld abonnement totdat alle abonnementen zijn verwijderd.

## <a name="step-4-disable-multi-factor-authentication"></a>Stap 4: Meervoudige verificatie uitschakelen

1. Ga in het beheercentrum **Users**naar de pagina  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Gebruikers actieve gebruikers.</a>

2. Kies **Multi-factor authenticatie**.

3. Schakel op de pagina multi-factor authenticatie alle accounts uit, behalve het globale beheerdersaccount dat u momenteel gebruikt.

U PowerShell ook <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">gebruiken om meervoudige verificatie voor meerdere gebruikers uit te schakelen.</a>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Stap 5: De map verwijderen in Azure Active Directory

1. Meld u aan bij het <a href="https://aad.portal.azure.com/" target="_blank">Azure AD-beheercentrum</a> met een Algemeen Administrator-account.

2. Selecteer **Azure Active Directory**.

3. Schakel over naar de map die u wilt verwijderen.

4. Selecteer **Map verwijderen**.

5. Als uw directory een of meer controles niet haalt, ziet u een koppeling naar meer informatie over hoe u de controles doorstaan. Nadat u alle controles hebt uitgevoerd, selecteert u **Verwijderen** om het proces te voltooien.

Nadat u deze laatste stap hebt voltooid, wordt uw account bij Microsoft gesloten en verwijderd.
