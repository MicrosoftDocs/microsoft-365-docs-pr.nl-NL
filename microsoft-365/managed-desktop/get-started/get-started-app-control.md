---
title: Aan de slag met app-besturingselement
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
ms.openlocfilehash: 12df7b074019ea47f2e293b71c6b0b25fe46f66f
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170693"
---
# <a name="get-started-with-app-control"></a><span data-ttu-id="f3b53-103">Aan de slag met app-besturingselement</span><span class="sxs-lookup"><span data-stu-id="f3b53-103">Get started with app control</span></span>

<span data-ttu-id="f3b53-104">Voordat u app-controle in uw omgeving inschakelt, moet u controleren en begrijpen [hoe Microsoft Managed Desktop deze implementeert](../service-description/app-control.md) en uw rollen en verantwoordelijkheden.</span><span class="sxs-lookup"><span data-stu-id="f3b53-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="f3b53-105">Microsoft Managed Desktop vereenvoudigt de app-controle door te zorgen voor de meer uitdagende aspecten van het verkrijgen van een veilig basisbeleid.</span><span class="sxs-lookup"><span data-stu-id="f3b53-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="f3b53-106">Uw IT-beheerders moeten uw apps nog steeds testen in de testring en de logboeken controleren op eventuele waarschuwingen of fouten.</span><span class="sxs-lookup"><span data-stu-id="f3b53-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="f3b53-107">Als een app een vrijstelling nodig heeft, u een aanvraag indienen of microsoft Managed Desktop Operation mogelijk, afhankelijk van wie deze eerst detecteert.</span><span class="sxs-lookup"><span data-stu-id="f3b53-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="f3b53-108">Eerste implementatie van apps</span><span class="sxs-lookup"><span data-stu-id="f3b53-108">Initial deployment of apps</span></span>

<span data-ttu-id="f3b53-109">Wanneer u apps voor het eerst implementeert, moet Microsoft Managed Desktop hun huidige gedrag beoordelen.</span><span class="sxs-lookup"><span data-stu-id="f3b53-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="f3b53-110">De exacte stappen voor het inschakelen van app-besturingselementen zijn afhankelijk van de vraag of apparaten al in uw omgeving zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="f3b53-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="f3b53-111">Apparaten die al in gebruik zijn</span><span class="sxs-lookup"><span data-stu-id="f3b53-111">Devices already in use</span></span>

<span data-ttu-id="f3b53-112">Als u al ten minste één Microsoft Managed Desktop-apparaat in gebruik hebt, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="f3b53-112">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="f3b53-113">Open een serviceticket met Microsoft Managed Desktop Operations met het verzoek om app-besturingselement in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="f3b53-113">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="f3b53-114">Operations implementeert een [auditbeleid](../service-description/app-control.md#audit-policy) op alle apparaten.</span><span class="sxs-lookup"><span data-stu-id="f3b53-114">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="f3b53-115">[Test uw toepassingen](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) om te zien of deze worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="f3b53-115">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="f3b53-116">Als een toepassing wordt geblokkeerd, opent u een [aanvraag voor ondertekenaar](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span><span class="sxs-lookup"><span data-stu-id="f3b53-116">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="f3b53-117">Zodra u uw tests hebt voltooid (ongeacht de resultaten), stelt u Operations hiervan op de hoogte en noteer u eventuele in behandeling zijnde ondertekenaarverzoeken.</span><span class="sxs-lookup"><span data-stu-id="f3b53-117">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="f3b53-118">Operations implementeert geleidelijk beleid naar implementatiegroepen volgens deze planning:</span><span class="sxs-lookup"><span data-stu-id="f3b53-118">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="f3b53-119">Implementatiegroep</span><span class="sxs-lookup"><span data-stu-id="f3b53-119">Deployment group</span></span>  |<span data-ttu-id="f3b53-120">Beleidstype</span><span class="sxs-lookup"><span data-stu-id="f3b53-120">Policy type</span></span>  |<span data-ttu-id="f3b53-121">Timing</span><span class="sxs-lookup"><span data-stu-id="f3b53-121">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="f3b53-122">Test</span><span class="sxs-lookup"><span data-stu-id="f3b53-122">Test</span></span>     |  <span data-ttu-id="f3b53-123">Audit</span><span class="sxs-lookup"><span data-stu-id="f3b53-123">Audit</span></span>       |  <span data-ttu-id="f3b53-124">Dag 0</span><span class="sxs-lookup"><span data-stu-id="f3b53-124">Day 0</span></span>       |
|<span data-ttu-id="f3b53-125">Eerste</span><span class="sxs-lookup"><span data-stu-id="f3b53-125">First</span></span>     | <span data-ttu-id="f3b53-126">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="f3b53-126">Enforced</span></span>        | <span data-ttu-id="f3b53-127">Dag 1</span><span class="sxs-lookup"><span data-stu-id="f3b53-127">Day 1</span></span>        |
|<span data-ttu-id="f3b53-128">Snel</span><span class="sxs-lookup"><span data-stu-id="f3b53-128">Fast</span></span>     | <span data-ttu-id="f3b53-129">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="f3b53-129">Enforced</span></span>        |  <span data-ttu-id="f3b53-130">Dag 3</span><span class="sxs-lookup"><span data-stu-id="f3b53-130">Day 3</span></span>       |
|<span data-ttu-id="f3b53-131">Brede</span><span class="sxs-lookup"><span data-stu-id="f3b53-131">Broad</span></span>     | <span data-ttu-id="f3b53-132">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="f3b53-132">Enforced</span></span>        |  <span data-ttu-id="f3b53-133">Dag 7</span><span class="sxs-lookup"><span data-stu-id="f3b53-133">Day 7</span></span>       |

<span data-ttu-id="f3b53-134">U altijd een andere serviceaanvraag openen om een deel van deze implementatie op elk gewenst moment tijdens de implementatie te onderbreken of terug te draaien.</span><span class="sxs-lookup"><span data-stu-id="f3b53-134">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="f3b53-135">Apparaten die nog niet in gebruik zijn</span><span class="sxs-lookup"><span data-stu-id="f3b53-135">Devices not yet in use</span></span>

<span data-ttu-id="f3b53-136">Als u nog geen apparaten in gebruik hebt, opent u een serviceticket met Microsoft Managed Desktop Operations met het verzoek om app-besturingselement in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="f3b53-136">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="f3b53-137">Operations implementeert geleidelijk beleid naar implementatiegroepen volgens deze planning:</span><span class="sxs-lookup"><span data-stu-id="f3b53-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="f3b53-138">Implementatiegroep</span><span class="sxs-lookup"><span data-stu-id="f3b53-138">Deployment group</span></span>  |<span data-ttu-id="f3b53-139">Beleidstype</span><span class="sxs-lookup"><span data-stu-id="f3b53-139">Policy type</span></span>  |<span data-ttu-id="f3b53-140">Timing</span><span class="sxs-lookup"><span data-stu-id="f3b53-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="f3b53-141">Test</span><span class="sxs-lookup"><span data-stu-id="f3b53-141">Test</span></span>     |  <span data-ttu-id="f3b53-142">Audit</span><span class="sxs-lookup"><span data-stu-id="f3b53-142">Audit</span></span>       |  <span data-ttu-id="f3b53-143">Dag 0</span><span class="sxs-lookup"><span data-stu-id="f3b53-143">Day 0</span></span>       |
|<span data-ttu-id="f3b53-144">Eerste</span><span class="sxs-lookup"><span data-stu-id="f3b53-144">First</span></span>     | <span data-ttu-id="f3b53-145">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="f3b53-145">Enforced</span></span>        | <span data-ttu-id="f3b53-146">Dag 1</span><span class="sxs-lookup"><span data-stu-id="f3b53-146">Day 1</span></span>        |
|<span data-ttu-id="f3b53-147">Snel</span><span class="sxs-lookup"><span data-stu-id="f3b53-147">Fast</span></span>     | <span data-ttu-id="f3b53-148">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="f3b53-148">Enforced</span></span>        |  <span data-ttu-id="f3b53-149">Dag 3</span><span class="sxs-lookup"><span data-stu-id="f3b53-149">Day 3</span></span>       |
|<span data-ttu-id="f3b53-150">Brede</span><span class="sxs-lookup"><span data-stu-id="f3b53-150">Broad</span></span>     | <span data-ttu-id="f3b53-151">Afgedwongen</span><span class="sxs-lookup"><span data-stu-id="f3b53-151">Enforced</span></span>        |  <span data-ttu-id="f3b53-152">Dag 7</span><span class="sxs-lookup"><span data-stu-id="f3b53-152">Day 7</span></span>       |

<span data-ttu-id="f3b53-153">U altijd een andere serviceaanvraag openen om een deel van deze implementatie op elk gewenst moment tijdens de implementatie te onderbreken of terug te draaien.</span><span class="sxs-lookup"><span data-stu-id="f3b53-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

