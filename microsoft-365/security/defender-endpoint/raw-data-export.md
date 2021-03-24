---
title: Microsoft Defender voor endpoint-gebeurtenis streamen
description: Meer informatie over het configureren van Microsoft Defender ATP voor het streamen van geavanceerde huntinggebeurtenissen naar Event Hubs of Een Azure-opslagaccount
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
ms.openlocfilehash: 22f4e4c974b60e291273eb9bebfa34583f4e2fb7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058185"
---
# <a name="raw-data-streaming-api"></a><span data-ttu-id="26b44-104">Raw Data Streaming API</span><span class="sxs-lookup"><span data-stu-id="26b44-104">Raw Data Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="26b44-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="26b44-105">**Applies to:**</span></span>
- [<span data-ttu-id="26b44-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="26b44-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="26b44-107">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="26b44-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="26b44-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="26b44-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="26b44-109">Stream Advanced Hunting-gebeurtenissen naar Event Hubs en/of Azure-opslagaccount.</span><span class="sxs-lookup"><span data-stu-id="26b44-109">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="26b44-110">Defender for Endpoint ondersteunt het streamen van alle gebeurtenissen die beschikbaar zijn via [Advanced Hunting](advanced-hunting-overview.md) naar een [Event Hubs](https://docs.microsoft.com/azure/event-hubs/) en/of [Azure-opslagaccount.](https://docs.microsoft.com/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="26b44-110">Defender for Endpoint supports streaming all the events available through [Advanced Hunting](advanced-hunting-overview.md) to an [Event Hubs](https://docs.microsoft.com/azure/event-hubs/) and/or [Azure storage account](https://docs.microsoft.com/azure/event-hubs/).</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a><span data-ttu-id="26b44-111">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="26b44-111">In this section</span></span>

<span data-ttu-id="26b44-112">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="26b44-112">Topic</span></span> | <span data-ttu-id="26b44-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="26b44-113">Description</span></span>
:---|:---
[<span data-ttu-id="26b44-114">Microsoft Defender voor eindpuntgebeurtenissen streamen naar Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="26b44-114">Stream Microsoft Defender for Endpoint events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="26b44-115">Meer informatie over het inschakelen van de streaming-API in uw tenant en het configureren van Defender voor Eindpunt om [Advanced Hunting te](advanced-hunting-overview.md) streamen naar Event Hubs.</span><span class="sxs-lookup"><span data-stu-id="26b44-115">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="26b44-116">Stream Defender voor eindpuntgebeurtenissen naar uw Azure-opslagaccount</span><span class="sxs-lookup"><span data-stu-id="26b44-116">Stream Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="26b44-117">Meer informatie over het inschakelen van de streaming-API in uw tenant en het configureren van Defender voor Eindpunt om [Advanced Hunting](advanced-hunting-overview.md) te streamen naar uw Azure-opslagaccount.</span><span class="sxs-lookup"><span data-stu-id="26b44-117">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="26b44-118">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="26b44-118">Related topics</span></span>
- [<span data-ttu-id="26b44-119">Overzicht van geavanceerd jagen</span><span class="sxs-lookup"><span data-stu-id="26b44-119">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="26b44-120">Documentatie van Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="26b44-120">Azure Event Hubs documentation</span></span>](https://docs.microsoft.com/azure/event-hubs/)
- [<span data-ttu-id="26b44-121">Documentatie over Azure Storage-account</span><span class="sxs-lookup"><span data-stu-id="26b44-121">Azure Storage Account documentation</span></span>](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
