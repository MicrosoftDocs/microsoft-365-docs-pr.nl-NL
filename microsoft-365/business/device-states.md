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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Meer informatie over de verschillende apparaattoestanden in de lijst Met apparaatacties in Het beheerhome in Microsoft 365 voor bedrijven.
ms.openlocfilehash: 64138e2b6ae73c067709cde1912a96615d08ebf1
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471174"
---
# <a name="device-states"></a><span data-ttu-id="be161-103">Apparaatstatussen</span><span class="sxs-lookup"><span data-stu-id="be161-103">Device states</span></span>

<span data-ttu-id="be161-104">Dit artikel is van toepassing op Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="be161-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="be161-105">Apparaten in de lijst **Apparaatacties** lijst (startpagina beheerders \> **Apparaatacties**) kunnen de volgende statuswaarden hebben.</span><span class="sxs-lookup"><span data-stu-id="be161-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="be161-107">**Status**</span><span class="sxs-lookup"><span data-stu-id="be161-107">**Status**</span></span>|<span data-ttu-id="be161-108">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="be161-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="be161-109">Beheerd door Intune</span><span class="sxs-lookup"><span data-stu-id="be161-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="be161-110">Beheerd door Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="be161-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="be161-111">In afwachting van buiten gebruik stellen</span><span class="sxs-lookup"><span data-stu-id="be161-111">Retire pending</span></span>  <br/> |<span data-ttu-id="be161-112">Microsoft 365 Business Premium maakt zich klaar om bedrijfsgegevens van het apparaat te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="be161-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="be161-113">Buitengebruikstelling wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="be161-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="be161-114">Microsoft 365 Business Premium verwijdert momenteel bedrijfsgegevens van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="be161-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="be161-115">Buiten gebruik stellen is mislukt</span><span class="sxs-lookup"><span data-stu-id="be161-115">Retire failed</span></span>  <br/> | <span data-ttu-id="be161-116">Het verwijderen van bedrijfsgegevens is mislukt.</span><span class="sxs-lookup"><span data-stu-id="be161-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="be161-117">Met pensioen geannuleerd</span><span class="sxs-lookup"><span data-stu-id="be161-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="be161-118">De actie Met pensioen is geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="be161-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="be161-119">Wissen in behandeling</span><span class="sxs-lookup"><span data-stu-id="be161-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="be161-120">Wachten tot de fabrieksinstellingen opnieuw worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="be161-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="be161-121">Wissen wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="be161-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="be161-122">De fabrieksinstellingen worden opnieuw ingesteld.</span><span class="sxs-lookup"><span data-stu-id="be161-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="be161-123">Wissen is mislukt</span><span class="sxs-lookup"><span data-stu-id="be161-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="be161-124">Kon niet doen fabriek resetten.</span><span class="sxs-lookup"><span data-stu-id="be161-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="be161-125">Veeg geannuleerd</span><span class="sxs-lookup"><span data-stu-id="be161-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="be161-126">Het afvegen van de fabriek is geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="be161-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="be161-127">Niet in orde</span><span class="sxs-lookup"><span data-stu-id="be161-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="be161-128">Er is een actie in behandeling (of wordt uitgevoerd), maar het apparaat heeft zich al meer dan 30 dagen niet ingecheckt.</span><span class="sxs-lookup"><span data-stu-id="be161-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="be161-129">In afwachting van verwijderen</span><span class="sxs-lookup"><span data-stu-id="be161-129">Delete pending</span></span>  <br/> |<span data-ttu-id="be161-130">Het verwijderen is in behandeling.</span><span class="sxs-lookup"><span data-stu-id="be161-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="be161-131">Gedetecteerd</span><span class="sxs-lookup"><span data-stu-id="be161-131">Discovered</span></span>  <br/> |<span data-ttu-id="be161-132">Microsoft 365 Business Premium heeft het apparaat gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="be161-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
