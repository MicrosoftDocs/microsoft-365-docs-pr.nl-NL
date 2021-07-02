---
title: Interoperabiliteit OneDrive Learning hulpprogramma's gebruiken
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Maak opdrachten en cijfertoewijzingen, bouw en beheer cursusinhoud en werk in realtime samen aan bestanden met de nieuwe OneDrive Learning Tools Interoperability App.
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256952"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="9ec06-103">LTI Microsoft OneDrive canvas gebruiken</span><span class="sxs-lookup"><span data-stu-id="9ec06-103">Use Microsoft OneDrive LTI with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ec06-104">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="9ec06-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="9ec06-105">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="9ec06-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="integrate-with-canvas"></a><span data-ttu-id="9ec06-106">Integreren met Canvas</span><span class="sxs-lookup"><span data-stu-id="9ec06-106">Integrate with Canvas</span></span>

<span data-ttu-id="9ec06-107">De persoon die deze integratie uitvoert, moet een beheerder van Canvas zijn en een beheerder van de Microsoft 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="9ec06-107">The person who performs this integration should be an admin of Canvas and an admin of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="9ec06-108">Meld u aan bij de Microsoft Azure portal met het tenantbeheerderaccount.</span><span class="sxs-lookup"><span data-stu-id="9ec06-108">Sign in to the Microsoft Azure portal with the tenant admin account.</span></span> <span data-ttu-id="9ec06-109">De Azure-tenantbeheerder moet ook de rol groepsbeheerder hebben.</span><span class="sxs-lookup"><span data-stu-id="9ec06-109">The Azure tenant administrator should also have the Group administrator role.</span></span>

    ![groepsbeheerder gemarkeerd](../media/lti-media/lti-group-admin.png)

2. <span data-ttu-id="9ec06-111">Meld u aan bij de Microsoft [OneDrive LTI-portal](https://odltiappnl.azurewebsites.net/admin).</span><span class="sxs-lookup"><span data-stu-id="9ec06-111">Sign in to the Microsoft [OneDrive LTI portal](https://odltiappnl.azurewebsites.net/admin).</span></span>

3. <span data-ttu-id="9ec06-112">Accepteer de machtigingen om de aanmelding te voltooien.</span><span class="sxs-lookup"><span data-stu-id="9ec06-112">Accept the permissions to complete the sign-in.</span></span>

    ![machtigingen accepteren](../media/lti-media/lti-permissions.png)

4. <span data-ttu-id="9ec06-114">Selecteer **LTI-tenant toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="9ec06-114">Select **Add LTI Tenant**.</span></span>

     ![LTI-tenant toevoegen](../media/lti-media/lti-add-tenant.png)

5. <span data-ttu-id="9ec06-116">Selecteer **LTI Consumer Platform** als **Canvas** in de vervolgkeuzekeuze.</span><span class="sxs-lookup"><span data-stu-id="9ec06-116">Select **LTI Consumer Platform** as **Canvas** from the dropdown.</span></span>

6. <span data-ttu-id="9ec06-117">Selecteer **Canvas Base URL** en selecteer vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="9ec06-117">Select **Canvas Base URL** and then select **Next**.</span></span>

    ![canvas selecteren en basis-URL toevoegen](../media/lti-media/lti-canvas-base-url.png)

   <span data-ttu-id="9ec06-119">In het volgende scherm ziet u velden die vertrouwelijk voor u zijn.</span><span class="sxs-lookup"><span data-stu-id="9ec06-119">The next screen shows fields that are confidential to you.</span></span>

7. <span data-ttu-id="9ec06-120">Selecteer **Volgende** van ??</span><span class="sxs-lookup"><span data-stu-id="9ec06-120">Select **Next** from ??</span></span> <span data-ttu-id="9ec06-121">(U bent bijna klaar).</span><span class="sxs-lookup"><span data-stu-id="9ec06-121">page.</span></span> <span data-ttu-id="9ec06-122">KUNNEN REVISOREN DE LEGE HIER INVULLEN?</span><span class="sxs-lookup"><span data-stu-id="9ec06-122">CAN REVIEWERS FILL IN THE BLANK HERE?</span></span>

8. <span data-ttu-id="9ec06-123">Selecteer **Volgende** in het scherm met informatie die vertrouwelijk voor u is.</span><span class="sxs-lookup"><span data-stu-id="9ec06-123">Select **Next** in the screen that shows information that's confidential to you.</span></span>

   <span data-ttu-id="9ec06-124">In het laatste scherm van de Azure-portal ziet u de volgende stappen voor het toevoegen van uw Canvas-exemplaar.</span><span class="sxs-lookup"><span data-stu-id="9ec06-124">The final screen of the Azure portal shows the next steps for adding your Canvas instance.</span></span>

9. <span data-ttu-id="9ec06-125">Kopieer de ontwikkelaarssleutels vanuit dit scherm.</span><span class="sxs-lookup"><span data-stu-id="9ec06-125">Copy the Developer Keys from this screen.</span></span> <span data-ttu-id="9ec06-126">U wordt gebruikt wanneer u het canvas-exemplaar maakt.</span><span class="sxs-lookup"><span data-stu-id="9ec06-126">You'll use when you create the Canvas instance.</span></span>

## <a name="add-the-canvas-instance"></a><span data-ttu-id="9ec06-127">Het canvas-exemplaar toevoegen</span><span class="sxs-lookup"><span data-stu-id="9ec06-127">Add the Canvas instance</span></span>

1. <span data-ttu-id="9ec06-128">Schakel in het canvas-exemplaar **deselecteer**  >  **beheerdersontwikkelaarssleutels uit.**</span><span class="sxs-lookup"><span data-stu-id="9ec06-128">In your Canvas instance, deselect **Admin** > **Developer Keys**.</span></span>

2. <span data-ttu-id="9ec06-129">Kies **LTI-toets** in de vervolgkeuzekeuze op **Ontwikkelaarssleutel.**</span><span class="sxs-lookup"><span data-stu-id="9ec06-129">Choose **LTI Key** in the dropdown on **Developer Key**.</span></span>

   ![De LTI-ontwikkelaarssleutels ophalen](../media/lti-media/lti-developer-keys.png)

3. <span data-ttu-id="9ec06-131">Plak de ontwikkelaarssleutels hier.</span><span class="sxs-lookup"><span data-stu-id="9ec06-131">Paste the developer keys here.</span></span>

     ![De ontwikkelaarssleutels plakken](../media/lti-media/lti-developer-keys.png)

   <span data-ttu-id="9ec06-133">De sleutel wordt gemaakt in **de UIT-modus**</span><span class="sxs-lookup"><span data-stu-id="9ec06-133">The key gets created in **OFF** mode</span></span>

   ![De gemaakte ontwikkelaarssleutels in de uit-modus](../media/lti-media/lti-copy-developer-keys.png)

4. <span data-ttu-id="9ec06-135">Kopieer de gemarkeerde tekst.</span><span class="sxs-lookup"><span data-stu-id="9ec06-135">Copy the highlighted text.</span></span>
    <span data-ttu-id="9ec06-136">Dit fungeert als client-id in Microsoft OneDrive LTI-portal.</span><span class="sxs-lookup"><span data-stu-id="9ec06-136">This serves as Client ID in Microsoft OneDrive LTI portal.</span></span>

5. <span data-ttu-id="9ec06-137">Plak de tekst in het **veld Client-id** in Microsoft OneDrive LTI-portal en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="9ec06-137">Paste the text into the **Client ID** field in Microsoft OneDrive LTI portal, and then select **Next**.</span></span>

6. <span data-ttu-id="9ec06-138">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9ec06-138">Select **Save**.</span></span>

7. <span data-ttu-id="9ec06-139">Bekijk de instellingen door **LTI-tenants weergeven te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="9ec06-139">View the settings by selecting **View LTI Tenants**.</span></span>
