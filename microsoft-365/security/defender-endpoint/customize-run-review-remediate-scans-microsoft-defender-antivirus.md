---
title: Geplande en on-demand scans uitvoeren en aanpassen
description: Microsoft Defender Antivirus scans aanpassen en starten op eindpunten in uw netwerk.
keywords: scannen, plannen, aanpassen, uitsluitingen, bestanden uitsluiten, herstellen, resultaten scannen, quarantaine, bedreiging verwijderen, quick scan, volledige scan, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8aa735cf7490a451a5758c3799bd08dff61f8063
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690026"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a>De resultaten van Microsoft Defender Antivirus scans en herstel aanpassen, starten en controleren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

U kunt Group Policy, PowerShell en Windows Management Instrumentation (WMI) gebruiken om Microsoft Defender Antivirus scans te configureren. 

## <a name="in-this-section"></a>In deze sectie

Onderwerp | Omschrijving
---|---
[Bestands-, map- en proces-geopende bestandsuitsluitingen configureren en valideren in Microsoft Defender Antivirus scans](configure-exclusions-microsoft-defender-antivirus.md) | U kunt bestanden (inclusief bestanden die zijn gewijzigd door opgegeven processen) en mappen uitsluiten van scans op aanvraag, geplande scans en altijd in realtime beveiligingscontrole en scannen
[Scanopties voor Microsoft Defender Antivirus configureren](configure-advanced-scan-types-microsoft-defender-antivirus.md) | U kunt Microsoft Defender Antivirus zo configureren dat bepaalde typen e-mailopslagbestanden, back-up- of herstelpunten en gearchiveerde bestanden (zoals ZIP-bestanden) in scans worden opgeslagen. U kunt ook netwerkbestandsscans inschakelen
[Herstel configureren voor scans](configure-remediation-microsoft-defender-antivirus.md) | Configureren wat Microsoft Defender Antivirus moet doen wanneer een bedreiging wordt gedetecteerd en hoe lang in quarantaine geplaatste bestanden moeten worden bewaard in de quarantainemap
[Geplande scans configureren](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | Terugkerende (geplande) scans instellen, inclusief wanneer ze moeten worden uitgevoerd en of ze als volledige of snelle scans moeten worden uitgevoerd
[Scans configureren en uitvoeren](run-scan-microsoft-defender-antivirus.md) | On-demand scans uitvoeren en configureren met PowerShell, Windows Management Instrumentation of afzonderlijk op eindpunten met de Windows Security-app
[Scanresultaten controleren](review-scan-results-microsoft-defender-antivirus.md) | Bekijk de resultaten van scans met Microsoft Endpoint Configuration Manager, Microsoft Intune of de Windows Security-app