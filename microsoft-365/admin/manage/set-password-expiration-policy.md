---
title: 'Het wachtwoordverloopbeleid voor uw organisatie instellen:'
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: Lees hoe een beheerder een wachtwoordverloopbeleid kan instellen voor uw bedrijf, school of non-profitorganisatie in het Microsoft 365-beheercentrum.
ms.openlocfilehash: fdd219e4fc99e2388acb5b19eacb2fc470041f79
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286727"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="f5cc9-103">Het wachtwoordverloopbeleid voor uw organisatie instellen</span><span class="sxs-lookup"><span data-stu-id="f5cc9-103">Set the password expiration policy for your organization</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f5cc9-104">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="f5cc9-104">Before you begin</span></span>

<span data-ttu-id="f5cc9-105">Dit artikel is bedoeld voor personen die het wachtwoordverloopbeleid voor een bedrijf, school of non-profitorganisatie opstellen.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-105">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="f5cc9-106">Voor het uitvoeren van deze stappen moet u zich aanmelden met uw Microsoft 365-beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-106">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="f5cc9-107">[Wat is een beheerdersaccount?](../../business-video/admin-center-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f5cc9-107">[What's an admin account?](../../business-video/admin-center-overview.md).</span></span>

<span data-ttu-id="f5cc9-p102">Als beheerder kunt u instellen dat gebruikerswachtwoorden na een bepaald aantal dagen verlopen of dat deze nooit verlopen. De standaardinstelling is dat wachtwoorden nooit verlopen voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-p102">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire. By default, passwords are set to never expire for your organization.</span></span>

<span data-ttu-id="f5cc9-110">Recent onderzoek geeft sterk aan dat verplichte wachtwoordwijzigingen meer kwaad dan goed doen.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-110">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="f5cc9-111">Gebruikers kiezen dan voor zwakkere wachtwoorden, hergebruik van wachtwoorden of ze werken oude wachtwoorden bij op een manier die eenvoudig te raden is voor hackers.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-111">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="f5cc9-112">Het is raadzaam om [meervoudige verificatie](../security-and-compliance/set-up-multi-factor-authentication.md) in te stellen.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-112">We recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span> <span data-ttu-id="f5cc9-113">Voor meer informatie over wachtwoordbeleid raadpleegt u [Aanbevelingen voor wachtwoordbeleid](../misc/password-policy-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="f5cc9-113">To learn more about password policy, check out [Password policy recommendations](../misc/password-policy-recommendations.md).</span></span>

<span data-ttu-id="f5cc9-114">Je moet een [globale beheerder](../add-users/about-admin-roles.md) zijn om deze stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-114">You must be a [global admin](../add-users/about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="f5cc9-p104">Als u een gebruiker bent, bent u niet gemachtigd om uw wachtwoord zo in te stellen dat het nooit verloopt. Vraag de technische ondersteuning van uw werk of school om de stappen in dit artikel voor u uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-p104">If you're a user, you don't have the permissions to set your password to never expire. Ask your work or school technical support to do the steps in this article for you.</span></span>

## <a name="set-password-expiration-policy"></a><span data-ttu-id="f5cc9-117">Wachtwoordverloopbeleid instellen</span><span class="sxs-lookup"><span data-stu-id="f5cc9-117">Set password expiration policy</span></span>

<span data-ttu-id="f5cc9-118">Volg onderstaande stappen als u wilt instellen dat gebruikerswachtwoorden na een bepaalde tijd verlopen.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-118">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>

1. <span data-ttu-id="f5cc9-119">Ga in het beheercentrum naar **Instellingen** \> **Organisatie-instellingen**.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-119">In the admin center, go to the **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="f5cc9-120">Ga naar de pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Beveiliging en privacy</a>.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="f5cc9-121">Als u geen globale beheerder bent, ziet u de optie Beveiliging en privacy niet.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-121">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="f5cc9-122">Selecteer **Verloopbeleid wachtwoorden**.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-122">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="f5cc9-123">Als u niet wilt dat gebruikers hun wachtwoorden moeten wijzigen, deselecteert u het selectievakje naast **Gebruikerswachtwoorden instellen om na een aantal dagen te verlopen**.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-123">If you don't want users to have to change passwords, uncheck the box next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="f5cc9-p106">Typ hoe vaak wachtwoorden moeten verlopen. Kies een aantal dagen tussen de 14 en 730.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-p106">Type how often passwords should expire. Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="f5cc9-126">Geef in het tweede vak op wanneer gebruikers een melding ontvangen over het verlopen van het wachtwoord en selecteer vervolgens **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-126">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="f5cc9-127">Kies een aantal dagen tussen 1 en 30.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-127">Choose a number of days from 1 to 30.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="f5cc9-128">Belangrijke dingen die u moet weten over de functie voor verlopen wachtwoorden</span><span class="sxs-lookup"><span data-stu-id="f5cc9-128">Important things you need to know about the password expiration feature</span></span>
  
<span data-ttu-id="f5cc9-p108">Personen die alleen gebruikmaken van de Outlook-app worden niet gedwongen hun Microsoft 365-beheerderswachtwoord opnieuw in te stellen voordat het in de cache is verlopen. Dit kan enkele dagen na de feitelijke verloopdatum in beslag nemen. Op beheerdersniveau is er geen tijdelijke oplossing voor dit probleem.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-p108">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>

## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="f5cc9-132">Voorkomen dat laatste wachtwoord opnieuw wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="f5cc9-132">Prevent last password from being used again</span></span>

<span data-ttu-id="f5cc9-133">Als u wilt voorkomen dat uw gebruikers oude wachtwoorden opnieuw gebruiken, kunt u dit doen door Wachtwoordgeschiedenis afdwingen in te stellen in on-premises Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="f5cc9-133">If you want to prevent your users from recycling old passwords, you can do so by enforcing password history in on-premises Active Directory (AD).</span></span> <span data-ttu-id="f5cc9-134">Raadpleeg [Een aangepast wachtwoordbeleid aanmaken](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span><span class="sxs-lookup"><span data-stu-id="f5cc9-134">See [Create a custom password policy](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span></span>

<span data-ttu-id="f5cc9-135">In Azure AD kan het laatste wachtwoord niet opnieuw worden gebruikt als de gebruiker een wachtwoord wijzigt.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-135">In Azure AD, The last password can't be used again when the user changes a password.</span></span> <span data-ttu-id="f5cc9-136">Het wachtwoordbeleid wordt toegepast op alle gebruikersaccounts die rechtstreeks in Azure AD worden aangemaakt en beheerd.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-136">The password policy is applied to all user accounts that are created and managed directly in Azure AD.</span></span> <span data-ttu-id="f5cc9-137">Dit wachtwoordbeleid kan niet worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-137">This password policy can't be modified.</span></span> <span data-ttu-id="f5cc9-138">Raadpleeg [Azure AD-wachtwoordbeleid](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span><span class="sxs-lookup"><span data-stu-id="f5cc9-138">See [Azure AD password policies](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span></span>

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="f5cc9-139">Gebruikerswachtwoordhashes synchroniseren vanuit een on-premises Active Directory naar Azure AD (Microsoft 365) </span><span class="sxs-lookup"><span data-stu-id="f5cc9-139">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="f5cc9-p111">Dit artikel gaat over het instellen van het verloopbeleid voor gebruikers die alleen de cloud gebruiken (Azure AD). Dit geldt niet voor hybride-identiteitsgebruikers die gebruikmaken van wachtwoordhashsynchronisatie, passthrough-verificatie of on-premises federatie, zoals ADFS.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-p111">This article is for setting the expiration policy for cloud-only users (Azure AD). It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication, or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="f5cc9-142">Zie [Wachtwoordhashsynchronisatie met Azure AD Connect-synchronisatie implementeren](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) voor informatie over het synchroniseren van gebruikerswachtwoordhashes in een on-premises AD met gebruikerswachtwoordhashes in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-142">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a><span data-ttu-id="f5cc9-143">Wachtwoordbeleid en accountbeperkingen in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-143">Password policies and account restrictions in Azure Active Directory</span></span>

<span data-ttu-id="f5cc9-144">U kunt meer wachtwoordbeleidsregels en beperkingen in Azure Active Directory instellen.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-144">You can set more password policies and restrictions in Azure active directory.</span></span> <span data-ttu-id="f5cc9-145">Voor meer informatie, gaat u naar [Wachtwoordbeleid en accountbeperkingen in Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy).</span><span class="sxs-lookup"><span data-stu-id="f5cc9-145">Check out [Password policies and account restrictions in Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy) for more info.</span></span>

## <a name="update-password-policy"></a><span data-ttu-id="f5cc9-146">Wachtwoordbeleid bijwerken</span><span class="sxs-lookup"><span data-stu-id="f5cc9-146">Update password Policy</span></span>

<span data-ttu-id="f5cc9-p113">De cmdlet Set-MsolPasswordPolicy werkt het wachtwoordbeleid bij van een opgegeven domein of tenant. Er zijn twee instellingen vereist; de eerste is om aan te geven hoe lang een wachtwoord geldig mag blijven voordat het moet worden gewijzigd en de tweede is om het aantal dagen aan te geven tot de verloopdatum van het wachtwoord, wat de eerste melding activeert die gebruikers ontvangen en hen vertelt dat het wachtwoord binnenkort vervalt.</span><span class="sxs-lookup"><span data-stu-id="f5cc9-p113">The Set-MsolPasswordPolicy cmdlet updates the password policy of a specified domain or tenant. Two settings are required; the first is to indicate the length of time that a password remains valid before it must be changed and the second is to indicate the number of days before the password expiration date that will trigger when users will receive their first notification that their password will soon expire.</span></span>

<span data-ttu-id="f5cc9-149">Voor meer informatie over het bijwerken van wachtwoordbeleid voor een specifiek domein of tenant, raadpleegt u [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy).</span><span class="sxs-lookup"><span data-stu-id="f5cc9-149">To learn how to update password policy for a specific domain or tenant, see [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy).</span></span>

## <a name="related-content"></a><span data-ttu-id="f5cc9-150">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f5cc9-150">Related content</span></span>

<span data-ttu-id="f5cc9-151">[Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen](../add-users/let-users-reset-passwords.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="f5cc9-151">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>\

<span data-ttu-id="f5cc9-152">[Wachtwoorden opnieuw instellen](../add-users/reset-passwords.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="f5cc9-152">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>
