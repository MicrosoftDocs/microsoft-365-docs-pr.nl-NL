---
title: Offboard-apparaten van de Microsoft Defender for Endpoint-service
description: Onboard Windows 10 apparaten, servers, niet-Windows apparaten van de Microsoft Defender for Endpoint-service
keywords: offboarding, Microsoft Defender voor endpoint offboarding, offboarding
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
ms.openlocfilehash: 425e5b9e0be12b89c8fd3b7201010b0f776cc6a5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934151"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="650d9-104">Offboard-apparaten van de Microsoft Defender for Endpoint-service</span><span class="sxs-lookup"><span data-stu-id="650d9-104">Offboard devices from the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="650d9-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="650d9-105">**Applies to:**</span></span>
- [<span data-ttu-id="650d9-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="650d9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="650d9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="650d9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="650d9-108">**Platforms**</span><span class="sxs-lookup"><span data-stu-id="650d9-108">**Platforms**</span></span>
- <span data-ttu-id="650d9-109">macOS</span><span class="sxs-lookup"><span data-stu-id="650d9-109">macOS</span></span>
- <span data-ttu-id="650d9-110">Linux</span><span class="sxs-lookup"><span data-stu-id="650d9-110">Linux</span></span>
- <span data-ttu-id="650d9-111">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="650d9-111">Windows Server 2012 R2</span></span>
- <span data-ttu-id="650d9-112">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="650d9-112">Windows Server 2016</span></span>

><span data-ttu-id="650d9-113">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="650d9-113">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="650d9-114">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="650d9-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

<span data-ttu-id="650d9-115">Volg de bijbehorende instructies, afhankelijk van uw voorkeursimplementatiemethode.</span><span class="sxs-lookup"><span data-stu-id="650d9-115">Follow the corresponding instructions depending on your preferred deployment method.</span></span>

>[!NOTE]
> <span data-ttu-id="650d9-116">De status van een apparaat wordt 7 dagen na het offboarden overgezet naar [Inactief.](fix-unhealthy-sensors.md#inactive-devices)</span><span class="sxs-lookup"><span data-stu-id="650d9-116">The status of a device will be switched to [Inactive](fix-unhealthy-sensors.md#inactive-devices) 7 days after offboarding.</span></span> <br> <span data-ttu-id="650d9-117">De gegevens van niet-geboarde apparaten (zoals tijdlijn, waarschuwingen, beveiligingsproblemen, enzovoort) blijven in de portal staan totdat de geconfigureerde bewaarperiode [verloopt.](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy)</span><span class="sxs-lookup"><span data-stu-id="650d9-117">Offboarded devices' data (such as Timeline, Alerts, Vulnerabilities, etc.) will remain in the portal until the configured [retention period](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) expires.</span></span> <br>
> <span data-ttu-id="650d9-118">Het profiel van het apparaat (zonder [](machines-view-overview.md) gegevens) blijft niet langer dan 180 dagen in de lijst met apparaten staan.</span><span class="sxs-lookup"><span data-stu-id="650d9-118">The device's profile (without data) will remain in the [Devices List](machines-view-overview.md) for no longer than 180 days.</span></span>
> <span data-ttu-id="650d9-119">Bovendien worden apparaten die niet actief zijn in de afgelopen 30 dagen, niet meegegegevens verwerkt [](tvm-exposure-score.md) die de Threat and Vulnerability Management blootstellingsscore van uw organisatie en Microsoft Secure Score voor apparaten weerspiegelen.</span><span class="sxs-lookup"><span data-stu-id="650d9-119">In addition, devices that are not active in the last 30 days are not factored in on the data that reflects your organization's threat and vulnerability management [exposure score](tvm-exposure-score.md) and Microsoft Secure Score for Devices.</span></span> <br>
> <span data-ttu-id="650d9-120">Als u alleen actieve apparaten wilt weergeven, kunt u filteren op [status,](machines-view-overview.md#health-state) [apparaatlabels](machine-tags.md) of [machinegroepen.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="650d9-120">To view only active devices, you can filter by [health state](machines-view-overview.md#health-state), [device tags](machine-tags.md) or [machine groups](machine-groups.md).</span></span> 

## <a name="offboard-windows-10-devices"></a><span data-ttu-id="650d9-121">Offboard-Windows 10 apparaten</span><span class="sxs-lookup"><span data-stu-id="650d9-121">Offboard Windows 10 devices</span></span>
- [<span data-ttu-id="650d9-122">Offboard-apparaten met een lokaal script</span><span class="sxs-lookup"><span data-stu-id="650d9-122">Offboard devices using a local script</span></span>](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [<span data-ttu-id="650d9-123">Offboard-apparaten met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="650d9-123">Offboard devices using Group Policy</span></span>](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [<span data-ttu-id="650d9-124">Offboard-apparaten met hulpprogramma's voor mobiel apparaatbeheer</span><span class="sxs-lookup"><span data-stu-id="650d9-124">Offboard devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a><span data-ttu-id="650d9-125">Offboard-servers</span><span class="sxs-lookup"><span data-stu-id="650d9-125">Offboard Servers</span></span>
- [<span data-ttu-id="650d9-126">Offboard-servers</span><span class="sxs-lookup"><span data-stu-id="650d9-126">Offboard servers</span></span>](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="650d9-127">Niet-offboard-Windows apparaten</span><span class="sxs-lookup"><span data-stu-id="650d9-127">Offboard non-Windows devices</span></span>
- [<span data-ttu-id="650d9-128">Niet-offboard-Windows apparaten</span><span class="sxs-lookup"><span data-stu-id="650d9-128">Offboard non-Windows devices</span></span>](configure-endpoints-non-windows.md#offboard-non-windows-devices)

