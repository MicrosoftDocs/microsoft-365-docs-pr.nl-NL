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
ms.technology: mde
ms.date: 06/02/2021
ms.topic: article
ms.openlocfilehash: 10351d97ba72945f929e042dc72a37724a1df291
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769603"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="fc946-104">Test attack surface reduction in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fc946-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fc946-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="fc946-105">**Applies to:**</span></span>
- [<span data-ttu-id="fc946-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="fc946-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="fc946-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc946-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="fc946-108">Als u deel uitmaakt van het beveiligingsteam van uw organisatie, kunt u de mogelijkheden voor het verminderen van aanvallen configureren om in de auditmodus uit te voeren om te zien hoe ze in uw organisatie werken.</span><span class="sxs-lookup"><span data-stu-id="fc946-108">If you're part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work in your organization.</span></span> <span data-ttu-id="fc946-109">U kunt in de auditmodus met name regels voor het verminderen van aanvallen, bescherming tegen aanvallen, netwerkbeveiliging en gecontroleerde maptoegang inschakelen.</span><span class="sxs-lookup"><span data-stu-id="fc946-109">In particular, you can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="fc946-110">Met de auditmodus kunt u een record zien van *wat* er zou zijn gebeurd als u de functie had ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="fc946-110">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="fc946-111">Mogelijk wilt u de auditmodus inschakelen wanneer u test hoe de functies in uw organisatie werken.</span><span class="sxs-lookup"><span data-stu-id="fc946-111">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="fc946-112">Dit helpt ervoor te zorgen dat uw line-of-business-apps niet worden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="fc946-112">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="fc946-113">U kunt ook een idee krijgen van het aantal pogingen om verdachte bestanden over een bepaalde periode te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="fc946-113">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="fc946-114">De functies blokkeren of voorkomen niet dat apps, scripts of bestanden worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="fc946-114">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="fc946-115">In het Windows gebeurtenislogboek worden echter gebeurtenissen opgeslagen alsof de functies volledig zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="fc946-115">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="fc946-116">In de auditmodus kunt u het gebeurtenislogboek bekijken om te zien welk effect de functie zou hebben gehad als deze was ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="fc946-116">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="fc946-117">Als u de gecontroleerde vermeldingen wilt vinden, gaat u naar **Toepassingen en services** van  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operationeel**.</span><span class="sxs-lookup"><span data-stu-id="fc946-117">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="fc946-118">U kunt Defender voor eindpunt gebruiken om meer details voor elke gebeurtenis te krijgen, met name voor het onderzoeken van regels voor het verminderen van de surface van de aanval.</span><span class="sxs-lookup"><span data-stu-id="fc946-118">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="fc946-119">Met de Console Defender voor eindpunt kunt u problemen onderzoeken als onderdeel van de [waarschuwingstijdlijn en onderzoeksscenario's.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="fc946-119">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="fc946-120">U kunt group policy, PowerShell en configuration service providers (CSP's) gebruiken om de auditmodus in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="fc946-120">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="fc946-121">U kunt ook de website Windows Defender Testground op demo.wd.microsoft.com om te controleren of de functies werken en te zien hoe ze werken. [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)</span><span class="sxs-lookup"><span data-stu-id="fc946-121">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

 <span data-ttu-id="fc946-122">**Controleopties**</span><span class="sxs-lookup"><span data-stu-id="fc946-122">**Audit options**</span></span> | <span data-ttu-id="fc946-123">**Controlemodus inschakelen**</span><span class="sxs-lookup"><span data-stu-id="fc946-123">**How to enable audit mode**</span></span> | <span data-ttu-id="fc946-124">**Gebeurtenissen weergeven**</span><span class="sxs-lookup"><span data-stu-id="fc946-124">**How to view events**</span></span>
|---------|---------|---------|
| <span data-ttu-id="fc946-125">Controle is van toepassing op alle gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="fc946-125">Audit applies to all events</span></span> | [<span data-ttu-id="fc946-126">Beheerde maptoegang inschakelen</span><span class="sxs-lookup"><span data-stu-id="fc946-126">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="fc946-127">Gebeurtenissen voor gecontroleerde maptoegang</span><span class="sxs-lookup"><span data-stu-id="fc946-127">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="fc946-128">Controle is van toepassing op afzonderlijke regels</span><span class="sxs-lookup"><span data-stu-id="fc946-128">Audit applies to individual rules</span></span> | [<span data-ttu-id="fc946-129">Regels voor het verminderen van aanvalsoppervlakken inschakelen</span><span class="sxs-lookup"><span data-stu-id="fc946-129">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="fc946-130">Regelgebeurtenissen voor surface reduction attack</span><span class="sxs-lookup"><span data-stu-id="fc946-130">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="fc946-131">Controle is van toepassing op alle gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="fc946-131">Audit applies to all events</span></span> | [<span data-ttu-id="fc946-132">Netwerkbeveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="fc946-132">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="fc946-133">Netwerkbeveiligingsgebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="fc946-133">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="fc946-134">Controle is van toepassing op afzonderlijke risico's</span><span class="sxs-lookup"><span data-stu-id="fc946-134">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="fc946-135">Bescherming tegen misbruik inschakelen</span><span class="sxs-lookup"><span data-stu-id="fc946-135">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="fc946-136">Beveiligingsgebeurtenissen misbruiken</span><span class="sxs-lookup"><span data-stu-id="fc946-136">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)


