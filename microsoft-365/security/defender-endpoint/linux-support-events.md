---
title: Problemen met ontbrekende gebeurtenissen of waarschuwingen oplossen voor MICROSOFT Defender ATP voor Linux
description: Problemen met ontbrekende gebeurtenissen oplossen of problemen met waarschuwingen in Microsoft Defender ATP voor Linux oplossen.
keywords: microsoft, defender, atp, linux, events
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5981cb75b4c835390e27d902b5950e3c68305200
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687452"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Problemen met ontbrekende gebeurtenissen of waarschuwingen oplossen voor Microsoft Defender voor Eindpunt op Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt op Linux](microsoft-defender-endpoint-linux.md)

In dit artikel vindt u enkele algemene stappen om ontbrekende gebeurtenissen of waarschuwingen in de portal van het [beveiligingscentrum te](https://securitycenter.windows.com/) beperken.

Wanneer **Microsoft Defender voor Eindpunt correct** is geïnstalleerd op een apparaat, wordt er een _apparaatpagina_ gegenereerd in de portal. U kunt alle opgenomen gebeurtenissen bekijken op het tabblad Tijdlijn op de apparaatpagina of op de pagina geavanceerd zoeken. In deze sectie wordt een probleem opgelost met het geval dat sommige of alle verwachte gebeurtenissen ontbreken.
Als bijvoorbeeld alle _createdFile-gebeurtenissen_ ontbreken.

## <a name="missing-network-and-login-events"></a>Ontbrekende netwerk- en aanmeldingsgebeurtenissen

Microsoft Defender for Endpoint heeft framework van `audit` linux gebruikt om netwerk- en aanmeldingsactiviteiten bij te houden.

1. Controleer of het auditkader werkt.

    ```bash
    service auditd status
    ```

    verwachte uitvoer:

    ```output
    ● auditd.service - Security Auditing Service
    Loaded: loaded (/usr/lib/systemd/system/auditd.service; enabled; vendor preset: enabled)
    Active: active (running) since Mon 2020-12-21 10:48:02 IST; 2 weeks 0 days ago
        Docs: man:auditd(8)
            https://github.com/linux-audit/audit-documentation
    Process: 16689 ExecStartPost=/sbin/augenrules --load (code=exited, status=1/FAILURE)
    Process: 16665 ExecStart=/sbin/auditd (code=exited, status=0/SUCCESS)
    Main PID: 16666 (auditd)
        Tasks: 25
    CGroup: /system.slice/auditd.service
            ├─16666 /sbin/auditd
            ├─16668 /sbin/audispd
            ├─16670 /usr/sbin/sedispatch
            └─16671 /opt/microsoft/mdatp/sbin/mdatp_audisp_plugin -d
    ```

2. Als `auditd` deze is gemarkeerd als gestopt, start u deze.

    ```bash
    service auditd start
    ```

**In SLES-systemen** is SYSCALL-auditing in mogelijk standaard uitgeschakeld en kan er rekening worden gehouden `auditd` met ontbrekende gebeurtenissen.

1. Als u wilt valideren dat SYSCALL-auditing niet is uitgeschakeld, vermeldt u de huidige controleregels:

    ```bash
    sudo auditctl -l
    ```

    als de volgende regel aanwezig is, verwijdert u deze of bewerkt u deze om ervoor te zorgen dat Microsoft Defender voor Eindpunt specifieke SYSCALLs kan bijhouden.

    ```output
    -a task, never
    ```

    auditregels bevinden zich op `/etc/audit/rules.d/audit.rules` .

## <a name="missing-file-events"></a>Ontbrekende bestandsgebeurtenissen

Bestandsgebeurtenissen worden verzameld met `fanotify` framework. Als sommige of alle bestandsgebeurtenissen ontbreken, moet u ervoor zorgen dat dit is ingeschakeld op het apparaat en of `fanotify` het bestandssysteem wordt [ondersteund.](microsoft-defender-endpoint-linux.md#system-requirements)

Vermeld de bestandssystemen op de computer met:

```bash
df -Th
```
