---
title: Onboarden hulpmiddelen en methoden voor Windows 10-apparaten
description: Windows 10-apparaten aan boord zodat ze sensorgegevens kunnen verzenden naar de ATP-sensor van Microsoft Defender
keywords: Onboard Windows 10-apparaten, groepsbeleid, endpoint configuration manager, mobile device management, local script, gp, sccm, mdm, intune
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
ms.openlocfilehash: 1831d8927e761827f9bbcee84551433b68e3c6cc
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165535"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="8831a-104">Onboarden hulpmiddelen en methoden voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="8831a-104">Onboarding tools and methods for Windows 10 devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8831a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8831a-105">**Applies to:**</span></span>
- [<span data-ttu-id="8831a-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="8831a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8831a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8831a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="8831a-108">Microsoft 365 Endpoint Data Loss Prevention (DLP)</span><span class="sxs-lookup"><span data-stu-id="8831a-108">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

><span data-ttu-id="8831a-109">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="8831a-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8831a-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="8831a-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="8831a-111">Apparaten in uw organisatie moeten zo zijn geconfigureerd dat de Defender voor Eindpunt-service sensorgegevens van deze apparaten kan krijgen.</span><span class="sxs-lookup"><span data-stu-id="8831a-111">Devices in your organization must be configured so that the Defender for Endpoint service can get sensor data from them.</span></span> <span data-ttu-id="8831a-112">Er zijn verschillende methoden en implementatiehulpmiddelen die u kunt gebruiken om de apparaten in uw organisatie te configureren.</span><span class="sxs-lookup"><span data-stu-id="8831a-112">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="8831a-113">De volgende implementatiehulpmiddelen en -methoden worden ondersteund:</span><span class="sxs-lookup"><span data-stu-id="8831a-113">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="8831a-114">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="8831a-114">Group Policy</span></span>
- <span data-ttu-id="8831a-115">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8831a-115">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="8831a-116">Mobile Device Management (inclusief Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="8831a-116">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="8831a-117">Lokaal script</span><span class="sxs-lookup"><span data-stu-id="8831a-117">Local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8831a-118">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="8831a-118">In this section</span></span>
<span data-ttu-id="8831a-119">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="8831a-119">Topic</span></span> | <span data-ttu-id="8831a-120">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="8831a-120">Description</span></span>
:---|:---
[<span data-ttu-id="8831a-121">Onboard Windows 10-apparaten met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="8831a-121">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md) | <span data-ttu-id="8831a-122">Gebruik Groepsbeleid om het configuratiepakket op apparaten te implementeren.</span><span class="sxs-lookup"><span data-stu-id="8831a-122">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="8831a-123">Onboard Windows-apparaten met Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8831a-123">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) | <span data-ttu-id="8831a-124">U kunt versie 1606 of Versie 1602 van Microsoft Endpoint Manager (huidige vertakking) of eerder gebruiken om het configuratiepakket op apparaten te implementeren.</span><span class="sxs-lookup"><span data-stu-id="8831a-124">You can use either use Microsoft Endpoint Manager (current branch) version 1606 or Microsoft Endpoint Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="8831a-125">Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="8831a-125">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md) | <span data-ttu-id="8831a-126">Gebruik hulpprogramma's voor mobiel apparaatbeheer of Microsoft Intune om het configuratiepakket op het apparaat te implementeren.</span><span class="sxs-lookup"><span data-stu-id="8831a-126">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="8831a-127">Onboarden Windows 10-apparaten met een lokaal script</span><span class="sxs-lookup"><span data-stu-id="8831a-127">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md) | <span data-ttu-id="8831a-128">Lees hoe u het lokale script gebruikt om het configuratiepakket op eindpunten te implementeren.</span><span class="sxs-lookup"><span data-stu-id="8831a-128">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="8831a-129">Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten</span><span class="sxs-lookup"><span data-stu-id="8831a-129">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md) | <span data-ttu-id="8831a-130">Lees hoe u het configuratiepakket gebruikt om VDI-apparaten te configureren.</span><span class="sxs-lookup"><span data-stu-id="8831a-130">Learn how to use the configuration package to configure VDI devices.</span></span>


><span data-ttu-id="8831a-131">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="8831a-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8831a-132">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="8831a-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
