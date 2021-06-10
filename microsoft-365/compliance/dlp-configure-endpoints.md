---
title: Onboarden hulpmiddelen en methoden voor Windows 10-apparaten
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Onboard Windows 10 apparaten zodat ze sensorgegevens kunnen verzenden naar de Microsoft 365 Compliance-oplossingen
ms.openlocfilehash: 7cbadc343c5cee1aa7704bcb9da8be2a152726ab
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161906"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="8c86c-103">Onboarden hulpmiddelen en methoden voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="8c86c-103">Onboarding tools and methods for Windows 10 devices</span></span>

<span data-ttu-id="8c86c-104">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8c86c-104">**Applies to:**</span></span>
- [<span data-ttu-id="8c86c-105">Microsoft 365 Preventie van gegevensverlies in eindpunten (DLP)</span><span class="sxs-lookup"><span data-stu-id="8c86c-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="8c86c-106">Apparaten in uw organisatie moeten zo zijn geconfigureerd dat Microsoft 365 endpoint-service voor preventie van gegevensverlies sensorgegevens van deze apparaten kan krijgen.</span><span class="sxs-lookup"><span data-stu-id="8c86c-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="8c86c-107">Er zijn verschillende methoden en implementatiehulpmiddelen die u kunt gebruiken om de apparaten in uw organisatie te configureren.</span><span class="sxs-lookup"><span data-stu-id="8c86c-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="8c86c-108">De volgende implementatiehulpmiddelen en -methoden worden ondersteund:</span><span class="sxs-lookup"><span data-stu-id="8c86c-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="8c86c-109">groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="8c86c-109">group policy</span></span>
- <span data-ttu-id="8c86c-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8c86c-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="8c86c-111">Mobile Device Management (inclusief Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="8c86c-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="8c86c-112">lokaal script</span><span class="sxs-lookup"><span data-stu-id="8c86c-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8c86c-113">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="8c86c-113">In this section</span></span>
<span data-ttu-id="8c86c-114">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="8c86c-114">Topic</span></span> | <span data-ttu-id="8c86c-115">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="8c86c-115">Description</span></span>
:---|:---
[<span data-ttu-id="8c86c-116">Onboard Windows 10 apparaten met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="8c86c-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="8c86c-117">Gebruik Groepsbeleid om het configuratiepakket op apparaten te implementeren.</span><span class="sxs-lookup"><span data-stu-id="8c86c-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="8c86c-118">Onboard Windows apparaten met Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8c86c-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="8c86c-119">U kunt versie 1606 Microsoft Endpoint Configuration Manager (current branch) versie 1606 of Microsoft Endpoint Configuration Manager (current branch) versie 1602 of eerder gebruiken om het configuratiepakket op apparaten te implementeren.</span><span class="sxs-lookup"><span data-stu-id="8c86c-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="8c86c-120">Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="8c86c-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="8c86c-121">Gebruik hulpprogramma's voor mobiel apparaatbeheer of Microsoft Intune om het configuratiepakket op het apparaat te implementeren.</span><span class="sxs-lookup"><span data-stu-id="8c86c-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="8c86c-122">Onboarden Windows 10-apparaten met een lokaal script</span><span class="sxs-lookup"><span data-stu-id="8c86c-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="8c86c-123">Lees hoe u het lokale script gebruikt om het configuratiepakket op eindpunten te implementeren.</span><span class="sxs-lookup"><span data-stu-id="8c86c-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="8c86c-124">Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten</span><span class="sxs-lookup"><span data-stu-id="8c86c-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="8c86c-125">Lees hoe u het configuratiepakket gebruikt om VDI-apparaten te configureren.</span><span class="sxs-lookup"><span data-stu-id="8c86c-125">Learn how to use the configuration package to configure VDI devices.</span></span>