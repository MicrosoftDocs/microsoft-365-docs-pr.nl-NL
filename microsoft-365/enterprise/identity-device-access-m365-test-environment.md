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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Maak een Microsoft 365-omgeving om de toegang tot identiteiten en apparaten te testen.
ms.openlocfilehash: e43483afc9e17de9582b2998867b53cfff7d8492
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42811636"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="76991-103">Identiteit en apparaattoegang voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="76991-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="76991-104">*Deze testlabrichtlijn kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="76991-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="76991-105">[Configuraties voor identiteits- en apparaattoegang](microsoft-365-policies-configurations.md) zijn een reeks functies en beleid voor voorwaardelijke toegang om de toegang tot alle services te beveiligen die zijn geïntegreerd met Azure Active Directory (Azure AD), met inbegrip van Office 365 en Microsoft Intune in Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="76991-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Microsoft Intune in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="76991-106">U kunt als volgt een testomgeving met deze beleidsregels maken:</span><span class="sxs-lookup"><span data-stu-id="76991-106">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="76991-107">Configureer uw testomgeving met de vereiste identiteits- en beveiligingsfuncties op basis van uw keuze van identiteitsmodel en verificatiemethode:</span><span class="sxs-lookup"><span data-stu-id="76991-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="76991-108">Alleen cloud</span><span class="sxs-lookup"><span data-stu-id="76991-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="76991-109">Wachtwoord-hash-synchronisatie (PHS)</span><span class="sxs-lookup"><span data-stu-id="76991-109">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="76991-110">Pass Through-verificatie (PTA)</span><span class="sxs-lookup"><span data-stu-id="76991-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="76991-111">Gebruik [gemeenschappelijk beleid voor identiteits- en apparaattoegang](identity-access-policies.md) om het beleid te configureren dat is gebaseerd op de vereisten en test bescherming voor identiteiten en apparaten.</span><span class="sxs-lookup"><span data-stu-id="76991-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="76991-112">Zie ook</span><span class="sxs-lookup"><span data-stu-id="76991-112">See also</span></span>

[<span data-ttu-id="76991-113">Aanvullende testlabrichtlijnen voor identiteit</span><span class="sxs-lookup"><span data-stu-id="76991-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="76991-114">Fase 2: Identiteit</span><span class="sxs-lookup"><span data-stu-id="76991-114">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="76991-115">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="76991-115">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="76991-116">Microsoft 365 Enterprise-implementatie</span><span class="sxs-lookup"><span data-stu-id="76991-116">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="76991-117">Microsoft 365 Enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="76991-117">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
