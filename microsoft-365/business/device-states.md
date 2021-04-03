---
title: Statuswaarden voor apparaten
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Meer informatie over de verschillende apparaatstaten in de lijst Apparaatacties in Beheerhuis in Microsoft 365 voor Bedrijven.
ms.openlocfilehash: e6f1b428413d094e0a1ce3afb026528074038736
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578462"
---
# <a name="device-states"></a><span data-ttu-id="3bbba-103">Apparaatstatussen</span><span class="sxs-lookup"><span data-stu-id="3bbba-103">Device states</span></span>

<span data-ttu-id="3bbba-104">Dit artikel is van toepassing op Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="3bbba-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="3bbba-105">Apparaten in de lijst **Apparaatacties** lijst (startpagina beheerders \> **Apparaatacties**) kunnen de volgende statuswaarden hebben.</span><span class="sxs-lookup"><span data-stu-id="3bbba-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="3bbba-107">**Status**</span><span class="sxs-lookup"><span data-stu-id="3bbba-107">**Status**</span></span>|<span data-ttu-id="3bbba-108">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="3bbba-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3bbba-109">Beheerd door Intune</span><span class="sxs-lookup"><span data-stu-id="3bbba-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="3bbba-110">Beheerd door Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="3bbba-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="3bbba-111">In afwachting van buiten gebruik stellen</span><span class="sxs-lookup"><span data-stu-id="3bbba-111">Retire pending</span></span>  <br/> |<span data-ttu-id="3bbba-112">Microsoft 365 Business Premium maakt zich klaar om bedrijfsgegevens van het apparaat te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3bbba-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="3bbba-113">Buitengebruikstelling wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="3bbba-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="3bbba-114">Microsoft 365 Business Premium verwijdert momenteel bedrijfsgegevens van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="3bbba-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="3bbba-115">Buiten gebruik stellen is mislukt</span><span class="sxs-lookup"><span data-stu-id="3bbba-115">Retire failed</span></span>  <br/> | <span data-ttu-id="3bbba-116">Het verwijderen van bedrijfsgegevens is mislukt.</span><span class="sxs-lookup"><span data-stu-id="3bbba-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="3bbba-117">Met pensioen gaan geannuleerd</span><span class="sxs-lookup"><span data-stu-id="3bbba-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="3bbba-118">De actie Voor het terug trekken is geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="3bbba-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="3bbba-119">Wissen in behandeling</span><span class="sxs-lookup"><span data-stu-id="3bbba-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="3bbba-120">Wachten tot de fabrieksinstellingen opnieuw worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="3bbba-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="3bbba-121">Wissen wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="3bbba-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="3bbba-122">De fabrieksinstellingen worden opnieuw ingesteld.</span><span class="sxs-lookup"><span data-stu-id="3bbba-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="3bbba-123">Wissen is mislukt</span><span class="sxs-lookup"><span data-stu-id="3bbba-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="3bbba-124">Het is niet mogelijk om de fabriek opnieuw in te stellen.</span><span class="sxs-lookup"><span data-stu-id="3bbba-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="3bbba-125">Geannuleerd wissen</span><span class="sxs-lookup"><span data-stu-id="3bbba-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="3bbba-126">Fabrieks wissen is geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="3bbba-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="3bbba-127">Niet in orde</span><span class="sxs-lookup"><span data-stu-id="3bbba-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="3bbba-128">Een actie is in behandeling (of wordt uitgevoerd), maar het apparaat is al meer dan 30 dagen niet ingecheckt.</span><span class="sxs-lookup"><span data-stu-id="3bbba-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="3bbba-129">In afwachting van verwijderen</span><span class="sxs-lookup"><span data-stu-id="3bbba-129">Delete pending</span></span>  <br/> |<span data-ttu-id="3bbba-130">Het verwijderen is in behandeling.</span><span class="sxs-lookup"><span data-stu-id="3bbba-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="3bbba-131">Gedetecteerd</span><span class="sxs-lookup"><span data-stu-id="3bbba-131">Discovered</span></span>  <br/> |<span data-ttu-id="3bbba-132">Microsoft 365 Business Premium heeft het apparaat gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="3bbba-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
