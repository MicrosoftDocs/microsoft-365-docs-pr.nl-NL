---
title: Overzicht van aangepaste detecties in Microsoft Threat Protection
description: Meer informatie over het gebruik van geavanceerde jacht om aangepaste detecties te maken en waarschuwingen te genereren
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, aangepaste detectie, schema, kusto, Microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: 28d6cca20c8b386d5e6f7f39b80264a39f88ec55
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199463"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="78b4b-104">Overzicht van aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="78b4b-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="78b4b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="78b4b-105">**Applies to:**</span></span>
- <span data-ttu-id="78b4b-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="78b4b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="78b4b-107">Met aangepaste detectie kunt u de diverse gebeurtenissen en systeemstatus proactief controleren en beantwoorden, waaronder verdachte schendings activiteiten en onjuist geconfigureerde eindpunten.</span><span class="sxs-lookup"><span data-stu-id="78b4b-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="78b4b-108">Dit is mogelijk door aanpasbare detectieregels die automatisch waarschuwingen en antwoord acties activeren.</span><span class="sxs-lookup"><span data-stu-id="78b4b-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="78b4b-109">Aangepaste detectie met [geavanceerde jacht](advanced-hunting-overview.md), dat een krachtige, flexibele querytaal biedt die een uitgebreide set gebeurtenis-en systeeminformatie omvat van uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="78b4b-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="78b4b-110">U kunt instellen dat ze met regelmatige tussenpozen worden uitgevoerd, en de acties voor het maken van waarschuwingen worden gegenereerd wanneer er overeenkomsten zijn.</span><span class="sxs-lookup"><span data-stu-id="78b4b-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="78b4b-111">Aangepaste detecties biedt:</span><span class="sxs-lookup"><span data-stu-id="78b4b-111">Custom detections provide:</span></span>
- <span data-ttu-id="78b4b-112">Waarschuwingen voor detectie op basis van een regel die is gebaseerd op geavanceerde jacht-query's</span><span class="sxs-lookup"><span data-stu-id="78b4b-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="78b4b-113">Acties voor automatisch reageren</span><span class="sxs-lookup"><span data-stu-id="78b4b-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="78b4b-114">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="78b4b-114">Related topic</span></span>
- [<span data-ttu-id="78b4b-115">Aangepaste detectieregels maken en beheren</span><span class="sxs-lookup"><span data-stu-id="78b4b-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="78b4b-116">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="78b4b-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
