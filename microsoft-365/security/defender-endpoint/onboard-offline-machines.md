---
title: Onboard-apparaten zonder internettoegang tot Microsoft Defender voor Eindpunt
ms.reviewer: ''
description: Onboard-apparaten zonder internetverbinding, zodat ze sensorgegevens kunnen verzenden naar de ATP-sensor van Microsoft Defender
keywords: onboard, servers, vm, on-premises, oms gateway, loganalyse, azure log analytics, mma
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b31705a4e6dc8cdd480c8b43c2154a2d6ddacddd
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186939"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="f7277-104">Onboard-apparaten zonder internettoegang tot Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f7277-104">Onboard devices without Internet access to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f7277-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f7277-105">**Applies to:**</span></span>
- [<span data-ttu-id="f7277-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="f7277-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f7277-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7277-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f7277-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f7277-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f7277-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="f7277-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="f7277-110">Als u apparaten zonder internetverbinding wilt gebruiken, moet u de volgende algemene stappen ondernemen:</span><span class="sxs-lookup"><span data-stu-id="f7277-110">To onboard devices without Internet access, you'll need to take the following general steps:</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="f7277-111">De onderstaande stappen zijn alleen van toepassing op apparaten met eerdere versies van Windows, zoals Windows Server 2016 en eerder of Windows 8.1 en eerder.</span><span class="sxs-lookup"><span data-stu-id="f7277-111">The steps below are applicable only to devices running previous versions of Windows such as: Windows Server 2016 and earlier or Windows 8.1 and earlier.</span></span>

> [!NOTE]
> - <span data-ttu-id="f7277-112">Een OMS-gatewayserver kan niet worden gebruikt als proxy voor losgekoppelde Windows 10- of Windows Server 2019-apparaten wanneer deze zijn geconfigureerd via het register 'TelemetryProxyServer' of GPO.</span><span class="sxs-lookup"><span data-stu-id="f7277-112">An OMS gateway server cannot be used as proxy for disconnected Windows 10 or Windows Server 2019 devices when configured via 'TelemetryProxyServer' registry or GPO.</span></span>
> - <span data-ttu-id="f7277-113">Voor Windows 10 of Windows Server 2019- hoewel u TelemetryProxyServer mag gebruiken, moet deze naar een standaardproxyapparaat of -apparaat wijzen.</span><span class="sxs-lookup"><span data-stu-id="f7277-113">For Windows 10 or Windows Server 2019 - while you may use TelemetryProxyServer, it must point to a standard proxy device or appliance.</span></span>
> - <span data-ttu-id="f7277-114">Daarnaast moet Windows 10 of Windows Server 2019 in niet-verbonden omgevingen certificaten vertrouwenslijsten offline kunnen bijwerken via een intern bestand of webserver.</span><span class="sxs-lookup"><span data-stu-id="f7277-114">In addition, Windows 10 or Windows Server 2019 in disconnected environments must be able to update Certificate Trust Lists offline via an internal file or web server.</span></span>
> - <span data-ttu-id="f7277-115">Zie Een bestand of webserver configureren om de CTL-bestanden te downloaden voor meer informatie over het offline bijwerken van [CTL's.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files)</span><span class="sxs-lookup"><span data-stu-id="f7277-115">For more information about updating CTLs offline, see [Configure a file or web server to download the CTL files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).</span></span>

<span data-ttu-id="f7277-116">Zie de volgende artikelen voor meer informatie over onboardingmethoden:</span><span class="sxs-lookup"><span data-stu-id="f7277-116">For more information about onboarding methods, see the following articles:</span></span>
- [<span data-ttu-id="f7277-117">Eerdere versies van Windows aan boord</span><span class="sxs-lookup"><span data-stu-id="f7277-117">Onboard previous versions of Windows</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [<span data-ttu-id="f7277-118">Onboard servers to the Microsoft Defender for Endpoint service</span><span class="sxs-lookup"><span data-stu-id="f7277-118">Onboard servers to the Microsoft Defender for Endpoint service</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [<span data-ttu-id="f7277-119">Instellingen voor apparaatproxy en internetverbinding configureren</span><span class="sxs-lookup"><span data-stu-id="f7277-119">Configure device proxy and Internet connectivity settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premise-devices"></a><span data-ttu-id="f7277-120">On-premises apparaten</span><span class="sxs-lookup"><span data-stu-id="f7277-120">On-premise devices</span></span>

- <span data-ttu-id="f7277-121">Azure Log Analytics (voorheen BEKEND als OMS Gateway) instellen als proxy of hub:</span><span class="sxs-lookup"><span data-stu-id="f7277-121">Setup Azure Log Analytics (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
  - [<span data-ttu-id="f7277-122">Azure Log Analytics Agent</span><span class="sxs-lookup"><span data-stu-id="f7277-122">Azure Log Analytics Agent</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - <span data-ttu-id="f7277-123">[Microsoft Monitoring Agent (MMA) installeren](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) en configureren, wijs Defender for Endpoint Workspace-sleutel voor & id</span><span class="sxs-lookup"><span data-stu-id="f7277-123">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>

- <span data-ttu-id="f7277-124">Offlineapparaten in hetzelfde netwerk van Azure Log Analytics</span><span class="sxs-lookup"><span data-stu-id="f7277-124">Offline devices in the same network of Azure Log Analytics</span></span>
  -  <span data-ttu-id="f7277-125">Configureer MMA om te wijzen naar:</span><span class="sxs-lookup"><span data-stu-id="f7277-125">Configure MMA to point to:</span></span>
     - <span data-ttu-id="f7277-126">Azure Log Analytics IP als proxy</span><span class="sxs-lookup"><span data-stu-id="f7277-126">Azure Log Analytics IP as a proxy</span></span>
     - <span data-ttu-id="f7277-127">Defender for Endpoint workspace key & ID</span><span class="sxs-lookup"><span data-stu-id="f7277-127">Defender for Endpoint workspace key & ID</span></span>

## <a name="azure-virtual-machines"></a><span data-ttu-id="f7277-128">Virtuele Azure-machines</span><span class="sxs-lookup"><span data-stu-id="f7277-128">Azure virtual machines</span></span>
- <span data-ttu-id="f7277-129">Azure [Log Analytics-werkruimte configureren en inschakelen](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)</span><span class="sxs-lookup"><span data-stu-id="f7277-129">Configure and enable [Azure Log Analytics workspace](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)</span></span>

    - <span data-ttu-id="f7277-130">Azure Log Analytics Gateway (voorheen OMS Gateway genoemd) instellen als proxy of hub:</span><span class="sxs-lookup"><span data-stu-id="f7277-130">Setup Azure Log Analytics Gateway (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
      - [<span data-ttu-id="f7277-131">Azure Log Analytics Gateway</span><span class="sxs-lookup"><span data-stu-id="f7277-131">Azure Log Analytics Gateway</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - <span data-ttu-id="f7277-132">[Microsoft Monitoring Agent (MMA) installeren](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) en configureren, wijs Defender for Endpoint Workspace-sleutel voor & id</span><span class="sxs-lookup"><span data-stu-id="f7277-132">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>
    - <span data-ttu-id="f7277-133">Offline Azure VMs in hetzelfde netwerk van OMS Gateway</span><span class="sxs-lookup"><span data-stu-id="f7277-133">Offline Azure VMs in the same network of OMS Gateway</span></span>
      - <span data-ttu-id="f7277-134">Azure Log Analytics IP configureren als een proxy</span><span class="sxs-lookup"><span data-stu-id="f7277-134">Configure Azure Log Analytics IP as a proxy</span></span>
      - <span data-ttu-id="f7277-135">Azure Log Analytics Workspace Key & ID</span><span class="sxs-lookup"><span data-stu-id="f7277-135">Azure Log Analytics Workspace Key & ID</span></span>

    - <span data-ttu-id="f7277-136">Azure Security Center (ASC)</span><span class="sxs-lookup"><span data-stu-id="f7277-136">Azure Security Center (ASC)</span></span>
      - [<span data-ttu-id="f7277-137">Werkruimte voor \> beveiligingsbeleidlogboekanalyse</span><span class="sxs-lookup"><span data-stu-id="f7277-137">Security Policy \> Log Analytics Workspace</span></span>](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [<span data-ttu-id="f7277-138">Threat Detection \> Allow Defender for Endpoint to access my data</span><span class="sxs-lookup"><span data-stu-id="f7277-138">Threat Detection \> Allow Defender for Endpoint to access my data</span></span>](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        <span data-ttu-id="f7277-139">Zie Werken met [beveiligingsbeleid voor meer informatie.](https://docs.microsoft.com/azure/security-center/tutorial-security-policy)</span><span class="sxs-lookup"><span data-stu-id="f7277-139">For more information, see [Working with security policies](https://docs.microsoft.com/azure/security-center/tutorial-security-policy).</span></span>
