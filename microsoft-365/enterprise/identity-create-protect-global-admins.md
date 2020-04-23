---
title: 'Stap 1: Uw globale beheerdersaccounts maken en beveiligen'
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
description: Uw globale beheerdersaccounts hebben een speciale behandeling nodig om ze te beschermen tegen inbreuk van referenties.
ms.openlocfilehash: c23a5730bc4c6af1f7fd829a40b63cc7ccc89184
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43621304"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a><span data-ttu-id="0700a-103">Stap 1: Uw globale beheerdersaccounts maken en beveiligen</span><span class="sxs-lookup"><span data-stu-id="0700a-103">Step 1: Create and protect your global admin accounts</span></span>

![Fase 2: Identiteit](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="0700a-105">Wereldwijde beheerdersaccounts beveiligen</span><span class="sxs-lookup"><span data-stu-id="0700a-105">Protect global administrator accounts</span></span>

<span data-ttu-id="0700a-106">*Dit is vereist en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="0700a-106">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="0700a-107">In deze sectie helpt u digitale aanvallen voorkomen op uw organisatie door ervoor te zorgen dat uw beheerdersaccounts zo veilig mogelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="0700a-107">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="0700a-108">Om dit te doen, moet u:</span><span class="sxs-lookup"><span data-stu-id="0700a-108">To do this, you must:</span></span>

- <span data-ttu-id="0700a-109">Meer dan één specifieke globale beheerdersaccount maken met [sterke wachtwoorden](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) en ze alleen gebruiken wanneer dat nodig is.</span><span class="sxs-lookup"><span data-stu-id="0700a-109">Create more than one dedicated global administrator accounts with [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="0700a-110">Dagelijks beheer uitvoeren door specifieke beheerdersrollen (zoals Exchange-beheerder of Wachtwoordbeheerder) toe te wijzen aan andere specifieke accounts voor die rollen of gebruikersaccounts van IT-medewerkers.</span><span class="sxs-lookup"><span data-stu-id="0700a-110">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to other dedicated accounts for those roles or user accounts of IT staff as needed.</span></span>

<span data-ttu-id="0700a-111">Voor uw specifieke globale beheerdersaccounts moet u ook:</span><span class="sxs-lookup"><span data-stu-id="0700a-111">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="0700a-112">Per gebruikersaccount testen of de Azure MFA-instellingen (Multi-Factor Authentication) voor voorwaardelijke toegang op een testgebruikersaccount testen om u ervan te verzekeren dat MFA correct en voorspelbaar werkt.</span><span class="sxs-lookup"><span data-stu-id="0700a-112">Test per-user account or Conditional Access-based Azure Multi-Factor Authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably.</span></span> <span data-ttu-id="0700a-113">MFA vereist een tweede vorm van verificatie, zoals een verificatiecode die naar een smartphone wordt gestuurd.</span><span class="sxs-lookup"><span data-stu-id="0700a-113">MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="0700a-114">Maak beleid voor voorwaardelijke toegang voor uw globale beheerdersaccounts dat MFA vereist, schakel dat in en gebruik de sterkste vorm van secundaire verificatie die beschikbaar is binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0700a-114">Create and enable a Conditional Access policy for your global administrator accounts that requires MFA and uses the strongest form of secondary authentication available in your organization.</span></span> <span data-ttu-id="0700a-115">Zie [Azure meervoudige verificatie](identity-access-prerequisites.md#protecting-administrator-accounts)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0700a-115">See [Azure Multi-Factor Authentication](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="0700a-116">Zie [Uw globale beheerdersaccount beveiligen](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations) voor aanvullende bescherming.</span><span class="sxs-lookup"><span data-stu-id="0700a-116">See [Protect your global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations) for additional protections.</span></span>

> [!Note]
> <span data-ttu-id="0700a-117">Noodtoegangsaccounts voor ‘break glass’-scenario’s, zoals een cyberaanval moeten cloudaccounts zijn.</span><span class="sxs-lookup"><span data-stu-id="0700a-117">Emergency accounts for break-glass scenarios in emergencies such as a cyberattack should be cloud-only accounts.</span></span> <span data-ttu-id="0700a-118">U kunt ook globale beheerdersaccounts (geschikt als of permanent) hebben die niet alleen in de cloud worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="0700a-118">You may also have global administrator accounts (eligible or permanent) that are not cloud-only.</span></span> <span data-ttu-id="0700a-119">Zie [Noodtoegangsaccounts beheren in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0700a-119">For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="0700a-120">De resultaten van deze sectie zijn:</span><span class="sxs-lookup"><span data-stu-id="0700a-120">The results of this section are:</span></span>

- <span data-ttu-id="0700a-121">De enige gebruikersaccounts in uw abonnement met de globale beheerdersrol, zijn de toegewezen globale beheerdersaccounts.</span><span class="sxs-lookup"><span data-stu-id="0700a-121">The only user accounts in your subscription that have the global admin role are the dedicated global administrator accounts.</span></span> <span data-ttu-id="0700a-122">Verifieer dit met de volgende Azure Active Directory PowerShell voor Graph-opdracht:</span><span class="sxs-lookup"><span data-stu-id="0700a-122">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```powershell
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="0700a-123">Aan alle andere gebruikersaccounts waarmee uw abonnementservices worden beheerd, zijn beheerdersrollen toegewezen die zijn gekoppeld aan de bijbehorende taakverantwoordelijkheden.</span><span class="sxs-lookup"><span data-stu-id="0700a-123">All other user accounts that manage your subscription services have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="0700a-124">Zie [Verbinding maken met Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) voor instructies over het installeren van de Azure Active Directory PowerShell for Graph-module en het aanmelden.</span><span class="sxs-lookup"><span data-stu-id="0700a-124">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="0700a-126">Zie de [Testlabrichtlijn globale beheerdersaccounts beschermen](protect-global-administrator-accounts-microsoft-365-test-environment.md) om deze configuratie in een testlab-omgeving te oefenen.</span><span class="sxs-lookup"><span data-stu-id="0700a-126">To practice this configuration in a test lab environment, see the [Protect global administrator accounts Test Lab Guide](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span></span> |
|||

<span data-ttu-id="0700a-127">Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-global-admin) voor deze stap bekijken.</span><span class="sxs-lookup"><span data-stu-id="0700a-127">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a><span data-ttu-id="0700a-128">Beheerders-op-aanvraag instellen</span><span class="sxs-lookup"><span data-stu-id="0700a-128">Set up on-demand administrators</span></span>

<span data-ttu-id="0700a-129">*Dit is optioneel en geldt alleen voor de E5-versie van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="0700a-129">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="0700a-130">In deze sectie stelt u de Azure Active Directory Privileged Identity Management (PIM) in om de tijd te verminderen dat uw beheerdersaccounts kwetsbaar zijn voor aanvallen door kwaadwillende gebruikers.</span><span class="sxs-lookup"><span data-stu-id="0700a-130">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="0700a-131">Met PIM kunt u op aanvraag een just-in-time-instructie van de beheerdersrollen inschakelen wanneer dat nodig is.</span><span class="sxs-lookup"><span data-stu-id="0700a-131">PIM provides on-demand, just-in-time assignment of the administrator roles when needed.</span></span>  

<span data-ttu-id="0700a-132">In plaats van dat uw beheerdersaccounts permanente beheerders zijn, worden ze in aanmerking komende beheerders.</span><span class="sxs-lookup"><span data-stu-id="0700a-132">Instead of your administrator accounts being permanent admins, they become eligible admins.</span></span> <span data-ttu-id="0700a-133">De beheerdersrol is inactief totdat iemand deze nodig heeft.</span><span class="sxs-lookup"><span data-stu-id="0700a-133">The administrator role is inactive until someone needs it.</span></span> <span data-ttu-id="0700a-134">Vervolgens voert u een activeringsprocedure uit om de beheerdersrol gedurende een bepaalde tijd toe te voegen aan het beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="0700a-134">You'll then complete an activation process to add the administrator role to the administrator account for a specific amount of time.</span></span> <span data-ttu-id="0700a-135">Als de tijd is verstreken, verwijdert PIM de beheerdersrol uit het beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="0700a-135">When the time expires, PIM removes the administrator role from the administrator account.</span></span>

<span data-ttu-id="0700a-136">PIM is beschikbaar met Azure Active Directory Premium P2, dat inbegrepen is bij Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="0700a-136">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 E5.</span></span> <span data-ttu-id="0700a-137">U kunt ook afzonderlijke Azure Active Directory Premium P2-licenties aanschaffen voor uw beheerdersaccounts.</span><span class="sxs-lookup"><span data-stu-id="0700a-137">Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your administrator accounts.</span></span>

<span data-ttu-id="0700a-138">Als u Azure PIM wilt inschakelen voor uw Azure Active Directory tenant -en beheerdersaccounts, raadpleegt u de [stappen voor het configureren van PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="0700a-138">To enable Azure PIM for your Azure AD tenant and administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="0700a-139">U kunt een uitgebreide roadmap ontwikkelen om bevoegde toegang te beveiligen tegen cyberaanvallers, zie [Bevoegde toegang voor hybride en cloudimplementaties in Azure Active Directory beveiligen](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="0700a-139">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="0700a-140">Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-pim) voor deze stap bekijken.</span><span class="sxs-lookup"><span data-stu-id="0700a-140">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a><span data-ttu-id="0700a-141">Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="0700a-141">Privileged access management</span></span>

<span data-ttu-id="0700a-142">Geprivilegieerd toegangsbeheer wordt ingeschakeld door beleid te configureren dat just-in-time-toegang specificeert voor taakactiviteiten in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="0700a-142">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your tenant.</span></span> <span data-ttu-id="0700a-143">Deze functie kan helpen uw organisatie te beschermen tegen inbreuken die mogelijk bestaande geprivilegieerde beheerdersaccounts gebruiken met permanente toegang tot gevoelige gegevens of toegang tot belangrijker configuratie-instellingen.</span><span class="sxs-lookup"><span data-stu-id="0700a-143">It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="0700a-144">U kunt bijvoorbeeld geprivilegieerd toegangsbeheerbeleid configureren dat expliciete goedkeuring vereist voor toegang tot en het wijzigen van postvakinstellingen van de organisatie in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="0700a-144">For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your tenant.</span></span>

<span data-ttu-id="0700a-145">In deze stap schakelt u geprivilegieerd toegangsbeheer in uw tenant in en configureert u geprivilegieerd toegangsbeleid dat aanvullende bescherming biedt voor taaktoegang tot gegevens en configuratie-instellingen voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0700a-145">In this step, you'll enable privileged access management in your tenant and configure privileged access policies that provide additional security for task-based access to data and configuration settings for your organization.</span></span> <span data-ttu-id="0700a-146">Er zijn drie basisstappen om aan de slag te gaan met geprivilegieerde toegang in uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="0700a-146">There are three basic steps to get started with privileged access in your organization:</span></span>

- <span data-ttu-id="0700a-147">Een groep met fiatteurs maken</span><span class="sxs-lookup"><span data-stu-id="0700a-147">Creating an approver's group</span></span>
- <span data-ttu-id="0700a-148">Geprivilegieerde toegang inschakelen</span><span class="sxs-lookup"><span data-stu-id="0700a-148">Enabling privileged access</span></span>
- <span data-ttu-id="0700a-149">Goedkeuringsbeleid maken</span><span class="sxs-lookup"><span data-stu-id="0700a-149">Creating approval policies</span></span>

<span data-ttu-id="0700a-150">Als geprivilegieerd toegangsbeheer is geconfigureerd, kan uw organisatie opereren zonder permanente bevoegdheden en een verdedigingslaag bieden tegen kwetsbaarheden die voortkomen uit dergelijke permanente beheerderstoegang.</span><span class="sxs-lookup"><span data-stu-id="0700a-150">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access.</span></span> <span data-ttu-id="0700a-151">Geprivilegieerde toegang vereist goedkeuring voor het uitvoeren van taken met een bijbehorend goedkeuringsbeleid.</span><span class="sxs-lookup"><span data-stu-id="0700a-151">Privileged access requires approvals for executing any task that has an associated approval policy defined.</span></span> <span data-ttu-id="0700a-152">Gebruikers die taken moeten uitvoeren die zijn opgenomen in het goedkeuringsbeleid, moeten toestemming voor toegang aanvragen en krijgen om de machtigingen te krijgen die nodig zijn om de taken, die zijn gedefinieerd in het beleid, uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="0700a-152">Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="0700a-153">Zie het onderwerp [Geprivilegieerd toegangsbeheer configureren](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) om Privileged Access Management in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="0700a-153">To enable privileged access management, see the [Configure privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="0700a-154">Zie het onderwerp [Geprivilegieerd toegangsbeheer](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0700a-154">For more information, see the [Privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="0700a-156">Zie de [Testlabrichtlijn geprivilegieerd toegangsbeheer](privileged-access-microsoft-365-enterprise-dev-test-environment.md) om deze configuratie in een testlab-omgeving te oefenen.</span><span class="sxs-lookup"><span data-stu-id="0700a-156">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="0700a-157">Zie de [afsluitcriteria](identity-exit-criteria.md#crit-identity-pam) voor deze stap als tussentijds controlepunt.</span><span class="sxs-lookup"><span data-stu-id="0700a-157">As an interim checkpoint, see the [exit criteria](identity-exit-criteria.md#crit-identity-pam) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="0700a-158">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="0700a-158">Next step</span></span>

|||
|:-------|:-----|
|![Stap 2](../media/stepnumbers/Step2.png)| [<span data-ttu-id="0700a-160">Wachtwoorden beveiligen</span><span class="sxs-lookup"><span data-stu-id="0700a-160">Secure your passwords</span></span>](identity-secure-your-passwords.md) |

