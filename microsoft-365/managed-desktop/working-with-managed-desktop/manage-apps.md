---
title: Apps beheren in Microsoft Managed Desktop
description: Informatie over het bijwerken van line-of-business-apps die zijn geïmplementeerd op Microsoft Managed Desktop apparaten
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: b016d8458b4b4cc9f6b684d3b8a3c0a1e1322fef
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925405"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="978f8-104">Line-Of-Business-apps beheren in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="978f8-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="978f8-105">Er zijn een aantal manieren om app-updates te beheren voor apps die u hebt ge onboarded voor Microsoft Managed Desktop en geïmplementeerd op uw Microsoft Managed Desktop apparaten.</span><span class="sxs-lookup"><span data-stu-id="978f8-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="978f8-106">U kunt app-updates maken in Microsoft Managed Desktop portal of Intune.</span><span class="sxs-lookup"><span data-stu-id="978f8-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="978f8-107">Line-of-business-apps bijwerken in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="978f8-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="978f8-108">**Uw line-of-business-apps bijwerken in Microsoft Managed Desktop portal**</span><span class="sxs-lookup"><span data-stu-id="978f8-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="978f8-109">Meld u aan [bij Microsoft Managed Desktop beheerportal.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="978f8-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="978f8-110">Selecteer **onder Inventaris** de optie **Apps.**</span><span class="sxs-lookup"><span data-stu-id="978f8-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="978f8-111">Selecteer de app die u wilt updaten en selecteer vervolgens **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="978f8-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="978f8-112">Selecteer **onder** Beheren de optie **Eigenschappen.**</span><span class="sxs-lookup"><span data-stu-id="978f8-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="978f8-113">Klik **op App-pakketbestand** en blader naar een nieuw app-pakketbestand.</span><span class="sxs-lookup"><span data-stu-id="978f8-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="978f8-114">Selecteer **App-pakketbestand**.</span><span class="sxs-lookup"><span data-stu-id="978f8-114">Select **App package file**.</span></span>
7. <span data-ttu-id="978f8-115">Selecteer het mappictogram en blader naar de locatie van het bijgewerkte app-bestand.</span><span class="sxs-lookup"><span data-stu-id="978f8-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="978f8-116">Selecteer **Openen**.</span><span class="sxs-lookup"><span data-stu-id="978f8-116">Select **Open**.</span></span> <span data-ttu-id="978f8-117">De app-informatie wordt bijgewerkt met de pakketgegevens.</span><span class="sxs-lookup"><span data-stu-id="978f8-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="978f8-118">Controleer of **de app-versie** het bijgewerkte app-pakket weerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="978f8-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="978f8-119">De bijgewerkte app wordt geïmplementeerd op de apparaten van uw gebruiker.</span><span class="sxs-lookup"><span data-stu-id="978f8-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="978f8-120">Line-of-Business-apps bijwerken in Intune</span><span class="sxs-lookup"><span data-stu-id="978f8-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="978f8-121">**Uw line-of-business-apps bijwerken in Intune**</span><span class="sxs-lookup"><span data-stu-id="978f8-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="978f8-122">Meld u aan bij [azure portal.](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="978f8-122">Sign in to [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="978f8-123">Selecteer **Alle Services**  >  **Intune**.</span><span class="sxs-lookup"><span data-stu-id="978f8-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="978f8-124">Intune staat in de sectie **Monitoring + Management.**</span><span class="sxs-lookup"><span data-stu-id="978f8-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="978f8-125">Selecteer **Client-apps > Apps.**</span><span class="sxs-lookup"><span data-stu-id="978f8-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="978f8-126">Zoek en selecteer uw app in de lijst met apps.</span><span class="sxs-lookup"><span data-stu-id="978f8-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="978f8-127">Selecteer eigenschappen **in het** blad **Overzicht.**</span><span class="sxs-lookup"><span data-stu-id="978f8-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="978f8-128">Selecteer **App-pakketbestand**.</span><span class="sxs-lookup"><span data-stu-id="978f8-128">Select **App package file**.</span></span>
7. <span data-ttu-id="978f8-129">Selecteer het mappictogram en blader naar de locatie van het bijgewerkte app-bestand.</span><span class="sxs-lookup"><span data-stu-id="978f8-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="978f8-130">Selecteer **Openen**.</span><span class="sxs-lookup"><span data-stu-id="978f8-130">Select **Open**.</span></span> <span data-ttu-id="978f8-131">De app-informatie wordt bijgewerkt met de pakketgegevens.</span><span class="sxs-lookup"><span data-stu-id="978f8-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="978f8-132">Controleer of **de app-versie** het bijgewerkte app-pakket weerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="978f8-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="978f8-133">Een app terugdraaien naar een vorige versie</span><span class="sxs-lookup"><span data-stu-id="978f8-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="978f8-134">Als er een fout is gevonden wanneer een nieuwe versie van een app wordt geïmplementeerd, kunt u terugdraaien naar een vorige versie.</span><span class="sxs-lookup"><span data-stu-id="978f8-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="978f8-135">Het proces dat hier wordt beschreven, is voor apps waarbij type wordt weergegeven **als Windows MSI line-of-business** app of **Windows-app (Win 32) - preview**</span><span class="sxs-lookup"><span data-stu-id="978f8-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="978f8-136">**Een line-of-business-app terugdraaien naar een vorige versie**</span><span class="sxs-lookup"><span data-stu-id="978f8-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="978f8-137">Meld u aan [bij Microsoft Managed Desktop beheerportal.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="978f8-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="978f8-138">Selecteer **onder Inventaris** de optie **Apps.**</span><span class="sxs-lookup"><span data-stu-id="978f8-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="978f8-139">Selecteer de app die u wilt terugdraaien en selecteer vervolgens **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="978f8-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="978f8-140">Selecteer **onder** Beheren de optie **Eigenschappen.**</span><span class="sxs-lookup"><span data-stu-id="978f8-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="978f8-141">Als **Windows app-apps voor een MSI-lijn** wilt gebruiken, selecteert u **App-informatie** en selecteert u vervolgens onder App-versie negeren **de** optie **Ja.**</span><span class="sxs-lookup"><span data-stu-id="978f8-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="978f8-142">Voor **Windows app (Win 32) -** preview-apps, selecteer **App-informatie,** selecteer **Detectieregels** en selecteer vervolgens **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="978f8-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="978f8-143">Als er een MSI-regel is, controleert u of de controle van **de MSI-productversie** is ingesteld op **Nee**.</span><span class="sxs-lookup"><span data-stu-id="978f8-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="978f8-144">[Upload een vorige versie van het app-bronbestand naar](../get-started/deploy-apps.md) Microsoft Managed Desktop beheerportal.</span><span class="sxs-lookup"><span data-stu-id="978f8-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

