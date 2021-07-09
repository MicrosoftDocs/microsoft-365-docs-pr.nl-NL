---
title: Onboarding-methoden en -hulpmiddelen voor Windows 10 apparaten
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
ms.openlocfilehash: 676fb3a7ffcae8d108fd9b7fabe61bb78b7e1744
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341698"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="eac35-103">Onboarden hulpmiddelen en methoden voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="eac35-103">Onboarding tools and methods for Windows 10 devices</span></span>

<span data-ttu-id="eac35-104">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="eac35-104">**Applies to:**</span></span>
- [<span data-ttu-id="eac35-105">Microsoft 365 Preventie van gegevensverlies in eindpunten (DLP)</span><span class="sxs-lookup"><span data-stu-id="eac35-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="eac35-106">Apparaten in uw organisatie moeten zo zijn geconfigureerd dat Microsoft 365 endpoint-service voor preventie van gegevensverlies sensorgegevens van deze apparaten kan krijgen.</span><span class="sxs-lookup"><span data-stu-id="eac35-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="eac35-107">Er zijn verschillende methoden en implementatiehulpmiddelen die u kunt gebruiken om de apparaten in uw organisatie te configureren.</span><span class="sxs-lookup"><span data-stu-id="eac35-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="eac35-108">De volgende implementatiehulpmiddelen en -methoden worden ondersteund:</span><span class="sxs-lookup"><span data-stu-id="eac35-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="eac35-109">groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="eac35-109">group policy</span></span>
- <span data-ttu-id="eac35-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="eac35-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="eac35-111">Mobile Device Management (inclusief Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="eac35-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="eac35-112">lokaal script</span><span class="sxs-lookup"><span data-stu-id="eac35-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="eac35-113">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="eac35-113">In this section</span></span>
<span data-ttu-id="eac35-114">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="eac35-114">Topic</span></span> | <span data-ttu-id="eac35-115">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="eac35-115">Description</span></span>
:---|:---
[<span data-ttu-id="eac35-116">Onboard Windows 10 apparaten met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="eac35-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="eac35-117">Gebruik Groepsbeleid om het configuratiepakket op apparaten te implementeren.</span><span class="sxs-lookup"><span data-stu-id="eac35-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="eac35-118">Onboard Windows apparaten met Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="eac35-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="eac35-119">U kunt versie 1606 Microsoft Endpoint Configuration Manager (current branch) versie 1606 of Microsoft Endpoint Configuration Manager (current branch) versie 1602 of eerder gebruiken om het configuratiepakket op apparaten te implementeren.</span><span class="sxs-lookup"><span data-stu-id="eac35-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="eac35-120">Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="eac35-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="eac35-121">Gebruik hulpprogramma's voor mobiel apparaatbeheer of Microsoft Intune om het configuratiepakket op het apparaat te implementeren.</span><span class="sxs-lookup"><span data-stu-id="eac35-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="eac35-122">Onboarden Windows 10-apparaten met een lokaal script</span><span class="sxs-lookup"><span data-stu-id="eac35-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="eac35-123">Lees hoe u het lokale script gebruikt om het configuratiepakket op eindpunten te implementeren.</span><span class="sxs-lookup"><span data-stu-id="eac35-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="eac35-124">Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten</span><span class="sxs-lookup"><span data-stu-id="eac35-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="eac35-125">Lees hoe u het configuratiepakket gebruikt om VDI-apparaten te configureren.</span><span class="sxs-lookup"><span data-stu-id="eac35-125">Learn how to use the configuration package to configure VDI devices.</span></span>