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
description: Meer informatie over de verschillende apparaatstatussen vindt u in de lijst Apparaatacties in Beheerhuis in Microsoft 365 Business.
ms.openlocfilehash: bed1610814ca0d60adb4b4b3d0018e3e7e6d763f
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/07/2020
ms.locfileid: "42560815"
---
# <a name="device-states"></a><span data-ttu-id="a7c41-103">Statuswaarden voor apparaten</span><span class="sxs-lookup"><span data-stu-id="a7c41-103">Device states</span></span>

<span data-ttu-id="a7c41-104">Apparaten in de lijst **Apparaatacties** lijst (startpagina beheerders \> **Apparaatacties**) kunnen de volgende statuswaarden hebben.</span><span class="sxs-lookup"><span data-stu-id="a7c41-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="a7c41-106">**Status**</span><span class="sxs-lookup"><span data-stu-id="a7c41-106">**Status**</span></span>|<span data-ttu-id="a7c41-107">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="a7c41-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a7c41-108">Beheerd door Intune</span><span class="sxs-lookup"><span data-stu-id="a7c41-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="a7c41-109">Beheerd door Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="a7c41-109">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="a7c41-110">In afwachting van buiten gebruik stellen</span><span class="sxs-lookup"><span data-stu-id="a7c41-110">Retire pending</span></span>  <br/> |<span data-ttu-id="a7c41-111">Microsoft 365 Business is bezig met de voorbereiding om bedrijfsgegevens van het apparaat te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a7c41-111">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="a7c41-112">Buitengebruikstelling wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="a7c41-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="a7c41-113">Microsoft 365 Business verwijdert momenteel bedrijfsgegevens van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a7c41-113">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="a7c41-114">Buiten gebruik stellen is mislukt</span><span class="sxs-lookup"><span data-stu-id="a7c41-114">Retire failed</span></span>  <br/> | <span data-ttu-id="a7c41-115">Het verwijderen van bedrijfsgegevens is mislukt.</span><span class="sxs-lookup"><span data-stu-id="a7c41-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="a7c41-116">Met pensioen geannuleerd</span><span class="sxs-lookup"><span data-stu-id="a7c41-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="a7c41-117">De actie voor de pensionering is geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="a7c41-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="a7c41-118">Wissen in behandeling</span><span class="sxs-lookup"><span data-stu-id="a7c41-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="a7c41-119">Wachten tot de fabrieksinstellingen opnieuw worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="a7c41-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="a7c41-120">Wissen wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="a7c41-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="a7c41-121">De fabrieksinstellingen worden opnieuw ingesteld.</span><span class="sxs-lookup"><span data-stu-id="a7c41-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="a7c41-122">Wissen is mislukt</span><span class="sxs-lookup"><span data-stu-id="a7c41-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="a7c41-123">Kon niet doen fabriek resetten.</span><span class="sxs-lookup"><span data-stu-id="a7c41-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="a7c41-124">Veeg geannuleerd</span><span class="sxs-lookup"><span data-stu-id="a7c41-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="a7c41-125">Fabrieksdoek werd geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="a7c41-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="a7c41-126">Niet in orde</span><span class="sxs-lookup"><span data-stu-id="a7c41-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="a7c41-127">Er is een actie in behandeling (of in uitvoering), maar het apparaat is al meer dan 30 dagen niet ingecheckt.</span><span class="sxs-lookup"><span data-stu-id="a7c41-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="a7c41-128">In afwachting van verwijderen</span><span class="sxs-lookup"><span data-stu-id="a7c41-128">Delete pending</span></span>  <br/> |<span data-ttu-id="a7c41-129">Het verwijderen is in behandeling.</span><span class="sxs-lookup"><span data-stu-id="a7c41-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="a7c41-130">Gedetecteerd</span><span class="sxs-lookup"><span data-stu-id="a7c41-130">Discovered</span></span>  <br/> |<span data-ttu-id="a7c41-131">Microsoft 365 Business heeft het apparaat gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="a7c41-131">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
