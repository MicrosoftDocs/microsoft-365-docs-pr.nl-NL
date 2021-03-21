---
title: 'Ondersteuning voor Microsoft 365 Client App: Meervoudige verificatie'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: In dit artikel leert u welke platforms, clients en PowerShell-modules meervoudige verificatie voor Microsoft 365 ondersteunen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 80ee370526d17d472cd048cd4d89b862e158b631
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927557"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a><span data-ttu-id="52b1c-103">Ondersteuning voor Microsoft 365 Client App: Meervoudige verificatie</span><span class="sxs-lookup"><span data-stu-id="52b1c-103">Microsoft 365 Client App Support: Multi-factor authentication</span></span>

<span data-ttu-id="52b1c-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="52b1c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="52b1c-105">Als u een extra beveiligingsniveau wilt bieden voor aanmeldingen, kunnen clients zijn geconfigureerd voor het gebruik van meervoudige verificatie (MFA), waarbij zowel een gebruikerswachtwoord als een andere methode voor gebruikersverificatie wordt gebruikt op basis van:</span><span class="sxs-lookup"><span data-stu-id="52b1c-105">To provide an additional level of security for sign-ins, clients may be configured to use multi-factor authentication (MFA), which uses both a user password and another user verification method based on:</span></span>

- <span data-ttu-id="52b1c-106">Iets in hun bezit dat niet eenvoudig kan worden gedupliceerd, zoals een smartphone.</span><span class="sxs-lookup"><span data-stu-id="52b1c-106">Something  in their possession that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="52b1c-107">Iets wat de gebruiker uniek en biologisch heeft, zoals zijn of haar vingerafdruk, gezicht of ander biometrisch kenmerk</span><span class="sxs-lookup"><span data-stu-id="52b1c-107">Something the user has uniquely and biologically, such as their fingerprints, face, or other biometric attribute</span></span>

<span data-ttu-id="52b1c-108">Meer informatie over [meervoudige verificatie](/azure/active-directory/authentication/multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="52b1c-108">Learn more about [multi-factor authentication](/azure/active-directory/authentication/multi-factor-authentication).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="52b1c-109">Ondersteunde clients & platforms</span><span class="sxs-lookup"><span data-stu-id="52b1c-109">Supported clients & platforms</span></span>

<span data-ttu-id="52b1c-110">De nieuwste versies van de volgende clients en platforms ondersteunen meervoudige verificatie.</span><span class="sxs-lookup"><span data-stu-id="52b1c-110">The latest versions of the following clients and platforms support multi-factor authentication.</span></span> <span data-ttu-id="52b1c-111">Zie Systeemvereisten voor Microsoft 365 voor meer informatie over platformondersteuning in [Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)</span><span class="sxs-lookup"><span data-stu-id="52b1c-111">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Multi-factor authentication services support table](../includes/microsoft-365-client-support-modern-authentication-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="52b1c-112">Ondersteunde PowerShell-modules</span><span class="sxs-lookup"><span data-stu-id="52b1c-112">Supported PowerShell modules</span></span>

- [<span data-ttu-id="52b1c-113">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="52b1c-113">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="52b1c-114">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="52b1c-114">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="52b1c-115">SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="52b1c-115">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)