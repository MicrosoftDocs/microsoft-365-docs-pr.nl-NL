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
ms.openlocfilehash: fad3dd64c9acf079bd8da778d417240c44031569
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772439"
---
# <a name="streaming-api"></a>Streaming-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Stream Advanced Hunting-gebeurtenissen naar Event Hubs en/of Azure-opslagaccount.

Microsoft 365 Defender ondersteunt het streamen van alle gebeurtenissen die beschikbaar zijn via [Advanced Hunting](../defender/advanced-hunting-overview.md) naar een [Event Hubs](/azure/event-hubs/) en/of [Azure-opslagaccount.](/azure/event-hubs/)



## <a name="in-this-section"></a>In deze sectie

Onderwerp | Omschrijving
:---|:---
[Gebeurtenissen streamen naar Azure Event Hubs](streaming-api-event-hub.md)| Meer informatie over het inschakelen van de streaming-API in uw tenant en het configureren Microsoft 365 Defender om [Advanced Hunting](../defender/advanced-hunting-overview.md) te streamen naar Event Hubs.
[Gebeurtenissen streamen naar uw Azure-opslagaccount](streaming-api-storage.md)| Meer informatie over het inschakelen van de streaming-API in uw tenant en het configureren Microsoft 365 Defender om [Advanced Hunting](advanced-hunting-overview.md) te streamen naar uw Azure-opslagaccount.


## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd jagen](../defender/advanced-hunting-overview.md)
- [Documentatie van Azure Event Hubs](/azure/event-hubs/)
- [Azure Storage Accountdocumentatie](/azure/storage/common/storage-account-overview)
