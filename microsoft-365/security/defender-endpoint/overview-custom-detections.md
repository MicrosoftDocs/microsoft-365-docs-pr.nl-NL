---
title: Overzicht van aangepaste detecties in Microsoft Defender ATP
ms.reviewer: ''
description: Meer informatie over hoe u geavanceerd zoeken kunt gebruiken om aangepaste detecties te maken en waarschuwingen te genereren
keywords: aangepaste detecties, waarschuwingen, detectieregels, geavanceerd zoeken, jagen, query, antwoordacties, interval, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c5de642d2fd22301b5cef1cf3674e60529455d5e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186915"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="ad7aa-104">Overzicht van aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="ad7aa-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ad7aa-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ad7aa-105">**Applies to:**</span></span>
- [<span data-ttu-id="ad7aa-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="ad7aa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ad7aa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad7aa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ad7aa-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="ad7aa-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ad7aa-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="ad7aa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="ad7aa-110">Met aangepaste detecties kunt u proactief controleren op en reageren op verschillende gebeurtenissen en systeemstaten, waaronder verdachte inbreukactiviteit en verkeerd geconfigureerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="ad7aa-110">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="ad7aa-111">U kunt dit doen met aanpasbare detectieregels die automatisch waarschuwingen en antwoordacties activeren.</span><span class="sxs-lookup"><span data-stu-id="ad7aa-111">You can do this with customizable detection rules that automatically trigger alerts and response actions.</span></span>

<span data-ttu-id="ad7aa-112">Aangepaste detecties werken met geavanceerde zoekprogramma's, die een krachtige, flexibele querytaal bieden die een breed scala aan gebeurtenis- en systeemgegevens van uw netwerk bestrijkt. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ad7aa-112">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="ad7aa-113">U kunt instellen dat ze regelmatig worden uitgevoerd, waarschuwingen genereren en antwoordacties uitvoeren wanneer er overeenkomsten zijn.</span><span class="sxs-lookup"><span data-stu-id="ad7aa-113">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="ad7aa-114">Aangepaste detecties bieden:</span><span class="sxs-lookup"><span data-stu-id="ad7aa-114">Custom detections provide:</span></span>
- <span data-ttu-id="ad7aa-115">Waarschuwingen voor op regels gebaseerde detecties die zijn gebaseerd op geavanceerde query's voor jagen</span><span class="sxs-lookup"><span data-stu-id="ad7aa-115">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="ad7aa-116">Automatische antwoordacties die van toepassing zijn op bestanden en apparaten</span><span class="sxs-lookup"><span data-stu-id="ad7aa-116">Automatic response actions that apply to files and devices</span></span>

## <a name="related-topics"></a><span data-ttu-id="ad7aa-117">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="ad7aa-117">Related topics</span></span>
- [<span data-ttu-id="ad7aa-118">Detectieregels maken</span><span class="sxs-lookup"><span data-stu-id="ad7aa-118">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="ad7aa-119">Detectieregels weergeven en beheren</span><span class="sxs-lookup"><span data-stu-id="ad7aa-119">View and manage detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="ad7aa-120">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="ad7aa-120">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
