---
title: Configureerbare instellingen implementeren in Microsoft Managed Desktop
description: Configureerbare instellingen in Microsoft Managed Desktop implementeren en bijhouden.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie, implementeren, gefaseerde implementatie, configureerbare instellingen
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b731422e6d981b12ea576ed26b841e7c679266ae
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530257"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="3f3eb-104">Configureerbare instellingen implementeren en bijhouden - Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="3f3eb-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="3f3eb-105">Nadat u wijzigingen hebt aangebracht in uw instellingscategorieën en een implementatie hebt gefaseerd, u op de pagina Implementatiestatus beginnen met het implementeren van uw instellingen in groepen.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="3f3eb-106">Op deze pagina ziet u een overzicht van elke configureerbare instelling.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="3f3eb-107">Door een instellingscategorie te openen, u instellingen implementeren voor groepen en de voortgang van deze implementaties bijhouden.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="3f3eb-108">Implementatiestatussen</span><span class="sxs-lookup"><span data-stu-id="3f3eb-108">Deployment statuses</span></span> 

<span data-ttu-id="3f3eb-109">Dit zijn de statussen die u voor elke implementatie ziet.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="3f3eb-110">Status</span><span class="sxs-lookup"><span data-stu-id="3f3eb-110">Status</span></span>  | <span data-ttu-id="3f3eb-111">Uitleg</span><span class="sxs-lookup"><span data-stu-id="3f3eb-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="3f3eb-112">Implementeren</span><span class="sxs-lookup"><span data-stu-id="3f3eb-112">Deploy</span></span> | <span data-ttu-id="3f3eb-113">Uw wijziging wacht om te worden geïmplementeerd in deze groep.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="3f3eb-114">In uitvoering</span><span class="sxs-lookup"><span data-stu-id="3f3eb-114">In progress</span></span> | <span data-ttu-id="3f3eb-115">De wijziging wordt toegepast op actieve apparaten in deze groep.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="3f3eb-116">Volledige</span><span class="sxs-lookup"><span data-stu-id="3f3eb-116">Complete</span></span> | <span data-ttu-id="3f3eb-117">De wijziging is voltooid op alle actieve apparaten in deze groep.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="3f3eb-118">Mislukt</span><span class="sxs-lookup"><span data-stu-id="3f3eb-118">Failed</span></span> | <span data-ttu-id="3f3eb-119">De wijziging is mislukt op 10 procent van de actieve apparaten in de groep, waardoor de implementatie is gestopt.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="3f3eb-120">Een ondersteuningsverzoek wordt automatisch geopend met Microsoft Managed Desktop-bewerkingen om de implementatie op te lossen.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="3f3eb-121">Teruggekeerd</span><span class="sxs-lookup"><span data-stu-id="3f3eb-121">Reverted</span></span> | <span data-ttu-id="3f3eb-122">De wijziging is teruggezet naar de laatste wijziging die is geïmplementeerd in alle implementatiegroepen.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="3f3eb-123">Wijzigingen implementeren</span><span class="sxs-lookup"><span data-stu-id="3f3eb-123">Deploy changes</span></span>

<span data-ttu-id="3f3eb-124">We tonen bureaublad achtergrondfoto in deze instructies.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="3f3eb-125">Nadat u een implementatie hebt geënsceneerd, implementeert u wijzigingen vanaf de pagina Implementatiestatus.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="3f3eb-126">**Wijzigingen implementeren**</span><span class="sxs-lookup"><span data-stu-id="3f3eb-126">**To deploy changes**</span></span>

1. <span data-ttu-id="3f3eb-127">Aanmelden bij [microsoft Managed Desktop Admin-portal](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="3f3eb-127">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="3f3eb-128">Selecteer **Configureerbaar**onder **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="3f3eb-129">Selecteer in **de werkruimte van** de implementatiestatus de instelling die u wilt implementeren en selecteer vervolgens de gefaseerde implementatie die moet worden geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="3f3eb-130">Selecteer **Implementeren** om de wijziging in een van de implementatiegroepen te implementeren.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE] 
> <span data-ttu-id="3f3eb-131">Het oranje waarschuwingspictogram geeft aan dat er een vorige groep beschikbaar is voor implementatie, omdat het wordt aanbevolen om in volgorde uit te rollen.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span> 

<span data-ttu-id="3f3eb-132">![Werkruimte voor implementatiestatus.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-132">![Deployment status workspace.</span></span> <span data-ttu-id="3f3eb-133">Deelvenster Vertrouwde sites aan de rechterkant.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-133">Trusted sites pane on the right.</span></span> <span data-ttu-id="3f3eb-134">In de sectie Implementatiegroepen bevinden zich drie kolommen: implementatiegroepen, apparaten en status.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-134">In the Deployment groups section are three columns: deployment groups, devices, and status.</span></span> <span data-ttu-id="3f3eb-135">In de statuskolom wordt 'implementeren' gemarkeerd.](../../media/1deployedit.png)</span><span class="sxs-lookup"><span data-stu-id="3f3eb-135">In the status column, "deploy" is highlighted.](../../media/1deployedit.png)</span></span>
<span data-ttu-id="3f3eb-136">We raden u aan om in deze volgorde te implementeren in implementatiegroepen: Test, First, Fast en vervolgens Broad.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-136">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="3f3eb-137">Wanneer wijzigingen in elke groep zijn voltooid, wordt de status gewijzigd in **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-137">When changes complete in each group, the status changes to **Complete**.</span></span>

![Werkruimte voor implementatiestatus met kolommen voor datum bijgewerkt, versie, test, eerste, snel en breed.](../../media/2completeedit.png)

## <a name="revert-deployment"></a><span data-ttu-id="3f3eb-140">Implementatie terugdraaien</span><span class="sxs-lookup"><span data-stu-id="3f3eb-140">Revert deployment</span></span>

<span data-ttu-id="3f3eb-141">Nadat u een wijziging hebt geïmplementeerd, u terugkeren van **de implementatiestatus**.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-141">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="3f3eb-142">Wanneer u een wijziging die **wordt uitgevoerd** of **voltooid,** terugzet, wordt de huidige implementatie gestopt.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-142">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="3f3eb-143">De instelling wordt teruggezet naar de laatste versie die voor alle groepen is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-143">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="3f3eb-144">We tonen de stappen om een wijziging terug te draaien met de achtergrondafbeelding bureaublad als voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-144">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="3f3eb-145">**Een wijziging terugdraaien**</span><span class="sxs-lookup"><span data-stu-id="3f3eb-145">**To revert a change**</span></span>
1. <span data-ttu-id="3f3eb-146">Aanmelden bij [microsoft Managed Desktop Admin-portal](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="3f3eb-146">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="3f3eb-147">Selecteer **Configureerbaar**onder **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-147">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="3f3eb-148">Selecteer in **de werkruimte van** de implementatiestatus de instelling die u wilt terugdraaien en selecteer vervolgens de gefaseerde implementatie om terug te keren.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-148">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="3f3eb-149">Selecteer Implementeren **van implementatie**onder Noodzaak om deze wijziging **terug te**draaien.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-149">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

![Werkruimte voor implementatiestatus.](../../media/3revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="3f3eb-153">Overige informatiebronnen</span><span class="sxs-lookup"><span data-stu-id="3f3eb-153">Additional resources</span></span>
- [<span data-ttu-id="3f3eb-154">Overzicht van configureerbare instellingen</span><span class="sxs-lookup"><span data-stu-id="3f3eb-154">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="3f3eb-155">Verwijzing naar configureerbare instellingen</span><span class="sxs-lookup"><span data-stu-id="3f3eb-155">Configurable settings reference</span></span>](config-setting-ref.md) 
