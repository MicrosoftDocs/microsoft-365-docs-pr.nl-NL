---
title: Rapporten bewaken en weergeven - Beveiligingscentrum
description: In dit artikel wordt beschreven hoe het Microsoft 365-beveiligingscentrum in één oogopslag een overzicht biedt van de beveiligings- en beveiligingsstatus.
keywords: beveiliging, malware, Microsoft 365, M365, beveiligingscentrum, monitor, rapport, status
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 4667c39a8d416d7e186d41063d7057109758cd33
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930400"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="571ab-104">Rapporten bewaken en weergeven in het Microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="571ab-104">Monitor and view reports in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="571ab-105">Wilt u ervaring met Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="571ab-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="571ab-106">U kunt [dit evalueren in een testomgeving](https://aka.ms/mtp-trial-lab) of uw [pilotproject in productie nemen.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="571ab-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="571ab-107">Het Microsoft 365-beveiligingscentrum biedt een overzicht van de beveiligingsstatus in uw Microsoft 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="571ab-107">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="571ab-108">Het beveiligingscentrum bevat een **sectie Rapporten** met een groot aantal kaarten voor verschillende gebieden.</span><span class="sxs-lookup"><span data-stu-id="571ab-108">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="571ab-109">Beveiligingsanalisten en beheerders kunnen de kaarten bijhouden als onderdeel van hun dagelijkse werkzaamheden.</span><span class="sxs-lookup"><span data-stu-id="571ab-109">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="571ab-110">Bij inzoomen bieden kaarten gedetailleerde rapporten en, in sommige gevallen, beheeropties.</span><span class="sxs-lookup"><span data-stu-id="571ab-110">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="571ab-111">Weergaven aanpassen</span><span class="sxs-lookup"><span data-stu-id="571ab-111">Customize views</span></span>

<span data-ttu-id="571ab-112">Kaarten zijn standaard gegroepeerd in deze categorieën:</span><span class="sxs-lookup"><span data-stu-id="571ab-112">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="571ab-113">[Identiteiten](monitor-and-report-identities.md) - gebruikersaccounts en referenties</span><span class="sxs-lookup"><span data-stu-id="571ab-113">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="571ab-114">[Gegevens](monitor-data.md) - e-mail en documentinhoud</span><span class="sxs-lookup"><span data-stu-id="571ab-114">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="571ab-115">[Apparaten](monitor-devices.md) - computers, mobiele telefoons en andere apparaten</span><span class="sxs-lookup"><span data-stu-id="571ab-115">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="571ab-116">[Apps](monitor-apps.md) - programma's en bijgevoegde onlineservices</span><span class="sxs-lookup"><span data-stu-id="571ab-116">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="571ab-117">Schakel over **naar Groeperen op onderwerp** om de kaarten te herschikken en te groeperen in de volgende onderwerpen:</span><span class="sxs-lookup"><span data-stu-id="571ab-117">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="571ab-118">**Risico's:** kaarten die entiteiten markeren, zoals accounts en apparaten, die mogelijk in gevaar zijn.</span><span class="sxs-lookup"><span data-stu-id="571ab-118">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="571ab-119">Deze kaarten markeren ook mogelijke risicobronnen, zoals nieuwe bedreigingscampagnes en bevoorrechte cloud-apps</span><span class="sxs-lookup"><span data-stu-id="571ab-119">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="571ab-120">**Detectietrends:** kaarten voor het markeren van nieuwe bedreigingsdetectie, bijzonder gedragingen en beleidsovertredingen</span><span class="sxs-lookup"><span data-stu-id="571ab-120">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="571ab-121">**Configuratie en statuskaarten** die betrekking hebben op de configuratie en implementatie van beveiligingscontroles, met inbegrip van de onboarding-statussen van apparaten voor beheerservices</span><span class="sxs-lookup"><span data-stu-id="571ab-121">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="571ab-122">**Over** het overige: alle andere kaarten die niet zijn gecategoriseerd onder andere onderwerpen</span><span class="sxs-lookup"><span data-stu-id="571ab-122">**Other** - all other cards not categorized under other topics</span></span>
