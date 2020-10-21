---
title: Sterke wachtwoordvereisten voor gebruikers instellen
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Informatie over het instellen van krachtige wachtwoordvereisten voor uw gebruikers met behulp van Windows PowerShell.
ms.openlocfilehash: 1634e2f0de2cdd2cac5e1928adbef54457e50716
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626141"
---
# <a name="set-strong-password-requirement-for-users"></a>Sterke wachtwoordvereisten voor gebruikers instellen

In dit artikel wordt uitgelegd hoe u vereisten voor sterke wachtwoorden instelt voor uw gebruikers. U moet deze stappen uitvoeren met PowerShell.

## <a name="before-you-begin"></a>Voordat u begint

Dit artikel is bedoeld voor personen die het wachtwoordbeleid voor een bedrijf, school of non-profit organisatie beheren. Voor het uitvoeren van deze stappen moet u zich aanmelden met uw Microsoft 365-beheerdersaccount. [Wat is een beheerdersaccount?](../admin-overview/admin-overview.md). U moet een [globale beheerder of wachtwoordbeheerder](about-admin-roles.md) zijn om deze stappen te kunnen uitvoeren.

U moet ook verbinding maken met Microsoft 365 met PowerShell.

## <a name="set-strong-passwords"></a>Sterke wachtwoorden instellen

1. [Maak verbinding met Microsoft 365 met PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. Met behulp van PowerShell kunt u sterke wachtwoordvereisten voor alle gebruikers inschakelen met de volgende opdracht:

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $true

3. You can turn on strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $true
    ```

> [!NOTE]
> De userPrincipalName moet de Internet stijl hebben, waarbij de gebruikersnaam wordt gevolgd door het apenstaartje (@) en een domeinnaam. Bijvoorbeeld: user@contoso.com.

## <a name="related-content"></a>Verwante onderwerpen

[Verbinding maken met Microsoft 365 met PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[Meer informatie over PowerShell MsolUser-opdrachten](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[Meer informatie over wachtwoordbeleid](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)