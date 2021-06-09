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
# <a name="manage-passwords-with-powershell"></a><span data-ttu-id="b41d6-103">Wachtwoorden beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="b41d6-103">Manage passwords with PowerShell</span></span>

<span data-ttu-id="b41d6-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b41d6-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b41d6-105">U kunt PowerShell voor Microsoft 365 gebruiken als alternatief voor het Microsoft 365 beheercentrum voor het beheren van wachtwoorden in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b41d6-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage passwords in Microsoft 365.</span></span> 

<span data-ttu-id="b41d6-106">Als voor een opdrachtblok in dit artikel variabele waarden moeten worden opgegeven, gebruikt u deze stappen.</span><span class="sxs-lookup"><span data-stu-id="b41d6-106">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="b41d6-107">Kopieer het opdrachtblok naar het klembord en plak het in Kladblok of de Geïntegreerde Scriptomgeving (ISE) van PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b41d6-107">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="b41d6-108">Vul de variabele waarden in en verwijder de tekens '<' en '>'.</span><span class="sxs-lookup"><span data-stu-id="b41d6-108">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="b41d6-109">Voer de opdrachten uit in het PowerShell-venster of de PowerShell-ise.</span><span class="sxs-lookup"><span data-stu-id="b41d6-109">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="b41d6-110">De powershell Azure Active Directory powershell gebruiken voor Graph module</span><span class="sxs-lookup"><span data-stu-id="b41d6-110">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="b41d6-111">Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="b41d6-111">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="b41d6-112">Een wachtwoord instellen</span><span class="sxs-lookup"><span data-stu-id="b41d6-112">Set a password</span></span>

<span data-ttu-id="b41d6-113">Gebruik deze opdrachten om een wachtwoord voor een gebruikersaccount op te geven.</span><span class="sxs-lookup"><span data-stu-id="b41d6-113">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="b41d6-114">Een gebruiker dwingen zijn of haar wachtwoord te wijzigen</span><span class="sxs-lookup"><span data-stu-id="b41d6-114">Force a user to change their password</span></span>

<span data-ttu-id="b41d6-115">Gebruik deze opdrachten om een wachtwoord in te stellen en een gebruiker te dwingen zijn of haar nieuwe wachtwoord te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b41d6-115">Use these commands to set a password and force a user to change their new password.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

<span data-ttu-id="b41d6-116">Gebruik deze opdrachten om een wachtwoord in te stellen en een gebruiker te dwingen het nieuwe wachtwoord te wijzigen wanneer deze zich de volgende keer aan melden.</span><span class="sxs-lookup"><span data-stu-id="b41d6-116">Use these commands to set a password and force a user to change their new password the next time they sign in.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="b41d6-117">Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b41d6-117">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="b41d6-118">Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="b41d6-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="b41d6-119">Een wachtwoord instellen</span><span class="sxs-lookup"><span data-stu-id="b41d6-119">Set a password</span></span>

<span data-ttu-id="b41d6-120">Gebruik deze opdrachten om een wachtwoord voor een gebruikersaccount op te geven.</span><span class="sxs-lookup"><span data-stu-id="b41d6-120">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="b41d6-121">Een gebruiker dwingen zijn of haar wachtwoord te wijzigen</span><span class="sxs-lookup"><span data-stu-id="b41d6-121">Force a user to change their password</span></span>

<span data-ttu-id="b41d6-122">Gebruik deze opdrachten om een gebruiker te dwingen zijn wachtwoord te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b41d6-122">Use these commands to force a user to change their password.</span></span>

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a><span data-ttu-id="b41d6-123">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b41d6-123">See also</span></span>

[<span data-ttu-id="b41d6-124">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="b41d6-124">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b41d6-125">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="b41d6-125">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b41d6-126">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b41d6-126">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

