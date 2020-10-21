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
# <a name="set-strong-password-requirement-for-users"></a><span data-ttu-id="0c245-103">Sterke wachtwoordvereisten voor gebruikers instellen</span><span class="sxs-lookup"><span data-stu-id="0c245-103">Set strong password requirement for users</span></span>

<span data-ttu-id="0c245-104">In dit artikel wordt uitgelegd hoe u vereisten voor sterke wachtwoorden instelt voor uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="0c245-104">This article explains how to set strong password requirements for your users.</span></span> <span data-ttu-id="0c245-105">U moet deze stappen uitvoeren met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c245-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0c245-106">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="0c245-106">Before you begin</span></span>

<span data-ttu-id="0c245-107">Dit artikel is bedoeld voor personen die het wachtwoordbeleid voor een bedrijf, school of non-profit organisatie beheren.</span><span class="sxs-lookup"><span data-stu-id="0c245-107">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="0c245-108">Voor het uitvoeren van deze stappen moet u zich aanmelden met uw Microsoft 365-beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="0c245-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="0c245-109">[Wat is een beheerdersaccount?](../admin-overview/admin-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0c245-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> <span data-ttu-id="0c245-110">U moet een [globale beheerder of wachtwoordbeheerder](about-admin-roles.md) zijn om deze stappen te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="0c245-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="0c245-111">U moet ook verbinding maken met Microsoft 365 met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c245-111">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="0c245-112">Sterke wachtwoorden instellen</span><span class="sxs-lookup"><span data-stu-id="0c245-112">Set strong passwords</span></span>

1. <span data-ttu-id="0c245-113">[Maak verbinding met Microsoft 365 met PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="0c245-113">[Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="0c245-114">Met behulp van PowerShell kunt u sterke wachtwoordvereisten voor alle gebruikers inschakelen met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="0c245-114">Using PowerShell, you can turn on strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $true

3. You can turn on strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $true
    ```

> [!NOTE]
> <span data-ttu-id="0c245-115">De userPrincipalName moet de Internet stijl hebben, waarbij de gebruikersnaam wordt gevolgd door het apenstaartje (@) en een domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="0c245-115">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="0c245-116">Bijvoorbeeld: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0c245-116">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="0c245-117">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="0c245-117">Related content</span></span>

[<span data-ttu-id="0c245-118">Verbinding maken met Microsoft 365 met PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c245-118">How to connect to Microsoft 365 with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="0c245-119">Meer informatie over PowerShell MsolUser-opdrachten</span><span class="sxs-lookup"><span data-stu-id="0c245-119">More information on PowerShell MsolUser commands</span></span>](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="0c245-120">Meer informatie over wachtwoordbeleid</span><span class="sxs-lookup"><span data-stu-id="0c245-120">More information on password policy</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)