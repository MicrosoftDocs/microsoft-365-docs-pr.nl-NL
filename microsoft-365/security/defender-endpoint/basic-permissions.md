---
title: Basismachtigingen gebruiken om toegang te krijgen tot het Microsoft Defender-beveiligingscentrum
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
ms.openlocfilehash: cb5762d2a9e4b62432aba6dacd1033ddc3c7daf2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163669"
---
# <a name="use-basic-permissions-to-access-the-portal"></a><span data-ttu-id="d8571-104">Basismachtigingen gebruiken om toegang te krijgen tot de portal</span><span class="sxs-lookup"><span data-stu-id="d8571-104">Use basic permissions to access the portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d8571-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d8571-105">**Applies to:**</span></span>
- <span data-ttu-id="d8571-106">Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d8571-106">Azure Active Directory</span></span>
- [<span data-ttu-id="d8571-107">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="d8571-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d8571-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8571-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d8571-109">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="d8571-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d8571-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="d8571-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

<span data-ttu-id="d8571-111">Raadpleeg de onderstaande instructies voor het gebruik van basismachtigingenbeheer.</span><span class="sxs-lookup"><span data-stu-id="d8571-111">Refer to the instructions below to use basic permissions management.</span></span>

<span data-ttu-id="d8571-112">U kunt een van de volgende oplossingen gebruiken:</span><span class="sxs-lookup"><span data-stu-id="d8571-112">You can use either of the following solutions:</span></span>
- <span data-ttu-id="d8571-113">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8571-113">Azure PowerShell</span></span>
- <span data-ttu-id="d8571-114">Azure-portal</span><span class="sxs-lookup"><span data-stu-id="d8571-114">Azure portal</span></span>

<span data-ttu-id="d8571-115">Voor gedetailleerde controle over machtigingen schakelt u over naar toegangsbesturingselement [op basis van rollen.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="d8571-115">For granular control over permissions, [switch to role-based access control](rbac.md).</span></span>

## <a name="assign-user-access-using-azure-powershell"></a><span data-ttu-id="d8571-116">Gebruikerstoegang toewijzen met Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8571-116">Assign user access using Azure PowerShell</span></span>
<span data-ttu-id="d8571-117">U kunt gebruikers toewijzen met een van de volgende machtigingsniveaus:</span><span class="sxs-lookup"><span data-stu-id="d8571-117">You can assign users with one of the following levels of permissions:</span></span>
- <span data-ttu-id="d8571-118">Volledige toegang (lezen en schrijven)</span><span class="sxs-lookup"><span data-stu-id="d8571-118">Full access (Read and Write)</span></span>
- <span data-ttu-id="d8571-119">Alleen-lezen toegang</span><span class="sxs-lookup"><span data-stu-id="d8571-119">Read-only access</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="d8571-120">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="d8571-120">Before you begin</span></span>

- <span data-ttu-id="d8571-121">Installeer Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8571-121">Install Azure PowerShell.</span></span> <span data-ttu-id="d8571-122">Zie Azure PowerShell installeren en configureren voor meer [informatie.](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)</span><span class="sxs-lookup"><span data-stu-id="d8571-122">For more information, see, [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span></span><br>

    > [!NOTE]
    > <span data-ttu-id="d8571-123">U moet de PowerShell-cmdlets uitvoeren op een verhoogde opdrachtregel.</span><span class="sxs-lookup"><span data-stu-id="d8571-123">You need to run the PowerShell cmdlets in an elevated command-line.</span></span>

- <span data-ttu-id="d8571-124">Maak verbinding met uw Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d8571-124">Connect to your Azure Active Directory.</span></span> <span data-ttu-id="d8571-125">Zie [Connect-MsolService](https://docs.microsoft.com/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d8571-125">For more information, see [Connect-MsolService](https://docs.microsoft.com/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true).</span></span>

<span data-ttu-id="d8571-126">**Volledige toegang**</span><span class="sxs-lookup"><span data-stu-id="d8571-126">**Full access**</span></span> <br>
<span data-ttu-id="d8571-127">Gebruikers met volledige toegang kunnen zich aanmelden, alle systeemgegevens bekijken en waarschuwingen oplossen, bestanden indienen voor uitgebreide analyse en het onboarding-pakket downloaden.</span><span class="sxs-lookup"><span data-stu-id="d8571-127">Users with full access can log in, view all system information and resolve alerts, submit files for deep analysis, and download the onboarding package.</span></span>
<span data-ttu-id="d8571-128">Als u volledige toegangsrechten toewijst, moeten de gebruikers worden toegevoegd aan de ingebouwde rollen 'Beveiligingsbeheerder' of 'Globale beheerder'.</span><span class="sxs-lookup"><span data-stu-id="d8571-128">Assigning full access rights requires adding the users to the "Security Administrator" or "Global Administrator" AAD built-in roles.</span></span>

<span data-ttu-id="d8571-129">**Alleen-lezen toegang**</span><span class="sxs-lookup"><span data-stu-id="d8571-129">**Read-only access**</span></span> <br>
<span data-ttu-id="d8571-130">Gebruikers met alleen-lezen toegang kunnen zich aanmelden, alle waarschuwingen en gerelateerde informatie bekijken.</span><span class="sxs-lookup"><span data-stu-id="d8571-130">Users with read-only access can log in, view all alerts, and related information.</span></span>
<span data-ttu-id="d8571-131">Ze kunnen geen waarschuwingstoestanden wijzigen, bestanden indienen voor uitgebreide analyse of statuswijzigingsbewerkingen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="d8571-131">They will not be able to change alert states, submit files for deep analysis or perform any state changing operations.</span></span>
<span data-ttu-id="d8571-132">Als u alleen-lezentoegangsrechten toewijst, moeten de gebruikers worden toegevoegd aan de ingebouwde azure AD-rol 'Beveiligingslezer'.</span><span class="sxs-lookup"><span data-stu-id="d8571-132">Assigning read-only access rights requires adding the users to the "Security Reader" Azure AD built-in role.</span></span>

<span data-ttu-id="d8571-133">Gebruik de volgende stappen om beveiligingsrollen toe te wijzen:</span><span class="sxs-lookup"><span data-stu-id="d8571-133">Use the following steps to assign security roles:</span></span>

- <span data-ttu-id="d8571-134">Voor **lees- en schrijftoegang** wijst u gebruikers toe aan de rol van beveiligingsbeheerder met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="d8571-134">For **read and write** access, assign users to the security administrator role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- <span data-ttu-id="d8571-135">Voor **alleen-lezentoegang** wijst u gebruikers toe aan de rol van de beveiligingslezer met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="d8571-135">For **read-only** access, assign users to the security reader role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

<span data-ttu-id="d8571-136">Zie Groepsleden toevoegen of verwijderen met Azure Active Directory voor [meer informatie.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="d8571-136">For more information, see [Add or remove group members using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).</span></span>

## <a name="assign-user-access-using-the-azure-portal"></a><span data-ttu-id="d8571-137">Gebruikerstoegang toewijzen met de Azure-portal</span><span class="sxs-lookup"><span data-stu-id="d8571-137">Assign user access using the Azure portal</span></span>

<span data-ttu-id="d8571-138">Zie Beheerders- en [niet-beheerdersrollen](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)toewijzen aan gebruikers met Azure Active Directory voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d8571-138">For more information, see [Assign administrator and non-administrator roles to users with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>

## <a name="related-topic"></a><span data-ttu-id="d8571-139">Gerelateerd onderwerp</span><span class="sxs-lookup"><span data-stu-id="d8571-139">Related topic</span></span>

- [<span data-ttu-id="d8571-140">Portaltoegang beheren met RBAC</span><span class="sxs-lookup"><span data-stu-id="d8571-140">Manage portal access using RBAC</span></span>](rbac.md)
