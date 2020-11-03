---
title: Overzicht van aangepaste detecties in Microsoft 365 Defender
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
ms.openlocfilehash: fe2b9f1b52fa2c8d9031bb58597992f3dda91520
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843910"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="97e59-104">Overzicht van aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="97e59-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="97e59-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="97e59-105">**Applies to:**</span></span>
- <span data-ttu-id="97e59-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97e59-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="97e59-107">Met aangepaste detectie kunt u de diverse gebeurtenissen en systeemstatus proactief controleren en beantwoorden, waaronder verdachte schendings activiteiten en onjuist geconfigureerde eindpunten.</span><span class="sxs-lookup"><span data-stu-id="97e59-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="97e59-108">Dit is mogelijk door aanpasbare detectieregels die automatisch waarschuwingen en antwoord acties activeren.</span><span class="sxs-lookup"><span data-stu-id="97e59-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="97e59-109">Aangepaste detectie met [geavanceerde jacht](advanced-hunting-overview.md), dat een krachtige, flexibele querytaal biedt die een uitgebreide set gebeurtenis-en systeeminformatie omvat van uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="97e59-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="97e59-110">U kunt instellen dat ze met regelmatige tussenpozen worden uitgevoerd, en de acties voor het maken van waarschuwingen worden gegenereerd wanneer er overeenkomsten zijn.</span><span class="sxs-lookup"><span data-stu-id="97e59-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="97e59-111">Aangepaste detecties biedt:</span><span class="sxs-lookup"><span data-stu-id="97e59-111">Custom detections provide:</span></span>
- <span data-ttu-id="97e59-112">Waarschuwingen voor detectie op basis van een regel die is gebaseerd op geavanceerde jacht-query's</span><span class="sxs-lookup"><span data-stu-id="97e59-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="97e59-113">Acties voor automatisch reageren</span><span class="sxs-lookup"><span data-stu-id="97e59-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="97e59-114">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="97e59-114">Related topic</span></span>
- [<span data-ttu-id="97e59-115">Aangepaste detectieregels maken en beheren</span><span class="sxs-lookup"><span data-stu-id="97e59-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="97e59-116">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="97e59-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
