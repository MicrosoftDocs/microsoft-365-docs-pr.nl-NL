---
title: Netwerkbeveiliging evalueren
description: Bekijk hoe netwerkbeveiliging werkt door veelvoorkomende scenario's te testen die worden beschermd tegen.
keywords: Netwerkbeveiliging, exploits, schadelijke website, ip, domein, domeinen, evalueren, testen, demo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 98e4c80c2e0262712885f1e7a2da82886b2ebe80
ms.sourcegitcommit: b6e63febe24ef1f1793dfb3ecc5ed41a4e730578
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/06/2021
ms.locfileid: "53309360"
---
# <a name="evaluate-network-protection"></a><span data-ttu-id="c0eb7-104">Netwerkbeveiliging evalueren</span><span class="sxs-lookup"><span data-stu-id="c0eb7-104">Evaluate network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c0eb7-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c0eb7-105">**Applies to:**</span></span>
- [<span data-ttu-id="c0eb7-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="c0eb7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- - [<span data-ttu-id="c0eb7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0eb7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="c0eb7-108">[Netwerkbeveiliging](network-protection.md) helpt voorkomen dat werknemers elke toepassing gebruiken om toegang te krijgen tot gevaarlijke domeinen die phishingpraktijken, exploits en andere schadelijke inhoud op internet kunnen hosten.</span><span class="sxs-lookup"><span data-stu-id="c0eb7-108">[Network protection](network-protection.md) helps prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the Internet.</span></span>

<span data-ttu-id="c0eb7-109">In dit artikel kunt u netwerkbeveiliging evalueren door de functie in te stellen en u te begeleiden naar een testsite.</span><span class="sxs-lookup"><span data-stu-id="c0eb7-109">This article helps you evaluate network protection by enabling the feature and guiding you to a testing site.</span></span> <span data-ttu-id="c0eb7-110">De sites in dit evaluatieartikel zijn niet schadelijk.</span><span class="sxs-lookup"><span data-stu-id="c0eb7-110">The sites in this evaluation article aren't malicious.</span></span> <span data-ttu-id="c0eb7-111">Ze zijn speciaal gemaakt websites die zich voordoen als schadelijk.</span><span class="sxs-lookup"><span data-stu-id="c0eb7-111">They're specially created websites that pretend to be malicious.</span></span> <span data-ttu-id="c0eb7-112">De site repliceert het gedrag dat zou plaatsvinden als een gebruiker een schadelijke site of domein bezocht.</span><span class="sxs-lookup"><span data-stu-id="c0eb7-112">The site will replicate the behavior that would happen if a user visited a malicious site or domain.</span></span>

> [!TIP]
> <span data-ttu-id="c0eb7-113">U kunt ook naar de Microsoft Defender Testground-website op demo.wd.microsoft.com [om](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) te zien hoe andere beveiligingsfuncties werken.</span><span class="sxs-lookup"><span data-stu-id="c0eb7-113">You can also visit the Microsoft Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how other protection features work.</span></span>

## <a name="enable-network-protection-in-audit-mode"></a><span data-ttu-id="c0eb7-114">Netwerkbeveiliging inschakelen in de auditmodus</span><span class="sxs-lookup"><span data-stu-id="c0eb7-114">Enable network protection in audit mode</span></span>

<span data-ttu-id="c0eb7-115">Schakel netwerkbeveiliging in de auditmodus in om te zien welke IP-adressen en domeinen zouden zijn geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="c0eb7-115">Enable network protection in audit mode to see which IP addresses and domains would have been blocked.</span></span> <span data-ttu-id="c0eb7-116">U kunt ervoor zorgen dat dit geen invloed heeft op line-of-business-apps of een idee krijgen van hoe vaak blokken voorkomen.</span><span class="sxs-lookup"><span data-stu-id="c0eb7-116">You can make sure it doesn't affect line-of-business apps, or get an idea of how often blocks occur.</span></span>

1. <span data-ttu-id="c0eb7-117">Typ **powershell** in de Startmenu, klik met **de rechtermuisknop op Windows PowerShell** en selecteer Uitvoeren als **beheerder**</span><span class="sxs-lookup"><span data-stu-id="c0eb7-117">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="c0eb7-118">Voer de volgende cmdlet in:</span><span class="sxs-lookup"><span data-stu-id="c0eb7-118">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a><span data-ttu-id="c0eb7-119">Een (nep)kwaadwillend domein bezoeken</span><span class="sxs-lookup"><span data-stu-id="c0eb7-119">Visit a (fake) malicious domain</span></span>

1. <span data-ttu-id="c0eb7-120">Open Internet Explorer, Google Chrome of een andere browser naar keuze.</span><span class="sxs-lookup"><span data-stu-id="c0eb7-120">Open Internet Explorer, Google Chrome, or any other browser of your choice.</span></span>

1. <span data-ttu-id="c0eb7-121">Ga naar [https://smartscreentestratings2.net](https://smartscreentestratings2.net).</span><span class="sxs-lookup"><span data-stu-id="c0eb7-121">Go to [https://smartscreentestratings2.net](https://smartscreentestratings2.net).</span></span>

<span data-ttu-id="c0eb7-122">De netwerkverbinding is toegestaan en er wordt een testbericht weergegeven.</span><span class="sxs-lookup"><span data-stu-id="c0eb7-122">The network connection will be allowed and a test message will be displayed.</span></span>

![Voorbeeldmelding met de melding Verbinding geblokkeerd: De IT-beheerder heeft Windows-beveiliging netwerkverbinding geblokkeerd.](images/np-notif.png)

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="c0eb7-125">Netwerkbeveiligingsgebeurtenissen bekijken in Windows Event Viewer</span><span class="sxs-lookup"><span data-stu-id="c0eb7-125">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="c0eb7-126">Als u apps wilt bekijken die zijn geblokkeerd, opent u Gebeurtenisviewer en filtert u op Gebeurtenis-id 1125 in het microsoft-Windows-Windows-Defender/Operationeel logboek.</span><span class="sxs-lookup"><span data-stu-id="c0eb7-126">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1125 in the Microsoft-Windows-Windows-Defender/Operational log.</span></span> <span data-ttu-id="c0eb7-127">In de volgende tabel worden alle netwerkbeveiligingsgebeurtenissen vermeld.</span><span class="sxs-lookup"><span data-stu-id="c0eb7-127">The following table lists all network protection events.</span></span>

| <span data-ttu-id="c0eb7-128">Gebeurtenis-id</span><span class="sxs-lookup"><span data-stu-id="c0eb7-128">Event ID</span></span> | <span data-ttu-id="c0eb7-129">Leveren/bron</span><span class="sxs-lookup"><span data-stu-id="c0eb7-129">Provide/Source</span></span> | <span data-ttu-id="c0eb7-130">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="c0eb7-130">Description</span></span> |
|-|-|-|
|<span data-ttu-id="c0eb7-131">5007</span><span class="sxs-lookup"><span data-stu-id="c0eb7-131">5007</span></span> | <span data-ttu-id="c0eb7-132">Windows Defender (operationeel)</span><span class="sxs-lookup"><span data-stu-id="c0eb7-132">Windows Defender (Operational)</span></span> | <span data-ttu-id="c0eb7-133">Gebeurtenis wanneer instellingen worden gewijzigd</span><span class="sxs-lookup"><span data-stu-id="c0eb7-133">Event when settings are changed</span></span> |
|<span data-ttu-id="c0eb7-134">1125</span><span class="sxs-lookup"><span data-stu-id="c0eb7-134">1125</span></span> | <span data-ttu-id="c0eb7-135">Windows Defender (operationeel)</span><span class="sxs-lookup"><span data-stu-id="c0eb7-135">Windows Defender (Operational)</span></span> | <span data-ttu-id="c0eb7-136">Gebeurtenis wanneer een netwerkverbinding wordt gecontroleerd</span><span class="sxs-lookup"><span data-stu-id="c0eb7-136">Event when a network connection is audited</span></span> |
|<span data-ttu-id="c0eb7-137">1126</span><span class="sxs-lookup"><span data-stu-id="c0eb7-137">1126</span></span> | <span data-ttu-id="c0eb7-138">Windows Defender (operationeel)</span><span class="sxs-lookup"><span data-stu-id="c0eb7-138">Windows Defender (Operational)</span></span> | <span data-ttu-id="c0eb7-139">Gebeurtenis wanneer een netwerkverbinding is geblokkeerd</span><span class="sxs-lookup"><span data-stu-id="c0eb7-139">Event when a network connection is blocked</span></span> |

## <a name="see-also"></a><span data-ttu-id="c0eb7-140">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c0eb7-140">See also</span></span>

* [<span data-ttu-id="c0eb7-141">Netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="c0eb7-141">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="c0eb7-142">Netwerkbeveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="c0eb7-142">Enable network protection</span></span>](enable-network-protection.md)
* [<span data-ttu-id="c0eb7-143">Problemen met netwerkbeveiliging oplossen</span><span class="sxs-lookup"><span data-stu-id="c0eb7-143">Troubleshoot network protection</span></span>](troubleshoot-np.md)
