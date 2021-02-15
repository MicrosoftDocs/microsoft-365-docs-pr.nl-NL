---
title: Identiteit en apparaattoegang voor uw Microsoft 365-testomgeving
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Maak een Microsoft 365-omgeving om de toegang tot identiteiten en apparaten te testen.
ms.openlocfilehash: ed143341079a55d6bdd1d4a68feea68acb86ef85
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233726"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="8b6d5-103">Identiteit en apparaattoegang voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="8b6d5-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="8b6d5-104">*Deze Test Lab Guide kan alleen worden gebruikt voor Microsoft 365 voor bedrijfstestomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="8b6d5-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="8b6d5-105">[Configuraties voor identiteits-](../security/office-365-security/microsoft-365-policies-configurations.md) en apparaattoegang zijn een reeks aanbevolen configuraties en beleidsregels voor voorwaardelijke toegang ter bescherming van de toegang tot alle services die zijn geïntegreerd met Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="8b6d5-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="8b6d5-106">Een testomgeving maken met de configuraties voor gemeenschappelijke identiteits- en apparaattoegang:</span><span class="sxs-lookup"><span data-stu-id="8b6d5-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="8b6d5-107">Configureer uw testomgeving met de vereiste identiteits- en beveiligingsfuncties op basis van uw keuze van identiteitsmodel en verificatiemethode:</span><span class="sxs-lookup"><span data-stu-id="8b6d5-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="8b6d5-108">Alleen cloud</span><span class="sxs-lookup"><span data-stu-id="8b6d5-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="8b6d5-109">Wachtwoord-hashsynchronisatie (PHS)</span><span class="sxs-lookup"><span data-stu-id="8b6d5-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="8b6d5-110">Pass Through-verificatie (PTA)</span><span class="sxs-lookup"><span data-stu-id="8b6d5-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="8b6d5-111">Gebruik [algemene beleidsregels](identity-access-policies.md) voor identiteits- en apparaattoegang om het beleid te configureren dat is gebaseerd op de vereisten die zijn geconfigureerd voor uw testomgeving, en om de beveiliging voor identiteiten en apparaten te verkennen en te controleren.</span><span class="sxs-lookup"><span data-stu-id="8b6d5-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b6d5-112">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8b6d5-112">See also</span></span>

[<span data-ttu-id="8b6d5-113">Aanvullende testlabrichtlijnen voor identiteit</span><span class="sxs-lookup"><span data-stu-id="8b6d5-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="8b6d5-114">Routekaart voor identiteit</span><span class="sxs-lookup"><span data-stu-id="8b6d5-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="8b6d5-115">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="8b6d5-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8b6d5-116">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="8b6d5-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="8b6d5-117">Microsoft 365 enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="8b6d5-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
