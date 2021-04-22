---
title: Offboard-apparaten van de Microsoft Defender for Endpoint-service
description: Onboard Windows 10-apparaten, servers, niet-Windows-apparaten van de Microsoft Defender for Endpoint-service
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
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a>Offboard-apparaten van de Microsoft Defender for Endpoint-service

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Platforms**
- macOS
- Linux
- Windows Server 2012 R2
- Windows Server 2016

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

Volg de bijbehorende instructies, afhankelijk van uw voorkeursimplementatiemethode.

>[!NOTE]
> De status van een apparaat wordt 7 dagen na het offboarden overgezet naar [Inactief.](fix-unhealthy-sensors.md#inactive-devices) <br> De gegevens van niet-geboarde apparaten (zoals tijdlijn, waarschuwingen, beveiligingsproblemen, enzovoort) blijven in de portal staan totdat de geconfigureerde bewaarperiode [verloopt.](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) <br>
> Het profiel van het apparaat (zonder [](machines-view-overview.md) gegevens) blijft niet langer dan 180 dagen in de lijst met apparaten staan.
> Bovendien worden apparaten die niet actief zijn in de afgelopen 30 dagen, niet meegeholpen aan [](tvm-exposure-score.md) de gegevens die de blootstellingsscore voor bedreigings- en kwetsbaarheidsbeheer van uw organisatie en Microsoft Secure Score voor apparaten weerspiegelen. <br>
> Als u alleen actieve apparaten wilt weergeven, kunt u filteren op [status,](machines-view-overview.md#health-state) [apparaatlabels](machine-tags.md) of [machinegroepen.](machine-groups.md) 

## <a name="offboard-windows-10-devices"></a>Offboard Windows 10-apparaten
- [Offboard-apparaten met een lokaal script](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [Offboard-apparaten met groepsbeleid](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [Offboard-apparaten met hulpprogramma's voor mobiel apparaatbeheer](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a>Offboard-servers
- [Offboard-servers](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a>Offboard niet-Windows-apparaten
- [Offboard niet-Windows-apparaten](configure-endpoints-non-windows.md#offboard-non-windows-devices)

