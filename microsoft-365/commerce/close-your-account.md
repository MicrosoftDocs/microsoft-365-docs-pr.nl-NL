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
ms.openlocfilehash: bdcf4408ddc9c198fab1d68b4c096fad9059b975
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376315"
---
# <a name="close-your-account"></a>Uw account sluiten

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Wanneer u uw account bij Microsoft sluit, wordt alle informatie met betrekking tot uw account verwijderd. Deze informatie omvat abonnementen, licenties, betalingsmethoden, gebruikers en gebruikersgegevens.

## <a name="before-you-begin"></a>Voordat u begint

Voordat u dit proces start, moet u een back-up maken van alle gegevens die u wilt behouden.

U moet een globale beheerder of Factureringsbeheerder zijn om de taken in dit artikel uit te voeren. Raadpleeg [Over beheerdersrollen](../admin/add-users/about-admin-roles.md) voor meer informatie.

## <a name="step-1-delete-users"></a>Stap 1: gebruikers verwijderen

Verwijder alle gebruikers behalve één globale beheerder. De globale beheerder voert de stappen uit om het account te sluiten. Voordat u de map aan het einde van dit proces kunt verwijderen, moet u alle andere gebruikers verwijderen.

Als gebruikers worden gesynchroniseerd vanuit on-premises, moet u eerst synchroniseren uitschakelen en vervolgens de gebruikers in de Cloud Directory verwijderen met behulp van de cmdlets van Azure portal of Azure PowerShell.

Zie <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">gebruikers van Gebruikersbeheer: een of meer gebruikers verwijderen</a>om gebruikers te verwijderen.

U kunt de PowerShell <a href="https://go.microsoft.com/fwlink/?linkid=842230">-cmdlet Remove-MsolUser</a> ook gebruiken om gebruikers bulksgewijs te verwijderen.

Als uw organisatie gebruikmaakt van Active Directory die wordt gesynchroniseerd met Microsoft Azure Active Directory (Azure AD), verwijdert u in plaats daarvan het gebruikersaccount uit Active Directory. Zie voor instructies een <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">bulk verwijdering van gebruikers in azure Active Directory</a>.

## <a name="step-2-cancel-all-active-subscriptions"></a>Stap 2: alle actieve abonnementen annuleren

1. Ga in het Beheercentrum naar de pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten</a> factureren.
2. Zoek op het tabblad **Products** een actief abonnement. Selecteer **meer acties** (drie puntjes) en selecteer vervolgens **abonnement annuleren**.
3. Kies in het deelvenster **abonnement annuleren** een reden waarom u wilt opzeggen. U kunt ook feedback geven.
4. Klik op **Opslaan**.
5. Herhaal de stappen 1 tot en met 4 om alle actieve abonnementen te annuleren.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Stap 3: alle uitgeschakelde abonnementen verwijderen

1. Ga in het Beheercentrum naar de pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten</a> factureren.
2. Selecteer op het tabblad **Products** een uitgeschakeld abonnement.
3. Selecteer op de pagina Details van abonnement in de sectie **Abonnementen en betalings instellingen** de optie **abonnement verwijderen**.
4. Selecteer in het deelvenster **abonnement verwijderen** de optie **abonnement verwijderen**.
5. Selecteer in het dialoogvenster **abonnement verwijderen** de optie **Ja**.
6. Herhaal de stappen 3 tot en met 5 voor elk uitgeschakeld abonnement totdat alle abonnementen worden verwijderd.

> [!NOTE]
> <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">Neem contact op met de ondersteuning</a> als u een uitgeschakeld abonnement niet onmiddellijk kunt verwijderen.

## <a name="step-4-disable-multi-factor-authentication"></a>Stap 4: multi-factor Authentication uitschakelen

1. Meld u aan bij het Beheercentrum met het account van een globale beheerder. Raadpleeg [beheerdersrollen in uw organisatie controleren](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)om te controleren welke rollen u hebt.
2. Ga naar de pagina **gebruikers** van  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active Users</a> .
3. Kies **multi-factor Authentication**.
4. Schakel op de pagina multi-factor Authentication alle accounts uit, met uitzondering van het globale beheerdersaccount dat u momenteel gebruikt.

U kunt ook <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell gebruiken om meervoudige verificatie voor meerdere gebruikers uit te schakelen</a>.

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Stap 5: de map verwijderen in azure Active Directory

1. Meld u aan bij het <a href="https://aad.portal.azure.com/" target="_blank">Azure AD-Beheercentrum</a> met het account van een globale beheerder.
2. Selecteer **Azure Active Directory**.
3. Ga naar de organisatie die u wilt verwijderen.
4. Selecteer **Tenant verwijderen**.
5. Als in uw organisatie een of meer controles mislukt, ziet u een koppeling naar meer informatie over het doorgeven van de controles. Wanneer u alle controles hebt uitgevoerd, selecteert u **verwijderen** om het proces te voltooien.

Wanneer u deze laatste stap hebt voltooid, wordt uw account met Microsoft gesloten en verwijderd.