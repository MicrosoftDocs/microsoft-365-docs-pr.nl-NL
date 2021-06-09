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
# <a name="turn-off-strong-password-requirements-for-users"></a><span data-ttu-id="7e872-103">Sterke wachtwoordvereisten voor gebruikers uitschakelen</span><span class="sxs-lookup"><span data-stu-id="7e872-103">Turn off strong password requirements for users</span></span>

<span data-ttu-id="7e872-104">In dit artikel wordt uitgelegd hoe u sterke wachtwoordvereisten voor uw gebruikers kunt uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="7e872-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="7e872-105">Sterke wachtwoordvereisten zijn standaard ingeschakeld in uw Microsoft 365 voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="7e872-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="7e872-106">Uw organisatie heeft mogelijk vereisten voor het uitschakelen van sterke wachtwoorden.</span><span class="sxs-lookup"><span data-stu-id="7e872-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="7e872-107">Volg de onderstaande stappen om sterke wachtwoordvereisten uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="7e872-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="7e872-108">U moet deze stappen met PowerShell voltooien.</span><span class="sxs-lookup"><span data-stu-id="7e872-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7e872-109">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="7e872-109">Before you begin</span></span>

<span data-ttu-id="7e872-110">Dit artikel is bedoeld voor personen die wachtwoordbeleid beheren voor een bedrijf, school of non-profitorganisatie.</span><span class="sxs-lookup"><span data-stu-id="7e872-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="7e872-111">Voor het uitvoeren van deze stappen moet u zich aanmelden met uw Microsoft 365-beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="7e872-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="7e872-112">Wat is een beheerdersaccount?</span><span class="sxs-lookup"><span data-stu-id="7e872-112">What's an admin account?</span></span>](/microsoft-365/business-video/admin-center-overview) <span data-ttu-id="7e872-113">U moet een globale [beheerder of wachtwoordbeheerder zijn om](about-admin-roles.md) deze stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="7e872-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="7e872-114">U moet ook verbinding maken met Microsoft 365 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7e872-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="7e872-115">Sterke wachtwoorden instellen</span><span class="sxs-lookup"><span data-stu-id="7e872-115">Set strong passwords</span></span>

1. <span data-ttu-id="7e872-116">[Verbinding maken om Microsoft 365 powershell te gebruiken.](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="7e872-116">[Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="7e872-117">Met PowerShell kunt u sterke wachtwoordvereisten uitschakelen voor alle gebruikers met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="7e872-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="7e872-118">De gebruikerPrincipalName moet zich in de aanmeldingsindeling voor internetstijl hebben, waar de gebruikersnaam wordt gevolgd door het bijteken (@) en een domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="7e872-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="7e872-119">Bijvoorbeeld: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7e872-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="7e872-120">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="7e872-120">Related content</span></span>

[<span data-ttu-id="7e872-121">Verbinding maken met Microsoft 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="7e872-121">How to connect to Microsoft 365 with PowerShell</span></span>](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="7e872-122">Meer informatie over PowerShell MsolUser-opdrachten</span><span class="sxs-lookup"><span data-stu-id="7e872-122">More information on PowerShell MsolUser commands</span></span>](/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="7e872-123">Meer informatie over wachtwoordbeleid</span><span class="sxs-lookup"><span data-stu-id="7e872-123">More information on password policy</span></span>](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)