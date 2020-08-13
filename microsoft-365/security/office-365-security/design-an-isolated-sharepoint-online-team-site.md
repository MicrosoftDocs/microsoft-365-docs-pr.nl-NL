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
description: U kunt geïsoleerde, geïsoleerde SharePoint Online-team sites ontwerpen, waaronder machtigingsniveaus bepalen, machtigingen toewijzen aan gebruikers met toegangsgroepen en geneste Azure AD-groepen.
ms.openlocfilehash: d26f55d9e037d86eac28e5cf21c56406eae5cc19
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653003"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="68152-103">Een geïsoleerde SharePoint Online-teamsite ontwerpen</span><span class="sxs-lookup"><span data-stu-id="68152-103">Design an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="68152-104">**Overzicht:** Stap voor stap door het ontwerpproces voor geïsoleerde SharePoint Online-team sites.</span><span class="sxs-lookup"><span data-stu-id="68152-104">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="68152-105">In dit artikel wordt u stapsgewijs begeleid bij het maken van een geïsoleerde ontwerp site van SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="68152-105">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="68152-106">Fase 1: uw SharePoint-groepen en machtigingsniveaus bepalen</span><span class="sxs-lookup"><span data-stu-id="68152-106">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="68152-107">Elke SharePoint Online-team site wordt standaard gemaakt met de volgende SharePoint-groepen:</span><span class="sxs-lookup"><span data-stu-id="68152-107">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>

- <span data-ttu-id="68152-108">\<site name>Leden</span><span class="sxs-lookup"><span data-stu-id="68152-108">\<site name> Members</span></span>

- <span data-ttu-id="68152-109">\<site name>Plaatst</span><span class="sxs-lookup"><span data-stu-id="68152-109">\<site name> Visitors</span></span>

- <span data-ttu-id="68152-110">\<site name>Sites</span><span class="sxs-lookup"><span data-stu-id="68152-110">\<site name> Owners</span></span>

<span data-ttu-id="68152-111">Deze groepen zijn gescheiden van de groepen Microsoft 365 en Azure Active Directory (AD) en vormen de basis voor het toewijzen van machtigingen voor de bronnen van de site.</span><span class="sxs-lookup"><span data-stu-id="68152-111">These groups are separate from Microsoft 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>

<span data-ttu-id="68152-112">De set specifieke machtigingen waarmee wordt bepaald wat een lid van een SharePoint-groep in een site kan doen, is een machtigingsniveau.</span><span class="sxs-lookup"><span data-stu-id="68152-112">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level.</span></span> <span data-ttu-id="68152-113">Een SharePoint Online-team site bevat standaard drie machtigingsniveaus: bewerken, lezen en volledig beheer.</span><span class="sxs-lookup"><span data-stu-id="68152-113">There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control.</span></span> <span data-ttu-id="68152-114">In de volgende tabel wordt de standaard correlatie van SharePoint-groepen en de toegewezen machtigingsniveaus weergegeven:</span><span class="sxs-lookup"><span data-stu-id="68152-114">The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>

****

|<span data-ttu-id="68152-115">SharePoint-groep</span><span class="sxs-lookup"><span data-stu-id="68152-115">SharePoint group</span></span>|<span data-ttu-id="68152-116">Machtigingsniveau</span><span class="sxs-lookup"><span data-stu-id="68152-116">Permission level</span></span>|
|---|---|
|<span data-ttu-id="68152-117">\<site name>Leden</span><span class="sxs-lookup"><span data-stu-id="68152-117">\<site name> Members</span></span>|<span data-ttu-id="68152-118">Bewerken</span><span class="sxs-lookup"><span data-stu-id="68152-118">Edit</span></span>|
|<span data-ttu-id="68152-119">\<site name>Plaatst</span><span class="sxs-lookup"><span data-stu-id="68152-119">\<site name> Visitors</span></span>|<span data-ttu-id="68152-120">Lezen</span><span class="sxs-lookup"><span data-stu-id="68152-120">Read</span></span>|
|<span data-ttu-id="68152-121">\<site name>Sites</span><span class="sxs-lookup"><span data-stu-id="68152-121">\<site name> Owners</span></span>|<span data-ttu-id="68152-122">Volledig beheer</span><span class="sxs-lookup"><span data-stu-id="68152-122">Full control</span></span>|
|

 <span data-ttu-id="68152-123">**Aanbevolen procedure:** U kunt extra SharePoint-groepen en machtigingsniveaus maken.</span><span class="sxs-lookup"><span data-stu-id="68152-123">**Best practice:** You can create additional SharePoint groups and permission levels.</span></span> <span data-ttu-id="68152-124">We raden u echter aan gebruik te maken van de standaardshare Point-groepen en machtigingsniveaus voor de geïsoleerde SharePoint Online-site.</span><span class="sxs-lookup"><span data-stu-id="68152-124">However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>

<span data-ttu-id="68152-125">Hier volgen de standaardshare Point-groepen en machtigingsniveaus.</span><span class="sxs-lookup"><span data-stu-id="68152-125">Here are the default SharePoint groups and permission levels.</span></span>

![De standaardshare Point-groepen en machtigingsniveaus voor een SharePoint Online-site.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="68152-127">Fase 2: machtigingen toewijzen aan gebruikers met toegangsgroepen</span><span class="sxs-lookup"><span data-stu-id="68152-127">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="68152-128">U kunt machtigingen toewijzen aan gebruikers door hun gebruikersaccount toe te voegen of een Microsoft 365-of Azure AD-groep waarvan het gebruikersaccount lid is van de SharePoint-groepen.</span><span class="sxs-lookup"><span data-stu-id="68152-128">You can assign permissions to users by adding their user account, or a Microsoft 365 or Azure AD group of which the user account is a member, to the SharePoint groups.</span></span> <span data-ttu-id="68152-129">Wanneer u eenmaal hebt toegevoegd, worden de gebruikersaccounts direct of indirect via lidmaatschap van een groep van Microsoft 365 of Azure AD toegewezen aan het machtigingsniveau dat is gekoppeld aan de SharePoint-groep.</span><span class="sxs-lookup"><span data-stu-id="68152-129">Once added, the user accounts, either directly or indirectly via membership in a Microsoft 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>

<span data-ttu-id="68152-130">Het gebruik van de standaardshare Point-groepen als voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="68152-130">Using the default SharePoint groups as an example:</span></span>

- <span data-ttu-id="68152-131">Leden van de SharePoint-groep \*\* \<site name> leden\*\* , die beide gebruikersaccounts en groepen kunnen bevatten, krijgen het machtigingsniveau **bewerken**</span><span class="sxs-lookup"><span data-stu-id="68152-131">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>

- <span data-ttu-id="68152-132">Leden van de SharePoint-groep \*\* \<site name> bezoekers\*\* , die zowel gebruikersaccounts als groepen kunnen bevatten, hebben het machtigingsniveau **lezen** toegewezen</span><span class="sxs-lookup"><span data-stu-id="68152-132">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>

- <span data-ttu-id="68152-133">Leden van de SharePoint-groep \*\* \<site name> eigenaren\*\* , waaronder gebruikersaccounts en groepen, kunnen het machtigingsniveau **volledig beheer** hebben.</span><span class="sxs-lookup"><span data-stu-id="68152-133">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>

 <span data-ttu-id="68152-134">**Aanbevolen procedure:** Hoewel u machtigingen kunt beheren via afzonderlijke gebruikersaccounts, kunt u het beste één Azure AD-groep gebruiken, ook wel een Access-groep genoemd.</span><span class="sxs-lookup"><span data-stu-id="68152-134">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead.</span></span> <span data-ttu-id="68152-135">Dit vergemakkelijkt het beheer van machtigingen door lidmaatschap van de Access-groep, in plaats van de lijst met gebruikersaccounts voor elke SharePoint-groep te beheren.</span><span class="sxs-lookup"><span data-stu-id="68152-135">This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>

<span data-ttu-id="68152-136">Azure AD-groepen voor Microsoft 365 zijn verschillend tha Microsoft 365 groepen.</span><span class="sxs-lookup"><span data-stu-id="68152-136">Azure AD groups for Microsoft 365 are different tha Microsoft 365 groups.</span></span> <span data-ttu-id="68152-137">Azure AD-groepen worden weergegeven in het Microsoft 365-Beheercentrum, waarbij hun **type** is ingesteld op **beveiliging** en geen e-mailadres heeft.</span><span class="sxs-lookup"><span data-stu-id="68152-137">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="68152-138">Azure AD-groepen kunnen worden beheerd binnen:</span><span class="sxs-lookup"><span data-stu-id="68152-138">Azure AD groups can be managed within:</span></span>

- <span data-ttu-id="68152-139">Active Directory Domain Services (AD DS)</span><span class="sxs-lookup"><span data-stu-id="68152-139">Active Directory Domain Services (AD DS)</span></span>

    <span data-ttu-id="68152-140">Dit zijn groepen die zijn gemaakt in uw on-premises AD DS-infrastructuur en die zijn gesynchroniseerd met uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="68152-140">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Microsoft 365 subscription.</span></span> <span data-ttu-id="68152-141">In het Microsoft 365-Beheercentrum hebben deze groepen **Status** de status **gesynchroniseerd met Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="68152-141">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>

- <span data-ttu-id="68152-142">Office 365</span><span class="sxs-lookup"><span data-stu-id="68152-142">Office 365</span></span>

    <span data-ttu-id="68152-143">Dit zijn groepen die zijn gemaakt met het Microsoft 365-Beheercentrum, de Azure-portal of Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68152-143">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="68152-144">In het Microsoft 365-Beheercentrum hebben deze groepen **Status** de status **Cloud**.</span><span class="sxs-lookup"><span data-stu-id="68152-144">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>

 <span data-ttu-id="68152-145">**Aanbevolen procedure:** Als u AD DS on-premises gebruikt en synchroniseert met uw Microsoft 365-abonnement, voert u uw gebruikers-en groepsbeheer met AD DS uit.</span><span class="sxs-lookup"><span data-stu-id="68152-145">**Best practice:** If you are using AD DS on-premises and synchronizing with your Microsoft 365 subscription, perform your user and group management with AD DS.</span></span>

<span data-ttu-id="68152-146">Voor geïsoleerde SharePoint Online-team sites ziet de aanbevolen groepsstructuur er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="68152-146">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>

****

|<span data-ttu-id="68152-147">SharePoint-groep</span><span class="sxs-lookup"><span data-stu-id="68152-147">SharePoint group</span></span>|<span data-ttu-id="68152-148">Azure AD-basis toegangsgroep</span><span class="sxs-lookup"><span data-stu-id="68152-148">Azure AD-based access group</span></span>|<span data-ttu-id="68152-149">Machtigingsniveau</span><span class="sxs-lookup"><span data-stu-id="68152-149">Permission level</span></span>|
|---|---|---|
|<span data-ttu-id="68152-150">\<site name>Leden</span><span class="sxs-lookup"><span data-stu-id="68152-150">\<site name> Members</span></span>|<span data-ttu-id="68152-151">\<site name>Leden</span><span class="sxs-lookup"><span data-stu-id="68152-151">\<site name> Members</span></span>|<span data-ttu-id="68152-152">Bewerken</span><span class="sxs-lookup"><span data-stu-id="68152-152">Edit</span></span>|
|<span data-ttu-id="68152-153">\<site name>Plaatst</span><span class="sxs-lookup"><span data-stu-id="68152-153">\<site name> Visitors</span></span>|<span data-ttu-id="68152-154">\<site name>Mensen</span><span class="sxs-lookup"><span data-stu-id="68152-154">\<site name> Viewers</span></span>|<span data-ttu-id="68152-155">Lezen</span><span class="sxs-lookup"><span data-stu-id="68152-155">Read</span></span>|
|<span data-ttu-id="68152-156">\<site name>Sites</span><span class="sxs-lookup"><span data-stu-id="68152-156">\<site name> Owners</span></span>|<span data-ttu-id="68152-157">\<site name>Beheerders</span><span class="sxs-lookup"><span data-stu-id="68152-157">\<site name> Admins</span></span>|<span data-ttu-id="68152-158">Volledig beheer</span><span class="sxs-lookup"><span data-stu-id="68152-158">Full control</span></span>|
|

 <span data-ttu-id="68152-159">**Aanbevolen procedure:** Hoewel u Microsoft 365 of een Azure AD-groep als lid van SharePoint-groepen kunt gebruiken, kunt u het beste gebruikmaken van Azure AD-groepen.</span><span class="sxs-lookup"><span data-stu-id="68152-159">**Best practice:** Although you can use either Microsoft 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="68152-160">Azure AD-groepen die worden beheerd via de AD DS of Microsoft 365, bieden u meer flexibiliteit bij het toewijzen van geneste groepen aan machtigingen.</span><span class="sxs-lookup"><span data-stu-id="68152-160">Azure AD groups, managed either through AD DS or Microsoft 365, give you more flexibility to use nested groups to assign permissions.</span></span>

<span data-ttu-id="68152-161">Hier volgen de standaardshare Point-groepen die zijn geconfigureerd voor het gebruik van Azure AD-gebaseerde toegangsgroepen.</span><span class="sxs-lookup"><span data-stu-id="68152-161">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>

![Toegangsgroepen gebruiken als leden van standaardsitegroepen van SharePoint Online.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

<span data-ttu-id="68152-163">Houd bij het ontwerpen van de drie toegangsgroepen rekening met het volgende:</span><span class="sxs-lookup"><span data-stu-id="68152-163">When designing the three access groups, keep the following in mind:</span></span>

- <span data-ttu-id="68152-164">U moet slechts enkele leden in de groep \*\* \<site name> beheerders\*\* toegang hebben, dat overeenkomt met een klein aantal beheerders van SharePoint Online dat de team site beheert.</span><span class="sxs-lookup"><span data-stu-id="68152-164">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>

- <span data-ttu-id="68152-165">De meeste van de siteleden bevinden zich in de groepen \*\* \<site name> leden\*\* en \*\* \<site name> kijkers\*\* .</span><span class="sxs-lookup"><span data-stu-id="68152-165">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="68152-166">Aangezien siteleden in de groep \*\* \<site name> leden\*\* toegang de mogelijkheid hebben om bronnen op de site te verwijderen of te wijzigen, is het belangrijk om rekening te houden met het lidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="68152-166">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="68152-167">Wanneer u twijfelt, voegt u de site lid toe aan de groep \*\* \<site name> gebruikers\*\* toegang.</span><span class="sxs-lookup"><span data-stu-id="68152-167">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>

<span data-ttu-id="68152-168">Hier ziet u een voorbeeld van de SharePoint-groepen en toegangsgroepen voor een afzonderlijke site met de naam Projectx.</span><span class="sxs-lookup"><span data-stu-id="68152-168">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>

![Een voorbeeld van het gebruik van toegangsgroepen voor een SharePoint Online-site met de naam Projectx.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="68152-170">Fase 3: geneste Azure AD-groepen gebruiken</span><span class="sxs-lookup"><span data-stu-id="68152-170">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="68152-171">Voor een project dat is afgestemd op een klein aantal personen, passen de meeste scenario's in één niveau van Azure AD-based Access-groepen die aan de SharePoint-groepen van de site zijn toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="68152-171">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios.</span></span> <span data-ttu-id="68152-172">Als u echter een groot aantal personen hebt en deze personen al deel uitmaken van de gevestigde Azure AD-groepen, kunt u eenvoudiger SharePoint-machtigingen toewijzen met geneste groepen of groepen die andere groepen als leden hebben.</span><span class="sxs-lookup"><span data-stu-id="68152-172">However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>

<span data-ttu-id="68152-173">U wilt bijvoorbeeld een geïsoleerde SharePoint Online-team site maken voor samenwerking tussen de leidinggevenden van de afdelingen voor verkoop, marketing, engineering, juridisch en ondersteunings afdelingen en van deze afdelingen al hun eigen groepen met lidmaatschap van het account van de beheerder.</span><span class="sxs-lookup"><span data-stu-id="68152-173">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership.</span></span> <span data-ttu-id="68152-174">In plaats van een nieuwe groep te maken voor de nieuwe siteleden en alle afzonderlijke gebruikersaccounts voor de beheerder in de groep te plaatsen, moet u de bestaande Executive groepen voor elke afdeling in de nieuwe groep.</span><span class="sxs-lookup"><span data-stu-id="68152-174">Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>

 <span data-ttu-id="68152-175">Als u een Microsoft 365-abonnement deelt tussen meerdere organisaties, kan het lastig zijn om een bepaald niveau van groepslidmaatschappen voor een geïsoleerde site van een organisatie te beheren vanwege het doorschijnende-aantal gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="68152-175">If you are sharing a Microsoft 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts.</span></span> <span data-ttu-id="68152-176">In dit geval kunt u geneste Azure AD-groepen gebruiken voor elke organisatie die de groepen binnen hun organisatie bevat om de machtigingen te beheren.</span><span class="sxs-lookup"><span data-stu-id="68152-176">In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>

<span data-ttu-id="68152-177">Geneste Azure AD-groepen gebruiken:</span><span class="sxs-lookup"><span data-stu-id="68152-177">To use nested Azure AD groups:</span></span>

1. <span data-ttu-id="68152-178">Identificeer of maak de Azure AD-groepen die gebruikersaccounts moeten bevatten en voeg de juiste gebruikersaccounts toe als leden.</span><span class="sxs-lookup"><span data-stu-id="68152-178">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>

2. <span data-ttu-id="68152-179">Maak de in de container Azure AD gebaseerde toegangsgroep die de andere Azure AD-groepen moet bevatten en voeg deze groepen toe als leden.</span><span class="sxs-lookup"><span data-stu-id="68152-179">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>

3. <span data-ttu-id="68152-180">Identificeer de SharePoint-groep en het bijbehorende machtigingsniveau voor het juiste toegangsniveau voor de groep container toegang.</span><span class="sxs-lookup"><span data-stu-id="68152-180">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>

> [!NOTE]
> <span data-ttu-id="68152-181">U kunt geneste Microsoft 365-groepen niet gebruiken.</span><span class="sxs-lookup"><span data-stu-id="68152-181">You cannot use nested Microsoft 365 groups.</span></span>

<span data-ttu-id="68152-182">Hier ziet u een voorbeeld van geneste Azure AD-groepen voor de groep leden toegang van Projectx.</span><span class="sxs-lookup"><span data-stu-id="68152-182">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>

![Een voorbeeld van het gebruik van geneste toegangsgroepen voor de groep leden toegang voor de Projectx-site.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

<span data-ttu-id="68152-184">Aangezien alle gebruikersaccounts in de teams voor onderzoek, engineering en project bedoeld zijn om siteleden te zijn, is het eenvoudiger om Azure AD-groepen toe te voegen aan de groep toegang tot leden van Projectx.</span><span class="sxs-lookup"><span data-stu-id="68152-184">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>

## <a name="next-step"></a><span data-ttu-id="68152-185">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="68152-185">Next step</span></span>

<span data-ttu-id="68152-186">Wanneer u klaar bent om een geïsoleerde site te maken en te configureren, raadpleegt u [een geïsoleerde SharePoint Online-team site implementeren](deploy-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="68152-186">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="68152-187">Zie ook</span><span class="sxs-lookup"><span data-stu-id="68152-187">See Also</span></span>

[<span data-ttu-id="68152-188">Geïsoleerde SharePoint Online-teamsites</span><span class="sxs-lookup"><span data-stu-id="68152-188">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="68152-189">Een geïsoleerde SharePoint Online-teamsite beheren</span><span class="sxs-lookup"><span data-stu-id="68152-189">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="68152-190">Een geïsoleerde SharePoint Online-teamsite implementeren</span><span class="sxs-lookup"><span data-stu-id="68152-190">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
