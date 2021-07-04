---
title: Basismachtigingen gebruiken om toegang te krijgen tot Microsoft Defender-beveiligingscentrum
description: Meer informatie over het gebruik van basismachtigingen voor toegang tot de Microsoft Defender for Endpoint-portal.
keywords: gebruikersrollen toewijzen, lees- en schrijftoegang toewijzen, alleen-lezentoegang toewijzen, gebruiker, gebruikersrollen, rollen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e7c208998e436245c53b90905858b7cf7ebe91d6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290193"
---
# <a name="use-basic-permissions-to-access-the-portal"></a><span data-ttu-id="10e20-104">Basismachtigingen gebruiken voor toegang tot de portal</span><span class="sxs-lookup"><span data-stu-id="10e20-104">Use basic permissions to access the portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="10e20-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="10e20-105">**Applies to:**</span></span>
- <span data-ttu-id="10e20-106">Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="10e20-106">Azure Active Directory</span></span>
- [<span data-ttu-id="10e20-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="10e20-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="10e20-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="10e20-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="10e20-109">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="10e20-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="10e20-110">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="10e20-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

<span data-ttu-id="10e20-111">Raadpleeg de onderstaande instructies voor het gebruik van basismachtigingenbeheer.</span><span class="sxs-lookup"><span data-stu-id="10e20-111">Refer to the instructions below to use basic permissions management.</span></span>

<span data-ttu-id="10e20-112">U kunt een van de volgende oplossingen gebruiken:</span><span class="sxs-lookup"><span data-stu-id="10e20-112">You can use either of the following solutions:</span></span>
- <span data-ttu-id="10e20-113">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="10e20-113">Azure PowerShell</span></span>
- <span data-ttu-id="10e20-114">Azure-portal</span><span class="sxs-lookup"><span data-stu-id="10e20-114">Azure portal</span></span>

<span data-ttu-id="10e20-115">Voor gedetailleerde controle over machtigingen schakelt u over naar toegangsbesturingselement [op basis van rollen.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="10e20-115">For granular control over permissions, [switch to role-based access control](rbac.md).</span></span>

## <a name="assign-user-access-using-azure-powershell"></a><span data-ttu-id="10e20-116">Gebruikerstoegang toewijzen met Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="10e20-116">Assign user access using Azure PowerShell</span></span>
<span data-ttu-id="10e20-117">U kunt gebruikers toewijzen met een van de volgende machtigingsniveaus:</span><span class="sxs-lookup"><span data-stu-id="10e20-117">You can assign users with one of the following levels of permissions:</span></span>
- <span data-ttu-id="10e20-118">Volledige toegang (lezen en schrijven)</span><span class="sxs-lookup"><span data-stu-id="10e20-118">Full access (Read and Write)</span></span>
- <span data-ttu-id="10e20-119">Alleen-lezen toegang</span><span class="sxs-lookup"><span data-stu-id="10e20-119">Read-only access</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="10e20-120">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="10e20-120">Before you begin</span></span>

- <span data-ttu-id="10e20-121">Installeer Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10e20-121">Install Azure PowerShell.</span></span> <span data-ttu-id="10e20-122">Zie Het installeren en configureren van Azure PowerShell voor [meer informatie.](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)</span><span class="sxs-lookup"><span data-stu-id="10e20-122">For more information, see, [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span></span><br>

    > [!NOTE]
    > <span data-ttu-id="10e20-123">U moet de PowerShell-cmdlets uitvoeren op een verhoogde opdrachtregel.</span><span class="sxs-lookup"><span data-stu-id="10e20-123">You need to run the PowerShell cmdlets in an elevated command-line.</span></span>

- <span data-ttu-id="10e20-124">Verbinding maken naar uw Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="10e20-124">Connect to your Azure Active Directory.</span></span> <span data-ttu-id="10e20-125">Zie [Verbinding maken-MsolService](/powershell/module/msonline/connect-msolservice)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="10e20-125">For more information, see [Connect-MsolService](/powershell/module/msonline/connect-msolservice).</span></span>

<span data-ttu-id="10e20-126">**Volledige toegang**</span><span class="sxs-lookup"><span data-stu-id="10e20-126">**Full access**</span></span> <br>
<span data-ttu-id="10e20-127">Gebruikers met volledige toegang kunnen zich aanmelden, alle systeemgegevens bekijken en waarschuwingen oplossen, bestanden indienen voor uitgebreide analyse en het onboarding-pakket downloaden.</span><span class="sxs-lookup"><span data-stu-id="10e20-127">Users with full access can log in, view all system information and resolve alerts, submit files for deep analysis, and download the onboarding package.</span></span>
<span data-ttu-id="10e20-128">Als u volledige toegangsrechten toewijst, moeten de gebruikers worden toegevoegd aan de ingebouwde rollen 'Beveiligingsbeheerder' of 'Globale beheerder'.</span><span class="sxs-lookup"><span data-stu-id="10e20-128">Assigning full access rights requires adding the users to the "Security Administrator" or "Global Administrator" AAD built-in roles.</span></span>

<span data-ttu-id="10e20-129">**Alleen-lezen toegang**</span><span class="sxs-lookup"><span data-stu-id="10e20-129">**Read-only access**</span></span> <br>
<span data-ttu-id="10e20-130">Gebruikers met alleen-lezen toegang kunnen zich aanmelden, alle waarschuwingen en gerelateerde informatie bekijken.</span><span class="sxs-lookup"><span data-stu-id="10e20-130">Users with read-only access can log in, view all alerts, and related information.</span></span>
<span data-ttu-id="10e20-131">Ze kunnen geen waarschuwingstoestanden wijzigen, bestanden indienen voor uitgebreide analyse of statuswijzigingsbewerkingen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="10e20-131">They will not be able to change alert states, submit files for deep analysis or perform any state changing operations.</span></span>
<span data-ttu-id="10e20-132">Als u alleen-lezentoegangsrechten toewijst, moeten de gebruikers worden toegevoegd aan de ingebouwde azure AD-rol 'Beveiligingslezer'.</span><span class="sxs-lookup"><span data-stu-id="10e20-132">Assigning read-only access rights requires adding the users to the "Security Reader" Azure AD built-in role.</span></span>

<span data-ttu-id="10e20-133">Gebruik de volgende stappen om beveiligingsrollen toe te wijzen:</span><span class="sxs-lookup"><span data-stu-id="10e20-133">Use the following steps to assign security roles:</span></span>

- <span data-ttu-id="10e20-134">Voor **lees- en schrijftoegang** wijst u gebruikers toe aan de rol van beveiligingsbeheerder met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="10e20-134">For **read and write** access, assign users to the security administrator role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- <span data-ttu-id="10e20-135">Voor **alleen-lezentoegang** wijst u gebruikers toe aan de rol van de beveiligingslezer met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="10e20-135">For **read-only** access, assign users to the security reader role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

<span data-ttu-id="10e20-136">Zie Groepsleden [toevoegen of](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)verwijderen met behulp van Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="10e20-136">For more information, see [Add or remove group members using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).</span></span>

## <a name="assign-user-access-using-the-azure-portal"></a><span data-ttu-id="10e20-137">Gebruikerstoegang toewijzen met de Azure-portal</span><span class="sxs-lookup"><span data-stu-id="10e20-137">Assign user access using the Azure portal</span></span>

<span data-ttu-id="10e20-138">Zie Beheerders- en [niet-beheerdersrollen](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)toewijzen aan gebruikers met Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="10e20-138">For more information, see [Assign administrator and non-administrator roles to users with Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>

## <a name="related-topic"></a><span data-ttu-id="10e20-139">Verwant onderwerp</span><span class="sxs-lookup"><span data-stu-id="10e20-139">Related topic</span></span>

- [<span data-ttu-id="10e20-140">Portaltoegang beheren met RBAC</span><span class="sxs-lookup"><span data-stu-id="10e20-140">Manage portal access using RBAC</span></span>](rbac.md)
