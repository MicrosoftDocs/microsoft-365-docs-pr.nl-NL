---
title: Gebruikersresourcetype
description: Recente waarschuwingen van Microsoft Defender voor eindpunten ophalen die betrekking hebben op gebruikers.
keywords: api's, graph api, ondersteunde api's, get, waarschuwingen, recent
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 39b73772bcc626590aa784bb5b21357f66229816
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772135"
---
# <a name="user-resource-type"></a><span data-ttu-id="bc993-104">Gebruikersresourcetype</span><span class="sxs-lookup"><span data-stu-id="bc993-104">User resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bc993-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="bc993-105">**Applies to:**</span></span>
- [<span data-ttu-id="bc993-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="bc993-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="bc993-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bc993-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bc993-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="bc993-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bc993-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="bc993-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="bc993-110">Methode</span><span class="sxs-lookup"><span data-stu-id="bc993-110">Method</span></span>|<span data-ttu-id="bc993-111">Retourtype</span><span class="sxs-lookup"><span data-stu-id="bc993-111">Return Type</span></span> |<span data-ttu-id="bc993-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="bc993-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="bc993-113">Gebruikersgerelateerde waarschuwingen lijst</span><span class="sxs-lookup"><span data-stu-id="bc993-113">List User related alerts</span></span>](get-user-related-alerts.md) | <span data-ttu-id="bc993-114">[waarschuwingsverzameling](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="bc993-114">[alert](alerts.md) collection</span></span> |  <span data-ttu-id="bc993-115">Vermeld alle waarschuwingen die aan een gebruiker [zijn gekoppeld.](user.md)</span><span class="sxs-lookup"><span data-stu-id="bc993-115">List all the alerts that are associated with a [user](user.md).</span></span>
[<span data-ttu-id="bc993-116">Gebruikersgerelateerde apparaten lijst</span><span class="sxs-lookup"><span data-stu-id="bc993-116">List User related devices</span></span>](get-user-related-machines.md) | <span data-ttu-id="bc993-117">[machineverzameling](machine.md)</span><span class="sxs-lookup"><span data-stu-id="bc993-117">[machine](machine.md) collection</span></span> | <span data-ttu-id="bc993-118">Vermeld alle apparaten die door een gebruiker zijn [aangemeld.](user.md)</span><span class="sxs-lookup"><span data-stu-id="bc993-118">List all the devices that were logged on by a [user](user.md).</span></span>
