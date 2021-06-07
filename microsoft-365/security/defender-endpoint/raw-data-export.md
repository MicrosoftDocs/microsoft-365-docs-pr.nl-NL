---
title: Microsoft Defender voor endpoint-gebeurtenis streamen
description: Meer informatie over het configureren van Microsoft Defender voor Eindpunt voor het streamen van Advanced Hunting-gebeurtenissen naar Event Hubs of Een Azure-opslagaccount
keywords: raw data export, streaming API, API, Event hubs, Azure storage, storage account, Advanced Hunting, raw data sharing
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.custom: api
ms.openlocfilehash: c8403dee11070dcf0825fad2502d8d21d54933fd
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782751"
---
# <a name="raw-data-streaming-api"></a><span data-ttu-id="03131-104">Raw Data Streaming API</span><span class="sxs-lookup"><span data-stu-id="03131-104">Raw Data Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="03131-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="03131-105">**Applies to:**</span></span>
- [<span data-ttu-id="03131-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="03131-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="03131-107">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="03131-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="03131-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="03131-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="03131-109">Stream Advanced Hunting-gebeurtenissen naar Event Hubs en/of Azure-opslagaccount.</span><span class="sxs-lookup"><span data-stu-id="03131-109">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>


<span data-ttu-id="03131-110">Microsoft Defender voor Eindpunt ondersteunt streaminggebeurtenissen die beschikbaar zijn via [Advanced Hunting](../defender/advanced-hunting-overview.md) naar een [Event Hubs](/azure/event-hubs/) en/of [Azure-opslagaccount.](/azure/storage/common/storage-account-overview)</span><span class="sxs-lookup"><span data-stu-id="03131-110">Microsoft Defender for Endpoint supports streaming events available through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/storage/common/storage-account-overview).</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a><span data-ttu-id="03131-111">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="03131-111">In this section</span></span>

<span data-ttu-id="03131-112">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="03131-112">Topic</span></span> | <span data-ttu-id="03131-113">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="03131-113">Description</span></span>
:---|:---
[<span data-ttu-id="03131-114">Microsoft Defender voor eindpuntgebeurtenissen streamen naar Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="03131-114">Stream Microsoft Defender for Endpoint events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="03131-115">Meer informatie over het inschakelen van de streaming-API in uw tenant en het configureren van Defender voor Eindpunt om [Advanced Hunting te](advanced-hunting-overview.md) streamen naar Event Hubs.</span><span class="sxs-lookup"><span data-stu-id="03131-115">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="03131-116">Stream Defender voor eindpuntgebeurtenissen naar uw Azure-opslagaccount</span><span class="sxs-lookup"><span data-stu-id="03131-116">Stream Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="03131-117">Meer informatie over het inschakelen van de streaming-API in uw tenant en het configureren van Defender voor Eindpunt om [Advanced Hunting](advanced-hunting-overview.md) te streamen naar uw Azure-opslagaccount.</span><span class="sxs-lookup"><span data-stu-id="03131-117">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="03131-118">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="03131-118">Related topics</span></span>
- [<span data-ttu-id="03131-119">Overzicht van geavanceerd jagen</span><span class="sxs-lookup"><span data-stu-id="03131-119">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="03131-120">Documentatie van Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="03131-120">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="03131-121">Azure Storage Accountdocumentatie</span><span class="sxs-lookup"><span data-stu-id="03131-121">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)