---
title: Waarschuwingenwachtrij in Microsoft Defender-beveiligingscentrum
ms.reviewer: ''
description: De waarschuwingen weergeven en beheren die zijn opgedoken in het Microsoft Defender-beveiligingscentrum
keywords: ''
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
ms.topic: conceptual
ms.date: 09/03/2018
ms.technology: mde
ms.openlocfilehash: d40fc887f26dfe62e05f7ee6ac7bbbb8ac45a402
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059962"
---
# <a name="alerts-queue-in-microsoft-defender-security-center"></a><span data-ttu-id="7a59a-103">Waarschuwingenwachtrij in Microsoft Defender-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="7a59a-103">Alerts queue in Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7a59a-104">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7a59a-104">**Applies to:**</span></span>
- [<span data-ttu-id="7a59a-105">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="7a59a-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="7a59a-106">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="7a59a-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7a59a-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="7a59a-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="7a59a-108">Lees hoe u de wachtrij kunt bekijken en beheren, zodat u bedreigingen die worden gezien op entiteiten zoals apparaten, bestanden of gebruikersaccounts, effectief kunt onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="7a59a-108">Learn how you can view and manage the queue so that you can effectively investigate threats seen on entities such as devices, files, or user accounts.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7a59a-109">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="7a59a-109">In this section</span></span>
<span data-ttu-id="7a59a-110">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="7a59a-110">Topic</span></span> | <span data-ttu-id="7a59a-111">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="7a59a-111">Description</span></span> 
:---|:---
[<span data-ttu-id="7a59a-112">De wachtrij Waarschuwingen weergeven en ordenen</span><span class="sxs-lookup"><span data-stu-id="7a59a-112">View and organize the Alerts queue</span></span>](alerts-queue.md) | <span data-ttu-id="7a59a-113">Toont een lijst met waarschuwingen die zijn gemarkeerd in uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="7a59a-113">Shows a list of alerts that were flagged in your network.</span></span>
[<span data-ttu-id="7a59a-114">Waarschuwingen beheren</span><span class="sxs-lookup"><span data-stu-id="7a59a-114">Manage alerts</span></span>](manage-alerts.md) | <span data-ttu-id="7a59a-115">Meer informatie over hoe u waarschuwingen kunt beheren, zoals de status wijzigen, deze toewijzen aan een lid van beveiligingsbewerkingen en de geschiedenis van een waarschuwing bekijken.</span><span class="sxs-lookup"><span data-stu-id="7a59a-115">Learn about how you can manage alerts such as change its status, assign it to a security operations member, and see the history of an alert.</span></span>
[<span data-ttu-id="7a59a-116">Waarschuwingen onderzoeken</span><span class="sxs-lookup"><span data-stu-id="7a59a-116">Investigate alerts</span></span>](investigate-alerts.md)| <span data-ttu-id="7a59a-117">Onderzoek waarschuwingen die van invloed zijn op uw netwerk, begrijpen wat ze betekenen en hoe u deze kunt oplossen.</span><span class="sxs-lookup"><span data-stu-id="7a59a-117">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>
[<span data-ttu-id="7a59a-118">Bestanden onderzoeken</span><span class="sxs-lookup"><span data-stu-id="7a59a-118">Investigate files</span></span>](investigate-files.md)| <span data-ttu-id="7a59a-119">Onderzoek de details van een bestand dat is gekoppeld aan een specifieke waarschuwing, gedrag of gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="7a59a-119">Investigate the details of a file associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="7a59a-120">Apparaten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="7a59a-120">Investigate devices</span></span>](investigate-machines.md)| <span data-ttu-id="7a59a-121">Onderzoek de details van een apparaat dat is gekoppeld aan een specifieke waarschuwing, gedrag of gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="7a59a-121">Investigate the details of a device associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="7a59a-122">Een IP-adres onderzoeken</span><span class="sxs-lookup"><span data-stu-id="7a59a-122">Investigate an IP address</span></span>](investigate-ip.md) | <span data-ttu-id="7a59a-123">Bekijk mogelijke communicatie tussen apparaten in uw netwerk en IP-adressen (External Internet Protocol).</span><span class="sxs-lookup"><span data-stu-id="7a59a-123">Examine possible communication between devices in your network and external internet protocol (IP) addresses.</span></span>
[<span data-ttu-id="7a59a-124">Een domein onderzoeken</span><span class="sxs-lookup"><span data-stu-id="7a59a-124">Investigate a domain</span></span>](investigate-domain.md) | <span data-ttu-id="7a59a-125">Onderzoek een domein om te zien of apparaten en servers in uw netwerk hebben gecommuniceerd met een bekend kwaadwillend domein.</span><span class="sxs-lookup"><span data-stu-id="7a59a-125">Investigate a domain to see if devices and servers in your network have been communicating with a known malicious domain.</span></span> 
[<span data-ttu-id="7a59a-126">Een gebruikersaccount onderzoeken</span><span class="sxs-lookup"><span data-stu-id="7a59a-126">Investigate a user account</span></span>](investigate-user.md) | <span data-ttu-id="7a59a-127">Identificeer gebruikersaccounts met de meest actieve waarschuwingen en onderzoek gevallen van mogelijke gecompromitteerde referenties.</span><span class="sxs-lookup"><span data-stu-id="7a59a-127">Identify user accounts with the most active alerts and investigate cases of potential compromised credentials.</span></span>  


