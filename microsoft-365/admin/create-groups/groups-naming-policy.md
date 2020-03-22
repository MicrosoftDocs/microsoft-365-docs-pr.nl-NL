---
title: Naamgevingsbeleid voor Office 365-groepen
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Meer informatie over het maken van een naamgevingsbeleid voor Office 365-groepen.
ms.openlocfilehash: 4325a5e0a1de0c3a83be71220abd256c204ec07d
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894621"
---
# <a name="office-365-groups-naming-policy"></a><span data-ttu-id="6a681-103">Naamgevingsbeleid voor Office 365-groepen</span><span class="sxs-lookup"><span data-stu-id="6a681-103">Office 365 Groups naming policy</span></span>

<span data-ttu-id="6a681-104">U gebruikt een groepsnaamgevingsbeleid om een consistente naamgevingsstrategie af te dwingen voor groepen die zijn gemaakt door gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="6a681-104">You use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="6a681-105">Met een naamgevingsbeleid kunnen u en uw gebruikers de functie van de groep, het lidmaatschap, de geografische regio of de groep identificeren.</span><span class="sxs-lookup"><span data-stu-id="6a681-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="6a681-106">Het naamgevingsbeleid kan ook helpen bij het categoriseren van groepen in het adresboek.</span><span class="sxs-lookup"><span data-stu-id="6a681-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="6a681-107">U het beleid gebruiken om te voorkomen dat specifieke woorden worden gebruikt in groepsnamen en aliassen.</span><span class="sxs-lookup"><span data-stu-id="6a681-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="6a681-108">Het naamgevingsbeleid wordt toegepast op groepen die zijn gemaakt voor alle groepenworkloads (zoals Outlook, Microsoft Teams, SharePoint, Planner, Yammer, enz.).</span><span class="sxs-lookup"><span data-stu-id="6a681-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="6a681-109">Het wordt toegepast op zowel de groepsnaam als de groepsalias.</span><span class="sxs-lookup"><span data-stu-id="6a681-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="6a681-110">Het wordt toegepast wanneer een gebruiker een groep maakt en wanneer groepsnaam of alias wordt bewerkt voor een bestaande groep.</span><span class="sxs-lookup"><span data-stu-id="6a681-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="6a681-111">Een office 365-groepsnaamgevingsbeleid is alleen van toepassing op Office 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="6a681-111">An Office 365 group naming policy only applies to Office 365 groups.</span></span> <span data-ttu-id="6a681-112">Dit geldt niet voor distributiegroepen die zijn gemaakt in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6a681-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="6a681-113">Zie [Een distributiegroepnaamgevingsbeleid maken](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)als u een naamgevingsbeleid voor distributiegroepen wilt maken.</span><span class="sxs-lookup"><span data-stu-id="6a681-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="6a681-114">Het groepsnaambeleid bestaat uit de volgende functie:</span><span class="sxs-lookup"><span data-stu-id="6a681-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="6a681-115">**Naamgevingsbeleid voor voorvoegsel:** U voorvoegsels of achtervoegsels gebruiken om de\_naamgevingsconventie van groepen te definiëren (bijvoorbeeld: 'US My Group\_Engineering').</span><span class="sxs-lookup"><span data-stu-id="6a681-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="6a681-116">De voorvoegsels/achtervoegsels kunnen bestaan uit vaste tekenreeksen of gebruikerskenmerken (zoals [Department]) die worden vervangen op basis van de gebruiker die de groep maakt.</span><span class="sxs-lookup"><span data-stu-id="6a681-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="6a681-117">**Aangepaste geblokkeerde woorden:** u een reeks geblokkeerde woorden uploaden die specifiek zijn voor uw organisatie en die worden geblokkeerd in groepen die door gebruikers zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="6a681-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="6a681-118">(Bijvoorbeeld: "CEO, Payroll, HR").</span><span class="sxs-lookup"><span data-stu-id="6a681-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="6a681-119">Licentievereisten</span><span class="sxs-lookup"><span data-stu-id="6a681-119">Licensing requirements</span></span>

<span data-ttu-id="6a681-120">Voor het gebruik van Azure AD-naamgevingsbeleid voor Office 365-groepen moet u een Azure Active Directory Premium P1-licentie of Azure AD Basic EDU-licentie toewijzen voor elke unieke gebruiker (inclusief gasten) die lid is van een of meer Office 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="6a681-120">Using Azure AD naming policy for Office 365 groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Office 365 groups.</span></span>

<span data-ttu-id="6a681-121">Dit is ook vereist voor de beheerder die het naamgevingsbeleid Groepen maakt.</span><span class="sxs-lookup"><span data-stu-id="6a681-121">This is also required for the administrator that creates the Groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="6a681-122">Naamgevingsbeleid voor voorvoegsel</span><span class="sxs-lookup"><span data-stu-id="6a681-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="6a681-123">Voorvoegsels en achtervoegsels kunnen vaste tekenreeksen of gebruikerskenmerken zijn.</span><span class="sxs-lookup"><span data-stu-id="6a681-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="6a681-124">Vaste tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="6a681-124">Fixed strings</span></span>

<span data-ttu-id="6a681-125">U korte tekenreeksen gebruiken waarmee u groepen in de GAL en de linkernavigatie van de groepsworkloads onderscheiden.</span><span class="sxs-lookup"><span data-stu-id="6a681-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="6a681-126">Enkele van de veelvoorkomende voorvoegsels zijn trefwoorden\_zoals 'Grp Name', 'Name',\#'Name'\_</span><span class="sxs-lookup"><span data-stu-id="6a681-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="6a681-127">Kenmerken</span><span class="sxs-lookup"><span data-stu-id="6a681-127">Attributes</span></span>

<span data-ttu-id="6a681-128">U kenmerken gebruiken waarmee u bepalen wie de groep heeft gemaakt, zoals [Afdeling] en waar deze is gemaakt vanuit een als volgt [Land].</span><span class="sxs-lookup"><span data-stu-id="6a681-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6a681-129">**Voorbeelden**</span><span class="sxs-lookup"><span data-stu-id="6a681-129">**Examples**</span></span>|<span data-ttu-id="6a681-130">Beleid = "GRP [GroupName] [Department]"</span><span class="sxs-lookup"><span data-stu-id="6a681-130">Policy = "GRP [GroupName] [Department]"</span></span>|
||<span data-ttu-id="6a681-131">Afdeling van de gebruiker = Engineering</span><span class="sxs-lookup"><span data-stu-id="6a681-131">User's department = Engineering</span></span>|
||<span data-ttu-id="6a681-132">Gemaakte groepsnaam = "GRP My Group Engineering"</span><span class="sxs-lookup"><span data-stu-id="6a681-132">Created group name = "GRP My Group Engineering"</span></span>|

<span data-ttu-id="6a681-133">Ondersteunde Azure Active Directory (Azure AD)-kenmerken zijn [Afdeling], [Bedrijf], [Office], [StateOrProvince], [CountryOrRegion] en [Titel].</span><span class="sxs-lookup"><span data-stu-id="6a681-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="6a681-p107">Niet-ondersteunde gebruikerskenmerken worden als vaste tekenreeksen beschouwd. Bijvoorbeeld "[postalCode]"</span><span class="sxs-lookup"><span data-stu-id="6a681-p107">Unsupported user attributes are considered as fixed strings. E.g. "[postalCode]"</span></span>

- <span data-ttu-id="6a681-137">Extensiekenmerken en aangepaste kenmerken worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="6a681-137">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="6a681-138">Het wordt aangeraden kenmerken te gebruiken met waarden die voor alle gebruikers in uw organisatie zijn ingevuld en geen kenmerken met lange waarden te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6a681-138">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="6a681-139">Dingen om op te letten</span><span class="sxs-lookup"><span data-stu-id="6a681-139">Things to look out for</span></span>

- <span data-ttu-id="6a681-140">Bij het maken van beleid mag de totale tekenreekslengte van voor- en achtervoegsel niet langer zijn dan 53 tekens.</span><span class="sxs-lookup"><span data-stu-id="6a681-140">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="6a681-141">Voor- en achtervoegsels kunnen speciale tekens bevatten die voor de groepsnaam en de groepsalias worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="6a681-141">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="6a681-142">Wanneer de voorvoegsels en achtervoegsels speciale tekens bevatten die niet zijn toegestaan in de groepsalias, worden ze alleen toegepast op de groepsnaam.</span><span class="sxs-lookup"><span data-stu-id="6a681-142">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="6a681-143">In dit geval zouden de voor- en achtervoegsels die op de groepsnaam worden toegepast verschillen van degene die op de groepsalias worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="6a681-143">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

- <span data-ttu-id="6a681-144">Als u met Yammer Office 365 verbonden groepen gebruikt, gebruikt u \# \[de \] \<volgende \>tekens in uw naamgevingsbeleid: @, , , , en .</span><span class="sxs-lookup"><span data-stu-id="6a681-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="6a681-145">Als deze tekens in het naamgevingsbeleid staan, kunnen gewone Yammer-gebruikers geen groepen maken.</span><span class="sxs-lookup"><span data-stu-id="6a681-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="6a681-146">Aangepaste geblokkeerde woorden</span><span class="sxs-lookup"><span data-stu-id="6a681-146">Custom blocked words</span></span>

<span data-ttu-id="6a681-147">U een door komma gescheiden lijst met geblokkeerde woorden invoeren die worden geblokkeerd in groepsnamen en aliassen.</span><span class="sxs-lookup"><span data-stu-id="6a681-147">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="6a681-148">Er worden geen subtekenreekszoekopdrachten uitgevoerd; in het bijzonder, een exacte overeenkomst tussen de gebruiker ingevoerde naam en de aangepaste geblokkeerde woorden is vereist om een fout te activeren.</span><span class="sxs-lookup"><span data-stu-id="6a681-148">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span> <span data-ttu-id="6a681-149">Subtekenreekszoeken wordt niet gedaan, zodat gebruikers enkele van de algemene woorden als 'Klasse' kunnen gebruiken, zelfs als 'kont' een geblokkeerd woord is.</span><span class="sxs-lookup"><span data-stu-id="6a681-149">Sub-string search isn't done so that users can use some of the common words like 'Class' even if 'ass' is a blocked word.</span></span>

<span data-ttu-id="6a681-150">**Dingen om op te letten:**</span><span class="sxs-lookup"><span data-stu-id="6a681-150">**Things to look out for**:</span></span>

- <span data-ttu-id="6a681-151">De geblokkeerde woorden zijn hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="6a681-151">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="6a681-152">Als er een geblokkeerd woord wordt ingevoerd, wordt een foutbericht met het geblokkeerde woord erin weergegeven.</span><span class="sxs-lookup"><span data-stu-id="6a681-152">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="6a681-153">Er bestaan geen restricties op tekens in het gebruikte geblokkeerde woord.</span><span class="sxs-lookup"><span data-stu-id="6a681-153">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="6a681-154">Er is een limiet van 5000 woorden die kunnen worden ingesteld als geblokkeerde woorden.</span><span class="sxs-lookup"><span data-stu-id="6a681-154">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="6a681-155">Overschrijven door beheerder</span><span class="sxs-lookup"><span data-stu-id="6a681-155">Admin override</span></span>

<span data-ttu-id="6a681-p111">Bepaalde beheerders zijn voor alle groepswerkbelastingen en eindpunten vrijgesteld van dit beleid, zodat ze groepen kunnen maken met deze geblokkeerde woorden en met eigen naamgevingsconventies. Hierna volgt een lijst van beheerdersrollen die zijn vrijgesteld van het groepsnaambeleid.</span><span class="sxs-lookup"><span data-stu-id="6a681-p111">Selective administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions. The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="6a681-158">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="6a681-158">Global admin</span></span>

- <span data-ttu-id="6a681-159">Partnerondersteuning voor laag 1</span><span class="sxs-lookup"><span data-stu-id="6a681-159">Partner Tier 1 Support</span></span>

- <span data-ttu-id="6a681-160">Partnerondersteuning voor laag 2</span><span class="sxs-lookup"><span data-stu-id="6a681-160">Partner Tier 2 Support</span></span>

- <span data-ttu-id="6a681-161">Beheerder van het gebruikersaccount</span><span class="sxs-lookup"><span data-stu-id="6a681-161">User account admin</span></span>

- <span data-ttu-id="6a681-162">Schrijvers van adreslijsten</span><span class="sxs-lookup"><span data-stu-id="6a681-162">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="6a681-163">Het naamgevingsbeleid instellen</span><span class="sxs-lookup"><span data-stu-id="6a681-163">How to set up the naming policy</span></span>

<span data-ttu-id="6a681-164">Ga als u een naamgevingsbeleid instelt:</span><span class="sxs-lookup"><span data-stu-id="6a681-164">To set up a naming policy:</span></span>

1. <span data-ttu-id="6a681-165">Klik in [Azure Active Directory](https://aad.portal.azure.com)onder **Beheren**op **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="6a681-165">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="6a681-166">Klik **onder Instellingen**op **Naamgevingsbeleid**.</span><span class="sxs-lookup"><span data-stu-id="6a681-166">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="6a681-167">Kies het tabblad **Beleid voor groepsnaamgeving.**</span><span class="sxs-lookup"><span data-stu-id="6a681-167">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="6a681-168">Kies **onder Huidig beleid**of u een voorvoegsel of achtervoegsel of beide wilt vereisen en schakel de juiste selectievakjes in.</span><span class="sxs-lookup"><span data-stu-id="6a681-168">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="6a681-169">Kies tussen **Kenmerk** en **Tekenreeks** voor elke regel en geef vervolgens het kenmerk of de tekenreeks op.</span><span class="sxs-lookup"><span data-stu-id="6a681-169">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="6a681-170">Wanneer u de voorvoegsels en achtervoegsels hebt toegevoegd die u nodig hebt, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6a681-170">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Schermafbeelding van de beleidsinstellingen voor groepsnaamgeving in Azure Active Directory](../../media/groups-naming-policy-azure.png)

> [!NOTE]
> <span data-ttu-id="6a681-172">StaffHub-teams volgen het naamgevingsbeleid niet, maar de onderliggende Office 365-groep wel.</span><span class="sxs-lookup"><span data-stu-id="6a681-172">StaffHub teams do not follow the naming policy, but the underlying Office 365 group does.</span></span> <span data-ttu-id="6a681-173">De teamnaam van StaffHub past de voorvoegsels en achtervoegsels niet toe en controleert niet op aangepaste geblokkeerde woorden.</span><span class="sxs-lookup"><span data-stu-id="6a681-173">StaffHub team name does not apply the prefixes and suffixes and does not check for custom blocked words.</span></span> <span data-ttu-id="6a681-174">Maar StaffHub past de voorvoegsels en achtervoegsels toe en verwijdert geblokkeerde woorden uit de onderliggende Office 365-groep.</span><span class="sxs-lookup"><span data-stu-id="6a681-174">But StaffHub does apply the prefixes and suffixes and removes blocked words from the underlying Office 365 group.</span></span>

## <a name="more-articles-on-naming-policy"></a><span data-ttu-id="6a681-175">Meer artikelen over naamgevingsbeleid</span><span class="sxs-lookup"><span data-stu-id="6a681-175">More articles on naming policy</span></span>

[<span data-ttu-id="6a681-176">Een naamgevingsbeleid afdwingen voor Office 365-groepen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6a681-176">Enforce a naming policy for Office 365 groups in Azure Active Directory</span></span>](https://go.microsoft.com/fwlink/?linkid=868340)

[<span data-ttu-id="6a681-177">Azure Active Directory-cmdlets voor het configureren van groepsinstellingen</span><span class="sxs-lookup"><span data-stu-id="6a681-177">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
