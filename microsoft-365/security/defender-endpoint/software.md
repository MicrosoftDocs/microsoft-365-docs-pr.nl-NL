---
title: Softwaremethoden en -eigenschappen
description: Hiermee worden de meest recente waarschuwingen opgehaald.
keywords: api's, graph api, ondersteunde api's, get, waarschuwingen, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9bfec2c4e65a390189556c14347eaf17236fb95e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187102"
---
# <a name="software-resource-type"></a><span data-ttu-id="48473-104">Type softwareresource</span><span class="sxs-lookup"><span data-stu-id="48473-104">Software resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="48473-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="48473-105">**Applies to:**</span></span>
- [<span data-ttu-id="48473-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="48473-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="48473-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48473-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="48473-108">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="48473-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="48473-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="48473-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="48473-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="48473-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="48473-111">Methoden</span><span class="sxs-lookup"><span data-stu-id="48473-111">Methods</span></span>

<span data-ttu-id="48473-112">Methode</span><span class="sxs-lookup"><span data-stu-id="48473-112">Method</span></span> |<span data-ttu-id="48473-113">Retourtype</span><span class="sxs-lookup"><span data-stu-id="48473-113">Return Type</span></span> |<span data-ttu-id="48473-114">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="48473-114">Description</span></span>
:---|:---|:---
[<span data-ttu-id="48473-115">Lijstsoftware</span><span class="sxs-lookup"><span data-stu-id="48473-115">List software</span></span>](get-software.md) | <span data-ttu-id="48473-116">Softwareverzameling</span><span class="sxs-lookup"><span data-stu-id="48473-116">Software collection</span></span> | <span data-ttu-id="48473-117">Vermeld de inventaris van de organisatiesoftware.</span><span class="sxs-lookup"><span data-stu-id="48473-117">List the organizational software inventory.</span></span>
[<span data-ttu-id="48473-118">Software downloaden op id</span><span class="sxs-lookup"><span data-stu-id="48473-118">Get software by Id</span></span>](get-software-by-id.md) | <span data-ttu-id="48473-119">Software</span><span class="sxs-lookup"><span data-stu-id="48473-119">Software</span></span> | <span data-ttu-id="48473-120">Een specifieke software downloaden op de software-id.</span><span class="sxs-lookup"><span data-stu-id="48473-120">Get a specific software by its software ID.</span></span>
[<span data-ttu-id="48473-121">Distributie van softwareversies van lijst</span><span class="sxs-lookup"><span data-stu-id="48473-121">List software version distribution</span></span>](get-software-ver-distribution.md)| <span data-ttu-id="48473-122">Distributieverzameling</span><span class="sxs-lookup"><span data-stu-id="48473-122">Distribution collection</span></span> | <span data-ttu-id="48473-123">Lijst met softwareversiedistributie per software-id.</span><span class="sxs-lookup"><span data-stu-id="48473-123">List software version distribution by software ID.</span></span>
[<span data-ttu-id="48473-124">Machines per softwarelijst maken</span><span class="sxs-lookup"><span data-stu-id="48473-124">List machines by software</span></span>](get-machines-by-software.md)| <span data-ttu-id="48473-125">MachineRef-verzameling</span><span class="sxs-lookup"><span data-stu-id="48473-125">MachineRef collection</span></span> | <span data-ttu-id="48473-126">Een lijst met apparaten ophalen die zijn gekoppeld aan de software-id.</span><span class="sxs-lookup"><span data-stu-id="48473-126">Retrieve a list of devices that are associated with the software ID.</span></span>
[<span data-ttu-id="48473-127">Beveiligingslekken door software op een lijst zetten</span><span class="sxs-lookup"><span data-stu-id="48473-127">List vulnerabilities by software</span></span>](get-vuln-by-software.md) | <span data-ttu-id="48473-128">[Kwetsbaarheidsverzameling](vulnerability.md)</span><span class="sxs-lookup"><span data-stu-id="48473-128">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="48473-129">Een lijst met beveiligingslekken ophalen die zijn gekoppeld aan de software-id.</span><span class="sxs-lookup"><span data-stu-id="48473-129">Retrieve a list of vulnerabilities associated with the software ID.</span></span>
[<span data-ttu-id="48473-130">Ontbrekende KBs krijgen</span><span class="sxs-lookup"><span data-stu-id="48473-130">Get missing KBs</span></span>](get-missing-kbs-software.md) | <span data-ttu-id="48473-131">KB-verzameling</span><span class="sxs-lookup"><span data-stu-id="48473-131">KB collection</span></span> | <span data-ttu-id="48473-132">Een lijst met ontbrekende KBs downloaden die zijn gekoppeld aan de software-id</span><span class="sxs-lookup"><span data-stu-id="48473-132">Get a list of missing KBs associated with the software ID</span></span>

## <a name="properties"></a><span data-ttu-id="48473-133">Eigenschappen</span><span class="sxs-lookup"><span data-stu-id="48473-133">Properties</span></span>

<span data-ttu-id="48473-134">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="48473-134">Property</span></span> |   <span data-ttu-id="48473-135">Type</span><span class="sxs-lookup"><span data-stu-id="48473-135">Type</span></span>   |   <span data-ttu-id="48473-136">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="48473-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="48473-137">id</span><span class="sxs-lookup"><span data-stu-id="48473-137">id</span></span> | <span data-ttu-id="48473-138">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48473-138">String</span></span> | <span data-ttu-id="48473-139">Software-id</span><span class="sxs-lookup"><span data-stu-id="48473-139">Software ID</span></span>
<span data-ttu-id="48473-140">Naam</span><span class="sxs-lookup"><span data-stu-id="48473-140">Name</span></span> | <span data-ttu-id="48473-141">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48473-141">String</span></span> | <span data-ttu-id="48473-142">Softwarenaam</span><span class="sxs-lookup"><span data-stu-id="48473-142">Software name</span></span>
<span data-ttu-id="48473-143">Leverancier</span><span class="sxs-lookup"><span data-stu-id="48473-143">Vendor</span></span> | <span data-ttu-id="48473-144">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48473-144">String</span></span> | <span data-ttu-id="48473-145">Naam softwareleverancier</span><span class="sxs-lookup"><span data-stu-id="48473-145">Software vendor name</span></span>
<span data-ttu-id="48473-146">Zwakke punten</span><span class="sxs-lookup"><span data-stu-id="48473-146">Weaknesses</span></span> | <span data-ttu-id="48473-147">Lang</span><span class="sxs-lookup"><span data-stu-id="48473-147">Long</span></span> | <span data-ttu-id="48473-148">Aantal gevonden beveiligingslekken</span><span class="sxs-lookup"><span data-stu-id="48473-148">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="48473-149">publicExploit</span><span class="sxs-lookup"><span data-stu-id="48473-149">publicExploit</span></span> | <span data-ttu-id="48473-150">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="48473-150">Boolean</span></span> | <span data-ttu-id="48473-151">Openbare exploit bestaat voor een aantal van de beveiligingslekken</span><span class="sxs-lookup"><span data-stu-id="48473-151">Public exploit exists for some of the vulnerabilities</span></span>
<span data-ttu-id="48473-152">activeAlert</span><span class="sxs-lookup"><span data-stu-id="48473-152">activeAlert</span></span> | <span data-ttu-id="48473-153">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="48473-153">Boolean</span></span> | <span data-ttu-id="48473-154">Actieve waarschuwing is gekoppeld aan deze software</span><span class="sxs-lookup"><span data-stu-id="48473-154">Active alert is associated with this software</span></span>
<span data-ttu-id="48473-155">exposedMachines</span><span class="sxs-lookup"><span data-stu-id="48473-155">exposedMachines</span></span> | <span data-ttu-id="48473-156">Lang</span><span class="sxs-lookup"><span data-stu-id="48473-156">Long</span></span> | <span data-ttu-id="48473-157">Aantal blootgestelde apparaten</span><span class="sxs-lookup"><span data-stu-id="48473-157">Number of exposed devices</span></span>
<span data-ttu-id="48473-158">impactScore</span><span class="sxs-lookup"><span data-stu-id="48473-158">impactScore</span></span> | <span data-ttu-id="48473-159">Dubbel</span><span class="sxs-lookup"><span data-stu-id="48473-159">Double</span></span> | <span data-ttu-id="48473-160">Impact van blootstellingsscore van deze software</span><span class="sxs-lookup"><span data-stu-id="48473-160">Exposure score impact of this software</span></span>
