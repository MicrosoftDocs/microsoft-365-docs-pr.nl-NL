---
title: Aan de slag met App-beheer
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 431e6cb3b8d7ab7e1dd317918fab4821889c7d4e
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430457"
---
# <a name="get-started-with-app-control"></a><span data-ttu-id="68750-103">Aan de slag met App-beheer</span><span class="sxs-lookup"><span data-stu-id="68750-103">Get started with app control</span></span>

<span data-ttu-id="68750-104">Voordat u app-controle in uw omgeving inschakelt, moet u controleren en begrijpen [hoe Microsoft Managed Desktop deze implementeert](../service-description/app-control.md) en uw rollen en verantwoordelijkheden.</span><span class="sxs-lookup"><span data-stu-id="68750-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="68750-105">Microsoft Managed Desktop vereenvoudigt de app-controle door te zorgen voor de meer uitdagende aspecten van het verkrijgen van een veilig basisbeleid.</span><span class="sxs-lookup"><span data-stu-id="68750-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="68750-106">Uw IT-beheerders moeten uw apps nog steeds testen in de testring en de logboeken controleren op eventuele waarschuwingen of fouten.</span><span class="sxs-lookup"><span data-stu-id="68750-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="68750-107">Als een app een vrijstelling nodig heeft, u een aanvraag indienen of microsoft Managed Desktop Operation mogelijk, afhankelijk van wie deze eerst detecteert.</span><span class="sxs-lookup"><span data-stu-id="68750-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="68750-108">Eerste implementatie van apps</span><span class="sxs-lookup"><span data-stu-id="68750-108">Initial deployment of apps</span></span>

<span data-ttu-id="68750-109">Wanneer u apps voor het eerst implementeert, moet Microsoft Managed Desktop hun huidige gedrag beoordelen.</span><span class="sxs-lookup"><span data-stu-id="68750-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="68750-110">De exacte stappen voor het inschakelen van app-besturingselementen zijn afhankelijk van de vraag of apparaten al in uw omgeving zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="68750-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="68750-111">Apparaten die nog niet in gebruik zijn</span><span class="sxs-lookup"><span data-stu-id="68750-111">Devices not yet in use</span></span>

<span data-ttu-id="68750-112">Als u nog geen apparaten in gebruik hebt, opent u een serviceticket met Microsoft Managed Desktop Operations met het verzoek om app-besturingselement in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="68750-112">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="68750-113">Operations implementeert geleidelijk beleid naar implementatiegroepen volgens deze planning:</span><span class="sxs-lookup"><span data-stu-id="68750-113">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="68750-114">Implementatiegroep</span><span class="sxs-lookup"><span data-stu-id="68750-114">Deployment group</span></span>  |<span data-ttu-id="68750-115">Beleidstype</span><span class="sxs-lookup"><span data-stu-id="68750-115">Policy type</span></span>  |<span data-ttu-id="68750-116">Timing</span><span class="sxs-lookup"><span data-stu-id="68750-116">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="68750-117">Test</span><span class="sxs-lookup"><span data-stu-id="68750-117">Test</span></span>     |  <span data-ttu-id="68750-118">Audit</span><span class="sxs-lookup"><span data-stu-id="68750-118">Audit</span></span>       |  <span data-ttu-id="68750-119">Dag 0</span><span class="sxs-lookup"><span data-stu-id="68750-119">Day 0</span></span>       |
|<span data-ttu-id="68750-120">Eerste</span><span class="sxs-lookup"><span data-stu-id="68750-120">First</span></span>     | <span data-ttu-id="68750-121">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="68750-121">Enforced</span></span>        | <span data-ttu-id="68750-122">Dag 1</span><span class="sxs-lookup"><span data-stu-id="68750-122">Day 1</span></span>        |
|<span data-ttu-id="68750-123">Snel</span><span class="sxs-lookup"><span data-stu-id="68750-123">Fast</span></span>     | <span data-ttu-id="68750-124">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="68750-124">Enforced</span></span>        |  <span data-ttu-id="68750-125">Dag 2</span><span class="sxs-lookup"><span data-stu-id="68750-125">Day 2</span></span>       |
|<span data-ttu-id="68750-126">Brede</span><span class="sxs-lookup"><span data-stu-id="68750-126">Broad</span></span>     | <span data-ttu-id="68750-127">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="68750-127">Enforced</span></span>        |  <span data-ttu-id="68750-128">Dag 3</span><span class="sxs-lookup"><span data-stu-id="68750-128">Day 3</span></span>       |

<span data-ttu-id="68750-129">U altijd een andere serviceaanvraag openen om een deel van deze implementatie op elk gewenst moment tijdens de implementatie te onderbreken of terug te draaien.</span><span class="sxs-lookup"><span data-stu-id="68750-129">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="68750-130">Apparaten die al in gebruik zijn</span><span class="sxs-lookup"><span data-stu-id="68750-130">Devices already in use</span></span>

<span data-ttu-id="68750-131">Als u al ten minste één Microsoft Managed Desktop-apparaat in gebruik hebt, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="68750-131">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="68750-132">Open een serviceticket met Microsoft Managed Desktop Operations met het verzoek om app-besturingselement in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="68750-132">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="68750-133">Operations implementeert een [auditbeleid](../service-description/app-control.md#audit-policy) op alle apparaten.</span><span class="sxs-lookup"><span data-stu-id="68750-133">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="68750-134">[Test uw toepassingen](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) om te zien of deze worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="68750-134">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="68750-135">Als een toepassing wordt geblokkeerd, opent u een [aanvraag voor ondertekenaar](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span><span class="sxs-lookup"><span data-stu-id="68750-135">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="68750-136">Zodra u uw tests hebt voltooid (ongeacht de resultaten), stelt u Operations hiervan op de hoogte en noteer u eventuele in behandeling zijnde ondertekenaarverzoeken.</span><span class="sxs-lookup"><span data-stu-id="68750-136">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="68750-137">Operations implementeert geleidelijk beleid naar implementatiegroepen volgens deze planning:</span><span class="sxs-lookup"><span data-stu-id="68750-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="68750-138">Implementatiegroep</span><span class="sxs-lookup"><span data-stu-id="68750-138">Deployment group</span></span>  |<span data-ttu-id="68750-139">Beleidstype</span><span class="sxs-lookup"><span data-stu-id="68750-139">Policy type</span></span>  |<span data-ttu-id="68750-140">Timing</span><span class="sxs-lookup"><span data-stu-id="68750-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="68750-141">Test</span><span class="sxs-lookup"><span data-stu-id="68750-141">Test</span></span>     |  <span data-ttu-id="68750-142">Audit</span><span class="sxs-lookup"><span data-stu-id="68750-142">Audit</span></span>       |  <span data-ttu-id="68750-143">Dag 0</span><span class="sxs-lookup"><span data-stu-id="68750-143">Day 0</span></span>       |
|<span data-ttu-id="68750-144">Eerste</span><span class="sxs-lookup"><span data-stu-id="68750-144">First</span></span>     | <span data-ttu-id="68750-145">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="68750-145">Enforced</span></span>        | <span data-ttu-id="68750-146">Dag 1</span><span class="sxs-lookup"><span data-stu-id="68750-146">Day 1</span></span>        |
|<span data-ttu-id="68750-147">Snel</span><span class="sxs-lookup"><span data-stu-id="68750-147">Fast</span></span>     | <span data-ttu-id="68750-148">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="68750-148">Enforced</span></span>        |  <span data-ttu-id="68750-149">Onderbroken, roll-out op aanvraag</span><span class="sxs-lookup"><span data-stu-id="68750-149">Paused, rollout on request</span></span>       |
|<span data-ttu-id="68750-150">Brede</span><span class="sxs-lookup"><span data-stu-id="68750-150">Broad</span></span>     | <span data-ttu-id="68750-151">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="68750-151">Enforced</span></span>        |  <span data-ttu-id="68750-152">Onderbroken, roll-out op aanvraag</span><span class="sxs-lookup"><span data-stu-id="68750-152">Paused, rollout on request</span></span>       |

<span data-ttu-id="68750-153">U altijd een andere serviceaanvraag openen om een deel van deze implementatie op elk gewenst moment tijdens de implementatie te onderbreken of terug te draaien.</span><span class="sxs-lookup"><span data-stu-id="68750-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>



