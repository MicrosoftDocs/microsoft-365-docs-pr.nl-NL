---
title: Naamgevingsbeleid voor groepen
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Meer informatie over het maken van een naamgevingsbeleid voor Microsoft 365-groepen.
ms.openlocfilehash: ae216d0d8f3319e9633d300d785b4a8c31702798
ms.sourcegitcommit: 3274b65a3932288721541d2b3fa5ecbf4c51e1ab
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2020
ms.locfileid: "44702546"
---
# <a name="groups-naming-policy"></a><span data-ttu-id="60787-103">Naamgevingsbeleid voor groepen</span><span class="sxs-lookup"><span data-stu-id="60787-103">Groups naming policy</span></span>

<span data-ttu-id="60787-104">U gebruikt een beleid voor groepsnaamgeving om een consistente naamgevingsstrategie af te dwingen voor groepen die zijn gemaakt door gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="60787-104">You use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="60787-105">Met een naamgevingsbeleid kunnen u en uw gebruikers de functie van de groep, het lidmaatschap, de geografische regio of de groep identificeren.</span><span class="sxs-lookup"><span data-stu-id="60787-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="60787-106">Het naamgevingsbeleid kan ook helpen bij het categoriseren van groepen in het adresboek.</span><span class="sxs-lookup"><span data-stu-id="60787-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="60787-107">U het beleid gebruiken om te voorkomen dat specifieke woorden worden gebruikt in groepsnamen en aliassen.</span><span class="sxs-lookup"><span data-stu-id="60787-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="60787-108">Het naamgevingsbeleid wordt toegepast op groepen die zijn gemaakt voor alle groepswerkbelastingen (zoals Outlook, Microsoft Teams, SharePoint, Planner, Yammer, enz.).</span><span class="sxs-lookup"><span data-stu-id="60787-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="60787-109">Het wordt toegepast op zowel de groepsnaam als de groepsalias.</span><span class="sxs-lookup"><span data-stu-id="60787-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="60787-110">Het wordt toegepast wanneer een gebruiker een groep maakt en wanneer groepsnaam of alias wordt bewerkt voor een bestaande groep.</span><span class="sxs-lookup"><span data-stu-id="60787-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="60787-111">Een microsoft 365-groepnaamgevingsbeleid is alleen van toepassing op Microsoft 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="60787-111">A Microsoft 365 group naming policy only applies to Microsoft 365 groups.</span></span> <span data-ttu-id="60787-112">Het is niet van toepassing op distributiegroepen die zijn gemaakt in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="60787-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="60787-113">Zie Een [naamgevingsbeleid voor distributiegroepen maken als](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)u een naamgevingsbeleid voor distributiegroepen wilt maken.</span><span class="sxs-lookup"><span data-stu-id="60787-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="60787-114">Het groepsnaambeleid bestaat uit de volgende functie:</span><span class="sxs-lookup"><span data-stu-id="60787-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="60787-115">**Voorvoegsel-achtervoegsel naamgevingsbeleid**: U voorvoegsels of achtervoegsels gebruiken om de naamgevingsconventie van groepen te definiëren (bijvoorbeeld: US \_ My Group \_ Engineering).</span><span class="sxs-lookup"><span data-stu-id="60787-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="60787-116">De voorvoegsels/achtervoegsels kunnen bestaan uit vaste tekenreeksen of gebruikerskenmerken (zoals [Department]) die worden vervangen op basis van de gebruiker die de groep maakt.</span><span class="sxs-lookup"><span data-stu-id="60787-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="60787-117">**Aangepaste geblokkeerde woorden:** u een set geblokkeerde woorden uploaden die specifiek zijn voor uw organisatie en die worden geblokkeerd in groepen die door gebruikers zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="60787-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="60787-118">(Bijvoorbeeld: "CEO, Payroll, HR").</span><span class="sxs-lookup"><span data-stu-id="60787-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="60787-119">Vergunningsvereisten</span><span class="sxs-lookup"><span data-stu-id="60787-119">Licensing requirements</span></span>

<span data-ttu-id="60787-120">Als u azure AD-naamgevingsbeleid voor Microsoft 365-groepen gebruikt, moet u een Azure Active Directory Premium P1-licentie of Azure AD AD EDU-licentie voor elke unieke gebruiker (inclusief gasten) die lid is van een of meer Microsoft 365-groepen, beschikken, maar niet noodzakelijkerwijs toewijzen.</span><span class="sxs-lookup"><span data-stu-id="60787-120">Using Azure AD naming policy for Microsoft 365 groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="60787-121">Dit is ook vereist voor de beheerder die het naamgevingsbeleid groepen maakt.</span><span class="sxs-lookup"><span data-stu-id="60787-121">This is also required for the administrator that creates the Groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="60787-122">Beleid voor naamgevingsbeleid voor voorvoegsel</span><span class="sxs-lookup"><span data-stu-id="60787-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="60787-123">Voorvoegsels en achtervoegsels kunnen vaste tekenreeksen of gebruikerskenmerken zijn.</span><span class="sxs-lookup"><span data-stu-id="60787-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="60787-124">Vaste tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="60787-124">Fixed strings</span></span>

<span data-ttu-id="60787-125">U korte tekenreeksen gebruiken waarmee u groepen onderscheiden in de GAL- en linkernavigatie van de groepsworkloads.</span><span class="sxs-lookup"><span data-stu-id="60787-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="60787-126">Enkele van de gemeenschappelijke voorvoegsels achtervoegsels zijn zoekwoorden als 'Grp \_ Name' , \# 'Name', \_ 'Name'</span><span class="sxs-lookup"><span data-stu-id="60787-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="60787-127">Kenmerken</span><span class="sxs-lookup"><span data-stu-id="60787-127">Attributes</span></span>

<span data-ttu-id="60787-128">U kenmerken gebruiken waarmee u bepalen wie de groep heeft gemaakt, zoals [Afdeling] en waar deze is gemaakt vanuit like [Land].</span><span class="sxs-lookup"><span data-stu-id="60787-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="60787-129">**Voorbeelden**</span><span class="sxs-lookup"><span data-stu-id="60787-129">**Examples**</span></span>|<span data-ttu-id="60787-130">Beleid = "GRP [GroupName] [Department]"</span><span class="sxs-lookup"><span data-stu-id="60787-130">Policy = "GRP [GroupName] [Department]"</span></span>|
||<span data-ttu-id="60787-131">Afdeling van de gebruiker = Engineering</span><span class="sxs-lookup"><span data-stu-id="60787-131">User's department = Engineering</span></span>|
||<span data-ttu-id="60787-132">Gemaakte groepsnaam = "GRP My Group Engineering"</span><span class="sxs-lookup"><span data-stu-id="60787-132">Created group name = "GRP My Group Engineering"</span></span>|

<span data-ttu-id="60787-133">Ondersteunde Azure Active Directory (Azure AD) kenmerken zijn [Afdeling], [Bedrijf], [Office], [StateOrProvince], [CountryOrRegion], en [Titel].</span><span class="sxs-lookup"><span data-stu-id="60787-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="60787-p107">Niet-ondersteunde gebruikerskenmerken worden als vaste tekenreeksen beschouwd. Bijvoorbeeld "[postalCode]"</span><span class="sxs-lookup"><span data-stu-id="60787-p107">Unsupported user attributes are considered as fixed strings. E.g. "[postalCode]"</span></span>

- <span data-ttu-id="60787-137">Extensiekenmerken en aangepaste kenmerken worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="60787-137">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="60787-138">Het wordt aangeraden kenmerken te gebruiken met waarden die voor alle gebruikers in uw organisatie zijn ingevuld en geen kenmerken met lange waarden te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="60787-138">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="60787-139">Dingen om op te letten</span><span class="sxs-lookup"><span data-stu-id="60787-139">Things to look out for</span></span>

- <span data-ttu-id="60787-140">Bij het maken van beleid mag de totale tekenreekslengte van voor- en achtervoegsel niet langer zijn dan 53 tekens.</span><span class="sxs-lookup"><span data-stu-id="60787-140">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="60787-141">Voor- en achtervoegsels kunnen speciale tekens bevatten die voor de groepsnaam en de groepsalias worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="60787-141">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="60787-142">Wanneer de voorvoegsels en achtervoegsels speciale tekens bevatten die niet zijn toegestaan in de groepsalias, worden ze alleen toegepast op de groepsnaam.</span><span class="sxs-lookup"><span data-stu-id="60787-142">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="60787-143">In dit geval zouden de voor- en achtervoegsels die op de groepsnaam worden toegepast verschillen van degene die op de groepsalias worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="60787-143">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

  > [!NOTE]
  > <span data-ttu-id="60787-144">Een periode (.) of een koppelteken (-) is overal in de groepsnaam toegestaan, behalve aan het begin of einde van de naam.</span><span class="sxs-lookup"><span data-stu-id="60787-144">A period (.) or a hyphen (-) is permitted anywhere in the group name, except at the beginning or end of the name.</span></span> <span data-ttu-id="60787-145">Een underscore (_) is overal in de groepsnaam toegestaan, ook aan het begin of einde van de naam.</span><span class="sxs-lookup"><span data-stu-id="60787-145">An underscore (_) is permitted anywhere in the group name, including at the beginning or end of the name.</span></span>

- <span data-ttu-id="60787-146">Als u verbonden yammer Microsoft 365-verbonden groepen gebruikt, vermijd dan het gebruik van de volgende tekens in uw naamgevingsbeleid: @, \# , , , , \[ \] \<, and \> .</span><span class="sxs-lookup"><span data-stu-id="60787-146">If you are using Yammer Microsoft 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="60787-147">Als deze tekens in het naamgevingsbeleid staan, kunnen gewone Yammer-gebruikers geen groepen maken.</span><span class="sxs-lookup"><span data-stu-id="60787-147">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="60787-148">Aangepaste geblokkeerde woorden</span><span class="sxs-lookup"><span data-stu-id="60787-148">Custom blocked words</span></span>

<span data-ttu-id="60787-149">U een lijst met geblokkeerde woorden invoeren die worden geblokkeerd in groepsnamen en aliassen.</span><span class="sxs-lookup"><span data-stu-id="60787-149">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="60787-150">Er worden geen subreekszoekopdrachten uitgevoerd; specifiek, een exacte overeenkomst tussen de gebruiker ingevoerde naam en de aangepaste geblokkeerde woorden is vereist om een fout te activeren.</span><span class="sxs-lookup"><span data-stu-id="60787-150">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span> <span data-ttu-id="60787-151">Sub-string zoeken wordt niet gedaan, zodat gebruikers kunnen een aantal van de gemeenschappelijke woorden zoals 'Klasse' te gebruiken, zelfs als 'kont' is een geblokkeerd woord.</span><span class="sxs-lookup"><span data-stu-id="60787-151">Sub-string search isn't done so that users can use some of the common words like 'Class' even if 'ass' is a blocked word.</span></span>

<span data-ttu-id="60787-152">**Dingen om op te letten:**</span><span class="sxs-lookup"><span data-stu-id="60787-152">**Things to look out for**:</span></span>

- <span data-ttu-id="60787-153">De geblokkeerde woorden zijn hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="60787-153">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="60787-154">Als er een geblokkeerd woord wordt ingevoerd, wordt een foutbericht met het geblokkeerde woord erin weergegeven.</span><span class="sxs-lookup"><span data-stu-id="60787-154">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="60787-155">Er bestaan geen restricties op tekens in het gebruikte geblokkeerde woord.</span><span class="sxs-lookup"><span data-stu-id="60787-155">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="60787-156">Er is een limiet van 5000 woorden die kunnen worden ingesteld als geblokkeerde woorden.</span><span class="sxs-lookup"><span data-stu-id="60787-156">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="60787-157">Overschrijven door beheerder</span><span class="sxs-lookup"><span data-stu-id="60787-157">Admin override</span></span>

<span data-ttu-id="60787-p112">Bepaalde beheerders zijn voor alle groepswerkbelastingen en eindpunten vrijgesteld van dit beleid, zodat ze groepen kunnen maken met deze geblokkeerde woorden en met eigen naamgevingsconventies. Hierna volgt een lijst van beheerdersrollen die zijn vrijgesteld van het groepsnaambeleid.</span><span class="sxs-lookup"><span data-stu-id="60787-p112">Selective administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions. The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="60787-160">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="60787-160">Global admin</span></span>

- <span data-ttu-id="60787-161">Partnerondersteuning voor laag 1</span><span class="sxs-lookup"><span data-stu-id="60787-161">Partner Tier 1 Support</span></span>

- <span data-ttu-id="60787-162">Partnerondersteuning voor laag 2</span><span class="sxs-lookup"><span data-stu-id="60787-162">Partner Tier 2 Support</span></span>

- <span data-ttu-id="60787-163">Beheerder van het gebruikersaccount</span><span class="sxs-lookup"><span data-stu-id="60787-163">User account admin</span></span>

- <span data-ttu-id="60787-164">Schrijvers van adreslijsten</span><span class="sxs-lookup"><span data-stu-id="60787-164">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="60787-165">Het naamgevingsbeleid instellen</span><span class="sxs-lookup"><span data-stu-id="60787-165">How to set up the naming policy</span></span>

<span data-ttu-id="60787-166">Ga als u een naamgevingsbeleid instellen:</span><span class="sxs-lookup"><span data-stu-id="60787-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="60787-167">Klik in [Azure Active Directory](https://aad.portal.azure.com)onder **Beheren**op **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="60787-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="60787-168">Klik **onder Instellingen**op **Naamgevingsbeleid**.</span><span class="sxs-lookup"><span data-stu-id="60787-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="60787-169">Kies het tabblad **Groepnaambeleid.**</span><span class="sxs-lookup"><span data-stu-id="60787-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="60787-170">Kies onder **Huidig beleid**of u een voorvoegsel of achtervoegsel of beide nodig wilt hebben en schakel de juiste selectievakjes in.</span><span class="sxs-lookup"><span data-stu-id="60787-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="60787-171">Kies tussen **Kenmerk** en **tekenreeks** voor elke regel en geef vervolgens het kenmerk of de tekenreeks op.</span><span class="sxs-lookup"><span data-stu-id="60787-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="60787-172">Wanneer u de voorvoegsels en achtervoegsels hebt toegevoegd die u nodig hebt, klikt u op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="60787-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Schermafbeelding van de beleidsinstellingen voor groepen in Azure Active Directory](../../media/groups-naming-policy-azure.png)

> [!NOTE]
> <span data-ttu-id="60787-174">StaffHub-teams volgen het naamgevingsbeleid niet, maar de onderliggende Microsoft 365-groep wel.</span><span class="sxs-lookup"><span data-stu-id="60787-174">StaffHub teams do not follow the naming policy, but the underlying Microsoft 365 group does.</span></span> <span data-ttu-id="60787-175">StaffHub-teamnaam past de voorvoegsels en achtervoegsels niet toe en controleert niet op aangepaste geblokkeerde woorden.</span><span class="sxs-lookup"><span data-stu-id="60787-175">StaffHub team name does not apply the prefixes and suffixes and does not check for custom blocked words.</span></span> <span data-ttu-id="60787-176">Maar StaffHub past wel de voorvoegsels en achtervoegsels toe en verwijdert geblokkeerde woorden uit de onderliggende Microsoft 365-groep.</span><span class="sxs-lookup"><span data-stu-id="60787-176">But StaffHub does apply the prefixes and suffixes and removes blocked words from the underlying Microsoft 365 group.</span></span>

## <a name="more-articles-on-naming-policy"></a><span data-ttu-id="60787-177">Meer artikelen over naamgevingsbeleid</span><span class="sxs-lookup"><span data-stu-id="60787-177">More articles on naming policy</span></span>

[<span data-ttu-id="60787-178">Een naamgevingsbeleid voor Microsoft 365-groepen afdwingen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="60787-178">Enforce a naming policy for Microsoft 365 groups in Azure Active Directory</span></span>](https://go.microsoft.com/fwlink/?linkid=868340)

[<span data-ttu-id="60787-179">Azure Active Directory-cmdlets voor het configureren van groepsinstellingen</span><span class="sxs-lookup"><span data-stu-id="60787-179">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
