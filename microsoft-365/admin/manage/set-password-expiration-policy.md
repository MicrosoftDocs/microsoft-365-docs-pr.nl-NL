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
description: Informatie over het instellen van een verloopbeleid voor wachtwoorden voor uw bedrijf in het Microsoft 365-beheercentrum.
ms.openlocfilehash: 74b23b4a1b67ecd5c9199388985e8e38c3231239
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2021
ms.locfileid: "51221821"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="52d92-103">Het wachtwoordverloopbeleid voor uw organisatie instellen:</span><span class="sxs-lookup"><span data-stu-id="52d92-103">Set the password expiration policy for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="52d92-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="52d92-104">The admin center is changing.</span></span> <span data-ttu-id="52d92-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](../microsoft-365-admin-center-preview.md?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="52d92-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?view=o365-worldwide).</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="52d92-106">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="52d92-106">Before you begin</span></span>

<span data-ttu-id="52d92-107">Dit artikel is bedoeld voor personen die het wachtwoordverloopbeleid voor een bedrijf, school of non-profitorganisatie opstellen.</span><span class="sxs-lookup"><span data-stu-id="52d92-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="52d92-108">Voor het uitvoeren van deze stappen moet u zich aanmelden met uw Microsoft 365-beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="52d92-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="52d92-109">[Wat is een beheerdersaccount?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview).</span><span class="sxs-lookup"><span data-stu-id="52d92-109">[What's an admin account?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview).</span></span>

<span data-ttu-id="52d92-110">Je moet een [globale beheerder](../add-users/about-admin-roles.md) zijn om deze stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="52d92-110">You must be a [global admin](../add-users/about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="52d92-111">Als u een gebruiker bent, bent u niet gemachtigd om uw wachtwoord zo in te stellen dat het nooit verloopt.</span><span class="sxs-lookup"><span data-stu-id="52d92-111">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="52d92-112">Vraag de technische ondersteuning van uw werk of school om de stappen in dit artikel voor u uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="52d92-112">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="52d92-113">Als beheerder kunt u instellen dat gebruikerswachtwoorden na een bepaald aantal dagen verlopen of dat deze nooit verlopen.</span><span class="sxs-lookup"><span data-stu-id="52d92-113">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span>

## <a name="set-password-expiration-policy"></a><span data-ttu-id="52d92-114">Wachtwoordverloopbeleid instellen</span><span class="sxs-lookup"><span data-stu-id="52d92-114">Set password expiration policy</span></span>

> [!Tip]
> <span data-ttu-id="52d92-115">Wachtwoorden verlopen standaard na 90 dagen.</span><span class="sxs-lookup"><span data-stu-id="52d92-115">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="52d92-116">Recent onderzoek geeft sterk aan dat verplichte wachtwoordwijzigingen meer kwaad dan goed doen.</span><span class="sxs-lookup"><span data-stu-id="52d92-116">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="52d92-117">Gebruikers kiezen dan voor zwakkere wachtwoorden, hergebruik van wachtwoorden of ze werken oude wachtwoorden bij op een manier die eenvoudig te raden is voor hackers.</span><span class="sxs-lookup"><span data-stu-id="52d92-117">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="52d92-118">Als u de wachtwoorden instelt om nooit te verlopen, raden we u aan [meervoudige verificatie](../security-and-compliance/set-up-multi-factor-authentication.md) in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="52d92-118">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="52d92-119">Volg onderstaande stappen als u wilt instellen dat gebruikerswachtwoorden na een bepaalde tijd verlopen.</span><span class="sxs-lookup"><span data-stu-id="52d92-119">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>

1. <span data-ttu-id="52d92-120">Ga in het beheercentrum naar **Instellingen** \> **Organisatie-instellingen**.</span><span class="sxs-lookup"><span data-stu-id="52d92-120">In the admin center, go to the **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="52d92-121">Ga naar de pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Beveiliging en privacy</a>.</span><span class="sxs-lookup"><span data-stu-id="52d92-121">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="52d92-122">Als u geen globale beheerder bent, ziet u de optie Beveiliging en privacy niet.</span><span class="sxs-lookup"><span data-stu-id="52d92-122">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="52d92-123">Selecteer **Verloopbeleid wachtwoorden**.</span><span class="sxs-lookup"><span data-stu-id="52d92-123">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="52d92-124">Als u niet wilt dat gebruikers hun wachtwoorden moeten wijzigen, deselecteert u het selectievakje naast **Gebruikerswachtwoorden instellen om na een aantal dagen te verlopen**.</span><span class="sxs-lookup"><span data-stu-id="52d92-124">If you don't want users to have to change passwords, uncheck the box next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="52d92-125">Geef op hoe vaak wachtwoorden moeten verlopen.</span><span class="sxs-lookup"><span data-stu-id="52d92-125">Type how often passwords should expire.</span></span> <span data-ttu-id="52d92-126">Kies een aantal dagen tussen 14 en 730.</span><span class="sxs-lookup"><span data-stu-id="52d92-126">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="52d92-127">Geef in het tweede vak op wanneer gebruikers een melding ontvangen over het verlopen van het wachtwoord en selecteer vervolgens **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="52d92-127">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="52d92-128">Kies een aantal dagen tussen 1 en 30.</span><span class="sxs-lookup"><span data-stu-id="52d92-128">Choose a number of days from 1 to 30.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="52d92-129">Belangrijke dingen die u moet weten over de functie voor verlopen wachtwoorden</span><span class="sxs-lookup"><span data-stu-id="52d92-129">Important things you need to know about the password expiration feature</span></span>
  
- <span data-ttu-id="52d92-p108">Personen die alleen gebruikmaken van de Outlook-app worden niet gedwongen hun Microsoft 365-beheerderswachtwoord opnieuw in te stellen voordat het in de cache is verlopen. Dit kan enkele dagen na de feitelijke verloopdatum in beslag nemen. Op beheerdersniveau is er geen tijdelijke oplossing voor dit probleem.</span><span class="sxs-lookup"><span data-stu-id="52d92-p108">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>

## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="52d92-133">Voorkomen dat laatste wachtwoord opnieuw wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="52d92-133">Prevent last password from being used again</span></span>

<span data-ttu-id="52d92-134">Als u wilt voorkomen dat uw gebruikers oude wachtwoorden opnieuw gebruiken, kunt u dit doen door Wachtwoordgeschiedenis afdwingen in te stellen in on-premises Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="52d92-134">If you want to prevent your users from recycling old passwords, you can do so by enforcing password history in on-premises Active Directory (AD).</span></span> <span data-ttu-id="52d92-135">Raadpleeg [Een aangepast wachtwoordbeleid aanmaken](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span><span class="sxs-lookup"><span data-stu-id="52d92-135">See [Create a custom password policy](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span></span>

<span data-ttu-id="52d92-136">In Azure AD kan het laatste wachtwoord niet opnieuw worden gebruikt als de gebruiker een wachtwoord wijzigt.</span><span class="sxs-lookup"><span data-stu-id="52d92-136">In Azure AD, The last password can't be used again when the user changes a password.</span></span> <span data-ttu-id="52d92-137">Het wachtwoordbeleid wordt toegepast op alle gebruikersaccounts die rechtstreeks in Azure AD worden aangemaakt en beheerd.</span><span class="sxs-lookup"><span data-stu-id="52d92-137">The password policy is applied to all user accounts that are created and managed directly in Azure AD.</span></span> <span data-ttu-id="52d92-138">Dit wachtwoordbeleid kan niet worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="52d92-138">This password policy can't be modified.</span></span> <span data-ttu-id="52d92-139">Raadpleeg [Azure AD-wachtwoordbeleid](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span><span class="sxs-lookup"><span data-stu-id="52d92-139">See [Azure AD password policies](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span></span>

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="52d92-140">Gebruikerswachtwoordhashes synchroniseren vanuit een on-premises Active Directory naar Azure AD (Microsoft 365) </span><span class="sxs-lookup"><span data-stu-id="52d92-140">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="52d92-141">Dit artikel gaat over het instellen van het vervalbeleid voor gebruikers die alleen de cloud gebruiken (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="52d92-141">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="52d92-142">Dit geldt niet voor hybride-identiteitsgebruikers die gebruikmaken van wachtwoordhashsynchronisatie, Pass Through-verificatie of on-premises federatie, zoals ADFS.</span><span class="sxs-lookup"><span data-stu-id="52d92-142">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication, or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="52d92-143">Zie [Wachtwoordhashsynchronisatie met Azure AD Connect-synchronisatie implementeren](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) voor informatie over het synchroniseren van gebruikerswachtwoordhashes in een on-premises AD met gebruikerswachtwoordhashes in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="52d92-143">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a><span data-ttu-id="52d92-144">Wachtwoordbeleid en accountbeperkingen in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="52d92-144">Password policies and account restrictions in Azure Active Directory</span></span>

<span data-ttu-id="52d92-145">U kunt meer wachtwoordbeleidsregels en beperkingen in Azure Active Directory instellen.</span><span class="sxs-lookup"><span data-stu-id="52d92-145">You can set more password policies and restrictions in Azure active directory.</span></span> <span data-ttu-id="52d92-146">Voor meer informatie, gaat u naar [Wachtwoordbeleid en accountbeperkingen in Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy).</span><span class="sxs-lookup"><span data-stu-id="52d92-146">Check out [Password policies and account restrictions in Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy) for more info.</span></span>

## <a name="update-password-policy"></a><span data-ttu-id="52d92-147">Wachtwoordbeleid bijwerken</span><span class="sxs-lookup"><span data-stu-id="52d92-147">Update password Policy</span></span>

<span data-ttu-id="52d92-148">Met de cmdlet Set-MsolPasswordPolicy wordt het wachtwoordbeleid van een opgegeven domein of tenant bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="52d92-148">The Set-MsolPasswordPolicy cmdlet updates the password policy of a specified domain or tenant.</span></span> <span data-ttu-id="52d92-149">Er zijn twee instellingen vereist. De eerste is om aan te geven hoe lang een wachtwoord geldig mag blijven voordat het moet worden gewijzigd en de tweede is om het aantal dagen aan te geven tot de vervaldatum van het wachtwoord, wat de eerste melding activeert die gebruikers ontvangen en hen vertelt dat het wachtwoord binnenkort vervalt.</span><span class="sxs-lookup"><span data-stu-id="52d92-149">Two settings are required; the first is to indicate the length of time that a password remains valid before it must be changed and the second is to indicate the number of days before the password expiration date that will trigger when users will receive their first notification that their password will soon expire.</span></span>

<span data-ttu-id="52d92-150">Voor meer informatie over het bijwerken van wachtwoordbeleid voor een specifiek domein of tenant, raadpleegt u [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="52d92-150">To learn how to update password policy for a specific domain or tenant, see [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span></span>

## <a name="related-content"></a><span data-ttu-id="52d92-151">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="52d92-151">Related content</span></span>

[<span data-ttu-id="52d92-152">Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen</span><span class="sxs-lookup"><span data-stu-id="52d92-152">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="52d92-153">Wachtwoorden opnieuw instellen</span><span class="sxs-lookup"><span data-stu-id="52d92-153">Reset passwords</span></span>](../add-users/reset-passwords.md)