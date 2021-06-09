---
title: Microsoft Defender Antivirus configureren met WMI
description: Meer informatie over het configureren en beheren Microsoft Defender Antivirus met WMI-scripts voor het ophalen, wijzigen en bijwerken van instellingen in Microsoft Defender voor Eindpunt.
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
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="72cd7-104">Gebruik Windows Management Instrumentation (WMI) voor het configureren en beheren van Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="72cd7-104">Use Windows Management Instrumentation (WMI) to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="72cd7-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="72cd7-105">**Applies to:**</span></span>

- [<span data-ttu-id="72cd7-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="72cd7-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="72cd7-107">Windows Management Instrumentation (WMI) is een scripting-interface waarmee u instellingen kunt ophalen, wijzigen en bijwerken.</span><span class="sxs-lookup"><span data-stu-id="72cd7-107">Windows Management Instrumentation (WMI) is a scripting interface that allows you to retrieve, modify, and update settings.</span></span>

<span data-ttu-id="72cd7-108">Lees meer over WMI in de [bibliotheek Microsoft Developer Network System Administration](/windows/win32/wmisdk/wmi-start-page).</span><span class="sxs-lookup"><span data-stu-id="72cd7-108">Read more about WMI at the [Microsoft Developer Network System Administration library](/windows/win32/wmisdk/wmi-start-page).</span></span>

<span data-ttu-id="72cd7-109">Microsoft Defender Antivirus heeft een aantal specifieke WMI-klassen die kunnen worden gebruikt om de meeste van dezelfde functies uit te voeren als groepsbeleid en andere beheerhulpmiddelen.</span><span class="sxs-lookup"><span data-stu-id="72cd7-109">Microsoft Defender Antivirus has a number of specific WMI classes that can be used to perform most of the same functions as Group Policy and other management tools.</span></span> <span data-ttu-id="72cd7-110">Veel van de klassen zijn vergelijkbaar met [Defender PowerShell-cmdlets.](use-powershell-cmdlets-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="72cd7-110">Many of the classes are analogous to [Defender PowerShell cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="72cd7-111">De [MSDN-Windows Defender WMIv2 Provider-naslagbibliotheek](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) bevat de beschikbare WMI-klassen voor Microsoft Defender Antivirus en bevat voorbeeldscripts.</span><span class="sxs-lookup"><span data-stu-id="72cd7-111">The [MSDN Windows Defender WMIv2 Provider reference library](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) lists the available WMI classes for Microsoft Defender Antivirus, and includes example scripts.</span></span>

<span data-ttu-id="72cd7-112">Wijzigingen die met WMI zijn aangebracht, zijn van invloed op lokale instellingen op het eindpunt waar de wijzigingen worden geïmplementeerd of aangebracht.</span><span class="sxs-lookup"><span data-stu-id="72cd7-112">Changes made with WMI will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="72cd7-113">Dit betekent dat implementaties van beleid met groepsbeleid, Microsoft Endpoint Configuration Manager of Microsoft Intune wijzigingen die met WMI zijn aangebracht, kunnen overschrijven.</span><span class="sxs-lookup"><span data-stu-id="72cd7-113">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with WMI.</span></span> 

<span data-ttu-id="72cd7-114">U kunt [configureren welke instellingen lokaal kunnen worden overschrijven met lokale beleidsbe perken.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="72cd7-114">You can [configure which settings can be overridden locally  with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="72cd7-115">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="72cd7-115">Related topics</span></span>

- [<span data-ttu-id="72cd7-116">Referentieonderwerpen voor beheer- en configuratiehulpmiddelen</span><span class="sxs-lookup"><span data-stu-id="72cd7-116">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="72cd7-117">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="72cd7-117">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)