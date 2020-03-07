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
ms.openlocfilehash: eda65e335df2a7c2c443d7095f7b35b5c1cf27e4
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561215"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="dec21-103">Beleid voor voorwaardelijke toegang instellen</span><span class="sxs-lookup"><span data-stu-id="dec21-103">Set up conditional access policies</span></span>

<span data-ttu-id="dec21-104">[Beleid voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) voegt aanzienlijke extra beveiliging toe.</span><span class="sxs-lookup"><span data-stu-id="dec21-104">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substantial additional security.</span></span> <span data-ttu-id="dec21-105">Microsoft biedt een set van basisbeleid voor voorwaardelijke toegang dat wordt aanbevolen voor alle klanten.</span><span class="sxs-lookup"><span data-stu-id="dec21-105">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="dec21-106">Basislijnbeleid is een reeks vooraf gedefinieerde beleidsregels die organisaties helpen beschermen tegen veel voorkomende aanvallen.</span><span class="sxs-lookup"><span data-stu-id="dec21-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="dec21-107">Deze veelvoorkomende aanvallen kunnen wachtwoordspray, replay en phishing omvatten.</span><span class="sxs-lookup"><span data-stu-id="dec21-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="dec21-108">Voor dit beleid moeten beheerders en gebruikers een tweede vorm van verificatie (multifactorauthenticatie of MFA) invoeren wanneer aan bepaalde voorwaarden is voldaan.</span><span class="sxs-lookup"><span data-stu-id="dec21-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="dec21-109">Als een gebruiker zich bijvoorbeeld aanmeldt vanuit een ander land, kan de aanmelding als riskant worden beschouwd en moet de gebruiker een extra vorm van verificatie opgeven.</span><span class="sxs-lookup"><span data-stu-id="dec21-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="dec21-110">Momenteel bevat het basisbeleid het volgende:</span><span class="sxs-lookup"><span data-stu-id="dec21-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="dec21-111">**MFA vereisen voor beheerders** &ndash; Vereist meervoudige verificatie voor de meest bevoorrechte beheerdersrollen, inclusief globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="dec21-111">**Require MFA for admins** &ndash; Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="dec21-112">**Bescherming van** &ndash; eindgebruikers Vereist multi-factor authenticatie voor gebruikers alleen wanneer een aanmelding riskant is.</span><span class="sxs-lookup"><span data-stu-id="dec21-112">**End user protection** &ndash; Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="dec21-113">**Oudere verificatie** &ndash; blokkeren Oudere client-apps en sommige nieuwe apps gebruiken geen nieuwere, veiligere verificatieprotocollen.</span><span class="sxs-lookup"><span data-stu-id="dec21-113">**Block legacy authentication** &ndash; Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="dec21-114">Deze oudere apps kunnen het beleid voor voorwaardelijke toegang omzeilen en ongeautoriseerde toegang tot uw omgeving krijgen.</span><span class="sxs-lookup"><span data-stu-id="dec21-114">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="dec21-115">Dit beleid blokkeert de toegang van clients die geen voorwaardelijke toegang ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="dec21-115">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="dec21-116">**MFA vereisen voor servicebeheer** &ndash; Vereist meervoudige verificatie voor toegang tot beheerhulpprogramma's, waaronder Azure-portal (waar u basislijnbeleid configureert).</span><span class="sxs-lookup"><span data-stu-id="dec21-116">**Require MFA for Service Management** &ndash; Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="dec21-117">Microsoft raadt u aan al deze basislijnbeleidsregels in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="dec21-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="dec21-118">Nadat dit beleid is ingeschakeld, worden beheerders en gebruikers gevraagd zich te registreren voor Azure Multii-Factor-verificatie.</span><span class="sxs-lookup"><span data-stu-id="dec21-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="dec21-119">Zie [Wat zijn basislijnbeleid](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)voor meer informatie over dit beleid?</span><span class="sxs-lookup"><span data-stu-id="dec21-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="dec21-120">Basislijnbeleid instellen</span><span class="sxs-lookup"><span data-stu-id="dec21-120">Set up baseline policies</span></span>

1. <span data-ttu-id="dec21-121">Ga naar [Azure-portal](https://portal.azure.com)en navigeer vervolgens naar **Azure Active Directory** \> **Conditional Access**.</span><span class="sxs-lookup"><span data-stu-id="dec21-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="dec21-122">Het basislijnbeleid wordt op de pagina weergegeven.</span><span class="sxs-lookup"><span data-stu-id="dec21-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="dec21-123">![Pagina met basislijnbeleid voor voorwaardelijke toegang.](../media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="dec21-123">![Page that lists baseline policies for conditional access.](../media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="dec21-124">Zie de volgende specifieke instructies voor elk beleid:</span><span class="sxs-lookup"><span data-stu-id="dec21-124">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="dec21-125">MFA vereisen voor beheerders</span><span class="sxs-lookup"><span data-stu-id="dec21-125">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="dec21-126">MFA vereisen voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="dec21-126">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="dec21-127">Oudere verificatie blokkeren</span><span class="sxs-lookup"><span data-stu-id="dec21-127">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="dec21-128">MFA vereisen voor servicebeheer</span><span class="sxs-lookup"><span data-stu-id="dec21-128">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="dec21-129">U veel extra beleidsregels instellen, zoals het vereisen van goedgekeurde client-apps.</span><span class="sxs-lookup"><span data-stu-id="dec21-129">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="dec21-130">Zie de documentatie [voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/)voor meer informatie .</span><span class="sxs-lookup"><span data-stu-id="dec21-130">For more information, see the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
