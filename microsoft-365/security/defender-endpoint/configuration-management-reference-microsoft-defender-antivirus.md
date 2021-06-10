---
title: Uw Windows Defender in uw bedrijf beheren
description: Meer informatie over het gebruik van groepsbeleid, configuratiebeheer, PowerShell, WMI, Intune en de opdrachtregel voor het beheren van Microsoft Defender AV
keywords: groepsbeleid, gpo, config manager, sccm, scep, powershell, wmi, intune, defender, antivirus, antimalware, beveiliging, beveiliging
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 2265f3680e425ade062d444685fbd8873eaa02ca
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274962"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a><span data-ttu-id="a11af-104">Uw Microsoft Defender Antivirus in uw bedrijf beheren</span><span class="sxs-lookup"><span data-stu-id="a11af-104">Manage Microsoft Defender Antivirus in your business</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a11af-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a11af-105">**Applies to:**</span></span>

- [<span data-ttu-id="a11af-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="a11af-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a11af-107">U kunt uw Microsoft Defender Antivirus met de volgende hulpmiddelen beheren en configureren:</span><span class="sxs-lookup"><span data-stu-id="a11af-107">You can manage and configure Microsoft Defender Antivirus with the following tools:</span></span>

- <span data-ttu-id="a11af-108">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (nu onderdeel van Microsoft Endpoint Manager)</span><span class="sxs-lookup"><span data-stu-id="a11af-108">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (now part of Microsoft Endpoint Manager)</span></span>
- <span data-ttu-id="a11af-109">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (nu onderdeel van Microsoft Endpoint Manager)</span><span class="sxs-lookup"><span data-stu-id="a11af-109">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (now part of Microsoft Endpoint Manager)</span></span>
- [<span data-ttu-id="a11af-110">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="a11af-110">Group Policy</span></span>](./use-group-policy-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a11af-111">PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="a11af-111">PowerShell cmdlets</span></span>](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a11af-112">Windows Beheerinstrumentatie (WMI)</span><span class="sxs-lookup"><span data-stu-id="a11af-112">Windows Management Instrumentation (WMI)</span></span>](./use-wmi-microsoft-defender-antivirus.md)
- <span data-ttu-id="a11af-113">De [Microsoft Malware Protection Command Line Utility](./command-line-arguments-microsoft-defender-antivirus.md) (ook wel het hulpprogramma voor *mpcmdrun.exe* genoemd</span><span class="sxs-lookup"><span data-stu-id="a11af-113">The [Microsoft Malware Protection Command Line Utility](./command-line-arguments-microsoft-defender-antivirus.md) (referred to as the *mpcmdrun.exe* utility</span></span>

<span data-ttu-id="a11af-114">De volgende artikelen bevatten meer informatie, koppelingen en bronnen voor het gebruik van deze hulpprogramma's voor het beheren en configureren van Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="a11af-114">The following articles provide further information, links, and resources for using these tools to manage and configure Microsoft Defender Antivirus.</span></span>

| <span data-ttu-id="a11af-115">Artikel</span><span class="sxs-lookup"><span data-stu-id="a11af-115">Article</span></span> | <span data-ttu-id="a11af-116">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="a11af-116">Description</span></span> |
|:---|:---|
|[<span data-ttu-id="a11af-117">Beheer Microsoft Defender Antivirus met Microsoft Intune en Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a11af-117">Manage Microsoft Defender Antivirus with Microsoft Intune and Microsoft Endpoint Configuration Manager</span></span>](use-intune-config-manager-microsoft-defender-antivirus.md)|<span data-ttu-id="a11af-118">Informatie over het gebruik van Intune en Configuration Manager voor het implementeren, beheren, rapporteren en configureren van Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="a11af-118">Information about using Intune and Configuration Manager to deploy, manage, report, and configure Microsoft Defender Antivirus</span></span> |
|[<span data-ttu-id="a11af-119">Beheer Microsoft Defender Antivirus met groepsbeleidsinstellingen</span><span class="sxs-lookup"><span data-stu-id="a11af-119">Manage Microsoft Defender Antivirus with Group Policy settings</span></span>](use-group-policy-microsoft-defender-antivirus.md)|<span data-ttu-id="a11af-120">Lijst met alle groepsbeleidsinstellingen in ADMX-sjablonen</span><span class="sxs-lookup"><span data-stu-id="a11af-120">List of all Group Policy settings located in ADMX templates</span></span> |
|[<span data-ttu-id="a11af-121">Beheer Microsoft Defender Antivirus met PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="a11af-121">Manage Microsoft Defender Antivirus with PowerShell cmdlets</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)|<span data-ttu-id="a11af-122">Instructies voor het gebruik van PowerShell-cmdlets voor het beheren van Microsoft Defender Antivirus, plus koppelingen naar documentatie voor alle cmdlets en toegestane parameters</span><span class="sxs-lookup"><span data-stu-id="a11af-122">Instructions for using PowerShell cmdlets to manage Microsoft Defender Antivirus, plus links to documentation for all cmdlets and allowed parameters</span></span> |
|[<span data-ttu-id="a11af-123">Beheer Microsoft Defender Antivirus met Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="a11af-123">Manage Microsoft Defender Antivirus with Windows Management Instrumentation (WMI)</span></span>](use-wmi-microsoft-defender-antivirus.md)| <span data-ttu-id="a11af-124">Instructies voor het gebruik van WMI om Microsoft Defender Antivirus te beheren, plus koppelingen naar documentatie voor de WMIv2-API's (inclusief alle klassen, methoden en eigenschappen)</span><span class="sxs-lookup"><span data-stu-id="a11af-124">Instructions for using WMI to manage Microsoft Defender Antivirus, plus links to documentation for the WMIv2 APIs (including all classes, methods, and properties)</span></span> |
|[<span data-ttu-id="a11af-125">Beheer Microsoft Defender Antivirus met het mpcmdrun.exe opdrachtregelhulpmiddel</span><span class="sxs-lookup"><span data-stu-id="a11af-125">Manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>](command-line-arguments-microsoft-defender-antivirus.md)|<span data-ttu-id="a11af-126">Instructies voor het gebruik van het speciale opdrachtregelprogramma voor het beheren en gebruiken van Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="a11af-126">Instructions on using the dedicated command-line tool to manage and use Microsoft Defender Antivirus</span></span> |