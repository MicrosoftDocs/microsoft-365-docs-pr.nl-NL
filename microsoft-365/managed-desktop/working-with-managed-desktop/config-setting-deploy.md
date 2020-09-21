---
title: Configureerbare instellingen implementeren in Microsoft Managed Desktop
description: Wijzigingen in de configureerbare instellingen in Microsoft beheerde Bureaubladimplementatie en bijhouden.
keywords: Microsoft Managed Desktop, Microsoft 365, service, Documentatie, implementatie, gefaseerde implementatie, configureerbare instellingen
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a24d0dc64e2262a8b208119c45a4a6bade701c10
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104532"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="f2e4e-104">Configureerbare instellingen implementeren en bijhouden: Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="f2e4e-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="f2e4e-105">Nadat u de instellings categorieën en de implementatie van een fase hebt gewijzigd, kunt u de instellingen van de pagina voor de implementatie van de instellingen wijzigen in groepen.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="f2e4e-106">Op deze pagina ziet u een overzicht van elke configureerbare instelling.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="f2e4e-107">Als u een instellings categorie opent, kunt u instellingen implementeren voor groepen en de voortgang van deze implementaties bijhouden.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="f2e4e-108">Implementatiestatus</span><span class="sxs-lookup"><span data-stu-id="f2e4e-108">Deployment statuses</span></span> 

<span data-ttu-id="f2e4e-109">Dit zijn de statussen die u ziet voor elke implementatie.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="f2e4e-110">Status</span><span class="sxs-lookup"><span data-stu-id="f2e4e-110">Status</span></span>  | <span data-ttu-id="f2e4e-111">Uitleg</span><span class="sxs-lookup"><span data-stu-id="f2e4e-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="f2e4e-112">Implementeren</span><span class="sxs-lookup"><span data-stu-id="f2e4e-112">Deploy</span></span> | <span data-ttu-id="f2e4e-113">De wijziging wacht op de implementatie van deze groep.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="f2e4e-114">Wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="f2e4e-114">In progress</span></span> | <span data-ttu-id="f2e4e-115">De wijziging wordt toegepast op actieve apparaten in deze groep.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="f2e4e-116">Vul</span><span class="sxs-lookup"><span data-stu-id="f2e4e-116">Complete</span></span> | <span data-ttu-id="f2e4e-117">De wijziging is voltooid op alle actieve apparaten in deze groep.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="f2e4e-118">Mislukt</span><span class="sxs-lookup"><span data-stu-id="f2e4e-118">Failed</span></span> | <span data-ttu-id="f2e4e-119">De wijziging mislukt op een 10 procent van de actieve apparaten in de groep, dus de implementatie is gestopt.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="f2e4e-120">Er wordt automatisch een ondersteuningsverzoek geopend met Microsoft beheerde bureaublad bewerkingen voor het oplossen van problemen met de implementatie.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="f2e4e-121">Teruggezet</span><span class="sxs-lookup"><span data-stu-id="f2e4e-121">Reverted</span></span> | <span data-ttu-id="f2e4e-122">De wijziging keert terug naar de laatste wijziging die is geïmplementeerd voor alle implementatie groepen.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="f2e4e-123">Wijzigingen implementeren</span><span class="sxs-lookup"><span data-stu-id="f2e4e-123">Deploy changes</span></span>

<span data-ttu-id="f2e4e-124">In deze instructies wordt de achtergrondafbeelding op het bureaublad weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="f2e4e-125">Wanneer u een implementatie hebt klaargezet, implementeert u de wijzigingen op de pagina implementatiestatus.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="f2e4e-126">**Wijzigingen implementeren**</span><span class="sxs-lookup"><span data-stu-id="f2e4e-126">**To deploy changes**</span></span>

1. <span data-ttu-id="f2e4e-127">Meld u aan bij [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en ga naar het menu **apparaten** .</span><span class="sxs-lookup"><span data-stu-id="f2e4e-127">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="f2e4e-128">Ga naar de sectie Microsoft Managed Desktop en selecteer **instellingen**.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-128">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="f2e4e-129">Selecteer in de werkruimte voor **implementatiestatus** de instelling die u wilt implementeren en selecteer vervolgens de gefaseerde implementatie die u wilt implementeren.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="f2e4e-130">Selecteer **implementeren** om de wijziging te implementeren voor een van de implementatie groepen.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE] 
> <span data-ttu-id="f2e4e-131">Het oranje waarschuwingspictogram geeft aan dat er een eerdere groep beschikbaar is om te worden geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span> 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

<span data-ttu-id="f2e4e-132">We raden u aan om in deze volgorde implementatie groepen te implementeren: testen, voor het eerst, snel en vervolgens algemeen.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-132">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="f2e4e-133">Wanneer wijzigingen in elke groep worden doorgevoerd, wordt de status gewijzigd in **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-133">When changes complete in each group, the status changes to **Complete**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a><span data-ttu-id="f2e4e-134">Implementatie herstellen</span><span class="sxs-lookup"><span data-stu-id="f2e4e-134">Revert deployment</span></span>

<span data-ttu-id="f2e4e-135">Nadat u een wijziging hebt geïmplementeerd, kunt u de **implementatiestatus**herstellen.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="f2e4e-136">Wanneer u een wijziging **doorvoert**die wordt **uitgevoerd** of voltooid, stopt de huidige implementatie.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="f2e4e-137">De instelling keert terug naar de laatste versie die is geïmplementeerd voor alle groepen.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-137">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="f2e4e-138">De stappen voor het herstellen van een wijziging met de bureaubladachtergrond afbeelding als voorbeeld worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="f2e4e-139">**Een wijziging ongedaan maken**</span><span class="sxs-lookup"><span data-stu-id="f2e4e-139">**To revert a change**</span></span>
1. <span data-ttu-id="f2e4e-140">Meld u aan bij [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) en ga naar het menu **apparaten** .</span><span class="sxs-lookup"><span data-stu-id="f2e4e-140">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="f2e4e-141">Ga naar de sectie Microsoft Managed Desktop en selecteer **instellingen**.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-141">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="f2e4e-142">Selecteer in de werkruimte voor **implementatiestatus** de instelling die u wilt herstellen en selecteer de gefaseerde implementatie die u wilt herstellen.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="f2e4e-143">Selecteer onder **wilt u deze wijziging herstellen? de**optie **herstel herstellen**.</span><span class="sxs-lookup"><span data-stu-id="f2e4e-143">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a><span data-ttu-id="f2e4e-144">Aanvullende bronnen</span><span class="sxs-lookup"><span data-stu-id="f2e4e-144">Additional resources</span></span>
- [<span data-ttu-id="f2e4e-145">Overzicht van configureerbare instellingen</span><span class="sxs-lookup"><span data-stu-id="f2e4e-145">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="f2e4e-146">Verwijzing naar configureerbare instellingen</span><span class="sxs-lookup"><span data-stu-id="f2e4e-146">Configurable settings reference</span></span>](config-setting-ref.md) 
