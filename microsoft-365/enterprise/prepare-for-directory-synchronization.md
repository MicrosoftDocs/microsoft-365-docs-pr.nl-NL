---
title: Voorbereidingen treffen voor adreslijstsynchronisatie om Microsoft 365
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
description: Hier wordt beschreven hoe u gebruikers kunt voorbereiden op Microsoft 365 gebruik te maken van adreslijstsynchronisatie en de voordelen op lange termijn van het gebruik van deze methode.
ms.openlocfilehash: 7f701bf0a8b165323f7fd61b50b41fb5e18268a6
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259557"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a><span data-ttu-id="dfed8-103">Voorbereidingen treffen voor adreslijstsynchronisatie om Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dfed8-103">Prepare for directory synchronization to Microsoft 365</span></span>

<span data-ttu-id="dfed8-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="dfed8-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="dfed8-105">De voordelen voor hybride identiteits- en adreslijstsynchronisatie van uw organisatie zijn:</span><span class="sxs-lookup"><span data-stu-id="dfed8-105">The benefits to hybrid identity and directory synchronization your organization include:</span></span>

- <span data-ttu-id="dfed8-106">De beheerprogramma's in uw organisatie verminderen</span><span class="sxs-lookup"><span data-stu-id="dfed8-106">Reducing the administrative programs in your organization</span></span>
- <span data-ttu-id="dfed8-107">Optioneel een enkel aanmeldingsscenario inschakelen</span><span class="sxs-lookup"><span data-stu-id="dfed8-107">Optionally enabling single sign-on scenario</span></span>
- <span data-ttu-id="dfed8-108">Accountwijzigingen automatiseren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dfed8-108">Automating account changes in Microsoft 365</span></span>

<span data-ttu-id="dfed8-109">Zie hybride identiteit met Azure Active Directory [(Azure AD)](/azure/active-directory/hybrid/whatis-hybrid-identity) en hybride identiteit voor Microsoft 365 voor meer informatie over de voordelen van het gebruik van [adreslijstsynchronisatie.](plan-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="dfed8-109">For more information about the advantages of using directory synchronization, see [hybrid identity with Azure Active Directory (Azure AD)](/azure/active-directory/hybrid/whatis-hybrid-identity) and [hybrid identity for Microsoft 365](plan-for-directory-synchronization.md).</span></span>

<span data-ttu-id="dfed8-110">Adreslijstsynchronisatie vereist echter planning en voorbereiding om ervoor te zorgen dat uw AD DS (Active Directory Domain Services) wordt gesynchroniseerd met de Azure AD-tenant van uw Microsoft 365-abonnement met een minimum aan fouten.</span><span class="sxs-lookup"><span data-stu-id="dfed8-110">However, directory synchronization requires planning and preparation to ensure that your Active Directory Domain Services (AD DS) synchronizes to the Azure AD tenant of your Microsoft 365 subscription with a minimum of errors.</span></span>

<span data-ttu-id="dfed8-111">Volg deze stappen om de beste resultaten te krijgen.</span><span class="sxs-lookup"><span data-stu-id="dfed8-111">Follow these steps in order for the best results.</span></span>

## <a name="1-directory-cleanup-tasks"></a><span data-ttu-id="dfed8-112">1. Adreslijst opschoningstaken</span><span class="sxs-lookup"><span data-stu-id="dfed8-112">1. Directory cleanup tasks</span></span>

<span data-ttu-id="dfed8-113">Voordat u uw AD DS synchroniseert met uw Azure AD-tenant, moet u uw AD DS ops schonen.</span><span class="sxs-lookup"><span data-stu-id="dfed8-113">Before you synchronize your AD DS to your Azure AD tenant, you need to clean up your AD DS.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dfed8-114">Als u geen AD DS-opschoning voert voordat u synchroniseert, kan dit leiden tot een aanzienlijke negatieve invloed op het implementatieproces.</span><span class="sxs-lookup"><span data-stu-id="dfed8-114">If you don't perform AD DS cleanup before you synchronize, it can lead to a significant negative impact on the deployment process.</span></span> <span data-ttu-id="dfed8-115">Het kan dagen of zelfs weken duren om door de cyclus van adreslijstsynchronisatie te lopen, fouten te identificeren en opnieuw te synchroniseren.</span><span class="sxs-lookup"><span data-stu-id="dfed8-115">It might take days, or even weeks, to go through the cycle of directory synchronization, identifying errors, and re-synchronization.</span></span>

<span data-ttu-id="dfed8-116">Voltooi in uw AD DS de volgende opruimtaken voor elk gebruikersaccount dat een licentie Microsoft 365 gebruikersaccount:</span><span class="sxs-lookup"><span data-stu-id="dfed8-116">In your AD DS, complete the following clean-up tasks for each user account that will be assigned a Microsoft 365 license:</span></span>

1. <span data-ttu-id="dfed8-117">Controleer een geldig en uniek e-mailadres in het **kenmerk proxyAddresses.**</span><span class="sxs-lookup"><span data-stu-id="dfed8-117">Ensure a valid and unique email address in the **proxyAddresses** attribute.</span></span>

2. <span data-ttu-id="dfed8-118">Verwijder dubbele waarden in het **kenmerk proxyAddresses.**</span><span class="sxs-lookup"><span data-stu-id="dfed8-118">Remove any duplicate values in the **proxyAddresses** attribute.</span></span>

3. <span data-ttu-id="dfed8-119">Zorg indien mogelijk voor een geldige en unieke waarde voor het **userPrincipalName-kenmerk** in het **gebruikersobject** van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="dfed8-119">If possible, ensure a valid and unique value for the **userPrincipalName** attribute in the user's **user** object.</span></span> <span data-ttu-id="dfed8-120">Zorg ervoor dat de AD DS UPN overeenkomt met de Azure AD UPN voor de beste synchronisatieervaring.</span><span class="sxs-lookup"><span data-stu-id="dfed8-120">For the best synchronization experience, ensure that the AD DS UPN matches the Azure AD UPN.</span></span> <span data-ttu-id="dfed8-121">Als een gebruiker geen waarde heeft voor het **kenmerk userPrincipalName,** moet het **gebruikersobject** een geldige en unieke waarde bevatten voor het **kenmerk sAMAccountName.**</span><span class="sxs-lookup"><span data-stu-id="dfed8-121">If a user does not have a value for the **userPrincipalName** attribute, then the **user** object must contain a valid and unique value for the **sAMAccountName** attribute.</span></span> <span data-ttu-id="dfed8-122">Verwijder eventuele dubbele waarden in het **userPrincipalName-kenmerk.**</span><span class="sxs-lookup"><span data-stu-id="dfed8-122">Remove any duplicate values in the **userPrincipalName** attribute.</span></span>

4. <span data-ttu-id="dfed8-123">Zorg ervoor dat de informatie in de volgende kenmerken van het AD DS-gebruikersaccount correct is voor optimaal gebruik van de algemene adreslijst (GAL):</span><span class="sxs-lookup"><span data-stu-id="dfed8-123">For optimal use of the global address list (GAL), ensure the information in the following attributes of the AD DS user account is correct:</span></span>

   - <span data-ttu-id="dfed8-124">givenName</span><span class="sxs-lookup"><span data-stu-id="dfed8-124">givenName</span></span>
   - <span data-ttu-id="dfed8-125">achternaam</span><span class="sxs-lookup"><span data-stu-id="dfed8-125">surname</span></span>
   - <span data-ttu-id="dfed8-126">displayName</span><span class="sxs-lookup"><span data-stu-id="dfed8-126">displayName</span></span>
   - <span data-ttu-id="dfed8-127">Functie</span><span class="sxs-lookup"><span data-stu-id="dfed8-127">Job Title</span></span>
   - <span data-ttu-id="dfed8-128">Department</span><span class="sxs-lookup"><span data-stu-id="dfed8-128">Department</span></span>
   - <span data-ttu-id="dfed8-129">Office</span><span class="sxs-lookup"><span data-stu-id="dfed8-129">Office</span></span>
   - <span data-ttu-id="dfed8-130">Zakelijk nummer</span><span class="sxs-lookup"><span data-stu-id="dfed8-130">Office Phone</span></span>
   - <span data-ttu-id="dfed8-131">Mobiel nummer</span><span class="sxs-lookup"><span data-stu-id="dfed8-131">Mobile Phone</span></span>
   - <span data-ttu-id="dfed8-132">Faxnummer</span><span class="sxs-lookup"><span data-stu-id="dfed8-132">Fax Number</span></span>
   - <span data-ttu-id="dfed8-133">Adres van straat</span><span class="sxs-lookup"><span data-stu-id="dfed8-133">Street Address</span></span>
   - <span data-ttu-id="dfed8-134">Plaats</span><span class="sxs-lookup"><span data-stu-id="dfed8-134">City</span></span>
   - <span data-ttu-id="dfed8-135">Provincie</span><span class="sxs-lookup"><span data-stu-id="dfed8-135">State or Province</span></span>
   - <span data-ttu-id="dfed8-136">Postcode</span><span class="sxs-lookup"><span data-stu-id="dfed8-136">Zip or Postal Code</span></span>
   - <span data-ttu-id="dfed8-137">Land of regio</span><span class="sxs-lookup"><span data-stu-id="dfed8-137">Country or Region</span></span>

## <a name="2-directory-object-and-attribute-preparation"></a><span data-ttu-id="dfed8-138">2. Voorbereiding van adreslijstobjecten en kenmerken</span><span class="sxs-lookup"><span data-stu-id="dfed8-138">2. Directory object and attribute preparation</span></span>

<span data-ttu-id="dfed8-139">Succesvolle adreslijstsynchronisatie tussen uw AD DS en Microsoft 365 vereist dat uw AD DS-kenmerken goed zijn voorbereid.</span><span class="sxs-lookup"><span data-stu-id="dfed8-139">Successful directory synchronization between your AD DS and Microsoft 365 requires that your AD DS attributes are properly prepared.</span></span> <span data-ttu-id="dfed8-140">U moet er bijvoorbeeld voor zorgen dat bepaalde tekens niet worden gebruikt in bepaalde kenmerken die worden gesynchroniseerd met de Microsoft 365 omgeving.</span><span class="sxs-lookup"><span data-stu-id="dfed8-140">For example, you need to ensure that specific characters aren't used in certain attributes that are synchronized with the Microsoft 365 environment.</span></span> <span data-ttu-id="dfed8-141">Onverwachte tekens leiden er niet toe dat adreslijstsynchronisatie mislukt, maar kan een waarschuwing retourneren.</span><span class="sxs-lookup"><span data-stu-id="dfed8-141">Unexpected characters do not cause directory synchronization to fail but might return a warning.</span></span> <span data-ttu-id="dfed8-142">Ongeldige tekens zorgen ervoor dat adreslijstsynchronisatie mislukt.</span><span class="sxs-lookup"><span data-stu-id="dfed8-142">Invalid characters will cause directory synchronization to fail.</span></span>

<span data-ttu-id="dfed8-143">Adreslijstsynchronisatie mislukt ook als sommige AD DS-gebruikers een of meer dubbele kenmerken hebben.</span><span class="sxs-lookup"><span data-stu-id="dfed8-143">Directory synchronization will also fail if some of your AD DS users have one or more duplicate attributes.</span></span> <span data-ttu-id="dfed8-144">Elke gebruiker moet unieke kenmerken hebben.</span><span class="sxs-lookup"><span data-stu-id="dfed8-144">Each user must have unique attributes.</span></span>

<span data-ttu-id="dfed8-145">De kenmerken die u moet voorbereiden, worden hier weergegeven:</span><span class="sxs-lookup"><span data-stu-id="dfed8-145">The attributes that you need to prepare are listed here:</span></span>

- <span data-ttu-id="dfed8-146">**displayName**</span><span class="sxs-lookup"><span data-stu-id="dfed8-146">**displayName**</span></span>

  - <span data-ttu-id="dfed8-147">Als het kenmerk bestaat in het gebruikersobject, wordt het gesynchroniseerd met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dfed8-147">If the attribute exists in the user object, it will be synchronized with Microsoft 365.</span></span>
  - <span data-ttu-id="dfed8-148">Als dit kenmerk bestaat in het gebruikersobject, moet er een waarde voor het object zijn.</span><span class="sxs-lookup"><span data-stu-id="dfed8-148">If this attribute exists in the user object, there must be a value for it.</span></span> <span data-ttu-id="dfed8-149">Dat wil zeggen dat het kenmerk niet leeg mag zijn.</span><span class="sxs-lookup"><span data-stu-id="dfed8-149">That is, the attribute must not be blank.</span></span>
  - <span data-ttu-id="dfed8-150">Maximum aantal tekens: 256</span><span class="sxs-lookup"><span data-stu-id="dfed8-150">Maximum number of characters: 256</span></span>

- <span data-ttu-id="dfed8-151">**givenName**</span><span class="sxs-lookup"><span data-stu-id="dfed8-151">**givenName**</span></span>

  - <span data-ttu-id="dfed8-152">Als het kenmerk bestaat in het gebruikersobject, wordt het gesynchroniseerd met Microsoft 365, maar Microsoft 365 het niet vereist of gebruikt.</span><span class="sxs-lookup"><span data-stu-id="dfed8-152">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>
  - <span data-ttu-id="dfed8-153">Maximum aantal tekens: 64</span><span class="sxs-lookup"><span data-stu-id="dfed8-153">Maximum number of characters: 64</span></span>

- <span data-ttu-id="dfed8-154">**e-mail**</span><span class="sxs-lookup"><span data-stu-id="dfed8-154">**mail**</span></span>

  - <span data-ttu-id="dfed8-155">De kenmerkwaarde moet uniek zijn in de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="dfed8-155">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dfed8-156">Als er dubbele waarden zijn, wordt de eerste gebruiker met de waarde gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="dfed8-156">If there are duplicate values, the first user with the value is synchronized.</span></span> <span data-ttu-id="dfed8-157">Volgende gebruikers worden niet weergegeven in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dfed8-157">Subsequent users will not appear in Microsoft 365.</span></span> <span data-ttu-id="dfed8-158">U moet de waarde in Microsoft 365 of beide waarden in AD DS wijzigen, zodat beide gebruikers in de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dfed8-158">You must modify either the value in Microsoft 365 or modify both of the values in AD DS in order for both users to appear in Microsoft 365.</span></span>

- <span data-ttu-id="dfed8-159">**mailNickname** (Exchange alias)</span><span class="sxs-lookup"><span data-stu-id="dfed8-159">**mailNickname** (Exchange alias)</span></span>

  - <span data-ttu-id="dfed8-160">De kenmerkwaarde kan niet beginnen met een punt (.).</span><span class="sxs-lookup"><span data-stu-id="dfed8-160">The attribute value cannot begin with a period (.).</span></span>
  - <span data-ttu-id="dfed8-161">De kenmerkwaarde moet uniek zijn in de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="dfed8-161">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dfed8-162">Onderstrepingstekens ("_") in de gesynchroniseerde naam geven aan dat de oorspronkelijke waarde van dit kenmerk ongeldige tekens bevat.</span><span class="sxs-lookup"><span data-stu-id="dfed8-162">Underscores ("_") in the synchronized name indicates that the original value of this attribute contains invalid characters.</span></span> <span data-ttu-id="dfed8-163">Zie het aliaskenmerk [Exchange meer informatie](/powershell/module/exchange/set-mailbox)over dit kenmerk.</span><span class="sxs-lookup"><span data-stu-id="dfed8-163">For more information on this attribute, see [Exchange alias attribute](/powershell/module/exchange/set-mailbox).</span></span>
    >

- <span data-ttu-id="dfed8-164">**proxyAddresses**</span><span class="sxs-lookup"><span data-stu-id="dfed8-164">**proxyAddresses**</span></span>

  - <span data-ttu-id="dfed8-165">Kenmerk met meerdere waarden</span><span class="sxs-lookup"><span data-stu-id="dfed8-165">Multiple-value attribute</span></span>
  - <span data-ttu-id="dfed8-166">Maximum aantal tekens per waarde: 256</span><span class="sxs-lookup"><span data-stu-id="dfed8-166">Maximum number of characters per value: 256</span></span>
  - <span data-ttu-id="dfed8-167">De kenmerkwaarde mag geen spatie bevatten.</span><span class="sxs-lookup"><span data-stu-id="dfed8-167">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="dfed8-168">De kenmerkwaarde moet uniek zijn in de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="dfed8-168">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="dfed8-169">Ongeldige tekens: \< \> ( ) ; , [ ] "</span><span class="sxs-lookup"><span data-stu-id="dfed8-169">Invalid characters: \< \> ( ) ; , [ ] "</span></span>

    <span data-ttu-id="dfed8-170">Houd er rekening mee dat de ongeldige tekens van toepassing zijn op de tekens na het type scheidingsteken en ':', zodat SMTP:User@contso.com is toegestaan, maar SMTP:user:M@contoso.com niet.</span><span class="sxs-lookup"><span data-stu-id="dfed8-170">Note that the invalid characters apply to the characters following the type delimiter and ":", such that SMTP:User@contso.com is allowed, but SMTP:user:M@contoso.com is not.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="dfed8-171">Alle SMTP-adressen (Simple Mail Transport Protocol) moeten voldoen aan de standaarden voor e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="dfed8-171">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span> <span data-ttu-id="dfed8-172">Verwijder dubbele of ongewenste adressen als deze bestaan.</span><span class="sxs-lookup"><span data-stu-id="dfed8-172">Remove duplicate or unwanted addresses if they exist.</span></span>

- <span data-ttu-id="dfed8-173">**sAMAccountName**</span><span class="sxs-lookup"><span data-stu-id="dfed8-173">**sAMAccountName**</span></span>

  - <span data-ttu-id="dfed8-174">Maximum aantal tekens: 20</span><span class="sxs-lookup"><span data-stu-id="dfed8-174">Maximum number of characters: 20</span></span>
  - <span data-ttu-id="dfed8-175">De kenmerkwaarde moet uniek zijn in de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="dfed8-175">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="dfed8-176">Ongeldige tekens: [ \ " | , / : \< \> + = ; ?</span><span class="sxs-lookup"><span data-stu-id="dfed8-176">Invalid characters: [ \ " | , / : \< \> + = ; ?</span></span> <span data-ttu-id="dfed8-177">\* ']</span><span class="sxs-lookup"><span data-stu-id="dfed8-177">\* ']</span></span>
  - <span data-ttu-id="dfed8-178">Als een gebruiker een ongeldig **sAMAccountName-kenmerk** heeft, maar een geldig **userPrincipalName-kenmerk** heeft, wordt het gebruikersaccount gemaakt in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dfed8-178">If a user has an invalid **sAMAccountName** attribute but has a valid **userPrincipalName** attribute, the user account is created in Microsoft 365.</span></span>
  - <span data-ttu-id="dfed8-179">Als zowel **sAMAccountName** als **userPrincipalName** ongeldig zijn, moet het AD DS **userPrincipalName-kenmerk** worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="dfed8-179">If both **sAMAccountName** and **userPrincipalName** are invalid, the AD DS **userPrincipalName** attribute must be updated.</span></span>

- <span data-ttu-id="dfed8-180">**sn** (achternaam)</span><span class="sxs-lookup"><span data-stu-id="dfed8-180">**sn** (surname)</span></span>

  - <span data-ttu-id="dfed8-181">Als het kenmerk bestaat in het gebruikersobject, wordt het gesynchroniseerd met Microsoft 365, maar Microsoft 365 het niet vereist of gebruikt.</span><span class="sxs-lookup"><span data-stu-id="dfed8-181">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>

- <span data-ttu-id="dfed8-182">**targetAddress**</span><span class="sxs-lookup"><span data-stu-id="dfed8-182">**targetAddress**</span></span>

    <span data-ttu-id="dfed8-183">Het is vereist dat het **targetAddress-kenmerk** (bijvoorbeeld SMTP:tom@contoso.com) dat voor de gebruiker wordt ingevuld, moet worden weergegeven in de Microsoft 365 GAL.</span><span class="sxs-lookup"><span data-stu-id="dfed8-183">It's required that the **targetAddress** attribute (for example, SMTP:tom@contoso.com) that's populated for the user must appear in the Microsoft 365 GAL.</span></span> <span data-ttu-id="dfed8-184">In scenario's voor berichtenmigratie van derden is hiervoor de Microsoft 365 voor de AD DS vereist.</span><span class="sxs-lookup"><span data-stu-id="dfed8-184">In third-party messaging migration scenarios, this would require the Microsoft 365 schema extension for the AD DS.</span></span> <span data-ttu-id="dfed8-185">De Microsoft 365 schemaextensie voegt ook andere nuttige kenmerken toe om Microsoft 365 objecten te beheren die worden ingevuld met behulp van een hulpprogramma voor adreslijstsynchronisatie van AD DS.</span><span class="sxs-lookup"><span data-stu-id="dfed8-185">The Microsoft 365 schema extension would also add other useful attributes to manage Microsoft 365 objects that are populated by using a directory synchronization tool from AD DS.</span></span> <span data-ttu-id="dfed8-186">Het **msExchHideFromAddressLists-kenmerk** voor het beheren van verborgen postvakken of distributiegroepen wordt bijvoorbeeld toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="dfed8-186">For example, the **msExchHideFromAddressLists** attribute to manage hidden mailboxes or distribution groups would be added.</span></span>

  - <span data-ttu-id="dfed8-187">Maximum aantal tekens: 256</span><span class="sxs-lookup"><span data-stu-id="dfed8-187">Maximum number of characters: 256</span></span>
  - <span data-ttu-id="dfed8-188">De kenmerkwaarde mag geen spatie bevatten.</span><span class="sxs-lookup"><span data-stu-id="dfed8-188">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="dfed8-189">De kenmerkwaarde moet uniek zijn in de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="dfed8-189">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="dfed8-190">Ongeldige tekens: \ \< \> ( ) ; , [ ] "</span><span class="sxs-lookup"><span data-stu-id="dfed8-190">Invalid characters: \ \< \> ( ) ; , [ ] "</span></span>
  - <span data-ttu-id="dfed8-191">Alle SMTP-adressen (Simple Mail Transport Protocol) moeten voldoen aan de standaarden voor e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="dfed8-191">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>

- <span data-ttu-id="dfed8-192">**userPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="dfed8-192">**userPrincipalName**</span></span>

  - <span data-ttu-id="dfed8-193">Het **userPrincipalName-kenmerk** moet zich in de aanmeldingsindeling voor internetstijl hebben, waarbij de gebruikersnaam wordt gevolgd door het at sign (@) en een domeinnaam: bijvoorbeeld user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="dfed8-193">The **userPrincipalName** attribute must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name: for example, user@contoso.com.</span></span> <span data-ttu-id="dfed8-194">Alle SMTP-adressen (Simple Mail Transport Protocol) moeten voldoen aan de standaarden voor e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="dfed8-194">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>
  - <span data-ttu-id="dfed8-195">Het maximum aantal tekens voor het **userPrincipalName-kenmerk** is 113.</span><span class="sxs-lookup"><span data-stu-id="dfed8-195">The maximum number of characters for the **userPrincipalName** attribute is 113.</span></span> <span data-ttu-id="dfed8-196">Een bepaald aantal tekens is voor en na het bijteken (@) als volgt toegestaan:</span><span class="sxs-lookup"><span data-stu-id="dfed8-196">A specific number of characters are permitted before and after the at sign (@), as follows:</span></span>
  - <span data-ttu-id="dfed8-197">Maximum aantal tekens voor de gebruikersnaam die zich vóór het bijteken (@): 64</span><span class="sxs-lookup"><span data-stu-id="dfed8-197">Maximum number of characters for the username that is in front of the at sign (@): 64</span></span>
  - <span data-ttu-id="dfed8-198">Maximum aantal tekens voor de domeinnaam na het bijteken (@): 48</span><span class="sxs-lookup"><span data-stu-id="dfed8-198">Maximum number of characters for the domain name following the at sign (@): 48</span></span>
  - <span data-ttu-id="dfed8-199">Ongeldige tekens: \ % &amp; \* + / = ?</span><span class="sxs-lookup"><span data-stu-id="dfed8-199">Invalid characters: \ % &amp; \* + / = ?</span></span> <span data-ttu-id="dfed8-200">{ } | \< \> ( ) ; : , [ ] "</span><span class="sxs-lookup"><span data-stu-id="dfed8-200">{ } | \< \> ( ) ; : , [ ] "</span></span>
  - <span data-ttu-id="dfed8-201">Tekens toegestaan: A – Z, a - z, 0 – 9, ' .</span><span class="sxs-lookup"><span data-stu-id="dfed8-201">Characters allowed: A – Z, a - z, 0 – 9, ' .</span></span> <span data-ttu-id="dfed8-202">- _ !</span><span class="sxs-lookup"><span data-stu-id="dfed8-202">- _ !</span></span> <span data-ttu-id="dfed8-203"># ^ ~</span><span class="sxs-lookup"><span data-stu-id="dfed8-203"># ^ ~</span></span>
  - <span data-ttu-id="dfed8-204">Letters met diakritische tekens, zoals umlauts, accenten en tildes, zijn ongeldige tekens.</span><span class="sxs-lookup"><span data-stu-id="dfed8-204">Letters with diacritical marks, such as umlauts, accents, and tildes, are invalid characters.</span></span>
  - <span data-ttu-id="dfed8-205">Het @-teken is vereist voor elke **gebruikerPrincipalName-waarde.**</span><span class="sxs-lookup"><span data-stu-id="dfed8-205">The @ character is required in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="dfed8-206">Het @-teken kan niet het eerste teken zijn in elke **gebruikerPrincipalName-waarde.**</span><span class="sxs-lookup"><span data-stu-id="dfed8-206">The @ character cannot be the first character in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="dfed8-207">De gebruikersnaam kan niet eindigen met een punt (.), een ampersand ( &amp; ), een spatie of een bijteken (@).</span><span class="sxs-lookup"><span data-stu-id="dfed8-207">The username cannot end with a period (.), an ampersand (&amp;), a space, or an at sign (@).</span></span>
  - <span data-ttu-id="dfed8-208">De gebruikersnaam mag geen spaties bevatten.</span><span class="sxs-lookup"><span data-stu-id="dfed8-208">The username cannot contain any spaces.</span></span>
  - <span data-ttu-id="dfed8-209">Routable domains must be used; lokale of interne domeinen kunnen bijvoorbeeld niet worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="dfed8-209">Routable domains must be used; for example, local or internal domains cannot be used.</span></span>
  - <span data-ttu-id="dfed8-210">Unicode wordt geconverteerd naar onderstrepingstekens.</span><span class="sxs-lookup"><span data-stu-id="dfed8-210">Unicode is converted to underscore characters.</span></span>
  - <span data-ttu-id="dfed8-211">**userPrincipalName** mag geen dubbele waarden in de adreslijst bevatten.</span><span class="sxs-lookup"><span data-stu-id="dfed8-211">**userPrincipalName** cannot contain any duplicate values in the directory.</span></span>

## <a name="3-prepare-the-userprincipalname-attribute"></a><span data-ttu-id="dfed8-212">3. Het userPrincipalName-kenmerk voorbereiden</span><span class="sxs-lookup"><span data-stu-id="dfed8-212">3. Prepare the userPrincipalName attribute</span></span>

<span data-ttu-id="dfed8-213">Active Directory is zo ontworpen dat eindgebruikers in uw organisatie zich kunnen aanmelden bij uw adreslijst met **sAMAccountName** of **userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="dfed8-213">Active Directory is designed to allow the end users in your organization to sign in to your directory by using either **sAMAccountName** or **userPrincipalName**.</span></span> <span data-ttu-id="dfed8-214">Op dezelfde manier kunnen eindgebruikers zich aanmelden bij Microsoft 365 met de gebruikersnaam (UPN) van hun werk- of schoolaccount.</span><span class="sxs-lookup"><span data-stu-id="dfed8-214">Similarly, end users can sign in to Microsoft 365 by using the user principal name (UPN) of their work or school account.</span></span> <span data-ttu-id="dfed8-215">Adreslijstsynchronisatie probeert nieuwe gebruikers te maken in Azure Active Directory met dezelfde UPN als in uw AD DS.</span><span class="sxs-lookup"><span data-stu-id="dfed8-215">Directory synchronization attempts to create new users in Azure Active Directory by using the same UPN that's in your AD DS.</span></span> <span data-ttu-id="dfed8-216">De UPN is opgemaakt als een e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="dfed8-216">The UPN is formatted like an email address.</span></span>

<span data-ttu-id="dfed8-217">In Microsoft 365 is de UPN het standaardkenmerk dat wordt gebruikt om het e-mailadres te genereren.</span><span class="sxs-lookup"><span data-stu-id="dfed8-217">In Microsoft 365, the UPN is the default attribute that's used to generate the email address.</span></span> <span data-ttu-id="dfed8-218">Het is eenvoudig om **userPrincipalName** (in AD DS en in Azure AD) en het primaire e-mailadres in **proxyAddresses** op verschillende waarden in te stellen.</span><span class="sxs-lookup"><span data-stu-id="dfed8-218">It's easy to get **userPrincipalName** (in AD DS and in Azure AD) and the primary email address in **proxyAddresses** set to different values.</span></span> <span data-ttu-id="dfed8-219">Wanneer ze zijn ingesteld op verschillende waarden, kan er verwarring ontstaan voor beheerders en eindgebruikers.</span><span class="sxs-lookup"><span data-stu-id="dfed8-219">When they are set to different values, there can be confusion for administrators and end users.</span></span>

<span data-ttu-id="dfed8-220">U kunt deze kenmerken het beste uitlijnen om verwarring te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="dfed8-220">It's best to align these attributes to reduce confusion.</span></span> <span data-ttu-id="dfed8-221">Als u wilt voldoen aan de vereisten van één aanmelding met Ad FS 2.0 (Active Directory Federation Services), moet u ervoor zorgen dat de UPN's in Azure Active Directory en uw AD DS overeenkomen en een geldige domeinnaamruimte gebruiken.</span><span class="sxs-lookup"><span data-stu-id="dfed8-221">To meet the requirements of single sign-on with Active Directory Federation Services (AD FS) 2.0, you need to ensure that the UPNs in Azure Active Directory and your AD DS match and are using a valid domain namespace.</span></span>

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a><span data-ttu-id="dfed8-222">4. Een alternatief UPN-achtervoegsel toevoegen aan AD DS</span><span class="sxs-lookup"><span data-stu-id="dfed8-222">4. Add an alternative UPN suffix to AD DS</span></span>

<span data-ttu-id="dfed8-223">Mogelijk moet u een alternatief UPN-achtervoegsel toevoegen om de bedrijfsreferenties van de gebruiker te koppelen aan de Microsoft 365 omgeving.</span><span class="sxs-lookup"><span data-stu-id="dfed8-223">You may need to add an alternative UPN suffix to associate the user's corporate credentials with the Microsoft 365 environment.</span></span> <span data-ttu-id="dfed8-224">Een UPN-achtervoegsel is het deel van een UPN rechts van het @-teken.</span><span class="sxs-lookup"><span data-stu-id="dfed8-224">A UPN suffix is the part of a UPN to the right of the @ character.</span></span> <span data-ttu-id="dfed8-225">UPN's die worden gebruikt voor een enkele aanmelding kunnen letters, cijfers, perioden, streepjes en onderstrepingstekens bevatten, maar geen andere typen tekens.</span><span class="sxs-lookup"><span data-stu-id="dfed8-225">UPNs that are used for single sign-on can contain letters, numbers, periods, dashes, and underscores, but no other types of characters.</span></span>

<span data-ttu-id="dfed8-226">Zie Voorbereiden op [adreslijstsynchronisatie]( https://go.microsoft.com/fwlink/p/?LinkId=525430)voor meer informatie over het toevoegen van een alternatief UPN-achtervoegsel aan Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dfed8-226">For more information on how to add an alternative UPN suffix to Active Directory, see [Prepare for directory synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span></span>

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a><span data-ttu-id="dfed8-227">5. Koppel de AD DS UPN aan de Microsoft 365 UPN</span><span class="sxs-lookup"><span data-stu-id="dfed8-227">5. Match the AD DS UPN with the Microsoft 365 UPN</span></span>

<span data-ttu-id="dfed8-228">Als u adreslijstsynchronisatie al hebt ingesteld, komt de UPN voor Microsoft 365 van de gebruiker mogelijk niet overeen met de AD DS UPN van de gebruiker die is gedefinieerd in uw AD DS.</span><span class="sxs-lookup"><span data-stu-id="dfed8-228">If you've already set up directory synchronization, the user's UPN for Microsoft 365 may not match the user's AD DS UPN that's defined in your AD DS.</span></span> <span data-ttu-id="dfed8-229">Dit kan gebeuren wanneer aan een gebruiker een licentie is toegewezen voordat het domein is geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="dfed8-229">This can occur when a user was assigned a license before the domain was verified.</span></span> <span data-ttu-id="dfed8-230">Als u dit wilt oplossen, [gebruikt u PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396730) om dubbele UPN op te lossen om de UPN van de gebruiker bij te werken om ervoor te zorgen dat de Microsoft 365 UPN overeenkomt met de zakelijke gebruikersnaam en het domein.</span><span class="sxs-lookup"><span data-stu-id="dfed8-230">To fix this, use [PowerShell to fix duplicate UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) to update the user's UPN to ensure that the Microsoft 365 UPN matches the corporate user name and domain.</span></span> <span data-ttu-id="dfed8-231">Als u de UPN in de AD DS bij wilt werken en deze wilt synchroniseren met de Azure Active Directory-identiteit, moet u de licentie van de gebruiker in Microsoft 365 verwijderen voordat u de wijzigingen in AD DS aan gaat brengen.</span><span class="sxs-lookup"><span data-stu-id="dfed8-231">If you are updating the UPN in the AD DS and would like it to synchronize with the Azure Active Directory identity, you need to remove the user's license in Microsoft 365 prior to making the changes in AD DS.</span></span>

<span data-ttu-id="dfed8-232">Zie Ook [Een niet-routable domain (zoals .local domain) voorbereiden voor adreslijstsynchronisatie.](prepare-a-non-routable-domain-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="dfed8-232">Also see [How to prepare a non-routable domain (such as .local domain) for directory synchronization](prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="dfed8-233">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="dfed8-233">Next steps</span></span>

<span data-ttu-id="dfed8-234">Zie Adreslijstsynchronisatie instellen als u stappen 1 tot en met 5 [hierboven hebt uitgevoerd.](set-up-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="dfed8-234">If you have done steps 1 through 5 above, see [Set up directory synchronization](set-up-directory-synchronization.md).</span></span>
