---
title: Microsoft Viva Learning (preview) instellen in het Teams beheercentrum
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
ms.openlocfilehash: 99e63210e8f8c10e3721c35fb69df7880c7e1929
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290217"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>Microsoft Viva Learning (preview) instellen in het Teams beheercentrum

> [!NOTE]
> De informatie in dit artikel heeft betrekking op een voorbeeldproduct dat aanzienlijk kan worden gewijzigd voordat het commercieel wordt uitgebracht. 

De Teams beheerder moet bepaalde stappen uitvoeren om Viva Learning (Preview) in te stellen voor hun gebruikers in de tenant. Deze stappen variëren op basis van de manier waarop de tenant is ingeschakeld: [*Openbare*](set-up-teams-admin-center.md#public-preview-tenants) preview of [ *Private Preview* (of Beta).](set-up-teams-admin-center.md#private-preview-tenants)

## <a name="public-preview-tenants"></a>Openbare preview-tenants

### <a name="administrator-steps-for-public-preview-tenants"></a>Beheerdersstappen voor openbare preview-tenants

Omdat de Viva Learning (Preview) nog niet algemeen beschikbaar is, zijn bepaalde stappen vereist om de functies in te stellen en machtigingen in te stellen voor specifieke gebruikers of groepen. 

1. Openbare preview-functies inschakelen voor Gebruikers Learning (Preview).

    a. Wijzig Teams updatebeleid om openbare preview-functies in te stellen. Zie [Microsoft Teams Openbare preview.](/microsoftteams/public-preview-doc-updates)

    b. Schakel het updatebeleid in voor gebruikers of groepen die Viva Learning (Preview) testen. Zie [Beleid toewijzen aan gebruikers en groepen.](/microsoftteams/assign-policies-users-and-groups)

2. Wijzig het app-machtigingsbeleid voor Gebruikers van Viva Learning (Preview).

    a. Tenzij het momenteel deel uitmaakt van het globale beleid, kunt u alle Microsoft-apps toestaan in het app-machtigingsbeleid. Zie [App-machtigingsbeleid beheren in Microsoft Teams.](/microsoftteams/teams-app-permission-policies) 

    b. Schakel het app-machtigingsbeleid in voor gebruikers of groepen die Viva Learning (Preview) testen. Zie [Beleid toewijzen aan gebruikers en groepen.](/microsoftteams/assign-policies-users-and-groups)

3. Informeer gebruikers die Viva Learning (Preview) testen om hun [buildclient](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants)over te schakelen naar Openbare preview voor Teams.

> [!IMPORTANT]
> Voor openbare preview-tenants wordt Viva Learning (Preview) pas weergegeven in beheerde **apps** in het Teams-beheercentrum tot de definitieve productversie. Gebruikers van openbare preview-weergave kunnen echter Viva Learning (Preview) vinden in de Teams-app store en deze gebruiken wanneer het juiste beleid en de juiste machtigingen zijn ingesteld.

### <a name="user-steps-for-public-preview-tenants"></a>Gebruikersstappen voor openbare preview-tenants

Gebruikers die zijn ingeschakeld voor het testen van openbare preview- door het eerder beschreven beleid in te [schakelen,](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) moeten overschakelen naar Openbare preview [in](/microsoftteams/public-preview-doc-updates#enable-public-preview) hun Teams client.

1. Gebruikers moeten hun profielafbeelding selecteren > **Over**  >  **openbare preview.**

    ![Bovenste navigatie in de Teams met het profiel van de gebruiker](../media/learning/learning-app-select-profile-teams.png)

2. Gebruikers moeten de algemene voorwaarden voor openbare preview-weergave accepteren.

    ![Overschakelen naar openbare preview-build](../media/learning/learning-app-switch-to-public-preview.png)

3. Gebruikers kunnen Nu Viva Learning (Preview) vinden in de Teams app Store en deze gaan gebruiken.

## <a name="private-preview-tenants"></a>Private Preview-tenants

### <a name="administrator-steps-for-private-preview-or-beta-tenants"></a>Beheerdersstappen voor tenants voor privévoorbeelden (of bètaversies)

Voor private preview-tenants zijn er geen aanvullende beleidsregels die moeten worden ingeschakeld. Viva Learning (Preview) moet echter beschikbaar zijn voor gebruikers in uw organisatie.

1. Ga in de linkernavigatie van het Teams beheercentrum naar Teams **Apps**  >  **beheren.**

   ![Navigatie links in het Teams beheercentrum met Teams apps en de sectie Apps beheren.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. Typ op **de pagina Apps** beheren in het zoekvak Viva *Learning* en selecteer vervolgens Viva **Learning (Voorbeeld).**

   ![De pagina Apps beheren in het Teams beheercentrum met het zoekvak.](../media/learning/learning-app-teams-manage-apps-page.png)

3. Selecteer op **de pagina Viva Learning (Preview)**  onder **Status** de optie Toegestaan om Viva Learning in te Learning (Voorbeeld).

   ![Learning pagina in het Teams-beheercentrum met de sectie Status- en App-instellingen.](../media/learning/learning-app-teams-learning-page.png)

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

## <a name="next-step"></a>Volgende stap

[Leerinhoudsbronnen configureren voor Viva Learning (Preview) in de Microsoft 365-beheercentrum](content-sources-365-admin-center.md)
