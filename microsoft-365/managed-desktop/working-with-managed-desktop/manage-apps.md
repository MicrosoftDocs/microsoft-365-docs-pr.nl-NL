---
title: Apps beheren in Microsoft Managed Desktop
description: Informatie over het bijwerken van zakelijke apps die zijn geïmplementeerd op Microsoft Managed Desktop-apparaten
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1a6b91ab5b4523f4b980dab0c25af41a9d614189
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42809136"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="f11a3-104">Zakelijke line-of-business-apps beheren in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="f11a3-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="f11a3-105">Er zijn een aantal manieren om app-updates te beheren voor apps die u hebt aangesloten op Microsoft Managed Desktop en geïmplementeerd op uw Microsoft Managed Desktop-apparaten.</span><span class="sxs-lookup"><span data-stu-id="f11a3-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f11a3-106">U app-updates uitvoeren in microsoft Managed Desktop-portal of Intune.</span><span class="sxs-lookup"><span data-stu-id="f11a3-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="f11a3-107">Line-of-business-apps bijwerken in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="f11a3-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="f11a3-108">**Uw bedrijfsregel-apps bijwerken in microsoft Managed Desktop-portal**</span><span class="sxs-lookup"><span data-stu-id="f11a3-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="f11a3-109">Meld u aan bij [microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="f11a3-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="f11a3-110">Selecteer **Onder Inventaris**de optie **Apps**.</span><span class="sxs-lookup"><span data-stu-id="f11a3-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="f11a3-111">Selecteer de app die u wilt bijwerken en selecteer **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="f11a3-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="f11a3-112">Selecteer **Eigenschappen** **onder Beheren**.</span><span class="sxs-lookup"><span data-stu-id="f11a3-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="f11a3-113">Klik **op App-pakketbestand**en blader vervolgens om een nieuw app-pakketbestand te uploaden.</span><span class="sxs-lookup"><span data-stu-id="f11a3-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="f11a3-114">Selecteer **App-pakketbestand**.</span><span class="sxs-lookup"><span data-stu-id="f11a3-114">Select **App package file**.</span></span>
7. <span data-ttu-id="f11a3-115">Selecteer het mappictogram en blader naar de locatie van uw bijgewerkte app-bestand.</span><span class="sxs-lookup"><span data-stu-id="f11a3-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="f11a3-116">Selecteer **Openen**.</span><span class="sxs-lookup"><span data-stu-id="f11a3-116">Select **Open**.</span></span> <span data-ttu-id="f11a3-117">De app-informatie wordt bijgewerkt met de pakketinformatie.</span><span class="sxs-lookup"><span data-stu-id="f11a3-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="f11a3-118">Controleer of **de app-versie** het bijgewerkte app-pakket weergeeft.</span><span class="sxs-lookup"><span data-stu-id="f11a3-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="f11a3-119">De bijgewerkte app wordt geïmplementeerd op de apparaten van uw gebruiker.</span><span class="sxs-lookup"><span data-stu-id="f11a3-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="f11a3-120">Line-of-business-apps bijwerken in Intune</span><span class="sxs-lookup"><span data-stu-id="f11a3-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="f11a3-121">**Uw line-of-business-apps bijwerken in Intune**</span><span class="sxs-lookup"><span data-stu-id="f11a3-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="f11a3-122">Meld u aan bij [Azure portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="f11a3-122">Sign in to [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="f11a3-123">Selecteer **Alle Services** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="f11a3-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="f11a3-124">Intune bevindt zich in de sectie **Monitoring + Management.**</span><span class="sxs-lookup"><span data-stu-id="f11a3-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="f11a3-125">Selecteer **Client Apps > Apps**.</span><span class="sxs-lookup"><span data-stu-id="f11a3-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="f11a3-126">Zoek en selecteer uw app in de lijst met apps.</span><span class="sxs-lookup"><span data-stu-id="f11a3-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="f11a3-127">Selecteer **eigenschappen**in het **blad Overzicht** .</span><span class="sxs-lookup"><span data-stu-id="f11a3-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="f11a3-128">Selecteer **App-pakketbestand**.</span><span class="sxs-lookup"><span data-stu-id="f11a3-128">Select **App package file**.</span></span>
7. <span data-ttu-id="f11a3-129">Selecteer het mappictogram en blader naar de locatie van uw bijgewerkte app-bestand.</span><span class="sxs-lookup"><span data-stu-id="f11a3-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="f11a3-130">Selecteer **Openen**.</span><span class="sxs-lookup"><span data-stu-id="f11a3-130">Select **Open**.</span></span> <span data-ttu-id="f11a3-131">De app-informatie wordt bijgewerkt met de pakketinformatie.</span><span class="sxs-lookup"><span data-stu-id="f11a3-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="f11a3-132">Controleer of **de app-versie** het bijgewerkte app-pakket weergeeft.</span><span class="sxs-lookup"><span data-stu-id="f11a3-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="f11a3-133">Een app terugdraaien naar een vorige versie</span><span class="sxs-lookup"><span data-stu-id="f11a3-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="f11a3-134">Als er een fout wordt gevonden wanneer een nieuwe versie van een app wordt geïmplementeerd, u terugdraaien naar een vorige versie.</span><span class="sxs-lookup"><span data-stu-id="f11a3-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="f11a3-135">Het hier beschreven proces is voor apps waarvan het type wordt vermeld als **Windows MSI line-of-business app** of **Windows-app (Win 32) - preview**</span><span class="sxs-lookup"><span data-stu-id="f11a3-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="f11a3-136">**Een bedrijfsregel-app terugdraaien naar een vorige versie**</span><span class="sxs-lookup"><span data-stu-id="f11a3-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="f11a3-137">Meld u aan bij [microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="f11a3-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="f11a3-138">Selecteer **Onder Inventaris**de optie **Apps**.</span><span class="sxs-lookup"><span data-stu-id="f11a3-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="f11a3-139">Selecteer de app die u moet terugdraaien en selecteer **Vervolgens Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="f11a3-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="f11a3-140">Selecteer **Eigenschappen** **onder Beheren**.</span><span class="sxs-lookup"><span data-stu-id="f11a3-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="f11a3-141">Selecteer **app-informatie**voor **Windows MSI-apps voor line-of-business** apps en selecteer vervolgens onder **App-versie negeren**de optie **Ja**.</span><span class="sxs-lookup"><span data-stu-id="f11a3-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="f11a3-142">Voor **Windows-apps (Win 32) - voorbeeld van** apps, selecteer **App-informatie,** selecteer **Detectieregels**en selecteer vervolgens **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="f11a3-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="f11a3-143">Als er een MSI-regel is, controleert u of **de controle van de MSI-productversie** is ingesteld op **Nee**.</span><span class="sxs-lookup"><span data-stu-id="f11a3-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="f11a3-144">[Upload een vorige versie van het bronbestand van de app](../get-started/deploy-apps.md) naar de Microsoft Managed Desktop Admin-portal.</span><span class="sxs-lookup"><span data-stu-id="f11a3-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

