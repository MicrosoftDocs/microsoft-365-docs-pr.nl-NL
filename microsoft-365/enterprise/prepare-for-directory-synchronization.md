---
title: Directory-synchronisatie voorbereiden op Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: In dit artikel wordt uitgelegd hoe u gebruikers kunt inrichten voor Microsoft 365 met behulp van adreslijstsynchronisatie en de lange termijn voordelen van het gebruik van deze methode.
ms.openlocfilehash: 41c2ff08c8e2ae11079e82d378110d10bd7cab3e
ms.sourcegitcommit: bcb88a6171f9e7bdb5b2d8c03cd628d11c5e7bbf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464238"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a><span data-ttu-id="2dee1-103">Directory-synchronisatie voorbereiden op Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2dee1-103">Prepare for directory synchronization to Microsoft 365</span></span>

<span data-ttu-id="2dee1-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="2dee1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2dee1-105">De voordelen van Hybrid Identity en adreslijstsynchronisatie uw organisatie omvat:</span><span class="sxs-lookup"><span data-stu-id="2dee1-105">The benefits to hybrid identity and directory synchronization your organization include:</span></span>

- <span data-ttu-id="2dee1-106">De beheerprogramma's in uw organisatie verminderen</span><span class="sxs-lookup"><span data-stu-id="2dee1-106">Reducing the administrative programs in your organization</span></span>
- <span data-ttu-id="2dee1-107">Optioneel scenario voor eenmalige aanmelding inschakelen</span><span class="sxs-lookup"><span data-stu-id="2dee1-107">Optionally enabling single sign-on scenario</span></span>
- <span data-ttu-id="2dee1-108">Account wijzigingen automatiseren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2dee1-108">Automating account changes in Microsoft 365</span></span>

<span data-ttu-id="2dee1-109">Zie voor meer informatie over de voordelen van het gebruik van adreslijstsynchronisatie [Hybrid Identity with Azure Active Directory (Azure AD)](https://go.microsoft.com/fwlink/p/?LinkId=525398) en [Hybrid Identity voor Microsoft 365](plan-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="2dee1-109">For more information about the advantages of using directory synchronization, see [hybrid identity with Azure Active Directory (Azure AD)](https://go.microsoft.com/fwlink/p/?LinkId=525398) and [hybrid identity for Microsoft 365](plan-for-directory-synchronization.md).</span></span>

<span data-ttu-id="2dee1-110">Adreslijstsynchronisatie vereist echter planning en voorbereidingen om ervoor te zorgen dat uw Active Directory Domain Services (AD DS) wordt gesynchroniseerd met de Azure AD-Tenant van uw Microsoft 365-abonnement met een minimum aan fouten.</span><span class="sxs-lookup"><span data-stu-id="2dee1-110">However, directory synchronization requires planning and preparation to ensure that your Active Directory Domain Services (AD DS) synchronizes to the Azure AD tenant of your Microsoft 365 subscription with a minimum of errors.</span></span>

<span data-ttu-id="2dee1-111">Voer de volgende stappen uit om de beste resultaten te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="2dee1-111">Follow these steps in order for the best results.</span></span>

## <a name="1-directory-cleanup-tasks"></a><span data-ttu-id="2dee1-112">1. taken in de Directory opschonen</span><span class="sxs-lookup"><span data-stu-id="2dee1-112">1. Directory cleanup tasks</span></span>

<span data-ttu-id="2dee1-113">Voordat u de AD DS synchroniseert met een Azure AD-Tenant, moet u de AD DS opschonen.</span><span class="sxs-lookup"><span data-stu-id="2dee1-113">Before you synchronize your AD DS to your Azure AD tenant, you need to clean up your AD DS.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2dee1-114">Als u AD DS cleanup niet uitvoert voordat u synchroniseert, kan dit leiden tot een significante negatieve impact op het implementatieproces.</span><span class="sxs-lookup"><span data-stu-id="2dee1-114">If you don't perform AD DS cleanup before you synchronize, it can lead to a significant negative impact on the deployment process.</span></span> <span data-ttu-id="2dee1-115">Het kan dagen duren voor de adreslijstsynchronisatie, het identificeren van fouten en het opnieuw synchroniseren van een week.</span><span class="sxs-lookup"><span data-stu-id="2dee1-115">It might take days, or even weeks, to go through the cycle of directory synchronization, identifying errors, and re-synchronization.</span></span>

<span data-ttu-id="2dee1-116">Voer in uw AD DS de volgende opschoningstaken uit voor elk gebruikersaccount waaraan een Microsoft 365-licentie is toegewezen:</span><span class="sxs-lookup"><span data-stu-id="2dee1-116">In your AD DS, complete the following clean-up tasks for each user account that will be assigned a Microsoft 365 license:</span></span>

1. <span data-ttu-id="2dee1-117">Zorg voor een geldig en uniek e-mailadres in het **proxyAddresses** -kenmerk.</span><span class="sxs-lookup"><span data-stu-id="2dee1-117">Ensure a valid and unique email address in the **proxyAddresses** attribute.</span></span>

2. <span data-ttu-id="2dee1-118">Verwijder alle dubbele waarden in het kenmerk **proxyAddresses** .</span><span class="sxs-lookup"><span data-stu-id="2dee1-118">Remove any duplicate values in the **proxyAddresses** attribute.</span></span>

3. <span data-ttu-id="2dee1-119">Controleer indien mogelijk een geldige en unieke waarde voor het kenmerk **userPrincipalName** in het **gebruikers** object van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="2dee1-119">If possible, ensure a valid and unique value for the **userPrincipalName** attribute in the user's **user** object.</span></span> <span data-ttu-id="2dee1-120">Voor de beste synchronisatie ervaring zorgt u ervoor dat de AD DS-UPN overeenkomt met de Azure AD-UPN.</span><span class="sxs-lookup"><span data-stu-id="2dee1-120">For the best synchronization experience, ensure that the AD DS UPN matches the Azure AD UPN.</span></span> <span data-ttu-id="2dee1-121">Als een gebruiker geen waarde heeft voor het kenmerk **userPrincipalName** , moet het **gebruikers** object een geldige en unieke waarde voor het kenmerk **sAMAccountName** bevatten.</span><span class="sxs-lookup"><span data-stu-id="2dee1-121">If a user does not have a value for the **userPrincipalName** attribute, then the **user** object must contain a valid and unique value for the **sAMAccountName** attribute.</span></span> <span data-ttu-id="2dee1-122">Verwijder alle dubbele waarden in het kenmerk **userPrincipalName** .</span><span class="sxs-lookup"><span data-stu-id="2dee1-122">Remove any duplicate values in the **userPrincipalName** attribute.</span></span>

4. <span data-ttu-id="2dee1-123">Voor optimaal gebruik van de algemene adreslijst (GAL) zorgt u ervoor dat de informatie in de volgende kenmerken van het AD DS-gebruikersaccount correct is:</span><span class="sxs-lookup"><span data-stu-id="2dee1-123">For optimal use of the global address list (GAL), ensure the information in the following attributes of the AD DS user account is correct:</span></span>

   - <span data-ttu-id="2dee1-124">voor benaming</span><span class="sxs-lookup"><span data-stu-id="2dee1-124">givenName</span></span>
   - <span data-ttu-id="2dee1-125">achternaam</span><span class="sxs-lookup"><span data-stu-id="2dee1-125">surname</span></span>
   - <span data-ttu-id="2dee1-126">displayName</span><span class="sxs-lookup"><span data-stu-id="2dee1-126">displayName</span></span>
   - <span data-ttu-id="2dee1-127">Functie</span><span class="sxs-lookup"><span data-stu-id="2dee1-127">Job Title</span></span>
   - <span data-ttu-id="2dee1-128">Department</span><span class="sxs-lookup"><span data-stu-id="2dee1-128">Department</span></span>
   - <span data-ttu-id="2dee1-129">Office</span><span class="sxs-lookup"><span data-stu-id="2dee1-129">Office</span></span>
   - <span data-ttu-id="2dee1-130">Zakelijk nummer</span><span class="sxs-lookup"><span data-stu-id="2dee1-130">Office Phone</span></span>
   - <span data-ttu-id="2dee1-131">Mobiel nummer</span><span class="sxs-lookup"><span data-stu-id="2dee1-131">Mobile Phone</span></span>
   - <span data-ttu-id="2dee1-132">Faxnummer</span><span class="sxs-lookup"><span data-stu-id="2dee1-132">Fax Number</span></span>
   - <span data-ttu-id="2dee1-133">Adres</span><span class="sxs-lookup"><span data-stu-id="2dee1-133">Street Address</span></span>
   - <span data-ttu-id="2dee1-134">Plaats</span><span class="sxs-lookup"><span data-stu-id="2dee1-134">City</span></span>
   - <span data-ttu-id="2dee1-135">Provincie</span><span class="sxs-lookup"><span data-stu-id="2dee1-135">State or Province</span></span>
   - <span data-ttu-id="2dee1-136">Post code</span><span class="sxs-lookup"><span data-stu-id="2dee1-136">Zip or Postal Code</span></span>
   - <span data-ttu-id="2dee1-137">Land of regio</span><span class="sxs-lookup"><span data-stu-id="2dee1-137">Country or Region</span></span>

## <a name="2-directory-object-and-attribute-preparation"></a><span data-ttu-id="2dee1-138">2. mapobject en kenmerk voorbereiding</span><span class="sxs-lookup"><span data-stu-id="2dee1-138">2. Directory object and attribute preparation</span></span>

<span data-ttu-id="2dee1-139">Als u wilt dat de adreslijstsynchronisatie mislukt tussen uw Active Directory-en Microsoft 365, moet u de kenmerken van de AD DS-kenmerken voorbereidingen hebben</span><span class="sxs-lookup"><span data-stu-id="2dee1-139">Successful directory synchronization between your AD DS and Microsoft 365 requires that your AD DS attributes are properly prepared.</span></span> <span data-ttu-id="2dee1-140">U moet bijvoorbeeld ervoor zorgen dat specifieke tekens niet worden gebruikt in bepaalde kenmerken die worden gesynchroniseerd met de Microsoft 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="2dee1-140">For example, you need to ensure that specific characters aren't used in certain attributes that are synchronized with the Microsoft 365 environment.</span></span> <span data-ttu-id="2dee1-141">Onverwachte tekens zorgen er niet voor dat de adreslijstsynchronisatie mislukt maar u kunt een waarschuwing retourneren.</span><span class="sxs-lookup"><span data-stu-id="2dee1-141">Unexpected characters do not cause directory synchronization to fail but might return a warning.</span></span> <span data-ttu-id="2dee1-142">Ongeldige tekens zorgen voor Directory-synchronisatie mislukt.</span><span class="sxs-lookup"><span data-stu-id="2dee1-142">Invalid characters will cause directory synchronization to fail.</span></span>

<span data-ttu-id="2dee1-143">Directory-synchronisatie mislukt ook als sommige van uw AD DS-gebruikers een of meer dubbele kenmerken hebben.</span><span class="sxs-lookup"><span data-stu-id="2dee1-143">Directory synchronization will also fail if some of your AD DS users have one or more duplicate attributes.</span></span> <span data-ttu-id="2dee1-144">Elke gebruiker moet unieke kenmerken hebben.</span><span class="sxs-lookup"><span data-stu-id="2dee1-144">Each user must have unique attributes.</span></span>

<span data-ttu-id="2dee1-145">De kenmerken die u moet voorbereiden, vindt u hier:</span><span class="sxs-lookup"><span data-stu-id="2dee1-145">The attributes that you need to prepare are listed here:</span></span>

- <span data-ttu-id="2dee1-146">**displayName**</span><span class="sxs-lookup"><span data-stu-id="2dee1-146">**displayName**</span></span>

  - <span data-ttu-id="2dee1-147">Als het kenmerk bestaat in het gebruikersobject, wordt het kenmerk gesynchroniseerd met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2dee1-147">If the attribute exists in the user object, it will be synchronized with Microsoft 365.</span></span>
  - <span data-ttu-id="2dee1-148">Als dit kenmerk bestaat in het gebruikersobject, moet er een waarde bestaan voor dit kenmerk.</span><span class="sxs-lookup"><span data-stu-id="2dee1-148">If this attribute exists in the user object, there must be a value for it.</span></span> <span data-ttu-id="2dee1-149">Dat wil zeggen dat het kenmerk niet leeg mag zijn.</span><span class="sxs-lookup"><span data-stu-id="2dee1-149">That is, the attribute must not be blank.</span></span>
  - <span data-ttu-id="2dee1-150">Maximum aantal tekens: 256</span><span class="sxs-lookup"><span data-stu-id="2dee1-150">Maximum number of characters: 256</span></span>

- <span data-ttu-id="2dee1-151">**voor benaming**</span><span class="sxs-lookup"><span data-stu-id="2dee1-151">**givenName**</span></span>

  - <span data-ttu-id="2dee1-152">Als het kenmerk bestaat in het gebruikersobject, wordt het gesynchroniseerd met Microsoft 365, maar Microsoft 365 maakt geen gebruik van dit kenmerk.</span><span class="sxs-lookup"><span data-stu-id="2dee1-152">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>
  - <span data-ttu-id="2dee1-153">Maximum aantal tekens: 64</span><span class="sxs-lookup"><span data-stu-id="2dee1-153">Maximum number of characters: 64</span></span>

- <span data-ttu-id="2dee1-154">**e-mail**</span><span class="sxs-lookup"><span data-stu-id="2dee1-154">**mail**</span></span>

  - <span data-ttu-id="2dee1-155">De kenmerkwaarde moet uniek zijn binnen de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="2dee1-155">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2dee1-156">Als er dubbele waarden zijn, wordt de eerste gebruiker met de waarde gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="2dee1-156">If there are duplicate values, the first user with the value is synchronized.</span></span> <span data-ttu-id="2dee1-157">De volgende gebruikers worden niet weergegeven in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2dee1-157">Subsequent users will not appear in Microsoft 365.</span></span> <span data-ttu-id="2dee1-158">U moet de waarde in Microsoft 365 wijzigen of beide waarden in AD DS wijzigen, zodat beide gebruikers in Microsoft 365 worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2dee1-158">You must modify either the value in Microsoft 365 or modify both of the values in AD DS in order for both users to appear in Microsoft 365.</span></span>

- <span data-ttu-id="2dee1-159">**mailNickname** (Exchange-alias)</span><span class="sxs-lookup"><span data-stu-id="2dee1-159">**mailNickname** (Exchange alias)</span></span>

  - <span data-ttu-id="2dee1-160">De kenmerkwaarde mag niet beginnen met een punt (.).</span><span class="sxs-lookup"><span data-stu-id="2dee1-160">The attribute value cannot begin with a period (.).</span></span>
  - <span data-ttu-id="2dee1-161">De kenmerkwaarde moet uniek zijn binnen de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="2dee1-161">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2dee1-162">Onderstrepingstekens ("_") in de gesynchroniseerde naam geven aan dat de oorspronkelijke waarde van dit kenmerk ongeldige tekens bevat.</span><span class="sxs-lookup"><span data-stu-id="2dee1-162">Underscores ("_") in the synchronized name indicates that the original value of this attribute contains invalid characters.</span></span> <span data-ttu-id="2dee1-163">Zie voor meer informatie over dit kenmerk [Exchange-alias kenmerk](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="2dee1-163">For more information on this attribute, see [Exchange alias attribute](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).</span></span>
    >

- <span data-ttu-id="2dee1-164">**proxyAddresses**</span><span class="sxs-lookup"><span data-stu-id="2dee1-164">**proxyAddresses**</span></span>

  - <span data-ttu-id="2dee1-165">Kenmerk met meerdere waarden</span><span class="sxs-lookup"><span data-stu-id="2dee1-165">Multiple-value attribute</span></span>
  - <span data-ttu-id="2dee1-166">Maximum aantal tekens per waarde: 256</span><span class="sxs-lookup"><span data-stu-id="2dee1-166">Maximum number of characters per value: 256</span></span>
  - <span data-ttu-id="2dee1-167">De kenmerkwaarde mag geen spatie bevatten.</span><span class="sxs-lookup"><span data-stu-id="2dee1-167">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="2dee1-168">De kenmerkwaarde moet uniek zijn binnen de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="2dee1-168">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="2dee1-169">Ongeldige tekens: \< \> ();, [] ""</span><span class="sxs-lookup"><span data-stu-id="2dee1-169">Invalid characters: \< \> ( ) ; , [ ] " '</span></span>

    <span data-ttu-id="2dee1-170">Houd er rekening mee dat de ongeldige tekens van toepassing zijn op de tekens die volgen op het type scheidingsteken en ': ', zodat de SMTP:User@contso.com is toegestaan, maar SMTP:user:M@contoso.com niet.</span><span class="sxs-lookup"><span data-stu-id="2dee1-170">Note that the invalid characters apply to the characters following the type delimiter and ":", such that SMTP:User@contso.com is allowed, but SMTP:user:M@contoso.com is not.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2dee1-171">Alle SMTP-adressen (Simple Mail Transport Protocol) moeten voldoen aan de standaarden voor e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="2dee1-171">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span> <span data-ttu-id="2dee1-172">Raadpleeg het Help-onderwerp [voor het verwijderen van dubbele en ongewenste proxy-adressen in Exchange](https://go.microsoft.com/fwlink/?LinkId=293860)als er dubbele of ongewenste adressen bestaan.</span><span class="sxs-lookup"><span data-stu-id="2dee1-172">If duplicate or unwanted addresses exist, see the Help topic [Removing duplicate and unwanted proxy addresses in Exchange](https://go.microsoft.com/fwlink/?LinkId=293860).</span></span>

- <span data-ttu-id="2dee1-173">**sAMAccountName**</span><span class="sxs-lookup"><span data-stu-id="2dee1-173">**sAMAccountName**</span></span>

  - <span data-ttu-id="2dee1-174">Maximum aantal tekens: 20</span><span class="sxs-lookup"><span data-stu-id="2dee1-174">Maximum number of characters: 20</span></span>
  - <span data-ttu-id="2dee1-175">De kenmerkwaarde moet uniek zijn binnen de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="2dee1-175">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="2dee1-176">Ongeldige tekens: [\ "|,/: \< \> + =;?</span><span class="sxs-lookup"><span data-stu-id="2dee1-176">Invalid characters: [ \ " | , / : \< \> + = ; ?</span></span> <span data-ttu-id="2dee1-177">\* ']</span><span class="sxs-lookup"><span data-stu-id="2dee1-177">\* ']</span></span>
  - <span data-ttu-id="2dee1-178">Als een gebruiker een ongeldig **sAMAccountName** -kenmerk heeft, maar beschikt over een geldig **userPrincipalName** -kenmerk, wordt het gebruikersaccount gemaakt in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2dee1-178">If a user has an invalid **sAMAccountName** attribute but has a valid **userPrincipalName** attribute, the user account is created in Microsoft 365.</span></span>
  - <span data-ttu-id="2dee1-179">Als zowel **sAMAccountName** als **userPrincipalName** ongeldig is, moet het kenmerk AD DS **userPrincipalName** worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="2dee1-179">If both **sAMAccountName** and **userPrincipalName** are invalid, the AD DS **userPrincipalName** attribute must be updated.</span></span>

- <span data-ttu-id="2dee1-180">**sn** (achternaam)</span><span class="sxs-lookup"><span data-stu-id="2dee1-180">**sn** (surname)</span></span>

  - <span data-ttu-id="2dee1-181">Als het kenmerk bestaat in het gebruikersobject, wordt het gesynchroniseerd met Microsoft 365, maar Microsoft 365 maakt geen gebruik van dit kenmerk.</span><span class="sxs-lookup"><span data-stu-id="2dee1-181">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>

- <span data-ttu-id="2dee1-182">**targetAddress**</span><span class="sxs-lookup"><span data-stu-id="2dee1-182">**targetAddress**</span></span>

    <span data-ttu-id="2dee1-183">U moet het kenmerk **targetAddress** (bijvoorbeeld SMTP:Tom@contoso.com) dat voor de gebruiker is ingevuld, worden weergegeven in de microsoft 365 Gal.</span><span class="sxs-lookup"><span data-stu-id="2dee1-183">It's required that the **targetAddress** attribute (for example, SMTP:tom@contoso.com) that's populated for the user must appear in the Microsoft 365 GAL.</span></span> <span data-ttu-id="2dee1-184">Voor de scenario van een externe communicatie met berichten migratie is hiervoor de Microsoft 365-schema-uitbreiding voor de AD DS vereist.</span><span class="sxs-lookup"><span data-stu-id="2dee1-184">In third-party messaging migration scenarios, this would require the Microsoft 365 schema extension for the AD DS.</span></span> <span data-ttu-id="2dee1-185">Met de Microsoft 365-schema extensie worden ook andere nuttige kenmerken toegevoegd voor het beheren van Microsoft 365-objecten die worden gevuld met behulp van een adreslijstsynchronisatie vanuit AD DS.</span><span class="sxs-lookup"><span data-stu-id="2dee1-185">The Microsoft 365 schema extension would also add other useful attributes to manage Microsoft 365 objects that are populated by using a directory synchronization tool from AD DS.</span></span> <span data-ttu-id="2dee1-186">Het kenmerk **msExchHideFromAddressLists** voor het beheren van verborgen postvakken of distributiegroepen werd bijvoorbeeld toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="2dee1-186">For example, the **msExchHideFromAddressLists** attribute to manage hidden mailboxes or distribution groups would be added.</span></span>

  - <span data-ttu-id="2dee1-187">Maximum aantal tekens: 256</span><span class="sxs-lookup"><span data-stu-id="2dee1-187">Maximum number of characters: 256</span></span>
  - <span data-ttu-id="2dee1-188">De kenmerkwaarde mag geen spatie bevatten.</span><span class="sxs-lookup"><span data-stu-id="2dee1-188">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="2dee1-189">De kenmerkwaarde moet uniek zijn binnen de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="2dee1-189">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="2dee1-190">Ongeldige tekens: \ \< \> ();, [] "</span><span class="sxs-lookup"><span data-stu-id="2dee1-190">Invalid characters: \ \< \> ( ) ; , [ ] "</span></span>
  - <span data-ttu-id="2dee1-191">Alle SMTP-adressen (Simple Mail Transport Protocol) moeten voldoen aan de standaarden voor e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="2dee1-191">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>

- <span data-ttu-id="2dee1-192">**userPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="2dee1-192">**userPrincipalName**</span></span>

  - <span data-ttu-id="2dee1-193">De aanmeldings opmaak van het **userPrincipalName** -kenmerk moet de Internet stijl hebben, waarbij de gebruikersnaam wordt gevolgd door het apenstaartje (@) en een domeinnaam: bijvoorbeeld user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2dee1-193">The **userPrincipalName** attribute must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name: for example, user@contoso.com.</span></span> <span data-ttu-id="2dee1-194">Alle SMTP-adressen (Simple Mail Transport Protocol) moeten voldoen aan de standaarden voor e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="2dee1-194">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>
  - <span data-ttu-id="2dee1-195">Het maximum aantal tekens voor het kenmerk **userPrincipalName** is 113.</span><span class="sxs-lookup"><span data-stu-id="2dee1-195">The maximum number of characters for the **userPrincipalName** attribute is 113.</span></span> <span data-ttu-id="2dee1-196">U kunt als volgt een specifiek aantal tekens voor en na het apenstaartje (@) zijn toegestaan:</span><span class="sxs-lookup"><span data-stu-id="2dee1-196">A specific number of characters are permitted before and after the at sign (@), as follows:</span></span>
  - <span data-ttu-id="2dee1-197">Het maximum aantal tekens voor de gebruikersnaam vóór het apenstaartje (@): 64</span><span class="sxs-lookup"><span data-stu-id="2dee1-197">Maximum number of characters for the username that is in front of the at sign (@): 64</span></span>
  - <span data-ttu-id="2dee1-198">Het maximum aantal tekens voor de domeinnaam na het apenstaartje (@): 48</span><span class="sxs-lookup"><span data-stu-id="2dee1-198">Maximum number of characters for the domain name following the at sign (@): 48</span></span>
  - <span data-ttu-id="2dee1-199">Ongeldige tekens: \% &amp; \* +/=?</span><span class="sxs-lookup"><span data-stu-id="2dee1-199">Invalid characters: \ % &amp; \* + / = ?</span></span> <span data-ttu-id="2dee1-200">{ } | \< \> ( ) ; : , [ ] " '</span><span class="sxs-lookup"><span data-stu-id="2dee1-200">{ } | \< \> ( ) ; : , [ ] " '</span></span>
  - <span data-ttu-id="2dee1-201">Tekens toegestaan: A-Z, a-z, 0-9, '.</span><span class="sxs-lookup"><span data-stu-id="2dee1-201">Characters allowed: A – Z, a - z, 0 – 9, ' .</span></span> <span data-ttu-id="2dee1-202">- _ !</span><span class="sxs-lookup"><span data-stu-id="2dee1-202">- _ !</span></span> <span data-ttu-id="2dee1-203"># ^ ~</span><span class="sxs-lookup"><span data-stu-id="2dee1-203"># ^ ~</span></span>
  - <span data-ttu-id="2dee1-204">Letters met diakritische tekens, zoals een umlaut, accenten en tilde, zijn ongeldige tekens.</span><span class="sxs-lookup"><span data-stu-id="2dee1-204">Letters with diacritical marks, such as umlauts, accents, and tildes, are invalid characters.</span></span>
  - <span data-ttu-id="2dee1-205">Het teken @ is vereist voor elke **userPrincipalName** -waarde.</span><span class="sxs-lookup"><span data-stu-id="2dee1-205">The @ character is required in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="2dee1-206">Het teken @ mag niet het eerste teken in een **userPrincipalName** -waarde zijn.</span><span class="sxs-lookup"><span data-stu-id="2dee1-206">The @ character cannot be the first character in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="2dee1-207">De gebruikersnaam mag niet eindigen op een punt (.), een &amp; en-teken (), een spatie of een apenstaartje (@).</span><span class="sxs-lookup"><span data-stu-id="2dee1-207">The username cannot end with a period (.), an ampersand (&amp;), a space, or an at sign (@).</span></span>
  - <span data-ttu-id="2dee1-208">De gebruikersnaam mag geen spaties bevatten.</span><span class="sxs-lookup"><span data-stu-id="2dee1-208">The username cannot contain any spaces.</span></span>
  - <span data-ttu-id="2dee1-209">Routeerbaar domein moet worden gebruikt; lokale of interne domeinen kunnen bijvoorbeeld niet worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="2dee1-209">Routable domains must be used; for example, local or internal domains cannot be used.</span></span>
  - <span data-ttu-id="2dee1-210">Unicode wordt geconverteerd naar onderstrepingstekens.</span><span class="sxs-lookup"><span data-stu-id="2dee1-210">Unicode is converted to underscore characters.</span></span>
  - <span data-ttu-id="2dee1-211">**userPrincipalName** mag geen dubbele waarden in de adreslijst bevatten.</span><span class="sxs-lookup"><span data-stu-id="2dee1-211">**userPrincipalName** cannot contain any duplicate values in the directory.</span></span>

## <a name="3-prepare-the-userprincipalname-attribute"></a><span data-ttu-id="2dee1-212">3. het kenmerk userPrincipalName voorbereiden</span><span class="sxs-lookup"><span data-stu-id="2dee1-212">3. Prepare the userPrincipalName attribute</span></span>

<span data-ttu-id="2dee1-213">Active Directory is bedoeld voor de eindgebruikers in uw organisatie waarmee ze zich kunnen aanmelden bij uw adreslijst met behulp van **sAMAccountName** of **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="2dee1-213">Active Directory is designed to allow the end users in your organization to sign in to your directory by using either **sAMAccountName** or **userPrincipalName**.</span></span> <span data-ttu-id="2dee1-214">Eindgebruikers kunnen zich ook aanmelden bij Microsoft 365 met behulp van de UPN (User Principal Name) van hun werk-of schoolaccount.</span><span class="sxs-lookup"><span data-stu-id="2dee1-214">Similarly, end users can sign in to Microsoft 365 by using the user principal name (UPN) of their work or school account.</span></span> <span data-ttu-id="2dee1-215">Adreslijstsynchronisatie probeert nieuwe gebruikers te maken in azure Active Directory met behulp van dezelfde UPN in uw AD DS.</span><span class="sxs-lookup"><span data-stu-id="2dee1-215">Directory synchronization attempts to create new users in Azure Active Directory by using the same UPN that's in your AD DS.</span></span> <span data-ttu-id="2dee1-216">De UPN wordt opgemaakt als een e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="2dee1-216">The UPN is formatted like an email address.</span></span>

<span data-ttu-id="2dee1-217">In Microsoft 365 is de UPN het standaardkenmerk dat wordt gebruikt voor het genereren van het e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="2dee1-217">In Microsoft 365, the UPN is the default attribute that's used to generate the email address.</span></span> <span data-ttu-id="2dee1-218">U kunt in de proxyAddresses **-app** en het primaire e-mailadres in **proxyAddresses** op verschillende waarden instellen.</span><span class="sxs-lookup"><span data-stu-id="2dee1-218">It's easy to get **userPrincipalName** (in AD DS and in Azure AD) and the primary email address in **proxyAddresses** set to different values.</span></span> <span data-ttu-id="2dee1-219">Wanneer ze zijn ingesteld op verschillende waarden, kan dit leiden tot verwarring voor beheerders en eindgebruikers.</span><span class="sxs-lookup"><span data-stu-id="2dee1-219">When they are set to different values, there can be confusion for administrators and end users.</span></span>

<span data-ttu-id="2dee1-220">U kunt deze kenmerken het best uitlijnen om verwarring te beperken.</span><span class="sxs-lookup"><span data-stu-id="2dee1-220">It's best to align these attributes to reduce confusion.</span></span> <span data-ttu-id="2dee1-221">Om te voldoen aan de vereisten van eenmalige aanmelding met Active Directory Federation Services (AD FS) 2,0, moet u ervoor zorgen dat de Upn's in azure Active Directory en de AD DS overeenkomen met een geldige domeinnaam ruimte.</span><span class="sxs-lookup"><span data-stu-id="2dee1-221">To meet the requirements of single sign-on with Active Directory Federation Services (AD FS) 2.0, you need to ensure that the UPNs in Azure Active Directory and your AD DS match and are using a valid domain namespace.</span></span>

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a><span data-ttu-id="2dee1-222">4. een alternatief UPN-achtervoegsel toevoegen aan AD DS</span><span class="sxs-lookup"><span data-stu-id="2dee1-222">4. Add an alternative UPN suffix to AD DS</span></span>

<span data-ttu-id="2dee1-223">Het kan zijn dat u een alternatief UPN-achtervoegsel moet toevoegen om de bedrijfsreferenties van de gebruiker te koppelen aan de Microsoft 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="2dee1-223">You may need to add an alternative UPN suffix to associate the user's corporate credentials with the Microsoft 365 environment.</span></span> <span data-ttu-id="2dee1-224">Een UPN-achtervoegsel is het onderdeel van een UPN rechts van het teken @.</span><span class="sxs-lookup"><span data-stu-id="2dee1-224">A UPN suffix is the part of a UPN to the right of the @ character.</span></span> <span data-ttu-id="2dee1-225">UPN-namen die worden gebruikt voor eenmalige aanmelding kunnen letters, cijfers, punten, streepjes en onderstrepingstekens bevatten, maar geen andere typen tekens.</span><span class="sxs-lookup"><span data-stu-id="2dee1-225">UPNs that are used for single sign-on can contain letters, numbers, periods, dashes, and underscores, but no other types of characters.</span></span>

<span data-ttu-id="2dee1-226">Zie voor meer informatie over het toevoegen van een alternatief UPN-achtervoegsel aan Active Directory voor meer informatie over het [voorbereiden van adreslijstsynchronisatie]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span><span class="sxs-lookup"><span data-stu-id="2dee1-226">For more information on how to add an alternative UPN suffix to Active Directory, see [Prepare for directory synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span></span>

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a><span data-ttu-id="2dee1-227">5. overeen met de AD DS-UPN met de Microsoft 365-UPN</span><span class="sxs-lookup"><span data-stu-id="2dee1-227">5. Match the AD DS UPN with the Microsoft 365 UPN</span></span>

<span data-ttu-id="2dee1-228">Als u al adreslijstsynchronisatie hebt ingesteld, komt de UPN van de gebruiker voor Microsoft 365 mogelijk niet overeen met de AD DS-UPN van de gebruiker die is gedefinieerd in uw AD DS.</span><span class="sxs-lookup"><span data-stu-id="2dee1-228">If you've already set up directory synchronization, the user's UPN for Microsoft 365 may not match the user's AD DS UPN that's defined in your AD DS.</span></span> <span data-ttu-id="2dee1-229">Dit kan zich voordoen wanneer aan een gebruiker een licentie is toegewezen voordat het domein is geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="2dee1-229">This can occur when a user was assigned a license before the domain was verified.</span></span> <span data-ttu-id="2dee1-230">U kunt dit oplossen door [PowerShell te gebruiken voor het herstellen](https://go.microsoft.com/fwlink/p/?LinkId=396730) van de UPN van de gebruiker om ervoor te zorgen dat de UPN van microsoft 365 overeenkomt met de naam en het domein van de zakelijke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="2dee1-230">To fix this, use [PowerShell to fix duplicate UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) to update the user's UPN to ensure that the Microsoft 365 UPN matches the corporate user name and domain.</span></span> <span data-ttu-id="2dee1-231">Als u de UPN in de AD DS bijwerkt en deze wilt synchroniseren met de Azure Active Directory-identiteit, moet u de licentie van de gebruiker verwijderen in Microsoft 365 voordat u wijzigingen aanbrengt in AD DS.</span><span class="sxs-lookup"><span data-stu-id="2dee1-231">If you are updating the UPN in the AD DS and would like it to synchronize with the Azure Active Directory identity, you need to remove the user's license in Microsoft 365 prior to making the changes in AD DS.</span></span>

<span data-ttu-id="2dee1-232">Zie ook [een niet-routeerbaar domein (zoals. lokaal) voorbereiden op adreslijstsynchronisatie](prepare-a-non-routable-domain-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="2dee1-232">Also see [How to prepare a non-routable domain (such as .local domain) for directory synchronization](prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="2dee1-233">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="2dee1-233">Next steps</span></span>

<span data-ttu-id="2dee1-234">Als u de stappen 1 tot en met 5 hierboven hebt uitgevoerd, raadpleegt u [adreslijstsynchronisatie instellen](set-up-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="2dee1-234">If you have done steps 1 through 5 above, see [Set up directory synchronization](set-up-directory-synchronization.md).</span></span>
