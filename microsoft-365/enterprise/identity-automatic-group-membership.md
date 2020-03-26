---
title: 'Stap 15: Dynamisch groepslidmaatschap instellen'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Informatie over automatisch groepslidmaatschap en leren configureren op basis van accountkenmerken.
ms.openlocfilehash: 8619179bc4e3ce17d9201cafb88e1b1c48fc7f4f
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "42806617"
---
# <a name="step-15-set-up-dynamic-group-membership"></a><span data-ttu-id="5c3c1-103">Stap 15: Dynamisch groepslidmaatschap instellen</span><span class="sxs-lookup"><span data-stu-id="5c3c1-103">Step 15: Set up dynamic group membership</span></span>

<span data-ttu-id="5c3c1-104">*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="5c3c1-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="5c3c1-105">In deze stap maakt u een reeks regels om gebruikersaccounts automatisch toe te voegen of te verwijderen als leden van een Azure AD-groep.</span><span class="sxs-lookup"><span data-stu-id="5c3c1-105">In this step, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="5c3c1-106">Dit wordt *dynamisch groepslidmaatschap* genoemd.</span><span class="sxs-lookup"><span data-stu-id="5c3c1-106">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="5c3c1-107">De regels zijn gebaseerd op kenmerken van gebruikersaccounts, zoals Afdeling of Land.</span><span class="sxs-lookup"><span data-stu-id="5c3c1-107">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="5c3c1-108">De regels worden als volgt toegepast:</span><span class="sxs-lookup"><span data-stu-id="5c3c1-108">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="5c3c1-109">Als een nieuw gebruikersaccount aan alle regels voor de groep voldoet, wordt het lid.</span><span class="sxs-lookup"><span data-stu-id="5c3c1-109">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="5c3c1-110">Als een gebruikersaccount geen lid is van de groep, maar de bijbehorende kenmerken zodanig worden gewijzigd dat deze voldoen aan alle regels voor de groep, wordt het account lid van die groep.</span><span class="sxs-lookup"><span data-stu-id="5c3c1-110">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="5c3c1-111">Als een gebruikersaccount niet voldoet aan alle regels voor de groep, wordt het niet toegevoegd aan de groep.</span><span class="sxs-lookup"><span data-stu-id="5c3c1-111">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="5c3c1-112">Als een gebruikersaccount lid is van de groep, maar de bijbehorende kenmerken zodanig worden gewijzigd dat het niet meer voldoet aan alle regels voor de groep, wordt het account als lid van de groep verwijderd.</span><span class="sxs-lookup"><span data-stu-id="5c3c1-112">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="5c3c1-113">Als u dynamisch lidmaatschap wilt gebruiken, moet u eerst bepalen welke sets groepen een gemeenschappelijke set gebruikersaccountkenmerken hebben.</span><span class="sxs-lookup"><span data-stu-id="5c3c1-113">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes.</span></span> <span data-ttu-id="5c3c1-114">Zo moeten bijvoorbeeld alle leden van de afdeling Verkoop zich bevinden in de Azure AD-groep Verkoop op basis van het gebruikersaccountkenmerk Afdeling met de waarde Verkoop.</span><span class="sxs-lookup"><span data-stu-id="5c3c1-114">For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="5c3c1-115">Zie de [instructies voor het maken en configureren van de regels voor een dynamische Azure AD-groep](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="5c3c1-115">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="5c3c1-116">De resultaten van deze stap zijn:</span><span class="sxs-lookup"><span data-stu-id="5c3c1-116">The results of this step are:</span></span>

- <span data-ttu-id="5c3c1-117">Een set Azure AD-groepen die kan worden geconfigureerd voor dynamisch lidmaatschap</span><span class="sxs-lookup"><span data-stu-id="5c3c1-117">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="5c3c1-118">Een set regels voor elke dynamische groep</span><span class="sxs-lookup"><span data-stu-id="5c3c1-118">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="5c3c1-120">Testlabrichtlijn: licenties en groepslidmaatschap automatiseren</span><span class="sxs-lookup"><span data-stu-id="5c3c1-120">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="5c3c1-121">Als tussentijds controlepunt kunt u het [afsluitcriterium](identity-exit-criteria.md#crit-identity-dyn-groups) voor deze stap bekijken.</span><span class="sxs-lookup"><span data-stu-id="5c3c1-121">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="5c3c1-122">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="5c3c1-122">Next step</span></span>

[<span data-ttu-id="5c3c1-123">Afsluitcriterium voor identiteitsinfrastructuur</span><span class="sxs-lookup"><span data-stu-id="5c3c1-123">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)
