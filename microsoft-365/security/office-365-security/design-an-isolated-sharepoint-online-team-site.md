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
ms.custom: Ent_Solutions
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 'Samenvatting: Ga door het ontwerpproces voor geïsoleerde SharePoint Online-teamsites.'
ms.openlocfilehash: f03df1f99650f458dd9df2c9e561decf491c3011
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812051"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="ec015-103">Een geïsoleerde SharePoint Online-teamsite ontwerpen</span><span class="sxs-lookup"><span data-stu-id="ec015-103">Design an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="ec015-104">**Samenvatting:** Stap door het ontwerpproces voor geïsoleerde SharePoint Online-teamsites.</span><span class="sxs-lookup"><span data-stu-id="ec015-104">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="ec015-105">In dit artikel neemt u de belangrijkste ontwerpbeslissingen die u moet nemen voordat u een geïsoleerde SharePoint Online-teamsite maakt, mee.</span><span class="sxs-lookup"><span data-stu-id="ec015-105">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="ec015-106">Fase 1: Uw SharePoint-groepen en machtigingsniveaus bepalen</span><span class="sxs-lookup"><span data-stu-id="ec015-106">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="ec015-107">Elke SharePoint Online-teamsite wordt standaard gemaakt met de volgende SharePoint-groepen:</span><span class="sxs-lookup"><span data-stu-id="ec015-107">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>
  
- <span data-ttu-id="ec015-108">\<sitenaam> leden</span><span class="sxs-lookup"><span data-stu-id="ec015-108">\<site name> Members</span></span>
    
- <span data-ttu-id="ec015-109">\<sitenaam> bezoekers</span><span class="sxs-lookup"><span data-stu-id="ec015-109">\<site name> Visitors</span></span>
    
- <span data-ttu-id="ec015-110">\<sitenaam> Eigenaren</span><span class="sxs-lookup"><span data-stu-id="ec015-110">\<site name> Owners</span></span>
    
<span data-ttu-id="ec015-111">Deze groepen zijn gescheiden van de groepen Office 365 en Azure Active Directory (AD) en vormen de basis voor het toewijzen van machtigingen voor de bronnen van de site.</span><span class="sxs-lookup"><span data-stu-id="ec015-111">These groups are separate from Office 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>
  
<span data-ttu-id="ec015-112">De set specifieke machtigingen die bepaalt wat een lid van een SharePoint-groep op een site kan doen, is een machtigingsniveau.</span><span class="sxs-lookup"><span data-stu-id="ec015-112">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level.</span></span> <span data-ttu-id="ec015-113">Er zijn standaard drie machtigingsniveaus voor een SharePoint Online-teamsite: Bewerken, Lezen en Volledig beheer.</span><span class="sxs-lookup"><span data-stu-id="ec015-113">There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control.</span></span> <span data-ttu-id="ec015-114">In de volgende tabel ziet u de standaardcorrelatie van SharePoint-groepen en toegewezen machtigingsniveaus:</span><span class="sxs-lookup"><span data-stu-id="ec015-114">The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>
  
|<span data-ttu-id="ec015-115">**SharePoint-groep**</span><span class="sxs-lookup"><span data-stu-id="ec015-115">**SharePoint group**</span></span>|<span data-ttu-id="ec015-116">**Machtigingsniveau**</span><span class="sxs-lookup"><span data-stu-id="ec015-116">**Permission level**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ec015-117">\<sitenaam> leden</span><span class="sxs-lookup"><span data-stu-id="ec015-117">\<site name> Members</span></span>  <br/> |<span data-ttu-id="ec015-118">Bewerken</span><span class="sxs-lookup"><span data-stu-id="ec015-118">Edit</span></span>  <br/> |
|<span data-ttu-id="ec015-119">\<sitenaam> bezoekers</span><span class="sxs-lookup"><span data-stu-id="ec015-119">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="ec015-120">Lezen</span><span class="sxs-lookup"><span data-stu-id="ec015-120">Read</span></span>  <br/> |
|<span data-ttu-id="ec015-121">\<sitenaam> Eigenaren</span><span class="sxs-lookup"><span data-stu-id="ec015-121">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="ec015-122">Volledige controle</span><span class="sxs-lookup"><span data-stu-id="ec015-122">Full control</span></span>  <br/> |
   
 <span data-ttu-id="ec015-123">**Beste praktijken:** U extra SharePoint-groepen en machtigingsniveaus maken.</span><span class="sxs-lookup"><span data-stu-id="ec015-123">**Best practice:** You can create additional SharePoint groups and permission levels.</span></span> <span data-ttu-id="ec015-124">We raden u echter aan de standaard SharePoint-groepen en machtigingsniveaus te gebruiken voor uw geïsoleerde SharePoint Online-site.</span><span class="sxs-lookup"><span data-stu-id="ec015-124">However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>
  
<span data-ttu-id="ec015-125">Hier volgen de standaard SharePoint-groepen en machtigingsniveaus.</span><span class="sxs-lookup"><span data-stu-id="ec015-125">Here are the default SharePoint groups and permission levels.</span></span>
  
![De standaard SharePoint-groepen en machtigingsniveaus voor een SharePoint Online-site.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="ec015-127">Fase 2: Machtigingen toewijzen aan gebruikers met toegangsgroepen</span><span class="sxs-lookup"><span data-stu-id="ec015-127">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="ec015-128">U machtigingen toewijzen aan gebruikers door hun gebruikersaccount toe te voegen of een Office 365- of Azure AD-groep waarvan het gebruikersaccount lid is, aan de SharePoint-groepen.</span><span class="sxs-lookup"><span data-stu-id="ec015-128">You can assign permissions to users by adding their user account, or an Office 365 or Azure AD group of which the user account is a member, to the SharePoint groups.</span></span> <span data-ttu-id="ec015-129">Eenmaal toegevoegd, krijgen de Office 365-gebruikersaccounts, direct of indirect via het lidmaatschap van een Office 365- of Azure AD-groep, het machtigingsniveau toegewezen dat is gekoppeld aan de SharePoint-groep.</span><span class="sxs-lookup"><span data-stu-id="ec015-129">Once added, the Office 365 user accounts, either directly or indirectly via membership in an Office 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>
  
<span data-ttu-id="ec015-130">De standaard SharePoint-groepen als voorbeeld gebruiken:</span><span class="sxs-lookup"><span data-stu-id="ec015-130">Using the default SharePoint groups as an example:</span></span>
  
- <span data-ttu-id="ec015-131">Leden van de \*\* \<sitenaam>\*\* SharePoint-groep Leden, die zowel gebruikersaccounts als groepen kunnen bevatten, krijgen het **machtigingsniveau Bewerken** toegewezen</span><span class="sxs-lookup"><span data-stu-id="ec015-131">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>
    
- <span data-ttu-id="ec015-132">Leden van de \*\* \<sitenaam>\*\* SharePoint-groep bezoekers, die zowel gebruikersaccounts als groepen kunnen bevatten, krijgen het **machtigingsniveau Lezen** toegewezen</span><span class="sxs-lookup"><span data-stu-id="ec015-132">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>
    
- <span data-ttu-id="ec015-133">Leden van de \*\* \<sitenaam>\*\* SharePoint-groep eigenaren, die zowel gebruikersaccounts als groepen kunnen bevatten, krijgen het **machtigingsniveau Volledig beheer** toegewezen</span><span class="sxs-lookup"><span data-stu-id="ec015-133">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>
    
 <span data-ttu-id="ec015-134">**Beste praktijken:** Hoewel u machtigingen beheren via afzonderlijke gebruikersaccounts, raden we u aan één Azure AD-groep te gebruiken, in plaats daarvan een toegangsgroep genoemd.</span><span class="sxs-lookup"><span data-stu-id="ec015-134">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead.</span></span> <span data-ttu-id="ec015-135">Dit vereenvoudigt het beheer van machtigingen via het lidmaatschap van de toegangsgroep, in plaats van de lijst met gebruikersaccounts voor elke SharePoint-groep te beheren.</span><span class="sxs-lookup"><span data-stu-id="ec015-135">This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>
  
<span data-ttu-id="ec015-136">Azure AD-groepen voor Office 365 zijn anders dan Office 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="ec015-136">Azure AD groups for Office 365 are different than Office 365 groups.</span></span> <span data-ttu-id="ec015-137">Azure AD-groepen worden weergegeven in het Microsoft 365-beheercentrum met hun **type** ingesteld op **Beveiliging** en hebben geen e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="ec015-137">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="ec015-138">Azure AD-groepen kunnen worden beheerd binnen:</span><span class="sxs-lookup"><span data-stu-id="ec015-138">Azure AD groups can be managed within:</span></span>
  
- <span data-ttu-id="ec015-139">Active Directory Domain Services (AD DS)</span><span class="sxs-lookup"><span data-stu-id="ec015-139">Active Directory Domain Services (AD DS)</span></span>
    
    <span data-ttu-id="ec015-140">Dit zijn groepen die zijn gemaakt in uw on-premises AD DS-infrastructuur en zijn gesynchroniseerd met uw Office 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="ec015-140">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Office 365 subscription.</span></span> <span data-ttu-id="ec015-141">In het Microsoft 365-beheercentrum hebben deze groepen een **status** van **synchronisatie met active directory**.</span><span class="sxs-lookup"><span data-stu-id="ec015-141">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>
    
- <span data-ttu-id="ec015-142">Office 365</span><span class="sxs-lookup"><span data-stu-id="ec015-142">Office 365</span></span>
    
    <span data-ttu-id="ec015-143">Dit zijn groepen die zijn gemaakt met behulp van het Microsoft 365-beheercentrum, de Azure-portal of Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec015-143">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="ec015-144">In het Microsoft 365-beheercentrum hebben deze groepen een **status** van **cloud.**</span><span class="sxs-lookup"><span data-stu-id="ec015-144">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>
    
 <span data-ttu-id="ec015-145">**Beste praktijken:** Als u AD DS on-premises gebruikt en synchroniseert met uw Office 365-abonnement, voert u uw gebruiker en groepsbeheer uit met AD DS.</span><span class="sxs-lookup"><span data-stu-id="ec015-145">**Best practice:** If you are using AD DS on-premises and synchronizing with your Office 365 subscription, perform your user and group management with AD DS.</span></span>
  
<span data-ttu-id="ec015-146">Voor geïsoleerde SharePoint Online-teamsites ziet de aanbevolen groepsstructuur er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="ec015-146">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>
  
|<span data-ttu-id="ec015-147">**SharePoint-groep**</span><span class="sxs-lookup"><span data-stu-id="ec015-147">**SharePoint group**</span></span>|<span data-ttu-id="ec015-148">**Azure AD-gebaseerde toegangsgroep**</span><span class="sxs-lookup"><span data-stu-id="ec015-148">**Azure AD-based access group**</span></span>|<span data-ttu-id="ec015-149">**Machtigingsniveau**</span><span class="sxs-lookup"><span data-stu-id="ec015-149">**Permission level**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ec015-150">\<sitenaam> leden</span><span class="sxs-lookup"><span data-stu-id="ec015-150">\<site name> Members</span></span>  <br/> |<span data-ttu-id="ec015-151">\<sitenaam> leden</span><span class="sxs-lookup"><span data-stu-id="ec015-151">\<site name> Members</span></span>  <br/> |<span data-ttu-id="ec015-152">Bewerken</span><span class="sxs-lookup"><span data-stu-id="ec015-152">Edit</span></span>  <br/> |
|<span data-ttu-id="ec015-153">\<sitenaam> bezoekers</span><span class="sxs-lookup"><span data-stu-id="ec015-153">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="ec015-154">\<sitenaam> kijkers</span><span class="sxs-lookup"><span data-stu-id="ec015-154">\<site name> Viewers</span></span>  <br/> |<span data-ttu-id="ec015-155">Lezen</span><span class="sxs-lookup"><span data-stu-id="ec015-155">Read</span></span>  <br/> |
|<span data-ttu-id="ec015-156">\<sitenaam> Eigenaren</span><span class="sxs-lookup"><span data-stu-id="ec015-156">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="ec015-157">\<sitenaam> beheerders</span><span class="sxs-lookup"><span data-stu-id="ec015-157">\<site name> Admins</span></span>  <br/> |<span data-ttu-id="ec015-158">Volledige controle</span><span class="sxs-lookup"><span data-stu-id="ec015-158">Full control</span></span>  <br/> |
   
 <span data-ttu-id="ec015-159">**Beste praktijken:** Hoewel u Office 365- of Azure AD-groepen gebruiken als leden van SharePoint-groepen, raden we u aan Azure AD-groepen te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ec015-159">**Best practice:** Although you can use either Office 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="ec015-160">Azure AD-groepen, beheerd via AD DS of Office 365, bieden u meer flexibiliteit om geneste groepen te gebruiken om machtigingen toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="ec015-160">Azure AD groups, managed either through AD DS or Office 365, give you more flexibility to use nested groups to assign permissions.</span></span>
  
<span data-ttu-id="ec015-161">Hier volgen de standaard SharePoint-groepen die zijn geconfigureerd om Op Azure AD gebaseerde toegangsgroepen te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ec015-161">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>
  
![Toegangsgroepen gebruiken als leden van standaard SharePoint Online-sitegroepen.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
<span data-ttu-id="ec015-163">Houd bij het ontwerpen van de drie toegangsgroepen rekening met het volgende:</span><span class="sxs-lookup"><span data-stu-id="ec015-163">When designing the three access groups, keep the following in mind:</span></span>
  
- <span data-ttu-id="ec015-164">Er mogen slechts een paar leden in de \*\* \<sitenaam\*\* staan> de toegangsgroep Beheerders, wat overeenkomt met een klein aantal SharePoint Online-beheerders die de teamsite beheren.</span><span class="sxs-lookup"><span data-stu-id="ec015-164">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>
    
- <span data-ttu-id="ec015-165">De meeste siteleden staan in de \*\* \<sitenaam> leden\*\* of \*\* \<sitenaam> kijkers\*\* toegang tot groepen.</span><span class="sxs-lookup"><span data-stu-id="ec015-165">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="ec015-166">Omdat siteleden in de \*\* \<sitenaam> leden\*\* toeganggroep de mogelijkheid hebben om bronnen op de site te verwijderen of te wijzigen, moet u het lidmaatschap zorgvuldig overwegen.</span><span class="sxs-lookup"><span data-stu-id="ec015-166">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="ec015-167">Voeg bij twijfel het sitelid toe aan de \*\* \<sitenaam>\*\* de toegangsgroep Kijkers.</span><span class="sxs-lookup"><span data-stu-id="ec015-167">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>
    
<span data-ttu-id="ec015-168">Hier vindt u een voorbeeld van de SharePoint-groepen en toegangsgroepen voor een geïsoleerde site met de naam ProjectX.</span><span class="sxs-lookup"><span data-stu-id="ec015-168">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>
  
![Een voorbeeld van het gebruik van toegangsgroepen voor een SharePoint Online-site met de naam ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="ec015-170">Fase 3: Geneste Azure AD-groepen gebruiken</span><span class="sxs-lookup"><span data-stu-id="ec015-170">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="ec015-171">Voor een project dat beperkt is tot een klein aantal personen, past één niveau van Azure AD-gebaseerde toegangsgroepen die zijn toegevoegd aan de SharePoint-groepen van de site in de meeste scenario's.</span><span class="sxs-lookup"><span data-stu-id="ec015-171">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios.</span></span> <span data-ttu-id="ec015-172">Als u echter een groot aantal personen hebt en deze mensen al lid zijn van gevestigde Azure AD-groepen, u SharePoint-machtigingen gemakkelijker toewijzen met behulp van geneste groepen of groepen die andere groepen als leden bevatten.</span><span class="sxs-lookup"><span data-stu-id="ec015-172">However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>
  
<span data-ttu-id="ec015-173">U wilt bijvoorbeeld een geïsoleerde Online SharePoint-teamsite maken voor samenwerking tussen de leidinggevenden van de afdelingen verkoop, marketing, engineering, juridische en ondersteuning en die afdelingen die al hun eigen groepen met een uitvoerend gebruikersaccount hebben Lidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="ec015-173">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership.</span></span> <span data-ttu-id="ec015-174">In plaats van het creëren van een nieuwe groep voor de nieuwe site leden en het plaatsen van alle individuele uitvoerende gebruikersaccounts in, zet de bestaande uitvoerende groepen voor elke afdeling in de nieuwe groep.</span><span class="sxs-lookup"><span data-stu-id="ec015-174">Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>
  
 <span data-ttu-id="ec015-175">Als u een Office 365-abonnement deelt tussen meerdere organisaties, kan een groepslidmaatschap voor een geïsoleerde site voor een organisatie moeilijk te beheren worden vanwege het enorme aantal gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="ec015-175">If you are sharing an Office 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts.</span></span> <span data-ttu-id="ec015-176">In dit geval u geneste Azure AD-groepen gebruiken voor elke organisatie die de groepen binnen hun organisatie bevat om de machtigingen te beheren.</span><span class="sxs-lookup"><span data-stu-id="ec015-176">In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>
  
<span data-ttu-id="ec015-177">Ga als nog steeds verbonden Azure AD-groepen gebruiken:</span><span class="sxs-lookup"><span data-stu-id="ec015-177">To use nested Azure AD groups:</span></span>
  
1. <span data-ttu-id="ec015-178">Identificeer of maak de Azure AD-groepen die gebruikersaccounts bevatten en voeg de juiste gebruikersaccounts toe als leden.</span><span class="sxs-lookup"><span data-stu-id="ec015-178">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>
    
2. <span data-ttu-id="ec015-179">Maak de op Azure AD gebaseerde toegangsgroep die de andere Azure AD-groepen bevat en voeg deze groepen toe als leden.</span><span class="sxs-lookup"><span data-stu-id="ec015-179">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>
    
3.  <span data-ttu-id="ec015-180">Voor het juiste toegangsniveau voor de containertoegangsgroep u de SharePoint-groep en het bijbehorende machtigingsniveau identificeren.</span><span class="sxs-lookup"><span data-stu-id="ec015-180">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ec015-181">U geneste Office 365-groepen niet gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ec015-181">You cannot use nested Office 365 groups.</span></span> 
  
<span data-ttu-id="ec015-182">Hier is een voorbeeld van geneste Azure AD-groepen voor de ProjectX-ledentoegangsgroep.</span><span class="sxs-lookup"><span data-stu-id="ec015-182">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>
  
![Een voorbeeld van het gebruik van geneste toegangsgroepen voor de ledentoegangsgroep voor de ProjectX-site.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
<span data-ttu-id="ec015-184">Omdat alle gebruikersaccounts in de teams Voor onderzoek, engineering en projectleads bedoeld zijn om siteleden te zijn, is het eenvoudiger om hun Azure AD-groepen toe te voegen aan de toegangsgroep ProjectX-leden.</span><span class="sxs-lookup"><span data-stu-id="ec015-184">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="ec015-185">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="ec015-185">Next step</span></span>

<span data-ttu-id="ec015-186">Zie [Een geïsoleerde SharePoint Online-teamsite](deploy-an-isolated-sharepoint-online-team-site.md)implementeren wanneer u klaar bent om een geïsoleerde site in productie te maken en te configureren.</span><span class="sxs-lookup"><span data-stu-id="ec015-186">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ec015-187">Zie ook</span><span class="sxs-lookup"><span data-stu-id="ec015-187">See Also</span></span>

[<span data-ttu-id="ec015-188">Geïsoleerde SharePoint Online-teamsites</span><span class="sxs-lookup"><span data-stu-id="ec015-188">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="ec015-189">Een geïsoleerde SharePoint Online-teamsite beheren</span><span class="sxs-lookup"><span data-stu-id="ec015-189">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="ec015-190">Een geïsoleerde SharePoint Online-teamsite implementeren</span><span class="sxs-lookup"><span data-stu-id="ec015-190">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



