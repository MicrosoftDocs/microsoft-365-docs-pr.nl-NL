---
title: 'Rapporten bijhouden en weergeven: Beveiligingscentrum'
description: In dit artikel wordt beschreven hoe u in een oogopslag kunt zien wat de bescherming en de beveiligingsstatus zijn van Microsoft 365 Beveiligingscentrum.
keywords: beveiliging, malware, Microsoft 365, M365, Beveiligingscentrum, monitor, rapport, status
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d52c401c4b2e995e5ec18895c158f77ce0fce746
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356881"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="c1cec-104">Rapporten in het Microsoft 365-Beveiligingscentrum bewaken en weergeven</span><span class="sxs-lookup"><span data-stu-id="c1cec-104">Monitor and view reports in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="c1cec-105">Wilt u Microsoft 365 Defender ervaren?</span><span class="sxs-lookup"><span data-stu-id="c1cec-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="c1cec-106">U kunt [deze beoordelen in een testomgeving](https://aka.ms/mtp-trial-lab) of een [proefproject uitvoeren op de productie](https://aka.ms/m365d-pilotplaybook).</span><span class="sxs-lookup"><span data-stu-id="c1cec-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="c1cec-107">Het Microsoft 365 Beveiligingscentrum biedt een overzicht van de beschermings-en beveiligingsstatus in uw Microsoft 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="c1cec-107">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="c1cec-108">Het Beveiligingscentrum bevat een sectie **rapporten** die een host van kaarten bestrijkt die verschillende gebieden bestrijken.</span><span class="sxs-lookup"><span data-stu-id="c1cec-108">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="c1cec-109">Beveiligings analisten en beheerders kunnen de kaarten bijhouden als onderdeel van de dagelijkse activiteiten.</span><span class="sxs-lookup"><span data-stu-id="c1cec-109">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="c1cec-110">Bij inzoomen biedt kaarten uitgebreide rapporten en in sommige gevallen beheeropties.</span><span class="sxs-lookup"><span data-stu-id="c1cec-110">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="c1cec-111">Weergaven aanpassen</span><span class="sxs-lookup"><span data-stu-id="c1cec-111">Customize views</span></span>

<span data-ttu-id="c1cec-112">Kaarten zijn standaard gegroepeerd in de volgende categorieën:</span><span class="sxs-lookup"><span data-stu-id="c1cec-112">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="c1cec-113">[Identiteiten](monitor-and-report-identities.md) -gebruikersaccounts en referenties</span><span class="sxs-lookup"><span data-stu-id="c1cec-113">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="c1cec-114">[Gegevens](monitor-data.md) -e-mail en documentinhoud</span><span class="sxs-lookup"><span data-stu-id="c1cec-114">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="c1cec-115">[Apparaten](monitor-devices.md) : computers, mobiele telefoons en andere apparaten</span><span class="sxs-lookup"><span data-stu-id="c1cec-115">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="c1cec-116">[Apps](monitor-apps.md) -Programma's en bijgevoegde Online Services</span><span class="sxs-lookup"><span data-stu-id="c1cec-116">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="c1cec-117">Ga naar **groeperen op onderwerp** als u de kaarten wilt herschikken en ze wilt groeperen in de volgende onderwerpen:</span><span class="sxs-lookup"><span data-stu-id="c1cec-117">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="c1cec-118">**Risico** kaarten die entiteiten markeren, zoals accounts en apparaten, zijn mogelijk risico.</span><span class="sxs-lookup"><span data-stu-id="c1cec-118">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="c1cec-119">Deze kaarten markeren ook mogelijke risico bronnen, zoals nieuwe Threat campagnes en geautoriseerde Cloud-apps</span><span class="sxs-lookup"><span data-stu-id="c1cec-119">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="c1cec-120">**Detectie trends** : kaarten die de nieuwe bedreigings detectie, afwijkingen en beleidsschendingen markeren</span><span class="sxs-lookup"><span data-stu-id="c1cec-120">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="c1cec-121">**Configuraties en Health** -kaarten voor de configuratie en implementatie van beveiligings besturing, waaronder de statussen voor het apparaat voor beheerservices</span><span class="sxs-lookup"><span data-stu-id="c1cec-121">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="c1cec-122">**Overige** : alle andere kaarten die niet zijn gecategoriseerd onder andere onderwerpen</span><span class="sxs-lookup"><span data-stu-id="c1cec-122">**Other** - all other cards not categorized under other topics</span></span>
