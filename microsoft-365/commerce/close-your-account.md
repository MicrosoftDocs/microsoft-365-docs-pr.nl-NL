---
title: Uw account sluiten
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Meer informatie over het sluiten van uw account met Microsoft.
ms.openlocfilehash: 9545c43ee27fb000149776527030b04b5e807a5c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638373"
---
# <a name="close-your-account"></a>Uw account sluiten

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Wanneer u uw account bij Microsoft sluit, wordt alle informatie met betrekking tot uw account verwijderd. Deze informatie omvat abonnementen, licenties, betalingsmethoden, gebruikers en gebruikersgegevens. Voordat u met deze procedure begint, moet u een back-up maken van alle gegevens die u wilt behouden.

## <a name="step-1-delete-users"></a>Stap 1: gebruikers verwijderen

Verwijder alle gebruikers behalve één globale beheerder die de stappen uitvoert om het account te sluiten. Voordat u de map aan het einde van dit proces kunt verwijderen, moet u alle andere gebruikers verwijderen.

Als gebruikers worden gesynchroniseerd vanuit on-premises, moet u eerst synchroniseren uitschakelen en vervolgens de gebruikers in de Cloud Directory verwijderen met behulp van de cmdlets van Azure portal of Azure PowerShell.

Zie <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">gebruikers van Gebruikersbeheer: een of meer gebruikers verwijderen</a>om gebruikers te verwijderen.

U kunt de PowerShell <a href="https://go.microsoft.com/fwlink/?linkid=842230">-cmdlet Remove-MsolUser</a> ook gebruiken om gebruikers bulksgewijs te verwijderen.

Als uw organisatie gebruikmaakt van Active Directory die wordt gesynchroniseerd met Azure AD, moet u in plaats daarvan het gebruikersaccount uit Active Directory verwijderen. Zie voor instructies een <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">bulk verwijdering van gebruikers in azure Active Directory</a>.

## <a name="step-2-cancel-all-active-subscriptions"></a>Stap 2: alle actieve abonnementen annuleren

1. Ga in het Beheercentrum naar de pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten</a> factureren.

2. Als de lijst met abonnementen in de **tabel** weergave wordt weergegeven, selecteert u **kaarten**aan de rechterkant.

3. Zoek een actief abonnement en selecteer in de sectie **instellingen & acties** de optie **abonnement opzeggen**.

4. Volg de aanwijzingen om het proces te voltooien.

5. Herhaal de stappen 1 tot en met 4 om alle actieve abonnementen te annuleren.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Stap 3: alle uitgeschakelde abonnementen verwijderen

1. Ga in het Beheercentrum naar de pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten</a> factureren.

2. Als de lijst met abonnementen in de **tabel** weergave wordt weergegeven, selecteert u **kaarten**aan de rechterkant.

3. Selecteer naast **status van abonnement**de optie **uitgeschakeld**.

4. Zoek een uitgeschakeld abonnement, en selecteer in de sectie **instellingen & acties** de optie **verwijderen**.

5. Schakel in het dialoogvenster **abonnement verwijderen** het selectievakje **Ik weet het effect** in en selecteer vervolgens **abonnement verwijderen**.

6. Herhaal de stappen 4 en 5 totdat alle abonnementen zijn verwijderd voor elk uitgeschakeld abonnement.

## <a name="step-4-disable-multi-factor-authentication"></a>Stap 4: multi-factor Authentication uitschakelen

1. Ga in het Beheercentrum naar de pagina **gebruikers**van  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active Users</a> .

2. Kies **multi-factor Authentication**.

3. Schakel op de pagina multi-factor Authentication alle accounts uit, met uitzondering van het globale beheerdersaccount dat u momenteel gebruikt.

U kunt ook <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell gebruiken om meervoudige verificatie voor meerdere gebruikers uit te schakelen</a>.

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Stap 5: de map verwijderen in azure Active Directory

1. Meld u aan bij het <a href="https://aad.portal.azure.com/" target="_blank">Azure AD-Beheercentrum</a> met het account van een globale beheerder.

2. Selecteer **Azure Active Directory**.

3. Ga naar de map die u wilt verwijderen.

4. Selecteer **map verwijderen**.

5. Als er in de Directory een of meer controles mislukt, ziet u een koppeling naar meer informatie over het doorgeven van de controles. Wanneer u alle controles hebt uitgevoerd, selecteert u **verwijderen** om het proces te voltooien.

Wanneer u deze laatste stap hebt voltooid, wordt uw account met Microsoft gesloten en verwijderd.
