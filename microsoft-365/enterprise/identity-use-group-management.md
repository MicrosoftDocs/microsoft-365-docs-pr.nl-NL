---
title: 'Stap 5: Groepen gebruiken voor beheer'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: U kunt groepen gebruiken om het beheer van sommige administratieve taken te automatiseren.
ms.openlocfilehash: 215bb84cbb0cedc2f1320372ba8239cd51d07c98
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806105"
---
# <a name="step-5-use-groups-for-management"></a><span data-ttu-id="7c40d-103">Stap 5: Groepen gebruiken voor beheer</span><span class="sxs-lookup"><span data-stu-id="7c40d-103">Step 5: Use groups for management</span></span>

![Fase 2-Identiteit](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="7c40d-105">Bied gebruikers de mogelijkheid om hun eigen groepen te maken en beheren</span><span class="sxs-lookup"><span data-stu-id="7c40d-105">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="7c40d-106">*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="7c40d-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="7c40d-107">In deze sectie vindt u de Azure AD-groepen (Azure Active Directory) die kunnen worden beheerd door groepseigenaren in plaats van IT-beheerders.</span><span class="sxs-lookup"><span data-stu-id="7c40d-107">In this section, you'll identify Azure Active Directory (Azure AD) groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="7c40d-108">Met deze functie, die *selfservice-groepsbeheer* wordt genoemd, kunnen groepseigenaren waaraan geen beheerdersrol is toegewezen, beveiligingsgroepen maken en beheren.</span><span class="sxs-lookup"><span data-stu-id="7c40d-108">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="7c40d-109">Gebruikers kunnen lidmaatschap van een beveiligingsgroep aanvragen en dit verzoek wordt vervolgens naar de eigenaar van de groep gestuurd, in plaats van een IT-beheerder.</span><span class="sxs-lookup"><span data-stu-id="7c40d-109">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator.</span></span> <span data-ttu-id="7c40d-110">Dit maakt het mogelijk om het groepslidmaatschap te laten beheren door team-, project- of bedrijfseigenaren die het zakelijke doel van de groep begrijpen en het lidmaatschap ervan kunnen beheren.</span><span class="sxs-lookup"><span data-stu-id="7c40d-110">This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="7c40d-111">Selfservice-groepsbeheer is alleen beschikbaar voor Azure AD-beveiligingsgroepen en Office 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="7c40d-111">Self-service group management is available only for Azure AD security and Office 365 groups.</span></span> <span data-ttu-id="7c40d-112">Het is niet beschikbaar voor groepen die met e-mail worden beheerd, distributielijsten of een groep die is gesynchroniseerd vanuit uw Active Directory Domain Services (AD DS) op locatie.</span><span class="sxs-lookup"><span data-stu-id="7c40d-112">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Active Directory Domain Services (AD DS).</span></span>
>

<span data-ttu-id="7c40d-113">Zie de [instructies voor het configureren van een Azure AD-groep voor selfservice-beheer](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7c40d-113">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="7c40d-114">Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-self-service-groups) voor deze sectie bekijken.</span><span class="sxs-lookup"><span data-stu-id="7c40d-114">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this section.</span></span>

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="7c40d-115">Dynamisch groepslidmaatschap instellen</span><span class="sxs-lookup"><span data-stu-id="7c40d-115">Set up dynamic group membership</span></span>

<span data-ttu-id="7c40d-116">*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="7c40d-116">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="7c40d-117">In deze sectie maakt u een reeks regels om gebruikersaccounts automatisch toe te voegen of te verwijderen als leden van een Azure AD-groep.</span><span class="sxs-lookup"><span data-stu-id="7c40d-117">In this section, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="7c40d-118">Dit wordt *dynamisch groepslidmaatschap* genoemd.</span><span class="sxs-lookup"><span data-stu-id="7c40d-118">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="7c40d-119">De regels zijn gebaseerd op kenmerken van gebruikersaccounts, zoals Afdeling of Land.</span><span class="sxs-lookup"><span data-stu-id="7c40d-119">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="7c40d-120">De regels worden als volgt toegepast:</span><span class="sxs-lookup"><span data-stu-id="7c40d-120">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="7c40d-121">Als een nieuw gebruikersaccount aan alle regels voor de groep voldoet, wordt het lid.</span><span class="sxs-lookup"><span data-stu-id="7c40d-121">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="7c40d-122">Als een gebruikersaccount geen lid is van de groep, maar de bijbehorende kenmerken zodanig worden gewijzigd dat deze voldoen aan alle regels voor de groep, wordt het account lid van die groep.</span><span class="sxs-lookup"><span data-stu-id="7c40d-122">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="7c40d-123">Als een gebruikersaccount niet voldoet aan alle regels voor de groep, wordt het niet toegevoegd aan de groep.</span><span class="sxs-lookup"><span data-stu-id="7c40d-123">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="7c40d-124">Als een gebruikersaccount lid is van de groep, maar de bijbehorende kenmerken zodanig worden gewijzigd dat het niet meer voldoet aan alle regels voor de groep, wordt het account als lid van de groep verwijderd.</span><span class="sxs-lookup"><span data-stu-id="7c40d-124">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="7c40d-125">Als u dynamisch lidmaatschap wilt gebruiken, moet u eerst bepalen welke sets groepen een gemeenschappelijke set gebruikersaccountkenmerken hebben.</span><span class="sxs-lookup"><span data-stu-id="7c40d-125">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes.</span></span> <span data-ttu-id="7c40d-126">Zo moeten bijvoorbeeld alle leden van de afdeling Verkoop zich bevinden in de Azure AD-groep Verkoop op basis van het gebruikersaccountkenmerk Afdeling met de waarde Verkoop.</span><span class="sxs-lookup"><span data-stu-id="7c40d-126">For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="7c40d-127">Zie de [instructies voor het maken en configureren van de regels voor een dynamische Azure AD-groep](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="7c40d-127">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="7c40d-128">De resultaten van deze sectie zijn:</span><span class="sxs-lookup"><span data-stu-id="7c40d-128">The results of this section are:</span></span>

- <span data-ttu-id="7c40d-129">Een set Azure AD-groepen die kan worden geconfigureerd voor dynamisch lidmaatschap</span><span class="sxs-lookup"><span data-stu-id="7c40d-129">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="7c40d-130">Een set regels voor elke dynamische groep</span><span class="sxs-lookup"><span data-stu-id="7c40d-130">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="7c40d-132">Testlabrichtlijn: licenties en groepslidmaatschap automatiseren</span><span class="sxs-lookup"><span data-stu-id="7c40d-132">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="7c40d-133">Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-dyn-groups) voor deze sectie bekijken.</span><span class="sxs-lookup"><span data-stu-id="7c40d-133">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this section.</span></span>

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a><span data-ttu-id="7c40d-134">Automatische licentie instellen</span><span class="sxs-lookup"><span data-stu-id="7c40d-134">Set up automatic licensing</span></span>

<span data-ttu-id="7c40d-135">*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="7c40d-135">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="7c40d-136">In deze stap worden beveiligingsgroepen in Azure AD geconfigureerd om automatisch licenties van een verzameling abonnementen toe te wijzen aan alle leden van de groep.</span><span class="sxs-lookup"><span data-stu-id="7c40d-136">In this section, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="7c40d-137">Dit wordt *licenties op groepsbasis* genoemd.</span><span class="sxs-lookup"><span data-stu-id="7c40d-137">This is known as *group-based licensing*.</span></span> <span data-ttu-id="7c40d-138">Als een gebruikersaccount wordt toegevoegd aan of verwijderd uit de groep, worden de licenties voor de groepsabonnementen automatisch toegewezen aan of verwijderd van het gebruikersaccount. </span><span class="sxs-lookup"><span data-stu-id="7c40d-138">If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="7c40d-139">Voor Microsoft 365 Enterprise worden Azure AD-beveiligingsgroepen geconfigureerd om de juiste Microsoft 365 Enterprise-licentie toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="7c40d-139">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="7c40d-140">Zorg ervoor dat u genoeg licenties hebt voor alle groepsleden.</span><span class="sxs-lookup"><span data-stu-id="7c40d-140">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="7c40d-141">Als u niet genoeg licenties hebt, krijgen nieuwe gebruikers geen licenties totdat er weer licenties beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="7c40d-141">If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="7c40d-142">Voor groepen die Azure B2B-accounts (business-to-business) bevatten, dient u *licenties op groepsbasis* niet te configureren.</span><span class="sxs-lookup"><span data-stu-id="7c40d-142">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="7c40d-143">Zie [Beginselen van licenties op groepsbasis in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7c40d-143">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="7c40d-144">Zie de [stappen om licenties op groepsbasis te configureren voor een Azure-beveiligingsgroep](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="7c40d-144">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="7c40d-145">De resultaten van deze sectie zijn:</span><span class="sxs-lookup"><span data-stu-id="7c40d-145">The results of this section are:</span></span>

- <span data-ttu-id="7c40d-146">U hebt vastgesteld welke beveiligingsgroepen geschikt zijn voor licenties op groepsbasis.</span><span class="sxs-lookup"><span data-stu-id="7c40d-146">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="7c40d-147">U hebt deze groepen geconfigureerd voor licenties op groepsbasis.</span><span class="sxs-lookup"><span data-stu-id="7c40d-147">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="7c40d-149">Testlabrichtlijn: licenties en groepslidmaatschap automatiseren</span><span class="sxs-lookup"><span data-stu-id="7c40d-149">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="7c40d-150">Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-group-license) voor deze sectie bekijken.</span><span class="sxs-lookup"><span data-stu-id="7c40d-150">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this section.</span></span>

|||
|:-------|:-----|
|![Stap 6](../media/stepnumbers/Step6.png)| [<span data-ttu-id="7c40d-152">Identiteitsbeheer configureren</span><span class="sxs-lookup"><span data-stu-id="7c40d-152">Configure identity governance</span></span>](identity-configure-identity-governance.md) |
