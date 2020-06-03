---
title: Overzicht van aangepaste detecties in Microsoft Threat Protection
description: Begrijp hoe u geavanceerde jacht gebruiken om aangepaste detecties te maken en waarschuwingen te genereren
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, aangepaste detecties, schema, kusto, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: cdbaf9cfd2172656ed75cb3c0a1a9e361070f25b
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498349"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="c07d8-104">Overzicht van aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="c07d8-104">Custom detections overview</span></span>

<span data-ttu-id="c07d8-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c07d8-105">**Applies to:**</span></span>
- <span data-ttu-id="c07d8-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c07d8-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c07d8-107">Met aangepaste detecties u proactief controleren op en reageren op verschillende gebeurtenissen en systeemtoestanden, waaronder vermoedelijke inbreukactiviteit en verkeerd geconfigureerde eindpunten.</span><span class="sxs-lookup"><span data-stu-id="c07d8-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="c07d8-108">Dit wordt mogelijk gemaakt door aanpasbare detectieregels die automatisch waarschuwingen en reactieacties activeren.</span><span class="sxs-lookup"><span data-stu-id="c07d8-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="c07d8-109">Aangepaste detecties werken met [geavanceerde jacht,](advanced-hunting-overview.md)die een krachtige, flexibele querytaal biedt die een brede set gebeurtenis- en systeeminformatie van uw netwerk omvat.</span><span class="sxs-lookup"><span data-stu-id="c07d8-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="c07d8-110">U instellen dat ze op regelmatige tijdstippen worden uitgevoerd, waarschuwingen genereren en responsacties uitvoeren wanneer er overeenkomsten zijn.</span><span class="sxs-lookup"><span data-stu-id="c07d8-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="c07d8-111">Aangepaste detecties bieden:</span><span class="sxs-lookup"><span data-stu-id="c07d8-111">Custom detections provide:</span></span>
- <span data-ttu-id="c07d8-112">Waarschuwingen voor op regels gebaseerde detecties die zijn opgebouwd uit geavanceerde jachtquery's</span><span class="sxs-lookup"><span data-stu-id="c07d8-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="c07d8-113">Automatische reactieacties</span><span class="sxs-lookup"><span data-stu-id="c07d8-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="c07d8-114">Gerelateerd onderwerp</span><span class="sxs-lookup"><span data-stu-id="c07d8-114">Related topic</span></span>
- [<span data-ttu-id="c07d8-115">Aangepaste detectieregels maken en beheren</span><span class="sxs-lookup"><span data-stu-id="c07d8-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="c07d8-116">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="c07d8-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)