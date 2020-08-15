---
title: Identiteit en apparaattoegang voor uw Microsoft 365-testomgeving
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Maak een Microsoft 365-omgeving om de toegang tot identiteiten en apparaten te testen.
ms.openlocfilehash: c5bc0fbbb3ae3839cb7aa71e8c840784ae4a4cad
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685852"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="cfffe-103">Identiteit en apparaattoegang voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="cfffe-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="cfffe-104">*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="cfffe-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="cfffe-105">[Configuraties voor identiteits-en Apparaattoegang](microsoft-365-policies-configurations.md) zijn een set functies en regels voor voorwaardelijke toegang om de toegang te beschermen tot alle services die zijn geïntegreerd in azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="cfffe-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="cfffe-106">U kunt als volgt een testomgeving met deze beleidsregels maken:</span><span class="sxs-lookup"><span data-stu-id="cfffe-106">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="cfffe-107">Configureer uw testomgeving met de vereiste identiteits- en beveiligingsfuncties op basis van uw keuze van identiteitsmodel en verificatiemethode:</span><span class="sxs-lookup"><span data-stu-id="cfffe-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="cfffe-108">Alleen cloud</span><span class="sxs-lookup"><span data-stu-id="cfffe-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="cfffe-109">Wachtwoord-hash-synchronisatie (PHS)</span><span class="sxs-lookup"><span data-stu-id="cfffe-109">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="cfffe-110">Pass Through-verificatie (PTA)</span><span class="sxs-lookup"><span data-stu-id="cfffe-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="cfffe-111">Gebruik [gemeenschappelijk beleid voor identiteits- en apparaattoegang](identity-access-policies.md) om het beleid te configureren dat is gebaseerd op de vereisten en test bescherming voor identiteiten en apparaten.</span><span class="sxs-lookup"><span data-stu-id="cfffe-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="cfffe-112">Zie ook</span><span class="sxs-lookup"><span data-stu-id="cfffe-112">See also</span></span>

[<span data-ttu-id="cfffe-113">Aanvullende testlabrichtlijnen voor identiteit</span><span class="sxs-lookup"><span data-stu-id="cfffe-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="cfffe-114">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="cfffe-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="cfffe-115">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="cfffe-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="cfffe-116">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="cfffe-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="cfffe-117">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="cfffe-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
