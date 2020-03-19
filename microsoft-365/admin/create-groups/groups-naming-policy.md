---
title: Naamgevingsbeleid voor Office 365-groepen
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 11e2907462d325e4ad421914ae5a0deb5013e695
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42809926"
---
# <a name="office-365-groups-naming-policy"></a><span data-ttu-id="e211e-103">Naamgevingsbeleid voor Office 365-groepen</span><span class="sxs-lookup"><span data-stu-id="e211e-103">Office 365 Groups naming policy</span></span>

<span data-ttu-id="e211e-104">U gebruikt een groepsnaamgevingsbeleid om een consistente naamgevingsstrategie af te dwingen voor groepen die zijn gemaakt door gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="e211e-104">You use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="e211e-105">Een naamgevingsbeleid kan u en uw gebruikers helpen de functie van de groep, het lidmaatschap, de geografische regio of de persoon die de groep heeft gemaakt te identificeren.</span><span class="sxs-lookup"><span data-stu-id="e211e-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="e211e-106">Het naamgevingsbeleid kan ook helpen bij het categoriseren van groepen in het adresboek.</span><span class="sxs-lookup"><span data-stu-id="e211e-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="e211e-107">U het beleid gebruiken om te voorkomen dat specifieke woorden worden gebruikt in groepsnamen en aliassen.</span><span class="sxs-lookup"><span data-stu-id="e211e-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="e211e-108">Het naamgevingsbeleid wordt toegepast op groepen die zijn gemaakt voor alle groepsworkloads (zoals Outlook, Microsoft Teams, SharePoint, Planner, Yammer, enz.).</span><span class="sxs-lookup"><span data-stu-id="e211e-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc).</span></span> <span data-ttu-id="e211e-109">Het wordt toegepast op zowel de groepsnaam als de groepsalias.</span><span class="sxs-lookup"><span data-stu-id="e211e-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="e211e-110">Deze wordt toegepast wanneer een gebruiker een groep maakt en wanneer groepsnaam of alias wordt bewerkt voor een bestaande groep.</span><span class="sxs-lookup"><span data-stu-id="e211e-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="e211e-111">Een office 365-groepsnaamgevingsbeleid is alleen van toepassing op Office 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="e211e-111">An Office 365 group naming policy only applies to Office 365 Groups.</span></span> <span data-ttu-id="e211e-112">Het is niet van toepassing op distributiegroepen die zijn gemaakt in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e211e-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="e211e-113">Zie [Een naamgevingsbeleid](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)voor distributiegroepen maken als u een naamgevingsbeleid wilt maken.</span><span class="sxs-lookup"><span data-stu-id="e211e-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="e211e-114">Het groepsnaambeleid bestaat uit de volgende functie:</span><span class="sxs-lookup"><span data-stu-id="e211e-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="e211e-115">**Naamgevingsbeleid voorvoegsel**:U voorvoegsels of achtervoegsels gebruiken om de naamgevingsconventie\_\_van\_groepen te definiëren (bijvoorbeeld: GRP US My Group Engineering).</span><span class="sxs-lookup"><span data-stu-id="e211e-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "GRP\_US\_My Group\_Engineering").</span></span> <span data-ttu-id="e211e-116">De voorvoegsels/achtervoegsels kunnen bestaan uit vaste tekenreeksen of gebruikerskenmerken (zoals [Department]) die worden vervangen op basis van de gebruiker die de groep maakt.</span><span class="sxs-lookup"><span data-stu-id="e211e-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="e211e-117">**Aangepaste geblokkeerde woorden:** u een set geblokkeerde woorden uploaden die specifiek zijn voor hun organisatie en die worden geblokkeerd in groepen die door gebruikers zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e211e-117">**Custom Blocked Words**: You can upload a set of blocked words specific to their organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="e211e-118">(Bijvoorbeeld: "CEO, Payroll, HR").</span><span class="sxs-lookup"><span data-stu-id="e211e-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="e211e-119">Licentievereisten</span><span class="sxs-lookup"><span data-stu-id="e211e-119">Licensing requirements</span></span>

<span data-ttu-id="e211e-120">Voor het gebruik van Azure AD-naamgevingsbeleid voor Office 365-groepen moet u beschikken over een Azure Active Directory Premium P1-licentie of Azure AD Basic EDU-licentie voor elke unieke gebruiker (inclusief gasten) die lid is van een of meer Office 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="e211e-120">Using Azure AD naming policy for Office 365 groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Office 365 groups.</span></span>
<span data-ttu-id="e211e-121">Dit is ook vereist voor de beheerder die het naamgevingsbeleid Groepen maakt.</span><span class="sxs-lookup"><span data-stu-id="e211e-121">This is also required for the administrator that creates the Groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="e211e-122">Naamgevingsbeleid voor voorvoegsel</span><span class="sxs-lookup"><span data-stu-id="e211e-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="e211e-123">Voorvoegsels en achtervoegsels kunnen vaste tekenreeksen of gebruikerskenmerken zijn.</span><span class="sxs-lookup"><span data-stu-id="e211e-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="e211e-124">Vaste tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="e211e-124">Fixed strings</span></span>

<span data-ttu-id="e211e-125">U korte tekenreeksen gebruiken waarmee u groepen differentiëren in het gal- en linkernavigatienav van de groepsworkloads.</span><span class="sxs-lookup"><span data-stu-id="e211e-125">You can use short strings that can help you differentiate groups in the GAL and Left nav of the group workloads.</span></span> <span data-ttu-id="e211e-126">Enkele van de gemeenschappelijke voorvoegsels zijn trefwoorden\_zoals 'Grp Name' , 'Naam',\#'Naam'\_</span><span class="sxs-lookup"><span data-stu-id="e211e-126">Some of the common prefixes suffixes are Keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="e211e-127">Kenmerken</span><span class="sxs-lookup"><span data-stu-id="e211e-127">Attributes</span></span>

<span data-ttu-id="e211e-128">U kenmerken gebruiken waarmee u bepalen wie de groep heeft gemaakt, zoals [Afdeling] en waar deze is gemaakt, zoals [Land].</span><span class="sxs-lookup"><span data-stu-id="e211e-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e211e-129">**Voorbeelden**</span><span class="sxs-lookup"><span data-stu-id="e211e-129">**Examples**</span></span>|<span data-ttu-id="e211e-130">Beleid = "GRP [GroupName] [Department]"</span><span class="sxs-lookup"><span data-stu-id="e211e-130">Policy = "GRP [GroupName] [Department]"</span></span>|
||<span data-ttu-id="e211e-131">Afdeling van de gebruiker = Engineering</span><span class="sxs-lookup"><span data-stu-id="e211e-131">User's department = Engineering</span></span>|
||<span data-ttu-id="e211e-132">Gemaakte groepsnaam = "GRP My Group Engineering"</span><span class="sxs-lookup"><span data-stu-id="e211e-132">Created group name = "GRP My Group Engineering"</span></span>|

<span data-ttu-id="e211e-133">Ondersteunde Azure Active Directory-kenmerken (Azure AD) zijn [Afdeling], [Bedrijf], [Office], [StateOrProvince], [CountryOrRegion], [Titel]</span><span class="sxs-lookup"><span data-stu-id="e211e-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], [Title]</span></span>

- <span data-ttu-id="e211e-p108">Niet-ondersteunde gebruikerskenmerken worden als vaste tekenreeksen beschouwd. Bijvoorbeeld "[postalCode]"</span><span class="sxs-lookup"><span data-stu-id="e211e-p108">Unsupported user attributes are considered as fixed strings. E.g. "[postalCode]"</span></span>

- <span data-ttu-id="e211e-137">Extensiekenmerken en aangepaste kenmerken worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="e211e-137">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="e211e-138">Het wordt aangeraden kenmerken te gebruiken met waarden die voor alle gebruikers in uw organisatie zijn ingevuld en geen kenmerken met lange waarden te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e211e-138">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="e211e-139">Dingen om op te letten</span><span class="sxs-lookup"><span data-stu-id="e211e-139">Things to look out for</span></span>

- <span data-ttu-id="e211e-140">Bij het maken van beleid mag de totale tekenreekslengte van voor- en achtervoegsel niet langer zijn dan 53 tekens.</span><span class="sxs-lookup"><span data-stu-id="e211e-140">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="e211e-p109">Voor- en achtervoegsels kunnen speciale tekens bevatten die voor de groepsnaam en de groepsalias worden ondersteund. Als de voor- en achtervoegsels speciale tekens bevatten die niet in de groepsalias zijn toegestaan, worden ze verwijderd en op de groepsalias toegepast. In dit geval zouden de voor- en achtervoegsels die op de groepsnaam worden toegepast verschillen van degene die op de groepsalias worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="e211e-p109">Prefixes and suffixes can contain special characters supported in group name and group alias. When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are removed and applied to the group alias. So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

- <span data-ttu-id="e211e-144">Als u yammer Office 365-verbonden groepen gebruikt, gebruikt u de \# \[volgende \] \<tekens \>in uw naamgevingsbeleid: @, , , en .</span><span class="sxs-lookup"><span data-stu-id="e211e-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="e211e-145">Als deze tekens zich in het naamgevingsbeleid bevinden, kunnen gewone Yammer-gebruikers geen groepen maken.</span><span class="sxs-lookup"><span data-stu-id="e211e-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="e211e-146">Aangepaste geblokkeerde woorden</span><span class="sxs-lookup"><span data-stu-id="e211e-146">Custom blocked words</span></span>

<span data-ttu-id="e211e-147">U een door komma gescheiden lijst met geblokkeerde woorden invoeren die worden geblokkeerd in groepsnamen en aliassen.</span><span class="sxs-lookup"><span data-stu-id="e211e-147">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="e211e-148">De geblokkeerde woordencontrole wordt uitgevoerd op de door de gebruiker ingevoerde groepsnaam.</span><span class="sxs-lookup"><span data-stu-id="e211e-148">The blocked words check is done on the user entered group name.</span></span> <span data-ttu-id="e211e-149">Dus als de gebruiker 'darnit'\_binnenkomt en 'Prefix' het naamgevingsbeleid is, zal 'Prefix\_darnit' mislukken.</span><span class="sxs-lookup"><span data-stu-id="e211e-149">So if user enters 'darnit' and 'Prefix\_' is the naming policy, 'Prefix\_darnit' will fail.</span></span>

<span data-ttu-id="e211e-150">Er worden geen zoekopdrachten uitgevoerd in subtekenreeksen; specifiek is een exacte overeenkomst tussen de ingevoerde naam van de gebruiker en de aangepaste geblokkeerde woorden vereist om een fout te activeren.</span><span class="sxs-lookup"><span data-stu-id="e211e-150">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span> <span data-ttu-id="e211e-151">Sub-string zoeken wordt niet gedaan, zodat gebruikers kunnen een aantal van de gemeenschappelijke woorden zoals 'Klasse' te gebruiken, zelfs als 'kont' is een geblokkeerd woord.</span><span class="sxs-lookup"><span data-stu-id="e211e-151">Sub-string search isn't done so that users can use some of the common words like 'Class' even if 'ass' is a blocked word.</span></span>

<span data-ttu-id="e211e-152">**Dingen om op te letten:**</span><span class="sxs-lookup"><span data-stu-id="e211e-152">**Things to look out for**:</span></span>

- <span data-ttu-id="e211e-153">De geblokkeerde woorden zijn hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="e211e-153">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="e211e-154">Als er een geblokkeerd woord wordt ingevoerd, wordt een foutbericht met het geblokkeerde woord erin weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e211e-154">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="e211e-155">Er bestaan geen restricties op tekens in het gebruikte geblokkeerde woord.</span><span class="sxs-lookup"><span data-stu-id="e211e-155">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="e211e-156">Er is een bovengrens van 5000 woorden die kunnen worden ingesteld als geblokkeerde woorden.</span><span class="sxs-lookup"><span data-stu-id="e211e-156">There is an upper limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="e211e-157">Overschrijven door beheerder</span><span class="sxs-lookup"><span data-stu-id="e211e-157">Admin override</span></span>

<span data-ttu-id="e211e-p113">Bepaalde beheerders zijn voor alle groepswerkbelastingen en eindpunten vrijgesteld van dit beleid, zodat ze groepen kunnen maken met deze geblokkeerde woorden en met eigen naamgevingsconventies. Hierna volgt een lijst van beheerdersrollen die zijn vrijgesteld van het groepsnaambeleid.</span><span class="sxs-lookup"><span data-stu-id="e211e-p113">Selective administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions. The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="e211e-160">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="e211e-160">Global admin</span></span>

- <span data-ttu-id="e211e-161">Partnerondersteuning voor laag 1</span><span class="sxs-lookup"><span data-stu-id="e211e-161">Partner Tier 1 Support</span></span>

- <span data-ttu-id="e211e-162">Partnerondersteuning voor laag 2</span><span class="sxs-lookup"><span data-stu-id="e211e-162">Partner Tier 2 Support</span></span>

- <span data-ttu-id="e211e-163">Beheerder van het gebruikersaccount</span><span class="sxs-lookup"><span data-stu-id="e211e-163">User account admin</span></span>

- <span data-ttu-id="e211e-164">Schrijvers van adreslijsten</span><span class="sxs-lookup"><span data-stu-id="e211e-164">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="e211e-165">Het naamgevingsbeleid instellen</span><span class="sxs-lookup"><span data-stu-id="e211e-165">How to set up the naming policy</span></span>

<span data-ttu-id="e211e-166">Ga als u een naamgevingsbeleid instellen:</span><span class="sxs-lookup"><span data-stu-id="e211e-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="e211e-167">Klik in [Azure Active Directory](https://aad.portal.azure.com)onder **Beheren**op **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="e211e-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="e211e-168">Klik onder **Instellingen**op **Naamgevingsbeleid**.</span><span class="sxs-lookup"><span data-stu-id="e211e-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="e211e-169">Kies het tabblad **Groepsnaamgevingsbeleid.**</span><span class="sxs-lookup"><span data-stu-id="e211e-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="e211e-170">Kies onder **Huidig beleid**of u een voorvoegsel of achtervoegsel of beide wilt vereisen en schakel de juiste selectievakjes in.</span><span class="sxs-lookup"><span data-stu-id="e211e-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="e211e-171">Kies tussen **Kenmerk** en **Tekenreeks** voor elke regel en geef vervolgens het kenmerk of de tekenreeks op.</span><span class="sxs-lookup"><span data-stu-id="e211e-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="e211e-172">Wanneer u de voorvoegsels en achtervoegsels hebt toegevoegd die u nodig hebt, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e211e-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Schermafbeelding van de beleidsinstellingen voor groepen naamgeving in Azure Active Directory](../../media/groups-naming-policy-azure.png)

## <a name="naming-policy-experiences-across-office-365-apps"></a><span data-ttu-id="e211e-174">Naamgevingsbeleid in Office 365-apps</span><span class="sxs-lookup"><span data-stu-id="e211e-174">Naming policy experiences across Office 365 apps</span></span>

<span data-ttu-id="e211e-p114">De Office 365-apps zijn bijgewerkt zodat ze een preview laten zien van de groepsnaam van het naamgevingsbeleid (inclusief voor- en achtervoegsels) als de gebruiker de groepsnaam en -alias typt. Als de gebruiker geblokkeerde woorden invoert, verschijnt een foutbericht zodat ze de geblokkeerde woorden kunnen verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e211e-p114">The Office 365 apps have been updated to show a preview of the naming policy group name (with prefixes and suffixes) when the user types in the group name and alias. When the user enters blocked words, they'll see an error message so they can remove the blocked words.</span></span>

## <a name="outlook-on-the-web"></a><span data-ttu-id="e211e-177">Web van Outlook op de website</span><span class="sxs-lookup"><span data-stu-id="e211e-177">Outlook on the web</span></span>

<span data-ttu-id="e211e-178">In Outlook op internet (voorheen Outlook Web App of OWA genoemd) wordt de naam van het naamgevingsbeleid weergegeven wanneer de gebruiker een groepsnaam of groepsalias typt.</span><span class="sxs-lookup"><span data-stu-id="e211e-178">Outlook on the web (formerly known as Outlook Web App or OWA) shows the naming policy decorated name when the user types a group name or group alias.</span></span> <span data-ttu-id="e211e-179">Als een gebruiker een geblokkeerd woord typt, wordt in de gebruikersinterface een foutbericht met het geblokkeerde woord weergegeven, zodat de gebruiker dit kan verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e211e-179">When an user enters a custom blocked word, an error message is shown in the UI along with the blocked word so that the user can remove it.</span></span> <span data-ttu-id="e211e-180">Outlook on the web experience snapshots worden hieronder weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e211e-180">Outlook on the web experience snapshots are shown below.</span></span>

![Naast elkaar weergave van groepsnaamgevingsbeleid in Office 365-groepen](../../media/1a21657a-c542-4d9e-ac7d-887ac542a9d9.png)

## <a name="outlook-desktop"></a><span data-ttu-id="e211e-182">Outlook (bureaublad)</span><span class="sxs-lookup"><span data-stu-id="e211e-182">Outlook Desktop</span></span>

<span data-ttu-id="e211e-183">Groepen die in de bureaubladversie van Outlook zijn gemaakt, voldoen aan het naamgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="e211e-183">Groups created in Outlook desktop are compliant with naming policy.</span></span> <span data-ttu-id="e211e-184">In de Outlook-bureaubladapp wordt nog geen preview weergegeven van het naamgevingsbeleid en retourneert de fouten voor aangepaste, geblokkeerde woorden niet als de gebruiker een groepsnaam invoert.</span><span class="sxs-lookup"><span data-stu-id="e211e-184">Outlook desktop app doesn't yet show the preview of the naming policy and doesn't return the custom blocked word errors, when the user enters the group name.</span></span> <span data-ttu-id="e211e-185">Het naamgevingsbeleid wordt echter automatisch toegepast bij het selecteren van maken/bewerken en gebruikers krijgen fouten als er aangepaste geblokkeerde woorden in de groepsnaam of alias zijn.</span><span class="sxs-lookup"><span data-stu-id="e211e-185">However, naming policy will be automatically applied on selecting create/edit and users will be presented with errors if there are custom blocked words in the group name or alias.</span></span>

## <a name="microsoft-teams"></a><span data-ttu-id="e211e-186">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e211e-186">Microsoft Teams</span></span>

<span data-ttu-id="e211e-187">Microsoft Teams toont de naam van het naamgevingsbeleid wanneer de gebruiker een teamnaam typt.</span><span class="sxs-lookup"><span data-stu-id="e211e-187">Microsoft Teams shows the naming policy decorated name when the user types a team name.</span></span> <span data-ttu-id="e211e-188">Wanneer een gebruiker een aangepast geblokkeerd woord invoert, wordt een foutbericht weergegeven samen met het geblokkeerde woord, zodat de gebruiker het kan verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e211e-188">When a user enters a custom blocked word, an error message is shown along with the blocked word so that the user can remove it.</span></span>

![Voorbeeld groepsnaamgeving smaken in Microsoft Teams geblokkeerd](../../media/7c904546-5853-4642-949a-a55dbb004eca.png)

## <a name="sharepoint"></a><span data-ttu-id="e211e-190">Sharepoint</span><span class="sxs-lookup"><span data-stu-id="e211e-190">SharePoint</span></span>

<span data-ttu-id="e211e-191">SharePoint toont de naam van het naamgevingsbeleid wanneer de gebruiker een sitenaam of groepse-mailadres typt.</span><span class="sxs-lookup"><span data-stu-id="e211e-191">SharePoint shows the naming policy name when the user types a site name or group email address.</span></span> <span data-ttu-id="e211e-192">Als een gebruiker een geblokkeerd woord typt, wordt een foutbericht met het geblokkeerde woord weergegeven, zodat de gebruiker dit kan verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e211e-192">When an user enters a custom blocked word, an error message is shown, along with the blocked word so that the user can remove it.</span></span>

![Groepsnaamgevingsbeleid - SharePoint-site geblokkeerde naam](../../media/cf0d6158-fd32-4a93-ac24-2e037102c42c.png)

## <a name="microsoft-stream"></a><span data-ttu-id="e211e-194">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="e211e-194">Microsoft Stream</span></span>

<span data-ttu-id="e211e-p119">In Microsoft Stream wordt de gedecoreerde naam van het naamgevingsbeleid getoond als de gebruiker een groepsnaam of -e-mailalias typt. Als een gebruiker een geblokkeerd woord typt, wordt een foutbericht met het geblokkeerde woord weergegeven, zodat de gebruiker dit kan verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e211e-p119">Microsoft Stream shows the naming policy decorated name when the user types a group name or group email alias. When an user enters a custom blocked word, an error message is shown with the blocked word so the user can remove it.</span></span>

![Groepsnaamgevingsbeleid geblokkeerd voorbeeld voor Microsoft Stream](../../media/9748f52a-3814-41a6-9ac1-4e8cd4c91011.png)

## <a name="outlook-ios-and-android-app"></a><span data-ttu-id="e211e-198">Outlook IOS- en Android-app</span><span class="sxs-lookup"><span data-stu-id="e211e-198">Outlook iOS and Android App</span></span>

<span data-ttu-id="e211e-199">Groepen die in Outlook-apps zijn gemaakt, voldoen aan het naamgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="e211e-199">Groups created in Outlook apps are compliant with naming policy.</span></span> <span data-ttu-id="e211e-200">In Outlook mobile wordt de voorbeeld van het naamgevingsbeleid weergegeven bij het invoeren van de groepsnaam.</span><span class="sxs-lookup"><span data-stu-id="e211e-200">Outlook mobile shows the naming policy preview when entering the Group name.</span></span> <span data-ttu-id="e211e-201">Wanneer een gebruiker een aangepast geblokkeerd woord invoert, wordt een foutbericht weergegeven bij het maken van de groep, zodat de gebruiker het geblokkeerde woord kan verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e211e-201">When a user enters a custom blocked word, an error message is shown on creating the group, so the user can remove the blocked word.</span></span>

## <a name="planner"></a><span data-ttu-id="e211e-202">Planner</span><span class="sxs-lookup"><span data-stu-id="e211e-202">Planner</span></span>

<span data-ttu-id="e211e-203">Planner voldoet aan het naamgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="e211e-203">Planner is compliant with naming policy.</span></span> <span data-ttu-id="e211e-204">Planner toont de voorbeeld van het naamgevingsbeleid bij het invoeren van de naam Plan.</span><span class="sxs-lookup"><span data-stu-id="e211e-204">Planner shows the naming policy preview when entering the Plan name.</span></span> <span data-ttu-id="e211e-205">Wanneer een gebruiker een aangepast geblokkeerd woord invoert, wordt een foutbericht weergegeven bij het maken van het plan, zodat de gebruiker het geblokkeerde woord kan verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e211e-205">When a user enters a custom blocked word, an error message is shown on creating the plan, so the user can remove the blocked word.</span></span>

![Groepsnaamgevingsbeleid - nieuw voorbeeld van een plan maken](../../media/ea692b44-3a56-4e6d-bcb8-8444fe5bbc4f.png)

## <a name="dynamics-365-for-customer-engagement"></a><span data-ttu-id="e211e-207">Dynamics 365 voor klantbetrokkenheid</span><span class="sxs-lookup"><span data-stu-id="e211e-207">Dynamics 365 for Customer Engagement</span></span>

<span data-ttu-id="e211e-208">Dynamics 365 voor Customer Engagement voldoet aan het naamgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="e211e-208">Dynamics 365 for Customer Engagement is compliant with naming policy.</span></span> <span data-ttu-id="e211e-209">Dynamics 365 toont de naam van het naamgevingsbeleid wanneer de gebruiker een groepsnaam of groepse-mailalias typt.</span><span class="sxs-lookup"><span data-stu-id="e211e-209">Dynamics 365 shows the naming policy decorated name when the user types a group name or group email alias.</span></span> <span data-ttu-id="e211e-210">Wanneer de gebruiker een aangepast geblokkeerd woord invoert, wordt een foutbericht weergegeven met het geblokkeerde woord, zodat de gebruiker het kan verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e211e-210">When the user enters a custom blocked word, an error message is shown with the blocked word so the user can remove it.</span></span>

![Dynamiek 365](../../media/8190331c-6779-42bd-a6b3-f7007428c8ae.png)

## <a name="school-data-sync-sds"></a><span data-ttu-id="e211e-212">School Data Sync (SDS)</span><span class="sxs-lookup"><span data-stu-id="e211e-212">School Data Sync (SDS)</span></span>

<span data-ttu-id="e211e-p123">Groepen die via SDS worden gemaakt, voldoen aan het naamgevingsbeleid, maar dit wordt niet automatisch toegepast. SDS-beheerders moeten de voor- en achtervoegsels zelf toevoegen aan de klassennamen waarvoor groepen moeten worden gemaakt en deze uploaden naar SDS. Als ze dit niet doen, mislukt het maken/bewerken van groepen.</span><span class="sxs-lookup"><span data-stu-id="e211e-p123">Groups created through SDS comply with naming policy, but the naming policy isn't applied automatically. SDS administrators have to append the prefixes and suffixes to class names for which groups need to be created and then upload to SDS. Groups creation/edit would fail otherwise.</span></span>

## <a name="outlook-customer-manager-ocm"></a><span data-ttu-id="e211e-216">Outlook Customer Manager (OCM)</span><span class="sxs-lookup"><span data-stu-id="e211e-216">Outlook Customer Manager (OCM)</span></span>

<span data-ttu-id="e211e-217">Outlook Customer Manager voldoet aan het naamgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="e211e-217">Outlook Customer Manager is compliant with naming policy.</span></span> <span data-ttu-id="e211e-218">Het naamgevingsbeleid wordt automatisch toegepast op de groep die is gemaakt in Outlook Customer Manager.</span><span class="sxs-lookup"><span data-stu-id="e211e-218">The naming policy gets automatically applied to the group created in Outlook Customer Manager.</span></span> <span data-ttu-id="e211e-219">Als een van de woorden in 'All Sales Team' wordt gedefinieerd als een aangepast geblokkeerd woord, wordt de groepcreatie in OCM geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="e211e-219">If any of the words within "All Sales Team" is defined as a custom blocked word, the group creation in OCM will be blocked.</span></span> <span data-ttu-id="e211e-220">De gebruiker kan de OCM-groep niet maken en wordt geblokkeerd voor het gebruik van de OCM-app."</span><span class="sxs-lookup"><span data-stu-id="e211e-220">The user will not be able to create the OCM group and will be blocked from using the OCM app."</span></span>

## <a name="classroom-app"></a><span data-ttu-id="e211e-221">Classroom-app</span><span class="sxs-lookup"><span data-stu-id="e211e-221">Classroom App</span></span>

<span data-ttu-id="e211e-p125">Groepen die in de Classroom-app worden gemaakt, voldoen aan het naamgevingsbeleid, maar het naamgevingsbeleid wordt niet automatisch toegepast, en de preview van het naamgevingsbeleid wordt niet aan de gebruikers getoond bij het invoeren van de groepsnaam voor een klaslokaal. Gebruikers moeten dus de gedecoreerde groepsnaam van het klaslokaal met de voor- en achtervoegsels invoeren. Als dat niet gebeurd, mislukt het maken of bewerken van de klaslokaalgroep en worden fouten weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e211e-p125">Groups created in classroom app comply with naming policy, but the naming policy isn't applied automatically, and the naming policy preview isn't shown to the users while entering a classroom group name. So users would have to enter the decorated classroom group name with prefixes and suffixes. Otherwise the classroom group create or edit will fail with errors.</span></span>

## <a name="power-bi"></a><span data-ttu-id="e211e-225">Power BI</span><span class="sxs-lookup"><span data-stu-id="e211e-225">Power BI</span></span>

<span data-ttu-id="e211e-226">Groepen die zijn gemaakt in Power BI-werkruimten voldoen aan het naamgevingsbeleid, maar het naamgevingsbeleid wordt niet automatisch toegepast.</span><span class="sxs-lookup"><span data-stu-id="e211e-226">Groups created in Power BI workspaces comply with the naming policy, but the naming policy isn't applied automatically.</span></span> <span data-ttu-id="e211e-227">En de voorbeelding van het naamgevingsbeleid wordt niet weergegeven aan gebruikers wanneer ze een Naam van power BI-werkruimte invoeren.</span><span class="sxs-lookup"><span data-stu-id="e211e-227">And, the naming policy preview isn't shown to users when they enter a Power BI workspace name.</span></span>

<span data-ttu-id="e211e-228">De aanbevolen naam - waarbij het naamgevingsbeleid is toegepast - wordt weergegeven in de foutdetails van werkruimten maken of bewerken.</span><span class="sxs-lookup"><span data-stu-id="e211e-228">The recommended name - with the naming policy applied - is shown in the error details on create or edit workspaces.</span></span> <span data-ttu-id="e211e-229">Dit betekent dat gebruikers de versierde werkruimtenaam moeten invoeren met voorvoegsels en achtervoegsels.</span><span class="sxs-lookup"><span data-stu-id="e211e-229">This means users have to enter the decorated workspace name with prefixes and suffixes.</span></span> <span data-ttu-id="e211e-230">Anders mislukt de werkruimte die wordt gemaakt of bewerkt met fouten.</span><span class="sxs-lookup"><span data-stu-id="e211e-230">Otherwise the workspace create or edit will fail with errors.</span></span>

## <a name="yammer"></a><span data-ttu-id="e211e-231">Yammer</span><span class="sxs-lookup"><span data-stu-id="e211e-231">Yammer</span></span>

<span data-ttu-id="e211e-232">Wanneer een gebruiker die zich met zijn Azure Active Directory-account heeft aangemeld bij Yammer een groep maakt of een groepsnaam bewerkt, voldoet de groepsnaam aan het naamgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="e211e-232">When a user signed in to Yammer with their Azure Active Directory account creates a group or edits a group name, the group name will comply with naming policy.</span></span> <span data-ttu-id="e211e-233">Dit geldt zowel voor verbonden Office 365-groepen als voor alle andere Yammer-groepen.</span><span class="sxs-lookup"><span data-stu-id="e211e-233">This applies both to Office 365 connected groups and all other Yammer groups.</span></span>

<span data-ttu-id="e211e-234">Als een verbonden Office 365-groep is gemaakt voordat het naamgevingsbeleid is ingevoerd, volgt de groepsnaam niet automatisch het naamgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="e211e-234">If an Office 365 connected group was created before the naming policy is in place, the group name will not automatically follow the naming policies.</span></span> <span data-ttu-id="e211e-235">Wanneer een gebruiker de groepsnaam bewerkt, wordt deze gevraagd het voorvoegsel en achtervoegsel toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="e211e-235">When a user edits the group name, they will be prompted to add the prefix and suffix.</span></span>

<span data-ttu-id="e211e-236">Als het naamgevingsbeleid tekens bevat die niet in yammer-groepsnamen kunnen staan, kunnen alleen beheerders een verbonden groep maken in Yammer.</span><span class="sxs-lookup"><span data-stu-id="e211e-236">If the naming policy includes characters that can't be in Yammer group names, only admins will be able to create a connected group in Yammer.</span></span>

## <a name="staffhub"></a><span data-ttu-id="e211e-237">StaffHub StaffHub</span><span class="sxs-lookup"><span data-stu-id="e211e-237">StaffHub</span></span>

<span data-ttu-id="e211e-238">StaffHub-teams volgen het naamgevingsbeleid niet, maar de onderliggende Office 365-groep wel.</span><span class="sxs-lookup"><span data-stu-id="e211e-238">StaffHub teams do not follow the naming policy, but the underlying Office 365 group does.</span></span> <span data-ttu-id="e211e-239">De teamnaam van StaffHub past de voorvoegsels en achtervoegsels niet toe en controleert niet op aangepaste geblokkeerde woorden.</span><span class="sxs-lookup"><span data-stu-id="e211e-239">StaffHub team name does not apply the prefixes and suffixes and does not check for custom blocked words.</span></span> <span data-ttu-id="e211e-240">Maar StaffHub past wel de voorvoegsels en achtervoegsels toe en verwijdert geblokkeerde woorden uit de onderliggende Office 365-groep.</span><span class="sxs-lookup"><span data-stu-id="e211e-240">But StaffHub does apply the prefixes and suffixes and removes blocked words from the underlying Office 365 group.</span></span>

## <a name="exchange-powershell"></a><span data-ttu-id="e211e-241">Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="e211e-241">Exchange PowerShell</span></span>

<span data-ttu-id="e211e-p131">Exchange PowerShell-cmdlets voldoen aan het naamgevingsbeleid. Als de naamsconventie niet voor groepsnamen en -aliassen wordt gebruikt, krijgen gebruikers passende foutberichten met voorgestelde voor- en achtervoegsels, en ook bij aangepaste, geblokkeerde woorden.</span><span class="sxs-lookup"><span data-stu-id="e211e-p131">Exchange PowerShell cmdlets are compliant with naming policy. Users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="azure-active-directory-powershell-cmdlets"></a><span data-ttu-id="e211e-244">Azure Active Directory PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="e211e-244">Azure Active Directory PowerShell cmdlets</span></span>

<span data-ttu-id="e211e-245">Azure Active Directory PowerShell-cmdlets voldoen aan het naamgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="e211e-245">Azure Active Directory PowerShell cmdlets are compliant with naming policy.</span></span> <span data-ttu-id="e211e-246">Als de naamsconventie niet voor groepsnamen en -aliassen wordt gebruikt, krijgen gebruikers passende foutberichten met voorgestelde voor- en achtervoegsels, en ook bij aangepaste, geblokkeerde woorden.</span><span class="sxs-lookup"><span data-stu-id="e211e-246">Users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="exchange-admin-center"></a><span data-ttu-id="e211e-247">Exchange-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="e211e-247">Exchange admin center</span></span>

<span data-ttu-id="e211e-248">Het Exchange-beheercentrum (EAC) voldoet aan het naamgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="e211e-248">The Exchange admin center (EAC) is compliant with naming policy.</span></span> <span data-ttu-id="e211e-249">Als de naamsconventie niet voor groepsnamen en -aliassen wordt gebruikt, krijgen gebruikers bij het maken en bewerken van namen passende foutberichten met voorgestelde voor- en achtervoegsels, en ook bij aangepaste, geblokkeerde woorden.</span><span class="sxs-lookup"><span data-stu-id="e211e-249">On create or edit actions, users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="microsoft-365-admin-center"></a><span data-ttu-id="e211e-250">Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="e211e-250">Microsoft 365 admin center</span></span>

<span data-ttu-id="e211e-251">Het Microsoft 365-beheercentrum voldoet aan het naamgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="e211e-251">The Microsoft 365 admin center is compliant with naming policy.</span></span> <span data-ttu-id="e211e-252">Bij het maken en bewerken van namen, wordt het naamgevingsbeleid automatisch toegepast.</span><span class="sxs-lookup"><span data-stu-id="e211e-252">On create or edit actions, naming policy will automatically get applied.</span></span> <span data-ttu-id="e211e-253">Gebruikers krijgen passende foutberichten wanneer ze aangepaste, geblokkeerde woorden invoeren.</span><span class="sxs-lookup"><span data-stu-id="e211e-253">Users will get appropriate errors when they enter custom blocked words.</span></span> <span data-ttu-id="e211e-254">In het Microsoft 365-beheercentrum wordt de voorbeeldvan het naamgevingsbeleid nog niet weergegeven en worden de aangepaste geblokkeerde woordfouten niet weergegeven wanneer de gebruiker de groepsnaam invoert.</span><span class="sxs-lookup"><span data-stu-id="e211e-254">The Microsoft 365 admin center doesn't yet show the preview of the naming policy and doesn't return the custom blocked word errors, when the user enters the group name.</span></span>

## <a name="azure-active-directory-portal"></a><span data-ttu-id="e211e-255">Azure Active Directory-portal</span><span class="sxs-lookup"><span data-stu-id="e211e-255">Azure Active Directory portal</span></span>

<span data-ttu-id="e211e-256">De Azure Active Directory-portal voldoet aan het naamgevingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="e211e-256">The Azure Active Directory portal is compliant with naming policy.</span></span> <span data-ttu-id="e211e-257">De Azure Active Directory-portal toont de voorbeeld van het naamgevingsbeleid bij het invoeren van de groepsnaam.</span><span class="sxs-lookup"><span data-stu-id="e211e-257">Azure Active Directory portal shows the naming policy preview when entering the Group name.</span></span> <span data-ttu-id="e211e-258">Wanneer een gebruiker een aangepast geblokkeerd woord invoert, wordt een foutbericht weergegeven bij het maken van de groep, zodat de gebruiker het geblokkeerde woord kan verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e211e-258">When a user enters a custom blocked word, an error message is shown on creating the group, so the user can remove the blocked word.</span></span>

## <a name="more-articles-on-naming-policy"></a><span data-ttu-id="e211e-259">Meer artikelen over naamgevingsbeleid</span><span class="sxs-lookup"><span data-stu-id="e211e-259">More articles on naming policy</span></span>

[<span data-ttu-id="e211e-260">Een naamgevingsbeleid afdwingen voor Office 365-groepen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e211e-260">Enforce a naming policy for Office 365 groups in Azure Active Directory</span></span>](https://go.microsoft.com/fwlink/?linkid=868340)

[<span data-ttu-id="e211e-261">Azure Active Directory-cmdlets voor het configureren van groepsinstellingen</span><span class="sxs-lookup"><span data-stu-id="e211e-261">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
