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
description: Meer informatie over het instellen van sterke wachtwoordvereisten voor uw gebruikers met Windows PowerShell.
ms.openlocfilehash: e2300e3c94de53cd04d0c1726538fdb8a86a1ccf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903534"
---
# <a name="turn-off-strong-password-requirements-for-users"></a><span data-ttu-id="8a953-103">Sterke wachtwoordvereisten voor gebruikers uitschakelen</span><span class="sxs-lookup"><span data-stu-id="8a953-103">Turn off strong password requirements for users</span></span>

<span data-ttu-id="8a953-104">In dit artikel wordt uitgelegd hoe u sterke wachtwoordvereisten voor uw gebruikers kunt uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="8a953-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="8a953-105">Sterke wachtwoordvereisten zijn standaard ingeschakeld in uw Microsoft 365 voor Bedrijven-organisatie.</span><span class="sxs-lookup"><span data-stu-id="8a953-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="8a953-106">Uw organisatie heeft mogelijk vereisten voor het uitschakelen van sterke wachtwoorden.</span><span class="sxs-lookup"><span data-stu-id="8a953-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="8a953-107">Volg de onderstaande stappen om sterke wachtwoordvereisten uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="8a953-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="8a953-108">U moet deze stappen met PowerShell voltooien.</span><span class="sxs-lookup"><span data-stu-id="8a953-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8a953-109">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="8a953-109">Before you begin</span></span>

<span data-ttu-id="8a953-110">Dit artikel is bedoeld voor personen die wachtwoordbeleid beheren voor een bedrijf, school of non-profitorganisatie.</span><span class="sxs-lookup"><span data-stu-id="8a953-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="8a953-111">Voor het uitvoeren van deze stappen moet u zich aanmelden met uw Microsoft 365-beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="8a953-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="8a953-112">Wat is een beheerdersaccount?</span><span class="sxs-lookup"><span data-stu-id="8a953-112">What's an admin account?</span></span>](../admin-overview/admin-overview.md) <span data-ttu-id="8a953-113">U moet een globale [beheerder of wachtwoordbeheerder zijn om](about-admin-roles.md) deze stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="8a953-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="8a953-114">U moet ook verbinding maken met Microsoft 365 met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a953-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="8a953-115">Sterke wachtwoorden instellen</span><span class="sxs-lookup"><span data-stu-id="8a953-115">Set strong passwords</span></span>

1. <span data-ttu-id="8a953-116">[Maak verbinding met Microsoft 365 met PowerShell.](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="8a953-116">[Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="8a953-117">Met PowerShell kunt u sterke wachtwoordvereisten uitschakelen voor alle gebruikers met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="8a953-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="8a953-118">De gebruikerPrincipalName moet zich in de aanmeldingsindeling voor internetstijl hebben, waar de gebruikersnaam wordt gevolgd door het bijteken (@) en een domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="8a953-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="8a953-119">Bijvoorbeeld: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8a953-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="8a953-120">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8a953-120">Related content</span></span>

[<span data-ttu-id="8a953-121">Verbinding maken met Microsoft 365 met PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a953-121">How to connect to Microsoft 365 with PowerShell</span></span>](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="8a953-122">Meer informatie over PowerShell MsolUser-opdrachten</span><span class="sxs-lookup"><span data-stu-id="8a953-122">More information on PowerShell MsolUser commands</span></span>](/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="8a953-123">Meer informatie over wachtwoordbeleid</span><span class="sxs-lookup"><span data-stu-id="8a953-123">More information on password policy</span></span>](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)