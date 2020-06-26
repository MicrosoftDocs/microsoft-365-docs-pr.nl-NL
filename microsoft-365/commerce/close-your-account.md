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
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Meer informatie over het sluiten van uw account bij Microsoft.
ms.openlocfilehash: a92b9f2053d9acf4e8233bee7a42047f51288943
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2020
ms.locfileid: "44898919"
---
# <a name="close-your-account"></a>Uw account sluiten

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Wanneer u uw account bij Microsoft sluit, wordt alle informatie met betrekking tot uw account verwijderd. Deze informatie omvat abonnementen, licenties, betalingsmethoden, gebruikers en gebruikersgegevens. Voordat u dit proces start, moet u een back-up maken van alle gegevens die u wilt bewaren.

## <a name="step-1-delete-users"></a>Stap 1: Gebruikers verwijderen

Verwijder alle gebruikers, behalve één globale beheerder die de stappen voltooit om het account te sluiten. Voordat u de map aan het einde van dit proces verwijderen, moet u alle andere gebruikers verwijderen.

Als gebruikers worden gesynchroniseerd vanaf on-premises, schakelt u eerst synchronisatie uit en verwijdert u de gebruikers in de cloudmap met behulp van de Azure-portal of Azure PowerShell-cmdlets.

Zie <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">Beheerder gebruikersbeheer: Een of meer gebruikers verwijderen</a>als u gebruikers wilt verwijderen.

U ook de <a href="https://go.microsoft.com/fwlink/?linkid=842230">PowerShell-cmdlet Remove-MsolUser</a> gebruiken om gebruikers in bulk te verwijderen.

Als uw organisatie Active Directory gebruikt die synchroniseert met Azure AD, verwijdert u in plaats daarvan het gebruikersaccount uit Active Directory. Zie Gebruikers <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">voor bulkverwijding in Azure Active Directory voor</a>instructies.

## <a name="step-2-cancel-all-active-subscriptions"></a>Stap 2: Alle actieve abonnementen opzeggen

1. Ga in het beheercentrum naar de pagina **Facturering van**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten.</a>

2. Als de lijst met abonnementen zich in de **tabelweergave** bevindt, selecteert u aan de rechterkant **Kaarten**.

3. Zoek een actief abonnement en selecteer in de sectie **Instellingen & Acties** de optie Abonnement **opzeggen.**

4. Volg de aanwijzingen om het proces te voltooien.

5. Herhaal stap 1 tot en met 4 om alle actieve abonnementen op te zeggen.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Stap 3: Alle uitgeschakelde abonnementen verwijderen

1. Ga in het beheercentrum naar de pagina **Facturering van**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten.</a>

2. Als de lijst met abonnementen zich in de **tabelweergave** bevindt, selecteert u aan de rechterkant **Kaarten**.

3. Selecteer naast **de status Abonnement**de optie **Uitgeschakeld**.

4. Zoek een uitgeschakeld abonnement en selecteer in de sectie **Instellingen & Acties** de optie **Verwijderen**.

5. Schakel in het dialoogvenster **Abonnement verwijderen** het selectievakje Ik begrijp het **effect in** en schakel **vervolgens Abonnement verwijderen**in.

6. Voor elk uitgeschakeld abonnement worden stap 4 en 5 herhaald totdat alle abonnementen zijn verwijderd.

## <a name="step-4-disable-multi-factor-authentication"></a>Stap 4: Meervoudige verificatie uitschakelen

1. Ga in het beheercentrum **Users**naar de pagina  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Gebruikers actieve gebruikers.</a>

2. Kies **Multi-factor authenticatie**.

3. Schakel op de pagina meervoudige verificatie alle accounts uit, behalve voor het algemene beheerdersaccount dat u momenteel gebruikt.

U PowerShell ook <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">gebruiken om meervoudige verificatie voor meerdere gebruikers uit te schakelen.</a>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Stap 5: De map verwijderen in Azure Active Directory

1. Meld u aan bij het <a href="https://aad.portal.azure.com/" target="_blank">Azure AD-beheercentrum</a> met een global administrator-account.

2. Selecteer **Azure Active Directory**.

3. Overschakelen naar de map die u wilt verwijderen.

4. Selecteer **Map verwijderen**.

5. Als uw map een of meer controles uitvalt, ziet u een koppeling naar meer informatie over het slagen van de controles. Nadat u alle controles hebt voltooid, selecteert u **Verwijderen** om het proces te voltooien.

Nadat u deze laatste stap hebt voltooid, wordt uw account bij Microsoft gesloten en verwijderd.
