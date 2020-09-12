---
title: Beleid voor identiteits-en toegangsbeleid voor het verlenen van toegang via gast en externe B2B-Microsoft 365 voor Enterprise | Microsoft docs
description: Een beschrijving van de aanbevolen voorwaardelijke toegang en gerelateerde beleidsregels voor de bescherming van de toegang van gasten en externe gebruikers.
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
ms.openlocfilehash: a88fc5f46a6dafda72a24ba5e80587b24a216955
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546470"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="57da5-103">Beleid voor het toestaan van toegang via gast en externe B2B</span><span class="sxs-lookup"><span data-stu-id="57da5-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="57da5-104">In dit artikel wordt uitgelegd hoe u de aanbevolen beleidsregels voor identiteits-en Apparaattoegang kunt aanpassen, zodat u toegang hebt tot een account van Business-to-Business (B2B) en externe gebruikers.</span><span class="sxs-lookup"><span data-stu-id="57da5-104">This article describes how to adjust the recommended common identity and device access policies to allow Business-to-Business (B2B) account access (guest and external users).</span></span> <span data-ttu-id="57da5-105">Deze richtlijnen zijn van toepassing op de [veelgebruikte beleidsregels voor identiteit en toegang tot apparaten](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="57da5-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="57da5-106">Deze aanbevelingen zijn bedoeld om toe te passen op de **basis** niveau beveiliging.</span><span class="sxs-lookup"><span data-stu-id="57da5-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="57da5-107">U kunt echter ook de aanbevelingen aanpassen op basis van de granulatie van uw behoeften voor **gevoelige** en **sterk gereguleerde** bescherming.</span><span class="sxs-lookup"><span data-stu-id="57da5-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="57da5-108">Als u een pad opgeeft voor B2B-gebruikers die zich in de Tenant van Azure Active Directory (Azure AD) bevinden, bieden deze gebruikers geen toegang tot uw gehele omgeving.</span><span class="sxs-lookup"><span data-stu-id="57da5-108">Providing a path for B2B users to authenticate with your Azure Active Directory (Azure AD) tenant doesn't give these users access to your entire environment.</span></span> <span data-ttu-id="57da5-109">B2B-gebruikers hebben alleen toegang tot bronnen die met hen zijn gedeeld (zoals bestanden) binnen de services die in het beleid voor voorwaardelijke toegang zijn verleend.</span><span class="sxs-lookup"><span data-stu-id="57da5-109">B2B users only have access to resources that are shared with them (such as files) within the services granted in the Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="57da5-110">Veelgebruikte beleidsregels bijwerken om gast en externe toegang toe te staan en te beschermen</span><span class="sxs-lookup"><span data-stu-id="57da5-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="57da5-111">In het volgende diagram ziet u welke beleidsregels u toevoegt of bijwerkt vanuit de veelgebruikte beleidsregels identiteit en Apparaattoegang.</span><span class="sxs-lookup"><span data-stu-id="57da5-111">To protect guest and external access, the following diagram illustrates which policies to add or update from the the common identity and device access policies .</span></span> 

<span data-ttu-id="57da5-112">[![Overzicht van beleidsupdates voor de bescherming van gasttoegang](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="57da5-112">[![Summary of policy updates for protecting guest access](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="57da5-113">Een grotere versie van deze afbeelding weergeven</span><span class="sxs-lookup"><span data-stu-id="57da5-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="57da5-114">In de volgende tabel vindt u een overzicht van de beleidsregels die u moet bijwerken of nieuw moet maken.</span><span class="sxs-lookup"><span data-stu-id="57da5-114">The following table lists the policies you either need to update or create new.</span></span> <span data-ttu-id="57da5-115">De koppeling common policies naar de gekoppelde configuratie-instructies in het artikel [common Identity en Apparaattoegang-beleid](identity-access-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="57da5-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="57da5-116">Beveiligingsniveau</span><span class="sxs-lookup"><span data-stu-id="57da5-116">Protection level</span></span>|<span data-ttu-id="57da5-117">Lijnen</span><span class="sxs-lookup"><span data-stu-id="57da5-117">Policies</span></span>|<span data-ttu-id="57da5-118">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="57da5-118">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="57da5-119">**Basislijn**</span><span class="sxs-lookup"><span data-stu-id="57da5-119">**Baseline**</span></span>|[<span data-ttu-id="57da5-120">MFA vereisen altijd voor gast en externe gebruikers</span><span class="sxs-lookup"><span data-stu-id="57da5-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="57da5-121">Dit nieuwe beleid maken en toepassen op gasten en externe gebruikers.</span><span class="sxs-lookup"><span data-stu-id="57da5-121">Create this new policy and apply it only to guests and external users.</span></span> <span data-ttu-id="57da5-122">Schakel onder **risico voor aanmelden**de optie alle opties uit als u meervoudige verificatie (MFA) altijd wilt afdwingen.</span><span class="sxs-lookup"><span data-stu-id="57da5-122">Under **Sign-in risk**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span>|
|        |[<span data-ttu-id="57da5-123">MFA vereisen wanneer het aanmeld risico *normaal* of *hoog* is</span><span class="sxs-lookup"><span data-stu-id="57da5-123">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="57da5-124">Dit beleid wijzigen om gast en externe gebruikers uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="57da5-124">Modify this policy to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="57da5-125">Eis conforme pc’s</span><span class="sxs-lookup"><span data-stu-id="57da5-125">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="57da5-126">Dit beleid wijzigen om gast en externe gebruikers uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="57da5-126">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="57da5-127">Als u gasten en externe gebruikers wilt opnemen of uitsluiten in regels voor voorwaardelijke toegang, klikt u op het tabblad **opnemen** of **uitsluiten** en schakelt u **alle gasten en externe gebruikers**in.</span><span class="sxs-lookup"><span data-stu-id="57da5-127">To include or exclude guests and external users in Conditional Access policies, click the **Include** or **Exclude** tab and check **All guests and external users**.</span></span>

![schermopname van besturingselementen voor exclusief gasten](../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="57da5-129">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="57da5-129">More information</span></span>

### <a name="guests-vs-external-users"></a><span data-ttu-id="57da5-130">Gasten versus externe gebruikers</span><span class="sxs-lookup"><span data-stu-id="57da5-130">Guests vs. external users</span></span>
<span data-ttu-id="57da5-131">In azure AD zijn gast en externe gebruikers hetzelfde.</span><span class="sxs-lookup"><span data-stu-id="57da5-131">In Azure AD, guest and external users are the same.</span></span> <span data-ttu-id="57da5-132">Het gebruikerstype voor beide gebruikers is gast.</span><span class="sxs-lookup"><span data-stu-id="57da5-132">The user type for both of these is Guest.</span></span> <span data-ttu-id="57da5-133">Gastgebruikers zijn B2B-gebruikers.</span><span class="sxs-lookup"><span data-stu-id="57da5-133">Guest users are B2B users.</span></span>

<span data-ttu-id="57da5-134">In Microsoft teams wordt onderscheid gemaakt tussen gastgebruikers en externe gebruikers binnen de app, maar dit zijn beide B2B-gebruikers bij het verifiëren.</span><span class="sxs-lookup"><span data-stu-id="57da5-134">Microsoft Teams differentiates between guest users and external users within the app, but these are both B2B users when authenticating.</span></span> <span data-ttu-id="57da5-135">Zie voor meer informatie over team gast en externe gebruikers het artikel [gast en externe toegang inschakelen voor teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).</span><span class="sxs-lookup"><span data-stu-id="57da5-135">For more information about Teams guest and external users, see [Enabling guest and external access for Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="57da5-136">MFA vereisen altijd voor gast en externe gebruikers</span><span class="sxs-lookup"><span data-stu-id="57da5-136">Require MFA always for guest and external users</span></span>
<span data-ttu-id="57da5-137">Dit beleid vraagt bezoekers zich voor MFA aan te melden bij uw Tenant, ongeacht of ze zich voor MFA registreren in hun thuis Tenant.</span><span class="sxs-lookup"><span data-stu-id="57da5-137">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="57da5-138">Bij het openen van bronnen in de Tenant zijn gasten en externe gebruikers verplicht MFA te gebruiken voor elke aanvraag.</span><span class="sxs-lookup"><span data-stu-id="57da5-138">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="57da5-139">Gast en externe gebruikers uitsluiten van MFA op basis van risico</span><span class="sxs-lookup"><span data-stu-id="57da5-139">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="57da5-140">Organisaties kunnen op basis van risico beleid voor B2B-gebruikers die gebruikmaken van Azure Active Directory-identiteitsbeveiliging, beperkingen instellen voor de implementatie van Azure AD-identiteitsbeveiliging voor B2B-samenwerkings gebruikers in een resource directory, omdat hun identiteit in hun basismap zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="57da5-140">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="57da5-141">Vanwege deze beperkingen adviseert Microsoft gastgebruikers uit te sluiten van op riskniveau MFA-beleidsregels en vragen deze gebruikers altijd MFA te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="57da5-141">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="57da5-142">Zie [beperkingen van identiteits bescherming voor B2B-samenwerkings gebruikers](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="57da5-142">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="57da5-143">Gebruikers van het beheer van apparaten zonder gast en externe gebruikers uitsluiten</span><span class="sxs-lookup"><span data-stu-id="57da5-143">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="57da5-144">Er kan slechts één organisatie een apparaat beheren.</span><span class="sxs-lookup"><span data-stu-id="57da5-144">Only one organization can manage a device.</span></span> <span data-ttu-id="57da5-145">Als u gast en externe gebruikers niet uitsluiten van beleidsregels waarvoor de naleving van een apparaat is vereist, blok keert dit beleid deze gebruikers.</span><span class="sxs-lookup"><span data-stu-id="57da5-145">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-step"></a><span data-ttu-id="57da5-146">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="57da5-146">Next step</span></span>

![Stap 4: beleidsregels voor Microsoft 365 Cloud-apps](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="57da5-148">Beleidsregels voor voorwaardelijke toegang configureren voor:</span><span class="sxs-lookup"><span data-stu-id="57da5-148">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="57da5-149">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="57da5-149">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="57da5-150">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="57da5-150">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="57da5-151">SharePoint</span><span class="sxs-lookup"><span data-stu-id="57da5-151">SharePoint</span></span>](secure-email-recommended-policies.md)

