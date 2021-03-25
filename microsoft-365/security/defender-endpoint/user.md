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
ms.technology: mde
ms.openlocfilehash: e3b2a567a953883d1d0ecd062159bfee4135dc85
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51197955"
---
# <a name="user-resource-type"></a><span data-ttu-id="17bdf-104">Gebruikersresourcetype</span><span class="sxs-lookup"><span data-stu-id="17bdf-104">User resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="17bdf-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="17bdf-105">**Applies to:**</span></span>
- [<span data-ttu-id="17bdf-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="17bdf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="17bdf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="17bdf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="17bdf-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="17bdf-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="17bdf-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="17bdf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="17bdf-110">Methode</span><span class="sxs-lookup"><span data-stu-id="17bdf-110">Method</span></span>|<span data-ttu-id="17bdf-111">Retourtype</span><span class="sxs-lookup"><span data-stu-id="17bdf-111">Return Type</span></span> |<span data-ttu-id="17bdf-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="17bdf-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="17bdf-113">Gebruikersgerelateerde waarschuwingen lijst</span><span class="sxs-lookup"><span data-stu-id="17bdf-113">List User related alerts</span></span>](get-user-related-alerts.md) | <span data-ttu-id="17bdf-114">[waarschuwingsverzameling](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="17bdf-114">[alert](alerts.md) collection</span></span> |  <span data-ttu-id="17bdf-115">Vermeld alle waarschuwingen die aan een gebruiker [zijn gekoppeld.](user.md)</span><span class="sxs-lookup"><span data-stu-id="17bdf-115">List all the alerts that are associated with a [user](user.md).</span></span>
[<span data-ttu-id="17bdf-116">Gebruikersgerelateerde apparaten lijst</span><span class="sxs-lookup"><span data-stu-id="17bdf-116">List User related devices</span></span>](get-user-related-machines.md) | <span data-ttu-id="17bdf-117">[machineverzameling](machine.md)</span><span class="sxs-lookup"><span data-stu-id="17bdf-117">[machine](machine.md) collection</span></span> | <span data-ttu-id="17bdf-118">Vermeld alle apparaten die door een gebruiker zijn [aangemeld.](user.md)</span><span class="sxs-lookup"><span data-stu-id="17bdf-118">List all the devices that were logged on by a [user](user.md).</span></span>
