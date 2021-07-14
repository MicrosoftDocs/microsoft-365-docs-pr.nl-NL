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
ms.date: 07/13/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f9ecade23964db88076347b3a89085b25c1b1538
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415561"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a><span data-ttu-id="0b052-104">Uw Microsoft Defender Antivirus in uw bedrijf beheren</span><span class="sxs-lookup"><span data-stu-id="0b052-104">Manage Microsoft Defender Antivirus in your business</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0b052-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="0b052-105">**Applies to:**</span></span>

- [<span data-ttu-id="0b052-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="0b052-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="0b052-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="0b052-107">Microsoft Defender Antivirus</span></span>](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-windows)

<span data-ttu-id="0b052-108">U kunt uw Microsoft Defender Antivirus met de volgende hulpmiddelen beheren en configureren:</span><span class="sxs-lookup"><span data-stu-id="0b052-108">You can manage and configure Microsoft Defender Antivirus with the following tools:</span></span>

- <span data-ttu-id="0b052-109">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (nu onderdeel van Microsoft Endpoint Manager)</span><span class="sxs-lookup"><span data-stu-id="0b052-109">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (now part of Microsoft Endpoint Manager)</span></span>
- <span data-ttu-id="0b052-110">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (nu onderdeel van Microsoft Endpoint Manager)</span><span class="sxs-lookup"><span data-stu-id="0b052-110">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (now part of Microsoft Endpoint Manager)</span></span>
- [<span data-ttu-id="0b052-111">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="0b052-111">Group Policy</span></span>](./use-group-policy-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0b052-112">PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="0b052-112">PowerShell cmdlets</span></span>](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0b052-113">Windows Beheerinstrumentatie (WMI)</span><span class="sxs-lookup"><span data-stu-id="0b052-113">Windows Management Instrumentation (WMI)</span></span>](./use-wmi-microsoft-defender-antivirus.md)
- <span data-ttu-id="0b052-114">De [Microsoft Malware Protection Command Line Utility](./command-line-arguments-microsoft-defender-antivirus.md) (ook wel het hulpprogramma voor *mpcmdrun.exe* genoemd</span><span class="sxs-lookup"><span data-stu-id="0b052-114">The [Microsoft Malware Protection Command Line Utility](./command-line-arguments-microsoft-defender-antivirus.md) (referred to as the *mpcmdrun.exe* utility</span></span>

<span data-ttu-id="0b052-115">De volgende artikelen bevatten meer informatie, koppelingen en bronnen voor het gebruik van deze hulpprogramma's voor het beheren en configureren van Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="0b052-115">The following articles provide further information, links, and resources for using these tools to manage and configure Microsoft Defender Antivirus.</span></span>

| <span data-ttu-id="0b052-116">Artikel</span><span class="sxs-lookup"><span data-stu-id="0b052-116">Article</span></span> | <span data-ttu-id="0b052-117">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="0b052-117">Description</span></span> |
|:---|:---|
|[<span data-ttu-id="0b052-118">Beheer Microsoft Defender Antivirus met Microsoft Intune en Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0b052-118">Manage Microsoft Defender Antivirus with Microsoft Intune and Microsoft Endpoint Configuration Manager</span></span>](use-intune-config-manager-microsoft-defender-antivirus.md)|<span data-ttu-id="0b052-119">Informatie over het gebruik van Intune en Configuration Manager voor het implementeren, beheren, rapporteren en configureren van Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="0b052-119">Information about using Intune and Configuration Manager to deploy, manage, report, and configure Microsoft Defender Antivirus</span></span> |
|[<span data-ttu-id="0b052-120">Beheer Microsoft Defender Antivirus met groepsbeleidsinstellingen</span><span class="sxs-lookup"><span data-stu-id="0b052-120">Manage Microsoft Defender Antivirus with Group Policy settings</span></span>](use-group-policy-microsoft-defender-antivirus.md)|<span data-ttu-id="0b052-121">Lijst met alle groepsbeleidsinstellingen in ADMX-sjablonen</span><span class="sxs-lookup"><span data-stu-id="0b052-121">List of all Group Policy settings located in ADMX templates</span></span> |
|[<span data-ttu-id="0b052-122">Beheer Microsoft Defender Antivirus met PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="0b052-122">Manage Microsoft Defender Antivirus with PowerShell cmdlets</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)|<span data-ttu-id="0b052-123">Instructies voor het gebruik van PowerShell-cmdlets voor het beheren van Microsoft Defender Antivirus, plus koppelingen naar documentatie voor alle cmdlets en toegestane parameters</span><span class="sxs-lookup"><span data-stu-id="0b052-123">Instructions for using PowerShell cmdlets to manage Microsoft Defender Antivirus, plus links to documentation for all cmdlets and allowed parameters</span></span> |
|[<span data-ttu-id="0b052-124">Beheer Microsoft Defender Antivirus met Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="0b052-124">Manage Microsoft Defender Antivirus with Windows Management Instrumentation (WMI)</span></span>](use-wmi-microsoft-defender-antivirus.md)| <span data-ttu-id="0b052-125">Instructies voor het gebruik van WMI om Microsoft Defender Antivirus te beheren, plus koppelingen naar documentatie voor de WMIv2-API's (inclusief alle klassen, methoden en eigenschappen)</span><span class="sxs-lookup"><span data-stu-id="0b052-125">Instructions for using WMI to manage Microsoft Defender Antivirus, plus links to documentation for the WMIv2 APIs (including all classes, methods, and properties)</span></span> |
|[<span data-ttu-id="0b052-126">Beheer Microsoft Defender Antivirus met het MpCmdRun.exe opdrachtregelhulpmiddel</span><span class="sxs-lookup"><span data-stu-id="0b052-126">Manage Microsoft Defender Antivirus with the MpCmdRun.exe command-line tool</span></span>](command-line-arguments-microsoft-defender-antivirus.md)| <span data-ttu-id="0b052-127">Instructies voor het gebruik van het speciale opdrachtregelprogramma voor het beheren en gebruiken van Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="0b052-127">Instructions on using the dedicated command-line tool to manage and use Microsoft Defender Antivirus</span></span> |
