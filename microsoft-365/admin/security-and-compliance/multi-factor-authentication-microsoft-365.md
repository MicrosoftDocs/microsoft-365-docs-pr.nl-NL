---
title: Meervoudige verificatie voor Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over multi-factor authenticatie in Microsoft 365.
ms.openlocfilehash: 128296b7dbc37ba5ebffb25a87bce589f8e5a904
ms.sourcegitcommit: 185d62f41f6b173894ba6e3e87b11b2b5d02db58
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/21/2020
ms.locfileid: "44340831"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="d25cb-103">Meervoudige verificatie voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d25cb-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="d25cb-104">Wachtwoorden zijn de meest voorkomende methode om een aanmelding bij een computer of online service te verifiëren, maar ze zijn ook het meest kwetsbaar.</span><span class="sxs-lookup"><span data-stu-id="d25cb-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="d25cb-105">Mensen kunnen eenvoudige wachtwoorden kiezen en dezelfde wachtwoorden gebruiken voor meerdere aanmeldingen op verschillende computers en services.</span><span class="sxs-lookup"><span data-stu-id="d25cb-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="d25cb-106">Als u een extra beveiligingsniveau wilt bieden voor aanmeldingen, moet u multi-factor authenticatie (MFA) gebruiken, waarbij zowel een wachtwoord wordt gebruikt, dat sterk moet zijn, als een aanvullende verificatiemethode op basis van:</span><span class="sxs-lookup"><span data-stu-id="d25cb-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="d25cb-107">Iets wat je bij je hebt dat niet gemakkelijk gedupliceerd is, zoals een smartphone.</span><span class="sxs-lookup"><span data-stu-id="d25cb-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="d25cb-108">Iets wat je uniek en biologisch hebt, zoals je vingerafdrukken, gezicht of ander biometrisch attribuut.</span><span class="sxs-lookup"><span data-stu-id="d25cb-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="d25cb-109">De aanvullende verificatiemethode wordt pas gebruikt nadat het wachtwoord van de gebruiker is geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="d25cb-109">The additional verification method is not employed until after the user’s password has been verified.</span></span> <span data-ttu-id="d25cb-110">Met MFA heeft de aanvaller, zelfs als een sterk gebruikerswachtwoord is gecompromitteerd, niet uw smartphone of uw vingerafdruk om de aanmelding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="d25cb-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="d25cb-111">MFA-ondersteuning in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d25cb-111">MFA support in Microsoft 365</span></span>
<span data-ttu-id="d25cb-112">Standaard ondersteunen zowel Microsoft 365 als Office 365 MFA voor gebruikersaccounts met behulp van:</span><span class="sxs-lookup"><span data-stu-id="d25cb-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="d25cb-113">Een sms-bericht dat naar een telefoon wordt verzonden waarbij de gebruiker een verificatiecode moet typen.</span><span class="sxs-lookup"><span data-stu-id="d25cb-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="d25cb-114">Een telefoontje.</span><span class="sxs-lookup"><span data-stu-id="d25cb-114">A phone call.</span></span>
- <span data-ttu-id="d25cb-115">De Microsoft Authenticator smart phone app.</span><span class="sxs-lookup"><span data-stu-id="d25cb-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="d25cb-116">In beide gevallen gebruikt de MFA-aanmelding de methode 'iets wat u bij u hebt dat niet gemakkelijk wordt gedupliceerd' voor de extra verificatie.</span><span class="sxs-lookup"><span data-stu-id="d25cb-116">In both cases, the MFA sign-in is using the “something you have with you that is not easily duplicated” method for the additional verification.</span></span>
<span data-ttu-id="d25cb-117">Er zijn meerdere manieren waarop u MFA voor Microsoft 365 en Office 365 inschakelen:</span><span class="sxs-lookup"><span data-stu-id="d25cb-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="d25cb-118">Met beveiligingsstandaards</span><span class="sxs-lookup"><span data-stu-id="d25cb-118">With security defaults</span></span>
- <span data-ttu-id="d25cb-119">Met beleid voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="d25cb-119">With Conditional Access policies</span></span>
- <span data-ttu-id="d25cb-120">Voor elk individueel gebruikersaccount (niet aanbevolen)</span><span class="sxs-lookup"><span data-stu-id="d25cb-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="d25cb-121">Deze manieren zijn gebaseerd op uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="d25cb-121">These ways are based on your Microsoft 365 plan.</span></span>
    
|<span data-ttu-id="d25cb-122">Abonnement</span><span class="sxs-lookup"><span data-stu-id="d25cb-122">Plan</span></span>  |<span data-ttu-id="d25cb-123">Aanbeveling</span><span class="sxs-lookup"><span data-stu-id="d25cb-123">Recommendation</span></span>  | <span data-ttu-id="d25cb-124">Type klant</span><span class="sxs-lookup"><span data-stu-id="d25cb-124">Type of customer</span></span> |
|---------|---------|----------|
| <span data-ttu-id="d25cb-125">Alle Microsoft 365-abonnementen</span><span class="sxs-lookup"><span data-stu-id="d25cb-125">All Microsoft 365 plans</span></span> | <span data-ttu-id="d25cb-126">Gebruik beveiligingsstandaardinstellingen waarvoor MFA vereist is voor alle gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="d25cb-126">Use security defaults, which require MFA for all user accounts.</span></span> <br> <span data-ttu-id="d25cb-127">U MFA ook per gebruikersaccount vereisen, maar dit wordt niet aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="d25cb-127">You can also require MFA on a per-user account basis, but this is not recommended.</span></span> | <span data-ttu-id="d25cb-128">Kleine bedrijven</span><span class="sxs-lookup"><span data-stu-id="d25cb-128">Small business</span></span> |
| <span data-ttu-id="d25cb-129">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="d25cb-129">Microsoft 365 Business Premium</span></span> <br><br> <span data-ttu-id="d25cb-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="d25cb-130">Microsoft 365 E3</span></span> <br><br> <span data-ttu-id="d25cb-131">Azure Active Directory (Azure AD) Premium P1-licenties</span><span class="sxs-lookup"><span data-stu-id="d25cb-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span> | <span data-ttu-id="d25cb-132">Gebruik beleid voor voorwaardelijke toegang om MFA voor gebruikersaccounts te vereisen op basis van groepslidmaatschap, apps of andere criteria.</span><span class="sxs-lookup"><span data-stu-id="d25cb-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span> | <span data-ttu-id="d25cb-133">Kleine bedrijven naar onderneming</span><span class="sxs-lookup"><span data-stu-id="d25cb-133">Small business to enterprise</span></span> |
| <span data-ttu-id="d25cb-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="d25cb-134">Microsoft 365 E5</span></span> <br><br> <span data-ttu-id="d25cb-135">Azure AD Premium P2-licenties</span><span class="sxs-lookup"><span data-stu-id="d25cb-135">Azure AD Premium P2 licenses</span></span> | <span data-ttu-id="d25cb-136">Gebruik Azure AD-identiteitsbeveiliging om MFA te vereisen op basis van aanmeldingsrisicocriteria.</span><span class="sxs-lookup"><span data-stu-id="d25cb-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span> |  <span data-ttu-id="d25cb-137">Enterprise</span><span class="sxs-lookup"><span data-stu-id="d25cb-137">Enterprise</span></span> |
||||

### <a name="security-defaults"></a><span data-ttu-id="d25cb-138">Standaardinstellingen voor beveiliging</span><span class="sxs-lookup"><span data-stu-id="d25cb-138">Security defaults</span></span>

<span data-ttu-id="d25cb-139">De standaardinstellingen voor beveiliging zijn een nieuwe functie voor betaalde Microsoft 365- en Office 365-abonnementen en proefabonnementen van Microsoft 365 en Office 365 die zijn gemaakt na 21 oktober 2019.</span><span class="sxs-lookup"><span data-stu-id="d25cb-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="d25cb-140">Deze abonnementen hebben beveiligingsstandaardinstellingen ingeschakeld, die:</span><span class="sxs-lookup"><span data-stu-id="d25cb-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="d25cb-141">Vereist dat al uw gebruikers MFA gebruiken met de Microsoft Authenticator-app.</span><span class="sxs-lookup"><span data-stu-id="d25cb-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="d25cb-142">Blokkeert verouderde verificatie.</span><span class="sxs-lookup"><span data-stu-id="d25cb-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="d25cb-143">Gebruikers hebben 14 dagen de tijd om zich te registreren voor MFA met de Microsoft Authenticator-app vanaf hun smartphone. Deze periode gaat in bij de eerste aanmelding nadat de standaardinstellingen voor beveiliging zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d25cb-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="d25cb-144">Na 14 dagen kunnen gebruikers zich alleen aanmelden als de MFA-registratie is voltooid.</span><span class="sxs-lookup"><span data-stu-id="d25cb-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="d25cb-145">De standaardinstellingen voor beveiliging bieden organisaties een basisbeveiligingsniveau voor gebruikersaanmeldingen dat standaard is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d25cb-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="d25cb-146">U beveiligingsstandaardinstellingen uitschakelen ten gunste van MFA met beleid voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="d25cb-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="d25cb-147">U schakelt beveiligingsstandaards in of uit vanuit het deelvenster **Eigenschappen** voor Azure AD in de Azure-portal.</span><span class="sxs-lookup"><span data-stu-id="d25cb-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="d25cb-148">U beveiligingsstandaardinstellingen gebruiken bij elk Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="d25cb-148">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="d25cb-149">Zie dit [overzicht van gevoeligheidslabels](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d25cb-149">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> 

### <a name="conditional-access-policies"></a><span data-ttu-id="d25cb-150">Beleid voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="d25cb-150">Conditional Access policies</span></span>

<span data-ttu-id="d25cb-151">Beleidsregels voor voorwaardelijke toegang zijn regels waarmee wordt aangegeven wanneer aanmeldingen worden beoordeeld en toegestaan.</span><span class="sxs-lookup"><span data-stu-id="d25cb-151">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="d25cb-152">U kunt bijvoorbeeld een toegangsbeleid met de volgende voorwaarden maken:</span><span class="sxs-lookup"><span data-stu-id="d25cb-152">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="d25cb-153">Als de naam van het gebruikersaccount lid is van een groep gebruikers die is toegewezen aan een Exchange-, gebruikers-, wachtwoord-, beveiligings-, SharePoint- of globale beheerdersrol, wordt MFA vereist om toegang te verlenen.</span><span class="sxs-lookup"><span data-stu-id="d25cb-153">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="d25cb-154">Met dit beleid kunt u MFA op basis van groepslidmaatschap vereisen in plaats van dat u afzonderlijke gebruikersaccounts voor MFA gaat configureren wanneer deze worden toegewezen (of als de toewijzing ongedaan wordt gemaakt) vanuit deze beheerdersrollen.</span><span class="sxs-lookup"><span data-stu-id="d25cb-154">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="d25cb-155">U ook beleid voor voorwaardelijke toegang gebruiken voor meer geavanceerde mogelijkheden, zoals het vereisen van MFA voor specifieke apps of dat de aanmelding wordt gedaan vanaf een compatibel apparaat, zoals uw laptop met Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d25cb-155">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="d25cb-156">U configureert beleid voor voorwaardelijke toegang vanuit het **beveiligingsdeelvenster** voor Azure AD in de Azure-portal.</span><span class="sxs-lookup"><span data-stu-id="d25cb-156">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="d25cb-157">U beleid voor voorwaardelijke toegang gebruiken met:</span><span class="sxs-lookup"><span data-stu-id="d25cb-157">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="d25cb-158">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="d25cb-158">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="d25cb-159">Microsoft 365 E3 en E5</span><span class="sxs-lookup"><span data-stu-id="d25cb-159">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="d25cb-160">Azure AD Premium P1- en Azure AD Premium P2-licenties</span><span class="sxs-lookup"><span data-stu-id="d25cb-160">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span> 

<span data-ttu-id="d25cb-161">Voor kleine bedrijven met Microsoft 365 Business Premium u eenvoudig beleid voor voorwaardelijke toegang gebruiken met de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="d25cb-161">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="d25cb-162">Maak een groep met de gebruikersaccounts waarvoor MFA vereist is.</span><span class="sxs-lookup"><span data-stu-id="d25cb-162">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="d25cb-163">Schakel het MFA vereisen in voor het beleid **voor globale beheerders.**</span><span class="sxs-lookup"><span data-stu-id="d25cb-163">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="d25cb-164">Maak een op groepen gebaseerd beleid voor voorwaardelijke toegang met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="d25cb-164">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="d25cb-165">Toewijzingen > gebruikers en groepen: de naam van uw groep in stap 1 hierboven.</span><span class="sxs-lookup"><span data-stu-id="d25cb-165">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="d25cb-166">Opdrachten > Cloud-apps of -acties: alle cloud-apps.</span><span class="sxs-lookup"><span data-stu-id="d25cb-166">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="d25cb-167">Toegangsbesturingselementen > Grant > Grant-toegang > Vereisen meervoudige verificatie.</span><span class="sxs-lookup"><span data-stu-id="d25cb-167">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="d25cb-168">Schakel het beleid in.</span><span class="sxs-lookup"><span data-stu-id="d25cb-168">Enable the policy.</span></span>
5. <span data-ttu-id="d25cb-169">Voeg een gebruikersaccount toe aan de groep die is gemaakt in stap 1 hierboven en test.</span><span class="sxs-lookup"><span data-stu-id="d25cb-169">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="d25cb-170">Als u MFA wilt vereisen voor extra gebruikersaccounts, voegt u deze toe aan de groep die is gemaakt in stap 1.</span><span class="sxs-lookup"><span data-stu-id="d25cb-170">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="d25cb-171">Met dit beleid voor voorwaardelijke toegang u de MFA-vereiste in uw eigen tempo naar uw gebruikers uitrollen.</span><span class="sxs-lookup"><span data-stu-id="d25cb-171">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="d25cb-172">Ondernemingen moeten [common conditional access-beleid](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) gebruiken om het volgende beleid te configureren:</span><span class="sxs-lookup"><span data-stu-id="d25cb-172">Enterprises should use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="d25cb-173">MFA vereisen voor beheerders</span><span class="sxs-lookup"><span data-stu-id="d25cb-173">Require MFA for administrators</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="d25cb-174">MFA vereisen voor alle gebruikers</span><span class="sxs-lookup"><span data-stu-id="d25cb-174">Require MFA for all users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="d25cb-175">Verouderde verificatie blokkeren</span><span class="sxs-lookup"><span data-stu-id="d25cb-175">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="d25cb-176">Zie dit [overzicht van voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d25cb-176">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="d25cb-177">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="d25cb-177">Azure AD Identity Protection</span></span>

<span data-ttu-id="d25cb-178">Met Azure AD-identiteitsbeveiliging u een extra beleid voor voorwaardelijke toegang maken om [MFA te vereisen wanneer het aanmeldingsrisico gemiddeld of hoog is.](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="d25cb-178">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="d25cb-179">U Azure AD-identiteitsbeveiliging en op risico's gebaseerdbeleid voor voorwaardelijke toegang gebruiken met:</span><span class="sxs-lookup"><span data-stu-id="d25cb-179">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="d25cb-180">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="d25cb-180">Microsoft 365 E5</span></span>
- <span data-ttu-id="d25cb-181">Azure AD Premium P2-licenties</span><span class="sxs-lookup"><span data-stu-id="d25cb-181">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="d25cb-182">Zie dit [overzicht van Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d25cb-182">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="mfa-for-an-individual-user-account-not-recommended"></a><span data-ttu-id="d25cb-183">MFA voor een individueel gebruikersaccount (niet aanbevolen)</span><span class="sxs-lookup"><span data-stu-id="d25cb-183">MFA for an individual user account (not recommended)</span></span>

<span data-ttu-id="d25cb-184">U moet beveiligingsstandaards of beleid voor voorwaardelijke toegang gebruiken om MFA voor aanmeldingen van uw gebruikersaccount te vereisen. Als een van deze echter niet kan worden gebruikt, raadt Microsoft MFA ten zeerste aan voor gebruikersaccounts met beheerdersrollen, met name de globale beheerdersrol, voor een abonnement van elke grootte.</span><span class="sxs-lookup"><span data-stu-id="d25cb-184">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span> 

<span data-ttu-id="d25cb-185">U schakelt MFA in voor afzonderlijke gebruikersaccounts vanuit het **actieve gebruikersvenster** van het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="d25cb-185">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="d25cb-186">Nadat de gebruiker zich de volgende keer aanmeldt, wordt hij gevraagd zich te registreren voor MFA en de aanvullende verificatiemethode te kiezen en te testen.</span><span class="sxs-lookup"><span data-stu-id="d25cb-186">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="d25cb-187">Deze methoden samen gebruiken</span><span class="sxs-lookup"><span data-stu-id="d25cb-187">Using these methods together</span></span>

<span data-ttu-id="d25cb-188">In deze tabel ziet u de resultaten van het inschakelen van MFA met de standaardinstellingen voor beveiliging, het beleid voor voorwaardelijke toegang en de instellingen per gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="d25cb-188">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

|| <span data-ttu-id="d25cb-189">Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="d25cb-189">Enabled</span></span> | <span data-ttu-id="d25cb-190">Uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="d25cb-190">Disabled</span></span> | <span data-ttu-id="d25cb-191">Secundaire verificatiemethode</span><span class="sxs-lookup"><span data-stu-id="d25cb-191">Secondary authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="d25cb-192">**Standaardinstellingen voor beveiliging**</span><span class="sxs-lookup"><span data-stu-id="d25cb-192">**Security defaults**</span></span> | <span data-ttu-id="d25cb-193">Kan geen beleid voor voorwaardelijke toegang gebruiken</span><span class="sxs-lookup"><span data-stu-id="d25cb-193">Can’t use Conditional Access policies</span></span> |   <span data-ttu-id="d25cb-194">Kan beleid voor voorwaardelijke toegang gebruiken</span><span class="sxs-lookup"><span data-stu-id="d25cb-194">Can use Conditional Access policies</span></span> | <span data-ttu-id="d25cb-195">De Microsoft Authenticator-app</span><span class="sxs-lookup"><span data-stu-id="d25cb-195">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="d25cb-196">**Beleidsregels voor voorwaardelijke toegang**</span><span class="sxs-lookup"><span data-stu-id="d25cb-196">**Conditional Access policies**</span></span> |<span data-ttu-id="d25cb-197">Als er een of meer zijn ingeschakeld, kunt u de standaardinstellingen voor beveiliging niet inschakelen</span><span class="sxs-lookup"><span data-stu-id="d25cb-197">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="d25cb-198">Als ze allemaal zijn uitgeschakeld, kunt u de standaardinstellingen voor beveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="d25cb-198">If all are disabled, you can enable security defaults</span></span> | <span data-ttu-id="d25cb-199">Door gebruiker opgegeven tijdens MFA-registratie</span><span class="sxs-lookup"><span data-stu-id="d25cb-199">User-specified during MFA registration</span></span> |
| <span data-ttu-id="d25cb-200">**Instelling voor account per gebruiker (niet aanbevolen)**</span><span class="sxs-lookup"><span data-stu-id="d25cb-200">**Per-user account setting (not recommended)**</span></span> | <span data-ttu-id="d25cb-201">Overschreven door beveiligingsstandaards en beleid voor voorwaardelijke toegang waarvoor MFA vereist is</span><span class="sxs-lookup"><span data-stu-id="d25cb-201">Overridden by security defaults and Conditional Access policies requiring MFA</span></span> | <span data-ttu-id="d25cb-202">Overschreven door beveiligingsstandaards en beleid voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="d25cb-202">Overridden by security defaults and Conditional Access policies</span></span> | <span data-ttu-id="d25cb-203">Door gebruiker opgegeven tijdens MFA-registratie</span><span class="sxs-lookup"><span data-stu-id="d25cb-203">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="d25cb-204">Als beveiligingsstandaardinstellingen zijn ingeschakeld, worden alle nieuwe gebruikers gevraagd om MFA-registratie en het gebruik van de Microsoft Authenticator-app bij hun volgende aanmelding.</span><span class="sxs-lookup"><span data-stu-id="d25cb-204">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

<span data-ttu-id="d25cb-205">Als een gebruiker echter een oudere telefoon heeft die tekstberichten kan ontvangen, maar de Microsoft Authenticator-app niet kan uitvoeren, u MFA inschakelen op dat specifieke gebruikersaccount en deze telefoon laten registreren met behulp van de aanvullende verificatiemethode voor tekstcode met de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="d25cb-205">However, if a user has an older phone that can receive text messages but cannot run the Microsoft Authenticator app, you can enable MFA on that specific user account and have them register using the text code additional verification method with these steps:</span></span>

1. <span data-ttu-id="d25cb-206">Beveiligingsstandaardinstellingen uitschakelen in de Azure-portal.</span><span class="sxs-lookup"><span data-stu-id="d25cb-206">Disable security defaults in the Azure portal.</span></span>
2. <span data-ttu-id="d25cb-207">Mfa inschakelen voor het gebruikersaccount in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="d25cb-207">Enable MFA for the user account in the Microsoft 365 admin center.</span></span>
3. <span data-ttu-id="d25cb-208">Laat de gebruiker zich aanmelden en registreren voor MFA en de verificatiemethode voor tekstcodes.</span><span class="sxs-lookup"><span data-stu-id="d25cb-208">Have the user sign in and register for MFA and the text code authentication method.</span></span>
4. <span data-ttu-id="d25cb-209">Als deze is voltooid, schakelt u beveiligingsstandaards in de Azure-portal in</span><span class="sxs-lookup"><span data-stu-id="d25cb-209">When complete, enable security defaults in the Azure portal</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="d25cb-210">Manieren om MFA-instellingen te beheren</span><span class="sxs-lookup"><span data-stu-id="d25cb-210">Ways to manage MFA settings</span></span>

<span data-ttu-id="d25cb-211">Er zijn twee manieren om MFA-instellingen te beheren.</span><span class="sxs-lookup"><span data-stu-id="d25cb-211">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="d25cb-212">In de Azure-portal u het als:</span><span class="sxs-lookup"><span data-stu-id="d25cb-212">In the Azure portal, you can:</span></span>

- <span data-ttu-id="d25cb-213">Beveiligingsstandaardinstellingen in- en uitschakelen</span><span class="sxs-lookup"><span data-stu-id="d25cb-213">Enable and disable security defaults</span></span>
- <span data-ttu-id="d25cb-214">Beleid voor voorwaardelijke toegang configureren</span><span class="sxs-lookup"><span data-stu-id="d25cb-214">Configure Conditional Access policies</span></span>

<span data-ttu-id="d25cb-215">In het Microsoft 365-beheercentrum u MFA-instellingen per gebruiker en service configureren.</span><span class="sxs-lookup"><span data-stu-id="d25cb-215">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="your-next-step"></a><span data-ttu-id="d25cb-216">Uw volgende stap</span><span class="sxs-lookup"><span data-stu-id="d25cb-216">Your next step</span></span>

[<span data-ttu-id="d25cb-217">MFA instellen voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d25cb-217">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)

