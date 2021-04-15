---
title: Microsoft Defender Antivirus configureren met WMI
description: Lees hoe u Microsoft Defender Antivirus configureert en beheert met behulp van WMI-scripts voor het ophalen, wijzigen en bijwerken van instellingen in Microsoft Defender voor Eindpunt.
keywords: wmi, scripts, windows management instrumentation, configuratie
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
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 25518383131e4f7ecb7451965ef7a42b1c6eee4b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764061"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a>Windows Management Instrumentation (WMI) gebruiken om Microsoft Defender Antivirus te configureren en te beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Windows Management Instrumentation (WMI) is een scripting-interface waarmee u instellingen kunt ophalen, wijzigen en bijwerken.

Lees meer over WMI in de [bibliotheek Microsoft Developer Network System Administration](/windows/win32/wmisdk/wmi-start-page).

Microsoft Defender Antivirus heeft een aantal specifieke WMI-klassen die kunnen worden gebruikt om de meeste van dezelfde functies uit te voeren als groepsbeleid en andere beheerhulpmiddelen. Veel van de klassen zijn vergelijkbaar met [Defender PowerShell-cmdlets.](use-powershell-cmdlets-microsoft-defender-antivirus.md)

De [MSDN Windows Defender WMIv2 Provider-naslagbibliotheek](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) bevat de beschikbare WMI-klassen voor Microsoft Defender Antivirus en bevat voorbeeldscripts.

Wijzigingen die met WMI zijn aangebracht, zijn van invloed op lokale instellingen op het eindpunt waar de wijzigingen worden geïmplementeerd of aangebracht. Dit betekent dat implementaties van beleid met groepsbeleid, Microsoft Endpoint Configuration Manager of Microsoft Intune wijzigingen kunnen overschrijven die zijn aangebracht met WMI. 

U kunt [configureren welke instellingen lokaal kunnen worden overschrijven met lokale beleidsbe perken.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

## <a name="related-topics"></a>Verwante onderwerpen

- [Referentieonderwerpen voor beheer- en configuratiehulpmiddelen](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)