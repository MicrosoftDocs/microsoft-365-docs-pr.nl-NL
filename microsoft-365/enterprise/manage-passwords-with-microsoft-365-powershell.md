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
# <a name="manage-passwords-with-powershell"></a><span data-ttu-id="5b173-103">Wachtwoorden beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b173-103">Manage passwords with PowerShell</span></span>

<span data-ttu-id="5b173-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="5b173-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5b173-105">U kunt PowerShell voor Microsoft 365 als alternatief gebruiken voor het Beheercentrum van Microsoft 365 voor het beheren van wachtwoorden in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5b173-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage passwords in Microsoft 365.</span></span> 

<span data-ttu-id="5b173-106">Voer de volgende stappen uit als u in dit artikel de waarde van een variabele moet opgeven voor een opdracht blokkering in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="5b173-106">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="5b173-107">Kopieer het opdracht blok naar het Klembord en plak dit in Kladblok of in de ISE (Integrated script Environment) van PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b173-107">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="5b173-108">Vul de waarden voor de variabele in en verwijder de tekens "<" en ">".</span><span class="sxs-lookup"><span data-stu-id="5b173-108">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="5b173-109">Voer de opdrachten uit in het PowerShell-venster of in het PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="5b173-109">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="5b173-110">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="5b173-110">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="5b173-111">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="5b173-111">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="5b173-112">Een wachtwoord instellen</span><span class="sxs-lookup"><span data-stu-id="5b173-112">Set a password</span></span>

<span data-ttu-id="5b173-113">Met deze opdrachten kunt u een wachtwoord opgeven voor een gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="5b173-113">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="5b173-114">Een gebruiker dwingen hun wachtwoord te wijzigen</span><span class="sxs-lookup"><span data-stu-id="5b173-114">Force a user to change their password</span></span>

<span data-ttu-id="5b173-115">Met deze opdrachten kunt u een wachtwoord instellen en een gebruiker dwingen hun nieuwe wachtwoord te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="5b173-115">Use these commands to set a password and force a user to change their new password.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

<span data-ttu-id="5b173-116">Met deze opdrachten kunt u een wachtwoord instellen en een gebruiker dwingen hun nieuwe wachtwoord te wijzigen wanneer ze zich de volgende keer aanmelden.</span><span class="sxs-lookup"><span data-stu-id="5b173-116">Use these commands to set a password and force a user to change their new password the next time they sign in.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="5b173-117">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="5b173-117">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="5b173-118">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="5b173-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="5b173-119">Een wachtwoord instellen</span><span class="sxs-lookup"><span data-stu-id="5b173-119">Set a password</span></span>

<span data-ttu-id="5b173-120">Met deze opdrachten kunt u een wachtwoord opgeven voor een gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="5b173-120">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="5b173-121">Een gebruiker dwingen hun wachtwoord te wijzigen</span><span class="sxs-lookup"><span data-stu-id="5b173-121">Force a user to change their password</span></span>

<span data-ttu-id="5b173-122">Met deze opdrachten kunt u een gebruiker dwingen hun wachtwoord te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="5b173-122">Use these commands to force a user to change their password.</span></span>

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a><span data-ttu-id="5b173-123">Zie ook</span><span class="sxs-lookup"><span data-stu-id="5b173-123">See also</span></span>

[<span data-ttu-id="5b173-124">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b173-124">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5b173-125">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b173-125">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5b173-126">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5b173-126">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

