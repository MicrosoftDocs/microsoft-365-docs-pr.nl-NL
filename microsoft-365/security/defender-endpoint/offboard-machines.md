---
title: Offboard-apparaten van de MICROSOFT Defender ATP-service
description: Onboard Windows 10-apparaten, servers, niet-Windows-apparaten van de MICROSOFT Defender ATP-service
keywords: offboarding, microsoft defender for endpoint offboarding, windows atp offboarding
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
ms.openlocfilehash: db22a19da58ba70ff09af781ca56e0b3c0d88dfd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056850"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="d2e96-104">Offboard-apparaten van de Microsoft Defender for Endpoint-service</span><span class="sxs-lookup"><span data-stu-id="d2e96-104">Offboard devices from the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d2e96-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d2e96-105">**Applies to:**</span></span>
- [<span data-ttu-id="d2e96-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="d2e96-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="d2e96-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d2e96-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="d2e96-108">**Platforms**</span><span class="sxs-lookup"><span data-stu-id="d2e96-108">**Platforms**</span></span>
- <span data-ttu-id="d2e96-109">macOS</span><span class="sxs-lookup"><span data-stu-id="d2e96-109">macOS</span></span>
- <span data-ttu-id="d2e96-110">Linux</span><span class="sxs-lookup"><span data-stu-id="d2e96-110">Linux</span></span>
- <span data-ttu-id="d2e96-111">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d2e96-111">Windows Server 2012 R2</span></span>
- <span data-ttu-id="d2e96-112">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="d2e96-112">Windows Server 2016</span></span>

><span data-ttu-id="d2e96-113">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="d2e96-113">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d2e96-114">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="d2e96-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

<span data-ttu-id="d2e96-115">Volg de bijbehorende instructies, afhankelijk van uw voorkeursimplementatiemethode.</span><span class="sxs-lookup"><span data-stu-id="d2e96-115">Follow the corresponding instructions depending on your preferred deployment method.</span></span>

>[!NOTE]
> <span data-ttu-id="d2e96-116">De status van een apparaat wordt 7 dagen na het offboarden overgezet naar [Inactief.](fix-unhealthy-sensors.md#inactive-devices)</span><span class="sxs-lookup"><span data-stu-id="d2e96-116">The status of a device will be switched to [Inactive](fix-unhealthy-sensors.md#inactive-devices) 7 days after offboarding.</span></span> <br> <span data-ttu-id="d2e96-117">De gegevens van niet-geboarde apparaten (zoals tijdlijn, waarschuwingen, beveiligingsproblemen, enzovoort) blijven in de portal staan totdat de geconfigureerde bewaarperiode [verloopt.](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy)</span><span class="sxs-lookup"><span data-stu-id="d2e96-117">Offboarded devices' data (such as Timeline, Alerts, Vulnerabilities, etc.) will remain in the portal until the configured [retention period](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) expires.</span></span> <br>
> <span data-ttu-id="d2e96-118">Het profiel van het apparaat (zonder [](machines-view-overview.md) gegevens) blijft niet langer dan 180 dagen in de lijst met apparaten staan.</span><span class="sxs-lookup"><span data-stu-id="d2e96-118">The device's profile (without data) will remain in the [Devices List](machines-view-overview.md) for no longer than 180 days.</span></span>
> <span data-ttu-id="d2e96-119">Bovendien worden apparaten die niet actief zijn in de afgelopen 30 dagen, niet meegeholpen aan [](tvm-exposure-score.md) de gegevens die de blootstellingsscore voor bedreigings- en kwetsbaarheidsbeheer van uw organisatie en Microsoft Secure Score voor apparaten weerspiegelen.</span><span class="sxs-lookup"><span data-stu-id="d2e96-119">In addition, devices that are not active in the last 30 days are not factored in on the data that reflects your organization's threat and vulnerability management [exposure score](tvm-exposure-score.md) and Microsoft Secure Score for Devices.</span></span> <br>
> <span data-ttu-id="d2e96-120">Als u alleen actieve apparaten wilt weergeven, kunt u filteren op [status,](machines-view-overview.md#health-state) [apparaatlabels](machine-tags.md) of [machinegroepen.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="d2e96-120">To view only active devices, you can filter by [health state](machines-view-overview.md#health-state), [device tags](machine-tags.md) or [machine groups](machine-groups.md).</span></span> 

## <a name="offboard-windows-10-devices"></a><span data-ttu-id="d2e96-121">Offboard Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="d2e96-121">Offboard Windows 10 devices</span></span>
- [<span data-ttu-id="d2e96-122">Offboard-apparaten met een lokaal script</span><span class="sxs-lookup"><span data-stu-id="d2e96-122">Offboard devices using a local script</span></span>](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [<span data-ttu-id="d2e96-123">Offboard-apparaten met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="d2e96-123">Offboard devices using Group Policy</span></span>](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [<span data-ttu-id="d2e96-124">Offboard-apparaten met hulpprogramma's voor mobiel apparaatbeheer</span><span class="sxs-lookup"><span data-stu-id="d2e96-124">Offboard devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a><span data-ttu-id="d2e96-125">Offboard-servers</span><span class="sxs-lookup"><span data-stu-id="d2e96-125">Offboard Servers</span></span>
- [<span data-ttu-id="d2e96-126">Offboard-servers</span><span class="sxs-lookup"><span data-stu-id="d2e96-126">Offboard servers</span></span>](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="d2e96-127">Offboard niet-Windows-apparaten</span><span class="sxs-lookup"><span data-stu-id="d2e96-127">Offboard non-Windows devices</span></span>
- [<span data-ttu-id="d2e96-128">Offboard niet-Windows-apparaten</span><span class="sxs-lookup"><span data-stu-id="d2e96-128">Offboard non-Windows devices</span></span>](configure-endpoints-non-windows.md#offboard-non-windows-devices)

