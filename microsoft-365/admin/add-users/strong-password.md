---
title: Sterke wachtwoordvereisten voor gebruikers uitschakelen
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
description: Informatie over het instellen van sterke wachtwoordvereisten voor uw gebruikers met behulp van Windows PowerShell.
ms.openlocfilehash: 898eaf30d813e883e88c3ccc8ff500d72ae72854
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840656"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>Sterke wachtwoordvereisten voor gebruikers uitschakelen

In dit artikel wordt uitgelegd hoe u sterke wachtwoordvereisten voor uw gebruikers kunt uitschakelen. Sterke wachtwoordvereisten zijn standaard ingeschakeld in uw Microsoft 365 voor bedrijven. Uw organisatie heeft mogelijk vereisten voor het uitschakelen van sterke wachtwoorden. Volg de onderstaande stappen om sterke wachtwoordvereisten uit te schakelen. U moet deze stappen met PowerShell voltooien.

## <a name="before-you-begin"></a>Voordat u begint

Dit artikel is bedoeld voor personen die wachtwoordbeleid beheren voor een bedrijf, school of non-profitorganisatie. Voor het uitvoeren van deze stappen moet u zich aanmelden met uw Microsoft 365-beheerdersaccount. [Wat is een beheerdersaccount?](/microsoft-365/business-video/admin-center-overview) U moet een globale [beheerder of wachtwoordbeheerder zijn om](about-admin-roles.md) deze stappen uit te voeren.

U moet ook verbinding maken met Microsoft 365 PowerShell.

## <a name="set-strong-passwords"></a>Sterke wachtwoorden instellen

1. [Verbinding maken om Microsoft 365 powershell te gebruiken.](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

2. Met PowerShell kunt u sterke wachtwoordvereisten uitschakelen voor alle gebruikers met de volgende opdracht:

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> De gebruikerPrincipalName moet zich in de aanmeldingsindeling voor internetstijl hebben, waar de gebruikersnaam wordt gevolgd door het bijteken (@) en een domeinnaam. Bijvoorbeeld: user@contoso.com.

## <a name="related-content"></a>Verwante onderwerpen

[Verbinding maken met Microsoft 365 PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[Meer informatie over PowerShell MsolUser-opdrachten](/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[Meer informatie over wachtwoordbeleid](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)