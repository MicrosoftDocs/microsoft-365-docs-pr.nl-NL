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
ms.openlocfilehash: 44428654946d31ad249bfd3e7a3609da3e3634a6
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860545"
---
# <a name="close-your-account"></a>Uw account sluiten

Wanneer u uw account bij Microsoft sluit, wordt alle informatie met betrekking tot uw account verwijderd. Deze informatie omvat abonnementen, licenties, betalingsmethoden, gebruikers en gebruikersgegevens.

## <a name="before-you-begin"></a>Voordat u begint

Voordat u dit proces start, moet u een back-up maken van alle gegevens die u wilt behouden.

U moet een Globale of Factureringsbeheerder zijn om de stappen in dit artikel uit te voeren. Zie[Over beheerdersrollen](../admin/add-users/about-admin-roles.md) voor meer informatie.

## <a name="step-1-delete-users"></a>Stap 1: Gebruikers verwijderen

Verwijder alle gebruikers, behalve één globale beheerder. De globale beheerder voltooit de stappen om het account te sluiten. Voordat u de adreslijst aan het einde van dit proces kunt verwijderen, moet u alle andere gebruikers verwijderen.

Als gebruikers on-premises worden gesynchroniseerd, moet u eerst synchronisatie uitschakelen en vervolgens de gebruikers in de cloudmap verwijderen met behulp van de Azure-portal of Azure PowerShell-cmdlets.

Zie Gebruikersbeheerbeheerder als u gebruikers wilt <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">verwijderen: Een of meer gebruikers verwijderen.</a>

U kunt ook de <a href="https://docs.microsoft.com/powershell/module/msonline/remove-msoluser">cmdlet Remove-MsolUser</a> PowerShell gebruiken om gebruikers bulksgewijs te verwijderen.

Als uw organisatie Active Directory gebruikt dat wordt gesynchroniseerd met Microsoft Azure Active Directory (Azure AD), verwijdert u in plaats daarvan het gebruikersaccount uit Active Directory. Zie Gebruikers <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">bulksgewijs verwijderen in Azure Active Directory</a>voor instructies.

## <a name="step-2-cancel-all-active-subscriptions"></a>Stap 2: Alle actieve abonnementen opzeggen

1. Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.
2. Zoek op **het** tabblad Producten naar een actief abonnement. Selecteer **Meer acties** (drie puntjes) en selecteer **Abonnement annuleren**.
3. Kies in het deelvenster **Abonnement annuleren** een reden waarom u wilt opzeggen. Geef desgewenst feedback.
4. Kies **Opslaan**.
5. Herhaal stap 1 tot en met 4 om alle actieve abonnementen te annuleren.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Stap 3: Alle uitgeschakelde abonnementen verwijderen

1. Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.
2. Selecteer op **het** tabblad Producten een uitgeschakeld abonnement.
3. Selecteer op de pagina Abonnementsgegevens in de sectie **Abonnements-** en betalingsinstellingen de optie **Abonnement verwijderen.**
4. Selecteer in **het deelvenster** Abonnement verwijderen de optie **Abonnement verwijderen.**
5. Selecteer ja **in het** dialoogvenster Abonnement **verwijderen.**
6. Herhaal stap 3 tot en met 5 voor elk uitgeschakeld abonnement totdat alle abonnementen worden verwijderd.

> [!NOTE]
> Als u een uitgeschakeld abonnement niet direct kunt verwijderen, <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">neem dan contact op met ondersteuning</a>

## <a name="step-4-disable-multi-factor-authentication"></a>Stap 4: Meervoudige verificatie uitschakelen

1. Meld u aan bij het beheercentrum met een globale beheerdersaccount. Zie Beheerdersrollen controleren in uw organisatie als u wilt controleren welke rollen [u hebt.](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)
2. Ga naar de **pagina Actieve** gebruikers  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">van gebruikers.</a>
3. Kies **Meervoudige verificatie.**
4. Schakel op de pagina meervoudige verificatie alle accounts uit, behalve het globale beheerdersaccount dat u momenteel gebruikt.

U kunt <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell ook gebruiken om meervoudige</a>verificatie voor meerdere gebruikers uit te schakelen.

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Stap 5: De adreslijst verwijderen in Azure Active Directory

1. Meld u aan bij <a href="https://aad.portal.azure.com/" target="_blank">het Azure AD-beheercentrum</a> met een globale beheerdersaccount.
2. Selecteer **Azure Active Directory**.
3. Ga naar de organisatie die u wilt verwijderen.
4. Selecteer **Tenant verwijderen.**
5. Als uw organisatie een of meer controles mislukt, ziet u een koppeling naar meer informatie over het doorgeven van de controles. Nadat u alle controles hebt uitgevoerd, **selecteert u Verwijderen om** het proces te voltooien.

Nadat u deze laatste stap hebt voltooid, wordt uw account bij Microsoft gesloten en verwijderd.