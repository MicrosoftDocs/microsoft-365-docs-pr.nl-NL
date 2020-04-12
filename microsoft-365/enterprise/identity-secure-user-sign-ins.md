---
title: 'Stap 3: gebruikersaanmeldingen beveiligen en beheren'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: U kunt gebruikersaanmeldingen voor Windows-apparaten en voor Microsoft 365 veiliger maken.
ms.openlocfilehash: c541f5b74fe3ea6e94b002212f21ec8645e8e87e
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806847"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a><span data-ttu-id="9fcff-103">Stap 3: gebruikersaanmeldingen beveiligen en beheren</span><span class="sxs-lookup"><span data-stu-id="9fcff-103">Step 3: Secure and manage your user sign-ins</span></span>

![Fase 2-identiteit](../media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a><span data-ttu-id="9fcff-105">Windows Hello voor Bedrijven gebruiken</span><span class="sxs-lookup"><span data-stu-id="9fcff-105">Use Windows Hello for Business</span></span>

<span data-ttu-id="9fcff-106">*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="9fcff-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="9fcff-107">Windows Hello voor Bedrijven in Windows 10 Enterprise vervangt wachtwoorden met sterke tweeledige verificatie bij het ondertekenen op een Windows-apparaat.</span><span class="sxs-lookup"><span data-stu-id="9fcff-107">Windows Hello for Business in Windows 10 Enterprise replaces passwords with strong two-factor authentication when signing on a Windows device.</span></span> <span data-ttu-id="9fcff-108">De twee factoren zijn een nieuw type gebruikersreferentie dat is gekoppeld aan een apparaat en een biometrisch kenmerk of een pincode.</span><span class="sxs-lookup"><span data-stu-id="9fcff-108">The two factors are a new type of user credential that is tied to a device and a biometric or PIN.</span></span>

<span data-ttu-id="9fcff-109">Zie [Overzicht Windows Hello voor Bedrijven](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9fcff-109">For more information, see [Windows Hello for Business Overview](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span></span>


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a><span data-ttu-id="9fcff-110">Meervoudige verificatie instellen in Azure</span><span class="sxs-lookup"><span data-stu-id="9fcff-110">Set up Azure Multi-Factor Authentication</span></span>

<span data-ttu-id="9fcff-111">*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="9fcff-111">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="9fcff-112">In deze stap stelt u Azure MFA (Multi-Factor Authentication) in om een tweede beveiligingslaag toe te voegen aan gebruikersaanmeldingen en transacties.</span><span class="sxs-lookup"><span data-stu-id="9fcff-112">In this step, you'll set up Azure Multi-Factor Authentication (MFA) to add a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="9fcff-113">MFA vereist een aanvullende verificatiemethode nadat gebruikers hun wachtwoord correct hebben ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="9fcff-113">MFA requires an additional verification method after users have correctly entered their password.</span></span> <span data-ttu-id="9fcff-114">Zonder MFA is het wachtwoord de enige verificatiemethode.</span><span class="sxs-lookup"><span data-stu-id="9fcff-114">Without MFA, the password is the only verification method.</span></span> <span data-ttu-id="9fcff-115">Het probleem met wachtwoorden is dat veel ervan gemakkelijk kunnen worden geraden door een aanvaller of onbewust worden gedeeld met niet-vertrouwde partijen.</span><span class="sxs-lookup"><span data-stu-id="9fcff-115">The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="9fcff-116">Met MFA kan de tweede beveiligingslaag bestaan uit:</span><span class="sxs-lookup"><span data-stu-id="9fcff-116">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="9fcff-117">Een persoonlijk en vertrouwd apparaat dat niet eenvoudig kan worden vervalst of gedupliceerd, zoals een smartphone.</span><span class="sxs-lookup"><span data-stu-id="9fcff-117">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="9fcff-118">Een biometrisch kenmerk, zoals een vingerafdruk.</span><span class="sxs-lookup"><span data-stu-id="9fcff-118">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="9fcff-119">U schakelt MFA in en configureert de secundaire verificatiemethode met [beleid voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), waarmee u Azure Active Directory (Azure AD)-groepen kunt gebruiken om MFA uit te rollen naar bepaalde groepen gebruikers, zoals pilotgebruikers, geografische regio's of afdelingen.</span><span class="sxs-lookup"><span data-stu-id="9fcff-119">You'll enable MFA and configure the secondary authentication method with [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), which allow you to use Azure Active Directory (Azure AD) groups to roll out MFA to specified sets of users, such as pilot users, geographical regions, or departments.</span></span> <span data-ttu-id="9fcff-120">Zorg ervoor dat uw gebruikers weten dat MFA is ingeschakeld, zodat ze de vereisten begrijpen, zoals het verplichte gebruik van een smartphone om in te loggen, en ze met succes kunnen inloggen.</span><span class="sxs-lookup"><span data-stu-id="9fcff-120">Make sure to let your users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span> 

<span data-ttu-id="9fcff-121">Zie voor meer informatie [Een cloudgebaseerde implementatie van Azure Multi-Factor Authentication plannen](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span><span class="sxs-lookup"><span data-stu-id="9fcff-121">For more information, see [Planning a cloud-based Azure Multi-Factor Authentication deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="9fcff-123">Testlabrichtlijn: meervoudige verificatie in Azure</span><span class="sxs-lookup"><span data-stu-id="9fcff-123">Test Lab Guide: Azure Multi-Factor Authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="9fcff-124">Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-mfa) voor deze stap bekijken.</span><span class="sxs-lookup"><span data-stu-id="9fcff-124">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="9fcff-125">Bescherming tegen inbreuk op referenties</span><span class="sxs-lookup"><span data-stu-id="9fcff-125">Protect against credential compromise</span></span>

<span data-ttu-id="9fcff-126">*Dit is optioneel en geldt alleen voor de E5-versie van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="9fcff-126">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="9fcff-127">In dit gedeelte leert u hoe u beleidsregels configureert die bescherming bieden tegen inbreuken op referenties, waarbij een kwaadwillende gebruiker een aanval uitvoert op de accountnaam en wachtwoord van een gebruiker om toegang te krijgen tot de cloudservices en gegevens van een organisatie.</span><span class="sxs-lookup"><span data-stu-id="9fcff-127">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="9fcff-128">Azure AD Identity Protection biedt verschillende manieren om te voorkomen dat een kwaadwillende gebruiker de referenties van een gebruikersaccount in gevaar kan brengen.</span><span class="sxs-lookup"><span data-stu-id="9fcff-128">Azure AD Identity Protection provides a number of ways to help prevent an attacker from compromising a user account's credentials.</span></span>

<span data-ttu-id="9fcff-129">Met Azure AD Identity Protection kunt u:</span><span class="sxs-lookup"><span data-stu-id="9fcff-129">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="9fcff-130">Mogelijke beveiligingslekken in de identiteiten van uw organisatie vaststellen en verhelpen</span><span class="sxs-lookup"><span data-stu-id="9fcff-130">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="9fcff-131">Azure AD gebruikt machine learning om afwijkingen en verdachte activiteiten te detecteren, zoals aanmeldingen en activiteiten na aanmelding.</span><span class="sxs-lookup"><span data-stu-id="9fcff-131">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities.</span></span> <span data-ttu-id="9fcff-132">Met deze gegevens genereert Azure AD Identity Protection rapporten en waarschuwingen om u te helpen bij het evalueren van problemen en het ondernemen van actie. </span><span class="sxs-lookup"><span data-stu-id="9fcff-132">Using this data, Azure AD Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="9fcff-133">Verdachte acties opsporen die zijn gerelateerd aan de identiteiten van uw organisatie en automatisch op deze acties reageren</span><span class="sxs-lookup"><span data-stu-id="9fcff-133">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="9fcff-134">U kunt beleidsregels met betrekking tot risicobeheer zodanig configureren dat deze automatisch reageren op opgespoorde problemen als een bepaald risiconiveau is bereikt.</span><span class="sxs-lookup"><span data-stu-id="9fcff-134">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="9fcff-135">Met deze beleidsregels kunt u, naast andere besturingselementen voor voorwaardelijke toegang die worden geboden door Azure AD en Microsoft Intune, de toegang automatisch blokkeren of corrigerende acties ondernemen, waaronder wachtwoordherstel en vereiste meervoudige verificatie in Azure voor volgende aanmeldingen.</span><span class="sxs-lookup"><span data-stu-id="9fcff-135">These policies, in addition to other Conditional Access controls provided by Azure AD and Microsoft Intune, can either automatically block access or take corrective actions, including password resets and requiring Azure Multi-Factor Authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="9fcff-136">Verdachte incidenten onderzoeken en deze oplossen met beheertaken</span><span class="sxs-lookup"><span data-stu-id="9fcff-136">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="9fcff-137">U kunt risico gebeurtenissen onderzoeken door informatie over het beveiligingsincident te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9fcff-137">You can investigate risk events using information about the security incident.</span></span> <span data-ttu-id="9fcff-138">Er zijn eenvoudige werkstromen beschikbaar om onderzoek bij te houden en herstelbewerkingen uit te voeren, zoals het opnieuw instellen van wachtwoorden.</span><span class="sxs-lookup"><span data-stu-id="9fcff-138">Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="9fcff-139">Zie [meer informatie over Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span><span class="sxs-lookup"><span data-stu-id="9fcff-139">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="9fcff-140">Zie de [stappen voor het inschakelen van de Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="9fcff-140">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="9fcff-141">Het resultaat van deze stap is dat de Azure AD Identity Protection is ingeschakeld en u deze gebruikt voor het volgende:</span><span class="sxs-lookup"><span data-stu-id="9fcff-141">The results of this step are that you've enabled Azure AD Identity Protection and you are using it to:</span></span>

- <span data-ttu-id="9fcff-142">Mogelijke beveiligingslekken met een identiteit oplossen.</span><span class="sxs-lookup"><span data-stu-id="9fcff-142">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="9fcff-143">Mogelijke inbreuk op referenties op te sporen.</span><span class="sxs-lookup"><span data-stu-id="9fcff-143">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="9fcff-144">Het onderzoeken en adresseren van voortdurende verdachte identiteitsincidenten.</span><span class="sxs-lookup"><span data-stu-id="9fcff-144">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Labrichtlijnen testen voor de Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="9fcff-146">Testlabrichtlijnen: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="9fcff-146">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="9fcff-147">Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-ident-prot) voor dit gedeelte bekijken.</span><span class="sxs-lookup"><span data-stu-id="9fcff-147">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

|||
|:-------|:-----|
|![Stap 4](../media/stepnumbers/Step4.png)| [<span data-ttu-id="9fcff-149">Gebruikersaccounts toevoegen</span><span class="sxs-lookup"><span data-stu-id="9fcff-149">Add your user accounts</span></span>](identity-add-user-accounts.md) |
