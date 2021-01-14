---
title: Beleid voor identiteits-en toegangsbeleid voor het toestaan van gastgebruikers en externe gebruikers B2B Access-Microsoft 365 voor ondernemingen | Microsoft docs
description: Een beschrijving van de aanbevolen voorwaardelijke toegang en gerelateerde beleidsregels voor het beschermen van de toegang van gasten en externe gebruikers.
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: 4ee6cb93e5c943d704950e28ba4dc70a246429a6
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845074"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="aaeaf-103">Beleid voor het verlenen van toegang tot gasttoegang en B2B-toegang tot externe gebruikers</span><span class="sxs-lookup"><span data-stu-id="aaeaf-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="aaeaf-104">Dit artikel bevat informatie over het aanpassen van het aanbevolen beleid voor het aanwijzen van gebruikers en het instellen van toegangsbeleid voor gasten en externe gebruikers die een Azure Active Directory-account (Azure AD) voor Business-to-Business (B2B) hebben.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="aaeaf-105">Deze richtlijnen zijn van toepassing op de [veelgebruikte beleidsregels voor identiteit en toegang tot apparaten](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="aaeaf-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="aaeaf-106">Deze aanbevelingen zijn bedoeld om toe te passen op de **basis** niveau beveiliging.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="aaeaf-107">U kunt ook de aanbevelingen aanpassen op basis van uw specifieke behoeften voor **gevoelige** en **sterk begereglementeerde** bescherming.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="aaeaf-108">Als u een pad opgeeft voor B2B-accounts voor verificatie met de Azure AD-Tenant, bieden deze accounts geen toegang tot uw gehele omgeving.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="aaeaf-109">B2B-gebruikers en hun accounts hebben toegang tot services en bronnen, zoals bestanden, gedeeld door het beleid voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="aaeaf-110">Veelgebruikte beleidsregels bijwerken om gasten en externe gebruikers toegang toe te staan en te beschermen</span><span class="sxs-lookup"><span data-stu-id="aaeaf-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="aaeaf-111">In dit diagram ziet u welke beleidsregels u kunt toevoegen of bijwerken tussen de veelgebruikte beleidsregels voor identiteits-en Apparaattoegang, voor B2B-gasten en externe gebruikers toegang.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="aaeaf-112">[![Overzicht van beleidsupdates voor de bescherming van gasttoegang](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="aaeaf-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="aaeaf-113">Een grotere versie van deze afbeelding weergeven</span><span class="sxs-lookup"><span data-stu-id="aaeaf-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="aaeaf-114">In de volgende tabel vindt u een overzicht van de beleidsregels die u moet maken en bijwerken.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="aaeaf-115">De koppeling common policies naar de gekoppelde configuratie-instructies in het artikel [common Identity en Apparaattoegang-beleid](identity-access-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="aaeaf-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="aaeaf-116">Beveiligingsniveau</span><span class="sxs-lookup"><span data-stu-id="aaeaf-116">Protection level</span></span>|<span data-ttu-id="aaeaf-117">Lijnen</span><span class="sxs-lookup"><span data-stu-id="aaeaf-117">Policies</span></span>|<span data-ttu-id="aaeaf-118">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="aaeaf-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="aaeaf-119">**Basislijn**</span><span class="sxs-lookup"><span data-stu-id="aaeaf-119">**Baseline**</span></span>|[<span data-ttu-id="aaeaf-120">MFA vereist altijd voor gasten en externe gebruikers</span><span class="sxs-lookup"><span data-stu-id="aaeaf-120">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="aaeaf-121">Maak dit nieuwe beleid en configureer de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="aaeaf-121">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="aaeaf-122">Voor **toewijzingen > gebruikers en groepen > toevoegen**, kiest **u gebruikers en groepen selecteren** en selecteert u vervolgens **alle gast en externe gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="aaeaf-123">Voor **toewijzingen > voorwaarden > aanmelden**, schakelt u alle opties uit als u meervoudige verificatie (MFA) altijd wilt afdwingen.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="aaeaf-124">MFA vereisen wanneer het aanmeld risico *normaal* of *hoog* is</span><span class="sxs-lookup"><span data-stu-id="aaeaf-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="aaeaf-125">Dit beleid wijzigen om gasten en externe gebruikers uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-125">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="aaeaf-126">Eis conforme pc’s</span><span class="sxs-lookup"><span data-stu-id="aaeaf-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="aaeaf-127">Dit beleid wijzigen om gasten en externe gebruikers uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-127">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="aaeaf-128">Als u gasten en externe gebruikers in beleidsregels voor voorwaardelijke toegang wilt opnemen of uitsluiten, schakelt u de selectievakjes voor **toewijzingen > gebruikers en groepen > toevoegen** of **uitsluiten** in en schakelt u **alle gast en externe gebruikers** in.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-128">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![schermopname van besturingselementen voor exclusief gasten en externe gebruikers](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="aaeaf-130">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="aaeaf-130">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="aaeaf-131">Gasten en externe gebruikers toegang met Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="aaeaf-131">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="aaeaf-132">In Microsoft teams worden de volgende gebruikers gedefinieerd:</span><span class="sxs-lookup"><span data-stu-id="aaeaf-132">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="aaeaf-133">**Gasttoegang** maakt gebruik van een Azure AD B2B-account dat kan worden toegevoegd als lid van een team en toegang hebben tot de communicatie en de bronnen van het team.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="aaeaf-134">**Externe toegang** is bedoeld voor externe gebruikers die geen B2B-account hebben.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-134">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="aaeaf-135">Toegang tot externe gebruikers omvat uitnodigingen, gesprekken, chats en vergaderingen, maar omvat geen team lidmaatschap en toegang tot de bronnen van het team.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-135">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="aaeaf-136">Zie de [vergelijking tussen gasten en externe gebruikers toegang voor teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-136">For more information, see the [comparison between guests and external user access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="aaeaf-137">Zie [aanbevelingen voor het beveiligen van teams-chats,-groepen en-bestanden](teams-access-policies.md)voor meer informatie over het beveiligen van beleidsregels voor identiteit en Apparaattoegang voor teams.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-137">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="aaeaf-138">MFA vereisen altijd voor gast en externe gebruikers</span><span class="sxs-lookup"><span data-stu-id="aaeaf-138">Require MFA always for guest and external users</span></span>

<span data-ttu-id="aaeaf-139">Dit beleid vraagt bezoekers zich voor MFA aan te melden bij uw Tenant, ongeacht of ze zich voor MFA registreren in hun thuis Tenant.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-139">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="aaeaf-140">Bij het openen van bronnen in de Tenant zijn gasten en externe gebruikers verplicht MFA te gebruiken voor elke aanvraag.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-140">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="aaeaf-141">Gasten en externe gebruikers uitsluiten van MFA op basis van risico</span><span class="sxs-lookup"><span data-stu-id="aaeaf-141">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="aaeaf-142">Organisaties kunnen op basis van risico beleid voor B2B-gebruikers die gebruikmaken van Azure Active Directory-identiteitsbeveiliging, beperkingen instellen voor de implementatie van Azure AD-identiteitsbeveiliging voor B2B-samenwerkings gebruikers in een resource directory, omdat hun identiteit in hun basismap zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-142">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="aaeaf-143">Als gevolg van deze beperkingen adviseert Microsoft gasten niet uit te sluiten op basis van Risk MFA-beleidsregels en vragen deze gebruikers altijd MFA te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-143">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="aaeaf-144">Zie [beperkingen van identiteits bescherming voor B2B-samenwerkings gebruikers](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-144">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="aaeaf-145">Gasten en externe gebruikers uitsluiten van Apparaatbeheer</span><span class="sxs-lookup"><span data-stu-id="aaeaf-145">Excluding guests and external users from device management</span></span>

<span data-ttu-id="aaeaf-146">Er kan slechts één organisatie een apparaat beheren.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-146">Only one organization can manage a device.</span></span> <span data-ttu-id="aaeaf-147">Als u gasten en externe gebruikers niet uitsluiten van beleidsregels waarvoor de naleving van een apparaat is vereist, blok keert dit beleid deze gebruikers.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-147">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="aaeaf-148">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="aaeaf-148">Next step</span></span>

![Stap 4: beleidsregels voor Microsoft 365 Cloud-apps](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="aaeaf-150">Beleidsregels voor voorwaardelijke toegang configureren voor:</span><span class="sxs-lookup"><span data-stu-id="aaeaf-150">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="aaeaf-151">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aaeaf-151">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="aaeaf-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="aaeaf-152">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="aaeaf-153">SharePoint</span><span class="sxs-lookup"><span data-stu-id="aaeaf-153">SharePoint</span></span>](sharepoint-file-access-policies.md)
