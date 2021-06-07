---
title: Gebeurtenissen Microsoft 365 Defender streamen
description: Meer informatie over het configureren Microsoft 365 Defender voor het streamen van Advanced Hunting-gebeurtenissen naar Event Hubs of Azure-opslagaccount
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
ms.openlocfilehash: 971cc757dcbd0a190917d2a5f11eb7f68b758008
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778195"
---
# <a name="streaming-api"></a><span data-ttu-id="3d435-104">Streaming-API</span><span class="sxs-lookup"><span data-stu-id="3d435-104">Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3d435-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="3d435-105">**Applies to:**</span></span>
- [<span data-ttu-id="3d435-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3d435-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="3d435-107">Stream Advanced Hunting-gebeurtenissen naar Event Hubs en/of Azure-opslagaccount.</span><span class="sxs-lookup"><span data-stu-id="3d435-107">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="3d435-108">Microsoft 365 Defender ondersteunt het streamen van alle gebeurtenissen die beschikbaar zijn via [Advanced Hunting](../defender/advanced-hunting-overview.md) naar een [Event Hubs](/azure/event-hubs/) en/of [Azure-opslagaccount.](/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="3d435-108">Microsoft 365 Defender supports streaming all the events available through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>



## <a name="in-this-section"></a><span data-ttu-id="3d435-109">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="3d435-109">In this section</span></span>

<span data-ttu-id="3d435-110">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="3d435-110">Topic</span></span> | <span data-ttu-id="3d435-111">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="3d435-111">Description</span></span>
:---|:---
[<span data-ttu-id="3d435-112">Gebeurtenissen streamen naar Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="3d435-112">Stream events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="3d435-113">Meer informatie over het inschakelen van de streaming-API in uw tenant en het configureren Microsoft 365 Defender om [Advanced Hunting](../defender/advanced-hunting-overview.md) te streamen naar Event Hubs.</span><span class="sxs-lookup"><span data-stu-id="3d435-113">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="3d435-114">Gebeurtenissen streamen naar uw Azure-opslagaccount</span><span class="sxs-lookup"><span data-stu-id="3d435-114">Stream events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="3d435-115">Meer informatie over het inschakelen van de streaming-API in uw tenant en het configureren Microsoft 365 Defender om [Advanced Hunting](../defender/advanced-hunting-overview.md) te streamen naar uw Azure-opslagaccount.</span><span class="sxs-lookup"><span data-stu-id="3d435-115">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="3d435-116">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="3d435-116">Related topics</span></span>
- [<span data-ttu-id="3d435-117">Overzicht van geavanceerd jagen</span><span class="sxs-lookup"><span data-stu-id="3d435-117">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="3d435-118">Documentatie van Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="3d435-118">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="3d435-119">Azure Storage Accountdocumentatie</span><span class="sxs-lookup"><span data-stu-id="3d435-119">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
