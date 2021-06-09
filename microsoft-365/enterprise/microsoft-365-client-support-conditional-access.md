---
title: 'Microsoft 365 Client-app-ondersteuning: Voorwaardelijke toegang'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: In dit artikel leert u welke platforms, clients en PowerShell-modules Voorwaardelijke Access voor Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7b0b65ea25091aad01fd8741f9925f2b545e9c4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904960"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a><span data-ttu-id="f6646-103">Microsoft 365 Client-app-ondersteuning: Voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="f6646-103">Microsoft 365 Client App Support: Conditional Access</span></span>

<span data-ttu-id="f6646-104">Op de moderne werkplek hebben gebruikers vanaf elke locatie toegang tot de resources van uw organisatie met behulp van verschillende apparaten en apps.</span><span class="sxs-lookup"><span data-stu-id="f6646-104">In the modern workplace, users can access your organization's resources using various devices and apps from anywhere.</span></span> <span data-ttu-id="f6646-105">Als gevolg hiervan volstaat het niet meer om alleen te focussen op wie toegang heeft tot een resource.</span><span class="sxs-lookup"><span data-stu-id="f6646-105">As a result, just focusing on who can access a resource is not sufficient anymore.</span></span> <span data-ttu-id="f6646-106">Uw organisatie moet ook ondersteunen hoe en waar een resource wordt gebruikt in uw toegangsbeheerinfrastructuur.</span><span class="sxs-lookup"><span data-stu-id="f6646-106">Your organization must also support how and where a resource is accessed in your access control infrastructure.</span></span>

<span data-ttu-id="f6646-107">Met Azure Active Directory apparaat, locatie en meervoudige verificatie op basis van voorwaardelijke toegang kunt u aan deze nieuwe vereiste voldoen.</span><span class="sxs-lookup"><span data-stu-id="f6646-107">With Azure Active Directory device, location, and multi-factor authentication-based Conditional Access, you can meet this new requirement.</span></span> <span data-ttu-id="f6646-108">Voorwaardelijke toegang is een Azure Active Directory waarmee u besturingselementen kunt afdwingen voor de toegang tot apps in uw omgeving, allemaal op basis van specifieke voorwaarden en beheerd vanaf een centrale locatie.</span><span class="sxs-lookup"><span data-stu-id="f6646-108">Conditional Access is a capability of Azure Active Directory that enables you to enforce controls on the access to apps in your environment, all based on specific conditions and managed from a central location.</span></span>

<span data-ttu-id="f6646-109">Meer informatie over [Azure Active Directory Voorwaardelijke toegang.](/azure/active-directory/conditional-access/)</span><span class="sxs-lookup"><span data-stu-id="f6646-109">Learn more about [Azure Active Directory Conditional Access](/azure/active-directory/conditional-access/).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="f6646-110">Ondersteunde clients & platforms</span><span class="sxs-lookup"><span data-stu-id="f6646-110">Supported clients & platforms</span></span>

<span data-ttu-id="f6646-111">De nieuwste versies van de volgende clients en platforms ondersteunen voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="f6646-111">The latest versions of the following clients and platforms support conditional access.</span></span> <span data-ttu-id="f6646-112">Zie Systeemvereisten voor Microsoft 365 voor meer informatie over platformondersteuning [in Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)</span><span class="sxs-lookup"><span data-stu-id="f6646-112">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Conditional access services support table](../includes/microsoft-365-client-support-conditional-access-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="f6646-113">Ondersteunde PowerShell-modules</span><span class="sxs-lookup"><span data-stu-id="f6646-113">Supported PowerShell modules</span></span>

- [<span data-ttu-id="f6646-114">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6646-114">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="f6646-115">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6646-115">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="f6646-116">SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6646-116">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
