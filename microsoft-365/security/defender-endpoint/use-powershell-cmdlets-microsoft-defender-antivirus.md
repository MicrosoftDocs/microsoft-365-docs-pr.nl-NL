---
title: PowerShell-cmdlets gebruiken om Microsoft Defender AV te configureren en uit te voeren
description: In Windows 10 kunt u PowerShell-cmdlets gebruiken om scans uit te voeren, beveiligingsinformatie bij te werken en instellingen te wijzigen in Microsoft Defender Antivirus.
keywords: scan, opdrachtregel, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 0fd1e6b2eec1be722af58e0753e158c050b56c6b
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51749874"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a>PowerShell-cmdlets gebruiken om Microsoft Defender Antivirus te configureren en te beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

U kunt PowerShell gebruiken om verschillende functies uit te voeren in Windows Defender. Net als bij de opdrachtprompt of opdrachtregel is PowerShell een taakgebaseerd opdrachtregelshell en scriptingtaal die speciaal is ontworpen voor systeembeheer. U kunt er meer over lezen op de [PowerShell-hub op MSDN.](/previous-versions/msdn10/mt173057(v=msdn.10))

Zie het [onderwerp Defender-cmdlets](/powershell/module/defender) voor een lijst met de cmdlets en de functies en beschikbare parameters.

PowerShell-cmdlets zijn het meest handig in Windows Server-omgevingen die niet afhankelijk zijn van een grafische gebruikersinterface (GUI) om software te configureren.

> [!NOTE]
> PowerShell-cmdlets mogen niet worden gebruikt als vervanging voor een volledige netwerkbeleidsbeheerinfrastructuur, zoals [Microsoft Endpoint Configuration Manager,](/configmgr) [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))of Microsoft Defender Antivirus Group Policy [ADMX-sjablonen.](https://www.microsoft.com/download/101445)

Wijzigingen die zijn aangebracht met PowerShell, zijn van invloed op lokale instellingen op het eindpunt waar de wijzigingen worden geïmplementeerd of aangebracht. Dit betekent dat implementaties van beleid met groepsbeleid, Microsoft Endpoint Configuration Manager of Microsoft Intune wijzigingen kunnen overschrijven die zijn aangebracht met PowerShell.

U kunt [configureren welke instellingen lokaal kunnen worden overschrijven met lokale beleidsbe perken.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

PowerShell wordt meestal geïnstalleerd onder de `%SystemRoot%\system32\WindowsPowerShell` map.

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a>Microsoft Defender Antivirus PowerShell-cmdlets gebruiken

1. Typ powershell in de **windows-zoekbalk.**
2. Selecteer **Windows PowerShell** in de resultaten om de interface te openen.
3. Voer de opdracht PowerShell en eventuele parameters in.

> [!NOTE]
> Mogelijk moet u PowerShell openen in de beheerdersmodus. Klik met de rechtermuisknop op het item in het menu Start, klik op **Uitvoeren als beheerder** en klik op **Ja** bij de machtigingenprompt.

Als u onlinehulp wilt openen voor een van de cmdlets, typt u het volgende:

```PowerShell
Get-Help <cmdlet> -Online
```

Laat de `-online` parameter weg om hulp in de lokale cache op te halen.

## <a name="related-topics"></a>Verwante onderwerpen

- [Referentieonderwerpen voor beheer- en configuratiehulpmiddelen](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus Cmdlets](/powershell/module/defender)