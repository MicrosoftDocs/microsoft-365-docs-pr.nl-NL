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
ms.openlocfilehash: c2ff6eac3254e855d4858edc218ae5df034352e4
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925649"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="37a9e-104">Test attack surface reduction in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="37a9e-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="37a9e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="37a9e-105">**Applies to:**</span></span>
- [<span data-ttu-id="37a9e-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="37a9e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="37a9e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37a9e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="37a9e-108">Als u deel uitmaakt van het beveiligingsteam van uw organisatie, kunt u de mogelijkheden voor het verminderen van aanvallen configureren om in de auditmodus uit te voeren om te zien hoe ze in uw organisatie werken.</span><span class="sxs-lookup"><span data-stu-id="37a9e-108">If you're part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work in your organization.</span></span> <span data-ttu-id="37a9e-109">U kunt in de auditmodus met name regels voor het verminderen van aanvallen, bescherming tegen aanvallen, netwerkbeveiliging en gecontroleerde maptoegang inschakelen.</span><span class="sxs-lookup"><span data-stu-id="37a9e-109">In particular, you can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="37a9e-110">Met de auditmodus kunt u een record zien van *wat* er zou zijn gebeurd als u de functie had ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="37a9e-110">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="37a9e-111">Mogelijk wilt u de auditmodus inschakelen wanneer u test hoe de functies in uw organisatie werken.</span><span class="sxs-lookup"><span data-stu-id="37a9e-111">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="37a9e-112">Dit helpt ervoor te zorgen dat uw line-of-business-apps niet worden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="37a9e-112">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="37a9e-113">U kunt ook een idee krijgen van het aantal pogingen om verdachte bestanden over een bepaalde periode te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="37a9e-113">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="37a9e-114">De functies blokkeren of voorkomen niet dat apps, scripts of bestanden worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="37a9e-114">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="37a9e-115">In het Windows gebeurtenislogboek worden echter gebeurtenissen opgeslagen alsof de functies volledig zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="37a9e-115">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="37a9e-116">In de auditmodus kunt u het gebeurtenislogboek bekijken om te zien welk effect de functie zou hebben gehad als deze was ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="37a9e-116">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="37a9e-117">Als u de gecontroleerde vermeldingen wilt vinden, gaat u naar **Toepassingen en services** van  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operationeel**.</span><span class="sxs-lookup"><span data-stu-id="37a9e-117">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="37a9e-118">U kunt Defender voor eindpunt gebruiken om meer details voor elke gebeurtenis te krijgen, met name voor het onderzoeken van regels voor het verminderen van de surface van de aanval.</span><span class="sxs-lookup"><span data-stu-id="37a9e-118">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="37a9e-119">Met de Console Defender voor eindpunt kunt u problemen onderzoeken als onderdeel van de [waarschuwingstijdlijn en onderzoeksscenario's.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="37a9e-119">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="37a9e-120">U kunt group policy, PowerShell en configuration service providers (CSP's) gebruiken om de auditmodus in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="37a9e-120">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="37a9e-121">U kunt ook de website Windows Defender Testground op demo.wd.microsoft.com om te controleren of de functies werken en te zien hoe ze werken. [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)</span><span class="sxs-lookup"><span data-stu-id="37a9e-121">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

| <span data-ttu-id="37a9e-122">Controleopties</span><span class="sxs-lookup"><span data-stu-id="37a9e-122">Audit options</span></span> | <span data-ttu-id="37a9e-123">Controlemodus inschakelen</span><span class="sxs-lookup"><span data-stu-id="37a9e-123">How to enable audit mode</span></span> | <span data-ttu-id="37a9e-124">Gebeurtenissen weergeven</span><span class="sxs-lookup"><span data-stu-id="37a9e-124">How to view events</span></span> |
|---------|---------|---------|
| <span data-ttu-id="37a9e-125">Controle is van toepassing op alle gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="37a9e-125">Audit applies to all events</span></span> | [<span data-ttu-id="37a9e-126">Beheerde maptoegang inschakelen</span><span class="sxs-lookup"><span data-stu-id="37a9e-126">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="37a9e-127">Gebeurtenissen voor gecontroleerde maptoegang</span><span class="sxs-lookup"><span data-stu-id="37a9e-127">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="37a9e-128">Controle is van toepassing op afzonderlijke regels</span><span class="sxs-lookup"><span data-stu-id="37a9e-128">Audit applies to individual rules</span></span> | [<span data-ttu-id="37a9e-129">Regels voor het verminderen van aanvalsoppervlakken inschakelen</span><span class="sxs-lookup"><span data-stu-id="37a9e-129">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="37a9e-130">Regelgebeurtenissen voor surface reduction attack</span><span class="sxs-lookup"><span data-stu-id="37a9e-130">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="37a9e-131">Controle is van toepassing op alle gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="37a9e-131">Audit applies to all events</span></span> | [<span data-ttu-id="37a9e-132">Netwerkbeveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="37a9e-132">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="37a9e-133">Netwerkbeveiligingsgebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="37a9e-133">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="37a9e-134">Controle is van toepassing op afzonderlijke risico's</span><span class="sxs-lookup"><span data-stu-id="37a9e-134">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="37a9e-135">Bescherming tegen misbruik inschakelen</span><span class="sxs-lookup"><span data-stu-id="37a9e-135">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="37a9e-136">Beveiligingsgebeurtenissen misbruiken</span><span class="sxs-lookup"><span data-stu-id="37a9e-136">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)


