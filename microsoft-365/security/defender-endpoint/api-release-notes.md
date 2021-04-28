---
title: Releasenotities van Microsoft Defender for Endpoint API
description: Releasenotities voor updates die zijn aangebracht in de Microsoft Defender for Endpoint-set API's.
keywords: Microsoft Defender for Endpoint API release notes, mde, API's, Microsoft Defender for Endpoint API, updates, notes, release
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5093bf64614f30c7daa145484453d7c9000ef2c7
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2021
ms.locfileid: "52060883"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="bc821-104">Releasenotities van Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="bc821-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="bc821-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="bc821-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="bc821-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="bc821-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bc821-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="bc821-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="bc821-108">De volgende informatie bevat de updates die zijn aangebracht aan de API's van Microsoft Defender voor eindpunten en de datums waarop ze zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="bc821-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>

> [!TIP]
> <span data-ttu-id="bc821-109">RSS-feed: Ontvang een melding wanneer deze pagina wordt bijgewerkt door de volgende URL in uw feedlezer te kopiëren en te kopiëren:</span><span class="sxs-lookup"><span data-stu-id="bc821-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
>
> ```http
> https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```


## <a name="release-notes---newest-to-oldest"></a><span data-ttu-id="bc821-110">Releasenotities - nieuwste naar oudste</span><span class="sxs-lookup"><span data-stu-id="bc821-110">Release notes - newest to oldest</span></span>

### <a name="23042021"></a><span data-ttu-id="bc821-111">23.04.2021</span><span class="sxs-lookup"><span data-stu-id="bc821-111">23.04.2021</span></span>

- <span data-ttu-id="bc821-112">Nieuwe API toegevoegd: [herstelactiviteitsmethoden en -eigenschappen](get-remediation-methods-properties.md).</span><span class="sxs-lookup"><span data-stu-id="bc821-112">Added new API: [Remediation activity methods and properties](get-remediation-methods-properties.md).</span></span>

### <a name="10022021"></a><span data-ttu-id="bc821-113">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="bc821-113">10.02.2021</span></span>

- <span data-ttu-id="bc821-114">Nieuwe API toegevoegd: [waarschuwingen voor batchupdates.](batch-update-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="bc821-114">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span>

### <a name="25012021"></a><span data-ttu-id="bc821-115">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="bc821-115">25.01.2021</span></span>

- <span data-ttu-id="bc821-116">Bijgewerkte tariefbeperkingen voor [Advanced Hunting API](run-advanced-query-api.md) van 15 tot 45 aanvragen per minuut.</span><span class="sxs-lookup"><span data-stu-id="bc821-116">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span>

### <a name="21012021"></a><span data-ttu-id="bc821-117">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="bc821-117">21.01.2021</span></span>

- <span data-ttu-id="bc821-118">Nieuwe API toegevoegd: [Apparaten zoeken op tag](machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="bc821-118">Added new API: [Find devices by tag](machine-tags.md).</span></span>
- <span data-ttu-id="bc821-119">Nieuwe API toegevoegd: [importindicatoren](import-ti-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="bc821-119">Added new API: [Import Indicators](import-ti-indicators.md).</span></span>

### <a name="03012021"></a><span data-ttu-id="bc821-120">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="bc821-120">03.01.2021</span></span>

- <span data-ttu-id="bc821-121">Bijgewerkte waarschuwingen: toegevoegde eigenschappen ***detectieStatus** _, _*_bovenliggendeProcessFilePath_*_ en _ *_parentProcessFileName_** .</span><span class="sxs-lookup"><span data-stu-id="bc821-121">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="bc821-122">Bijgewerkte [waarschuwingsentiteit:](alerts.md) ***eigenschap melderid*** toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="bc821-122">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

### <a name="15122020"></a><span data-ttu-id="bc821-123">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="bc821-123">15.12.2020</span></span>

- <span data-ttu-id="bc821-124">Bijgewerkte apparaatentiteit: ***lijst met IpInterfaces*** toegevoegd. [](machine.md)</span><span class="sxs-lookup"><span data-stu-id="bc821-124">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="bc821-125">Zie [Lijstapparaten](get-machines.md).</span><span class="sxs-lookup"><span data-stu-id="bc821-125">See [List devices](get-machines.md).</span></span>

### <a name="04112020"></a><span data-ttu-id="bc821-126">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="bc821-126">04.11.2020</span></span>

- <span data-ttu-id="bc821-127">Nieuwe API toegevoegd: [apparaatwaarde instellen.](set-device-value.md)</span><span class="sxs-lookup"><span data-stu-id="bc821-127">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="bc821-128">Bijgewerkte apparaatentiteit: ***eigenschap apparaatwaarde*** toegevoegd. [](machine.md)</span><span class="sxs-lookup"><span data-stu-id="bc821-128">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

### <a name="01092020"></a><span data-ttu-id="bc821-129">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="bc821-129">01.09.2020</span></span>

- <span data-ttu-id="bc821-130">De optie Toegevoegd om de entiteit Waarschuwing uit te vouwen met het bijbehorende bewijs.</span><span class="sxs-lookup"><span data-stu-id="bc821-130">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="bc821-131">Zie [Lijstwaarschuwingen](get-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="bc821-131">See [List Alerts](get-alerts.md).</span></span>
