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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Meer informatie over het instellen van beleid voor voorwaardelijke toegang voor Microsoft 365-campagnes om aanzienlijke extra beveiliging toe te voegen.
ms.openlocfilehash: 58ee760877ee2fd7e53ef9463242657ab66a2b6e
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470642"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="d86f5-103">Beleid voor voorwaardelijke toegang instellen</span><span class="sxs-lookup"><span data-stu-id="d86f5-103">Set up conditional access policies</span></span>

<span data-ttu-id="d86f5-104">Dit artikel is van toepassing op Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="d86f5-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="d86f5-105">[Beleid voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) voegt aanzienlijke extra beveiliging toe.</span><span class="sxs-lookup"><span data-stu-id="d86f5-105">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substantial additional security.</span></span> <span data-ttu-id="d86f5-106">Microsoft biedt een set basislijnvoorwaarden voor voorwaardelijke toegang die voor alle klanten worden aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="d86f5-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="d86f5-107">Basislijnbeleid is een set vooraf gedefinieerde beleidsregels die organisaties helpen beschermen tegen veel voorkomende aanvallen.</span><span class="sxs-lookup"><span data-stu-id="d86f5-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="d86f5-108">Deze veelvoorkomende aanvallen kunnen wachtwoordspray, herhaling en phishing omvatten.</span><span class="sxs-lookup"><span data-stu-id="d86f5-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="d86f5-109">Dit beleid vereist dat beheerders en gebruikers een tweede vorm van verificatie invoeren (multifactorauthenticatie of MFA genoemd) wanneer aan bepaalde voorwaarden is voldaan.</span><span class="sxs-lookup"><span data-stu-id="d86f5-109">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="d86f5-110">Als een gebruiker zich bijvoorbeeld vanuit een ander land aanmeldt, kan de aanmelding als riskant worden beschouwd en moet de gebruiker een extra vorm van verificatie opgeven.</span><span class="sxs-lookup"><span data-stu-id="d86f5-110">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="d86f5-111">Momenteel omvatten basislijnbeleid het volgende:</span><span class="sxs-lookup"><span data-stu-id="d86f5-111">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="d86f5-112">**MFA nodig voor beheerders** &ndash; Vereist meervoudige verificatie voor de meest bevoorrechte beheerdersrollen, inclusief globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="d86f5-112">**Require MFA for admins** &ndash; Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="d86f5-113">**Beveiliging van eindgebruikers** &ndash; Vereist multi-factor authenticatie voor gebruikers alleen wanneer een aanmelding riskant is.</span><span class="sxs-lookup"><span data-stu-id="d86f5-113">**End user protection** &ndash; Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="d86f5-114">**Verouderde verificatie blokkeren** &ndash; Oudere client-apps en sommige nieuwe apps gebruiken geen nieuwere, veiligere verificatieprotocollen.</span><span class="sxs-lookup"><span data-stu-id="d86f5-114">**Block legacy authentication** &ndash; Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="d86f5-115">Deze oudere apps kunnen het beleid voor voorwaardelijke toegang omzeilen en ongeautoriseerde toegang tot uw omgeving krijgen.</span><span class="sxs-lookup"><span data-stu-id="d86f5-115">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="d86f5-116">Dit beleid blokkeert de toegang van clients die geen voorwaardelijke toegang ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="d86f5-116">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="d86f5-117">**MFA vereisen voor servicebeheer** &ndash; Vereist meervoudige verificatie voor toegang tot beheerhulpprogramma's, waaronder Azure-portal (waar u basislijnbeleid configureert).</span><span class="sxs-lookup"><span data-stu-id="d86f5-117">**Require MFA for Service Management** &ndash; Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="d86f5-118">Microsoft raadt u aan al deze basislijnregels in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="d86f5-118">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="d86f5-119">Nadat dit beleid is ingeschakeld, worden beheerders en gebruikers gevraagd zich te registreren voor Azure Multii-Factor-verificatie.</span><span class="sxs-lookup"><span data-stu-id="d86f5-119">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="d86f5-120">Zie [Wat zijn basislijnbeleid voor](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)meer informatie over dit beleid?</span><span class="sxs-lookup"><span data-stu-id="d86f5-120">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="d86f5-121">Basislijnbeleid instellen</span><span class="sxs-lookup"><span data-stu-id="d86f5-121">Set up baseline policies</span></span>

1. <span data-ttu-id="d86f5-122">Ga naar [Azure-portal](https://portal.azure.com)en navigeer naar **Azure Active Directory** Voorwaardelijke \> **toegang**.</span><span class="sxs-lookup"><span data-stu-id="d86f5-122">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="d86f5-123">Het basislijnbeleid wordt op de pagina weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d86f5-123">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="d86f5-124">![Pagina met basislijnbeleid voor voorwaardelijke toegang.](../media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="d86f5-124">![Page that lists baseline policies for conditional access.](../media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="d86f5-125">Zie de volgende specifieke instructies voor elk beleid:</span><span class="sxs-lookup"><span data-stu-id="d86f5-125">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="d86f5-126">MFA nodig voor beheerders</span><span class="sxs-lookup"><span data-stu-id="d86f5-126">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="d86f5-127">MFA vereisen voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="d86f5-127">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="d86f5-128">Verouderde verificatie blokkeren</span><span class="sxs-lookup"><span data-stu-id="d86f5-128">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="d86f5-129">MFA vereisen voor servicebeheer</span><span class="sxs-lookup"><span data-stu-id="d86f5-129">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="d86f5-130">U veel aanvullende beleidsregels instellen, zoals het vereisen van goedgekeurde client-apps.</span><span class="sxs-lookup"><span data-stu-id="d86f5-130">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="d86f5-131">Zie de documentatie [voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/)voor meer informatie .</span><span class="sxs-lookup"><span data-stu-id="d86f5-131">For more information, see the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
