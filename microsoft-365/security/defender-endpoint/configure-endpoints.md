---
title: Onboarden hulpmiddelen en methoden voor Windows 10-apparaten
description: Onboard Windows 10 apparaten zodat ze sensorgegevens kunnen verzenden naar de Microsoft Defender for Endpoint-sensor
keywords: Onboard Windows 10 apparaten, groepsbeleid, endpoint configuration manager, mobile device management, local script, gp, sccm, mdm, intune
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
ms.technology: mde
ms.openlocfilehash: f1ef2670a1ca749e0a2f1ebc96300d4eca043bf8
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892827"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="3bd3d-104">Onboarden hulpmiddelen en methoden voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="3bd3d-104">Onboarding tools and methods for Windows 10 devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3bd3d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="3bd3d-105">**Applies to:**</span></span>
- [<span data-ttu-id="3bd3d-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="3bd3d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3bd3d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3bd3d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="3bd3d-108">Microsoft 365 Preventie van gegevensverlies in eindpunten (DLP)</span><span class="sxs-lookup"><span data-stu-id="3bd3d-108">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [<span data-ttu-id="3bd3d-109">Microsoft 365 Insider-risicobeheer</span><span class="sxs-lookup"><span data-stu-id="3bd3d-109">Microsoft 365 Insider risk management</span></span>](/microsoft-365/compliance/insider-risk-management)

><span data-ttu-id="3bd3d-110">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="3bd3d-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3bd3d-111">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="3bd3d-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="3bd3d-112">Apparaten in uw organisatie moeten zo zijn geconfigureerd dat de Defender voor Eindpunt-service sensorgegevens van deze apparaten kan krijgen.</span><span class="sxs-lookup"><span data-stu-id="3bd3d-112">Devices in your organization must be configured so that the Defender for Endpoint service can get sensor data from them.</span></span> <span data-ttu-id="3bd3d-113">Er zijn verschillende methoden en implementatiehulpmiddelen die u kunt gebruiken om de apparaten in uw organisatie te configureren.</span><span class="sxs-lookup"><span data-stu-id="3bd3d-113">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="3bd3d-114">De volgende implementatiehulpmiddelen en -methoden worden ondersteund:</span><span class="sxs-lookup"><span data-stu-id="3bd3d-114">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="3bd3d-115">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="3bd3d-115">Group Policy</span></span>
- <span data-ttu-id="3bd3d-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3bd3d-116">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="3bd3d-117">Mobile Device Management (inclusief Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="3bd3d-117">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="3bd3d-118">Lokaal script</span><span class="sxs-lookup"><span data-stu-id="3bd3d-118">Local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3bd3d-119">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="3bd3d-119">In this section</span></span>
<span data-ttu-id="3bd3d-120">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="3bd3d-120">Topic</span></span> | <span data-ttu-id="3bd3d-121">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="3bd3d-121">Description</span></span>
:---|:---
[<span data-ttu-id="3bd3d-122">Onboard Windows 10 apparaten met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="3bd3d-122">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md) | <span data-ttu-id="3bd3d-123">Gebruik Groepsbeleid om het configuratiepakket op apparaten te implementeren.</span><span class="sxs-lookup"><span data-stu-id="3bd3d-123">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="3bd3d-124">Onboard Windows apparaten met Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3bd3d-124">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) | <span data-ttu-id="3bd3d-125">U kunt versie 1606 Microsoft Endpoint Manager (current branch) versie 1606 of Microsoft Endpoint Manager (current branch) versie 1602 of eerder gebruiken om het configuratiepakket op apparaten te implementeren.</span><span class="sxs-lookup"><span data-stu-id="3bd3d-125">You can use either use Microsoft Endpoint Manager (current branch) version 1606 or Microsoft Endpoint Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="3bd3d-126">Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="3bd3d-126">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md) | <span data-ttu-id="3bd3d-127">Gebruik hulpprogramma's voor mobiel apparaatbeheer of Microsoft Intune om het configuratiepakket op het apparaat te implementeren.</span><span class="sxs-lookup"><span data-stu-id="3bd3d-127">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="3bd3d-128">Onboarden Windows 10-apparaten met een lokaal script</span><span class="sxs-lookup"><span data-stu-id="3bd3d-128">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md) | <span data-ttu-id="3bd3d-129">Lees hoe u het lokale script gebruikt om het configuratiepakket op eindpunten te implementeren.</span><span class="sxs-lookup"><span data-stu-id="3bd3d-129">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="3bd3d-130">Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten</span><span class="sxs-lookup"><span data-stu-id="3bd3d-130">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md) | <span data-ttu-id="3bd3d-131">Lees hoe u het configuratiepakket gebruikt om VDI-apparaten te configureren.</span><span class="sxs-lookup"><span data-stu-id="3bd3d-131">Learn how to use the configuration package to configure VDI devices.</span></span>


><span data-ttu-id="3bd3d-132">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="3bd3d-132">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3bd3d-133">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="3bd3d-133">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
