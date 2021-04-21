---
title: Problemen met ontbrekende gebeurtenissen of waarschuwingen oplossen voor Microsoft Defender voor Eindpunt op Linux
description: Problemen met ontbrekende gebeurtenissen oplossen of problemen met waarschuwingen in Microsoft Defender voor Eindpunt op Linux oplossen.
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
ms.openlocfilehash: 40d394a4fc7349789dea9bd96ccdaf71067ab39e
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903996"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="4fd99-104">Problemen met ontbrekende gebeurtenissen of waarschuwingen oplossen voor Microsoft Defender voor Eindpunt op Linux</span><span class="sxs-lookup"><span data-stu-id="4fd99-104">Troubleshoot missing events or alerts issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4fd99-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4fd99-105">**Applies to:**</span></span>

- [<span data-ttu-id="4fd99-106">Microsoft Defender voor Eindpunt op Linux</span><span class="sxs-lookup"><span data-stu-id="4fd99-106">Microsoft Defender for Endpoint on Linux</span></span>](microsoft-defender-endpoint-linux.md)

<span data-ttu-id="4fd99-107">In dit artikel vindt u enkele algemene stappen om ontbrekende gebeurtenissen of waarschuwingen in de portal van het [beveiligingscentrum te](https://securitycenter.windows.com/) beperken.</span><span class="sxs-lookup"><span data-stu-id="4fd99-107">This article provides some general steps to mitigate missing events or alerts in the [security center](https://securitycenter.windows.com/) portal.</span></span>

<span data-ttu-id="4fd99-108">Wanneer **Microsoft Defender voor Eindpunt correct** is geïnstalleerd op een apparaat, wordt er een _apparaatpagina_ gegenereerd in de portal.</span><span class="sxs-lookup"><span data-stu-id="4fd99-108">Once **Microsoft Defender for Endpoint** has been installed properly on a device, a _device page_ will be generated in the portal.</span></span> <span data-ttu-id="4fd99-109">U kunt alle opgenomen gebeurtenissen bekijken op het tabblad Tijdlijn op de apparaatpagina of op de pagina geavanceerd zoeken.</span><span class="sxs-lookup"><span data-stu-id="4fd99-109">You can review all recorded events in the timeline tab in the device page, or in advanced hunting page.</span></span> <span data-ttu-id="4fd99-110">In deze sectie wordt een probleem opgelost met het geval dat sommige of alle verwachte gebeurtenissen ontbreken.</span><span class="sxs-lookup"><span data-stu-id="4fd99-110">This section troubleshoots the case of some or all expected events are missing.</span></span>
<span data-ttu-id="4fd99-111">Als bijvoorbeeld alle _createdFile-gebeurtenissen_ ontbreken.</span><span class="sxs-lookup"><span data-stu-id="4fd99-111">For instance, if all _CreatedFile_ events are missing.</span></span>

## <a name="missing-network-and-login-events"></a><span data-ttu-id="4fd99-112">Ontbrekende netwerk- en aanmeldingsgebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="4fd99-112">Missing network and login events</span></span>

<span data-ttu-id="4fd99-113">Microsoft Defender for Endpoint heeft framework van `audit` linux gebruikt om netwerk- en aanmeldingsactiviteiten bij te houden.</span><span class="sxs-lookup"><span data-stu-id="4fd99-113">Microsoft Defender for Endpoint utilized `audit` framework from linux to track network and login activity.</span></span>

1. <span data-ttu-id="4fd99-114">Controleer of het auditkader werkt.</span><span class="sxs-lookup"><span data-stu-id="4fd99-114">Make sure audit framework is working.</span></span>

    ```bash
    service auditd status
    ```

    <span data-ttu-id="4fd99-115">verwachte uitvoer:</span><span class="sxs-lookup"><span data-stu-id="4fd99-115">expected output:</span></span>

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

2. <span data-ttu-id="4fd99-116">Als `auditd` deze is gemarkeerd als gestopt, start u deze.</span><span class="sxs-lookup"><span data-stu-id="4fd99-116">If `auditd` is marked as stopped, start it.</span></span>

    ```bash
    service auditd start
    ```

<span data-ttu-id="4fd99-117">**In SLES-systemen** is SYSCALL-auditing in mogelijk standaard uitgeschakeld en kan er rekening worden gehouden `auditd` met ontbrekende gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="4fd99-117">**On SLES** systems, SYSCALL auditing in `auditd` might be disabled by default and can be accounted for missing events.</span></span>

1. <span data-ttu-id="4fd99-118">Als u wilt valideren dat SYSCALL-auditing niet is uitgeschakeld, vermeldt u de huidige controleregels:</span><span class="sxs-lookup"><span data-stu-id="4fd99-118">To validate that SYSCALL auditing is not disabled, list the current audit rules:</span></span>

    ```bash
    sudo auditctl -l
    ```

    <span data-ttu-id="4fd99-119">als de volgende regel aanwezig is, verwijdert u deze of bewerkt u deze om ervoor te zorgen dat Microsoft Defender voor Eindpunt specifieke SYSCALLs kan bijhouden.</span><span class="sxs-lookup"><span data-stu-id="4fd99-119">if the following line is present, remove it or edit it to enable Microsoft Defender for Endpoint to track specific SYSCALLs.</span></span>

    ```output
    -a task, never
    ```

    <span data-ttu-id="4fd99-120">auditregels bevinden zich op `/etc/audit/rules.d/audit.rules` .</span><span class="sxs-lookup"><span data-stu-id="4fd99-120">audit rules are located at `/etc/audit/rules.d/audit.rules`.</span></span>

## <a name="missing-file-events"></a><span data-ttu-id="4fd99-121">Ontbrekende bestandsgebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="4fd99-121">Missing file events</span></span>

<span data-ttu-id="4fd99-122">Bestandsgebeurtenissen worden verzameld met `fanotify` framework.</span><span class="sxs-lookup"><span data-stu-id="4fd99-122">File events are collected with `fanotify` framework.</span></span> <span data-ttu-id="4fd99-123">Als sommige of alle bestandsgebeurtenissen ontbreken, moet u ervoor zorgen dat dit is ingeschakeld op het apparaat en of `fanotify` het bestandssysteem wordt [ondersteund.](microsoft-defender-endpoint-linux.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="4fd99-123">In case some or all file events are missing, make sure `fanotify` is enabled on the device and that the file system is [supported](microsoft-defender-endpoint-linux.md#system-requirements).</span></span>

<span data-ttu-id="4fd99-124">Vermeld de bestandssystemen op de computer met:</span><span class="sxs-lookup"><span data-stu-id="4fd99-124">List the filesystems on the machine with:</span></span>

```bash
df -Th
```
