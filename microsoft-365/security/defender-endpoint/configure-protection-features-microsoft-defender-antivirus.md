---
title: Microsoft Defender Antivirusbeveiligingsfuncties in- en configureren
description: Schakel op gedrag gebaseerde, heuristische en realtime beveiliging in microsoft Defender AV in.
keywords: heuristisch, machine-learning, gedragsmonitor, realtime beveiliging, always-on, Microsoft Defender Antivirus, antimalware, beveiliging, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7a0e0571445e8ec753c3813a81dbcca9c698e7df
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690058"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a><span data-ttu-id="2c98d-104">Gedrags-, heuristische en realtimebeveiliging configureren</span><span class="sxs-lookup"><span data-stu-id="2c98d-104">Configure behavioral, heuristic, and real-time protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2c98d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2c98d-105">**Applies to:**</span></span>

- [<span data-ttu-id="2c98d-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="2c98d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="2c98d-107">Microsoft Defender Antivirus gebruikt verschillende methoden om bedreigingsbeveiliging te bieden:</span><span class="sxs-lookup"><span data-stu-id="2c98d-107">Microsoft Defender Antivirus uses several methods to provide threat protection:</span></span>

- <span data-ttu-id="2c98d-108">Beveiliging in de cloud voor bijna direct detecteren en blokkeren van nieuwe en nieuwe bedreigingen</span><span class="sxs-lookup"><span data-stu-id="2c98d-108">Cloud-delivered protection for near-instant detection and blocking of new and emerging threats</span></span>
- <span data-ttu-id="2c98d-109">Always-on scanning, using file and process behavior monitoring and other heuristics (ook wel 'real-time protection' genoemd)</span><span class="sxs-lookup"><span data-stu-id="2c98d-109">Always-on scanning, using file and process behavior monitoring and other heuristics (also known as "real-time protection")</span></span>
- <span data-ttu-id="2c98d-110">Speciale beveiligingsupdates op basis van machine learning, menselijke en geautomatiseerde analyse van big data en uitgebreid onderzoek naar bedreigingsresistentie</span><span class="sxs-lookup"><span data-stu-id="2c98d-110">Dedicated protection updates based on machine-learning, human and automated big-data analysis, and in-depth threat resistance research</span></span>

<span data-ttu-id="2c98d-111">U kunt configureren hoe Microsoft Defender Antivirus deze methoden gebruikt met Groepsbeleid, Systeemcentrumconfiguratie beheren, PowerShell-cmdlets en Windows Management Instrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="2c98d-111">You can configure how Microsoft Defender Antivirus uses these methods with Group Policy, System Center Configuration Manage, PowerShell cmdlets, and Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="2c98d-112">In deze sectie vindt u informatie over de configuratie voor altijd-on scannen, inclusief het detecteren en blokkeren van apps die als onveilig worden beschouwd, maar mogelijk niet worden gedetecteerd als malware.</span><span class="sxs-lookup"><span data-stu-id="2c98d-112">This section covers configuration for always-on scanning, including how to detect and block apps that are deemed unsafe, but may not be detected as malware.</span></span>

<span data-ttu-id="2c98d-113">Zie [Next-gen Microsoft Defender Antivirus technologies through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for how to enable and configure Microsoft Defender Antivirus cloud-delivered protection(Next-gen Microsoft Defender Antivirus technologies through cloud-delivered protection for how to enable and configure Microsoft Defender Antivirus cloud-delivered protection).</span><span class="sxs-lookup"><span data-stu-id="2c98d-113">See [Use next-gen Microsoft Defender Antivirus technologies through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for how to enable and configure Microsoft Defender Antivirus cloud-delivered protection.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2c98d-114">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="2c98d-114">In this section</span></span>

 <span data-ttu-id="2c98d-115">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="2c98d-115">Topic</span></span> | <span data-ttu-id="2c98d-116">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="2c98d-116">Description</span></span>
---|---
[<span data-ttu-id="2c98d-117">Potentieel ongewenste toepassingen detecteren en blokkeren</span><span class="sxs-lookup"><span data-stu-id="2c98d-117">Detect and block potentially unwanted applications</span></span>](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | <span data-ttu-id="2c98d-118">Apps detecteren en blokkeren die ongewenst kunnen zijn in uw netwerk, zoals malware, browsermodules en werkbalken, en malafide of nep-antivirus-apps</span><span class="sxs-lookup"><span data-stu-id="2c98d-118">Detect and block apps that may be unwanted in your network, such as adware, browser modifiers and toolbars, and rogue or fake antivirus apps</span></span>
[<span data-ttu-id="2c98d-119">Microsoft Defender Antivirus protection capabilities inschakelen en configureren</span><span class="sxs-lookup"><span data-stu-id="2c98d-119">Enable and configure Microsoft Defender Antivirus protection capabilities</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md) | <span data-ttu-id="2c98d-120">Realtime beveiliging, heuristische functies en andere functies voor het controleren van Microsoft Defender Antivirus inschakelen en configureren</span><span class="sxs-lookup"><span data-stu-id="2c98d-120">Enable and configure real-time protection, heuristics, and other always-on Microsoft Defender Antivirus monitoring features</span></span>