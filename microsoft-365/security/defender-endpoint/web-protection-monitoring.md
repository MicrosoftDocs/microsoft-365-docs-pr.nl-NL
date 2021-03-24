---
title: Beveiliging van surfen op het web in Microsoft Defender ATP controleren
description: Webbeveiliging gebruiken in Microsoft Defender ATP om de beveiliging van surfen op het web te controleren
keywords: webbeveiliging, bescherming tegen webdreigingen, surfen op het web, monitoring, rapporten, kaarten, domeinlijst, beveiliging, phishing, malware, exploit, websites, netwerkbeveiliging, Edge, Internet Explorer, Chrome, Firefox, webbrowser
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5d5cb89bccb0d7ea0fa4891c3b5b0d11a7244cf8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058114"
---
# <a name="monitor-web-browsing-security"></a><span data-ttu-id="0fc09-104">Beveiliging voor surfen op het web controleren</span><span class="sxs-lookup"><span data-stu-id="0fc09-104">Monitor web browsing security</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0fc09-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="0fc09-105">**Applies to:**</span></span>
- [<span data-ttu-id="0fc09-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="0fc09-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="0fc09-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0fc09-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0fc09-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="0fc09-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0fc09-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="0fc09-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="0fc09-110">Met webbeveiliging kunt u de browsebeveiliging van uw organisatie controleren via rapporten onder **Rapporten > webbeveiliging** in het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="0fc09-110">Web protection lets you monitor your organization’s web browsing security through reports under **Reports > Web protection** in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="0fc09-111">Het rapport bevat kaarten die statistieken over detectie van bedreigingen voor het web bieden.</span><span class="sxs-lookup"><span data-stu-id="0fc09-111">The report contains cards that provide web threat detection statistics.</span></span>

- <span data-ttu-id="0fc09-112">**Detectie van webdreigingsbeveiliging** in de loop van de tijd: deze trending card geeft het aantal webbedreigingen weer dat tijdens de geselecteerde periode per type is gedetecteerd (Last 30 days, Last 3 months, Last 6 months)</span><span class="sxs-lookup"><span data-stu-id="0fc09-112">**Web threat protection detections over time** - this trending card displays the number of web threats detected by type during the selected time period (Last 30 days, Last 3 months, Last 6 months)</span></span>
 
    ![Afbeelding van de kaart met beveiligingsdetecties voor webbedreigingen in de tijd](images/wtp-blocks-over-time.png)

- <span data-ttu-id="0fc09-114">**Overzicht van webdreigingsbeveiliging:** op deze kaart worden de totale detecties van webdreigingen in de afgelopen 30 dagen weergegeven, met de verdeling over de verschillende typen webrisico's.</span><span class="sxs-lookup"><span data-stu-id="0fc09-114">**Web threat protection summary** - this card displays the total web threat detections in the past 30 days, showing distribution across the different types of web threats.</span></span> <span data-ttu-id="0fc09-115">Als u een segment selecteert, wordt de lijst geopend met de domeinen die zijn gevonden bij schadelijke of ongewenste websites.</span><span class="sxs-lookup"><span data-stu-id="0fc09-115">Selecting a slice opens the list of the domains that were found with malicious or unwanted websites.</span></span>

    ![Afbeelding van de kaart met een overzicht van de beveiliging van webbedreigingen](images/wtp-summary.png)

>[!Note]
><span data-ttu-id="0fc09-117">Het kan tot 12 uur duren voordat een blok wordt weergegeven in de kaarten of de lijst met domeinen.</span><span class="sxs-lookup"><span data-stu-id="0fc09-117">It can take up to 12 hours before a block is reflected in the cards or the domain list.</span></span>

## <a name="types-of-web-threats"></a><span data-ttu-id="0fc09-118">Typen webbedreigingen</span><span class="sxs-lookup"><span data-stu-id="0fc09-118">Types of web threats</span></span>

<span data-ttu-id="0fc09-119">Webbeveiliging categoriseert schadelijke en ongewenste websites als:</span><span class="sxs-lookup"><span data-stu-id="0fc09-119">Web protection categorizes malicious and unwanted websites as:</span></span>

- <span data-ttu-id="0fc09-120">**Phishing** : websites met vervalste webformulieren en andere phishingmechanismen die zijn ontworpen om gebruikers te verleiden tot het openbaar maken van referenties en andere gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="0fc09-120">**Phishing** - websites that contain spoofed web forms and other phishing mechanisms designed to trick users into divulging credentials and other sensitive information</span></span>
- <span data-ttu-id="0fc09-121">**Schadelijk** : websites die malware hosten en code misbruiken</span><span class="sxs-lookup"><span data-stu-id="0fc09-121">**Malicious** - websites that host malware and exploit code</span></span>
- <span data-ttu-id="0fc09-122">**Aangepaste indicator** : websites waarvan u URL's of domeinen hebt toegevoegd aan uw [aangepaste indicatorlijst](manage-indicators.md) voor het blokkeren</span><span class="sxs-lookup"><span data-stu-id="0fc09-122">**Custom indicator** - websites whose URLs or domains you've added to your [custom indicator list](manage-indicators.md) for blocking</span></span>

## <a name="view-the-domain-list"></a><span data-ttu-id="0fc09-123">De lijst met domeinen weergeven</span><span class="sxs-lookup"><span data-stu-id="0fc09-123">View the domain list</span></span>

<span data-ttu-id="0fc09-124">Selecteer een specifieke categorie voor webbedreigingen in de **overzichtskaart voor webdreigingsbeveiliging** om de pagina **Domeinen te** openen.</span><span class="sxs-lookup"><span data-stu-id="0fc09-124">Select a specific web threat category in the **Web threat protection summary** card to open the **Domains** page.</span></span> <span data-ttu-id="0fc09-125">Op deze pagina wordt de lijst weergegeven met de domeinen onder die bedreigingscategorie.</span><span class="sxs-lookup"><span data-stu-id="0fc09-125">This page displays the list of the domains under that threat category.</span></span> <span data-ttu-id="0fc09-126">De pagina bevat de volgende informatie voor elk domein:</span><span class="sxs-lookup"><span data-stu-id="0fc09-126">The page provides the following information for each domain:</span></span>

- <span data-ttu-id="0fc09-127">**Aantal access-** het aantal aanvragen voor URL's in het domein</span><span class="sxs-lookup"><span data-stu-id="0fc09-127">**Access count** - number of requests for URLs in the domain</span></span>
- <span data-ttu-id="0fc09-128">**Blokken** : aantal keren dat aanvragen zijn geblokkeerd</span><span class="sxs-lookup"><span data-stu-id="0fc09-128">**Blocks** - number of times requests were blocked</span></span>
- <span data-ttu-id="0fc09-129">**Access-trend:** het aantal toegangspogingen wijzigen</span><span class="sxs-lookup"><span data-stu-id="0fc09-129">**Access trend** - change in number of access attempts</span></span>
- <span data-ttu-id="0fc09-130">**Bedreigingscategorie** - type webdreiging</span><span class="sxs-lookup"><span data-stu-id="0fc09-130">**Threat category** - type of web threat</span></span>
- <span data-ttu-id="0fc09-131">**Apparaten** - aantal apparaten met toegangspogingen</span><span class="sxs-lookup"><span data-stu-id="0fc09-131">**Devices** - number of devices with access attempts</span></span>

<span data-ttu-id="0fc09-132">Selecteer een domein om de lijst met apparaten weer te geven die hebben geprobeerd url's in dat domein en de lijst met URL's te openen.</span><span class="sxs-lookup"><span data-stu-id="0fc09-132">Select a domain to view the list of devices that have attempted to access URLs in that domain and the list of URLs.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0fc09-133">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="0fc09-133">Related topics</span></span>

- [<span data-ttu-id="0fc09-134">Overzicht van webbeveiliging</span><span class="sxs-lookup"><span data-stu-id="0fc09-134">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="0fc09-135">Filteren van webinhoud</span><span class="sxs-lookup"><span data-stu-id="0fc09-135">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="0fc09-136">Beveiliging tegen bedreigingen op het web</span><span class="sxs-lookup"><span data-stu-id="0fc09-136">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="0fc09-137">Reageren op webbedreigingen</span><span class="sxs-lookup"><span data-stu-id="0fc09-137">Respond to web threats</span></span>](web-protection-response.md)
