---
title: Wachtwoorden beheren met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- O365ITProTrain
description: Meer informatie over het gebruik van PowerShell voor het beheren van wachtwoorden.
ms.openlocfilehash: ac0a47edb4ccbed93c1a3b88df083d463784b4a4
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073196"
---
# <a name="manage-passwords-with-powershell"></a>Wachtwoorden beheren met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

U kunt PowerShell voor Microsoft 365 als alternatief gebruiken voor het Beheercentrum van Microsoft 365 voor het beheren van wachtwoorden in Microsoft 365. 

Voer de volgende stappen uit als u in dit artikel de waarde van een variabele moet opgeven voor een opdracht blokkering in dit artikel.

1. Kopieer het opdracht blok naar het Klembord en plak dit in Kladblok of in de ISE (Integrated script Environment) van PowerShell.
2. Vul de waarden voor de variabele in en verwijder de tekens "<" en ">".
3. Voer de opdrachten uit in het PowerShell-venster of in het PowerShell-ISE.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph module gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

### <a name="set-a-password"></a>Een wachtwoord instellen

Met deze opdrachten kunt u een wachtwoord opgeven voor een gebruikersaccount.

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a>Een gebruiker dwingen hun wachtwoord te wijzigen

Met deze opdrachten kunt u een wachtwoord instellen en een gebruiker dwingen hun nieuwe wachtwoord te wijzigen.

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

Met deze opdrachten kunt u een wachtwoord instellen en een gebruiker dwingen hun nieuwe wachtwoord te wijzigen wanneer ze zich de volgende keer aanmelden.

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="set-a-password"></a>Een wachtwoord instellen

Met deze opdrachten kunt u een wachtwoord opgeven voor een gebruikersaccount.

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a>Een gebruiker dwingen hun wachtwoord te wijzigen

Met deze opdrachten kunt u een gebruiker dwingen hun wachtwoord te wijzigen.

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)

