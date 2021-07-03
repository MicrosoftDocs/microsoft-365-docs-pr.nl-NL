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
ms.openlocfilehash: 763380429b8643c5dd01971117fccb040a9a0210
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286559"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a><span data-ttu-id="8165c-103">Microsoft 365 Client-app-ondersteuning: Voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="8165c-103">Microsoft 365 Client App Support: Conditional Access</span></span>

<span data-ttu-id="8165c-104">Op de moderne werkplek hebben gebruikers vanaf elke locatie toegang tot de resources van uw organisatie met behulp van verschillende apparaten en apps.</span><span class="sxs-lookup"><span data-stu-id="8165c-104">In the modern workplace, users can access your organization's resources using various devices and apps from anywhere.</span></span> <span data-ttu-id="8165c-105">Als gevolg hiervan volstaat het niet meer om alleen te focussen op wie toegang heeft tot een resource.</span><span class="sxs-lookup"><span data-stu-id="8165c-105">As a result, just focusing on who can access a resource is not sufficient anymore.</span></span> <span data-ttu-id="8165c-106">Uw organisatie moet ook ondersteunen hoe en waar een resource wordt gebruikt in uw toegangsbeheerinfrastructuur.</span><span class="sxs-lookup"><span data-stu-id="8165c-106">Your organization must also support how and where a resource is accessed in your access control infrastructure.</span></span>

<span data-ttu-id="8165c-107">Met Azure Active Directory apparaat, locatie en meervoudige verificatie op basis van voorwaardelijke toegang kunt u aan deze nieuwe vereiste voldoen.</span><span class="sxs-lookup"><span data-stu-id="8165c-107">With Azure Active Directory device, location, and multi-factor authentication-based Conditional Access, you can meet this new requirement.</span></span> <span data-ttu-id="8165c-108">Voorwaardelijke toegang is een Azure Active Directory waarmee u besturingselementen kunt afdwingen voor de toegang tot apps in uw omgeving, allemaal op basis van specifieke voorwaarden en beheerd vanaf een centrale locatie.</span><span class="sxs-lookup"><span data-stu-id="8165c-108">Conditional Access is a capability of Azure Active Directory that enables you to enforce controls on the access to apps in your environment, all based on specific conditions and managed from a central location.</span></span>

<span data-ttu-id="8165c-109">Meer informatie over [Azure Active Directory Voorwaardelijke toegang.](/azure/active-directory/conditional-access/)</span><span class="sxs-lookup"><span data-stu-id="8165c-109">Learn more about [Azure Active Directory Conditional Access](/azure/active-directory/conditional-access/).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="8165c-110">Ondersteunde clients & platforms</span><span class="sxs-lookup"><span data-stu-id="8165c-110">Supported clients & platforms</span></span>

<span data-ttu-id="8165c-111">De nieuwste versies van de volgende clients en platforms ondersteunen voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="8165c-111">The latest versions of the following clients and platforms support conditional access.</span></span> <span data-ttu-id="8165c-112">Zie Systeemvereisten voor Microsoft 365 voor meer informatie over platformondersteuning [in Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)</span><span class="sxs-lookup"><span data-stu-id="8165c-112">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Conditional access services support table](../includes/microsoft-365-client-support-conditional-access-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="8165c-113">Ondersteunde PowerShell-modules</span><span class="sxs-lookup"><span data-stu-id="8165c-113">Supported PowerShell modules</span></span>

- [<span data-ttu-id="8165c-114">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="8165c-114">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview)
- [<span data-ttu-id="8165c-115">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="8165c-115">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="8165c-116">SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="8165c-116">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
