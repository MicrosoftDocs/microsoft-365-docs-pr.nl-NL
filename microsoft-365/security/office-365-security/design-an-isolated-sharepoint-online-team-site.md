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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: Ontwerp geïsoleerde SharePoint Online-teamsites, waaronder het bepalen van machtigingsniveaus, het toewijzen van machtigingen aan gebruikers met toegangsgroepen en geneste Azure AD-groepen.
ms.openlocfilehash: 4663a0b9710fc05d0b063a3100d3b5ac223a2161
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034838"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="c7b53-103">Een geïsoleerde SharePoint Online-teamsite ontwerpen</span><span class="sxs-lookup"><span data-stu-id="c7b53-103">Design an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="c7b53-104">**Samenvatting:** Stap door het ontwerpproces voor geïsoleerde SharePoint Online-teamsites.</span><span class="sxs-lookup"><span data-stu-id="c7b53-104">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="c7b53-105">In dit artikel neemt u de belangrijkste ontwerpbeslissingen mee die u moet nemen voordat u een geïsoleerde SharePoint Online-teamsite maakt.</span><span class="sxs-lookup"><span data-stu-id="c7b53-105">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="c7b53-106">Fase 1: Uw SharePoint-groepen en machtigingsniveaus bepalen</span><span class="sxs-lookup"><span data-stu-id="c7b53-106">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="c7b53-107">Elke SharePoint Online-teamsite wordt standaard gemaakt met de volgende SharePoint-groepen:</span><span class="sxs-lookup"><span data-stu-id="c7b53-107">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>
  
- <span data-ttu-id="c7b53-108">\<sitenaam> leden</span><span class="sxs-lookup"><span data-stu-id="c7b53-108">\<site name> Members</span></span>
    
- <span data-ttu-id="c7b53-109">\<sitenaam> Bezoekers</span><span class="sxs-lookup"><span data-stu-id="c7b53-109">\<site name> Visitors</span></span>
    
- <span data-ttu-id="c7b53-110">\<sitenaam> Eigenaren</span><span class="sxs-lookup"><span data-stu-id="c7b53-110">\<site name> Owners</span></span>
    
<span data-ttu-id="c7b53-111">Deze groepen staan los van microsoft 365- en Azure Active Directory -groepen (AD) en vormen de basis voor het toewijzen van machtigingen voor de bronnen van de site.</span><span class="sxs-lookup"><span data-stu-id="c7b53-111">These groups are separate from Microsoft 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>
  
<span data-ttu-id="c7b53-112">De set specifieke machtigingen die bepaalt wat een lid van een SharePoint-groep kan doen in een site is een machtigingsniveau.</span><span class="sxs-lookup"><span data-stu-id="c7b53-112">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level.</span></span> <span data-ttu-id="c7b53-113">Er zijn standaard drie machtigingsniveaus voor een SharePoint Online-teamsite: Bewerken, Lezen en Volledig beheer.</span><span class="sxs-lookup"><span data-stu-id="c7b53-113">There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control.</span></span> <span data-ttu-id="c7b53-114">In de volgende tabel ziet u de standaardcorrelatie van SharePoint-groepen en toegewezen machtigingsniveaus:</span><span class="sxs-lookup"><span data-stu-id="c7b53-114">The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>
  
|<span data-ttu-id="c7b53-115">**SharePoint-groep**</span><span class="sxs-lookup"><span data-stu-id="c7b53-115">**SharePoint group**</span></span>|<span data-ttu-id="c7b53-116">**Machtigingsniveau**</span><span class="sxs-lookup"><span data-stu-id="c7b53-116">**Permission level**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c7b53-117">\<sitenaam> leden</span><span class="sxs-lookup"><span data-stu-id="c7b53-117">\<site name> Members</span></span>  <br/> |<span data-ttu-id="c7b53-118">Bewerken</span><span class="sxs-lookup"><span data-stu-id="c7b53-118">Edit</span></span>  <br/> |
|<span data-ttu-id="c7b53-119">\<sitenaam> Bezoekers</span><span class="sxs-lookup"><span data-stu-id="c7b53-119">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="c7b53-120">Lezen</span><span class="sxs-lookup"><span data-stu-id="c7b53-120">Read</span></span>  <br/> |
|<span data-ttu-id="c7b53-121">\<sitenaam> Eigenaren</span><span class="sxs-lookup"><span data-stu-id="c7b53-121">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="c7b53-122">Volledige controle</span><span class="sxs-lookup"><span data-stu-id="c7b53-122">Full control</span></span>  <br/> |
   
 <span data-ttu-id="c7b53-123">**Beste praktijken:** U extra SharePoint-groepen en machtigingsniveaus maken.</span><span class="sxs-lookup"><span data-stu-id="c7b53-123">**Best practice:** You can create additional SharePoint groups and permission levels.</span></span> <span data-ttu-id="c7b53-124">We raden u echter aan de standaardSharePoint-groepen en machtigingsniveaus te gebruiken voor uw geïsoleerde SharePoint Online-site.</span><span class="sxs-lookup"><span data-stu-id="c7b53-124">However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>
  
<span data-ttu-id="c7b53-125">Hier volgen de standaard SharePoint-groepen en machtigingsniveaus.</span><span class="sxs-lookup"><span data-stu-id="c7b53-125">Here are the default SharePoint groups and permission levels.</span></span>
  
![De standaardSharePoint-groepen en machtigingsniveaus voor een SharePoint Online-site.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="c7b53-127">Fase 2: Machtigingen toewijzen aan gebruikers met toegangsgroepen</span><span class="sxs-lookup"><span data-stu-id="c7b53-127">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="c7b53-128">U machtigingen toewijzen aan gebruikers door hun gebruikersaccount of een Microsoft 365- of Azure AD-groep waarvan het gebruikersaccount lid is, toe te voegen aan de SharePoint-groepen.</span><span class="sxs-lookup"><span data-stu-id="c7b53-128">You can assign permissions to users by adding their user account, or an Microsoft 365 or Azure AD group of which the user account is a member, to the SharePoint groups.</span></span> <span data-ttu-id="c7b53-129">Eenmaal toegevoegd, krijgen de gebruikersaccounts, direct of indirect via lidmaatschap in een Microsoft 365- of Azure AD-groep, het machtigingsniveau toegewezen dat is gekoppeld aan de SharePoint-groep.</span><span class="sxs-lookup"><span data-stu-id="c7b53-129">Once added, the user accounts, either directly or indirectly via membership in an Microsoft 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>
  
<span data-ttu-id="c7b53-130">Als voorbeeld de standaardSharePoint-groepen gebruiken:</span><span class="sxs-lookup"><span data-stu-id="c7b53-130">Using the default SharePoint groups as an example:</span></span>
  
- <span data-ttu-id="c7b53-131">Leden van de \*\* \<sitenaam> SharePoint-groep van leden,\*\* die zowel gebruikersaccounts als groepen kunnen bevatten, krijgen het **machtigingsniveau bewerken** toegewezen</span><span class="sxs-lookup"><span data-stu-id="c7b53-131">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>
    
- <span data-ttu-id="c7b53-132">Leden van de \*\* \<sitenaam> SharePoint-groep bezoekers,\*\* die zowel gebruikersaccounts als groepen kan bevatten, krijgen het **machtigingsniveau lezen** toegewezen</span><span class="sxs-lookup"><span data-stu-id="c7b53-132">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>
    
- <span data-ttu-id="c7b53-133">Leden van de \*\* \<sitenaam> SharePoint-groep Eigenaren,\*\* die zowel gebruikersaccounts als groepen kunnen bevatten, krijgen het **machtigingsniveau Volledig beheer** toegewezen</span><span class="sxs-lookup"><span data-stu-id="c7b53-133">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>
    
 <span data-ttu-id="c7b53-134">**Beste praktijken:** Hoewel u machtigingen beheren via afzonderlijke gebruikersaccounts, raden we u aan in plaats daarvan één Azure AD-groep te gebruiken, die een toegangsgroep wordt genoemd.</span><span class="sxs-lookup"><span data-stu-id="c7b53-134">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead.</span></span> <span data-ttu-id="c7b53-135">Dit vereenvoudigt het beheer van machtigingen via het lidmaatschap van de toegangsgroep, in plaats van het beheren van de lijst met gebruikersaccounts voor elke SharePoint-groep.</span><span class="sxs-lookup"><span data-stu-id="c7b53-135">This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>
  
<span data-ttu-id="c7b53-136">Azure AD-groepen voor Microsoft 365 zijn anders dan Microsoft 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="c7b53-136">Azure AD groups for Microsoft 365 are different than Microsoft 365 groups.</span></span> <span data-ttu-id="c7b53-137">Azure AD-groepen worden weergegeven in het Microsoft 365-beheercentrum met hun **type** ingesteld op **Beveiliging** en hebben geen e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="c7b53-137">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="c7b53-138">Azure AD-groepen kunnen worden beheerd binnen:</span><span class="sxs-lookup"><span data-stu-id="c7b53-138">Azure AD groups can be managed within:</span></span>
  
- <span data-ttu-id="c7b53-139">Active Directory Domain Services (AD DS)</span><span class="sxs-lookup"><span data-stu-id="c7b53-139">Active Directory Domain Services (AD DS)</span></span>
    
    <span data-ttu-id="c7b53-140">Dit zijn groepen die zijn gemaakt in uw on-premises AD DS-infrastructuur en zijn gesynchroniseerd met uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="c7b53-140">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Microsoft 365 subscription.</span></span> <span data-ttu-id="c7b53-141">In het Microsoft 365-beheercentrum hebben deze groepen een **status** van **gesynchroniseerd met active directory.**</span><span class="sxs-lookup"><span data-stu-id="c7b53-141">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>
    
- <span data-ttu-id="c7b53-142">Office 365</span><span class="sxs-lookup"><span data-stu-id="c7b53-142">Office 365</span></span>
    
    <span data-ttu-id="c7b53-143">Dit zijn groepen die zijn gemaakt met behulp van het Microsoft 365-beheercentrum, de Azure-portal of Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7b53-143">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="c7b53-144">In het Microsoft 365-beheercentrum hebben deze groepen een **status** van **cloud**.</span><span class="sxs-lookup"><span data-stu-id="c7b53-144">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>
    
 <span data-ttu-id="c7b53-145">**Beste praktijken:** Als u ad DS on-premises gebruikt en synchroniseert met uw Microsoft 365-abonnement, voert u uw gebruikers- en groepsbeheer uit met AD DS.</span><span class="sxs-lookup"><span data-stu-id="c7b53-145">**Best practice:** If you are using AD DS on-premises and synchronizing with your Microsoft 365 subscription, perform your user and group management with AD DS.</span></span>
  
<span data-ttu-id="c7b53-146">Voor geïsoleerde SharePoint Online-teamsites ziet de aanbevolen groepsstructuur er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="c7b53-146">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>
  
|<span data-ttu-id="c7b53-147">**SharePoint-groep**</span><span class="sxs-lookup"><span data-stu-id="c7b53-147">**SharePoint group**</span></span>|<span data-ttu-id="c7b53-148">**Azure AD-gebaseerde toegangsgroep**</span><span class="sxs-lookup"><span data-stu-id="c7b53-148">**Azure AD-based access group**</span></span>|<span data-ttu-id="c7b53-149">**Machtigingsniveau**</span><span class="sxs-lookup"><span data-stu-id="c7b53-149">**Permission level**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c7b53-150">\<sitenaam> leden</span><span class="sxs-lookup"><span data-stu-id="c7b53-150">\<site name> Members</span></span>  <br/> |<span data-ttu-id="c7b53-151">\<sitenaam> leden</span><span class="sxs-lookup"><span data-stu-id="c7b53-151">\<site name> Members</span></span>  <br/> |<span data-ttu-id="c7b53-152">Bewerken</span><span class="sxs-lookup"><span data-stu-id="c7b53-152">Edit</span></span>  <br/> |
|<span data-ttu-id="c7b53-153">\<sitenaam> Bezoekers</span><span class="sxs-lookup"><span data-stu-id="c7b53-153">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="c7b53-154">\<sitenaam> Kijkers</span><span class="sxs-lookup"><span data-stu-id="c7b53-154">\<site name> Viewers</span></span>  <br/> |<span data-ttu-id="c7b53-155">Lezen</span><span class="sxs-lookup"><span data-stu-id="c7b53-155">Read</span></span>  <br/> |
|<span data-ttu-id="c7b53-156">\<sitenaam> Eigenaren</span><span class="sxs-lookup"><span data-stu-id="c7b53-156">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="c7b53-157">\<sitenaam> Beheerders</span><span class="sxs-lookup"><span data-stu-id="c7b53-157">\<site name> Admins</span></span>  <br/> |<span data-ttu-id="c7b53-158">Volledige controle</span><span class="sxs-lookup"><span data-stu-id="c7b53-158">Full control</span></span>  <br/> |
   
 <span data-ttu-id="c7b53-159">**Beste praktijken:** Hoewel u Microsoft 365- of Azure AD-groepen gebruiken als leden van SharePoint-groepen, raden we u aan Azure AD-groepen te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c7b53-159">**Best practice:** Although you can use either Microsoft 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="c7b53-160">Azure AD-groepen, beheerd via AD DS of Microsoft 365, bieden u meer flexibiliteit om geneste groepen te gebruiken om machtigingen toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="c7b53-160">Azure AD groups, managed either through AD DS or Microsoft 365, give you more flexibility to use nested groups to assign permissions.</span></span>
  
<span data-ttu-id="c7b53-161">Hier volgen de standaard SharePoint-groepen die zijn geconfigureerd om op Azure AD gebaseerde toegangsgroepen te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c7b53-161">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>
  
![Toegangsgroepen gebruiken als leden van standaard SharePoint Online-sitegroepen.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
<span data-ttu-id="c7b53-163">Houd bij het ontwerpen van de drie toegangsgroepen rekening met het volgende:</span><span class="sxs-lookup"><span data-stu-id="c7b53-163">When designing the three access groups, keep the following in mind:</span></span>
  
- <span data-ttu-id="c7b53-164">Er mogen slechts een paar leden in de \*\* \<sitenaam>\*\* beheerders-toegangsgroep zijn, wat overeenkomt met een klein aantal SharePoint Online-beheerders die de teamsite beheren.</span><span class="sxs-lookup"><span data-stu-id="c7b53-164">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>
    
- <span data-ttu-id="c7b53-165">De meeste van uw siteleden staan in de \*\* \<sitenaam> leden\*\* of \*\* \<sitenaam> kijkers\*\* toegang tot groepen.</span><span class="sxs-lookup"><span data-stu-id="c7b53-165">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="c7b53-166">Omdat siteleden in de \*\* \<sitenaam> ledende\*\* toegangsgroep de mogelijkheid hebben om bronnen op de site te verwijderen of te wijzigen, moet u het lidmaatschap zorgvuldig overwegen.</span><span class="sxs-lookup"><span data-stu-id="c7b53-166">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="c7b53-167">Voeg bij twijfel het sitelid toe aan de \*\* \<sitenaam>\*\* kijkerstoegangsgroep.</span><span class="sxs-lookup"><span data-stu-id="c7b53-167">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>
    
<span data-ttu-id="c7b53-168">Hier vindt u een voorbeeld van de SharePoint-groepen en toegangsgroepen voor een geïsoleerde site met de naam ProjectX.</span><span class="sxs-lookup"><span data-stu-id="c7b53-168">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>
  
![Een voorbeeld van het gebruik van toegangsgroepen voor een SharePoint Online-site met de naam ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="c7b53-170">Fase 3: Geneste Azure AD-groepen gebruiken</span><span class="sxs-lookup"><span data-stu-id="c7b53-170">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="c7b53-171">Voor een project dat beperkt is tot een klein aantal personen, past één niveau van op Azure AD gebaseerde toegangsgroepen die zijn toegevoegd aan de SharePoint-groepen van de site, de meeste scenario's.</span><span class="sxs-lookup"><span data-stu-id="c7b53-171">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios.</span></span> <span data-ttu-id="c7b53-172">Als u echter een groot aantal mensen hebt en deze mensen al lid zijn van gevestigde Azure AD-groepen, u gemakkelijker SharePoint-machtigingen toewijzen door geneste groepen of groepen te gebruiken die andere groepen als leden bevatten.</span><span class="sxs-lookup"><span data-stu-id="c7b53-172">However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>
  
<span data-ttu-id="c7b53-173">U wilt bijvoorbeeld een geïsoleerde SharePoint online teamsite maken voor samenwerking tussen de leidinggevenden van de afdelingen verkoop, marketing, engineering, juridische en ondersteuningsen en die afdelingen die al hun eigen groepen hebben met een lidmaatschap van een uitvoerend gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="c7b53-173">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership.</span></span> <span data-ttu-id="c7b53-174">In plaats van het creëren van een nieuwe groep voor de nieuwe site leden en het plaatsen van alle individuele executive user accounts in, zet de bestaande uitvoerende groepen voor elke afdeling in de nieuwe groep.</span><span class="sxs-lookup"><span data-stu-id="c7b53-174">Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>
  
 <span data-ttu-id="c7b53-175">Als u een Microsoft 365-abonnement deelt tussen meerdere organisaties, kan een enkel groepslidmaatschap voor een geïsoleerde site voor een organisatie moeilijk te beheren zijn vanwege het grote aantal gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="c7b53-175">If you are sharing a Microsoft 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts.</span></span> <span data-ttu-id="c7b53-176">In dit geval u geneste Azure AD-groepen gebruiken voor elke organisatie die de groepen binnen hun organisatie bevatten om de machtigingen te beheren.</span><span class="sxs-lookup"><span data-stu-id="c7b53-176">In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>
  
<span data-ttu-id="c7b53-177">Ga als een gebruiksaanwijzing voor geneste Azure AD-groepen:</span><span class="sxs-lookup"><span data-stu-id="c7b53-177">To use nested Azure AD groups:</span></span>
  
1. <span data-ttu-id="c7b53-178">Identificeer of maak de Azure AD-groepen die gebruikersaccounts bevatten en voeg de juiste gebruikersaccounts toe als leden.</span><span class="sxs-lookup"><span data-stu-id="c7b53-178">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>
    
2. <span data-ttu-id="c7b53-179">Maak de op container Azure AD gebaseerde toegangsgroep die de andere Azure AD-groepen bevat en voeg deze groepen toe als leden.</span><span class="sxs-lookup"><span data-stu-id="c7b53-179">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>
    
3.  <span data-ttu-id="c7b53-180">Voor het juiste toegangsniveau voor de groep containertoegang u de SharePoint-groep en het bijbehorende machtigingsniveau identificeren.</span><span class="sxs-lookup"><span data-stu-id="c7b53-180">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c7b53-181">U geneste Microsoft 365-groepen niet gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c7b53-181">You cannot use nested Microsoft 365 groups.</span></span> 
  
<span data-ttu-id="c7b53-182">Hier vindt u een voorbeeld van geneste Azure AD-groepen voor de projectx-toegangsgroep voor leden.</span><span class="sxs-lookup"><span data-stu-id="c7b53-182">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>
  
![Een voorbeeld van het gebruik van geneste toegangsgroepen voor de ledentoegangsgroep voor de ProjectX-site.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
<span data-ttu-id="c7b53-184">Omdat alle gebruikersaccounts in de leadsteams Voor Onderzoek, Engineering en Project bedoeld zijn om siteleden te zijn, is het eenvoudiger om hun Azure AD-groepen toe te voegen aan de toegangsgroep voor ProjectX-leden.</span><span class="sxs-lookup"><span data-stu-id="c7b53-184">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="c7b53-185">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="c7b53-185">Next step</span></span>

<span data-ttu-id="c7b53-186">Zie [Een geïsoleerde SharePoint Online-teamsite implementeren](deploy-an-isolated-sharepoint-online-team-site.md)wanneer u een geïsoleerde site in productie wilt maken en configureren.</span><span class="sxs-lookup"><span data-stu-id="c7b53-186">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c7b53-187">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c7b53-187">See Also</span></span>

[<span data-ttu-id="c7b53-188">Geïsoleerde SharePoint Online-teamsites</span><span class="sxs-lookup"><span data-stu-id="c7b53-188">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="c7b53-189">Een geïsoleerde SharePoint Online-teamsite beheren</span><span class="sxs-lookup"><span data-stu-id="c7b53-189">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="c7b53-190">Een geïsoleerde SharePoint Online-teamsite implementeren</span><span class="sxs-lookup"><span data-stu-id="c7b53-190">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



