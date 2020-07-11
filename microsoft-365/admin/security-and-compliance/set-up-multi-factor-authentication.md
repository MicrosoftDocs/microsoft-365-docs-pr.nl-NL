---
title: Meervoudige verificatie instellen voor gebruikers
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
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
ms.openlocfilehash: 56ca51e77b2ba4fa370a2814a7be9df1393c29dc
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083536"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="572c1-103">Meervoudige verificatie instellen</span><span class="sxs-lookup"><span data-stu-id="572c1-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="572c1-104">Gezien uw ervaring met [meervoudige verificatie (MFA) en de bijbehorende ondersteuning in Microsoft 365](multi-factor-authentication-microsoft-365.md), is het tijd om dit in te stellen en te implementeren in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="572c1-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="572c1-105">Controleer voordat u begint of een van de volgende situaties op u van toepassing is en voer indien nodig de bijbehorende actie uit:</span><span class="sxs-lookup"><span data-stu-id="572c1-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="572c1-106">Als u Office 2013-clients op Windows-apparaten hebt, [moet u Moderne verificatie](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication) inschakelen.</span><span class="sxs-lookup"><span data-stu-id="572c1-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="572c1-107">Als u adreslijstservices van derden van Active Directory Federation Services (AD FS) hebt, moet u de Azure MFA-server instellen.</span><span class="sxs-lookup"><span data-stu-id="572c1-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="572c1-108">Raadpleeg [geavanceerde scenario's met Azure Multi-Factor Authentication en VPN-oplossingen van derden](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="572c1-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

<span data-ttu-id="572c1-109">Alle andere gebruikers wordt gevraagd om indien nodig aanvullende verificatie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="572c1-109">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="572c1-110">Voor meer informatie gaat u naar [tweeledige verificatiemethode en -instellingen](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).</span><span class="sxs-lookup"><span data-stu-id="572c1-110">For more information, please visit [Two-factor verification method and settings](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="572c1-111">Stap 1: bepaal hoe uw gebruikers MFA moeten gebruiken</span><span class="sxs-lookup"><span data-stu-id="572c1-111">Step 1: Decide on the method of requiring your users to use MFA</span></span>

> [!NOTE]
> <span data-ttu-id="572c1-112">U moet een algemeen beheerder zijn om MFA in te stellen of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="572c1-112">You must be a global admin to set up or modify MFA.</span></span> <span data-ttu-id="572c1-113">Er zijn drie manieren om uw gebruikers MFA te laten gebruiken voor aanmelding. Zie [MFA-ondersteuning in Microsoft 365](multi-factor-authentication-microsoft-365.md) voor meer details hierover.</span><span class="sxs-lookup"><span data-stu-id="572c1-113">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="572c1-114">Standaardinstellingen voor beveiliging (aanbevolen voor kleine bedrijven)</span><span class="sxs-lookup"><span data-stu-id="572c1-114">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="572c1-115">Als u na 21 oktober 2019 uw abonnement of proefabonnement hebt afgesloten en u wordt onverwacht gevraagd om aanvullende verificatie met MFA, zijn de [standaardinstellingen voor beveiliging](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatisch ingeschakeld voor uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="572c1-115">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="572c1-116">De standaardinstellingen voor beveiliging zijn automatisch ingeschakeld voor elk nieuw abonnement op Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="572c1-116">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="572c1-117">Dit betekent dat elke gebruiker MFA moet instellen en de Microsoft Authenticator-app op zijn mobiele apparaat moet installeren.</span><span class="sxs-lookup"><span data-stu-id="572c1-117">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="572c1-118">Alle gebruikers moeten de Microsoft Authenticator-app als extra verificatiemethode gebruiken en de oude methode wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="572c1-118">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="572c1-119">Beleid voor voorwaardelijke toegang (aanbevolen voor bedrijven)</span><span class="sxs-lookup"><span data-stu-id="572c1-119">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="572c1-120">Gebruikers kiezen de aanvullende verificatiemethode tijdens de MFA-registratie.</span><span class="sxs-lookup"><span data-stu-id="572c1-120">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="572c1-121">Account per gebruiker (niet aanbevolen)</span><span class="sxs-lookup"><span data-stu-id="572c1-121">Per-user account (not recommended)</span></span>

  <span data-ttu-id="572c1-122">Gebruikers kiezen de aanvullende verificatiemethode tijdens de MFA-registratie.</span><span class="sxs-lookup"><span data-stu-id="572c1-122">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="572c1-123">Stap 2.</span><span class="sxs-lookup"><span data-stu-id="572c1-123">Step 2.</span></span> <span data-ttu-id="572c1-124">MFA testen met testfasedeelnemers </span><span class="sxs-lookup"><span data-stu-id="572c1-124">Test MFA on your pilot users</span></span>

<span data-ttu-id="572c1-125">Als u een beleid voor voorwaardelijke toegang hanteert of MFA per gebruiker (niet aanbevolen), selecteert u testfasedeelnemers in uw bedrijf of organisatie om MFA-registratie en -aanmelding te testen. Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="572c1-125">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="572c1-126">Voor beleid voor voorwaardelijke toegang maakt u een testfasedeelnemersgroep aan en een beleid dat MFA vereist voor de leden van de groep en voor alle-apps.</span><span class="sxs-lookup"><span data-stu-id="572c1-126">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="572c1-127">Vervolgens voegt u de accounts van de testfasedeelnemers toe aan de groep.</span><span class="sxs-lookup"><span data-stu-id="572c1-127">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="572c1-128">Voor MFA per gebruiker schakelt u MFA voor de gebruikersaccounts van de testfasedeelnemers een voor een in.</span><span class="sxs-lookup"><span data-stu-id="572c1-128">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="572c1-129">Werk samen met de testfasedeelnemers om vragen en problemen op te lossen om een soepele implementatie in uw organisatie voor te bereiden.</span><span class="sxs-lookup"><span data-stu-id="572c1-129">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="572c1-130">Stap 3.</span><span class="sxs-lookup"><span data-stu-id="572c1-130">Step 3.</span></span> <span data-ttu-id="572c1-131">Laat uw organisatie weten dat MFA eraan komt</span><span class="sxs-lookup"><span data-stu-id="572c1-131">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="572c1-132">Gebruik e-mailmeldingen, posters op de gang, teamvergaderingen of formele training om te zorgen dat uw medewerkers begrijpen:</span><span class="sxs-lookup"><span data-stu-id="572c1-132">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="572c1-133">waarom MFA vereist is voor aanmelding</span><span class="sxs-lookup"><span data-stu-id="572c1-133">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="572c1-134">hoe ze zich kunnen registreren voor de aanvullende verificatiemethode</span><span class="sxs-lookup"><span data-stu-id="572c1-134">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="572c1-135">hoe ze zich moeten aanmelden na registratie</span><span class="sxs-lookup"><span data-stu-id="572c1-135">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="572c1-136">hoe ze de aanvullende verificatiemethode kunnen wijzigen</span><span class="sxs-lookup"><span data-stu-id="572c1-136">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="572c1-137">hoe ze moeten omgaan met situaties als een nieuwe smartphone</span><span class="sxs-lookup"><span data-stu-id="572c1-137">How to deal with situations like a new smart phone</span></span>](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="572c1-138">Het belangrijkste is dat uw medewerkers weten ***vanaf wanneer MFA vereist is***, zodat het niet onverwachts komt.</span><span class="sxs-lookup"><span data-stu-id="572c1-138">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="572c1-139">Stap 4.</span><span class="sxs-lookup"><span data-stu-id="572c1-139">Step 4.</span></span> <span data-ttu-id="572c1-140">MFA implementeren voor uw organisatie of gebruikers</span><span class="sxs-lookup"><span data-stu-id="572c1-140">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="572c1-141">Implementeer MFA voor de werknemers en niet meer voor de testfasedeelnemers op basis van de gekozen MFA-verificatiemethode.</span><span class="sxs-lookup"><span data-stu-id="572c1-141">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="572c1-142">Standaardinstellingen voor beveiliging</span><span class="sxs-lookup"><span data-stu-id="572c1-142">Security defaults</span></span>

<span data-ttu-id="572c1-143">U kunt standaardinstellingen voor beveiliging in- of uitschakelen vanuit het deelvenster **Eigenschappen** voor Azure Active Directory (Azure AD) in Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="572c1-143">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="572c1-144">Meld u aan bij [Microsoft 365-beheercentrum](https://admin.microsoft.com) met algemeen beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="572c1-144">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="572c1-145">Ga naar de [eigenschappenpagina van Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="572c1-145">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="572c1-146">Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.</span><span class="sxs-lookup"><span data-stu-id="572c1-146">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="572c1-147">Kies **Ja** als u de standaardinstellingen voor beveiliging wilt inschakelen of **Nee** om deze uit te schakelen en kies vervolgens **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="572c1-147">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="572c1-148">Als u [beleid voor voorwaardelijke toegang volgens basislijn](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection) gebruikt, gaat u als volgt te werk om de standaardinstellingen voor beveiliging te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="572c1-148">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="572c1-149">Ga naar de [pagina met beleidsregels voor voorwaardelijke toegang](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="572c1-149">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="572c1-150">Kies elk basislijnbeleid dat **Aan** staat en zet **Beleid inschakelen** **Uit**.</span><span class="sxs-lookup"><span data-stu-id="572c1-150">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="572c1-151">Ga naar de [eigenschappenpagina van Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="572c1-151">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="572c1-152">Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.</span><span class="sxs-lookup"><span data-stu-id="572c1-152">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="572c1-153">Kies **Ja** als u de standaardinstellingen voor beveiliging wilt inschakelen of **Nee** om deze uit te schakelen en kies vervolgens **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="572c1-153">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="572c1-154">Beleidsregels voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="572c1-154">Conditional Access policies</span></span>

<span data-ttu-id="572c1-155">De juiste beleidsregels aanmaken, configureren en inschakelen voor de gebruikersgroep die zich met MFA moet aanmelden.</span><span class="sxs-lookup"><span data-stu-id="572c1-155">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="572c1-156">MFA per gebruiker (niet aanbevolen)</span><span class="sxs-lookup"><span data-stu-id="572c1-156">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="572c1-157">Schakel gebruikersaccounts in voor MFA in overeenstemming met uw implementatie.</span><span class="sxs-lookup"><span data-stu-id="572c1-157">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="572c1-158">Ondersteuning voor uw werknemers</span><span class="sxs-lookup"><span data-stu-id="572c1-158">Supporting your employees</span></span>

<span data-ttu-id="572c1-159">Zorg ervoor dat IT-specialisten, IT-afdeling of helpdesk snel vragen kan beantwoorden en problemen kan oplossen als uw werknemers zich registreren en gaan aanmelden met MFA.</span><span class="sxs-lookup"><span data-stu-id="572c1-159">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="572c1-160">Raadpleeg dit artikel voor [informatie over het oplossen van problemen bij het aanmelden met MFA](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2).</span><span class="sxs-lookup"><span data-stu-id="572c1-160">See this article for [information about troubleshooting MFA sign-ins](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


