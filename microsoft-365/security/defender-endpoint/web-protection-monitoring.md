---
title: Beveiliging van surfen op het web in Microsoft Defender voor Eindpunt controleren
description: Webbeveiliging gebruiken in Microsoft Defender voor Eindpunt om de beveiliging van surfen op het web te controleren
keywords: webbeveiliging, bescherming tegen webdreigingen, surfen op het web, monitoring, rapporten, kaarten, domeinlijst, beveiliging, phishing, malware, exploit, websites, netwerkbeveiliging, Edge, Internet Explorer, Chrome, Firefox, webbrowser
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ee6388c779d2c5bc09a82f5e9064d1b981e885cb
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687421"
---
# <a name="monitor-web-browsing-security"></a><span data-ttu-id="a3cc8-104">Beveiliging voor surfen op het web controleren</span><span class="sxs-lookup"><span data-stu-id="a3cc8-104">Monitor web browsing security</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a3cc8-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a3cc8-105">**Applies to:**</span></span>
- [<span data-ttu-id="a3cc8-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="a3cc8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a3cc8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a3cc8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a3cc8-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="a3cc8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a3cc8-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="a3cc8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="a3cc8-110">Met webbeveiliging kunt u de beveiliging van surfen in uw organisatie controleren via rapporten onder **Rapporten > webbeveiliging** in de Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="a3cc8-110">Web protection lets you monitor your organization’s web browsing security through reports under **Reports > Web protection** in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="a3cc8-111">Het rapport bevat kaarten die statistieken over detectie van bedreigingen voor het web bieden.</span><span class="sxs-lookup"><span data-stu-id="a3cc8-111">The report contains cards that provide web threat detection statistics.</span></span>

- <span data-ttu-id="a3cc8-112">**Detectie van webdreigingsbeveiliging** in de loop van de tijd: deze trending card geeft het aantal webbedreigingen weer dat tijdens de geselecteerde periode per type is gedetecteerd (Last 30 days, Last 3 months, Last 6 months)</span><span class="sxs-lookup"><span data-stu-id="a3cc8-112">**Web threat protection detections over time** - this trending card displays the number of web threats detected by type during the selected time period (Last 30 days, Last 3 months, Last 6 months)</span></span>
 
    ![Afbeelding van de kaart met beveiligingsdetecties voor webbedreigingen in de tijd](images/wtp-blocks-over-time.png)

- <span data-ttu-id="a3cc8-114">**Overzicht van webdreigingsbeveiliging:** op deze kaart worden de totale detecties van webdreigingen in de afgelopen 30 dagen weergegeven, met de verdeling over de verschillende typen webrisico's.</span><span class="sxs-lookup"><span data-stu-id="a3cc8-114">**Web threat protection summary** - this card displays the total web threat detections in the past 30 days, showing distribution across the different types of web threats.</span></span> <span data-ttu-id="a3cc8-115">Als u een segment selecteert, wordt de lijst geopend met de domeinen die zijn gevonden bij schadelijke of ongewenste websites.</span><span class="sxs-lookup"><span data-stu-id="a3cc8-115">Selecting a slice opens the list of the domains that were found with malicious or unwanted websites.</span></span>

    ![Afbeelding van de kaart met een overzicht van de beveiliging van webbedreigingen](images/wtp-summary.png)

>[!Note]
><span data-ttu-id="a3cc8-117">Het kan tot 12 uur duren voordat een blok wordt weergegeven in de kaarten of de lijst met domeinen.</span><span class="sxs-lookup"><span data-stu-id="a3cc8-117">It can take up to 12 hours before a block is reflected in the cards or the domain list.</span></span>

## <a name="types-of-web-threats"></a><span data-ttu-id="a3cc8-118">Typen webbedreigingen</span><span class="sxs-lookup"><span data-stu-id="a3cc8-118">Types of web threats</span></span>

<span data-ttu-id="a3cc8-119">Webbeveiliging categoriseert schadelijke en ongewenste websites als:</span><span class="sxs-lookup"><span data-stu-id="a3cc8-119">Web protection categorizes malicious and unwanted websites as:</span></span>

- <span data-ttu-id="a3cc8-120">**Phishing** : websites met vervalste webformulieren en andere phishingmechanismen die zijn ontworpen om gebruikers te verleiden tot het openbaar maken van referenties en andere gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="a3cc8-120">**Phishing** - websites that contain spoofed web forms and other phishing mechanisms designed to trick users into divulging credentials and other sensitive information</span></span>
- <span data-ttu-id="a3cc8-121">**Schadelijk** : websites die malware hosten en code misbruiken</span><span class="sxs-lookup"><span data-stu-id="a3cc8-121">**Malicious** - websites that host malware and exploit code</span></span>
- <span data-ttu-id="a3cc8-122">**Aangepaste indicator** : websites waarvan u URL's of domeinen hebt toegevoegd aan uw [aangepaste indicatorlijst](manage-indicators.md) voor het blokkeren</span><span class="sxs-lookup"><span data-stu-id="a3cc8-122">**Custom indicator** - websites whose URLs or domains you've added to your [custom indicator list](manage-indicators.md) for blocking</span></span>

## <a name="view-the-domain-list"></a><span data-ttu-id="a3cc8-123">De lijst met domeinen weergeven</span><span class="sxs-lookup"><span data-stu-id="a3cc8-123">View the domain list</span></span>

<span data-ttu-id="a3cc8-124">Selecteer een specifieke categorie voor webbedreigingen in de **overzichtskaart voor webdreigingsbeveiliging** om de pagina **Domeinen te** openen.</span><span class="sxs-lookup"><span data-stu-id="a3cc8-124">Select a specific web threat category in the **Web threat protection summary** card to open the **Domains** page.</span></span> <span data-ttu-id="a3cc8-125">Op deze pagina wordt de lijst weergegeven met de domeinen onder die bedreigingscategorie.</span><span class="sxs-lookup"><span data-stu-id="a3cc8-125">This page displays the list of the domains under that threat category.</span></span> <span data-ttu-id="a3cc8-126">De pagina bevat de volgende informatie voor elk domein:</span><span class="sxs-lookup"><span data-stu-id="a3cc8-126">The page provides the following information for each domain:</span></span>

- <span data-ttu-id="a3cc8-127">**Aantal access-** het aantal aanvragen voor URL's in het domein</span><span class="sxs-lookup"><span data-stu-id="a3cc8-127">**Access count** - number of requests for URLs in the domain</span></span>
- <span data-ttu-id="a3cc8-128">**Blokken** : aantal keren dat aanvragen zijn geblokkeerd</span><span class="sxs-lookup"><span data-stu-id="a3cc8-128">**Blocks** - number of times requests were blocked</span></span>
- <span data-ttu-id="a3cc8-129">**Access-trend:** het aantal toegangspogingen wijzigen</span><span class="sxs-lookup"><span data-stu-id="a3cc8-129">**Access trend** - change in number of access attempts</span></span>
- <span data-ttu-id="a3cc8-130">**Bedreigingscategorie** - type webdreiging</span><span class="sxs-lookup"><span data-stu-id="a3cc8-130">**Threat category** - type of web threat</span></span>
- <span data-ttu-id="a3cc8-131">**Apparaten** - aantal apparaten met toegangspogingen</span><span class="sxs-lookup"><span data-stu-id="a3cc8-131">**Devices** - number of devices with access attempts</span></span>

<span data-ttu-id="a3cc8-132">Selecteer een domein om de lijst met apparaten weer te geven die hebben geprobeerd url's in dat domein en de lijst met URL's te openen.</span><span class="sxs-lookup"><span data-stu-id="a3cc8-132">Select a domain to view the list of devices that have attempted to access URLs in that domain and the list of URLs.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a3cc8-133">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="a3cc8-133">Related topics</span></span>

- [<span data-ttu-id="a3cc8-134">Overzicht webbeveiliging</span><span class="sxs-lookup"><span data-stu-id="a3cc8-134">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="a3cc8-135">Filteren van webinhoud</span><span class="sxs-lookup"><span data-stu-id="a3cc8-135">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="a3cc8-136">Webbedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="a3cc8-136">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="a3cc8-137">Reageren op webbedreigingen</span><span class="sxs-lookup"><span data-stu-id="a3cc8-137">Respond to web threats</span></span>](web-protection-response.md)
