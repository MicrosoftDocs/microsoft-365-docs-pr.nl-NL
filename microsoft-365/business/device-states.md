---
title: Statuswaarden voor apparaten
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Meer informatie over Microsoft 365 Business apparaat de lidstaten.
ms.openlocfilehash: bd6f1ad7f7671d9616fd14d477dfcfb164ff6bd0
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "26982902"
---
# <a name="device-states"></a><span data-ttu-id="f6576-103">Statuswaarden voor apparaten</span><span class="sxs-lookup"><span data-stu-id="f6576-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="f6576-104">Statuswaarden voor apparaten</span><span class="sxs-lookup"><span data-stu-id="f6576-104">Device states</span></span>

<span data-ttu-id="f6576-105">Apparaten in de lijst **Apparaatacties** lijst (startpagina beheerders \> **Apparaatacties**) kunnen de volgende statuswaarden hebben.</span><span class="sxs-lookup"><span data-stu-id="f6576-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="f6576-107">**Status**</span><span class="sxs-lookup"><span data-stu-id="f6576-107">**Status**</span></span>|<span data-ttu-id="f6576-108">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="f6576-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f6576-109">Beheerd door Intune</span><span class="sxs-lookup"><span data-stu-id="f6576-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="f6576-110">Beheerd door Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="f6576-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="f6576-111">In afwachting van buiten gebruik stellen</span><span class="sxs-lookup"><span data-stu-id="f6576-111">Retire pending</span></span>  <br/> |<span data-ttu-id="f6576-112">Microsoft 365 Business is bezig met de voorbereiding om bedrijfsgegevens van het apparaat te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f6576-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="f6576-113">Buitengebruikstelling wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="f6576-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="f6576-114">Microsoft 365 Business verwijdert momenteel bedrijfsgegevens van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="f6576-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="f6576-115">Buiten gebruik stellen is mislukt</span><span class="sxs-lookup"><span data-stu-id="f6576-115">Retire failed</span></span>  <br/> | <span data-ttu-id="f6576-116">Het verwijderen van bedrijfsgegevens is mislukt.</span><span class="sxs-lookup"><span data-stu-id="f6576-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="f6576-117">Buiten gebruik stellen is geannuleerd</span><span class="sxs-lookup"><span data-stu-id="f6576-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="f6576-118">De actie voor buiten gebruik stellen is geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="f6576-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="f6576-119">Wissen in behandeling</span><span class="sxs-lookup"><span data-stu-id="f6576-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="f6576-120">Wachten tot de fabrieksinstellingen opnieuw worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="f6576-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="f6576-121">Wissen wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="f6576-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="f6576-122">De fabrieksinstellingen worden opnieuw ingesteld.</span><span class="sxs-lookup"><span data-stu-id="f6576-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="f6576-123">Wissen is mislukt</span><span class="sxs-lookup"><span data-stu-id="f6576-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="f6576-124">De fabrieksinstellingen kunnen niet opnieuw worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="f6576-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="f6576-125">Wissen is geannuleerd</span><span class="sxs-lookup"><span data-stu-id="f6576-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="f6576-126">Het wissen van de fabrieksinstellingen is geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="f6576-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="f6576-127">Niet in orde</span><span class="sxs-lookup"><span data-stu-id="f6576-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="f6576-128">Dit betekent dat een actie in behandeling is (of wordt uitgevoerd), maar dat het apparaat meer dan 30 dagen niet is ingecheckt.</span><span class="sxs-lookup"><span data-stu-id="f6576-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="f6576-129">In afwachting van verwijderen</span><span class="sxs-lookup"><span data-stu-id="f6576-129">Delete pending</span></span>  <br/> |<span data-ttu-id="f6576-130">Het verwijderen is in behandeling.</span><span class="sxs-lookup"><span data-stu-id="f6576-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="f6576-131">Gedetecteerd</span><span class="sxs-lookup"><span data-stu-id="f6576-131">Discovered</span></span>  <br/> |<span data-ttu-id="f6576-132">Microsoft 365 Business heeft het apparaat gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="f6576-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
