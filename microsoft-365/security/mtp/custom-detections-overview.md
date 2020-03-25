---
title: Overzicht van aangepaste detecties in Microsoft Threat Protection
description: Begrijpen hoe u geavanceerde jacht gebruiken om aangepaste detecties te maken en waarschuwingen te genereren
keywords: geavanceerde jacht, dreigingsjacht, cyberdreigingsjacht, bescherming tegen microsoft-bedreigingen, microsoft 365, mtp, m365, zoeken, query, telemetrie, aangepaste detecties, schema, kusto, microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: a9ba61650b69e3c42506735c90ae05b917a53209
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2020
ms.locfileid: "42931724"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="9fd5c-104">Overzicht van aangepaste detecties</span><span class="sxs-lookup"><span data-stu-id="9fd5c-104">Custom detections overview</span></span>

<span data-ttu-id="9fd5c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="9fd5c-105">**Applies to:**</span></span>
- <span data-ttu-id="9fd5c-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="9fd5c-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="9fd5c-107">Met aangepaste detecties u proactief controleren op en reageren op verschillende gebeurtenissen en systeemtoestanden, waaronder vermoedelijke inbreukactiviteiten en verkeerd geconfigureerde eindpunten.</span><span class="sxs-lookup"><span data-stu-id="9fd5c-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="9fd5c-108">Dit wordt mogelijk gemaakt door aanpasbare detectieregels die automatisch waarschuwingen en reactieacties activeren.</span><span class="sxs-lookup"><span data-stu-id="9fd5c-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="9fd5c-109">Aangepaste detecties werken met [geavanceerde jacht,](advanced-hunting-overview.md)die een krachtige, flexibele querytaal biedt die een brede set gebeurtenis- en systeeminformatie uit uw netwerk omvat.</span><span class="sxs-lookup"><span data-stu-id="9fd5c-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="9fd5c-110">U instellen dat ze op regelmatige tijdstippen worden uitgevoerd, waarschuwingen genereren en responsacties uitvoeren wanneer er overeenkomsten zijn.</span><span class="sxs-lookup"><span data-stu-id="9fd5c-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="9fd5c-111">Aangepaste detecties bieden:</span><span class="sxs-lookup"><span data-stu-id="9fd5c-111">Custom detections provide:</span></span>
- <span data-ttu-id="9fd5c-112">Waarschuwingen voor op regels gebaseerde detecties die zijn gebaseerd op geavanceerde jachtquery's</span><span class="sxs-lookup"><span data-stu-id="9fd5c-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="9fd5c-113">Automatische reactieacties</span><span class="sxs-lookup"><span data-stu-id="9fd5c-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="9fd5c-114">Gerelateerd onderwerp</span><span class="sxs-lookup"><span data-stu-id="9fd5c-114">Related topic</span></span>
- [<span data-ttu-id="9fd5c-115">Aangepaste detectieregels maken en beheren</span><span class="sxs-lookup"><span data-stu-id="9fd5c-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="9fd5c-116">Geavanceerd jachtoverzicht</span><span class="sxs-lookup"><span data-stu-id="9fd5c-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)