---
title: Identiteits- en apparaattoegangsbeleid voor het toestaan van B2B-toegang van gast en externe gebruiker - Microsoft 365 voor ondernemingen | Microsoft Docs
description: Hier worden de aanbevolen voorwaardelijke toegang en verwante beleidsregels voor de beveiliging van de toegang van gasten en externe gebruikers beschreven.
ms.prod: m365-security
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
ms.technology: mdo
ms.openlocfilehash: 2ef494f8e383f50f16b1e64f6387b6e5d62459c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932608"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="49724-103">Beleidsregels voor het toestaan van gasttoegang en B2B-toegang voor externe gebruikers</span><span class="sxs-lookup"><span data-stu-id="49724-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="49724-104">In dit artikel wordt beschreven hoe u het aanbevolen beleid voor apparaat- en identiteitstoegang kunt aanpassen om toegang toe te staan voor gasten en externe gebruikers met een Azure Active Directory-account (Azure AD) business-to-business-account (B2B).</span><span class="sxs-lookup"><span data-stu-id="49724-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="49724-105">Deze richtlijnen zijn gebaseerd op [het algemene beleid voor identiteits- en apparaattoegang.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="49724-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="49724-106">Deze aanbevelingen zijn bedoeld voor  de basislijnbeveiligingslaag.</span><span class="sxs-lookup"><span data-stu-id="49724-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="49724-107">Maar u kunt de aanbevelingen ook aanpassen op basis van uw specifieke behoeften aan **gevoelige** en **sterk reguleerde** bescherming.</span><span class="sxs-lookup"><span data-stu-id="49724-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="49724-108">Als een pad wordt gebruikt voor B2B-accounts voor verificatie bij uw Azure AD-tenant, hebben deze accounts niet toegang tot uw hele omgeving.</span><span class="sxs-lookup"><span data-stu-id="49724-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="49724-109">B2B-gebruikers en hun accounts hebben toegang tot services en bronnen, zoals bestanden, die met hen zijn gedeeld via het beleid voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="49724-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="49724-110">Het algemene beleid bijwerken om gasten en externe gebruikerstoegang toe te staan en te beschermen</span><span class="sxs-lookup"><span data-stu-id="49724-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="49724-111">In dit diagram ziet u welk beleid moet worden toegevoegd of bijgewerkt tussen het algemene beleid voor identiteits- en apparaattoegang voor B2B-gasten en externe gebruikerstoegang.</span><span class="sxs-lookup"><span data-stu-id="49724-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="49724-112">[![Overzicht van beleidsupdates voor het beveiligen van gasttoegang](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="49724-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="49724-113">Een grotere versie van deze afbeelding bekijken</span><span class="sxs-lookup"><span data-stu-id="49724-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="49724-114">De volgende tabel bevat het beleid dat u moet maken en bijwerken.</span><span class="sxs-lookup"><span data-stu-id="49724-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="49724-115">De koppeling naar de bijbehorende configuratie-instructies in het artikel Common [identity and device access policies (Algemene identiteit en apparaattoegangsbeleid) is](identity-access-policies.md) gekoppeld aan de bijbehorende configuratie-instructies.</span><span class="sxs-lookup"><span data-stu-id="49724-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="49724-116">Beveiligingsniveau</span><span class="sxs-lookup"><span data-stu-id="49724-116">Protection level</span></span>|<span data-ttu-id="49724-117">Beleidsregels</span><span class="sxs-lookup"><span data-stu-id="49724-117">Policies</span></span>|<span data-ttu-id="49724-118">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="49724-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="49724-119">**Basislijn**</span><span class="sxs-lookup"><span data-stu-id="49724-119">**Baseline**</span></span>|[<span data-ttu-id="49724-120">MFA altijd vereisen voor gasten en externe gebruikers</span><span class="sxs-lookup"><span data-stu-id="49724-120">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="49724-121">Maak dit nieuwe beleid en configureer:</span><span class="sxs-lookup"><span data-stu-id="49724-121">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="49724-122">Voor **opdrachten > gebruikers en** groepen >, kiest u Gebruikers en groepen selecteren en vervolgens Alle gast en **externe gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="49724-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="49724-123">Als **voor toewijzingen > de >,** laat u alle opties uitgeschakeld om altijd meervoudige verificatie (MFA) af te dwingen.</span><span class="sxs-lookup"><span data-stu-id="49724-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="49724-124">MFA vereisen wanneer het aanmeldingsrisico *gemiddeld* *of* hoog is</span><span class="sxs-lookup"><span data-stu-id="49724-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="49724-125">Wijzig dit beleid om gasten en externe gebruikers uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="49724-125">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="49724-126">Eis conforme pc’s</span><span class="sxs-lookup"><span data-stu-id="49724-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="49724-127">Wijzig dit beleid om gasten en externe gebruikers uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="49724-127">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="49724-128">Als u gasten en externe gebruikers wilt opnemen > uitsluiten in het beleid voor **voorwaardelijke** toegang, moet u voor Toewijzingen > Gebruikers en groepen > Alle gast en externe gebruikers opnemen of **uitsluiten.** </span><span class="sxs-lookup"><span data-stu-id="49724-128">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![schermopname van besturingselementen voor het uitsluiten van gasten en externe gebruikers](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="49724-130">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="49724-130">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="49724-131">Gasten en externe gebruikerstoegang met Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="49724-131">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="49724-132">Microsoft Teams definieert de volgende gebruikers:</span><span class="sxs-lookup"><span data-stu-id="49724-132">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="49724-133">**Voor gasttoegang** wordt een B2B Azure AD-account gebruikt dat kan worden toegevoegd als lid van een team en toegang heeft tot de communicatie en bronnen van het team.</span><span class="sxs-lookup"><span data-stu-id="49724-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="49724-134">**Externe toegang** is voor een externe gebruiker die geen B2B-account heeft.</span><span class="sxs-lookup"><span data-stu-id="49724-134">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="49724-135">Externe gebruikerstoegang omvat uitnodigingen, oproepen, chats en vergaderingen, maar omvat geen teamlidmaatschap en toegang tot de resources van het team.</span><span class="sxs-lookup"><span data-stu-id="49724-135">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="49724-136">Zie de vergelijking tussen gasten en externe gebruikerstoegang [voor teams voor meer informatie.](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="49724-136">For more information, see the [comparison between guests and external user access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="49724-137">Zie Beleidsaanbevelingen voor het beveiligen van [Teams-chats,](teams-access-policies.md)-groepen en -bestanden voor meer informatie over het beveiligen van identiteits- en apparaattoegangsbeleid voor Teams.</span><span class="sxs-lookup"><span data-stu-id="49724-137">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="49724-138">MFA altijd vereisen voor gast- en externe gebruikers</span><span class="sxs-lookup"><span data-stu-id="49724-138">Require MFA always for guest and external users</span></span>

<span data-ttu-id="49724-139">Met dit beleid wordt gasten gevraagd zich te registreren voor MFA in uw tenant, ongeacht of ze zijn geregistreerd voor MFA in hun thuisten tenant.</span><span class="sxs-lookup"><span data-stu-id="49724-139">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="49724-140">Als u bronnen in uw tenant gebruikt, moeten gasten en externe gebruikers MFA gebruiken voor elke aanvraag.</span><span class="sxs-lookup"><span data-stu-id="49724-140">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="49724-141">Gasten en externe gebruikers uitsluiten van risicogebaseerde MFA</span><span class="sxs-lookup"><span data-stu-id="49724-141">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="49724-142">Hoewel organisaties risicogebaseerd beleid kunnen afdwingen voor B2B-gebruikers die Azure AD-identiteitsbescherming gebruiken, gelden er beperkingen voor de implementatie van Azure AD-identiteitsbescherming voor B2B-samenwerkingsgebruikers in een resourcemap vanwege hun identiteit die in hun thuismap bestaat.</span><span class="sxs-lookup"><span data-stu-id="49724-142">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="49724-143">Vanwege deze beperkingen raadt Microsoft u aan gasten uit te sluiten van risicogebaseerd MFA-beleid en deze gebruikers altijd MFA te laten gebruiken.</span><span class="sxs-lookup"><span data-stu-id="49724-143">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="49724-144">Zie Beperkingen van [identiteitsbeveiliging voor B2B-samenwerkingsgebruikers voor meer informatie.](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)</span><span class="sxs-lookup"><span data-stu-id="49724-144">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="49724-145">Gasten en externe gebruikers uitsluiten van apparaatbeheer</span><span class="sxs-lookup"><span data-stu-id="49724-145">Excluding guests and external users from device management</span></span>

<span data-ttu-id="49724-146">Slechts één organisatie kan een apparaat beheren.</span><span class="sxs-lookup"><span data-stu-id="49724-146">Only one organization can manage a device.</span></span> <span data-ttu-id="49724-147">Als u gasten en externe gebruikers niet uitsluit van beleid waarvoor apparaat compliance is vereist, worden deze gebruikers geblokkeerd door dit beleid.</span><span class="sxs-lookup"><span data-stu-id="49724-147">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="49724-148">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="49724-148">Next step</span></span>

![Stap 4: Beleid voor Microsoft 365-cloud-apps](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="49724-150">Beleidsregels voor voorwaardelijke toegang configureren voor:</span><span class="sxs-lookup"><span data-stu-id="49724-150">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="49724-151">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="49724-151">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="49724-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="49724-152">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="49724-153">SharePoint</span><span class="sxs-lookup"><span data-stu-id="49724-153">SharePoint</span></span>](sharepoint-file-access-policies.md)
