---
title: Beleid voor identiteits- en apparaattoegang voor het toestaan van gast- en externe gebruiker B2B-toegang - Microsoft 365 voor bedrijven | Microsoft Docs
description: Beschrijft het aanbevolen beleid voor voorwaardelijke toegang en verwante beleidsregels voor het beschermen van de toegang van gasten en externe gebruikers.
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
ms.openlocfilehash: 9d3a47752efc86c8ced32905bda851b7d8157f82
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057937"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="2aeb1-103">Beleid voor het toestaan van gasttoegang en B2B-externe gebruikerstoegang</span><span class="sxs-lookup"><span data-stu-id="2aeb1-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="2aeb1-104">In dit artikel wordt beschreven hoe u het aanbevolen beleid voor apparaat- en identiteitstoegang aanpast om toegang te verlenen aan gasten en externe gebruikers die een Azure Active Directory-account (Azure AD) Business-to-Business (B2B) hebben.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="2aeb1-105">Deze richtlijnen zijn gebaseerd op [het algemene beleid voor identiteits- en apparaattoegang.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="2aeb1-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="2aeb1-106">Deze aanbevelingen zijn bedoeld om  van toepassing te zijn op de basislijnbeveiligingslaag.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="2aeb1-107">Maar u kunt de aanbevelingen ook aanpassen op basis van uw specifieke behoeften voor **gevoelige** en sterk **gereguleerde** beveiliging.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="2aeb1-108">Als u een pad biedt voor B2B-accounts om te verifiëren met uw Azure AD-tenant, hebben deze accounts geen toegang tot uw hele omgeving.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="2aeb1-109">B2B-gebruikers en hun accounts hebben toegang tot services en resources, zoals bestanden, die met hen worden gedeeld via beleid voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="2aeb1-110">Het algemene beleid bijwerken om gasten en externe gebruikerstoegang toe te staan en te beveiligen</span><span class="sxs-lookup"><span data-stu-id="2aeb1-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="2aeb1-111">In dit diagram ziet u welk beleid moet worden toegevoegd of bijgewerkt tussen het algemene beleid voor identiteits- en apparaattoegang, voor B2B-gast- en externe gebruikerstoegang.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="2aeb1-112">[![Overzicht van beleidsupdates voor het beschermen van gasttoegang](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="2aeb1-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

<span data-ttu-id="2aeb1-113">In de volgende tabel ziet u de beleidsregels die u moet maken en bijwerken.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-113">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="2aeb1-114">De algemene beleidsregels koppelen aan de bijbehorende configuratie-instructies in het artikel Algemene [identiteits-](identity-access-policies.md) en apparaattoegangsbeleid.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-114">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="2aeb1-115">Beveiligingsniveau</span><span class="sxs-lookup"><span data-stu-id="2aeb1-115">Protection level</span></span>|<span data-ttu-id="2aeb1-116">Beleid</span><span class="sxs-lookup"><span data-stu-id="2aeb1-116">Policies</span></span>|<span data-ttu-id="2aeb1-117">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="2aeb1-117">More information</span></span>|
|---|---|---|
|<span data-ttu-id="2aeb1-118">**Basislijn**</span><span class="sxs-lookup"><span data-stu-id="2aeb1-118">**Baseline**</span></span>|[<span data-ttu-id="2aeb1-119">MFA altijd vereisen voor gasten en externe gebruikers</span><span class="sxs-lookup"><span data-stu-id="2aeb1-119">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="2aeb1-120">Maak dit nieuwe beleid en configureer:</span><span class="sxs-lookup"><span data-stu-id="2aeb1-120">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="2aeb1-121">Voor **Opdrachten > Gebruikers en groepen > Opnemen,** kiest u Gebruikers en groepen selecteren **en** selecteert u vervolgens **Alle gast- en externe gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="2aeb1-121">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="2aeb1-122">Voor **Toewijzingen > voorwaarden > Aanmelden**, laat u alle opties uitgeschakeld om altijd meervoudige verificatie (MFA) af te dwingen.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-122">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="2aeb1-123">MFA vereisen wanneer het aanmeldingsrisico gemiddeld *of* *hoog* is</span><span class="sxs-lookup"><span data-stu-id="2aeb1-123">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="2aeb1-124">Wijzig dit beleid om gasten en externe gebruikers uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-124">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="2aeb1-125">Eis conforme pc’s</span><span class="sxs-lookup"><span data-stu-id="2aeb1-125">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="2aeb1-126">Wijzig dit beleid om gasten en externe gebruikers uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-126">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="2aeb1-127">Als u gasten en externe gebruikers wilt opnemen of uitsluiten in beleidsregels voor voorwaardelijke toegang, controleert u alle gast- en externe gebruikers voor Opdrachten > Gebruikers en groepen **> Opnemen of** **Uitsluiten.**</span><span class="sxs-lookup"><span data-stu-id="2aeb1-127">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![schermopname van besturingselementen voor het uitsluiten van gasten en externe gebruikers](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="2aeb1-129">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="2aeb1-129">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="2aeb1-130">Gasten en externe gebruikerstoegang met Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2aeb1-130">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="2aeb1-131">Microsoft Teams definieert de volgende gebruikers:</span><span class="sxs-lookup"><span data-stu-id="2aeb1-131">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="2aeb1-132">**Gasttoegang** maakt gebruik van een Azure AD B2B-account dat kan worden toegevoegd als lid van een team en toegang heeft tot de communicatie en bronnen van het team.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-132">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="2aeb1-133">**Externe toegang** is voor een externe gebruiker die geen B2B-account heeft.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-133">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="2aeb1-134">Externe gebruikerstoegang omvat uitnodigingen, oproepen, chats en vergaderingen, maar omvat geen teamlidmaatschap en toegang tot de resources van het team.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-134">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="2aeb1-135">Zie de vergelijking tussen gasten en externe gebruikerstoegang voor [teams voor meer informatie.](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="2aeb1-135">For more information, see the [comparison between guests and external user access for teams](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="2aeb1-136">Zie Beleidsaanbevelingen voor het beveiligen van [Teams-chats, groepen en bestanden](teams-access-policies.md)voor meer informatie over het beveiligen van identiteits- en apparaattoegangsbeleid voor Teams.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-136">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="2aeb1-137">MFA altijd vereisen voor gast- en externe gebruikers</span><span class="sxs-lookup"><span data-stu-id="2aeb1-137">Require MFA always for guest and external users</span></span>

<span data-ttu-id="2aeb1-138">Dit beleid vraagt gasten zich te registreren voor MFA in uw tenant, ongeacht of ze zijn geregistreerd voor MFA in hun huisten tenant.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-138">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="2aeb1-139">Wanneer u toegang hebt tot resources in uw tenant, moeten gasten en externe gebruikers MFA voor elke aanvraag gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-139">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="2aeb1-140">Gasten en externe gebruikers uitsluiten van risicogebaseerde MFA</span><span class="sxs-lookup"><span data-stu-id="2aeb1-140">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="2aeb1-141">Hoewel organisaties op risico's gebaseerde beleidsregels kunnen afdwingen voor B2B-gebruikers die Azure AD Identity Protection gebruiken, gelden er beperkingen voor de implementatie van Azure AD Identity Protection voor B2B-samenwerkingsgebruikers in een resourcemap vanwege hun identiteit die in de thuismap staat.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-141">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="2aeb1-142">Vanwege deze beperkingen raadt Microsoft u aan gasten uit te sluiten van MFA-beleid op basis van risico's en deze gebruikers altijd MFA te laten gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-142">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="2aeb1-143">Zie Beperkingen van identiteitsbeveiliging [voor B2B-samenwerkingsgebruikers](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-143">For more information, see [Limitations of Identity Protection for B2B collaboration users](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="2aeb1-144">Gasten en externe gebruikers uitsluiten van apparaatbeheer</span><span class="sxs-lookup"><span data-stu-id="2aeb1-144">Excluding guests and external users from device management</span></span>

<span data-ttu-id="2aeb1-145">Slechts één organisatie kan een apparaat beheren.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-145">Only one organization can manage a device.</span></span> <span data-ttu-id="2aeb1-146">Als u gasten en externe gebruikers niet uitsluit van beleidsregels waarvoor apparaat compliance vereist is, worden deze gebruikers geblokkeerd door dit beleid.</span><span class="sxs-lookup"><span data-stu-id="2aeb1-146">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="2aeb1-147">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="2aeb1-147">Next step</span></span>

![Stap 4: Beleidsregels voor Cloud-apps van Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="2aeb1-149">Beleid voor voorwaardelijke toegang configureren voor:</span><span class="sxs-lookup"><span data-stu-id="2aeb1-149">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="2aeb1-150">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2aeb1-150">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="2aeb1-151">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2aeb1-151">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="2aeb1-152">SharePoint</span><span class="sxs-lookup"><span data-stu-id="2aeb1-152">SharePoint</span></span>](sharepoint-file-access-policies.md)