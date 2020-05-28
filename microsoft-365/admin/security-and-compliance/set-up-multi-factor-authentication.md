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
localization_priority: Normal
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
description: Meer informatie over het instellen van multi-factor authenticatie voor uw organisatie.
monikerRange: o365-worldwide
ms.openlocfilehash: 2b4ac2b5950d2641254742e03f054f3e4c886833
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399120"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="81dd2-103">Meervoudige verificatie instellen</span><span class="sxs-lookup"><span data-stu-id="81dd2-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="81dd2-104">Op basis van uw kennis van [multi-factor authenticatie (MFA) en de ondersteuning ervan in Microsoft 365,](multi-factor-authentication-microsoft-365.md)is het tijd om het in te stellen en uit te rollen naar uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="81dd2-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="81dd2-105">Bepaal voordat u begint of deze speciale voorwaarden op u van toepassing zijn en onderneem de juiste actie:</span><span class="sxs-lookup"><span data-stu-id="81dd2-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="81dd2-106">Als u Office 2013-clients op Windows-apparaten hebt, [schakelt u Moderne verificatie in.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)</span><span class="sxs-lookup"><span data-stu-id="81dd2-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="81dd2-107">Als u directoryservices van derden hebt met Active Directory Federation Services (AD FS), stelt u de Azure MFA-server in.</span><span class="sxs-lookup"><span data-stu-id="81dd2-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="81dd2-108">Bekijk [geavanceerde scenario's met Azure Multi-Factor Authentication en VPN-oplossingen van derden](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="81dd2-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="81dd2-109">Stap 1: Bepaal de methode om uw gebruikers MFA te verplichten</span><span class="sxs-lookup"><span data-stu-id="81dd2-109">Step 1: Decide on the method of requiring your users to use MFA</span></span>

<span data-ttu-id="81dd2-110">Er zijn drie manieren om uw gebruikers te verplichten MFA te gebruiken voor aanmeldingen. Zie [MFA-ondersteuning in Microsoft 365](multi-factor-authentication-microsoft-365.md) voor de details.</span><span class="sxs-lookup"><span data-stu-id="81dd2-110">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="81dd2-111">Beveiligingsstandaards (aanbevolen voor kleine bedrijven)</span><span class="sxs-lookup"><span data-stu-id="81dd2-111">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="81dd2-112">Als u uw abonnement of proefversie na 21 oktober 2019 hebt gekocht en u onverwacht wordt gevraagd voor MFA, zijn [beveiligingsstandaards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatisch ingeschakeld voor uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="81dd2-112">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="81dd2-113">Bij elk nieuw Microsoft 365-abonnement is automatisch beveiligingsstandaards ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="81dd2-113">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="81dd2-114">Dit betekent dat elke gebruiker MFA moet instellen en de Microsoft Authenticator-app op zijn mobiele apparaat moet installeren.</span><span class="sxs-lookup"><span data-stu-id="81dd2-114">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="81dd2-115">Alle gebruikers moeten de Microsoft Authenticator-app gebruiken omdat hun aanvullende verificatiemethode en verouderde verificatie worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="81dd2-115">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="81dd2-116">Beleid voor voorwaardelijke toegang (aanbevolen voor ondernemingen)</span><span class="sxs-lookup"><span data-stu-id="81dd2-116">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="81dd2-117">Gebruikers kiezen de aanvullende verificatiemethode tijdens mfa-registratie.</span><span class="sxs-lookup"><span data-stu-id="81dd2-117">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="81dd2-118">Account per gebruiker (niet aanbevolen)</span><span class="sxs-lookup"><span data-stu-id="81dd2-118">Per-user account (not recommended)</span></span>

  <span data-ttu-id="81dd2-119">Gebruikers kiezen de aanvullende verificatiemethode tijdens mfa-registratie.</span><span class="sxs-lookup"><span data-stu-id="81dd2-119">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="81dd2-120">Stap 2.</span><span class="sxs-lookup"><span data-stu-id="81dd2-120">Step 2.</span></span> <span data-ttu-id="81dd2-121">MFA testen op uw pilotgebruikers</span><span class="sxs-lookup"><span data-stu-id="81dd2-121">Test MFA on your pilot users</span></span>

<span data-ttu-id="81dd2-122">Als u beleid voor voorwaardelijke toegang of MFA per gebruiker gebruikt (niet aanbevolen), selecteert u pilotgebruikers in uw bedrijf of organisatie om MFA-registratie en aanmeldingen te testen. Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="81dd2-122">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="81dd2-123">Maak voor beleid voor voorwaardelijke toegang een groep pilotgebruikers en een beleid waarvoor MFA vereist is voor de leden van de groep en voor alle apps.</span><span class="sxs-lookup"><span data-stu-id="81dd2-123">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="81dd2-124">Voeg vervolgens de accounts van de pilootgebruiker toe aan de groep.</span><span class="sxs-lookup"><span data-stu-id="81dd2-124">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="81dd2-125">Schakel MFA voor de gebruikersaccounts van uw pilotgebruikers één keer in.</span><span class="sxs-lookup"><span data-stu-id="81dd2-125">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="81dd2-126">Werk samen met uw pilootgebruikers om vragen en problemen aan te pakken om zich voor te bereiden op een soepele uitrol naar uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="81dd2-126">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="81dd2-127">Stap 3.</span><span class="sxs-lookup"><span data-stu-id="81dd2-127">Step 3.</span></span> <span data-ttu-id="81dd2-128">Informeer uw organisatie dat MFA eraan komt</span><span class="sxs-lookup"><span data-stu-id="81dd2-128">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="81dd2-129">Gebruik e-mailmeldingen, gangposters, teamvergaderingen of formele training om ervoor te zorgen dat uw medewerkers het inzicht krijgen:</span><span class="sxs-lookup"><span data-stu-id="81dd2-129">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="81dd2-130">Waarom MFA nodig is voor aanmeldingen</span><span class="sxs-lookup"><span data-stu-id="81dd2-130">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="81dd2-131">Registreren voor hun aanvullende verificatiemethode</span><span class="sxs-lookup"><span data-stu-id="81dd2-131">How to register for their additional verification method</span></span>](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [<span data-ttu-id="81dd2-132">Aanmelden na registratie</span><span class="sxs-lookup"><span data-stu-id="81dd2-132">How to sign-in after registration</span></span>](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="81dd2-133">Hun aanvullende verificatiemethode wijzigen</span><span class="sxs-lookup"><span data-stu-id="81dd2-133">How to change their additional verification method</span></span>](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="81dd2-134">Hoe om te gaan met situaties zoals een nieuwe smartphone</span><span class="sxs-lookup"><span data-stu-id="81dd2-134">How to deal with situations like a new smart phone</span></span>](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="81dd2-135">Het belangrijkste is, zorg ervoor dat uw medewerkers begrijpen ***wanneer de MFA-eis zal worden opgelegd,*** zodat het hen niet verrast.</span><span class="sxs-lookup"><span data-stu-id="81dd2-135">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="81dd2-136">Stap 4.</span><span class="sxs-lookup"><span data-stu-id="81dd2-136">Step 4.</span></span> <span data-ttu-id="81dd2-137">De MFA-vereiste uitrollen naar uw organisatie of gebruikers</span><span class="sxs-lookup"><span data-stu-id="81dd2-137">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="81dd2-138">Op basis van de door u gekozen MFA-vereistenmethode rolt u MFA-verificatie uit naar de werknemers buiten uw pilottesters.</span><span class="sxs-lookup"><span data-stu-id="81dd2-138">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="81dd2-139">Standaardinstellingen voor beveiliging</span><span class="sxs-lookup"><span data-stu-id="81dd2-139">Security defaults</span></span>

<span data-ttu-id="81dd2-140">U schakelt beveiligingsstandaards in of uit vanuit het deelvenster **Eigenschappen** voor Azure Active Directory (Azure AD) in de Azure-portal.</span><span class="sxs-lookup"><span data-stu-id="81dd2-140">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="81dd2-141">Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met algemene beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="81dd2-141">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="81dd2-142">Ga naar de [pagina Azure Active Directory - Eigenschappen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="81dd2-142">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="81dd2-143">Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.</span><span class="sxs-lookup"><span data-stu-id="81dd2-143">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="81dd2-144">Kies **Ja** om beveiligingsstandaards in te schakelen en **Nee** om beveiligingsstandaards uit te schakelen en kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="81dd2-144">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="81dd2-145">Als u het [beleid voor voorwaardelijke basislijnhebt](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)gebruikt, gaat u als u over op het gebruik van beveiligingsstandaardinstellingen.</span><span class="sxs-lookup"><span data-stu-id="81dd2-145">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="81dd2-146">Ga naar de [pagina Voorwaardelijke toegang - Beleid](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="81dd2-146">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="81dd2-147">Kies elk basislijnbeleid dat is **ingeschakeld** en stel **Beleid inschakelen** in **op Uit**.</span><span class="sxs-lookup"><span data-stu-id="81dd2-147">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="81dd2-148">Ga naar de [pagina Azure Active Directory - Eigenschappen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="81dd2-148">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="81dd2-149">Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.</span><span class="sxs-lookup"><span data-stu-id="81dd2-149">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="81dd2-150">Kies **Ja** om beveiligingsstandaards in te schakelen en **Nee** om beveiligingsstandaards uit te schakelen en kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="81dd2-150">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="81dd2-151">Beleid voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="81dd2-151">Conditional Access policies</span></span>

<span data-ttu-id="81dd2-152">Maak, configureer en schakel het juiste beleid in dat de groep gebruikers bevat die MFA nodig heeft voor aanmelding.</span><span class="sxs-lookup"><span data-stu-id="81dd2-152">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="81dd2-153">MFA per gebruiker (niet aanbevolen)</span><span class="sxs-lookup"><span data-stu-id="81dd2-153">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="81dd2-154">Gebruikersaccounts voor MFA inschakelen die overeenkomen met uw implementatie.</span><span class="sxs-lookup"><span data-stu-id="81dd2-154">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="81dd2-155">Uw medewerkers ondersteunen</span><span class="sxs-lookup"><span data-stu-id="81dd2-155">Supporting your employees</span></span>

<span data-ttu-id="81dd2-156">Zorg er tijdens het registreren van uw medewerkers voor dat uw IT-specialisten, IT-afdeling of helpdesk vragen kunnen beantwoorden en problemen snel kunnen oplossen.</span><span class="sxs-lookup"><span data-stu-id="81dd2-156">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="81dd2-157">Zie dit artikel voor [informatie over het oplossen van MFA-aanmeldingen](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2).</span><span class="sxs-lookup"><span data-stu-id="81dd2-157">See this article for [information about troubleshooting MFA sign-ins](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


