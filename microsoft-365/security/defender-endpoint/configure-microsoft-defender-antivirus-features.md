---
title: Microsoft Defender Antivirus-functies configureren
description: U kunt de Microsoft Defender Antivirus configureren met Intune, Microsoft Endpoint Configuration Manager, Groepsbeleid en PowerShell.
keywords: Microsoft Defender Antivirus, antimalware, beveiliging, defender, configureren, configuratie, Config Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, mobile device management, GP, group policy, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6ef9a2c34a88d7c9f5506c681088db9dc84cb0cc
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789025"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="e4e61-104">Microsoft Defender Antivirus-functies configureren</span><span class="sxs-lookup"><span data-stu-id="e4e61-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e4e61-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e4e61-105">**Applies to:**</span></span>

- [<span data-ttu-id="e4e61-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="e4e61-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e4e61-107">U kunt Microsoft Defender Antivirus met een aantal hulpprogramma's configureren, zoals:</span><span class="sxs-lookup"><span data-stu-id="e4e61-107">You can configure Microsoft Defender Antivirus with a number of tools, such as:</span></span>

- <span data-ttu-id="e4e61-108">Microsoft Endpoint Manager (inclusief Microsoft Intune en Microsoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="e4e61-108">Microsoft Endpoint Manager (which includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
- <span data-ttu-id="e4e61-109">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="e4e61-109">Group Policy</span></span>
- <span data-ttu-id="e4e61-110">PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="e4e61-110">PowerShell cmdlets</span></span>
- <span data-ttu-id="e4e61-111">Windows Beheerinstrumentatie (WMI)</span><span class="sxs-lookup"><span data-stu-id="e4e61-111">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="e4e61-112">De volgende algemene categorieën functies kunnen worden geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="e4e61-112">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="e4e61-113">Beveiliging in de cloud.</span><span class="sxs-lookup"><span data-stu-id="e4e61-113">Cloud-delivered protection.</span></span> <span data-ttu-id="e4e61-114">Zie [Beveiliging en beveiliging in](cloud-protection-microsoft-defender-antivirus.md) de cloud Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="e4e61-114">See [Cloud-delivered protection and Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)</span></span>
 
- <span data-ttu-id="e4e61-115">Altijd in realtime bescherming, inclusief bescherming op basis van gedrag, heuristische en op machine learning gebaseerde beveiliging.</span><span class="sxs-lookup"><span data-stu-id="e4e61-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection.</span></span> <span data-ttu-id="e4e61-116">Zie [Gedrags-, heuristische en realtimebeveiliging configureren.](configure-protection-features-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="e4e61-116">See [Configure behavioral, heuristic, and real-time protection](configure-protection-features-microsoft-defender-antivirus.md).</span></span>

- <span data-ttu-id="e4e61-117">De interactie tussen eindgebruikers met de client op afzonderlijke eindpunten.</span><span class="sxs-lookup"><span data-stu-id="e4e61-117">How end users interact with the client on individual endpoints.</span></span> <span data-ttu-id="e4e61-118">Zie de volgende bronnen:</span><span class="sxs-lookup"><span data-stu-id="e4e61-118">See the following resources:</span></span>
   
   - [<span data-ttu-id="e4e61-119">Voorkomen dat gebruikers de gebruikersinterface van de Microsoft Defender Antivirus zien of gebruiken</span><span class="sxs-lookup"><span data-stu-id="e4e61-119">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md)

   - [<span data-ttu-id="e4e61-120">Voorkomen of toestaan dat gebruikers lokaal de beleidsinstellingen Microsoft Defender Antivirus wijzigen</span><span class="sxs-lookup"><span data-stu-id="e4e61-120">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) 

> [!TIP]
> <span data-ttu-id="e4e61-121">Bekijk [Naslagonderwerpen voor beheer- en configuratiehulpprogramma's.](configuration-management-reference-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="e4e61-121">Review [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md).</span></span>