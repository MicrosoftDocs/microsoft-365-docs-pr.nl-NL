---
title: 'Stap 12: Automatische licentie instellen'
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
description: Licenties op groepsbasis voor Azure AD-groepen doorgronden en configureren.
ms.openlocfilehash: 82e4192f2ef9ba3d1d5ed7bd99a8cf603d7d4cc9
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "42809823"
---
# <a name="step-12-set-up-automatic-licensing"></a><span data-ttu-id="f81f2-103">Stap 12: Automatische licentie instellen</span><span class="sxs-lookup"><span data-stu-id="f81f2-103">Step 12: Set up automatic licensing</span></span>

<span data-ttu-id="f81f2-104">*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="f81f2-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="f81f2-105">In deze stap worden beveiligingsgroepen in Azure AD geconfigureerd om automatisch licenties van een verzameling abonnementen toe te wijzen aan alle leden van de groep.</span><span class="sxs-lookup"><span data-stu-id="f81f2-105">In this step, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="f81f2-106">Dit wordt *licenties op groepsbasis* genoemd.</span><span class="sxs-lookup"><span data-stu-id="f81f2-106">This is known as *group-based licensing*.</span></span> <span data-ttu-id="f81f2-107">Als een gebruikersaccount wordt toegevoegd aan of verwijderd uit een groep worden de licenties voor de groepsabonnementen automatisch toegewezen aan of verwijderd van de gebruikersaccount. </span><span class="sxs-lookup"><span data-stu-id="f81f2-107">If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or removed from the user account.</span></span>

<span data-ttu-id="f81f2-108">Voor Microsoft 365 Enterprise worden Azure AD-beveiligingsgroepen geconfigureerd om deze beide licenties toe te wijzen:</span><span class="sxs-lookup"><span data-stu-id="f81f2-108">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign both of these licenses:</span></span>

- <span data-ttu-id="f81f2-109">Office 365 Enterprise E3 of E5</span><span class="sxs-lookup"><span data-stu-id="f81f2-109">Office 365 Enterprise E3 or E5</span></span>
- <span data-ttu-id="f81f2-110">Enterprise Mobility + Security (EMS) E3 of E5</span><span class="sxs-lookup"><span data-stu-id="f81f2-110">Enterprise Mobility + Security (EMS) E3 or E5</span></span>

<span data-ttu-id="f81f2-111">Zoek in de groepen die u in stap 2 hebt geïdentificeerd naar groepen die een lijst bevatten met accounts waarin alle gebruikers in die groep zowel Office 365- als EMS-licenties moeten hebben.</span><span class="sxs-lookup"><span data-stu-id="f81f2-111">Using the groups you identified in Step 2, look for groups that contain a list of accounts where all users in that group must have both Office 365 and EMS licenses.</span></span> <span data-ttu-id="f81f2-112">Zorg ervoor dat u genoeg licenties hebt voor alle groepsleden.</span><span class="sxs-lookup"><span data-stu-id="f81f2-112">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="f81f2-113">Als u niet genoeg licenties hebt, krijgen nieuwe gebruikers geen licenties totdat er weer licenties beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="f81f2-113">If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="f81f2-114">Voor groepen die Azure B2B-accounts (business-to-business) bevatten, moet u *licenties op groepsbasis* niet configureren.</span><span class="sxs-lookup"><span data-stu-id="f81f2-114">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="f81f2-115">Zie [De beginselen van licenties op groepsbasis in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f81f2-115">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="f81f2-116">Zie de [stappen om licenties op groepsbasis te configureren voor een Azure-beveiligingsgroep](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="f81f2-116">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="f81f2-117">De resultaten van deze stap zijn:</span><span class="sxs-lookup"><span data-stu-id="f81f2-117">The results of this step are:</span></span>

- <span data-ttu-id="f81f2-118">U hebt vastgesteld welke beveiligingsgroepen geschikt zijn voor licenties op groepsbasis.</span><span class="sxs-lookup"><span data-stu-id="f81f2-118">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="f81f2-119">U hebt deze groepen geconfigureerd voor licenties op groepsbasis.</span><span class="sxs-lookup"><span data-stu-id="f81f2-119">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="f81f2-121">Testlabrichtlijn: licenties en groepslidmaatschap automatiseren</span><span class="sxs-lookup"><span data-stu-id="f81f2-121">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="f81f2-122">Als tussentijds controlepunt kunt u het [afsluitcriterium](identity-exit-criteria.md#crit-identity-group-license) voor deze stap bekijken.</span><span class="sxs-lookup"><span data-stu-id="f81f2-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="f81f2-123">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="f81f2-123">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [<span data-ttu-id="f81f2-124">Tenant- en aanmeldingsactiviteit controleren</span><span class="sxs-lookup"><span data-stu-id="f81f2-124">Monitor tenant and sign-in activity</span></span>](identity-azure-ad-access-usage-reporting.md) |

