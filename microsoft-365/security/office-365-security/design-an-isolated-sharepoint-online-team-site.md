---
title: Een geïsoleerde SharePoint Online-teamsite ontwerpen
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: Afzonderlijke SharePoint Online-teamsites ontwerpen, waaronder machtigingsniveaus bepalen, machtigingen toewijzen aan gebruikers met toegangsgroepen en geneste Azure AD-groepen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0f92a925948dbf6c8c5c1beb6b9c709f508c4b3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165509"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="1e639-103">Een geïsoleerde SharePoint Online-teamsite ontwerpen</span><span class="sxs-lookup"><span data-stu-id="1e639-103">Design an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1e639-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="1e639-104">**Applies to**</span></span>
- [<span data-ttu-id="1e639-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="1e639-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="1e639-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e639-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


 <span data-ttu-id="1e639-107">**Overzicht:** Stap door het ontwerpproces voor afzonderlijke SharePoint Online-teamsites.</span><span class="sxs-lookup"><span data-stu-id="1e639-107">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="1e639-108">In dit artikel worden de belangrijkste ontwerpbeslissingen genomen die u moet nemen voordat u een afzonderlijke SharePoint Online-teamsite maakt.</span><span class="sxs-lookup"><span data-stu-id="1e639-108">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="1e639-109">Fase 1: Uw SharePoint-groepen en machtigingsniveaus bepalen</span><span class="sxs-lookup"><span data-stu-id="1e639-109">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="1e639-110">Elke SharePoint Online-teamsite wordt standaard gemaakt met de volgende SharePoint-groepen:</span><span class="sxs-lookup"><span data-stu-id="1e639-110">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>

- <span data-ttu-id="1e639-111">\<site name> Leden</span><span class="sxs-lookup"><span data-stu-id="1e639-111">\<site name> Members</span></span>

- <span data-ttu-id="1e639-112">\<site name> Bezoekers</span><span class="sxs-lookup"><span data-stu-id="1e639-112">\<site name> Visitors</span></span>

- <span data-ttu-id="1e639-113">\<site name> Eigenaren</span><span class="sxs-lookup"><span data-stu-id="1e639-113">\<site name> Owners</span></span>

<span data-ttu-id="1e639-114">Deze groepen staan los van Microsoft 365- en Azure Active Directory-groepen (AD) en vormen de basis voor het toewijzen van machtigingen voor de bronnen van de site.</span><span class="sxs-lookup"><span data-stu-id="1e639-114">These groups are separate from Microsoft 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>

<span data-ttu-id="1e639-115">De set specifieke machtigingen die bepaalt wat een lid van een SharePoint-groep op een site kan doen, is een machtigingsniveau.</span><span class="sxs-lookup"><span data-stu-id="1e639-115">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level.</span></span> <span data-ttu-id="1e639-116">Er zijn standaard drie machtigingsniveaus voor een SharePoint Online-teamsite: Bewerken, Lezen en Volledig beheer.</span><span class="sxs-lookup"><span data-stu-id="1e639-116">There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control.</span></span> <span data-ttu-id="1e639-117">In de volgende tabel ziet u de standaard correlatie van SharePoint-groepen en toegewezen machtigingsniveaus:</span><span class="sxs-lookup"><span data-stu-id="1e639-117">The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>

****

|<span data-ttu-id="1e639-118">SharePoint-groep</span><span class="sxs-lookup"><span data-stu-id="1e639-118">SharePoint group</span></span>|<span data-ttu-id="1e639-119">Machtigingsniveau</span><span class="sxs-lookup"><span data-stu-id="1e639-119">Permission level</span></span>|
|---|---|
|<span data-ttu-id="1e639-120">\<site name> Leden</span><span class="sxs-lookup"><span data-stu-id="1e639-120">\<site name> Members</span></span>|<span data-ttu-id="1e639-121">Bewerken</span><span class="sxs-lookup"><span data-stu-id="1e639-121">Edit</span></span>|
|<span data-ttu-id="1e639-122">\<site name> Bezoekers</span><span class="sxs-lookup"><span data-stu-id="1e639-122">\<site name> Visitors</span></span>|<span data-ttu-id="1e639-123">Lezen</span><span class="sxs-lookup"><span data-stu-id="1e639-123">Read</span></span>|
|<span data-ttu-id="1e639-124">\<site name> Eigenaren</span><span class="sxs-lookup"><span data-stu-id="1e639-124">\<site name> Owners</span></span>|<span data-ttu-id="1e639-125">Volledig beheer</span><span class="sxs-lookup"><span data-stu-id="1e639-125">Full control</span></span>|
|

 <span data-ttu-id="1e639-126">**Best practice:** U kunt extra SharePoint-groepen en machtigingsniveaus maken.</span><span class="sxs-lookup"><span data-stu-id="1e639-126">**Best practice:** You can create additional SharePoint groups and permission levels.</span></span> <span data-ttu-id="1e639-127">U wordt echter aangeraden de standaardgroepen en machtigingsniveaus van SharePoint te gebruiken voor uw afzonderlijke SharePoint Online-site.</span><span class="sxs-lookup"><span data-stu-id="1e639-127">However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>

<span data-ttu-id="1e639-128">Dit zijn de sharePoint-standaardgroepen en -machtigingsniveaus.</span><span class="sxs-lookup"><span data-stu-id="1e639-128">Here are the default SharePoint groups and permission levels.</span></span>

![De sharePoint-standaardgroepen en -machtigingsniveaus voor een SharePoint Online-site.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="1e639-130">Fase 2: Machtigingen toewijzen aan gebruikers met toegangsgroepen</span><span class="sxs-lookup"><span data-stu-id="1e639-130">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="1e639-131">U kunt machtigingen toewijzen aan gebruikers door hun gebruikersaccount of een Microsoft 365- of Azure AD-groep waarvan het gebruikersaccount lid is, toe te voegen aan de SharePoint-groepen.</span><span class="sxs-lookup"><span data-stu-id="1e639-131">You can assign permissions to users by adding their user account, or a Microsoft 365 or Azure AD group of which the user account is a member, to the SharePoint groups.</span></span> <span data-ttu-id="1e639-132">Nadat ze zijn toegevoegd, wordt aan de gebruikersaccounts, direct of indirect via lidmaatschap in een Microsoft 365- of Azure AD-groep, het machtigingsniveau toegewezen dat is gekoppeld aan de SharePoint-groep.</span><span class="sxs-lookup"><span data-stu-id="1e639-132">Once added, the user accounts, either directly or indirectly via membership in a Microsoft 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>

<span data-ttu-id="1e639-133">De standaard SharePoint-groepen als voorbeeld gebruiken:</span><span class="sxs-lookup"><span data-stu-id="1e639-133">Using the default SharePoint groups as an example:</span></span>

- <span data-ttu-id="1e639-134">Leden van **\<site name> de** SharePoint-groep Leden, die zowel gebruikersaccounts als groepen kan bevatten, krijgen het **machtigingsniveau** Bewerken toegewezen</span><span class="sxs-lookup"><span data-stu-id="1e639-134">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>

- <span data-ttu-id="1e639-135">Leden van **\<site name> de** SharePoint-groep Bezoekers, die zowel gebruikersaccounts als groepen kan bevatten, krijgen het **machtigingsniveau** Lezen</span><span class="sxs-lookup"><span data-stu-id="1e639-135">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>

- <span data-ttu-id="1e639-136">Leden van **\<site name> de** SharePoint-groep Eigenaren, die zowel gebruikersaccounts  als groepen kan bevatten, krijgen het machtigingsniveau Volledig beheer</span><span class="sxs-lookup"><span data-stu-id="1e639-136">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>

 <span data-ttu-id="1e639-137">**Best practice:** Hoewel u machtigingen kunt beheren via afzonderlijke gebruikersaccounts, raden we u aan slechts één Azure AD-groep, ook wel een toegangsgroep genoemd, te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1e639-137">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead.</span></span> <span data-ttu-id="1e639-138">Dit vereenvoudigt het beheer van machtigingen via lidmaatschap van de toegangsgroep in plaats van de lijst met gebruikersaccounts voor elke SharePoint-groep te beheren.</span><span class="sxs-lookup"><span data-stu-id="1e639-138">This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>

<span data-ttu-id="1e639-139">Azure AD-groepen voor Microsoft 365 verschillen van de Microsoft 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="1e639-139">Azure AD groups for Microsoft 365 are different tha Microsoft 365 groups.</span></span> <span data-ttu-id="1e639-140">Azure AD-groepen worden weergegeven in het Microsoft 365-beheercentrum met hun **Type** ingesteld op Beveiliging en hebben geen e-mailadres. </span><span class="sxs-lookup"><span data-stu-id="1e639-140">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="1e639-141">Azure AD-groepen kunnen worden beheerd binnen:</span><span class="sxs-lookup"><span data-stu-id="1e639-141">Azure AD groups can be managed within:</span></span>

- <span data-ttu-id="1e639-142">Active Directory Domain Services (AD DS)</span><span class="sxs-lookup"><span data-stu-id="1e639-142">Active Directory Domain Services (AD DS)</span></span>

    <span data-ttu-id="1e639-143">Dit zijn groepen die zijn gemaakt in uw on-premises AD DS-infrastructuur en zijn gesynchroniseerd met uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="1e639-143">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Microsoft 365 subscription.</span></span> <span data-ttu-id="1e639-144">In het Microsoft 365-beheercentrum hebben deze groepen de **status** **Gesynchroniseerd met active directory.**</span><span class="sxs-lookup"><span data-stu-id="1e639-144">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>

- <span data-ttu-id="1e639-145">Office 365</span><span class="sxs-lookup"><span data-stu-id="1e639-145">Office 365</span></span>

    <span data-ttu-id="1e639-146">Dit zijn groepen die zijn gemaakt met behulp van het Microsoft 365-beheercentrum, de Azure Portal of Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e639-146">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="1e639-147">In het Microsoft 365-beheercentrum hebben deze groepen de **status** **Cloud.**</span><span class="sxs-lookup"><span data-stu-id="1e639-147">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>

 <span data-ttu-id="1e639-148">**Best practice:** Als u AD DS on-premises gebruikt en synchroniseert met uw Microsoft 365-abonnement, voert u het beheer van gebruikers en groepen uit met AD DS.</span><span class="sxs-lookup"><span data-stu-id="1e639-148">**Best practice:** If you are using AD DS on-premises and synchronizing with your Microsoft 365 subscription, perform your user and group management with AD DS.</span></span>

<span data-ttu-id="1e639-149">Voor afzonderlijke SharePoint Online-teamsites ziet de aanbevolen groepsstructuur er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="1e639-149">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>

****

|<span data-ttu-id="1e639-150">SharePoint-groep</span><span class="sxs-lookup"><span data-stu-id="1e639-150">SharePoint group</span></span>|<span data-ttu-id="1e639-151">Toegangsgroep op basis van Azure AD</span><span class="sxs-lookup"><span data-stu-id="1e639-151">Azure AD-based access group</span></span>|<span data-ttu-id="1e639-152">Machtigingsniveau</span><span class="sxs-lookup"><span data-stu-id="1e639-152">Permission level</span></span>|
|---|---|---|
|<span data-ttu-id="1e639-153">\<site name> Leden</span><span class="sxs-lookup"><span data-stu-id="1e639-153">\<site name> Members</span></span>|<span data-ttu-id="1e639-154">\<site name> Leden</span><span class="sxs-lookup"><span data-stu-id="1e639-154">\<site name> Members</span></span>|<span data-ttu-id="1e639-155">Bewerken</span><span class="sxs-lookup"><span data-stu-id="1e639-155">Edit</span></span>|
|<span data-ttu-id="1e639-156">\<site name> Bezoekers</span><span class="sxs-lookup"><span data-stu-id="1e639-156">\<site name> Visitors</span></span>|<span data-ttu-id="1e639-157">\<site name> Kijkers</span><span class="sxs-lookup"><span data-stu-id="1e639-157">\<site name> Viewers</span></span>|<span data-ttu-id="1e639-158">Lezen</span><span class="sxs-lookup"><span data-stu-id="1e639-158">Read</span></span>|
|<span data-ttu-id="1e639-159">\<site name> Eigenaren</span><span class="sxs-lookup"><span data-stu-id="1e639-159">\<site name> Owners</span></span>|<span data-ttu-id="1e639-160">\<site name> Beheerders</span><span class="sxs-lookup"><span data-stu-id="1e639-160">\<site name> Admins</span></span>|<span data-ttu-id="1e639-161">Volledig beheer</span><span class="sxs-lookup"><span data-stu-id="1e639-161">Full control</span></span>|
|

 <span data-ttu-id="1e639-162">**Best practice:** Hoewel u Microsoft 365- of Azure AD-groepen kunt gebruiken als leden van SharePoint-groepen, raden we u aan Azure AD-groepen te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1e639-162">**Best practice:** Although you can use either Microsoft 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="1e639-163">Azure AD-groepen, beheerd via AD DS of Microsoft 365, bieden u meer flexibiliteit bij het gebruik van geneste groepen om machtigingen toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="1e639-163">Azure AD groups, managed either through AD DS or Microsoft 365, give you more flexibility to use nested groups to assign permissions.</span></span>

<span data-ttu-id="1e639-164">Hier zijn de standaard SharePoint-groepen die zijn geconfigureerd voor toegangsgroepen op basis van Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1e639-164">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>

![Toegangsgroepen gebruiken als leden van standaard SharePoint Online-sitegroepen.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

<span data-ttu-id="1e639-166">Houd bij het ontwerpen van de drie toegangsgroepen rekening met het volgende:</span><span class="sxs-lookup"><span data-stu-id="1e639-166">When designing the three access groups, keep the following in mind:</span></span>

- <span data-ttu-id="1e639-167">De **\<site name> toegangsgroep** Beheerders moet slechts een paar leden hebben, die betrekking hebben op een klein aantal SharePoint Online-beheerders die de teamsite beheren.</span><span class="sxs-lookup"><span data-stu-id="1e639-167">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>

- <span data-ttu-id="1e639-168">De meeste leden van uw site maken deel uit van de **\<site name> groepen Leden** **\<site name> of Viewers.**</span><span class="sxs-lookup"><span data-stu-id="1e639-168">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="1e639-169">Omdat siteleden in de **\<site name> groep Leden** toegang hebben tot de mogelijkheid resources op de site te verwijderen of te wijzigen, moet u zorgvuldig rekening houden met het lidmaatschap van de groep.</span><span class="sxs-lookup"><span data-stu-id="1e639-169">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="1e639-170">Als u twijfelt, voegt u het sitelid toe aan de **\<site name> toegangsgroep Viewers.**</span><span class="sxs-lookup"><span data-stu-id="1e639-170">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>

<span data-ttu-id="1e639-171">Hier volgen een voorbeeld van de SharePoint-groepen en toegangsgroepen voor een afzonderlijke site met de naam ProjectX.</span><span class="sxs-lookup"><span data-stu-id="1e639-171">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>

![Een voorbeeld van het gebruik van toegangsgroepen voor een SharePoint Online-site met de naam ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="1e639-173">Fase 3: Geneste Azure AD-groepen gebruiken</span><span class="sxs-lookup"><span data-stu-id="1e639-173">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="1e639-174">Voor een project dat wordt beperkt tot een klein aantal personen, past één niveau van op Azure AD gebaseerde toegangsgroepen die zijn toegevoegd aan de SharePoint-groepen van de site, in de meeste scenario's.</span><span class="sxs-lookup"><span data-stu-id="1e639-174">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios.</span></span> <span data-ttu-id="1e639-175">Als u echter een groot aantal personen hebt en die personen al lid zijn van bestaande Azure AD-groepen, kunt u gemakkelijker SharePoint-machtigingen toewijzen met behulp van geneste groepen of groepen die andere groepen als leden bevatten.</span><span class="sxs-lookup"><span data-stu-id="1e639-175">However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>

<span data-ttu-id="1e639-176">U wilt bijvoorbeeld een afzonderlijke SharePoint Online-teamsite maken om samen te werken tussen de leidinggevenden van de afdelingen Verkoop, Marketing, Engineering, Legal en Support, en die afdelingen hebben al hun eigen groepen met het lidmaatschap van een executive gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="1e639-176">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership.</span></span> <span data-ttu-id="1e639-177">In plaats van een nieuwe groep te maken voor de nieuwe siteleden en alle afzonderlijke gebruikersaccounts voor leidinggevenden in de groep te plaatsen, zet u de bestaande managementgroepen voor elke afdeling in de nieuwe groep.</span><span class="sxs-lookup"><span data-stu-id="1e639-177">Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>

 <span data-ttu-id="1e639-178">Als u een Microsoft 365-abonnement deelt tussen meerdere organisaties, kan één groepslidmaatschap voor een afzonderlijke site voor een organisatie moeilijk te beheren worden vanwege het grote aantal gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="1e639-178">If you are sharing a Microsoft 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts.</span></span> <span data-ttu-id="1e639-179">In dit geval kunt u geneste Azure AD-groepen gebruiken voor elke organisatie die de groepen binnen de organisatie bevat om de machtigingen te beheren.</span><span class="sxs-lookup"><span data-stu-id="1e639-179">In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>

<span data-ttu-id="1e639-180">Geneste Azure AD-groepen gebruiken:</span><span class="sxs-lookup"><span data-stu-id="1e639-180">To use nested Azure AD groups:</span></span>

1. <span data-ttu-id="1e639-181">Identificeer of maak de Azure AD-groepen die gebruikersaccounts bevatten en voeg de juiste gebruikersaccounts toe als leden.</span><span class="sxs-lookup"><span data-stu-id="1e639-181">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>

2. <span data-ttu-id="1e639-182">Maak de op Azure AD gebaseerde toegangsgroep van de container die de andere Azure AD-groepen bevat en voeg deze groepen toe als leden.</span><span class="sxs-lookup"><span data-stu-id="1e639-182">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>

3. <span data-ttu-id="1e639-183">Identificeer de SharePoint-groep en het bijbehorende machtigingsniveau voor het juiste toegangsniveau voor de containertoegangsgroep.</span><span class="sxs-lookup"><span data-stu-id="1e639-183">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>

> [!NOTE]
> <span data-ttu-id="1e639-184">U kunt geneste Microsoft 365-groepen niet gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1e639-184">You cannot use nested Microsoft 365 groups.</span></span>

<span data-ttu-id="1e639-185">Hier is een voorbeeld van geneste Azure AD-groepen voor de toegangsgroep voor ProjectX-leden.</span><span class="sxs-lookup"><span data-stu-id="1e639-185">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>

![Een voorbeeld van het gebruik van geneste toegangsgroepen voor de ledentoegangsgroep voor de ProjectX-site.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

<span data-ttu-id="1e639-187">Omdat alle gebruikersaccounts in de teams Research, Engineering en Project zijn bedoeld als siteleden, is het eenvoudiger om hun Azure AD-groepen toe te voegen aan de toegangsgroep ProjectX-leden.</span><span class="sxs-lookup"><span data-stu-id="1e639-187">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>

## <a name="next-step"></a><span data-ttu-id="1e639-188">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="1e639-188">Next step</span></span>

<span data-ttu-id="1e639-189">Zie Een afzonderlijke [SharePoint Online-teamsite](deploy-an-isolated-sharepoint-online-team-site.md)implementeren wanneer u klaar bent om een geïsoleerd site in productie te maken en te configureren.</span><span class="sxs-lookup"><span data-stu-id="1e639-189">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1e639-190">Zie ook</span><span class="sxs-lookup"><span data-stu-id="1e639-190">See Also</span></span>

[<span data-ttu-id="1e639-191">Geïsoleerde SharePoint Online-teamsites</span><span class="sxs-lookup"><span data-stu-id="1e639-191">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="1e639-192">Een geïsoleerde SharePoint Online-teamsite beheren</span><span class="sxs-lookup"><span data-stu-id="1e639-192">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="1e639-193">Een geïsoleerde SharePoint Online-teamsite implementeren</span><span class="sxs-lookup"><span data-stu-id="1e639-193">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
