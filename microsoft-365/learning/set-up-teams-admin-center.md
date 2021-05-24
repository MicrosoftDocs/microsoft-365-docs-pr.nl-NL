---
title: Microsoft Viva Learning (Preview) instellen in het Teams beheercentrum
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/24/2021
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
ms.openlocfilehash: a96a2f3ecf7d4e1ee0c136ae155868218f08aaf4
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636132"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="99392-103">Microsoft Viva Learning (Preview) instellen in het Teams beheercentrum</span><span class="sxs-lookup"><span data-stu-id="99392-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="99392-104">De informatie in dit artikel heeft betrekking op een voorbeeldproduct dat aanzienlijk kan worden gewijzigd voordat het commercieel wordt uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="99392-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="99392-105">De Teams beheerder installeert Viva Learning (Preview) en past machtigingsbeleid toe via het Teams beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="99392-105">The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.</span></span>

1. <span data-ttu-id="99392-106">Voor Viva Learning (Preview) moet u eerst het updatebeleid instellen in Teams.</span><span class="sxs-lookup"><span data-stu-id="99392-106">For Viva Learning (Preview), you must first set the Update policy in Teams.</span></span> <span data-ttu-id="99392-107">Zie openbare Microsoft Teams [voor meer informatie.](/MicrosoftTeams/public-preview-doc-updates)</span><span class="sxs-lookup"><span data-stu-id="99392-107">For more information, see [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).</span></span>

    1. <span data-ttu-id="99392-108">Meld u aan bij het Teams beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="99392-108">Sign in to the Teams admin center.</span></span>

    2. <span data-ttu-id="99392-109">Selecteer **Teams**  >  **Beleid bijwerken**.</span><span class="sxs-lookup"><span data-stu-id="99392-109">Select **Teams** > **Update policies**.</span></span>

    3. <span data-ttu-id="99392-110">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="99392-110">Select **Add**.</span></span> 

    4. <span data-ttu-id="99392-111">Geef het updatebeleid een naam, voeg een beleid toe en schakel **Voorbeeldfuncties weergeven in.**</span><span class="sxs-lookup"><span data-stu-id="99392-111">Name the update policy, add a policy, and turn on **Show preview features**.</span></span>

2. <span data-ttu-id="99392-112">De beheerder moet gebruikers op de hoogte stellen van de beleidsupdate, zodat ze hun build kunnen verplaatsen naar het openbare voorbeeld voor Teams.</span><span class="sxs-lookup"><span data-stu-id="99392-112">The admin must notify users of the policy update so that they move their build into the Public Preview for Teams.</span></span> 

    1. <span data-ttu-id="99392-113">Gebruikers moeten hun profielafbeelding selecteren > **Over**  >  **openbare preview.**</span><span class="sxs-lookup"><span data-stu-id="99392-113">Users must select their profile image > **About** > **Public Preview**.</span></span>
   
        ![Bovenste navigatie in de Teams met het profiel van de gebruiker](../media/learning/learning-app-select-profile-teams.png)
    
    2. <span data-ttu-id="99392-115">Gebruikers moeten de algemene voorwaarden **voor openbare preview-weergave** accepteren.</span><span class="sxs-lookup"><span data-stu-id="99392-115">Users must accept the **Public preview** terms and conditions.</span></span>

        ![Overschakelen naar openbare preview-build](../media/learning/learning-app-switch-to-public-preview.png)
 
3. <span data-ttu-id="99392-117">Voor organisaties die een beperkend beleid hebben en Viva Learning (Preview) moeten inschakelen, volgt u het proces in de volgende sectie.</span><span class="sxs-lookup"><span data-stu-id="99392-117">For organizations that have restrictive policies and need to enable Viva Learning (Preview), follow the process in the next section.</span></span>

## <a name="manage-settings-for-viva-learning-preview"></a><span data-ttu-id="99392-118">Instellingen voor Viva Learning beheren (voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="99392-118">Manage settings for Viva Learning (Preview)</span></span>

<span data-ttu-id="99392-119">U moet een beheerder zijn in het Teams beheercentrum om deze taken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="99392-119">You must be an administrator in the Teams admin center to perform these tasks.</span></span>

<span data-ttu-id="99392-120">Als u Viva Learning (Preview) beschikbaar wilt maken voor gebruikers in uw organisatie, volgt u de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="99392-120">To make Viva Learning (Preview) available for users in your organization, follow these steps:</span></span>

1. <span data-ttu-id="99392-121">Ga in de linkernavigatie van het Teams beheercentrum naar Teams **Apps**  >  **beheren.**</span><span class="sxs-lookup"><span data-stu-id="99392-121">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Navigatie links in het Teams beheercentrum met Teams apps en de sectie Apps beheren.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="99392-123">Typ op **de pagina Apps** beheren in het zoekvak Viva *learning* en selecteer vervolgens Viva **Learning (Preview).**</span><span class="sxs-lookup"><span data-stu-id="99392-123">On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![De pagina Apps beheren in het Teams beheercentrum met het zoekvak.](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="99392-125">Op de **pagina Viva Learning (Preview)** :</span><span class="sxs-lookup"><span data-stu-id="99392-125">On the **Viva Learning (Preview)** page:</span></span>

   1. <span data-ttu-id="99392-126">Selecteer **onder Status** de optie **Toegestaan** om Viva Learning (Preview) in te zetten.</span><span class="sxs-lookup"><span data-stu-id="99392-126">Under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

   2. <span data-ttu-id="99392-127">Ga op **Instellingen** tabblad Onder **App-instellingen** naar het Microsoft 365 beheercentrum om [leerinhoudsbronnen te configureren.](content-sources-365-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="99392-127">On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).</span></span>

   ![Leerpagina in het Teams beheercentrum met de sectie Status- en App-instellingen.](../media/learning/learning-app-teams-learning-page.png)

4. <span data-ttu-id="99392-129">Nadat **u app-instellingen** beheren  hebt ingesteld, gaat u naar Machtigingsbeleid en Installatiebeleid om toestemming te verlenen aan werknemers die toegang moeten hebben tot Viva Learning (Preview) als onderdeel van de deelname van uw organisatie aan het voorbeeld. </span><span class="sxs-lookup"><span data-stu-id="99392-129">After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="99392-130">Als uw organisatie ring 4.0 heeft als onderdeel van Teams TAP100-programma, moet u mogelijk goedgekeurde gebruikers in Ring 3.0 inschakelen voor toegang tot Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="99392-130">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview).</span></span> <br><br><span data-ttu-id="99392-131">Als onderdeel van het voorbeeld wordt Viva Learning (Preview) uitgebracht in Ring 3.0.</span><span class="sxs-lookup"><span data-stu-id="99392-131">As part of the preview, Viva Learning (Preview) is released in Ring 3.0.</span></span> <span data-ttu-id="99392-132">Als uw organisatie Ring 4.0 gebruikt, ziet u Viva Learning (Preview) niet op de **pagina Apps beheren.**</span><span class="sxs-lookup"><span data-stu-id="99392-132">If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page.</span></span> <span data-ttu-id="99392-133">Als u de app wilt testen, moet u een aangepast machtigingsbeleid voor apps maken, instellen op Alle **apps** toestaan en deze toewijzen aan goedgekeurde gebruikers van Ring 3.0.</span><span class="sxs-lookup"><span data-stu-id="99392-133">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span> <br><br>   <span data-ttu-id="99392-134">![Tap-AppsPermission-Plcy-pagina met alle geselecteerde apps toestaan.](../media/learning/learning-app-tap-appspermission-plcy.png)</span><span class="sxs-lookup"><span data-stu-id="99392-134">![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)</span></span>

## <a name="next-step"></a><span data-ttu-id="99392-135">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="99392-135">Next step</span></span>

[<span data-ttu-id="99392-136">Bronnen voor leerinhoud configureren voor Viva Learning (preview) in het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="99392-136">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)
