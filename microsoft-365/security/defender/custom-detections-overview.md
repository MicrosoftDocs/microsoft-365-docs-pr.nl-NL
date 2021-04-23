---
title: Overzicht van aangepaste detecties in Microsoft 365 Defender
description: Meer informatie over hoe u geavanceerd zoeken kunt gebruiken om aangepaste detecties te maken en waarschuwingen te genereren
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, custom detections, schema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 748b3534ef1f6ca5736667fc3910bb9fa96d23ff
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952534"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="f5a04-104">Overzicht van aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="f5a04-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f5a04-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f5a04-105">**Applies to:**</span></span>
- <span data-ttu-id="f5a04-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5a04-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="f5a04-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f5a04-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="f5a04-108">Met aangepaste detecties kunt u proactief controleren op en reageren op verschillende gebeurtenissen en systeemstaten, waaronder verdachte inbreukactiviteit en verkeerd geconfigureerde eindpunten.</span><span class="sxs-lookup"><span data-stu-id="f5a04-108">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="f5a04-109">Dit wordt mogelijk gemaakt door aanpasbare detectieregels die automatisch waarschuwingen en antwoordacties activeren.</span><span class="sxs-lookup"><span data-stu-id="f5a04-109">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="f5a04-110">Aangepaste detecties werken met geavanceerde zoekprogramma's, die een krachtige, flexibele querytaal bieden die een breed scala aan gebeurtenis- en systeemgegevens van uw netwerk bestrijkt. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f5a04-110">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="f5a04-111">U kunt instellen dat ze regelmatig worden uitgevoerd, waarschuwingen genereren en antwoordacties uitvoeren wanneer er overeenkomsten zijn.</span><span class="sxs-lookup"><span data-stu-id="f5a04-111">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="f5a04-112">Aangepaste detecties bieden:</span><span class="sxs-lookup"><span data-stu-id="f5a04-112">Custom detections provide:</span></span>
- <span data-ttu-id="f5a04-113">Waarschuwingen voor op regels gebaseerde detecties die zijn gebaseerd op geavanceerde query's voor jagen</span><span class="sxs-lookup"><span data-stu-id="f5a04-113">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="f5a04-114">Automatische antwoordacties</span><span class="sxs-lookup"><span data-stu-id="f5a04-114">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="f5a04-115">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f5a04-115">See also</span></span>
- [<span data-ttu-id="f5a04-116">Aangepaste detectieregels maken en beheren</span><span class="sxs-lookup"><span data-stu-id="f5a04-116">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="f5a04-117">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="f5a04-117">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f5a04-118">Geavanceerde zoekquery's migreren van Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f5a04-118">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
