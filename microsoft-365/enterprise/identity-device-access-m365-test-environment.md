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
ms.openlocfilehash: 84af7747fc1d0e80e933397f4f0f96018ed246c3
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327805"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="8e70e-103">Identiteit en apparaattoegang voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="8e70e-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="8e70e-104">*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="8e70e-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="8e70e-105">[Configuraties voor identiteits-en Apparaattoegang](microsoft-365-policies-configurations.md) zijn een set functies en regels voor voorwaardelijke toegang om de toegang te beschermen tot alle services die zijn geïntegreerd in azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="8e70e-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="8e70e-106">U kunt als volgt een testomgeving maken met de algemene configuraties voor identiteiten en Apparaattoegang:</span><span class="sxs-lookup"><span data-stu-id="8e70e-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="8e70e-107">Configureer uw testomgeving met de vereiste identiteits- en beveiligingsfuncties op basis van uw keuze van identiteitsmodel en verificatiemethode:</span><span class="sxs-lookup"><span data-stu-id="8e70e-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="8e70e-108">Alleen cloud</span><span class="sxs-lookup"><span data-stu-id="8e70e-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="8e70e-109">Synchronisatie van wachtwoord hash (PHS)</span><span class="sxs-lookup"><span data-stu-id="8e70e-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="8e70e-110">Pass Through-verificatie (PTA)</span><span class="sxs-lookup"><span data-stu-id="8e70e-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="8e70e-111">Gebruik [veelgebruikte beleidsregels voor identiteiten en apparaten](identity-access-policies.md) om het beleid te configureren dat wordt gebruikt voor de testomgeving, en om de bescherming voor identiteiten en apparaten te verkennen en te verifiëren.</span><span class="sxs-lookup"><span data-stu-id="8e70e-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e70e-112">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8e70e-112">See also</span></span>

[<span data-ttu-id="8e70e-113">Aanvullende testlabrichtlijnen voor identiteit</span><span class="sxs-lookup"><span data-stu-id="8e70e-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="8e70e-114">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="8e70e-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="8e70e-115">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="8e70e-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8e70e-116">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="8e70e-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="8e70e-117">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="8e70e-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
