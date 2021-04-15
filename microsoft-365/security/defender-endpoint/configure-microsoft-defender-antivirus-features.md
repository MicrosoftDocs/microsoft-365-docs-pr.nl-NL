---
title: Microsoft Defender Antivirus-functies configureren
description: U kunt Microsoft Defender Antivirus-functies configureren met Intune, Microsoft Endpoint Configuration Manager, Group Policy en PowerShell.
keywords: Microsoft Defender Antivirus, antimalware, beveiliging, defender, configureren, configuratie, Config Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, mobile device management, GP, group policy, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8503bb5bdd6337ec60390ef1d8e59f6f506fbce2
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765165"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="bd436-104">Microsoft Defender Antivirus-functies configureren</span><span class="sxs-lookup"><span data-stu-id="bd436-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bd436-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="bd436-105">**Applies to:**</span></span>

- [<span data-ttu-id="bd436-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="bd436-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="bd436-107">U kunt Microsoft Defender Antivirus configureren met een aantal hulpprogramma's, waaronder:</span><span class="sxs-lookup"><span data-stu-id="bd436-107">You can configure Microsoft Defender Antivirus with a number of tools, including:</span></span>

- <span data-ttu-id="bd436-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bd436-108">Microsoft Intune</span></span>
- <span data-ttu-id="bd436-109">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bd436-109">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="bd436-110">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="bd436-110">Group Policy</span></span>
- <span data-ttu-id="bd436-111">PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="bd436-111">PowerShell cmdlets</span></span>
- <span data-ttu-id="bd436-112">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="bd436-112">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="bd436-113">De volgende algemene categorieën functies kunnen worden geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="bd436-113">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="bd436-114">Beveiliging in de cloud</span><span class="sxs-lookup"><span data-stu-id="bd436-114">Cloud-delivered protection</span></span>
- <span data-ttu-id="bd436-115">Altijd-op realtime bescherming, inclusief bescherming op basis van gedrag, heuristische en op machine learning gebaseerde beveiliging</span><span class="sxs-lookup"><span data-stu-id="bd436-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection</span></span>
- <span data-ttu-id="bd436-116">De interactie van eindgebruikers met de client op afzonderlijke eindpunten</span><span class="sxs-lookup"><span data-stu-id="bd436-116">How end users interact with the client on individual endpoints</span></span>

<span data-ttu-id="bd436-117">In de volgende artikelen wordt beschreven hoe u belangrijke taken kunt uitvoeren bij het configureren van Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="bd436-117">The following articles describe how to perform key tasks when configuring Microsoft Defender Antivirus.</span></span> <span data-ttu-id="bd436-118">Elk artikel bevat instructies voor het van toepassing zijnde configuratiehulpmiddel (of hulpprogramma's).</span><span class="sxs-lookup"><span data-stu-id="bd436-118">Each article includes instructions for the applicable configuration tool (or tools).</span></span>

|<span data-ttu-id="bd436-119">Artikel</span><span class="sxs-lookup"><span data-stu-id="bd436-119">Article</span></span>  |<span data-ttu-id="bd436-120">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="bd436-120">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="bd436-121">Microsoft Defender Antivirusbeveiliging in de cloud gebruiken</span><span class="sxs-lookup"><span data-stu-id="bd436-121">Utilize Microsoft cloud-provided Microsoft Defender Antivirus protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)     | <span data-ttu-id="bd436-122">Gebruik cloudbeveiliging voor geavanceerde, snelle en krachtige antivirusdetectie.</span><span class="sxs-lookup"><span data-stu-id="bd436-122">Use cloud-delivered protection for advanced, fast, robust antivirus detection.</span></span>        |
|[<span data-ttu-id="bd436-123">Gedrag, heuristiek en realtime bescherming configureren</span><span class="sxs-lookup"><span data-stu-id="bd436-123">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)     |<span data-ttu-id="bd436-124">Schakel op gedrag gebaseerde, heuristische en realtime antivirusbeveiliging in.</span><span class="sxs-lookup"><span data-stu-id="bd436-124">Enable behavior-based, heuristic, and real-time antivirus protection.</span></span>         |
|[<span data-ttu-id="bd436-125">Interactie tussen eindgebruikers configureren met Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="bd436-125">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="bd436-126">Configureer hoe eindgebruikers in uw organisatie werken met Microsoft Defender Antivirus, welke meldingen ze zien en of ze de instellingen kunnen overschrijven.</span><span class="sxs-lookup"><span data-stu-id="bd436-126">Configure how end users in your organization interact with Microsoft Defender Antivirus, what notifications they see, and whether they can override settings.</span></span> |

> [!TIP]
> <span data-ttu-id="bd436-127">U kunt ook het onderwerp Referentieonderwerpen voor beheer- en [configuratiehulpmiddelen](configuration-management-reference-microsoft-defender-antivirus.md) bekijken voor een overzicht van elk hulpmiddel en koppelingen naar verdere hulp.</span><span class="sxs-lookup"><span data-stu-id="bd436-127">You can also review the [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md) topic for an overview of each tool and links to further help.</span></span>