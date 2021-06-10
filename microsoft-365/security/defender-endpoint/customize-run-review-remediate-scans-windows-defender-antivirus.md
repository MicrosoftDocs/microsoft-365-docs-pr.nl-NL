---
title: Geplande en on-demand scans uitvoeren en aanpassen
description: U kunt de Microsoft Defender Antivirus op eindpunten in uw netwerk aanpassen en starten.
keywords: scannen, plannen, aanpassen, uitsluitingen, bestanden uitsluiten, herstel, scanresultaten, quarantaine, bedreiging verwijderen, quick scan, volledige scan, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f3e0cc7ffccf02e24b9746d539a44d3a72810ead
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286153"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans--remediation"></a>De resultaten van de scans van Microsoft Defender Antivirus en & aanpassen, starten en controleren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

U kunt Groepsbeleid, PowerShell en Windows Management Instrumentation (WMI) gebruiken om de Microsoft Defender Antivirus configureren. 

## <a name="in-this-section"></a>In deze sectie

| Artikel | Beschrijving |
|:---|:---|
|[Bestands-, map- en proces-geopende bestandsuitsluitingen configureren en valideren in Microsoft Defender Antivirus scans](configure-exclusions-microsoft-defender-antivirus.md) | U kunt bestanden (inclusief bestanden die zijn gewijzigd door opgegeven processen) en mappen uitsluiten van scans op aanvraag, geplande scans en altijd in realtime beveiligingscontrole en scannen |
|[Microsoft Defender Antivirus-scanopties configureren](configure-advanced-scan-types-microsoft-defender-antivirus.md) | U kunt Microsoft Defender Antivirus instellen dat bepaalde typen e-mailopslagbestanden, back-up- of reparse-punten en gearchiveerde bestanden (zoals .zip bestanden) in scans worden opgeslagen. U kunt ook netwerkbestandsscans inschakelen |
|[Herstel configureren voor scans](configure-remediation-microsoft-defender-antivirus.md) | Configureren wat Microsoft Defender Antivirus moet doen wanneer er een bedreiging wordt gedetecteerd en hoe lang in quarantaine geplaatste bestanden moeten worden bewaard in de quarantainemap |
|[Geplande scans configureren](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | Terugkerende (geplande) scans instellen, inclusief wanneer ze moeten worden uitgevoerd en of ze als volledige of snelle scans moeten worden uitgevoerd |
|[Scans configureren en uitvoeren](run-scan-microsoft-defender-antivirus.md) | On-demand scans uitvoeren en configureren met behulp van PowerShell, Windows Management Instrumentation of afzonderlijk op eindpunten met de Windows-beveiliging app |
|[Scanresultaten controleren](review-scan-results-microsoft-defender-antivirus.md) | Bekijk de resultaten van scans met Microsoft Endpoint Configuration Manager, Microsoft Intune of de Windows-beveiliging app |