---
title: Meervoudige verificatie instellen voor gebruikers
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Instructies voor het instellen van meervoudige verificatie voor uw organisatie.
monikerRange: o365-worldwide
ms.openlocfilehash: db858cbd4242a096261942fd12b911ecff43f71f
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558208"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="d92be-103">Meervoudige verificatie instellen</span><span class="sxs-lookup"><span data-stu-id="d92be-103">Set up multi-factor authentication</span></span>

<span data-ttu-id="d92be-104">Gezien uw ervaring met [meervoudige verificatie (MFA) en de bijbehorende ondersteuning in Microsoft 365](multi-factor-authentication-microsoft-365.md), is het tijd om dit in te stellen en te implementeren in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d92be-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it's time to set it up and roll it out to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d92be-105">Als u na 21 oktober 2019 uw abonnement of proefabonnement hebt afgesloten en u wordt gevraagd om aanvullende verificatie met MFA als u zich aanmeldt, zijn de [standaardinstellingen voor beveiliging](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatisch ingeschakeld voor uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="d92be-105">If you purchased your subscription or trial after October 21, 2019, and you're prompted for MFA when you sign in, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d92be-106">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="d92be-106">Before you begin</span></span>

- <span data-ttu-id="d92be-107">U moet een algemeen beheerder zijn om MFA te beheren.</span><span class="sxs-lookup"><span data-stu-id="d92be-107">You must be a Global admin to manage MFA.</span></span> <span data-ttu-id="d92be-108">Raadpleeg [Over beheerdersrollen](../add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d92be-108">For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="d92be-109">Als verouderde per persoon-MFA is ingeschakeld, [schakel dit dan uit](#turn-off-legacy-per-user-mfa).</span><span class="sxs-lookup"><span data-stu-id="d92be-109">If you have legacy per-user MFA turned on, [Turn off legacy per-user MFA](#turn-off-legacy-per-user-mfa).</span></span>
- <span data-ttu-id="d92be-110">Als u Office 2013-clients op Windows-apparaten hebt, moet u [Moderne verificatie voor Office 2013-clients inschakelen](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="d92be-110">If you have Office 2013 clients on Windows devices, [turn on Modern Authentication for Office 2013 clients](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>
- <span data-ttu-id="d92be-111">Geavanceerd: als u adreslijstservices van derden met Active Directory Federation Services (AD FS) hebt, moet u de Azure MFA-server instellen.</span><span class="sxs-lookup"><span data-stu-id="d92be-111">Advanced: If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="d92be-112">Raadpleeg [geavanceerde scenario's met Azure AD Multi-Factor Authentication en VPN-oplossingen van derden](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d92be-112">See [advanced scenarios with Azure AD Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="turn-security-defaults-on-or-off"></a><span data-ttu-id="d92be-113">Standaardinstellingen voor beveiliging in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="d92be-113">Turn Security defaults on or off</span></span>

<span data-ttu-id="d92be-114">Voor de meeste organisaties bieden standaardinstellingen voor beveiliging een goed niveau aanvullende aanmeldingsbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="d92be-114">For most organizations, Security defaults offer a good level of additional sign-in security.</span></span> <span data-ttu-id="d92be-115">Raadpleeg [Wat zijn standaardinstellingen voor beveiliging?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="d92be-115">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="d92be-116">Als uw abonnement nieuw is, zijn de standaardinstellingen voor beveiliging mogelijk al automatisch ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d92be-116">If your subscription is new, Security defaults might already be turned on for you automatically.</span></span>

<span data-ttu-id="d92be-117">U kunt standaardinstellingen voor beveiliging in- of uitschakelen vanuit het deelvenster **Eigenschappen** voor Azure Active Directory (Azure AD) in Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="d92be-117">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1. <span data-ttu-id="d92be-118">Meld u aan bij [Microsoft 365-beheercentrum](https://admin.microsoft.com) met algemeen beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="d92be-118">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2. <span data-ttu-id="d92be-119">Kies in het linker navigatievenster **Alle weergeven** en kies onder **Beheercentra** **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="d92be-119">In the left nav choose **Show All** and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="d92be-120">Kies in het **Azure Active Directory-beheercentrum** **Azure Active Directory** \> **-eigenschappen**.</span><span class="sxs-lookup"><span data-stu-id="d92be-120">In the **Azure Active Directory admin center** choose **Azure Active Directory** \> **Properties**.</span></span>
4. <span data-ttu-id="d92be-121">Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.</span><span class="sxs-lookup"><span data-stu-id="d92be-121">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="d92be-122">Kies **Ja** als u de standaardinstellingen voor beveiliging wilt inschakelen of **Nee** om deze uit te schakelen en kies vervolgens **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d92be-122">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="d92be-123">Als u [Beleid voor voorwaardelijke toegang volgens basislijn](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection) gebruikt, zal u gevraagd worden dit uit te schakelen alvorens standaardinstellingen voor beveiliging te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d92be-123">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), you will be prompted to turn them off before you move to using security defaults.</span></span>

1. <span data-ttu-id="d92be-124">Ga naar de [pagina met beleidsregels voor voorwaardelijke toegang](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="d92be-124">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="d92be-125">Kies elk basislijnbeleid dat **Aan** staat en zet **Beleid inschakelen** **Uit**.</span><span class="sxs-lookup"><span data-stu-id="d92be-125">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="d92be-126">Ga naar de [eigenschappenpagina van Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="d92be-126">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="d92be-127">Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.</span><span class="sxs-lookup"><span data-stu-id="d92be-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="d92be-128">Kies **Ja** als u de standaardinstellingen voor beveiliging wilt inschakelen of **Nee** om deze uit te schakelen en kies vervolgens **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d92be-128">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="use-conditional-access-policies"></a><span data-ttu-id="d92be-129">Gebruik Beleid voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="d92be-129">Use Conditional Access policies</span></span>

<span data-ttu-id="d92be-130">Als uw organisatie gedetailleerdere beveiligingsbehoeften voor aanmelding heeft, kunt u met Beleid voor voorwaardelijke toegang meer controle krijgen.</span><span class="sxs-lookup"><span data-stu-id="d92be-130">If your organization has more granular sign-in security needs, Conditional Access policies can offer you more control.</span></span> <span data-ttu-id="d92be-131">Met voorwaardelijke toegang kunt u regels maken en definiëren die reageren op aanmeldingsgebeurtenissen en aanvullende acties verzoeken voordat een gebruiker toegang krijgt tot een toepassing of service.</span><span class="sxs-lookup"><span data-stu-id="d92be-131">Conditional Access lets you create and define policies that react to sign in events and request additional actions before a user is granted access to an application or service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d92be-132">Schakel zowel per gebruiker-MFA als Standaardinstellingen voor beveiliging uit voordat u Beleid voor voorwaardelijke toegang inschakelt.</span><span class="sxs-lookup"><span data-stu-id="d92be-132">Turn off both per-user MFA and Security defaults before you enable Conditional Access policies.</span></span>

<span data-ttu-id="d92be-133">Voorwaardelijke toegang is beschikbaar voor klanten die Azure AD Premium P1 hebben aangeschaft of licenties hebben waarin dit is inbegrepen, zoals Microsoft 365 Business Premium en Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="d92be-133">Conditional Access is available for customers who have purchased Azure AD Premium P1, or licenses that include this, such as Microsoft 365 Business Premium, and Microsoft 365 E3.</span></span> <span data-ttu-id="d92be-134">Raadpleeg [Een regel voor voorwaardelijke toegang maken](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d92be-134">For more information, see [create a Conditional Access policy](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span></span>

<span data-ttu-id="d92be-135">Op risico's gebaseerde voorwaardelijke toegang is beschikbaar met de Azure AD Premium P2-licentie of licenties waarin dit is inbegrepen, zoals Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="d92be-135">Risk-based conditional access is available through Azure AD Premium P2 license, or licenses that include this, such as Microsoft 365 E5.</span></span> <span data-ttu-id="d92be-136">Raadpleeg [Op risico's gebaseerde voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d92be-136">For more information, see [risk-based Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span></span>

<span data-ttu-id="d92be-137">Voor meer informatie over de Azure AD P1 en P2, zie [Prijzen Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="d92be-137">For more information about the Azure AD P1 and P2, see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

### <a name="turn-on-modern-authentication-for-your-organization"></a><span data-ttu-id="d92be-138">Moderne verificatie voor uw organisatie inschakelen</span><span class="sxs-lookup"><span data-stu-id="d92be-138">Turn on Modern authentication for your organization</span></span>

<span data-ttu-id="d92be-139">Voor de meeste abonnementen wordt moderne verificatie automatisch ingeschakeld, maar als u uw abonnement lang geleden hebt aangeschaft, is dat mogelijk niet het geval.</span><span class="sxs-lookup"><span data-stu-id="d92be-139">For most subscriptions modern authentication is automatically turned on, but if you purchased your subscription a long time ago, it might not be.</span></span> <span data-ttu-id="d92be-140">Dit moet worden ingeschakeld voordat MFA correct werkt met Office-apps.</span><span class="sxs-lookup"><span data-stu-id="d92be-140">This has to be turned on before MFA works appropriately with Office apps.</span></span>

1. <span data-ttu-id="d92be-141">In het Microsoft 365-beheercentrum kiest u in het linker navigatievenster **Instellingen** \> **Org-instellingen**.</span><span class="sxs-lookup"><span data-stu-id="d92be-141">In the Microsoft 365 admin center, in the left nav choose **Settings** \> **Org settings**.</span></span>
1. <span data-ttu-id="d92be-142">Kies op het tabblad **Services** **Moderne verificatie** en zorg dat in het deelvenster **Moderne verificatie** de optie **Moderne verificatie inschakelen** is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="d92be-142">Under **Services** tab, choose **Modern authentication**, and in the **Modern authentication** pane, make sure **Enable Modern authentication** is selected.</span></span> <span data-ttu-id="d92be-143">Kies **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d92be-143">Choose **Save changes**.</span></span>

### <a name="turn-off-legacy-per-user-mfa"></a><span data-ttu-id="d92be-144">Verouderde per gebruiker-MFA uitschakelen</span><span class="sxs-lookup"><span data-stu-id="d92be-144">Turn off legacy per-user MFA</span></span>

<span data-ttu-id="d92be-145">Als u eerder per gebruiker-MFA hebt ingeschakeld, moet u dit uitschakelen voordat u de standaardinstellingen voor beveiliging inschakelt.</span><span class="sxs-lookup"><span data-stu-id="d92be-145">If you have previously turned on per-user MFA, you must turn it off before enabling Security defaults.</span></span>

1. <span data-ttu-id="d92be-146">In het Microsoft 365-beheercentrum kiest u in het linker navigatievenster **Gebruikers** \> **Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="d92be-146">In the Microsoft 365 admin center, in the left nav choose **Users** \> **Active users**.</span></span>
1. <span data-ttu-id="d92be-147">Kies **Meervoudige verificatie** op de pagina **Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="d92be-147">On the **Active users** page, choose **Multi-factor authentication**.</span></span>
1. <span data-ttu-id="d92be-148">Selecteer elke gebruiker op de pagina Meervoudige verificatie en stel hun meervoudige verificatiestatus in op **Uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="d92be-148">On the multi-factor authentication page, select each user and set their Multi-Factor auth status to **Disabled**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d92be-149">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="d92be-149">Next steps</span></span>

- [<span data-ttu-id="d92be-150">hoe ze zich kunnen registreren voor de aanvullende verificatiemethode</span><span class="sxs-lookup"><span data-stu-id="d92be-150">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="d92be-151">Wat is meervoudige verificatie</span><span class="sxs-lookup"><span data-stu-id="d92be-151">What is: Multifactor Authentication</span></span>](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [<span data-ttu-id="d92be-152">hoe ze zich moeten aanmelden na registratie</span><span class="sxs-lookup"><span data-stu-id="d92be-152">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="d92be-153">hoe ze de aanvullende verificatiemethode kunnen wijzigen</span><span class="sxs-lookup"><span data-stu-id="d92be-153">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
