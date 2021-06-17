---
title: Test hoe Microsoft Defender voor eindpuntfuncties werken in de auditmodus
description: Met de auditmodus kunt u zien hoe Microsoft Defender voor Eindpunt uw apparaten zou beveiligen als deze was ingeschakeld.
keywords: exploit guard, audit, auditing, mode, enabled, disabled, test, demo, evaluate, lab
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.topic: article
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 23de13e9a2b0fb02b95c9bb367c3fd99e11e89c8
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985094"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="7d5cf-104">Test attack surface reduction in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7d5cf-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7d5cf-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7d5cf-105">**Applies to:**</span></span>

- [<span data-ttu-id="7d5cf-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="7d5cf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="7d5cf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7d5cf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="7d5cf-108">Als onderdeel van het beveiligingsteam van uw organisatie kunt u de mogelijkheden voor het verlagen van de surface voor aanvallen configureren om in de auditmodus uit te voeren om te zien hoe ze werken.</span><span class="sxs-lookup"><span data-stu-id="7d5cf-108">As part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work.</span></span> <span data-ttu-id="7d5cf-109">In de auditmodus kunt u het volgende inschakelen:</span><span class="sxs-lookup"><span data-stu-id="7d5cf-109">In audit mode, you can enable:</span></span>

- <span data-ttu-id="7d5cf-110">Regels voor het verminderen van kwetsbaarheid voor aanvallen</span><span class="sxs-lookup"><span data-stu-id="7d5cf-110">Attack surface reduction rules</span></span>
- <span data-ttu-id="7d5cf-111">Bescherming tegen misbruik</span><span class="sxs-lookup"><span data-stu-id="7d5cf-111">Exploit protection</span></span>
- <span data-ttu-id="7d5cf-112">Netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="7d5cf-112">Network protection</span></span>
- <span data-ttu-id="7d5cf-113">En gecontroleerde toegang tot mappen in de auditmodus</span><span class="sxs-lookup"><span data-stu-id="7d5cf-113">And controlled folder access in audit mode</span></span>

<span data-ttu-id="7d5cf-114">Met de auditmodus kunt u een record zien van *wat* er zou zijn gebeurd als u de functie had ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="7d5cf-114">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="7d5cf-115">U kunt de auditmodus inschakelen wanneer u test hoe de functies werken.</span><span class="sxs-lookup"><span data-stu-id="7d5cf-115">You can enable audit mode when testing how the features will work.</span></span> <span data-ttu-id="7d5cf-116">Dit helpt ervoor te zorgen dat uw line-of-business-apps niet worden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="7d5cf-116">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="7d5cf-117">U kunt ook een idee krijgen van het aantal pogingen om verdachte bestanden over een bepaalde periode te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="7d5cf-117">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="7d5cf-118">De functies blokkeren of voorkomen niet dat apps, scripts of bestanden worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="7d5cf-118">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="7d5cf-119">In het Windows gebeurtenislogboek worden echter gebeurtenissen opgeslagen alsof de functies volledig zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="7d5cf-119">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="7d5cf-120">In de auditmodus kunt u het gebeurtenislogboek bekijken om te zien wat voor invloed de functie zou hebben gehad als deze was ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="7d5cf-120">With audit mode, you can review the event log to see what affect the feature would have had if it was enabled.</span></span>

<span data-ttu-id="7d5cf-121">Als u de gecontroleerde vermeldingen wilt vinden, gaat u naar **Toepassingen en services** van  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operationeel**.</span><span class="sxs-lookup"><span data-stu-id="7d5cf-121">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="7d5cf-122">Gebruik Defender voor eindpunt om meer details voor elke gebeurtenis te krijgen, met name voor het onderzoeken van regels voor het verminderen van het oppervlak van de aanval.</span><span class="sxs-lookup"><span data-stu-id="7d5cf-122">Use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="7d5cf-123">Met de Console Defender voor eindpunt kunt u problemen onderzoeken als onderdeel van de [waarschuwingstijdlijn en onderzoeksscenario's.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="7d5cf-123">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="7d5cf-124">U kunt de auditmodus inschakelen met group policy, PowerShell en configuration service providers (CSP's).</span><span class="sxs-lookup"><span data-stu-id="7d5cf-124">You can enable audit mode using Group Policy, PowerShell, and configuration service providers (CSPs).</span></span>

> [!TIP]
> <span data-ttu-id="7d5cf-125">U kunt ook de website Windows Defender Testground op demo.wd.microsoft.com om te controleren of de functies werken en te zien hoe ze werken. [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)</span><span class="sxs-lookup"><span data-stu-id="7d5cf-125">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

| <span data-ttu-id="7d5cf-126">Controleopties</span><span class="sxs-lookup"><span data-stu-id="7d5cf-126">Audit options</span></span> | <span data-ttu-id="7d5cf-127">Controlemodus inschakelen</span><span class="sxs-lookup"><span data-stu-id="7d5cf-127">How to enable audit mode</span></span> | <span data-ttu-id="7d5cf-128">Gebeurtenissen weergeven</span><span class="sxs-lookup"><span data-stu-id="7d5cf-128">How to view events</span></span> |
|---------|---------|---------|
| <span data-ttu-id="7d5cf-129">Controle is van toepassing op alle gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="7d5cf-129">Audit applies to all events</span></span> | [<span data-ttu-id="7d5cf-130">Beheerde maptoegang inschakelen</span><span class="sxs-lookup"><span data-stu-id="7d5cf-130">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="7d5cf-131">Gebeurtenissen voor gecontroleerde maptoegang</span><span class="sxs-lookup"><span data-stu-id="7d5cf-131">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="7d5cf-132">Controle is van toepassing op afzonderlijke regels</span><span class="sxs-lookup"><span data-stu-id="7d5cf-132">Audit applies to individual rules</span></span> | [<span data-ttu-id="7d5cf-133">Regels voor het verminderen van aanvalsoppervlakken inschakelen</span><span class="sxs-lookup"><span data-stu-id="7d5cf-133">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="7d5cf-134">Regelgebeurtenissen voor surface reduction attack</span><span class="sxs-lookup"><span data-stu-id="7d5cf-134">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="7d5cf-135">Controle is van toepassing op alle gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="7d5cf-135">Audit applies to all events</span></span> | [<span data-ttu-id="7d5cf-136">Netwerkbeveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="7d5cf-136">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="7d5cf-137">Netwerkbeveiligingsgebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="7d5cf-137">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="7d5cf-138">Controle is van toepassing op afzonderlijke risico's</span><span class="sxs-lookup"><span data-stu-id="7d5cf-138">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="7d5cf-139">Bescherming tegen misbruik inschakelen</span><span class="sxs-lookup"><span data-stu-id="7d5cf-139">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="7d5cf-140">Beveiligingsgebeurtenissen misbruiken</span><span class="sxs-lookup"><span data-stu-id="7d5cf-140">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)
