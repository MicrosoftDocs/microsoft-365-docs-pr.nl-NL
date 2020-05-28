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
description: Meer informatie over de verschillende apparaatstatussen in de lijst Apparaatacties in Beheerhuis in Microsoft 365 voor Bedrijven.
ms.openlocfilehash: 90c11caa03249408ba2916d303bcb4a59fbcca8c
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400949"
---
# <a name="device-states"></a><span data-ttu-id="14b13-103">Apparaatstatussen</span><span class="sxs-lookup"><span data-stu-id="14b13-103">Device states</span></span>

<span data-ttu-id="14b13-104">Apparaten in de lijst **Apparaatacties** lijst (startpagina beheerders \> **Apparaatacties**) kunnen de volgende statuswaarden hebben.</span><span class="sxs-lookup"><span data-stu-id="14b13-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="14b13-106">**Status**</span><span class="sxs-lookup"><span data-stu-id="14b13-106">**Status**</span></span>|<span data-ttu-id="14b13-107">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="14b13-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="14b13-108">Beheerd door Intune</span><span class="sxs-lookup"><span data-stu-id="14b13-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="14b13-109">Beheerd door Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="14b13-109">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="14b13-110">In afwachting van buiten gebruik stellen</span><span class="sxs-lookup"><span data-stu-id="14b13-110">Retire pending</span></span>  <br/> |<span data-ttu-id="14b13-111">Microsoft 365 Business Premium maakt zich klaar om bedrijfsgegevens van het apparaat te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="14b13-111">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="14b13-112">Buitengebruikstelling wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="14b13-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="14b13-113">Microsoft 365 Business Premium verwijdert momenteel bedrijfsgegevens van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="14b13-113">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="14b13-114">Buiten gebruik stellen is mislukt</span><span class="sxs-lookup"><span data-stu-id="14b13-114">Retire failed</span></span>  <br/> | <span data-ttu-id="14b13-115">Het verwijderen van bedrijfsgegevens is mislukt.</span><span class="sxs-lookup"><span data-stu-id="14b13-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="14b13-116">Pensioen geannuleerd</span><span class="sxs-lookup"><span data-stu-id="14b13-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="14b13-117">De actie met pensioen gaan is geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="14b13-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="14b13-118">Wissen in behandeling</span><span class="sxs-lookup"><span data-stu-id="14b13-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="14b13-119">Wachten tot de fabrieksinstellingen opnieuw worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="14b13-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="14b13-120">Wissen wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="14b13-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="14b13-121">De fabrieksinstellingen worden opnieuw ingesteld.</span><span class="sxs-lookup"><span data-stu-id="14b13-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="14b13-122">Wissen is mislukt</span><span class="sxs-lookup"><span data-stu-id="14b13-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="14b13-123">Ik kon de fabrieksreset niet doen.</span><span class="sxs-lookup"><span data-stu-id="14b13-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="14b13-124">Wipe geannuleerd</span><span class="sxs-lookup"><span data-stu-id="14b13-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="14b13-125">Factory wipe werd geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="14b13-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="14b13-126">Niet in orde</span><span class="sxs-lookup"><span data-stu-id="14b13-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="14b13-127">Er is een actie in behandeling (of in uitvoering), maar het apparaat heeft al meer dan 30 dagen niet ingecheckt.</span><span class="sxs-lookup"><span data-stu-id="14b13-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="14b13-128">In afwachting van verwijderen</span><span class="sxs-lookup"><span data-stu-id="14b13-128">Delete pending</span></span>  <br/> |<span data-ttu-id="14b13-129">Het verwijderen is in behandeling.</span><span class="sxs-lookup"><span data-stu-id="14b13-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="14b13-130">Gedetecteerd</span><span class="sxs-lookup"><span data-stu-id="14b13-130">Discovered</span></span>  <br/> |<span data-ttu-id="14b13-131">Microsoft 365 Business Premium heeft het apparaat gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="14b13-131">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
