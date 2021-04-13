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
ms.openlocfilehash: 912136a7229ec55b7f1644aebc946f63acb68040
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690618"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="a0ef3-104">PowerShell-cmdlets gebruiken om Microsoft Defender Antivirus te configureren en te beheren</span><span class="sxs-lookup"><span data-stu-id="a0ef3-104">Use PowerShell cmdlets to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a0ef3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a0ef3-105">**Applies to:**</span></span>

- [<span data-ttu-id="a0ef3-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="a0ef3-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a0ef3-107">U kunt PowerShell gebruiken om verschillende functies uit te voeren in Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-107">You can use PowerShell to perform various functions in Windows Defender.</span></span> <span data-ttu-id="a0ef3-108">Net als bij de opdrachtprompt of opdrachtregel is PowerShell een taakgebaseerd opdrachtregelshell en scriptingtaal die speciaal is ontworpen voor systeembeheer.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-108">Similar to the command prompt or command line, PowerShell is a task-based command-line shell and scripting language designed especially for system administration.</span></span> <span data-ttu-id="a0ef3-109">U kunt er meer over lezen op de [PowerShell-hub op MSDN.](/previous-versions/msdn10/mt173057(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="a0ef3-109">You can read more about it at the [PowerShell hub on MSDN](/previous-versions/msdn10/mt173057(v=msdn.10)).</span></span>

<span data-ttu-id="a0ef3-110">Zie het [onderwerp Defender-cmdlets](/powershell/module/defender) voor een lijst met de cmdlets en de functies en beschikbare parameters.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-110">For a list of the cmdlets and their functions and available parameters, see the [Defender cmdlets](/powershell/module/defender) topic.</span></span>

<span data-ttu-id="a0ef3-111">PowerShell-cmdlets zijn het meest handig in Windows Server-omgevingen die niet afhankelijk zijn van een grafische gebruikersinterface (GUI) om software te configureren.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-111">PowerShell cmdlets are most useful in Windows Server environments that don't rely on a graphical user interface (GUI) to configure software.</span></span>

> [!NOTE]
> <span data-ttu-id="a0ef3-112">PowerShell-cmdlets mogen niet worden gebruikt als vervanging voor een volledige netwerkbeleidsbeheerinfrastructuur, zoals [Microsoft Endpoint Configuration Manager,](/configmgr) [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))of Microsoft Defender Antivirus Group Policy [ADMX-sjablonen.](https://www.microsoft.com/download/101445)</span><span class="sxs-lookup"><span data-stu-id="a0ef3-112">PowerShell cmdlets should not be used as a replacement for a full network policy management infrastructure, such as [Microsoft Endpoint Configuration Manager](/configmgr), [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), or [Microsoft Defender Antivirus Group Policy ADMX templates](https://www.microsoft.com/download/101445).</span></span>

<span data-ttu-id="a0ef3-113">Wijzigingen die zijn aangebracht met PowerShell, zijn van invloed op lokale instellingen op het eindpunt waar de wijzigingen worden geïmplementeerd of aangebracht.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-113">Changes made with PowerShell will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="a0ef3-114">Dit betekent dat implementaties van beleid met groepsbeleid, Microsoft Endpoint Configuration Manager of Microsoft Intune wijzigingen kunnen overschrijven die zijn aangebracht met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-114">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with PowerShell.</span></span>

<span data-ttu-id="a0ef3-115">U kunt [configureren welke instellingen lokaal kunnen worden overschrijven met lokale beleidsbe perken.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a0ef3-115">You can [configure which settings can be overridden locally with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="a0ef3-116">PowerShell wordt meestal geïnstalleerd onder de `%SystemRoot%\system32\WindowsPowerShell` map.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-116">PowerShell is typically installed under the folder `%SystemRoot%\system32\WindowsPowerShell`.</span></span>

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a><span data-ttu-id="a0ef3-117">Microsoft Defender Antivirus PowerShell-cmdlets gebruiken</span><span class="sxs-lookup"><span data-stu-id="a0ef3-117">Use Microsoft Defender Antivirus PowerShell cmdlets</span></span>

1. <span data-ttu-id="a0ef3-118">Typ powershell in de **windows-zoekbalk.**</span><span class="sxs-lookup"><span data-stu-id="a0ef3-118">In the Windows search bar, type **powershell**.</span></span>
2. <span data-ttu-id="a0ef3-119">Selecteer **Windows PowerShell** in de resultaten om de interface te openen.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-119">Select **Windows PowerShell** from the results to open the interface.</span></span>
3. <span data-ttu-id="a0ef3-120">Voer de opdracht PowerShell en eventuele parameters in.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-120">Enter the PowerShell command and any parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="a0ef3-121">Mogelijk moet u PowerShell openen in de beheerdersmodus.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-121">You may need to open PowerShell in administrator mode.</span></span> <span data-ttu-id="a0ef3-122">Klik met de rechtermuisknop op het item in het menu Start, klik op **Uitvoeren als beheerder** en klik op **Ja** bij de machtigingenprompt.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-122">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span>

<span data-ttu-id="a0ef3-123">Als u onlinehulp wilt openen voor een van de cmdlets, typt u het volgende:</span><span class="sxs-lookup"><span data-stu-id="a0ef3-123">To open online help for any of the cmdlets type the following:</span></span>

```PowerShell
Get-Help <cmdlet> -Online
```

<span data-ttu-id="a0ef3-124">Laat de `-online` parameter weg om hulp in de lokale cache op te halen.</span><span class="sxs-lookup"><span data-stu-id="a0ef3-124">Omit the `-online` parameter to get locally cached help.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a0ef3-125">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="a0ef3-125">Related topics</span></span>

- [<span data-ttu-id="a0ef3-126">Referentieonderwerpen voor beheer- en configuratiehulpmiddelen</span><span class="sxs-lookup"><span data-stu-id="a0ef3-126">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a0ef3-127">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="a0ef3-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="a0ef3-128">Microsoft Defender Antivirus Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a0ef3-128">Microsoft Defender Antivirus Cmdlets</span></span>](/powershell/module/defender/?view=win10-ps)