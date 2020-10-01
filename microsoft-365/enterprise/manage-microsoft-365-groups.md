---
title: Microsoft 365-groepen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Meer informatie over het beheren van Microsoft 365 groepen.
ms.openlocfilehash: a01bf5dcc0b87cbdce8d7044b666cfb3a16a5aa9
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328498"
---
# <a name="manage-microsoft-365-groups"></a><span data-ttu-id="c2b36-103">Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="c2b36-103">Manage Microsoft 365 groups</span></span>

<span data-ttu-id="c2b36-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c2b36-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c2b36-105">U kunt Microsoft 365-groepen op verschillende manieren beheren, afhankelijk van de configuratie.</span><span class="sxs-lookup"><span data-stu-id="c2b36-105">You can manage Microsoft 365 groups in several different ways, depending on your configuration.</span></span> <span data-ttu-id="c2b36-106">U kunt gebruikersaccounts beheren in het [Microsoft 365-Beheercentrum](https://docs.microsoft.com/microsoft-365/admin/add-users/), powershell, in Active Directory Domain Services (AD DS) of in het [Azure Active Directory-beheercentrum (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="c2b36-106">You can manage user accounts in the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/), PowerShell, in Active Directory Domain Services (AD DS), or in the [Azure Active Directory (Azure AD) admin center](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span></span> 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a><span data-ttu-id="c2b36-107">Plannen waar en hoe u uw groepen beheert</span><span class="sxs-lookup"><span data-stu-id="c2b36-107">Plan for where and how you will manage your groups</span></span>

<span data-ttu-id="c2b36-108">Waar en hoe u uw gebruikersaccounts kunt beheren, is afhankelijk van het identiteits model dat u wilt gebruiken voor uw Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c2b36-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="c2b36-109">De twee algemene modellen zijn alleen in de Cloud en hybride.</span><span class="sxs-lookup"><span data-stu-id="c2b36-109">The two overall models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="c2b36-110">Alleen in de cloud</span><span class="sxs-lookup"><span data-stu-id="c2b36-110">Cloud-only</span></span>

<span data-ttu-id="c2b36-111">U maakt en beheert groepen met:</span><span class="sxs-lookup"><span data-stu-id="c2b36-111">You create and manage groups with:</span></span>

- [<span data-ttu-id="c2b36-112">Het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="c2b36-112">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [<span data-ttu-id="c2b36-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2b36-113">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c2b36-114">Azure AD-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="c2b36-114">Azure AD admin center</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a><span data-ttu-id="c2b36-115">Hybride</span><span class="sxs-lookup"><span data-stu-id="c2b36-115">Hybrid</span></span>

<span data-ttu-id="c2b36-116">AD DS-groepen worden gesynchroniseerd met Microsoft 365 vanuit AD DS, zodat u on-premises AD DS-hulpprogramma's moet gebruiken voor het beheren van deze groepen.</span><span class="sxs-lookup"><span data-stu-id="c2b36-116">AD DS groups are synchronized with Microsoft 365 from AD DS, so you must use on-premises AD DS tools to manage these groups.</span></span>

<span data-ttu-id="c2b36-117">U kunt ook Azure AD-groepen maken en beheren die geen deel uitmaken van Active Directory-groepen, maar u kunt ook gebruikers en groepen uit AD DS opnemen.</span><span class="sxs-lookup"><span data-stu-id="c2b36-117">You can also create and manage Azure AD groups that are separate from AD DS groups but can contain users and groups from AD DS.</span></span> <span data-ttu-id="c2b36-118">In dit geval kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="c2b36-118">In this case, you can use:</span></span>

- [<span data-ttu-id="c2b36-119">Het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="c2b36-119">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [<span data-ttu-id="c2b36-120">PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2b36-120">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c2b36-121">Azure AD-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="c2b36-121">Azure AD admin center</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="c2b36-122">Bied gebruikers de mogelijkheid om hun eigen groepen te maken en beheren</span><span class="sxs-lookup"><span data-stu-id="c2b36-122">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="c2b36-123">In azure AD kunnen groepen worden beheerd door groepseigenaren in plaats van IT-beheerders.</span><span class="sxs-lookup"><span data-stu-id="c2b36-123">Azure AD allows groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="c2b36-124">Met deze functie, die *selfservice-groepsbeheer* wordt genoemd, kunnen groepseigenaren waaraan geen beheerdersrol is toegewezen, beveiligingsgroepen maken en beheren.</span><span class="sxs-lookup"><span data-stu-id="c2b36-124">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="c2b36-125">Gebruikers kunnen lidmaatschap van een beveiligingsgroep aanvragen en dit verzoek wordt vervolgens naar de eigenaar van de groep gestuurd, in plaats van een IT-beheerder.</span><span class="sxs-lookup"><span data-stu-id="c2b36-125">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator.</span></span> <span data-ttu-id="c2b36-126">Dit maakt het mogelijk om het groepslidmaatschap te laten beheren door team-, project- of bedrijfseigenaren die het zakelijke doel van de groep begrijpen en het lidmaatschap ervan kunnen beheren.</span><span class="sxs-lookup"><span data-stu-id="c2b36-126">This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="c2b36-127">Selfservice-groepsbeheer is alleen beschikbaar voor Azure AD-beveiligingsgroepen en Microsoft 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="c2b36-127">Self-service group management is available only for Azure AD security and Microsoft 365 groups.</span></span> <span data-ttu-id="c2b36-128">Deze functie is niet beschikbaar voor groepen met e-mail, distributielijsten of groepen die zijn gesynchroniseerd vanuit AD DS.</span><span class="sxs-lookup"><span data-stu-id="c2b36-128">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from AD DS.</span></span>
>

<span data-ttu-id="c2b36-129">Zie de [instructies voor het configureren van een Azure AD-groep voor selfservice-beheer](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c2b36-129">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="c2b36-130">Dynamisch groepslidmaatschap instellen</span><span class="sxs-lookup"><span data-stu-id="c2b36-130">Set up dynamic group membership</span></span>

<span data-ttu-id="c2b36-131">Azure AD biedt ondersteuning voor het configureren van een reeks regels waarmee automatisch gebruikersaccounts worden toegevoegd of verwijderd als lid van een Azure AD-groep.</span><span class="sxs-lookup"><span data-stu-id="c2b36-131">Azure AD supports configuring a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="c2b36-132">Dit wordt *dynamisch groepslidmaatschap* genoemd.</span><span class="sxs-lookup"><span data-stu-id="c2b36-132">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="c2b36-133">De regels zijn gebaseerd op kenmerken van gebruikersaccounts, zoals Afdeling of Land.</span><span class="sxs-lookup"><span data-stu-id="c2b36-133">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="c2b36-134">De regels worden als volgt toegepast:</span><span class="sxs-lookup"><span data-stu-id="c2b36-134">Here's how the rules are applied:</span></span>

- <span data-ttu-id="c2b36-135">Als een nieuw gebruikersaccount aan alle regels voor de groep voldoet, wordt het lid.</span><span class="sxs-lookup"><span data-stu-id="c2b36-135">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="c2b36-136">Als een gebruikersaccount geen lid is van de groep, maar de bijbehorende kenmerken zodanig worden gewijzigd dat deze voldoen aan alle regels voor de groep, wordt het account lid van die groep.</span><span class="sxs-lookup"><span data-stu-id="c2b36-136">If a user account isn't a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="c2b36-137">Als een gebruikersaccount niet voldoet aan alle regels voor de groep, wordt het niet toegevoegd aan de groep.</span><span class="sxs-lookup"><span data-stu-id="c2b36-137">If a user account doesn't match all the rules for the group, it isn't added to the group.</span></span>
- <span data-ttu-id="c2b36-138">Als een gebruikersaccount lid is van de groep, maar de bijbehorende kenmerken zodanig worden gewijzigd dat het niet meer voldoet aan alle regels voor de groep, wordt het account als lid van de groep verwijderd.</span><span class="sxs-lookup"><span data-stu-id="c2b36-138">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="c2b36-139">Als u dynamisch lidmaatschap wilt gebruiken, moet u eerst bepalen welke sets groepen een gemeenschappelijke set gebruikersaccountkenmerken hebben.</span><span class="sxs-lookup"><span data-stu-id="c2b36-139">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes.</span></span> <span data-ttu-id="c2b36-140">Zo moeten bijvoorbeeld alle leden van de afdeling Verkoop zich bevinden in de Azure AD-groep Verkoop op basis van het gebruikersaccountkenmerk Afdeling met de waarde 'Verkoop'.</span><span class="sxs-lookup"><span data-stu-id="c2b36-140">For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to "Sales".</span></span>

<span data-ttu-id="c2b36-141">Zie de [instructies voor het maken en configureren van de regels voor een dynamische Azure AD-groep](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="c2b36-141">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

## <a name="set-up-automatic-licensing"></a><span data-ttu-id="c2b36-142">Automatische licentie instellen</span><span class="sxs-lookup"><span data-stu-id="c2b36-142">Set up automatic licensing</span></span>

<span data-ttu-id="c2b36-143">U kunt beveiligingsgroepen configureren in azure AD om automatisch licenties toe te wijzen aan een reeks abonnementen voor alle leden van de groep.</span><span class="sxs-lookup"><span data-stu-id="c2b36-143">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="c2b36-144">Dit wordt *licenties op groepsbasis* genoemd.</span><span class="sxs-lookup"><span data-stu-id="c2b36-144">This is known as *group-based licensing*.</span></span> <span data-ttu-id="c2b36-145">Als een gebruikersaccount wordt toegevoegd aan of verwijderd uit de groep, worden de licenties voor de groepsabonnementen automatisch toegewezen aan of verwijderd van het gebruikersaccount. </span><span class="sxs-lookup"><span data-stu-id="c2b36-145">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="c2b36-146">Voor Microsoft 365 Enterprise worden Azure AD-beveiligingsgroepen geconfigureerd om de juiste Microsoft 365 Enterprise-licentie toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="c2b36-146">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="c2b36-147">Zorg ervoor dat u genoeg licenties hebt voor alle groepsleden.</span><span class="sxs-lookup"><span data-stu-id="c2b36-147">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="c2b36-148">Als u niet genoeg licenties hebt, krijgen nieuwe gebruikers geen licenties totdat er weer licenties beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="c2b36-148">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="c2b36-149">Voor groepen die Azure B2B-accounts (business-to-business) bevatten, dient u licenties op groepsbasis niet te configureren.</span><span class="sxs-lookup"><span data-stu-id="c2b36-149">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="c2b36-150">Zie [beginselen van licentieverlening op basis van groepen in azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c2b36-150">For more information, see [Group-based licensing basics in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="c2b36-151">Zie de [instructies voor het configureren van de op groepen gebaseerde licentieverlening voor een Azure-beveiligingsgroep](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="c2b36-151">See the [instructions to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>
