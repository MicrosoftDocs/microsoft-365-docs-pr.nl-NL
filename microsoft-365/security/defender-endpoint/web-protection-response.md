---
title: Reageren op webbedreigingen in Microsoft Defender ATP
description: Reageren op waarschuwingen met betrekking tot schadelijke en ongewenste websites. Meer informatie over de manier waarop webbedreigingsbeveiliging eindgebruikers informeert via hun webbrowsers en Windows-meldingen
keywords: webbeveiliging, bescherming tegen webdreigingen, surfen op het web, waarschuwingen, reactie, beveiliging, phishing, malware, exploit, websites, netwerkbeveiliging, Edge, Internet Explorer, Chrome, Firefox, webbrowser, meldingen, eindgebruikers, Windows-meldingen, blokkeringspagina,
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
ms.openlocfilehash: a9f3873db4f85cec3f5f1a400dcfb7930c6a4faa
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187539"
---
# <a name="respond-to-web-threats"></a><span data-ttu-id="9d359-105">Reageren op webbedreigingen</span><span class="sxs-lookup"><span data-stu-id="9d359-105">Respond to web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9d359-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="9d359-106">**Applies to:**</span></span>
- [<span data-ttu-id="9d359-107">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="9d359-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9d359-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9d359-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="9d359-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="9d359-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9d359-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="9d359-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="9d359-111">Met webbeveiliging in Microsoft Defender voor Eindpunt kunt u waarschuwingen met betrekking tot schadelijke websites en websites in uw aangepaste indicatorlijst efficiënt onderzoeken en beantwoorden.</span><span class="sxs-lookup"><span data-stu-id="9d359-111">Web protection in Microsoft Defender for Endpoint lets you efficiently investigate and respond to alerts related to malicious websites and websites in your custom indicator list.</span></span>

## <a name="view-web-threat-alerts"></a><span data-ttu-id="9d359-112">Waarschuwingen voor webbedreigingen weergeven</span><span class="sxs-lookup"><span data-stu-id="9d359-112">View web threat alerts</span></span>
<span data-ttu-id="9d359-113">Microsoft Defender voor Eindpunt genereert de volgende [waarschuwingen voor](manage-alerts.md) schadelijke of verdachte webactiviteit:</span><span class="sxs-lookup"><span data-stu-id="9d359-113">Microsoft Defender for Endpoint generates the following [alerts](manage-alerts.md) for malicious or suspicious web activity:</span></span>
- <span data-ttu-id="9d359-114">**Verdachte verbinding geblokkeerd door netwerkbeveiliging:** deze waarschuwing wordt gegenereerd wanneer een poging om toegang  te krijgen tot een schadelijke website of een website in uw aangepaste indicatorlijst wordt gestopt door netwerkbeveiliging in de *blokmodus*</span><span class="sxs-lookup"><span data-stu-id="9d359-114">**Suspicious connection blocked by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is *stopped* by network protection in *block* mode</span></span>
- <span data-ttu-id="9d359-115">**Verdachte verbinding gedetecteerd** door netwerkbeveiliging: deze waarschuwing wordt gegenereerd wanneer een poging om toegang te krijgen tot een schadelijke website of een website in uw aangepaste indicatorlijst wordt gedetecteerd door netwerkbeveiliging *in* de modus Alleen controleren</span><span class="sxs-lookup"><span data-stu-id="9d359-115">**Suspicious connection detected by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is detected by network protection in *audit only* mode</span></span>

<span data-ttu-id="9d359-116">Elke waarschuwing bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="9d359-116">Each alert provides the following information:</span></span> 
- <span data-ttu-id="9d359-117">Apparaat dat heeft geprobeerd toegang te krijgen tot de geblokkeerde website</span><span class="sxs-lookup"><span data-stu-id="9d359-117">Device that attempted to access the blocked website</span></span>
- <span data-ttu-id="9d359-118">Toepassing of programma dat wordt gebruikt om de webaanvraag te verzenden</span><span class="sxs-lookup"><span data-stu-id="9d359-118">Application or program used to send the web request</span></span>
- <span data-ttu-id="9d359-119">Schadelijke URL of URL in de lijst met aangepaste indicatoren</span><span class="sxs-lookup"><span data-stu-id="9d359-119">Malicious URL or URL in the custom indicator list</span></span>
- <span data-ttu-id="9d359-120">Aanbevolen acties voor responders</span><span class="sxs-lookup"><span data-stu-id="9d359-120">Recommended actions for responders</span></span>

![Afbeelding van een waarschuwing met betrekking tot beveiliging tegen webdreigingen](images/wtp-alert.png)

>[!Note]
><span data-ttu-id="9d359-122">Als u het aantal waarschuwingen wilt beperken, worden detecties van webdreigingen voor hetzelfde domein op hetzelfde apparaat elke dag samengevoegd tot één waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="9d359-122">To reduce the volume of alerts, Microsoft Defender for Endpoint consolidates web threat detections for the same domain on the same device each day to a single alert.</span></span> <span data-ttu-id="9d359-123">Er wordt slechts één waarschuwing gegenereerd en geteld in het [webbeveiligingsrapport.](web-protection-monitoring.md)</span><span class="sxs-lookup"><span data-stu-id="9d359-123">Only one alert is generated and counted into the [web protection report](web-protection-monitoring.md).</span></span>

## <a name="inspect-website-details"></a><span data-ttu-id="9d359-124">Websitedetails controleren</span><span class="sxs-lookup"><span data-stu-id="9d359-124">Inspect website details</span></span>
<span data-ttu-id="9d359-125">U kunt verder gaan door de URL of het domein van de website in de waarschuwing te selecteren.</span><span class="sxs-lookup"><span data-stu-id="9d359-125">You can dive deeper by selecting the URL or domain of the website in the alert.</span></span> <span data-ttu-id="9d359-126">Hiermee opent u een pagina over die specifieke URL of domein met diverse informatie, waaronder:</span><span class="sxs-lookup"><span data-stu-id="9d359-126">This opens a page about that particular URL or domain with various information, including:</span></span>
- <span data-ttu-id="9d359-127">Apparaten die hebben geprobeerd toegang te krijgen tot de website</span><span class="sxs-lookup"><span data-stu-id="9d359-127">Devices that attempted to access website</span></span>
- <span data-ttu-id="9d359-128">Incidenten en waarschuwingen met betrekking tot de website</span><span class="sxs-lookup"><span data-stu-id="9d359-128">Incidents and alerts related to the website</span></span>
- <span data-ttu-id="9d359-129">Hoe vaak de website is gezien in gebeurtenissen in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="9d359-129">How frequent the website was seen in events in your organization</span></span>

    ![Afbeelding van de pagina met domein- of URL-entiteitdetails](images/wtp-website-details.png)

[<span data-ttu-id="9d359-131">Meer informatie over url- of domeinentiteitspagina's</span><span class="sxs-lookup"><span data-stu-id="9d359-131">Learn more about URL or domain entity pages</span></span>](investigate-domain.md)

## <a name="inspect-the-device"></a><span data-ttu-id="9d359-132">Het apparaat controleren</span><span class="sxs-lookup"><span data-stu-id="9d359-132">Inspect the device</span></span>
<span data-ttu-id="9d359-133">U kunt ook het apparaat controleren dat heeft geprobeerd toegang te krijgen tot een geblokkeerde URL.</span><span class="sxs-lookup"><span data-stu-id="9d359-133">You can also check the device that attempted to access a blocked URL.</span></span> <span data-ttu-id="9d359-134">Als u de naam van het apparaat op de waarschuwingspagina selecteert, wordt er een pagina geopend met uitgebreide informatie over het apparaat.</span><span class="sxs-lookup"><span data-stu-id="9d359-134">Selecting the name of the device on the alert page opens a page with comprehensive information about the device.</span></span>

[<span data-ttu-id="9d359-135">Meer informatie over pagina's met apparaatentiteit</span><span class="sxs-lookup"><span data-stu-id="9d359-135">Learn more about device entity pages</span></span>](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a><span data-ttu-id="9d359-136">Webbrowser en Windows-meldingen voor eindgebruikers</span><span class="sxs-lookup"><span data-stu-id="9d359-136">Web browser and Windows notifications for end users</span></span>

<span data-ttu-id="9d359-137">Met webbeveiliging in Microsoft Defender voor Eindpunt kunnen uw eindgebruikers geen schadelijke of ongewenste websites bezoeken met Microsoft Edge of andere browsers.</span><span class="sxs-lookup"><span data-stu-id="9d359-137">With web protection in Microsoft Defender for Endpoint, your end users will be prevented from visiting malicious or unwanted websites using Microsoft Edge or other browsers.</span></span> <span data-ttu-id="9d359-138">Omdat blokkeren wordt uitgevoerd door [netwerkbeveiliging,](network-protection.md)zien ze een algemene fout in de webbrowser.</span><span class="sxs-lookup"><span data-stu-id="9d359-138">Because blocking is performed by [network protection](network-protection.md), they will see a generic error from the web browser.</span></span> <span data-ttu-id="9d359-139">Ze zien ook een melding van Windows.</span><span class="sxs-lookup"><span data-stu-id="9d359-139">They will also see a notification from Windows.</span></span>

<span data-ttu-id="9d359-140">![Afbeelding van Microsoft Edge met een 403-fout en de ](images/wtp-browser-blocking-page.png)
 *Windows-meldingswebdreiging geblokkeerd op Microsoft Edge*</span><span class="sxs-lookup"><span data-stu-id="9d359-140">![Image of Microsoft Edge showing a 403 error and the Windows notification](images/wtp-browser-blocking-page.png)
*Web threat blocked on Microsoft Edge*</span></span>

<span data-ttu-id="9d359-141">![Afbeelding van de webbrowser Chrome met een waarschuwing voor een beveiligde verbinding en de ](images/wtp-chrome-browser-blocking-page.png)
 *Windows-meldingswebdreiging geblokkeerd in Chrome*</span><span class="sxs-lookup"><span data-stu-id="9d359-141">![Image of Chrome web browser showing a secure connection warning and the Windows notification](images/wtp-chrome-browser-blocking-page.png)
*Web threat blocked on Chrome*</span></span>

## <a name="related-topics"></a><span data-ttu-id="9d359-142">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="9d359-142">Related topics</span></span>
- [<span data-ttu-id="9d359-143">Overzicht van webbeveiliging</span><span class="sxs-lookup"><span data-stu-id="9d359-143">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="9d359-144">Filteren van webinhoud</span><span class="sxs-lookup"><span data-stu-id="9d359-144">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="9d359-145">Beveiliging tegen bedreigingen op het web</span><span class="sxs-lookup"><span data-stu-id="9d359-145">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="9d359-146">Webbeveiliging controleren</span><span class="sxs-lookup"><span data-stu-id="9d359-146">Monitor web security</span></span>](web-protection-monitoring.md)
