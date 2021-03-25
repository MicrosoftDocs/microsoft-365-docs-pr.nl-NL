---
title: Scoremethoden en -eigenschappen
description: Haalt de blootstellingsscore van uw organisatie, de veilige apparaatscore en de blootstellingsscore per apparaatgroep op
keywords: api's, graph api, ondersteunde api's, score, blootstellingsscore, veilige apparaatscore, blootstellingsscore per apparaatgroep
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 72dacca8529b54b082590d911f03aaa86bfe9097
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200159"
---
# <a name="score-resource-type"></a><span data-ttu-id="fc022-104">Scoreresourcetype</span><span class="sxs-lookup"><span data-stu-id="fc022-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fc022-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="fc022-105">**Applies to:**</span></span>
- [<span data-ttu-id="fc022-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="fc022-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="fc022-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc022-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fc022-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="fc022-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fc022-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="fc022-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="fc022-110">Methoden</span><span class="sxs-lookup"><span data-stu-id="fc022-110">Methods</span></span>

<span data-ttu-id="fc022-111">Methode</span><span class="sxs-lookup"><span data-stu-id="fc022-111">Method</span></span> |<span data-ttu-id="fc022-112">Retourtype</span><span class="sxs-lookup"><span data-stu-id="fc022-112">Return Type</span></span> |<span data-ttu-id="fc022-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="fc022-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="fc022-114">Score voor blootstelling krijgen</span><span class="sxs-lookup"><span data-stu-id="fc022-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="fc022-115">Score</span><span class="sxs-lookup"><span data-stu-id="fc022-115">Score</span></span>](score.md) | <span data-ttu-id="fc022-116">De score voor de blootstelling van de organisatie krijgen.</span><span class="sxs-lookup"><span data-stu-id="fc022-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="fc022-117">Veilige score voor apparaten krijgen</span><span class="sxs-lookup"><span data-stu-id="fc022-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="fc022-118">Score</span><span class="sxs-lookup"><span data-stu-id="fc022-118">Score</span></span>](score.md) | <span data-ttu-id="fc022-119">Haal de secure score van het organisatieapparaat.</span><span class="sxs-lookup"><span data-stu-id="fc022-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="fc022-120">Lijstblootstellingsscore per apparaatgroep</span><span class="sxs-lookup"><span data-stu-id="fc022-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="fc022-121">Score</span><span class="sxs-lookup"><span data-stu-id="fc022-121">Score</span></span>](score.md) | <span data-ttu-id="fc022-122">Lijstscores per apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="fc022-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="fc022-123">Eigenschappen</span><span class="sxs-lookup"><span data-stu-id="fc022-123">Properties</span></span>

<span data-ttu-id="fc022-124">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="fc022-124">Property</span></span> |  <span data-ttu-id="fc022-125">Type</span><span class="sxs-lookup"><span data-stu-id="fc022-125">Type</span></span>    |   <span data-ttu-id="fc022-126">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="fc022-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="fc022-127">Score</span><span class="sxs-lookup"><span data-stu-id="fc022-127">Score</span></span> | <span data-ttu-id="fc022-128">Dubbel</span><span class="sxs-lookup"><span data-stu-id="fc022-128">Double</span></span> | <span data-ttu-id="fc022-129">De huidige score.</span><span class="sxs-lookup"><span data-stu-id="fc022-129">The current score.</span></span>
<span data-ttu-id="fc022-130">Tijd</span><span class="sxs-lookup"><span data-stu-id="fc022-130">Time</span></span> | <span data-ttu-id="fc022-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="fc022-131">DateTime</span></span> | <span data-ttu-id="fc022-132">De datum en tijd waarin de oproep voor deze API is gedaan.</span><span class="sxs-lookup"><span data-stu-id="fc022-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="fc022-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="fc022-133">RbacGroupName</span></span> | <span data-ttu-id="fc022-134">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="fc022-134">String</span></span> | <span data-ttu-id="fc022-135">De naam van de apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="fc022-135">The device group name.</span></span>
