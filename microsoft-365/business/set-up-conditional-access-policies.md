---
title: Beleid voor voorwaardelijke toegang instellen voor Microsoft 365-campagnes
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
description: Meer informatie over het instellen van beleid voor voorwaardelijke toegang voor Microsoft 365-campagnes om aanzienlijke extra beveiliging toe te voegen.
ms.openlocfilehash: 26fadecc69486d7931dac069d8f53061592f397f
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153761"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="a7d1f-103">Beleid voor voorwaardelijke toegang instellen</span><span class="sxs-lookup"><span data-stu-id="a7d1f-103">Set up Conditional Access policies</span></span>

<span data-ttu-id="a7d1f-104">[Het](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) beleid voor voorwaardelijke toegang voegt aanzienlijke extra beveiliging toe.</span><span class="sxs-lookup"><span data-stu-id="a7d1f-104">[Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substantial additional security.</span></span> <span data-ttu-id="a7d1f-105">Microsoft biedt een set voorwaardelijke toegangsbeleid basislijn dat wordt aanbevolen voor alle klanten.</span><span class="sxs-lookup"><span data-stu-id="a7d1f-105">Microsoft provides a set of baseline Conditional Access policies that are recommended for all customers.</span></span> <span data-ttu-id="a7d1f-106">Basislijnbeleid is een set vooraf gedefinieerde beleidsregels die organisaties helpen beschermen tegen veelvoorkomende aanvallen.</span><span class="sxs-lookup"><span data-stu-id="a7d1f-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="a7d1f-107">Deze veelvoorkomende aanvallen kunnen wachtwoordspray, replay en phishing omvatten.</span><span class="sxs-lookup"><span data-stu-id="a7d1f-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="a7d1f-108">Voor dit beleid moeten beheerders en gebruikers een tweede vorm van verificatie (multifactorauthenticatie of MFA) invoeren wanneer aan bepaalde voorwaarden is voldaan.</span><span class="sxs-lookup"><span data-stu-id="a7d1f-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="a7d1f-109">Als een gebruiker zich bijvoorbeeld aanmeldt vanuit een ander land, kan de aanmelding als riskant worden beschouwd en moet de gebruiker een extra vorm van verificatie opgeven.</span><span class="sxs-lookup"><span data-stu-id="a7d1f-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="a7d1f-110">Momenteel omvat het basislijnbeleid het volgende:</span><span class="sxs-lookup"><span data-stu-id="a7d1f-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="a7d1f-111">**Mfa vereisen voor beheerders** &ndash; Vereist multi-factor authenticatie voor de meest bevoorrechte beheerdersrollen, inclusief globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="a7d1f-111">**Require MFA for admins** &ndash; Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="a7d1f-112">**Bescherming van eindgebruikers** &ndash; Vereist multi-factor authenticatie voor gebruikers alleen wanneer een aanmelding riskant is.</span><span class="sxs-lookup"><span data-stu-id="a7d1f-112">**End user protection** &ndash; Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="a7d1f-113">**Verouderde verificatie** &ndash; blokkeren Oudere client-apps en sommige nieuwe apps maken geen gebruik van nieuwere, veiligere verificatieprotocollen.</span><span class="sxs-lookup"><span data-stu-id="a7d1f-113">**Block legacy authentication** &ndash; Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="a7d1f-114">Deze oudere apps kunnen het beleid voor voorwaardelijke toegang omzeilen en ongeautoriseerde toegang tot uw omgeving krijgen.</span><span class="sxs-lookup"><span data-stu-id="a7d1f-114">These older apps can bypass Conditional Access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="a7d1f-115">Dit beleid blokkeert de toegang van clients die voorwaardelijke toegang niet ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="a7d1f-115">This policy blocks access from clients that don't support Conditional Access.</span></span> 
- <span data-ttu-id="a7d1f-116">**Mfa vereisen voor servicebeheer** &ndash; Vereist multi-factor authenticatie voor toegang tot beheertools, waaronder Azure portal (waar u basislijnbeleid configureert).</span><span class="sxs-lookup"><span data-stu-id="a7d1f-116">**Require MFA for Service Management** &ndash; Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="a7d1f-117">Microsoft raadt u aan al deze basislijnbeleidsregels in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="a7d1f-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="a7d1f-118">Nadat dit beleid is ingeschakeld, worden beheerders en gebruikers gevraagd zich te registreren voor Azure Multii-Factor-verificatie.</span><span class="sxs-lookup"><span data-stu-id="a7d1f-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="a7d1f-119">Zie [Wat zijn basislijnbeleid](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)voor meer informatie over dit beleid?</span><span class="sxs-lookup"><span data-stu-id="a7d1f-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="a7d1f-120">Basislijnbeleid instellen</span><span class="sxs-lookup"><span data-stu-id="a7d1f-120">Set up baseline policies</span></span>

1. <span data-ttu-id="a7d1f-121">Ga naar [Azure-portal](https://portal.azure.com)en navigeer naar Voorwaardelijke **toegang** **voor Azure Active Directory** \> .</span><span class="sxs-lookup"><span data-stu-id="a7d1f-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="a7d1f-122">Het basislijnbeleid wordt op de pagina weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a7d1f-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="a7d1f-123">![Pagina met basislijnbeleid voor voorwaardelijke toegang.](../media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="a7d1f-123">![Page that lists baseline policies for Conditional Access.](../media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="a7d1f-124">Zie de volgende specifieke instructies voor elk beleid:</span><span class="sxs-lookup"><span data-stu-id="a7d1f-124">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="a7d1f-125">MFA vereisen voor beheerders</span><span class="sxs-lookup"><span data-stu-id="a7d1f-125">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="a7d1f-126">MFA vereisen voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="a7d1f-126">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="a7d1f-127">Verouderde verificatie blokkeren</span><span class="sxs-lookup"><span data-stu-id="a7d1f-127">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="a7d1f-128">MFA vereisen voor servicebeheer</span><span class="sxs-lookup"><span data-stu-id="a7d1f-128">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="a7d1f-129">U veel aanvullende beleidsregels instellen, zoals het vereisen van goedgekeurde client-apps.</span><span class="sxs-lookup"><span data-stu-id="a7d1f-129">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="a7d1f-130">Zie de documentatie [voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/)voor meer informatie .</span><span class="sxs-lookup"><span data-stu-id="a7d1f-130">For more information, see the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
