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
ms.openlocfilehash: 9f6fd61396d99245ffeabf757d3cb65c5d5cb85e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646617"
---
# <a name="set-strong-password-requirement-for-users"></a><span data-ttu-id="a5a9e-103">Sterke wachtwoordvereisten voor gebruikers instellen</span><span class="sxs-lookup"><span data-stu-id="a5a9e-103">Set strong password requirement for users</span></span>

<span data-ttu-id="a5a9e-104">In dit artikel wordt uitgelegd hoe u sterke wachtwoordvereisten voor uw gebruikers uitschakelt.</span><span class="sxs-lookup"><span data-stu-id="a5a9e-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="a5a9e-105">Sterke wachtwoordvereisten zijn standaard ingeschakeld in de organisatie Microsoft 365 voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="a5a9e-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="a5a9e-106">Uw organisatie heeft mogelijk vereisten voor het uitschakelen van sterke wachtwoorden.</span><span class="sxs-lookup"><span data-stu-id="a5a9e-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="a5a9e-107">Voer de onderstaande stappen uit om sterke wachtwoordvereisten uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="a5a9e-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="a5a9e-108">U moet deze stappen uitvoeren met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a5a9e-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a5a9e-109">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="a5a9e-109">Before you begin</span></span>

<span data-ttu-id="a5a9e-110">Dit artikel is bedoeld voor personen die het wachtwoordbeleid voor een bedrijf, school of non-profit organisatie beheren.</span><span class="sxs-lookup"><span data-stu-id="a5a9e-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="a5a9e-111">Voor het uitvoeren van deze stappen moet u zich aanmelden met uw Microsoft 365-beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="a5a9e-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="a5a9e-112">Wat is een beheerdersaccount?</span><span class="sxs-lookup"><span data-stu-id="a5a9e-112">What's an admin account?</span></span>](../admin-overview/admin-overview.md) <span data-ttu-id="a5a9e-113">U moet een [globale beheerder of wachtwoordbeheerder](about-admin-roles.md) zijn om deze stappen te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="a5a9e-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="a5a9e-114">U moet ook verbinding maken met Microsoft 365 met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a5a9e-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="a5a9e-115">Sterke wachtwoorden instellen</span><span class="sxs-lookup"><span data-stu-id="a5a9e-115">Set strong passwords</span></span>

1. <span data-ttu-id="a5a9e-116">[Maak verbinding met Microsoft 365 met PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="a5a9e-116">[Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="a5a9e-117">Met behulp van PowerShell kunt u sterke wachtwoordvereisten voor alle gebruikers uitschakelen met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="a5a9e-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="a5a9e-118">De userPrincipalName moet de Internet stijl hebben, waarbij de gebruikersnaam wordt gevolgd door het apenstaartje (@) en een domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="a5a9e-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="a5a9e-119">Bijvoorbeeld: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a5a9e-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="a5a9e-120">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="a5a9e-120">Related content</span></span>

[<span data-ttu-id="a5a9e-121">Verbinding maken met Microsoft 365 met PowerShell</span><span class="sxs-lookup"><span data-stu-id="a5a9e-121">How to connect to Microsoft 365 with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="a5a9e-122">Meer informatie over PowerShell MsolUser-opdrachten</span><span class="sxs-lookup"><span data-stu-id="a5a9e-122">More information on PowerShell MsolUser commands</span></span>](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="a5a9e-123">Meer informatie over wachtwoordbeleid</span><span class="sxs-lookup"><span data-stu-id="a5a9e-123">More information on password policy</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)