---
title: Statuswaarden voor apparaten
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
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
description: Meer informatie over apparaatstatussen in Microsoft 365 Business.
ms.openlocfilehash: b55e6a5d538ec28d195225e93797cea27afd2e8b
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/14/2019
ms.locfileid: "38320203"
---
# <a name="device-states"></a><span data-ttu-id="9f918-103">Statuswaarden voor apparaten</span><span class="sxs-lookup"><span data-stu-id="9f918-103">Device states</span></span>

<span data-ttu-id="9f918-104">Apparaten in de lijst **Apparaatacties** lijst (startpagina beheerders \> **Apparaatacties**) kunnen de volgende statuswaarden hebben.</span><span class="sxs-lookup"><span data-stu-id="9f918-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="9f918-106">**Status**</span><span class="sxs-lookup"><span data-stu-id="9f918-106">**Status**</span></span>|<span data-ttu-id="9f918-107">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="9f918-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9f918-108">Beheerd door Intune</span><span class="sxs-lookup"><span data-stu-id="9f918-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="9f918-109">Beheerd door Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="9f918-109">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="9f918-110">In afwachting van buiten gebruik stellen</span><span class="sxs-lookup"><span data-stu-id="9f918-110">Retire pending</span></span>  <br/> |<span data-ttu-id="9f918-111">Microsoft 365 Business is bezig met de voorbereiding om bedrijfsgegevens van het apparaat te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9f918-111">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="9f918-112">Buitengebruikstelling wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="9f918-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="9f918-113">Microsoft 365 Business verwijdert momenteel bedrijfsgegevens van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="9f918-113">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="9f918-114">Buiten gebruik stellen is mislukt</span><span class="sxs-lookup"><span data-stu-id="9f918-114">Retire failed</span></span>  <br/> | <span data-ttu-id="9f918-115">Het verwijderen van bedrijfsgegevens is mislukt.</span><span class="sxs-lookup"><span data-stu-id="9f918-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="9f918-116">Geannuleerd intrekken</span><span class="sxs-lookup"><span data-stu-id="9f918-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="9f918-117">Actie intrekken is geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="9f918-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="9f918-118">Wissen in behandeling</span><span class="sxs-lookup"><span data-stu-id="9f918-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="9f918-119">Wachten tot de fabrieksinstellingen opnieuw worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="9f918-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="9f918-120">Wissen wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="9f918-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="9f918-121">De fabrieksinstellingen worden opnieuw ingesteld.</span><span class="sxs-lookup"><span data-stu-id="9f918-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="9f918-122">Wissen is mislukt</span><span class="sxs-lookup"><span data-stu-id="9f918-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="9f918-123">Kon niet Factory Reset doen.</span><span class="sxs-lookup"><span data-stu-id="9f918-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="9f918-124">Wissen geannuleerd</span><span class="sxs-lookup"><span data-stu-id="9f918-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="9f918-125">Fabrieksinstelling wissen is geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="9f918-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="9f918-126">Niet in orde</span><span class="sxs-lookup"><span data-stu-id="9f918-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="9f918-127">Een actie is in behandeling (of wordt uitgevoerd), maar het apparaat is niet ingecheckt voor 30 + dagen.</span><span class="sxs-lookup"><span data-stu-id="9f918-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="9f918-128">In afwachting van verwijderen</span><span class="sxs-lookup"><span data-stu-id="9f918-128">Delete pending</span></span>  <br/> |<span data-ttu-id="9f918-129">Het verwijderen is in behandeling.</span><span class="sxs-lookup"><span data-stu-id="9f918-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="9f918-130">Gedetecteerd</span><span class="sxs-lookup"><span data-stu-id="9f918-130">Discovered</span></span>  <br/> |<span data-ttu-id="9f918-131">Microsoft 365 Business heeft het apparaat gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="9f918-131">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
