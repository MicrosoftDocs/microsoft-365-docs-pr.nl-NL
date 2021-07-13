---
title: Meervoudige verificatie voor Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: MFA (Multi-Factor Authentication) gebruikt zowel een wachtwoord, dat sterk moet zijn, als een extra verificatiemethode.
ms.openlocfilehash: 9b3347f1a8e7b1f62c9bbfe77a7f14c221ef28b5
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393641"
---
# <a name="multifactor-authentication-for-microsoft-365"></a><span data-ttu-id="8185c-103">Meervoudige verificatie voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8185c-103">Multifactor authentication for Microsoft 365</span></span>

<span data-ttu-id="8185c-104">Wachtwoorden zijn de meest voorkomende methode om een aanmelding bij een computer of een online service te verifiëren, maar deze zijn ook het meest kwetsbaar.</span><span class="sxs-lookup"><span data-stu-id="8185c-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="8185c-105">Mensen kunnen eenvoudige wachtwoorden kiezen en dezelfde wachtwoorden gebruiken voor meerdere aanmeldingen bij verschillende computers en services.</span><span class="sxs-lookup"><span data-stu-id="8185c-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="8185c-106">Als u een extra beveiligingsniveau wilt bieden voor aanmeldingen, moet u meervoudige verificatie (MFA) gebruiken, waarbij zowel een wachtwoord wordt gebruikt, dat sterk moet zijn, als een extra verificatiemethode op basis van:</span><span class="sxs-lookup"><span data-stu-id="8185c-106">To provide an additional level of security for sign-ins, you must use multifactor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="8185c-107">Iets wat men bij zich heeft dat niet makkelijk te dupliceren is, zoals een smartphone.</span><span class="sxs-lookup"><span data-stu-id="8185c-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="8185c-108">Iets wat u uniek en biologisch heeft, zoals uw vingerafdrukken, gezicht of ander biometrisch kenmerk.</span><span class="sxs-lookup"><span data-stu-id="8185c-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="8185c-109">De aanvullende verificatiemethode wordt pas gebruikt nadat het wachtwoord van de gebruiker is geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="8185c-109">The additional verification method is not employed until after the user's password has been verified.</span></span> <span data-ttu-id="8185c-110">Met MFA, zelfs als een sterk gebruikerswachtwoord wordt gestolen, heeft de aanvaller niet de beschikking over uw smartphone of vingerafdruk om de aanmelding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="8185c-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="8185c-111">MFA-ondersteuning in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8185c-111">MFA support in Microsoft 365</span></span>

<span data-ttu-id="8185c-112">Standaard wordt MFA ondersteund door Microsoft 365 en Office 365 voor gebruikersaccounts met:</span><span class="sxs-lookup"><span data-stu-id="8185c-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="8185c-113">Een SMS-bericht dat wordt verzonden naar een telefoon waarvoor de gebruiker een verificatiecode moet typen.</span><span class="sxs-lookup"><span data-stu-id="8185c-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="8185c-114">Een telefonische oproep.</span><span class="sxs-lookup"><span data-stu-id="8185c-114">A phone call.</span></span>
- <span data-ttu-id="8185c-115">De Smart Phone-app van Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="8185c-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="8185c-116">In beide gevallen gebruikt de MFA-aanmelding de methode 'iets wat u bij u hebt dat niet gemakkelijk is gedupliceerd' voor de extra verificatie.</span><span class="sxs-lookup"><span data-stu-id="8185c-116">In both cases, the MFA sign-in is using the "something you have with you that is not easily duplicated" method for the additional verification.</span></span> <span data-ttu-id="8185c-117">Er zijn verschillende manieren waarop u MFA voor Microsoft 365 en Office 365 kunt inschakelen:</span><span class="sxs-lookup"><span data-stu-id="8185c-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="8185c-118">Met standaardinstellingen voor beveiliging</span><span class="sxs-lookup"><span data-stu-id="8185c-118">With security defaults</span></span>
- <span data-ttu-id="8185c-119">Met beleidsregels voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="8185c-119">With Conditional Access policies</span></span>
- <span data-ttu-id="8185c-120">Voor elk afzonderlijk gebruikersaccount (niet aanbevolen)</span><span class="sxs-lookup"><span data-stu-id="8185c-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="8185c-121">Deze manieren zijn gebaseerd op uw abonnement op Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8185c-121">These ways are based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="8185c-122">Abonnement</span><span class="sxs-lookup"><span data-stu-id="8185c-122">Plan</span></span>|<span data-ttu-id="8185c-123">Aanbeveling</span><span class="sxs-lookup"><span data-stu-id="8185c-123">Recommendation</span></span>|<span data-ttu-id="8185c-124">Type klant</span><span class="sxs-lookup"><span data-stu-id="8185c-124">Type of customer</span></span>|
|---|---|---|
|<span data-ttu-id="8185c-125">Alle Microsoft 365-abonnementen</span><span class="sxs-lookup"><span data-stu-id="8185c-125">All Microsoft 365 plans</span></span>|<span data-ttu-id="8185c-126">Gebruik standaardinstellingen voor beveiliging, die MFA vereisen voor alle gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="8185c-126">Use security defaults, which require MFA for all user accounts.</span></span> <p> <span data-ttu-id="8185c-127">U kunt MFA per gebruiker ook configureren voor afzonderlijke gebruikersaccounts, maar dit wordt niet aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="8185c-127">You can also configure per-user MFA on individual user accounts, but this is not recommended.</span></span>|<span data-ttu-id="8185c-128">Kleine bedrijven</span><span class="sxs-lookup"><span data-stu-id="8185c-128">Small business</span></span>|
|<span data-ttu-id="8185c-129">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="8185c-129">Microsoft 365 Business Premium</span></span> <p> <span data-ttu-id="8185c-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="8185c-130">Microsoft 365 E3</span></span> <p> <span data-ttu-id="8185c-131">Licenties voor Azure Active Directory (Azure AD) Premium P1</span><span class="sxs-lookup"><span data-stu-id="8185c-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span>|<span data-ttu-id="8185c-132">Gebruik beleid voor voorwaardelijke toegang om MFA in te stellen voor gebruikersaccounts op basis van groepslidmaatschap, apps of andere criteria.</span><span class="sxs-lookup"><span data-stu-id="8185c-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span>|<span data-ttu-id="8185c-133">Klein bedrijf tot ondernemingen</span><span class="sxs-lookup"><span data-stu-id="8185c-133">Small business to enterprise</span></span>|
|<span data-ttu-id="8185c-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="8185c-134">Microsoft 365 E5</span></span> <p> <span data-ttu-id="8185c-135">Licenties voor Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="8185c-135">Azure AD Premium P2 licenses</span></span>|<span data-ttu-id="8185c-136">De Azure AD-identiteitsbeveiliging gebruiken om MFA te vereisen op basis van het aanmeldingsrisicocriterium.</span><span class="sxs-lookup"><span data-stu-id="8185c-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span>|<span data-ttu-id="8185c-137">Enterprise</span><span class="sxs-lookup"><span data-stu-id="8185c-137">Enterprise</span></span>|
||||

### <a name="security-defaults"></a><span data-ttu-id="8185c-138">Standaardinstellingen voor beveiliging</span><span class="sxs-lookup"><span data-stu-id="8185c-138">Security defaults</span></span>

<span data-ttu-id="8185c-139">De standaardinstellingen voor beveiliging zijn een nieuwe functie voor betaalde Microsoft 365- en Office 365-abonnementen en proefabonnementen van Microsoft 365 en Office 365 die zijn gemaakt na 21 oktober 2019.</span><span class="sxs-lookup"><span data-stu-id="8185c-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="8185c-140">Voor deze abonnementen zijn de beveiligingsinstellingen standaard ingeschakeld. Dit betekent het volgende:</span><span class="sxs-lookup"><span data-stu-id="8185c-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="8185c-141">Vereist dat al uw gebruikers MFA gebruiken met de Microsoft Authenticator-app.</span><span class="sxs-lookup"><span data-stu-id="8185c-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="8185c-142">Blokkeert verouderde verificatie.</span><span class="sxs-lookup"><span data-stu-id="8185c-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="8185c-143">Gebruikers hebben 14 dagen de tijd om zich te registreren voor MFA met de Microsoft Authenticator-app vanaf hun smartphone. Deze periode gaat in bij de eerste aanmelding nadat de standaardinstellingen voor beveiliging zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8185c-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="8185c-144">Na 14 dagen kunnen gebruikers zich alleen aanmelden als de MFA-registratie is voltooid.</span><span class="sxs-lookup"><span data-stu-id="8185c-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="8185c-145">De standaardinstellingen voor beveiliging bieden organisaties een basisbeveiligingsniveau voor gebruikersaanmeldingen dat standaard is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8185c-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="8185c-146">U kunt de standaardinstellingen voor beveiliging uitschakelen ten gunste van MFA met voorwaardelijk toegangsbeleid.</span><span class="sxs-lookup"><span data-stu-id="8185c-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="8185c-147">U kunt beveiligingsstandaarden in- of uitschakelen vanuit het **eigenschappen** venster voor Azure AD in de Azure-portal.</span><span class="sxs-lookup"><span data-stu-id="8185c-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![Afbeelding van de pagina Adreslijsteigenschappen.](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="8185c-149">U kunt beveiligingsstandaarden gebruiken met elk Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="8185c-149">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="8185c-150">Zie dit [overzicht van gevoeligheidslabels](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8185c-150">For more information, see this [overview of security defaults](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="8185c-151">Beleid voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="8185c-151">Conditional Access policies</span></span>

<span data-ttu-id="8185c-152">Beleidsregels voor voorwaardelijke toegang zijn regels waarmee wordt aangegeven wanneer aanmeldingen worden beoordeeld en toegestaan.</span><span class="sxs-lookup"><span data-stu-id="8185c-152">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="8185c-153">U kunt bijvoorbeeld een toegangsbeleid met de volgende voorwaarden maken:</span><span class="sxs-lookup"><span data-stu-id="8185c-153">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="8185c-154">Als de naam van het gebruikersaccount lid is van een groep gebruikers die is toegewezen aan een Exchange-, gebruikers-, wachtwoord-, beveiligings-, SharePoint- of globale beheerdersrol, wordt MFA vereist om toegang te verlenen.</span><span class="sxs-lookup"><span data-stu-id="8185c-154">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="8185c-155">Met dit beleid kunt u MFA op basis van groepslidmaatschap vereisen in plaats van dat u afzonderlijke gebruikersaccounts voor MFA gaat configureren wanneer deze worden toegewezen (of als de toewijzing ongedaan wordt gemaakt) vanuit deze beheerdersrollen.</span><span class="sxs-lookup"><span data-stu-id="8185c-155">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="8185c-156">U kunt beleidsregels voor voorwaardelijke toegang ook gebruiken voor meer geavanceerde mogelijkheden, zoals vereisen dat MFA wordt gebruikt voor bepaalde apps, of dat de aanmelding wordt uitgevoerd vanaf een compatibel apparaat, zoals uw laptop met Windows 10.</span><span class="sxs-lookup"><span data-stu-id="8185c-156">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="8185c-157">U configureert het beleid voor voorwaardelijke toegang vanuit het deelvenster **Beveiliging** voor Azure AD in de Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="8185c-157">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![Afbeelding van menuoptie voor Voorwaardelijke toegang](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="8185c-159">U kunt voorwaardelijke toegangsbeleidsregels gebruiken met:</span><span class="sxs-lookup"><span data-stu-id="8185c-159">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="8185c-160">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="8185c-160">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="8185c-161">Microsoft 365 E3 en E5</span><span class="sxs-lookup"><span data-stu-id="8185c-161">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="8185c-162">Azure AD Premium P1 en Azure AD Premium P2-licenties</span><span class="sxs-lookup"><span data-stu-id="8185c-162">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="8185c-163">Voor kleine bedrijven die Microsoft 365 Business Premium gebruikten, kunt u eenvoudig beleid voor voorwaardelijke toegang instellen met de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="8185c-163">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="8185c-164">Maak een groep voor de gebruikersaccounts die MFA vereisen.</span><span class="sxs-lookup"><span data-stu-id="8185c-164">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="8185c-165">Schakel het beleid **MFA vereisen voor globale beheerders** in.</span><span class="sxs-lookup"><span data-stu-id="8185c-165">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="8185c-166">Een beleid voor voorwaardelijke toegang op basis van een groep maken met deze instellingen:</span><span class="sxs-lookup"><span data-stu-id="8185c-166">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="8185c-167">Opdrachten > Gebruikers en groepen: de naam van uw groep uit stap 1 hierboven.</span><span class="sxs-lookup"><span data-stu-id="8185c-167">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="8185c-168">Opdrachten > Cloud-apps of -acties: alle Cloud-apps.</span><span class="sxs-lookup"><span data-stu-id="8185c-168">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="8185c-169">Toegangscontrole > Verlenen > Toegang verlenen > Meervoudige verificatie vereisen.</span><span class="sxs-lookup"><span data-stu-id="8185c-169">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="8185c-170">Schakel het beleid in.</span><span class="sxs-lookup"><span data-stu-id="8185c-170">Enable the policy.</span></span>
5. <span data-ttu-id="8185c-171">Voeg een gebruikersaccount toe aan de groep die u in Stap 1 hebt gemaakt en voer een test uit.</span><span class="sxs-lookup"><span data-stu-id="8185c-171">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="8185c-172">Als u MFA wilt vereisen voor extra gebruikersaccounts, kunt u deze toevoegen aan de groep die u in stap 1 hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8185c-172">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="8185c-173">Met dit beleid voor voorwaardelijke toegang kunt u de MFA-vereiste voor uw gebruikers in uw eigen tempo uitrollen.</span><span class="sxs-lookup"><span data-stu-id="8185c-173">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="8185c-174">Ondernemingen moeten [Gemeenschappelijk beleid voor voorwaardelijke toegang](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) gebruiken om het volgende beleid te configureren:</span><span class="sxs-lookup"><span data-stu-id="8185c-174">Enterprises should use [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="8185c-175">MFA vereisen voor beheerders</span><span class="sxs-lookup"><span data-stu-id="8185c-175">Require MFA for administrators</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="8185c-176">MFA vereisen voor alle gebruikers</span><span class="sxs-lookup"><span data-stu-id="8185c-176">Require MFA for all users</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="8185c-177">Verouderde verificatie blokkeren</span><span class="sxs-lookup"><span data-stu-id="8185c-177">Block legacy authentication</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="8185c-178">Zie dit [overzicht van voorwaardelijke toegang](/azure/active-directory/conditional-access/overview) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8185c-178">For more information, see this [overview of Conditional Access](/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="8185c-179">Azure AD-identiteitsbescherming</span><span class="sxs-lookup"><span data-stu-id="8185c-179">Azure AD Identity Protection</span></span>

<span data-ttu-id="8185c-180">Met Azure AD-identiteitsbescherming kunt u een aanvullend beleid voor voorwaardelijke toegang maken om [MFA te vereisen wanneer het aanmeldingsrisico gemiddeld of hoog is](../../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk).</span><span class="sxs-lookup"><span data-stu-id="8185c-180">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](../../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="8185c-181">U kunt Azure AD-identiteitsbescherming en beleid voor voorwaardelijke toegang op basis van risico gebruiken met:</span><span class="sxs-lookup"><span data-stu-id="8185c-181">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="8185c-182">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="8185c-182">Microsoft 365 E5</span></span>
- <span data-ttu-id="8185c-183">Licenties voor Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="8185c-183">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="8185c-184">Zie dit [overzicht van Azure AD-identiteitsbescherming](/azure/active-directory/identity-protection/overview-identity-protection) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8185c-184">For more information, see this [overview of Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="legacy-per-user-mfa-not-recommended"></a><span data-ttu-id="8185c-185">Oudere MFA per gebruiker (niet aanbevolen)</span><span class="sxs-lookup"><span data-stu-id="8185c-185">Legacy per-user MFA (not recommended)</span></span>

<span data-ttu-id="8185c-186">U moet beveiligingsstandaarden of beleid voor voorwaardelijke toegang gebruiken om MFA te vereisen voor het aanmelden van gebruikersaccounts. Als een van beide echter niet kan worden gebruikt, raadt Microsoft ten zeerste aan om MFA te gebruiken voor gebruikersaccounts met beheerdersrollen, met name voor de algemene beheerdersrol, voor elke abonnementomvang.</span><span class="sxs-lookup"><span data-stu-id="8185c-186">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span>

<span data-ttu-id="8185c-187">U schakelt MFA in voor individuele gebruikersaccounts vanuit het venster **Actieve gebruiker** van het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="8185c-187">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![Afbeelding van de optie Meervoudige verificatie op de pagina Actieve gebruikers](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="8185c-189">Wanneer de gebruiker zich de volgende keer aanmeldt, wordt hen gevraagd zich aan te melden bij MFA en de extra verificatiemethode te kiezen en te testen.</span><span class="sxs-lookup"><span data-stu-id="8185c-189">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="8185c-190">Deze methoden samen gebruiken</span><span class="sxs-lookup"><span data-stu-id="8185c-190">Using these methods together</span></span>

<span data-ttu-id="8185c-191">In deze tabel ziet u de resultaten van het inschakelen van MFA met de standaardinstellingen voor beveiliging, het beleid voor voorwaardelijke toegang en de instellingen per gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="8185c-191">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

|<span data-ttu-id="8185c-192">*Item*</span><span class="sxs-lookup"><span data-stu-id="8185c-192">*Item*</span></span>|<span data-ttu-id="8185c-193">Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="8185c-193">Enabled</span></span>|<span data-ttu-id="8185c-194">Uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="8185c-194">Disabled</span></span>|<span data-ttu-id="8185c-195">Secundaire verificatiemethode</span><span class="sxs-lookup"><span data-stu-id="8185c-195">Secondary authentication method</span></span>|
|---|---|---|---|
|<span data-ttu-id="8185c-196">**Standaardinstellingen voor beveiliging**</span><span class="sxs-lookup"><span data-stu-id="8185c-196">**Security defaults**</span></span>|<span data-ttu-id="8185c-197">Beleid voor voorwaardelijke toegang kan niet worden gebruikt</span><span class="sxs-lookup"><span data-stu-id="8185c-197">Can't use Conditional Access policies</span></span>|<span data-ttu-id="8185c-198">Kan beleid voor voorwaardelijke toegang gebruiken</span><span class="sxs-lookup"><span data-stu-id="8185c-198">Can use Conditional Access policies</span></span>|<span data-ttu-id="8185c-199">De Microsoft Authenticator-app</span><span class="sxs-lookup"><span data-stu-id="8185c-199">Microsoft Authenticator app</span></span>|
|<span data-ttu-id="8185c-200">**Beleidsregels voor voorwaardelijke toegang**</span><span class="sxs-lookup"><span data-stu-id="8185c-200">**Conditional Access policies**</span></span>|<span data-ttu-id="8185c-201">Als deze zijn ingeschakeld, kunt u beveiligingsinstellingen niet inschakelen</span><span class="sxs-lookup"><span data-stu-id="8185c-201">If any are enabled, you can't enable security defaults</span></span>|<span data-ttu-id="8185c-202">Als ze allemaal zijn uitgeschakeld, kunt u de standaardinstellingen voor beveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="8185c-202">If all are disabled, you can enable security defaults</span></span>|<span data-ttu-id="8185c-203">Door gebruiker opgegeven tijdens MFA-registratie</span><span class="sxs-lookup"><span data-stu-id="8185c-203">User-specified during MFA registration</span></span>|
|<span data-ttu-id="8185c-204">**Oudere MFA per gebruiker (niet aanbevolen)**</span><span class="sxs-lookup"><span data-stu-id="8185c-204">**Legacy per-user MFA (not recommended)**</span></span>|<span data-ttu-id="8185c-205">Negeert beveiligingsstandaarden en beleid voor voorwaardelijke toegang dat MFA vereist bij elke aanmelding</span><span class="sxs-lookup"><span data-stu-id="8185c-205">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span>|<span data-ttu-id="8185c-206">Genegeerd door beveiligingsstandaarden en beleid voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="8185c-206">Overridden by security defaults and Conditional Access policies</span></span>|<span data-ttu-id="8185c-207">Door gebruiker opgegeven tijdens MFA-registratie</span><span class="sxs-lookup"><span data-stu-id="8185c-207">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="8185c-208">Als beveiligingsstandaarden zijn ingeschakeld, worden alle nieuwe gebruikers bij hun volgende aanmelding gevraagd om MFA-registratie en het gebruik van de Microsoft Authenticator-app.</span><span class="sxs-lookup"><span data-stu-id="8185c-208">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="8185c-209">Manieren om MFA-instellingen te beheren</span><span class="sxs-lookup"><span data-stu-id="8185c-209">Ways to manage MFA settings</span></span>

<span data-ttu-id="8185c-210">Er zijn twee manieren om MFA-instellingen te beheren.</span><span class="sxs-lookup"><span data-stu-id="8185c-210">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="8185c-211">In de Azure-Portal kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="8185c-211">In the Azure portal, you can:</span></span>

- <span data-ttu-id="8185c-212">Standaardinstellingen voor beveiliging in- en uitschakelen</span><span class="sxs-lookup"><span data-stu-id="8185c-212">Enable and disable security defaults</span></span>
- <span data-ttu-id="8185c-213">Beleid voor voorwaardelijke toegang configureren</span><span class="sxs-lookup"><span data-stu-id="8185c-213">Configure Conditional Access policies</span></span>

<span data-ttu-id="8185c-214">In het Microsoft 365-beheercentrum kunt u MFA-instellingen per gebruiker en service configureren.</span><span class="sxs-lookup"><span data-stu-id="8185c-214">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8185c-215">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="8185c-215">Next steps</span></span>

[<span data-ttu-id="8185c-216">MFA instellen voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8185c-216">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)

## <a name="related-content"></a><span data-ttu-id="8185c-217">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="8185c-217">Related content</span></span>

<span data-ttu-id="8185c-218">[Meervoudige verificatie](../../business-video/turn-on-mfa.md) (video)\ inschakelen</span><span class="sxs-lookup"><span data-stu-id="8185c-218">[Turn on multifactor authentication](../../business-video/turn-on-mfa.md) (video)\</span></span>
<span data-ttu-id="8185c-219">[Meervoudige verificatie voor uw telefoon inschakelen](../../business-video/set-up-mfa.md) (video)</span><span class="sxs-lookup"><span data-stu-id="8185c-219">[Turn on multifactor authentication for your phone](../../business-video/set-up-mfa.md) (video)</span></span>