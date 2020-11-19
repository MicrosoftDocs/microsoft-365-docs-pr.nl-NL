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
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: 55a84fa8ba31cfd4f981f2820811b541ae340a27
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357621"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="cf6d5-103">Beleid voor het toestaan van toegang via gast en externe B2B</span><span class="sxs-lookup"><span data-stu-id="cf6d5-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="cf6d5-104">In dit artikel wordt uitgelegd hoe u de aanbevolen beleidsregels voor identiteit en Apparaattoegang aanpast om toegang te krijgen tot gast en externe gebruikers die een Azure Active Directory-Business-to-Business-account (B2B) bieden.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-104">This article describes how to adjust the recommended common identity and device access policies to allow access for guest and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="cf6d5-105">Deze richtlijnen zijn van toepassing op de [veelgebruikte beleidsregels voor identiteit en toegang tot apparaten](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cf6d5-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="cf6d5-106">Deze aanbevelingen zijn bedoeld om toe te passen op de **basis** niveau beveiliging.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="cf6d5-107">U kunt echter ook de aanbevelingen aanpassen op basis van de granulatie van uw behoeften voor **gevoelige** en **sterk gereguleerde** bescherming.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="cf6d5-108">Als u een pad opgeeft voor B2B-accounts voor verificatie met de Azure AD-Tenant, bieden deze accounts geen toegang tot uw gehele omgeving.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="cf6d5-109">B2B-gebruikers en hun accounts hebben alleen toegang tot de bronnen die met hen zijn gedeeld (zoals bestanden) binnen de services die zijn toegewezen aan voorwaardelijke toegangsbeleid.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-109">B2B users and their accounts only have access to resources that are shared with them (such as files) within the services granted in Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="cf6d5-110">Veelgebruikte beleidsregels bijwerken om gast en externe toegang toe te staan en te beschermen</span><span class="sxs-lookup"><span data-stu-id="cf6d5-110">Updating the common policies to allow and protect guest and external access</span></span>

<span data-ttu-id="cf6d5-111">In het volgende diagram ziet u welke beleidsregels u toevoegt of bijwerkt in de algemene beleidsregels voor identiteit en Apparaattoegang om gast en externe toegang te beschermen met Azure AD B2B-accounts.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-111">To protect guest and external access with Azure AD B2B accounts, the following diagram illustrates which policies to add or update from the the common identity and device access policies.</span></span>

<span data-ttu-id="cf6d5-112">[![Overzicht van beleidsupdates voor de bescherming van gasttoegang](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="cf6d5-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="cf6d5-113">Een grotere versie van deze afbeelding weergeven</span><span class="sxs-lookup"><span data-stu-id="cf6d5-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="cf6d5-114">In de volgende tabel vindt u een overzicht van de beleidsregels die u moet maken en bijwerken.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="cf6d5-115">De koppeling common policies naar de gekoppelde configuratie-instructies in het artikel [common Identity en Apparaattoegang-beleid](identity-access-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="cf6d5-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="cf6d5-116">Beveiligingsniveau</span><span class="sxs-lookup"><span data-stu-id="cf6d5-116">Protection level</span></span>|<span data-ttu-id="cf6d5-117">Lijnen</span><span class="sxs-lookup"><span data-stu-id="cf6d5-117">Policies</span></span>|<span data-ttu-id="cf6d5-118">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="cf6d5-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="cf6d5-119">**Basislijn**</span><span class="sxs-lookup"><span data-stu-id="cf6d5-119">**Baseline**</span></span>|[<span data-ttu-id="cf6d5-120">MFA vereisen altijd voor gast en externe gebruikers</span><span class="sxs-lookup"><span data-stu-id="cf6d5-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="cf6d5-121">Maak dit nieuwe beleid en configureer de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="cf6d5-121">Create this new policy and configure:</span></span> <ul><li> <span data-ttu-id="cf6d5-122">Voor **toewijzingen > gebruikers en groepen > toevoegen**, kiest **u gebruikers en groepen selecteren** en selecteert u vervolgens **alle gast en externe gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span> </li><li> <span data-ttu-id="cf6d5-123">Voor **toewijzingen > voorwaarden > aanmelden**, schakelt u alle opties uit als u meervoudige verificatie (MFA) altijd wilt afdwingen.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li>|
||[<span data-ttu-id="cf6d5-124">MFA vereisen wanneer het aanmeld risico *normaal* of *hoog* is</span><span class="sxs-lookup"><span data-stu-id="cf6d5-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="cf6d5-125">Dit beleid wijzigen om gast en externe gebruikers uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-125">Modify this policy to exclude guest and external users.</span></span>|
||[<span data-ttu-id="cf6d5-126">Eis conforme pc’s</span><span class="sxs-lookup"><span data-stu-id="cf6d5-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="cf6d5-127">Dit beleid wijzigen om gast en externe gebruikers uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-127">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="cf6d5-128">Als u gast en externe gebruikers wilt opnemen in en uitsluiten van beleidsregels voor voorwaardelijke toegang voor **toewijzingen > gebruikers en groepen > toevoegen** of **uitsluiten**, controleert u **alle gast en externe gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-128">To include or exclude guest and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![schermopname van besturingselementen voor exclusief gast en externe gebruikers](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="cf6d5-130">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="cf6d5-130">More information</span></span>

### <a name="guest-and-external-access-with-microsoft-teams"></a><span data-ttu-id="cf6d5-131">Gast en externe toegang met Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="cf6d5-131">Guest and external access with Microsoft Teams</span></span>

<span data-ttu-id="cf6d5-132">In Microsoft teams wordt het volgende gedefinieerd:</span><span class="sxs-lookup"><span data-stu-id="cf6d5-132">Microsoft Teams defines the following:</span></span>

- <span data-ttu-id="cf6d5-133">**Gasttoegang** maakt gebruik van een Azure AD B2B-account dat kan worden toegevoegd als lid van een team en gemachtigd zijn om toegang te krijgen tot de communicatie en de bronnen van het team.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have all permissioned access to the communications and resources of the team.</span></span>

- <span data-ttu-id="cf6d5-134">**Externe toegang** is bedoeld voor externe gebruikers die geen B2B-account hebben.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-134">**External access** is for an external user that does not have a B2B account.</span></span> <span data-ttu-id="cf6d5-135">Externe toegang omvat uitnodigingen en deelnemen aan gesprekken, chats en vergaderingen, maar omvat geen team lidmaatschap en toegang tot de bronnen van het team.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-135">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="cf6d5-136">Zie de [vergelijking tussen gast en externe toegang voor teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-136">For more information, see the [comparison between guest and external access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="cf6d5-137">Beleidsregels voor voorwaardelijke toegang gelden alleen voor gasttoegang in teams omdat er een Azure AD B2B-account is.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-137">Conditional Access policies only apply to guest access in Teams because there is a corresponding Azure AD B2B account.</span></span>

<span data-ttu-id="cf6d5-138">Raadpleeg [beleids aanbevelingen voor het beveiligen van teams-chats,-groepen en-bestanden](teams-access-policies.md) voor meer informatie over het beveiligen van identiteits-en Apparaattoegang voor teams.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-138">See [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md) for more information about securing identity and device access policies for Teams.</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="cf6d5-139">MFA vereisen altijd voor gast en externe gebruikers</span><span class="sxs-lookup"><span data-stu-id="cf6d5-139">Require MFA always for guest and external users</span></span>

<span data-ttu-id="cf6d5-140">Dit beleid vraagt bezoekers zich voor MFA aan te melden bij uw Tenant, ongeacht of ze zich voor MFA registreren in hun thuis Tenant.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-140">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="cf6d5-141">Bij het openen van bronnen in de Tenant zijn gast en externe gebruikers verplicht MFA te gebruiken voor elke aanvraag.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-141">When accessing resources in your tenant, guest and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="cf6d5-142">Gast en externe gebruikers uitsluiten van MFA op basis van risico</span><span class="sxs-lookup"><span data-stu-id="cf6d5-142">Excluding guest and external users from risk-based MFA</span></span>

<span data-ttu-id="cf6d5-143">Organisaties kunnen op basis van risico beleid voor B2B-gebruikers die gebruikmaken van Azure Active Directory-identiteitsbeveiliging, beperkingen instellen voor de implementatie van Azure AD-identiteitsbeveiliging voor B2B-samenwerkings gebruikers in een resource directory, omdat hun identiteit in hun basismap zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-143">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="cf6d5-144">Vanwege deze beperkingen adviseert Microsoft gastgebruikers uit te sluiten van op riskniveau MFA-beleidsregels en vragen deze gebruikers altijd MFA te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-144">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="cf6d5-145">Zie [beperkingen van identiteits bescherming voor B2B-samenwerkings gebruikers](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-145">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="cf6d5-146">Gebruikers van het beheer van apparaten zonder gast en externe gebruikers uitsluiten</span><span class="sxs-lookup"><span data-stu-id="cf6d5-146">Excluding guest and external users from device management</span></span>

<span data-ttu-id="cf6d5-147">Er kan slechts één organisatie een apparaat beheren.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-147">Only one organization can manage a device.</span></span> <span data-ttu-id="cf6d5-148">Als u gast en externe gebruikers niet uitsluiten van beleidsregels waarvoor de naleving van een apparaat is vereist, blok keert dit beleid deze gebruikers.</span><span class="sxs-lookup"><span data-stu-id="cf6d5-148">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="cf6d5-149">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="cf6d5-149">Next step</span></span>

![Stap 4: beleidsregels voor Microsoft 365 Cloud-apps](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="cf6d5-151">Beleidsregels voor voorwaardelijke toegang configureren voor:</span><span class="sxs-lookup"><span data-stu-id="cf6d5-151">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="cf6d5-152">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf6d5-152">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="cf6d5-153">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cf6d5-153">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="cf6d5-154">SharePoint</span><span class="sxs-lookup"><span data-stu-id="cf6d5-154">SharePoint</span></span>](sharepoint-file-access-policies.md)
