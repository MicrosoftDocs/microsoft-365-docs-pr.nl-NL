---
title: Instellen van het beleid voor Microsoft 365 campagnes voorwaardelijke toegang
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
search.appverid:
- BCS160
- MET150
- MOE150
description: Informatie over het instellen van het beleid van voorwaardelijke toegang voor Microsoft 365 campagnes.
ms.openlocfilehash: 7d8e1f16019d151478aae57b1593b0e0758e5b19
ms.sourcegitcommit: 7e46db0b35c188ee6a7b40ab3eb2d76ff6c101c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2019
ms.locfileid: "35086307"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="3504b-103">Instellen van het beleid van voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="3504b-103">Set up conditional access policies</span></span>

<span data-ttu-id="3504b-104">[-Voorwaardelijke](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) beleidsregels toevoegen substancial extra beveiliging.</span><span class="sxs-lookup"><span data-stu-id="3504b-104">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substancial additional security.</span></span> <span data-ttu-id="3504b-105">Microsoft biedt een reeks basislijn voorwaardelijke toegang beleidsregels die worden aanbevolen voor alle klanten.</span><span class="sxs-lookup"><span data-stu-id="3504b-105">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="3504b-106">Beleid van de basislijn zijn een reeks vooraf gedefinieerde beleidsinstellingen die organisaties tegen veel voorkomende aanvallen beschermen.</span><span class="sxs-lookup"><span data-stu-id="3504b-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="3504b-107">Deze gemeenschappelijke aanvallen zijn wachtwoord spray, replay en phishing.</span><span class="sxs-lookup"><span data-stu-id="3504b-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="3504b-108">Dit beleid is vereist voor beheerders en gebruikers kunnen invoeren, een tweede vorm van verificatie (multifactor-verificatie of MVR gesloten genoemd) wanneer aan bepaalde voorwaarden wordt voldaan.</span><span class="sxs-lookup"><span data-stu-id="3504b-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="3504b-109">Bijvoorbeeld als een gebruiker vanaf een ander land aanmeldt zich, moet het aanmelden kan worden beschouwd als riskant en de gebruiker een extra vorm van verificatie.</span><span class="sxs-lookup"><span data-stu-id="3504b-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="3504b-110">Op dit moment omvatten basislijn beleid het volgende:</span><span class="sxs-lookup"><span data-stu-id="3504b-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="3504b-111">**MVR gesloten nodig voor beheerders** — meerledige verificatie vereist is voor de meeste bevoegdheden beheerdersrollen, inclusief globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="3504b-111">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="3504b-112">**Bescherming van de eindgebruiker** — meerledige verificatie vereist is voor gebruikers alleen wanneer een aanmelden riskant is.</span><span class="sxs-lookup"><span data-stu-id="3504b-112">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="3504b-113">**Verouderde verificatie blok** , oudere clienttoepassingen en sommige nieuwe apps geen nieuwere, meer beveiligde verificatieprotocollen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3504b-113">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="3504b-114">Deze oudere apps kunnen omzeilen van beleid voor voorwaardelijke toegang en onbevoegde toegang krijgen tot uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="3504b-114">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="3504b-115">Dit beleid blokkeert de toegang van clients die geen ondersteuning voor voorwaardelijke toegang bieden.</span><span class="sxs-lookup"><span data-stu-id="3504b-115">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="3504b-116">**MVR gesloten vereist voor servicebeheer** , meerledige verificatie vereist is voor toegang tot de beheerprogramma's, waaronder Azure portal (waar u basislijn beleidsregels configureren).</span><span class="sxs-lookup"><span data-stu-id="3504b-116">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="3504b-117">Microsoft adviseert dat u deze basislijn beleid inschakelen.</span><span class="sxs-lookup"><span data-stu-id="3504b-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="3504b-118">Nadat u dit beleid hebt ingeschakeld, worden beheerders en gebruikers te registreren voor Azure Multii-Factor verificatie gevraagd.</span><span class="sxs-lookup"><span data-stu-id="3504b-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="3504b-119">Zie [Wat zijn volgens de basislijn beleid](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)voor meer informatie over deze beleidsregels?</span><span class="sxs-lookup"><span data-stu-id="3504b-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="3504b-120">Beleid basislijn instellen</span><span class="sxs-lookup"><span data-stu-id="3504b-120">Set up baseline policies</span></span>

1. <span data-ttu-id="3504b-121">Ga naar [Azure portal](https://portal.azure.com)en navigeer vervolgens naar **Azure Active Directory** \> **Voorwaardelijke toegang**.</span><span class="sxs-lookup"><span data-stu-id="3504b-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="3504b-122">Het beleid van de basislijn worden vermeld op de pagina.</span><span class="sxs-lookup"><span data-stu-id="3504b-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="3504b-123">![Pagina met basislijn beleid voor voorwaardelijke toegang.](media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="3504b-123">![Page that lists baseline policies for conditional access.](media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="3504b-124">Zie de volgende specifieke instructies voor elk beleid:</span><span class="sxs-lookup"><span data-stu-id="3504b-124">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="3504b-125">MVR gesloten voor beheerders vereisen</span><span class="sxs-lookup"><span data-stu-id="3504b-125">Require MFA for admins</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="3504b-126">MFA Reequire voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="3504b-126">Reequire MFA for users</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="3504b-127">Verouderde verificatie blokkeren</span><span class="sxs-lookup"><span data-stu-id="3504b-127">Block legacy authentication</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="3504b-128">MVR gesloten vereist voor servicebeheer</span><span class="sxs-lookup"><span data-stu-id="3504b-128">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="3504b-129">U kunt veel aanvullend beleid, zoals het verplicht stellen van goedgekeurde clienttoepassingen instellen.</span><span class="sxs-lookup"><span data-stu-id="3504b-129">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="3504b-130">Raadpleeg de [Documentatie van voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3504b-130">See the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/) for more information.</span></span>