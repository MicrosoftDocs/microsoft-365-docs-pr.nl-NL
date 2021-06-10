---
title: Microsoft Viva Learning (Preview) instellen in het Teams beheercentrum
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: ''
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Meer informatie over het configureren van Microsoft Viva Learning (Preview) in het Teams beheercentrum.
ms.openlocfilehash: 860f16bee7d93f2212072c5d738263402704272f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789229"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="24ac9-103">Microsoft Viva Learning (Preview) instellen in het Teams beheercentrum</span><span class="sxs-lookup"><span data-stu-id="24ac9-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="24ac9-104">De informatie in dit artikel heeft betrekking op een voorbeeldproduct dat aanzienlijk kan worden gewijzigd voordat het commercieel wordt uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="24ac9-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="24ac9-105">De Teams beheerder moet bepaalde stappen uitvoeren om Viva Learning (Preview) in te stellen voor hun gebruikers in de tenant.</span><span class="sxs-lookup"><span data-stu-id="24ac9-105">The Teams administrator needs to perform certain steps to enable Viva Learning (Preview) for their users in the tenant.</span></span> <span data-ttu-id="24ac9-106">Deze stappen variëren op basis van de manier waarop de tenant is ingeschakeld: [*Openbare*](set-up-teams-admin-center.md#public-preview-tenants) preview of [ *Private Preview* (of Beta).](set-up-teams-admin-center.md#private-preview-tenants)</span><span class="sxs-lookup"><span data-stu-id="24ac9-106">These steps vary based on how the tenant is enabled:  [*Public Preview*](set-up-teams-admin-center.md#public-preview-tenants) or [*Private Preview* (or Beta)](set-up-teams-admin-center.md#private-preview-tenants).</span></span>

## <a name="public-preview-tenants"></a><span data-ttu-id="24ac9-107">Openbare preview-tenants</span><span class="sxs-lookup"><span data-stu-id="24ac9-107">Public Preview tenants</span></span>

### <a name="administrator-steps-for-public-preview-tenants"></a><span data-ttu-id="24ac9-108">Beheerdersstappen voor openbare preview-tenants</span><span class="sxs-lookup"><span data-stu-id="24ac9-108">Administrator steps for Public Preview tenants</span></span>

<span data-ttu-id="24ac9-109">Omdat Viva Learning (Preview) nog niet algemeen beschikbaar is, zijn bepaalde stappen vereist om de functies in te stellen en machtigingen in te stellen voor specifieke gebruikers of groepen.</span><span class="sxs-lookup"><span data-stu-id="24ac9-109">Because the Viva Learning (Preview) is not yet generally available, certain steps are required to enable the features and set permissions for specific users or groups.</span></span> 

1. <span data-ttu-id="24ac9-110">Openbare preview-functies inschakelen voor Gebruikers van Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="24ac9-110">Enable Public Preview features for Viva Learning (Preview) users.</span></span>

    <span data-ttu-id="24ac9-111">a.</span><span class="sxs-lookup"><span data-stu-id="24ac9-111">a.</span></span> <span data-ttu-id="24ac9-112">Wijzig Teams updatebeleid om openbare preview-functies in te stellen.</span><span class="sxs-lookup"><span data-stu-id="24ac9-112">Modify Teams update policy to enable Public Preview features.</span></span> <span data-ttu-id="24ac9-113">Zie [Microsoft Teams Openbare preview.](/microsoftteams/public-preview-doc-updates)</span><span class="sxs-lookup"><span data-stu-id="24ac9-113">See [Microsoft Teams Public Preview](/microsoftteams/public-preview-doc-updates).</span></span>

    <span data-ttu-id="24ac9-114">b.</span><span class="sxs-lookup"><span data-stu-id="24ac9-114">b.</span></span> <span data-ttu-id="24ac9-115">Schakel het updatebeleid in voor gebruikers of groepen die Viva Learning (Preview) testen.</span><span class="sxs-lookup"><span data-stu-id="24ac9-115">Enable the update policy for users or groups who will perform Viva Learning (Preview) testing.</span></span> <span data-ttu-id="24ac9-116">Zie [Beleid toewijzen aan gebruikers en groepen.](/microsoftteams/assign-policies-users-and-groups)</span><span class="sxs-lookup"><span data-stu-id="24ac9-116">See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).</span></span>

2. <span data-ttu-id="24ac9-117">Wijzig het app-machtigingsbeleid voor Gebruikers van Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="24ac9-117">Modify the app permission policy for Viva Learning (Preview) users.</span></span>

    <span data-ttu-id="24ac9-118">a.</span><span class="sxs-lookup"><span data-stu-id="24ac9-118">a.</span></span> <span data-ttu-id="24ac9-119">Tenzij het momenteel deel uitmaakt van het globale beleid, kunt u alle Microsoft-apps toestaan in het app-machtigingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="24ac9-119">Unless it's currently part of the global policy, allow all Microsoft apps in the app permission policy.</span></span> <span data-ttu-id="24ac9-120">Zie [App-machtigingsbeleid beheren in Microsoft Teams.](/microsoftteams/teams-app-permission-policies)</span><span class="sxs-lookup"><span data-stu-id="24ac9-120">See [Manage app permission policies in Microsoft Teams](/microsoftteams/teams-app-permission-policies).</span></span> 

    <span data-ttu-id="24ac9-121">b.</span><span class="sxs-lookup"><span data-stu-id="24ac9-121">b.</span></span> <span data-ttu-id="24ac9-122">Schakel het app-machtigingsbeleid in voor gebruikers of groepen die Viva Learning (Preview) testen.</span><span class="sxs-lookup"><span data-stu-id="24ac9-122">Enable the app permission policy for users or groups who will perform Viva Learning (Preview) testing.</span></span> <span data-ttu-id="24ac9-123">Zie [Beleid toewijzen aan gebruikers en groepen.](/microsoftteams/assign-policies-users-and-groups)</span><span class="sxs-lookup"><span data-stu-id="24ac9-123">See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).</span></span>

3.  <span data-ttu-id="24ac9-124">Informeer gebruikers die Viva Learning (Preview) testen om hun [buildclient](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants)over te schakelen naar Openbare preview voor Teams.</span><span class="sxs-lookup"><span data-stu-id="24ac9-124">Notify users who will test Viva Learning (Preview) to [switch their build client to Public Preview for Teams](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="24ac9-125">Voor openbare preview-tenants wordt Viva Learning (Preview) niet weergegeven in beheerde **apps** in het Teams-beheercentrum tot de definitieve productversie.</span><span class="sxs-lookup"><span data-stu-id="24ac9-125">For Public Preview tenants, Viva Learning (Preview) will not be displayed in **Managed apps** in the Teams admin center until final product release.</span></span> <span data-ttu-id="24ac9-126">Gebruikers van openbare preview-weergave kunnen echter Viva Learning (Preview) vinden in de Teams app Store en gebruiken, zodra het juiste beleid en de juiste machtigingen zijn ingesteld.</span><span class="sxs-lookup"><span data-stu-id="24ac9-126">However, enabled Public Preview users can find Viva Learning (Preview) in the Teams app store and use it, once the correct policies and permissions have been set up.</span></span>

### <a name="user-steps-for-public-preview-tenants"></a><span data-ttu-id="24ac9-127">Gebruikersstappen voor openbare preview-tenants</span><span class="sxs-lookup"><span data-stu-id="24ac9-127">User steps for Public Preview tenants</span></span>

<span data-ttu-id="24ac9-128">Gebruikers die zijn ingeschakeld voor het testen van openbare preview- door het eerder beschreven beleid in te [schakelen,](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) moeten overschakelen naar Openbare preview [in](/microsoftteams/public-preview-doc-updates#enable-public-preview) hun Teams client.</span><span class="sxs-lookup"><span data-stu-id="24ac9-128">Users who have been enabled for Public Preview testing — by enabling the [policies previously described](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) — need to [switch to Public Preview](/microsoftteams/public-preview-doc-updates#enable-public-preview) in their Teams client.</span></span>

1. <span data-ttu-id="24ac9-129">Gebruikers moeten hun profielafbeelding selecteren > **Over**  >  **openbare preview.**</span><span class="sxs-lookup"><span data-stu-id="24ac9-129">Users must select their profile image > **About** > **Public Preview**.</span></span>
   
    ![Bovenste navigatie in de Teams met het profiel van de gebruiker](../media/learning/learning-app-select-profile-teams.png)
    
2. <span data-ttu-id="24ac9-131">Gebruikers moeten de algemene voorwaarden voor openbare preview-weergave accepteren.</span><span class="sxs-lookup"><span data-stu-id="24ac9-131">Users must accept the Public Preview terms and conditions.</span></span>

    ![Overschakelen naar openbare preview-build](../media/learning/learning-app-switch-to-public-preview.png)
 
3. <span data-ttu-id="24ac9-133">Gebruikers kunnen Nu Viva Learning (Preview) vinden in de Teams app Store en deze gaan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="24ac9-133">Users can now find Viva Learning (Preview) in the Teams app store and start using it.</span></span>

## <a name="private-preview-tenants"></a><span data-ttu-id="24ac9-134">Private Preview-tenants</span><span class="sxs-lookup"><span data-stu-id="24ac9-134">Private Preview tenants</span></span>

### <a name="administrator-steps-for-private-preview-or-beta-tenants"></a><span data-ttu-id="24ac9-135">Beheerdersstappen voor tenants voor privévoorbeelden (of bètaversies)</span><span class="sxs-lookup"><span data-stu-id="24ac9-135">Administrator steps for Private Preview (or Beta) tenants</span></span>

<span data-ttu-id="24ac9-136">Voor private preview-tenants zijn er geen aanvullende beleidsregels die moeten worden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="24ac9-136">For Private Preview tenants, there are no additional policies that need to be enabled.</span></span> <span data-ttu-id="24ac9-137">Viva Learning (Preview) moet echter beschikbaar zijn voor gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="24ac9-137">However, Viva Learning (Preview) must be made available for users in your organization.</span></span>

1. <span data-ttu-id="24ac9-138">Ga in de linkernavigatie van het Teams beheercentrum naar Teams **Apps**  >  **beheren.**</span><span class="sxs-lookup"><span data-stu-id="24ac9-138">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Navigatie links in het Teams beheercentrum met Teams apps en de sectie Apps beheren.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="24ac9-140">Typ op **de pagina Apps** beheren in het zoekvak Viva *Learning* en selecteer vervolgens Viva **Learning (Preview).**</span><span class="sxs-lookup"><span data-stu-id="24ac9-140">On the **Manage apps** page, in the search box, type *Viva Learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![De pagina Apps beheren in het Teams beheercentrum met het zoekvak.](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="24ac9-142">Selecteer op **de pagina Viva Learning (Preview)** onder **Status** de optie Toegestaan **om** Viva Learning (Preview) in te zetten.</span><span class="sxs-lookup"><span data-stu-id="24ac9-142">On the **Viva Learning (Preview)** page, under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

   ![Leerpagina in het Teams beheercentrum met de sectie Status- en App-instellingen.](../media/learning/learning-app-teams-learning-page.png)


<!---
The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.

1. For Viva Learning (Preview), you must first set the Update policy in Teams. For more information, see [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).

    1. Sign in to the Teams admin center.

    2. Select **Teams** > **Update policies**.

    3. Select **Add**. 

    4. Name the update policy, add a policy, and turn on **Show preview features**.

2. The admin must notify users of the policy update so that they move their build into the Public Preview for Teams. 

    1. Users must select their profile image > **About** > **Public Preview**.
   
        ![Upper navigation in the Teams application showing user's profile](../media/learning/learning-app-select-profile-teams.png)
    
    2. Users must accept the **Public preview** terms and conditions.

        ![Switch to public preview build](../media/learning/learning-app-switch-to-public-preview.png)
 
3. For organizations that have restrictive policies and need to enable Viva Learning (Preview), follow the process in the next section.

## Manage settings for Viva Learning (Preview)

You must be an administrator in the Teams admin center to perform these tasks.

To make Viva Learning (Preview) available for users in your organization, follow these steps:

1. In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.

   ![Left navigation in the Teams admin center showing Teams apps and Manage apps section.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.

   ![Manage apps page in the Teams admin center showing the search box.](../media/learning/learning-app-teams-manage-apps-page.png)

3. On the **Viva Learning (Preview)** page:

   1. Under **Status**, select **Allowed** to turn on Viva Learning (Preview).

   2. On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).

   ![Learning page in the Teams admin center showing Status and App settings section.](../media/learning/learning-app-teams-learning-page.png)

4. After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.

> [!NOTE]
>  If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview). <br><br>As part of the preview, Viva Learning (Preview) is released in Ring 3.0. If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page. To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users. <br><br>   ![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)

--->

## <a name="next-step"></a><span data-ttu-id="24ac9-144">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="24ac9-144">Next step</span></span>

[<span data-ttu-id="24ac9-145">Bronnen voor leerinhoud configureren voor Viva Learning (preview) in het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="24ac9-145">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)
