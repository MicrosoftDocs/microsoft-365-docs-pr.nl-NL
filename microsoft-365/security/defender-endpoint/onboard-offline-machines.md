---
title: Onboard-apparaten zonder internettoegang tot Microsoft Defender voor Eindpunt
ms.reviewer: ''
description: Onboard-apparaten zonder internetverbinding, zodat ze sensorgegevens kunnen verzenden naar de Microsoft Defender for Endpoint-sensor
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
ms.openlocfilehash: 73110d89c39319825cc8dc8e347d137de52a510a
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028377"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a>Onboard-apparaten zonder internettoegang tot Microsoft Defender voor Eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Als u apparaten zonder internetverbinding wilt gebruiken, moet u de volgende algemene stappen ondernemen:

> [!IMPORTANT] 
> De onderstaande stappen zijn alleen van toepassing op apparaten met eerdere versies van Windows, zoals Windows Server 2016 en eerder of Windows 8.1 en eerder.

> [!NOTE]
> - Een OMS-gatewayserver kan niet worden gebruikt als proxy voor losgekoppelde Windows 10- of Windows Server 2019-apparaten wanneer deze zijn geconfigureerd via het register 'TelemetryProxyServer' of GPO.
> - Voor Windows 10 of Windows Server 2019- hoewel u TelemetryProxyServer mag gebruiken, moet deze naar een standaardproxyapparaat of -apparaat wijzen.
> - Daarnaast moet Windows 10 of Windows Server 2019 in niet-verbonden omgevingen certificaten vertrouwenslijsten offline kunnen bijwerken via een intern bestand of webserver.
> - Zie Een bestand of webserver configureren om de CTL-bestanden te downloaden voor meer informatie over het offline bijwerken van [CTL's.](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files)

Zie de volgende artikelen voor meer informatie over onboardingmethoden:
- [Onboarden eerdere versies van Windows](/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [Onboard servers to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [Instellingen voor apparaatproxy en internetverbinding configureren](/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premises-devices"></a>On-premises apparaten

- Azure Log Analytics (voorheen BEKEND als OMS Gateway) instellen als proxy of hub:
  - [Azure Log Analytics Agent](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - [Microsoft Monitoring Agent (MMA) installeren](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) en configureren, wijs Defender for Endpoint Workspace-sleutel voor & id

- Offlineapparaten in hetzelfde netwerk van Azure Log Analytics
  -  Configureer MMA om te wijzen naar:
     - Azure Log Analytics IP als proxy
     - Defender for Endpoint workspace key & ID

## <a name="azure-virtual-machines"></a>Virtuele Azure-machines
- Azure [Log Analytics-werkruimte configureren en inschakelen](/azure/azure-monitor/platform/gateway)

    - Azure Log Analytics Gateway (voorheen OMS Gateway genoemd) instellen als proxy of hub:
      - [Azure Log Analytics Gateway](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - [Microsoft Monitoring Agent (MMA) installeren](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) en configureren, wijs Defender for Endpoint Workspace-sleutel voor & id
    - Offline Azure VMs in hetzelfde netwerk van OMS Gateway
      - Azure Log Analytics IP configureren als een proxy
      - Azure Log Analytics Workspace Key & ID

    - Azure Defender
      - [Werkruimte voor \> beveiligingsbeleidlogboekanalyse](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [Threat Detection \> Allow Defender for Endpoint to access my data](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        Zie Werken met [beveiligingsbeleid voor meer informatie.](/azure/security-center/tutorial-security-policy)
