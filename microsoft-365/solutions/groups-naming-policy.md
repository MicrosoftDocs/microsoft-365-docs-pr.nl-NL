---
title: Microsoft 365 naamgevingsbeleid voor groepen
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
recommendations: false
description: Meer informatie over het maken van een naamgevingsbeleid voor Microsoft 365 groepen.
ms.openlocfilehash: 5ab5f252e2b81470413b4efea17b131613aabc18
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538169"
---
# <a name="microsoft-365-groups-naming-policy"></a><span data-ttu-id="96967-103">Microsoft 365 naamgevingsbeleid voor groepen</span><span class="sxs-lookup"><span data-stu-id="96967-103">Microsoft 365 groups naming policy</span></span>

<span data-ttu-id="96967-104">U kunt een naamgevingsbeleid voor groepen gebruiken om een consistente naamgevingsstrategie af te dwingen voor groepen die zijn gemaakt door gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="96967-104">You can use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="96967-105">Een naamgevingsbeleid kan u en uw gebruikers helpen bij het identificeren van de functie van de groep, het lidmaatschap, de geografische regio of de persoon die de groep heeft gemaakt.</span><span class="sxs-lookup"><span data-stu-id="96967-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="96967-106">Het naamgevingsbeleid kan ook helpen bij het categoriseren van groepen in het adresboek.</span><span class="sxs-lookup"><span data-stu-id="96967-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="96967-107">U kunt het beleid gebruiken om te blokkeren dat specifieke woorden worden gebruikt in groepsnamen en aliassen.</span><span class="sxs-lookup"><span data-stu-id="96967-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="96967-108">Het naamgevingsbeleid wordt toegepast op groepen die worden gemaakt in alle groepen werkbelastingen (zoals Outlook, Microsoft Teams, SharePoint, Planner, Yammer, enzovoort).</span><span class="sxs-lookup"><span data-stu-id="96967-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="96967-109">Deze wordt toegepast op zowel de groepsnaam als de groepsalias.</span><span class="sxs-lookup"><span data-stu-id="96967-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="96967-110">Het wordt ook toegepast wanneer een gebruiker een groep maakt en wanneer de groepsnaam, alias, beschrijving of avatar wordt bewerkt voor een bestaande groep.</span><span class="sxs-lookup"><span data-stu-id="96967-110">It also gets applied when a user creates a group and when the group name, alias, description, or avatar is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="96967-111">Een Microsoft 365 groepsbeleid is alleen van toepassing op Microsoft 365 groepen.</span><span class="sxs-lookup"><span data-stu-id="96967-111">A Microsoft 365 group naming policy only applies to Microsoft 365 groups.</span></span> <span data-ttu-id="96967-112">Het is niet van toepassing op distributiegroepen die zijn gemaakt in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="96967-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="96967-113">Zie Een naamgevingsbeleid voor distributiegroepen maken als u een [naamgevingsbeleid voor](/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)distributiegroepen wilt maken.</span><span class="sxs-lookup"><span data-stu-id="96967-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="96967-114">Het groepsnaambeleid bestaat uit de volgende functie:</span><span class="sxs-lookup"><span data-stu-id="96967-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="96967-115">**Naamgevingsbeleid** voor voorvoegsel: u kunt voorvoegsels of achtervoegsels gebruiken om de naamgevingsconventie van groepen te definiëren (bijvoorbeeld: 'US \_ My Group \_ Engineering').</span><span class="sxs-lookup"><span data-stu-id="96967-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="96967-116">De voorvoegsels/achtervoegsels kunnen bestaan uit vaste tekenreeksen of gebruikerskenmerken (zoals [Department]) die worden vervangen op basis van de gebruiker die de groep maakt.</span><span class="sxs-lookup"><span data-stu-id="96967-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="96967-117">**Aangepaste geblokkeerde woorden:** u kunt een set geblokkeerde woorden uploaden die specifiek zijn voor uw organisatie en die worden geblokkeerd in groepen die door gebruikers zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="96967-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="96967-118">(Bijvoorbeeld: 'CEO, Salarisadministratie, HR').</span><span class="sxs-lookup"><span data-stu-id="96967-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="96967-119">Licentievereisten</span><span class="sxs-lookup"><span data-stu-id="96967-119">Licensing requirements</span></span>

<span data-ttu-id="96967-120">Voor het gebruik van Azure AD-naamgevingsbeleid voor Microsoft 365 Groepen moet u een Azure Active Directory Premium P1-licentie of Azure AD Basic EDU-licentie toewijzen voor elke unieke gebruiker (inclusief gasten) die lid is van een of meer Microsoft 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="96967-120">Using Azure AD naming policy for Microsoft 365 Groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="96967-121">Dit is ook vereist voor de beheerder die het naamgevingsbeleid voor groepen maakt.</span><span class="sxs-lookup"><span data-stu-id="96967-121">This is also required for the administrator that creates the groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="96967-122">Prefix-Suffix naamgevingsbeleid</span><span class="sxs-lookup"><span data-stu-id="96967-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="96967-123">Voorvoegsels en achtervoegsels kunnen vaste tekenreeksen of gebruikerskenmerken zijn.</span><span class="sxs-lookup"><span data-stu-id="96967-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="96967-124">Vaste tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="96967-124">Fixed strings</span></span>

<span data-ttu-id="96967-125">U kunt korte tekenreeksen gebruiken om groepen te onderscheiden in de gal en linkernavigatie van de groepswerkbelastingen.</span><span class="sxs-lookup"><span data-stu-id="96967-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="96967-126">Enkele algemene voorvoegsels zijn trefwoorden zoals 'Grp \_ Name', \# 'Name', ' Name' en \_ 'Name'</span><span class="sxs-lookup"><span data-stu-id="96967-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="96967-127">Kenmerken</span><span class="sxs-lookup"><span data-stu-id="96967-127">Attributes</span></span>

<span data-ttu-id="96967-128">U kunt kenmerken gebruiken om te bepalen wie de groep heeft gemaakt, zoals [Afdeling] en waar deze is gemaakt, zoals [Land].</span><span class="sxs-lookup"><span data-stu-id="96967-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

<span data-ttu-id="96967-129">Voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="96967-129">Examples:</span></span>

- <span data-ttu-id="96967-130">Beleid = "GRP [GroupName] [Department]"</span><span class="sxs-lookup"><span data-stu-id="96967-130">Policy = "GRP [GroupName] [Department]"</span></span>
- <span data-ttu-id="96967-131">Afdeling van de gebruiker = Engineering</span><span class="sxs-lookup"><span data-stu-id="96967-131">User's department = Engineering</span></span>
- <span data-ttu-id="96967-132">Gemaakte groepsnaam = "GRP My Group Engineering"</span><span class="sxs-lookup"><span data-stu-id="96967-132">Created group name = "GRP My Group Engineering"</span></span>

<span data-ttu-id="96967-133">Ondersteunde Azure Active Directory (Azure AD) kenmerken zijn [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion] en [Title].</span><span class="sxs-lookup"><span data-stu-id="96967-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="96967-134">Niet-ondersteunde gebruikerskenmerken worden beschouwd als vaste tekenreeksen, bijvoorbeeld [postcode].</span><span class="sxs-lookup"><span data-stu-id="96967-134">Unsupported user attributes are considered as fixed strings, for example [postalCode].</span></span>

- <span data-ttu-id="96967-135">Extensiekenmerken en aangepaste kenmerken worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="96967-135">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="96967-136">Het wordt aangeraden kenmerken te gebruiken met waarden die voor alle gebruikers in uw organisatie zijn ingevuld en geen kenmerken met lange waarden te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="96967-136">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="96967-137">Dingen om op te kijken</span><span class="sxs-lookup"><span data-stu-id="96967-137">Things to look out for</span></span>

- <span data-ttu-id="96967-138">Bij het maken van beleid mag de totale tekenreekslengte van voor- en achtervoegsel niet langer zijn dan 53 tekens.</span><span class="sxs-lookup"><span data-stu-id="96967-138">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="96967-139">Voor- en achtervoegsels kunnen speciale tekens bevatten die voor de groepsnaam en de groepsalias worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="96967-139">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="96967-140">Wanneer de voor- en achtervoegsels speciale tekens bevatten die niet zijn toegestaan in de groepsalias, worden ze alleen toegepast op de groepsnaam.</span><span class="sxs-lookup"><span data-stu-id="96967-140">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="96967-141">In dit geval zouden de voor- en achtervoegsels die op de groepsnaam worden toegepast verschillen van degene die op de groepsalias worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="96967-141">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

  > [!NOTE]
  > <span data-ttu-id="96967-142">Een punt (.) of een afbreekstreester (-) is overal in de groepsnaam toegestaan, behalve aan het begin of einde van de naam.</span><span class="sxs-lookup"><span data-stu-id="96967-142">A period (.) or a hyphen (-) is permitted anywhere in the group name, except at the beginning or end of the name.</span></span> <span data-ttu-id="96967-143">Een onderstrepingsteken (_) is overal in de groepsnaam toegestaan, ook aan het begin of einde van de naam.</span><span class="sxs-lookup"><span data-stu-id="96967-143">An underscore (_) is permitted anywhere in the group name, including at the beginning or end of the name.</span></span>

- <span data-ttu-id="96967-144">Als u Yammer Office 365 groepen gebruikt, vermijdt u het gebruik van de volgende tekens in uw naamgevingsbeleid: @, \# , \[ , , \] \<, and \> .</span><span class="sxs-lookup"><span data-stu-id="96967-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="96967-145">Als deze tekens in het naamgevingsbeleid staan, kunnen Yammer gebruikers geen groepen maken.</span><span class="sxs-lookup"><span data-stu-id="96967-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

> [!Tip]
> - <span data-ttu-id="96967-146">Gebruik korte tekenreeksen als achtervoegsel.</span><span class="sxs-lookup"><span data-stu-id="96967-146">Use short strings as suffix.</span></span>
> - <span data-ttu-id="96967-147">Gebruik kenmerken met waarden.</span><span class="sxs-lookup"><span data-stu-id="96967-147">Use attributes with values.</span></span>
> - <span data-ttu-id="96967-148">Wees niet te creatief, de totale naamlengte heeft een maximum van 264 tekens.</span><span class="sxs-lookup"><span data-stu-id="96967-148">Don't be too creative, total name length has a maximum of 264 characters.</span></span>
> - <span data-ttu-id="96967-149">Upload uw organisatie specifieke geblokkeerde woorden om het gebruik te beperken.</span><span class="sxs-lookup"><span data-stu-id="96967-149">Upload your organization specific blocked words to restrict usage.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="96967-150">Aangepaste geblokkeerde woorden</span><span class="sxs-lookup"><span data-stu-id="96967-150">Custom blocked words</span></span>

<span data-ttu-id="96967-151">U kunt een door komma's gescheiden lijst met geblokkeerde woorden invoeren die worden geblokkeerd in groepsnamen en aliassen.</span><span class="sxs-lookup"><span data-stu-id="96967-151">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="96967-152">Er worden geen subreekszoekingen uitgevoerd. een exacte overeenkomst tussen de ingevoerde naam van de gebruiker en de aangepaste geblokkeerde woorden is vereist om een fout te activeren.</span><span class="sxs-lookup"><span data-stu-id="96967-152">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span>

<span data-ttu-id="96967-153">**Dingen om op te kijken:**</span><span class="sxs-lookup"><span data-stu-id="96967-153">**Things to look out for**:</span></span>

- <span data-ttu-id="96967-154">De geblokkeerde woorden zijn hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="96967-154">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="96967-155">Als er een geblokkeerd woord wordt ingevoerd, wordt een foutbericht met het geblokkeerde woord erin weergegeven.</span><span class="sxs-lookup"><span data-stu-id="96967-155">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="96967-156">Er bestaan geen restricties op tekens in het gebruikte geblokkeerde woord.</span><span class="sxs-lookup"><span data-stu-id="96967-156">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="96967-157">Er is een limiet van 5000 woorden die kunnen worden ingesteld als geblokkeerde woorden.</span><span class="sxs-lookup"><span data-stu-id="96967-157">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="96967-158">Overschrijven door beheerder</span><span class="sxs-lookup"><span data-stu-id="96967-158">Admin override</span></span>

<span data-ttu-id="96967-159">Sommige beheerders zijn vrijgesteld van dit beleid, voor alle groepswerkbelastingen en eindpunten, zodat ze groepen kunnen maken met deze geblokkeerde woorden en met de gewenste naamgevingsconventies.</span><span class="sxs-lookup"><span data-stu-id="96967-159">Some administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="96967-160">Hierna volgt een lijst van beheerdersrollen die zijn vrijgesteld van het groepsnaambeleid.</span><span class="sxs-lookup"><span data-stu-id="96967-160">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="96967-161">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="96967-161">Global admin</span></span>

- <span data-ttu-id="96967-162">Partnerondersteuning voor laag 1</span><span class="sxs-lookup"><span data-stu-id="96967-162">Partner Tier 1 Support</span></span>

- <span data-ttu-id="96967-163">Partnerondersteuning voor laag 2</span><span class="sxs-lookup"><span data-stu-id="96967-163">Partner Tier 2 Support</span></span>

- <span data-ttu-id="96967-164">Beheerder van het gebruikersaccount</span><span class="sxs-lookup"><span data-stu-id="96967-164">User account admin</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="96967-165">Het naamgevingsbeleid instellen</span><span class="sxs-lookup"><span data-stu-id="96967-165">How to set up the naming policy</span></span>

<span data-ttu-id="96967-166">Een naamgevingsbeleid instellen:</span><span class="sxs-lookup"><span data-stu-id="96967-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="96967-167">Klik [Azure Active Directory](https://aad.portal.azure.com)onder **Beheren** op **Groepen.**</span><span class="sxs-lookup"><span data-stu-id="96967-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="96967-168">Klik **onder Instellingen** op **Naamgevingsbeleid**.</span><span class="sxs-lookup"><span data-stu-id="96967-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="96967-169">Kies het **tabblad Groepnaamgevingsbeleid.**</span><span class="sxs-lookup"><span data-stu-id="96967-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="96967-170">Kies **onder Huidig** beleid of u een voorvoegsel of achtervoegsel of beide wilt vereisen en schakel de juiste selectievakjes in.</span><span class="sxs-lookup"><span data-stu-id="96967-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="96967-171">Kies tussen **Kenmerk** en **Tekenreeks** voor elke regel en geef vervolgens het kenmerk of de tekenreeks op.</span><span class="sxs-lookup"><span data-stu-id="96967-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="96967-172">Wanneer u de voor- en achtervoegsels hebt toegevoegd die u nodig hebt, klikt u op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="96967-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Schermafbeelding van de instellingen voor het naamgevingsbeleid van groepen in Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a><span data-ttu-id="96967-174">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="96967-174">Related topics</span></span>

[<span data-ttu-id="96967-175">Planning van samenwerkingsbeheer stap voor stap</span><span class="sxs-lookup"><span data-stu-id="96967-175">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="96967-176">Uw samenwerkingsbeheerplan maken</span><span class="sxs-lookup"><span data-stu-id="96967-176">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="96967-177">Azure Active Directory cmdlets voor het configureren van groepsinstellingen</span><span class="sxs-lookup"><span data-stu-id="96967-177">Azure Active Directory cmdlets for configuring group settings</span></span>](/azure/active-directory/enterprise-users/groups-settings-cmdlets)