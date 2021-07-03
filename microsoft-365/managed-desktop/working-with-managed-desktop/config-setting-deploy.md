---
title: Configureerbare instellingen implementeren in Microsoft Managed Desktop
description: Configureerbare instellingen wijzigen implementeren en bijhouden in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie, implementeren, gefaseerd implementeren, configureerbare instellingen
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: aad4995f9c329b0fd8fcbcc8b1d13379453c2a76
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287793"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="68d57-104">Configureerbare instellingen implementeren en bijhouden - Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="68d57-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="68d57-105">Nadat u wijzigingen hebt aangebracht in uw instellingscategorieën en een implementatie hebt geïmplementeerd, kunt u op de pagina Implementatiestatus beginnen met het implementeren van uw instellingen naar groepen.</span><span class="sxs-lookup"><span data-stu-id="68d57-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="68d57-106">Op deze pagina ziet u een overzicht van elke configureerbare instelling.</span><span class="sxs-lookup"><span data-stu-id="68d57-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="68d57-107">Door een instellingscategorie te openen, kunt u instellingen implementeren voor groepen en de voortgang van deze implementaties bijhouden.</span><span class="sxs-lookup"><span data-stu-id="68d57-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="68d57-108">Implementatiestatussen</span><span class="sxs-lookup"><span data-stu-id="68d57-108">Deployment statuses</span></span>

<span data-ttu-id="68d57-109">Dit zijn de statussen die u voor elke implementatie ziet.</span><span class="sxs-lookup"><span data-stu-id="68d57-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="68d57-110">Status</span><span class="sxs-lookup"><span data-stu-id="68d57-110">Status</span></span> | <span data-ttu-id="68d57-111">Uitleg</span><span class="sxs-lookup"><span data-stu-id="68d57-111">Explanation</span></span>
--- | ---
<span data-ttu-id="68d57-112">Implementeren</span><span class="sxs-lookup"><span data-stu-id="68d57-112">Deploy</span></span> | <span data-ttu-id="68d57-113">Uw wijziging wacht op de geïmplementeerde wijziging in deze groep.</span><span class="sxs-lookup"><span data-stu-id="68d57-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="68d57-114">In uitvoering</span><span class="sxs-lookup"><span data-stu-id="68d57-114">In progress</span></span> | <span data-ttu-id="68d57-115">De wijziging wordt toegepast op actieve apparaten in deze groep.</span><span class="sxs-lookup"><span data-stu-id="68d57-115">The change is being applied to active devices in this group.</span></span>
<span data-ttu-id="68d57-116">Voltooien</span><span class="sxs-lookup"><span data-stu-id="68d57-116">Complete</span></span> | <span data-ttu-id="68d57-117">De wijziging is voltooid op alle actieve apparaten in deze groep.</span><span class="sxs-lookup"><span data-stu-id="68d57-117">The change completed on all active devices in this group.</span></span>
<span data-ttu-id="68d57-118">Mislukt</span><span class="sxs-lookup"><span data-stu-id="68d57-118">Failed</span></span> | <span data-ttu-id="68d57-119">De wijziging is mislukt op een 10 procent van de actieve apparaten in de groep, dus de implementatie is gestopt.</span><span class="sxs-lookup"><span data-stu-id="68d57-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="68d57-120">Er wordt automatisch een ondersteuningsaanvraag geopend met Microsoft Managed Desktop om de implementatie op te lossen.</span><span class="sxs-lookup"><span data-stu-id="68d57-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span>
<span data-ttu-id="68d57-121">Teruggevormd</span><span class="sxs-lookup"><span data-stu-id="68d57-121">Reverted</span></span> | <span data-ttu-id="68d57-122">De wijziging is teruggezet naar de laatste wijziging die is geïmplementeerd voor alle implementatiegroepen.</span><span class="sxs-lookup"><span data-stu-id="68d57-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="68d57-123">Wijzigingen implementeren</span><span class="sxs-lookup"><span data-stu-id="68d57-123">Deploy changes</span></span>

<span data-ttu-id="68d57-124">In deze instructies wordt een bureaubladachtergrondafbeelding weergeven.</span><span class="sxs-lookup"><span data-stu-id="68d57-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="68d57-125">Nadat u een implementatie hebt gefaseerd, implementeert u wijzigingen vanaf de pagina Implementatiestatus.</span><span class="sxs-lookup"><span data-stu-id="68d57-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span>

<span data-ttu-id="68d57-126">**Wijzigingen implementeren**</span><span class="sxs-lookup"><span data-stu-id="68d57-126">**To deploy changes**</span></span>

1. <span data-ttu-id="68d57-127">Meld u aan [bij Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en ga naar **het** menu Apparaten</span><span class="sxs-lookup"><span data-stu-id="68d57-127">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="68d57-128">Zoek naar de Microsoft Managed Desktop sectie en selecteer **Instellingen.**</span><span class="sxs-lookup"><span data-stu-id="68d57-128">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="68d57-129">Selecteer **in de werkruimte** Implementatiestatus de instelling die u wilt implementeren en selecteer vervolgens de gefaseerd implementatie die u wilt implementeren.</span><span class="sxs-lookup"><span data-stu-id="68d57-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="68d57-130">Selecteer **Implementeren** om de wijziging te implementeren in een van de implementatiegroepen.</span><span class="sxs-lookup"><span data-stu-id="68d57-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE]
> <span data-ttu-id="68d57-131">Het oranje waarschuwingspictogram geeft aan dat er een vorige groep beschikbaar is voor implementatie, omdat het wordt aanbevolen om deze in volgorde uit te rollen.</span><span class="sxs-lookup"><span data-stu-id="68d57-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

<span data-ttu-id="68d57-132">We raden u aan om in deze volgorde te implementeren voor implementatiegroepen: Test, First, Fast en vervolgens Broad.</span><span class="sxs-lookup"><span data-stu-id="68d57-132">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="68d57-133">Wanneer wijzigingen in elke groep zijn voltooid, wordt de status gewijzigd in **Voltooid.**</span><span class="sxs-lookup"><span data-stu-id="68d57-133">When changes complete in each group, the status changes to **Complete**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a><span data-ttu-id="68d57-134">Implementatie terugdraaien</span><span class="sxs-lookup"><span data-stu-id="68d57-134">Revert deployment</span></span>

<span data-ttu-id="68d57-135">Nadat u een wijziging hebt geïmplementeerd, kunt u terugkeren van de **implementatiestatus.**</span><span class="sxs-lookup"><span data-stu-id="68d57-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="68d57-136">Wanneer u een wijziging die In uitvoering **of** Voltooid **is,** terugzet, wordt de huidige implementatie gestopt.</span><span class="sxs-lookup"><span data-stu-id="68d57-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="68d57-137">De instelling wordt terug naar de laatste versie die is geïmplementeerd voor alle groepen.</span><span class="sxs-lookup"><span data-stu-id="68d57-137">The setting will revert to the last version that was deployed to all groups.</span></span>

<span data-ttu-id="68d57-138">We laten de stappen zien om een wijziging terug te zetten met de achtergrondafbeelding bureaublad als voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="68d57-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="68d57-139">**Een wijziging terugdraaien**</span><span class="sxs-lookup"><span data-stu-id="68d57-139">**To revert a change**</span></span>

1. <span data-ttu-id="68d57-140">Meld u aan [bij Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en ga naar **het** menu Apparaten</span><span class="sxs-lookup"><span data-stu-id="68d57-140">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="68d57-141">Zoek naar de Microsoft Managed Desktop sectie en selecteer **Instellingen.**</span><span class="sxs-lookup"><span data-stu-id="68d57-141">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="68d57-142">Selecteer **in de** werkruimte Implementatiestatus de instelling die u wilt terugdraaien en selecteer vervolgens de gefaseerd implementatie die u wilt terugdraaien.</span><span class="sxs-lookup"><span data-stu-id="68d57-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="68d57-143">Selecteer **onder Wilt u deze wijziging terugdraaien?** de optie Implementatie **terugdraaien.**</span><span class="sxs-lookup"><span data-stu-id="68d57-143">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a><span data-ttu-id="68d57-144">Aanvullende bronnen</span><span class="sxs-lookup"><span data-stu-id="68d57-144">Additional resources</span></span>

- [<span data-ttu-id="68d57-145">Overzicht van configureerbare instellingen</span><span class="sxs-lookup"><span data-stu-id="68d57-145">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="68d57-146">Verwijzing naar configureerbare instellingen</span><span class="sxs-lookup"><span data-stu-id="68d57-146">Configurable settings reference</span></span>](config-setting-ref.md) 
