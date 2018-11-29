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
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/28/2018
ms.locfileid: "26982902"
---
# <a name="device-states"></a><span data-ttu-id="e77fd-103">Statuswaarden voor apparaten</span><span class="sxs-lookup"><span data-stu-id="e77fd-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="e77fd-104">Statuswaarden voor apparaten</span><span class="sxs-lookup"><span data-stu-id="e77fd-104">Device states</span></span>

<span data-ttu-id="e77fd-105">Apparaten in de lijst **Apparaatacties** lijst (startpagina beheerders \> **Apparaatacties**) kunnen de volgende statuswaarden hebben.</span><span class="sxs-lookup"><span data-stu-id="e77fd-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="e77fd-107">**Status**</span><span class="sxs-lookup"><span data-stu-id="e77fd-107">**Status**</span></span>|<span data-ttu-id="e77fd-108">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="e77fd-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e77fd-109">Beheerd door Intune</span><span class="sxs-lookup"><span data-stu-id="e77fd-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="e77fd-110">Beheerd door Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="e77fd-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="e77fd-111">In afwachting van buiten gebruik stellen</span><span class="sxs-lookup"><span data-stu-id="e77fd-111">Retire pending</span></span>  <br/> |<span data-ttu-id="e77fd-112">Microsoft 365 Business is bezig met de voorbereiding om bedrijfsgegevens van het apparaat te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e77fd-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="e77fd-113">Buitengebruikstelling wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="e77fd-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="e77fd-114">Microsoft 365 Business verwijdert momenteel bedrijfsgegevens van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="e77fd-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="e77fd-115">Buiten gebruik stellen is mislukt</span><span class="sxs-lookup"><span data-stu-id="e77fd-115">Retire failed</span></span>  <br/> | <span data-ttu-id="e77fd-116">Het verwijderen van bedrijfsgegevens is mislukt.</span><span class="sxs-lookup"><span data-stu-id="e77fd-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="e77fd-117">Buiten gebruik stellen is geannuleerd</span><span class="sxs-lookup"><span data-stu-id="e77fd-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="e77fd-118">De actie voor buiten gebruik stellen is geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="e77fd-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="e77fd-119">Wissen in behandeling</span><span class="sxs-lookup"><span data-stu-id="e77fd-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="e77fd-120">Wachten tot de fabrieksinstellingen opnieuw worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="e77fd-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="e77fd-121">Wissen wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="e77fd-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="e77fd-122">De fabrieksinstellingen worden opnieuw ingesteld.</span><span class="sxs-lookup"><span data-stu-id="e77fd-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="e77fd-123">Wissen is mislukt</span><span class="sxs-lookup"><span data-stu-id="e77fd-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="e77fd-124">De fabrieksinstellingen kunnen niet opnieuw worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="e77fd-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="e77fd-125">Wissen is geannuleerd</span><span class="sxs-lookup"><span data-stu-id="e77fd-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="e77fd-126">Het wissen van de fabrieksinstellingen is geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="e77fd-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="e77fd-127">Niet in orde</span><span class="sxs-lookup"><span data-stu-id="e77fd-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="e77fd-128">Dit betekent dat een actie in behandeling is (of wordt uitgevoerd), maar dat het apparaat meer dan 30 dagen niet is ingecheckt.</span><span class="sxs-lookup"><span data-stu-id="e77fd-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="e77fd-129">In afwachting van verwijderen</span><span class="sxs-lookup"><span data-stu-id="e77fd-129">Delete pending</span></span>  <br/> |<span data-ttu-id="e77fd-130">Het verwijderen is in behandeling.</span><span class="sxs-lookup"><span data-stu-id="e77fd-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="e77fd-131">Gedetecteerd</span><span class="sxs-lookup"><span data-stu-id="e77fd-131">Discovered</span></span>  <br/> |<span data-ttu-id="e77fd-132">Microsoft 365 Business heeft het apparaat gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="e77fd-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
