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
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: dda0e58e587add2693f8448dd0833ce17706786c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059938"
---
# <a name="test-how-microsoft-defender-for-endpoint-features-work-in-audit-mode"></a><span data-ttu-id="b31f3-104">Test hoe Microsoft Defender voor eindpuntfuncties werken in de auditmodus</span><span class="sxs-lookup"><span data-stu-id="b31f3-104">Test how Microsoft Defender for Endpoint features work in audit mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b31f3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b31f3-105">**Applies to:**</span></span>
- [<span data-ttu-id="b31f3-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="b31f3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="b31f3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b31f3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="b31f3-108">In de auditmodus kunt u regels voor het verminderen van aanvallen, misbruikbeveiliging, netwerkbeveiliging en gecontroleerde maptoegang inschakelen.</span><span class="sxs-lookup"><span data-stu-id="b31f3-108">You can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="b31f3-109">Met de auditmodus kunt u een record zien van *wat* er zou zijn gebeurd als u de functie had ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b31f3-109">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="b31f3-110">Mogelijk wilt u de auditmodus inschakelen wanneer u test hoe de functies in uw organisatie werken.</span><span class="sxs-lookup"><span data-stu-id="b31f3-110">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="b31f3-111">Dit helpt ervoor te zorgen dat uw line-of-business-apps niet worden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="b31f3-111">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="b31f3-112">U kunt ook een idee krijgen van het aantal pogingen om verdachte bestanden over een bepaalde periode te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b31f3-112">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="b31f3-113">De functies blokkeren of voorkomen niet dat apps, scripts of bestanden worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="b31f3-113">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="b31f3-114">In het Windows-gebeurtenislogboek worden echter gebeurtenissen opgeslagen alsof de functies volledig zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b31f3-114">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="b31f3-115">In de auditmodus kunt u het gebeurtenislogboek bekijken om te zien welk effect de functie zou hebben gehad als deze was ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b31f3-115">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="b31f3-116">Als u de gecontroleerde vermeldingen wilt vinden, gaat u naar **Toepassingen en services**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operationeel.**</span><span class="sxs-lookup"><span data-stu-id="b31f3-116">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="b31f3-117">U kunt Defender voor eindpunt gebruiken om meer details voor elke gebeurtenis te krijgen, met name voor het onderzoeken van regels voor het verminderen van de surface van de aanval.</span><span class="sxs-lookup"><span data-stu-id="b31f3-117">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="b31f3-118">Met de Console Defender voor eindpunt kunt u problemen onderzoeken als onderdeel van de [waarschuwingstijdlijn en onderzoeksscenario's.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="b31f3-118">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="b31f3-119">U kunt group policy, PowerShell en configuration service providers (CSP's) gebruiken om de auditmodus in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="b31f3-119">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="b31f3-120">U kunt ook de Windows Defender [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Testground-website op demo.wd.microsoft.com om te bevestigen dat de functies werken en te zien hoe ze werken.</span><span class="sxs-lookup"><span data-stu-id="b31f3-120">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

 <span data-ttu-id="b31f3-121">**Controleopties**</span><span class="sxs-lookup"><span data-stu-id="b31f3-121">**Audit options**</span></span> | <span data-ttu-id="b31f3-122">**Controlemodus inschakelen**</span><span class="sxs-lookup"><span data-stu-id="b31f3-122">**How to enable audit mode**</span></span> | <span data-ttu-id="b31f3-123">**Gebeurtenissen weergeven**</span><span class="sxs-lookup"><span data-stu-id="b31f3-123">**How to view events**</span></span>
|---------|---------|---------|
| <span data-ttu-id="b31f3-124">Controle is van toepassing op alle gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="b31f3-124">Audit applies to all events</span></span> | [<span data-ttu-id="b31f3-125">Gecontroleerde maptoegang inschakelen</span><span class="sxs-lookup"><span data-stu-id="b31f3-125">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="b31f3-126">Gebeurtenissen voor gecontroleerde maptoegang</span><span class="sxs-lookup"><span data-stu-id="b31f3-126">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="b31f3-127">Controle is van toepassing op afzonderlijke regels</span><span class="sxs-lookup"><span data-stu-id="b31f3-127">Audit applies to individual rules</span></span> | [<span data-ttu-id="b31f3-128">Regels voor het verlagen van de surface voor aanvallen inschakelen</span><span class="sxs-lookup"><span data-stu-id="b31f3-128">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="b31f3-129">Regelgebeurtenissen voor surface reduction attack</span><span class="sxs-lookup"><span data-stu-id="b31f3-129">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="b31f3-130">Controle is van toepassing op alle gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="b31f3-130">Audit applies to all events</span></span> | [<span data-ttu-id="b31f3-131">Netwerkbeveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="b31f3-131">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="b31f3-132">Netwerkbeveiligingsgebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="b31f3-132">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="b31f3-133">Controle is van toepassing op afzonderlijke risico's</span><span class="sxs-lookup"><span data-stu-id="b31f3-133">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="b31f3-134">Exploitbeveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="b31f3-134">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="b31f3-135">Beveiligingsgebeurtenissen misbruiken</span><span class="sxs-lookup"><span data-stu-id="b31f3-135">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)

## <a name="related-topics"></a><span data-ttu-id="b31f3-136">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b31f3-136">Related topics</span></span>

* [<span data-ttu-id="b31f3-137">Apparaten beveiligen tegen exploits</span><span class="sxs-lookup"><span data-stu-id="b31f3-137">Protect devices from exploits</span></span>](exploit-protection.md)
* [<span data-ttu-id="b31f3-138">Aanvalsoppervlakken verminderen met regels voor het beperken van de surface van de aanval</span><span class="sxs-lookup"><span data-stu-id="b31f3-138">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="b31f3-139">Uw netwerk beveiligen</span><span class="sxs-lookup"><span data-stu-id="b31f3-139">Protect your network</span></span>](network-protection.md)
* [<span data-ttu-id="b31f3-140">Belangrijke mappen beveiligen</span><span class="sxs-lookup"><span data-stu-id="b31f3-140">Protect important folders</span></span>](controlled-folders.md)
