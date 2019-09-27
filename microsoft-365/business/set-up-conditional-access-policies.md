---
title: Beleid voor voorwaardelijke toegang instellen voor Microsoft 365-campagnes
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
description: Informatie over het instellen van beleid voor voorwaardelijke toegang voor Microsoft 365-campagnes.
ms.openlocfilehash: dbb5231032d2faef0a7ecb2734226b34290c70bf
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288610"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="bc1a1-103">Beleid voor voorwaardelijke toegang instellen</span><span class="sxs-lookup"><span data-stu-id="bc1a1-103">Set up conditional access policies</span></span>

<span data-ttu-id="bc1a1-104">Beleid voor [voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) toevoegen verbouwings extra beveiliging.</span><span class="sxs-lookup"><span data-stu-id="bc1a1-104">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substancial additional security.</span></span> <span data-ttu-id="bc1a1-105">Microsoft biedt een set basislijn beleid voor voorwaardelijke toegang die worden aanbevolen voor alle klanten.</span><span class="sxs-lookup"><span data-stu-id="bc1a1-105">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="bc1a1-106">Basislijn beleid is een set vooraf gedefinieerde beleidsregels die organisaties helpen beschermen tegen veel veelvoorkomende aanvallen.</span><span class="sxs-lookup"><span data-stu-id="bc1a1-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="bc1a1-107">Deze veelvoorkomende aanvallen kunnen bestaan uit het wachtwoord spray, replay en phishing.</span><span class="sxs-lookup"><span data-stu-id="bc1a1-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="bc1a1-108">Deze beleidsregels vereisen dat beheerders en gebruikers een tweede vorm van verificatie (multi factor Authentication, of MFA) invoeren wanneer aan bepaalde voorwaarden wordt voldaan.</span><span class="sxs-lookup"><span data-stu-id="bc1a1-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="bc1a1-109">Als een gebruiker zich bijvoorbeeld aanmeldt vanuit een ander land, kan de aanmelding als riskant worden beschouwd en moet de gebruiker een extra verificatie vorm opgeven.</span><span class="sxs-lookup"><span data-stu-id="bc1a1-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="bc1a1-110">Op dit moment basislijn beleid omvatten de volgende:</span><span class="sxs-lookup"><span data-stu-id="bc1a1-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="bc1a1-111">**MFA vereisen voor beheerders** : multi-factor Authentication vereist voor de meest bevoorrechte beheerdersrollen, met inbegrip van de globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="bc1a1-111">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="bc1a1-112">**Bescherming van eindgebruikers** : multi-factor Authentication vereist voor gebruikers alleen wanneer een aanmelding riskant is.</span><span class="sxs-lookup"><span data-stu-id="bc1a1-112">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="bc1a1-113">**Verouderde verificatie blokkeren** : oudere client-apps en sommige nieuwe apps gebruiken geen nieuwere, veiligere verificatieprotocollen.</span><span class="sxs-lookup"><span data-stu-id="bc1a1-113">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="bc1a1-114">Deze oudere apps kunnen beleid voor voorwaardelijke toegang omzeilen en onbevoegde toegang tot uw omgeving te krijgen.</span><span class="sxs-lookup"><span data-stu-id="bc1a1-114">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="bc1a1-115">Dit beleid blokkeert de toegang van clients die geen ondersteuning bieden voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="bc1a1-115">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="bc1a1-116">**MFA vereisen voor Service beheer** : multi-factor Authentication vereist voor toegang tot beheerhulpprogramma's, met inbegrip van Azure Portal (waar u Basisbeleid configureren).</span><span class="sxs-lookup"><span data-stu-id="bc1a1-116">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="bc1a1-117">Microsoft raadt aan dat u al deze basislijn beleid inschakelen.</span><span class="sxs-lookup"><span data-stu-id="bc1a1-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="bc1a1-118">Nadat dit beleid is ingeschakeld, worden beheerders en gebruikers gevraagd om zich te registreren voor Azure Multii-Factor Authentication.</span><span class="sxs-lookup"><span data-stu-id="bc1a1-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="bc1a1-119">Zie voor meer informatie over dit beleid, [Wat zijn Basisbeleid](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span><span class="sxs-lookup"><span data-stu-id="bc1a1-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="bc1a1-120">Basislijn beleid instellen</span><span class="sxs-lookup"><span data-stu-id="bc1a1-120">Set up baseline policies</span></span>

1. <span data-ttu-id="bc1a1-121">Ga naar [Azure Portal](https://portal.azure.com), en navigeer vervolgens naar **Azure Active Directory** \> **voorwaardelijke toegang**.</span><span class="sxs-lookup"><span data-stu-id="bc1a1-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="bc1a1-122">Het basislijn beleid wordt weergegeven op de pagina.</span><span class="sxs-lookup"><span data-stu-id="bc1a1-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="bc1a1-123">![Pagina waarop het basisbeleid voor voorwaardelijke toegang wordt vermeld.](media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="bc1a1-123">![Page that lists baseline policies for conditional access.](media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="bc1a1-124">Zie de volgende specifieke instructies voor elk beleid:</span><span class="sxs-lookup"><span data-stu-id="bc1a1-124">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="bc1a1-125">MFA vereisen voor beheerders</span><span class="sxs-lookup"><span data-stu-id="bc1a1-125">Require MFA for admins</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="bc1a1-126">MFA vereisen voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="bc1a1-126">Require MFA for users</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="bc1a1-127">Verouderde verificatie blokkeren</span><span class="sxs-lookup"><span data-stu-id="bc1a1-127">Block legacy authentication</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="bc1a1-128">MFA vereisen voor servicebeheer</span><span class="sxs-lookup"><span data-stu-id="bc1a1-128">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="bc1a1-129">U veel extra beleidsregels instellen, zoals het vereisen van goedgekeurde client-apps.</span><span class="sxs-lookup"><span data-stu-id="bc1a1-129">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="bc1a1-130">Zie de [documentatie voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bc1a1-130">See the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/) for more information.</span></span>