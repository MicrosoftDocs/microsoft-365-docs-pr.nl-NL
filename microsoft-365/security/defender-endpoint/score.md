---
title: Scoringsmethoden en -eigenschappen
description: Haalt de blootstellingsscore van uw organisatie, de veilige apparaatscore en de blootstellingsscore per apparaatgroep op
keywords: api's, graph api, ondersteunde api's, score, blootstellingsscore, veilige apparaatscore, blootstellingsscore per apparaatgroep
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 89012dce4aa5b74d09f071b23f7709b4bd0bf03c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771427"
---
# <a name="score-resource-type"></a><span data-ttu-id="2f640-104">Scoreresourcetype</span><span class="sxs-lookup"><span data-stu-id="2f640-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2f640-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2f640-105">**Applies to:**</span></span>
- [<span data-ttu-id="2f640-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="2f640-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="2f640-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f640-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2f640-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="2f640-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2f640-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="2f640-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="2f640-110">Methoden</span><span class="sxs-lookup"><span data-stu-id="2f640-110">Methods</span></span>

<span data-ttu-id="2f640-111">Methode</span><span class="sxs-lookup"><span data-stu-id="2f640-111">Method</span></span> |<span data-ttu-id="2f640-112">Retourtype</span><span class="sxs-lookup"><span data-stu-id="2f640-112">Return Type</span></span> |<span data-ttu-id="2f640-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="2f640-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="2f640-114">Blootstellingsscore ophalen</span><span class="sxs-lookup"><span data-stu-id="2f640-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="2f640-115">Score</span><span class="sxs-lookup"><span data-stu-id="2f640-115">Score</span></span>](score.md) | <span data-ttu-id="2f640-116">De score voor de blootstelling van de organisatie krijgen.</span><span class="sxs-lookup"><span data-stu-id="2f640-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="2f640-117">Secure Score voor apparaten ophalen</span><span class="sxs-lookup"><span data-stu-id="2f640-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="2f640-118">Score</span><span class="sxs-lookup"><span data-stu-id="2f640-118">Score</span></span>](score.md) | <span data-ttu-id="2f640-119">Haal de secure score van het organisatieapparaat.</span><span class="sxs-lookup"><span data-stu-id="2f640-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="2f640-120">Lijstblootstellingsscore per apparaatgroep</span><span class="sxs-lookup"><span data-stu-id="2f640-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="2f640-121">Score</span><span class="sxs-lookup"><span data-stu-id="2f640-121">Score</span></span>](score.md) | <span data-ttu-id="2f640-122">Lijstscores per apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="2f640-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="2f640-123">Eigenschappen</span><span class="sxs-lookup"><span data-stu-id="2f640-123">Properties</span></span>

<span data-ttu-id="2f640-124">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="2f640-124">Property</span></span> |  <span data-ttu-id="2f640-125">Type</span><span class="sxs-lookup"><span data-stu-id="2f640-125">Type</span></span>    |   <span data-ttu-id="2f640-126">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="2f640-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="2f640-127">Score</span><span class="sxs-lookup"><span data-stu-id="2f640-127">Score</span></span> | <span data-ttu-id="2f640-128">Dubbel</span><span class="sxs-lookup"><span data-stu-id="2f640-128">Double</span></span> | <span data-ttu-id="2f640-129">De huidige score.</span><span class="sxs-lookup"><span data-stu-id="2f640-129">The current score.</span></span>
<span data-ttu-id="2f640-130">Tijd</span><span class="sxs-lookup"><span data-stu-id="2f640-130">Time</span></span> | <span data-ttu-id="2f640-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="2f640-131">DateTime</span></span> | <span data-ttu-id="2f640-132">De datum en tijd waarin de oproep voor deze API is gedaan.</span><span class="sxs-lookup"><span data-stu-id="2f640-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="2f640-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="2f640-133">RbacGroupName</span></span> | <span data-ttu-id="2f640-134">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2f640-134">String</span></span> | <span data-ttu-id="2f640-135">De naam van de apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="2f640-135">The device group name.</span></span>
