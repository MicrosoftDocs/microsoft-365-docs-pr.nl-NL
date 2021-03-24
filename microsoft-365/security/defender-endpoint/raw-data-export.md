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
# <a name="raw-data-streaming-api"></a>Raw Data Streaming API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Stream Advanced Hunting-gebeurtenissen naar Event Hubs en/of Azure-opslagaccount.

Defender for Endpoint ondersteunt het streamen van alle gebeurtenissen die beschikbaar zijn via [Advanced Hunting](advanced-hunting-overview.md) naar een [Event Hubs](https://docs.microsoft.com/azure/event-hubs/) en/of [Azure-opslagaccount.](https://docs.microsoft.com/azure/event-hubs/)

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a>In deze sectie

Onderwerp | Beschrijving
:---|:---
[Microsoft Defender voor eindpuntgebeurtenissen streamen naar Azure Event Hubs](raw-data-export-event-hub.md)| Meer informatie over het inschakelen van de streaming-API in uw tenant en het configureren van Defender voor Eindpunt om [Advanced Hunting te](advanced-hunting-overview.md) streamen naar Event Hubs.
[Stream Defender voor eindpuntgebeurtenissen naar uw Azure-opslagaccount](raw-data-export-storage.md)| Meer informatie over het inschakelen van de streaming-API in uw tenant en het configureren van Defender voor Eindpunt om [Advanced Hunting](advanced-hunting-overview.md) te streamen naar uw Azure-opslagaccount.


## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd jagen](advanced-hunting-overview.md)
- [Documentatie van Azure Event Hubs](https://docs.microsoft.com/azure/event-hubs/)
- [Documentatie over Azure Storage-account](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
