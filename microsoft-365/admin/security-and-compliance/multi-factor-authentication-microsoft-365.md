---
title: Meervoudige verificatie instellen voor Microsoft 365
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over meervoudige verificatie in Microsoft 365.
ms.openlocfilehash: cb425f3fd3d97dc0cd8815699bd22cb2540aed46
ms.sourcegitcommit: 09518b7c9146cda7fd42839ee644ad418d48491a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/12/2020
ms.locfileid: "49001511"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="00f9e-103">Meervoudige verificatie instellen voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="00f9e-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="00f9e-104">Wachtwoorden zijn de meest voorkomende methode om een aanmelding bij een computer of een online service te verifiëren, maar deze zijn ook het meest kwetsbaar.</span><span class="sxs-lookup"><span data-stu-id="00f9e-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="00f9e-105">Mensen kunnen eenvoudige wachtwoorden kiezen en dezelfde wachtwoorden gebruiken voor meerdere aanmeldingen bij verschillende computers en services.</span><span class="sxs-lookup"><span data-stu-id="00f9e-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="00f9e-106">Om een extra beveiligingsniveau voor aanmeldingen te bieden, moet u meervoudige verificatie (MFA) gebruiken, dat zowel een wachtwoord gebruikt dat sterk moet zijn, als een aanvullende verificatiemethode op basis van:</span><span class="sxs-lookup"><span data-stu-id="00f9e-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="00f9e-107">Iets wat men bij zich heeft dat niet makkelijk te dupliceren is, zoals een smartphone.</span><span class="sxs-lookup"><span data-stu-id="00f9e-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="00f9e-108">Iets wat u uniek en biologisch heeft, zoals uw vingerafdrukken, gezicht of ander biometrisch kenmerk.</span><span class="sxs-lookup"><span data-stu-id="00f9e-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="00f9e-109">De extra verificatiemethode wordt pas gebruikt wanneer het wachtwoord van de gebruiker is geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="00f9e-109">The additional verification method is not employed until after the user's password has been verified.</span></span> <span data-ttu-id="00f9e-110">Met MFA, zelfs als een sterk gebruikerswachtwoord wordt gestolen, heeft de aanvaller niet de beschikking over uw smartphone of vingerafdruk om de aanmelding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="00f9e-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="00f9e-111">MFA-ondersteuning in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="00f9e-111">MFA support in Microsoft 365</span></span>

<span data-ttu-id="00f9e-112">Standaard wordt MFA ondersteund door Microsoft 365 en Office 365 voor gebruikersaccounts met:</span><span class="sxs-lookup"><span data-stu-id="00f9e-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="00f9e-113">Een SMS-bericht dat wordt verzonden naar een telefoon waarvoor de gebruiker een verificatiecode moet typen.</span><span class="sxs-lookup"><span data-stu-id="00f9e-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="00f9e-114">Een telefonische oproep.</span><span class="sxs-lookup"><span data-stu-id="00f9e-114">A phone call.</span></span>
- <span data-ttu-id="00f9e-115">De Smart Phone-app van Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="00f9e-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="00f9e-116">In beide gevallen wordt met de SSO-aanmelding de methode ' wat u met u hebt met u hebt die u niet eenvoudig gedupliceerd ' gebruikt voor de aanvullende verificatie.</span><span class="sxs-lookup"><span data-stu-id="00f9e-116">In both cases, the MFA sign-in is using the "something you have with you that is not easily duplicated" method for the additional verification.</span></span> <span data-ttu-id="00f9e-117">Er zijn verschillende manieren waarop u MFA voor Microsoft 365 en Office 365 kunt inschakelen:</span><span class="sxs-lookup"><span data-stu-id="00f9e-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="00f9e-118">Met standaardinstellingen voor beveiliging</span><span class="sxs-lookup"><span data-stu-id="00f9e-118">With security defaults</span></span>
- <span data-ttu-id="00f9e-119">Met beleidsregels voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="00f9e-119">With Conditional Access policies</span></span>
- <span data-ttu-id="00f9e-120">Voor elk afzonderlijk gebruikersaccount (niet aanbevolen)</span><span class="sxs-lookup"><span data-stu-id="00f9e-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="00f9e-121">Deze manieren zijn gebaseerd op uw abonnement op Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="00f9e-121">These ways are based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="00f9e-122">Abonnement</span><span class="sxs-lookup"><span data-stu-id="00f9e-122">Plan</span></span>|<span data-ttu-id="00f9e-123">Aanbeveling</span><span class="sxs-lookup"><span data-stu-id="00f9e-123">Recommendation</span></span>|<span data-ttu-id="00f9e-124">Type klant</span><span class="sxs-lookup"><span data-stu-id="00f9e-124">Type of customer</span></span>|
|---|---|---|
|<span data-ttu-id="00f9e-125">Alle Microsoft 365-abonnementen</span><span class="sxs-lookup"><span data-stu-id="00f9e-125">All Microsoft 365 plans</span></span>|<span data-ttu-id="00f9e-126">Gebruik standaardinstellingen voor beveiliging, die MFA vereisen voor alle gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="00f9e-126">Use security defaults, which require MFA for all user accounts.</span></span> <p> <span data-ttu-id="00f9e-127">U kunt ook per gebruiker MFA configureren voor afzonderlijke gebruikersaccounts, maar dit wordt niet aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="00f9e-127">You can also configure per-user MFA on individual user accounts, but this is not recommended.</span></span>|<span data-ttu-id="00f9e-128">Kleine bedrijven</span><span class="sxs-lookup"><span data-stu-id="00f9e-128">Small business</span></span>|
|<span data-ttu-id="00f9e-129">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="00f9e-129">Microsoft 365 Business Premium</span></span> <p> <span data-ttu-id="00f9e-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="00f9e-130">Microsoft 365 E3</span></span> <p> <span data-ttu-id="00f9e-131">Licenties voor Azure Active Directory (Azure AD) Premium P1</span><span class="sxs-lookup"><span data-stu-id="00f9e-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span>|<span data-ttu-id="00f9e-132">Gebruik beleid voor voorwaardelijke toegang om MFA in te stellen voor gebruikersaccounts op basis van groepslidmaatschap, apps of andere criteria.</span><span class="sxs-lookup"><span data-stu-id="00f9e-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span>|<span data-ttu-id="00f9e-133">Klein bedrijf tot ondernemingen</span><span class="sxs-lookup"><span data-stu-id="00f9e-133">Small business to enterprise</span></span>|
|<span data-ttu-id="00f9e-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="00f9e-134">Microsoft 365 E5</span></span> <p> <span data-ttu-id="00f9e-135">Licenties voor Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="00f9e-135">Azure AD Premium P2 licenses</span></span>|<span data-ttu-id="00f9e-136">De Azure AD-identiteitsbeveiliging gebruiken om MFA te vereisen op basis van het aanmeldingsrisicocriterium.</span><span class="sxs-lookup"><span data-stu-id="00f9e-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span>|<span data-ttu-id="00f9e-137">Enterprise</span><span class="sxs-lookup"><span data-stu-id="00f9e-137">Enterprise</span></span>|
||||

### <a name="security-defaults"></a><span data-ttu-id="00f9e-138">Standaardinstellingen voor beveiliging</span><span class="sxs-lookup"><span data-stu-id="00f9e-138">Security defaults</span></span>

<span data-ttu-id="00f9e-139">De standaardinstellingen voor beveiliging zijn een nieuwe functie voor betaalde Microsoft 365- en Office 365-abonnementen en proefabonnementen van Microsoft 365 en Office 365 die zijn gemaakt na 21 oktober 2019.</span><span class="sxs-lookup"><span data-stu-id="00f9e-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="00f9e-140">Voor deze abonnementen zijn de beveiligingsinstellingen standaard ingeschakeld. Dit betekent het volgende:</span><span class="sxs-lookup"><span data-stu-id="00f9e-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="00f9e-141">Vereist dat al uw gebruikers MFA gebruiken met de Microsoft Authenticator-app.</span><span class="sxs-lookup"><span data-stu-id="00f9e-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="00f9e-142">Blokkeert verouderde verificatie.</span><span class="sxs-lookup"><span data-stu-id="00f9e-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="00f9e-143">Gebruikers hebben 14 dagen de tijd om zich te registreren voor MFA met de Microsoft Authenticator-app vanaf hun smartphone. Deze periode gaat in bij de eerste aanmelding nadat de standaardinstellingen voor beveiliging zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="00f9e-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="00f9e-144">Na 14 dagen kunnen gebruikers zich alleen aanmelden als de MFA-registratie is voltooid.</span><span class="sxs-lookup"><span data-stu-id="00f9e-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="00f9e-145">De standaardinstellingen voor beveiliging bieden organisaties een basisbeveiligingsniveau voor gebruikersaanmeldingen dat standaard is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="00f9e-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="00f9e-146">U kunt de standaardinstellingen voor beveiliging uitschakelen ten gunste van MFA met voorwaardelijk toegangsbeleid.</span><span class="sxs-lookup"><span data-stu-id="00f9e-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="00f9e-147">U kunt beveiligingsstandaarden in- of uitschakelen vanuit het **eigenschappen** venster voor Azure AD in de Azure-portal.</span><span class="sxs-lookup"><span data-stu-id="00f9e-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![Afbeelding van de pagina met adreslijst eigenschappen.](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="00f9e-149">U kunt beveiligingsstandaarden gebruiken met elk Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="00f9e-149">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="00f9e-150">Zie dit [overzicht van gevoeligheidslabels](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="00f9e-150">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="00f9e-151">Beleid voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="00f9e-151">Conditional Access policies</span></span>

<span data-ttu-id="00f9e-152">Beleidsregels voor voorwaardelijke toegang zijn regels waarmee wordt aangegeven wanneer aanmeldingen worden beoordeeld en toegestaan.</span><span class="sxs-lookup"><span data-stu-id="00f9e-152">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="00f9e-153">U kunt bijvoorbeeld een toegangsbeleid met de volgende voorwaarden maken:</span><span class="sxs-lookup"><span data-stu-id="00f9e-153">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="00f9e-154">Als de naam van het gebruikersaccount lid is van een groep gebruikers die is toegewezen aan een Exchange-, gebruikers-, wachtwoord-, beveiligings-, SharePoint- of globale beheerdersrol, wordt MFA vereist om toegang te verlenen.</span><span class="sxs-lookup"><span data-stu-id="00f9e-154">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="00f9e-155">Met dit beleid kunt u MFA op basis van groepslidmaatschap vereisen in plaats van dat u afzonderlijke gebruikersaccounts voor MFA gaat configureren wanneer deze worden toegewezen (of als de toewijzing ongedaan wordt gemaakt) vanuit deze beheerdersrollen.</span><span class="sxs-lookup"><span data-stu-id="00f9e-155">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="00f9e-156">U kunt beleidsregels voor voorwaardelijke toegang ook gebruiken voor meer geavanceerde mogelijkheden, zoals vereisen dat MFA wordt gebruikt voor bepaalde apps, of dat de aanmelding wordt uitgevoerd vanaf een compatibel apparaat, zoals uw laptop met Windows 10.</span><span class="sxs-lookup"><span data-stu-id="00f9e-156">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="00f9e-157">U configureert het beleid voor voorwaardelijke toegang vanuit het deelvenster **Beveiliging** voor Azure AD in de Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="00f9e-157">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![Afbeelding van de menuoptie voor voorwaardelijke toegang](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="00f9e-159">U kunt voorwaardelijke toegangsbeleidsregels gebruiken met:</span><span class="sxs-lookup"><span data-stu-id="00f9e-159">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="00f9e-160">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="00f9e-160">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="00f9e-161">Microsoft 365 E3 en E5</span><span class="sxs-lookup"><span data-stu-id="00f9e-161">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="00f9e-162">Azure AD Premium P1 en Azure AD Premium P2-licenties</span><span class="sxs-lookup"><span data-stu-id="00f9e-162">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="00f9e-163">Voor kleine bedrijven die Microsoft 365 Business Premium gebruikten, kunt u eenvoudig beleid voor voorwaardelijke toegang instellen met de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="00f9e-163">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="00f9e-164">Maak een groep voor de gebruikersaccounts die MFA vereisen.</span><span class="sxs-lookup"><span data-stu-id="00f9e-164">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="00f9e-165">Schakel het beleid **MFA vereisen voor globale beheerders** in.</span><span class="sxs-lookup"><span data-stu-id="00f9e-165">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="00f9e-166">Een beleid voor voorwaardelijke toegang op basis van een groep maken met deze instellingen:</span><span class="sxs-lookup"><span data-stu-id="00f9e-166">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="00f9e-167">Opdrachten > Gebruikers en groepen: de naam van uw groep uit stap 1 hierboven.</span><span class="sxs-lookup"><span data-stu-id="00f9e-167">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="00f9e-168">Opdrachten > Cloud-apps of -acties: alle Cloud-apps.</span><span class="sxs-lookup"><span data-stu-id="00f9e-168">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="00f9e-169">Toegangscontrole > Verlenen > Toegang verlenen > Meervoudige verificatie vereisen.</span><span class="sxs-lookup"><span data-stu-id="00f9e-169">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="00f9e-170">Schakel het beleid in.</span><span class="sxs-lookup"><span data-stu-id="00f9e-170">Enable the policy.</span></span>
5. <span data-ttu-id="00f9e-171">Voeg een gebruikersaccount toe aan de groep die u in Stap 1 hebt gemaakt en voer een test uit.</span><span class="sxs-lookup"><span data-stu-id="00f9e-171">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="00f9e-172">Als u MFA wilt vereisen voor extra gebruikersaccounts, kunt u deze toevoegen aan de groep die u in stap 1 hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="00f9e-172">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="00f9e-173">Met dit beleid voor voorwaardelijke toegang kunt u de MFA-vereiste voor uw gebruikers in uw eigen tempo uitrollen.</span><span class="sxs-lookup"><span data-stu-id="00f9e-173">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="00f9e-174">Ondernemingen moeten [Gemeenschappelijk beleid voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) gebruiken om het volgende beleid te configureren:</span><span class="sxs-lookup"><span data-stu-id="00f9e-174">Enterprises should use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="00f9e-175">MFA vereisen voor beheerders</span><span class="sxs-lookup"><span data-stu-id="00f9e-175">Require MFA for administrators</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="00f9e-176">MFA vereisen voor alle gebruikers</span><span class="sxs-lookup"><span data-stu-id="00f9e-176">Require MFA for all users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="00f9e-177">Verouderde verificatie blokkeren</span><span class="sxs-lookup"><span data-stu-id="00f9e-177">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="00f9e-178">Zie dit [overzicht van voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="00f9e-178">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="00f9e-179">Azure AD-identiteitsbescherming</span><span class="sxs-lookup"><span data-stu-id="00f9e-179">Azure AD Identity Protection</span></span>

<span data-ttu-id="00f9e-180">Met Azure AD-identiteitsbescherming kunt u een aanvullend beleid voor voorwaardelijke toegang maken om [MFA te vereisen wanneer het aanmeldingsrisico gemiddeld of hoog is](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span><span class="sxs-lookup"><span data-stu-id="00f9e-180">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="00f9e-181">U kunt Azure AD-identiteitsbescherming en beleid voor voorwaardelijke toegang op basis van risico gebruiken met:</span><span class="sxs-lookup"><span data-stu-id="00f9e-181">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="00f9e-182">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="00f9e-182">Microsoft 365 E5</span></span>
- <span data-ttu-id="00f9e-183">Licenties voor Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="00f9e-183">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="00f9e-184">Zie dit [overzicht van Azure AD-identiteitsbescherming](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="00f9e-184">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="legacy-per-user-mfa-not-recommended"></a><span data-ttu-id="00f9e-185">Verouderde MFA per gebruiker (niet aanbevolen)</span><span class="sxs-lookup"><span data-stu-id="00f9e-185">Legacy per-user MFA (not recommended)</span></span>

<span data-ttu-id="00f9e-186">U moet beveiligingsstandaarden of beleid voor voorwaardelijke toegang gebruiken om MFA te vereisen voor het aanmelden van gebruikersaccounts. Als een van beide echter niet kan worden gebruikt, raadt Microsoft ten zeerste aan om MFA te gebruiken voor gebruikersaccounts met beheerdersrollen, met name voor de algemene beheerdersrol, voor elke abonnementomvang.</span><span class="sxs-lookup"><span data-stu-id="00f9e-186">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span>

<span data-ttu-id="00f9e-187">U schakelt MFA in voor individuele gebruikersaccounts vanuit het venster **Actieve gebruiker** van het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="00f9e-187">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![Afbeelding van de optie multi factor Authentication op de pagina actieve gebruikers](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="00f9e-189">Wanneer de gebruiker zich de volgende keer aanmeldt, wordt hen gevraagd zich aan te melden bij MFA en de extra verificatiemethode te kiezen en te testen.</span><span class="sxs-lookup"><span data-stu-id="00f9e-189">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="00f9e-190">Deze methoden samen gebruiken</span><span class="sxs-lookup"><span data-stu-id="00f9e-190">Using these methods together</span></span>

<span data-ttu-id="00f9e-191">In deze tabel ziet u de resultaten van het inschakelen van MFA met de standaardinstellingen voor beveiliging, het beleid voor voorwaardelijke toegang en de instellingen per gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="00f9e-191">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

||<span data-ttu-id="00f9e-192">Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="00f9e-192">Enabled</span></span>|<span data-ttu-id="00f9e-193">Uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="00f9e-193">Disabled</span></span>|<span data-ttu-id="00f9e-194">Secundaire verificatiemethode</span><span class="sxs-lookup"><span data-stu-id="00f9e-194">Secondary authentication method</span></span>|
|---|---|---|---|
|<span data-ttu-id="00f9e-195">**Standaardinstellingen voor beveiliging**</span><span class="sxs-lookup"><span data-stu-id="00f9e-195">**Security defaults**</span></span>|<span data-ttu-id="00f9e-196">Kan beleidsregels voor voorwaardelijke toegang niet gebruiken</span><span class="sxs-lookup"><span data-stu-id="00f9e-196">Can't use Conditional Access policies</span></span>|<span data-ttu-id="00f9e-197">Kan beleid voor voorwaardelijke toegang gebruiken</span><span class="sxs-lookup"><span data-stu-id="00f9e-197">Can use Conditional Access policies</span></span>|<span data-ttu-id="00f9e-198">De Microsoft Authenticator-app</span><span class="sxs-lookup"><span data-stu-id="00f9e-198">Microsoft Authenticator app</span></span>|
|<span data-ttu-id="00f9e-199">**Beleidsregels voor voorwaardelijke toegang**</span><span class="sxs-lookup"><span data-stu-id="00f9e-199">**Conditional Access policies**</span></span>|<span data-ttu-id="00f9e-200">Als dit is ingeschakeld, kunt u de beveiligingsinstellingen niet inschakelen</span><span class="sxs-lookup"><span data-stu-id="00f9e-200">If any are enabled, you can't enable security defaults</span></span>|<span data-ttu-id="00f9e-201">Als ze allemaal zijn uitgeschakeld, kunt u de standaardinstellingen voor beveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="00f9e-201">If all are disabled, you can enable security defaults</span></span>|<span data-ttu-id="00f9e-202">Door gebruiker opgegeven tijdens MFA-registratie</span><span class="sxs-lookup"><span data-stu-id="00f9e-202">User-specified during MFA registration</span></span>|
|<span data-ttu-id="00f9e-203">**Verouderde MFA per gebruiker (niet aanbevolen)**</span><span class="sxs-lookup"><span data-stu-id="00f9e-203">**Legacy per-user MFA (not recommended)**</span></span>|<span data-ttu-id="00f9e-204">Negeert beveiligingsstandaarden en beleid voor voorwaardelijke toegang dat MFA vereist bij elke aanmelding</span><span class="sxs-lookup"><span data-stu-id="00f9e-204">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span>|<span data-ttu-id="00f9e-205">Genegeerd door beveiligingsstandaarden en beleid voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="00f9e-205">Overridden by security defaults and Conditional Access policies</span></span>|<span data-ttu-id="00f9e-206">Door gebruiker opgegeven tijdens MFA-registratie</span><span class="sxs-lookup"><span data-stu-id="00f9e-206">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="00f9e-207">Als beveiligingsstandaarden zijn ingeschakeld, worden alle nieuwe gebruikers bij hun volgende aanmelding gevraagd om MFA-registratie en het gebruik van de Microsoft Authenticator-app.</span><span class="sxs-lookup"><span data-stu-id="00f9e-207">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="00f9e-208">Manieren om MFA-instellingen te beheren</span><span class="sxs-lookup"><span data-stu-id="00f9e-208">Ways to manage MFA settings</span></span>

<span data-ttu-id="00f9e-209">Er zijn twee manieren om MFA-instellingen te beheren.</span><span class="sxs-lookup"><span data-stu-id="00f9e-209">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="00f9e-210">In de Azure-Portal kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="00f9e-210">In the Azure portal, you can:</span></span>

- <span data-ttu-id="00f9e-211">Standaardinstellingen voor beveiliging in- en uitschakelen</span><span class="sxs-lookup"><span data-stu-id="00f9e-211">Enable and disable security defaults</span></span>
- <span data-ttu-id="00f9e-212">Beleid voor voorwaardelijke toegang configureren</span><span class="sxs-lookup"><span data-stu-id="00f9e-212">Configure Conditional Access policies</span></span>

<span data-ttu-id="00f9e-213">In het Microsoft 365-beheercentrum kunt u MFA-instellingen per gebruiker en service configureren.</span><span class="sxs-lookup"><span data-stu-id="00f9e-213">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="your-next-step"></a><span data-ttu-id="00f9e-214">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="00f9e-214">Your next step</span></span>

[<span data-ttu-id="00f9e-215">MFA instellen voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="00f9e-215">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)
