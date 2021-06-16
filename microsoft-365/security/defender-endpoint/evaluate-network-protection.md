---
title: Netwerkbeveiliging evalueren
description: Bekijk hoe netwerkbeveiliging werkt door veelvoorkomende scenario's te testen die worden beschermd tegen.
keywords: Netwerkbeveiliging, exploits, schadelijke website, ip, domein, domeinen, evalueren, testen, demo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 03d05966401c8f3a8bdcec413e85c9a6d2a3ec5c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926569"
---
# <a name="evaluate-network-protection"></a>Netwerkbeveiliging evalueren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- - [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[Netwerkbeveiliging](network-protection.md) helpt voorkomen dat werknemers elke toepassing gebruiken om toegang te krijgen tot gevaarlijke domeinen die phishingpraktijken, exploits en andere schadelijke inhoud op internet kunnen hosten.

In dit artikel kunt u netwerkbeveiliging evalueren door de functie in te stellen en u te begeleiden naar een testsite. De sites in dit evaluatieartikel zijn niet schadelijk. Ze zijn speciaal gemaakt websites die zich voordoen als schadelijk. De site repliceert het gedrag dat zou plaatsvinden als een gebruiker een schadelijke site of domein bezocht.

> [!TIP]
> U kunt ook naar de Microsoft Defender Testground-website op demo.wd.microsoft.com [om](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) te zien hoe andere beveiligingsfuncties werken.

## <a name="enable-network-protection-in-audit-mode"></a>Netwerkbeveiliging inschakelen in de auditmodus

Schakel netwerkbeveiliging in de auditmodus in om te zien welke IP-adressen en domeinen zouden zijn geblokkeerd. U kunt ervoor zorgen dat dit geen invloed heeft op line-of-business-apps of een idee krijgen van hoe vaak blokken voorkomen.

1. Typ **powershell** in het menu Start, klik met de **rechtermuisknop Windows PowerShell** en selecteer Uitvoeren als **beheerder**
2. Voer de volgende cmdlet in:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a>Een (nep)kwaadwillend domein bezoeken

1. Open Internet Explorer, Google Chrome of een andere browser naar keuze.

1. Ga naar [https://smartscreentestratings2.net](https://smartscreentestratings2.net).

De netwerkverbinding is toegestaan en er wordt een testbericht weergegeven.

![Voorbeeldmelding met de melding Verbinding geblokkeerd: De IT-beheerder heeft Windows-beveiliging netwerkverbinding geblokkeerd. Neem contact op met uw IT-helpdesk.](/microsoft-365/security/defender-endpoint/images/np-notif)

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Netwerkbeveiligingsgebeurtenissen bekijken in Windows Event Viewer

Als u apps wilt bekijken die zijn geblokkeerd, opent u Gebeurtenisviewer en filtert u op Gebeurtenis-id 1125 in het microsoft-Windows-Windows-Defender/Operationeel logboek. In de volgende tabel worden alle netwerkbeveiligingsgebeurtenissen vermeld.

| Gebeurtenis-id | Leveren/bron | Omschrijving |
|-|-|-|
|5007 | Windows Defender (operationeel) | Gebeurtenis wanneer instellingen worden gewijzigd |
|1125 | Windows Defender (operationeel) | Gebeurtenis wanneer een netwerkverbinding wordt gecontroleerd |
|1126 | Windows Defender (operationeel) | Gebeurtenis wanneer een netwerkverbinding is geblokkeerd |

## <a name="see-also"></a>Zie ook

* [Netwerkbeveiliging](network-protection.md)
* [Netwerkbeveiliging inschakelen](enable-network-protection.md)
* [Problemen met netwerkbeveiliging oplossen](troubleshoot-np.md)
