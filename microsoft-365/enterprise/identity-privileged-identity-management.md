---
title: 'Stap 3: Globale beheerders op aanvraag instellen'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Lees meer over en configureer Azure Active Directory Privileged Identity Management.
ms.openlocfilehash: 659beff3c31d17afa03d3ecf754c581f3ca2e230
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "42812021"
---
# <a name="step-3-set-up-on-demand-global-administrators"></a><span data-ttu-id="f1eae-103">Stap 3: Globale beheerders op aanvraag instellen</span><span class="sxs-lookup"><span data-stu-id="f1eae-103">Step 3: Set up on-demand global administrators</span></span>

<span data-ttu-id="f1eae-104">*Deze stap is optioneel en geldt voor alleen voor de E5-versie van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="f1eae-104">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="f1eae-105">In deze stap stelt u de Azure Active Directory Privileged Identity Management (PIM) in om de tijd te verminderen dat uw globale beheerdersaccounts kwetsbaar zijn voor aanvallen door kwaadwillende gebruikers.</span><span class="sxs-lookup"><span data-stu-id="f1eae-105">In this step, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="f1eae-106">Met PIM kunt u op aanvraag een just-in-time-instructie van de globale beheerdersrol inschakelen.</span><span class="sxs-lookup"><span data-stu-id="f1eae-106">PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="f1eae-107">In plaats van uw globale beheerdersaccounts een permanente beheerder te worden, worden ze in aanmerking komende beheerders.</span><span class="sxs-lookup"><span data-stu-id="f1eae-107">Instead of your global administrator accounts being a permanent admin, they become eligible admins.</span></span> <span data-ttu-id="f1eae-108">De globale beheerdersrol is inactief totdat iemand deze nodig heeft.</span><span class="sxs-lookup"><span data-stu-id="f1eae-108">The global administrator role is inactive until someone needs it.</span></span> <span data-ttu-id="f1eae-109">Vervolgens voert u een activeringsprocedure uit om de globale beheerdersrol gedurende een bepaalde tijd toe te voegen aan het globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="f1eae-109">You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time.</span></span> <span data-ttu-id="f1eae-110">Als de tijd is verstreken, verwijdert PIM de globale beheerdersrol uit het globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="f1eae-110">When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="f1eae-111">PIM is beschikbaar met Azure Active Directory Premium P2, dat inbegrepen is bij Microsoft 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="f1eae-111">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5.</span></span> <span data-ttu-id="f1eae-112">U kunt ook afzonderlijke Azure Active Directory Premium P2-licenties aanschaffen voor uw globale-beheerdersaccounts.</span><span class="sxs-lookup"><span data-stu-id="f1eae-112">Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="f1eae-113">Als u Azure PIM wilt inschakelen voor uw Azure Active Directory tenant -en globale beheerdersaccounts, raadpleegt u de [stappen voor het configureren van PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="f1eae-113">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="f1eae-114">U kunt een uitgebreide roadmap ontwikkelen om bevoegde toegang te beveiligen tegen cyberaanvallers, zie [Bevoegde toegang voor hybride en cloudimplementaties in Azure Active Directory beveiligen](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="f1eae-114">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="f1eae-115">Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-pim) voor deze stap bekijken.</span><span class="sxs-lookup"><span data-stu-id="f1eae-115">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="f1eae-116">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="f1eae-116">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="f1eae-117">Het opnieuw instellen van wachtwoorden vereenvoudigen</span><span class="sxs-lookup"><span data-stu-id="f1eae-117">Simplify password resets</span></span>](identity-password-reset.md) |

