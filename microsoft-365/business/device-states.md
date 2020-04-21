---
title: Statuswaarden voor apparaten
f1.keywords:
- NOCSH
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
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Meer informatie over de verschillende apparaatstatussen in de lijst Apparaatacties in Beheerhuis in Microsoft 365 voor Bedrijven.
ms.openlocfilehash: 1a66e76dd3a74428923292427b01551db2449e48
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627241"
---
# <a name="device-states"></a><span data-ttu-id="568e1-103">Apparaatstatussen</span><span class="sxs-lookup"><span data-stu-id="568e1-103">Device states</span></span>

<span data-ttu-id="568e1-104">Apparaten in de lijst **Apparaatacties** lijst (startpagina beheerders \> **Apparaatacties**) kunnen de volgende statuswaarden hebben.</span><span class="sxs-lookup"><span data-stu-id="568e1-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="568e1-106">**Status**</span><span class="sxs-lookup"><span data-stu-id="568e1-106">**Status**</span></span>|<span data-ttu-id="568e1-107">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="568e1-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="568e1-108">Beheerd door Intune</span><span class="sxs-lookup"><span data-stu-id="568e1-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="568e1-109">Beheerd door Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="568e1-109">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="568e1-110">In afwachting van buiten gebruik stellen</span><span class="sxs-lookup"><span data-stu-id="568e1-110">Retire pending</span></span>  <br/> |<span data-ttu-id="568e1-111">Microsoft 365 Business Premium maakt zich klaar om bedrijfsgegevens van het apparaat te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="568e1-111">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="568e1-112">Buitengebruikstelling wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="568e1-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="568e1-113">Microsoft 365 Business Premium verwijdert momenteel bedrijfsgegevens van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="568e1-113">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="568e1-114">Buiten gebruik stellen is mislukt</span><span class="sxs-lookup"><span data-stu-id="568e1-114">Retire failed</span></span>  <br/> | <span data-ttu-id="568e1-115">Het verwijderen van bedrijfsgegevens is mislukt.</span><span class="sxs-lookup"><span data-stu-id="568e1-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="568e1-116">Pensioen geannuleerd</span><span class="sxs-lookup"><span data-stu-id="568e1-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="568e1-117">De actie met pensioen gaan is geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="568e1-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="568e1-118">Wissen in behandeling</span><span class="sxs-lookup"><span data-stu-id="568e1-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="568e1-119">Wachten tot de fabrieksinstellingen opnieuw worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="568e1-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="568e1-120">Wissen wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="568e1-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="568e1-121">De fabrieksinstellingen worden opnieuw ingesteld.</span><span class="sxs-lookup"><span data-stu-id="568e1-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="568e1-122">Wissen is mislukt</span><span class="sxs-lookup"><span data-stu-id="568e1-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="568e1-123">Ik kon de fabrieksreset niet doen.</span><span class="sxs-lookup"><span data-stu-id="568e1-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="568e1-124">Wipe geannuleerd</span><span class="sxs-lookup"><span data-stu-id="568e1-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="568e1-125">Factory wipe werd geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="568e1-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="568e1-126">Niet in orde</span><span class="sxs-lookup"><span data-stu-id="568e1-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="568e1-127">Er is een actie in behandeling (of in uitvoering), maar het apparaat heeft al meer dan 30 dagen niet ingecheckt.</span><span class="sxs-lookup"><span data-stu-id="568e1-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="568e1-128">In afwachting van verwijderen</span><span class="sxs-lookup"><span data-stu-id="568e1-128">Delete pending</span></span>  <br/> |<span data-ttu-id="568e1-129">Het verwijderen is in behandeling.</span><span class="sxs-lookup"><span data-stu-id="568e1-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="568e1-130">Gedetecteerd</span><span class="sxs-lookup"><span data-stu-id="568e1-130">Discovered</span></span>  <br/> |<span data-ttu-id="568e1-131">Microsoft 365 Business Premium heeft het apparaat gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="568e1-131">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
