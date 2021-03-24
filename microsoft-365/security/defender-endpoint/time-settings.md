---
title: Tijdzone-instellingen voor microsoft Defender Security Center
description: Gebruik de informatie hier om de tijdzone-instellingen van het Microsoft Defender-beveiligingscentrum te configureren en licentiegegevens weer te geven.
keywords: instellingen, Microsoft Defender, cyberbeveiligingsbedreigingsinformatie, geavanceerde bedreigingsbeveiliging, tijdzone, utc, lokale tijd, licentie
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 25f2fc979cd6ffe82ba16e1ab870c97cdf4fcfe9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059298"
---
# <a name="microsoft-defender-security-center-time-zone-settings"></a><span data-ttu-id="9c5e0-104">Tijdzone-instellingen voor microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="9c5e0-104">Microsoft Defender Security Center time zone settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9c5e0-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="9c5e0-105">**Applies to:**</span></span>
- [<span data-ttu-id="9c5e0-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="9c5e0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="9c5e0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9c5e0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)




><span data-ttu-id="9c5e0-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="9c5e0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9c5e0-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-settings-abovefoldlink)

<span data-ttu-id="9c5e0-110">Gebruik het **pictogram Tijdzone-instellingen** in het menu ![ Tijdzone1 om de tijdzone te ](images/atp-time-zone.png) configureren en licentiegegevens weer te geven.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-110">Use the **Time zone** menu ![Time zone settings icon1](images/atp-time-zone.png) to configure the time zone and view license information.</span></span>

## <a name="time-zone-settings"></a><span data-ttu-id="9c5e0-111">Tijdzone-instellingen</span><span class="sxs-lookup"><span data-stu-id="9c5e0-111">Time zone settings</span></span>
<span data-ttu-id="9c5e0-112">Het tijdsaspect is belangrijk bij het beoordelen en analyseren van waargenomen en werkelijke cyberaanvallen.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-112">The aspect of time is important in the assessment and analysis of perceived and actual cyberattacks.</span></span>

<span data-ttu-id="9c5e0-113">Cyberforensische onderzoeken zijn vaak afhankelijk van tijdstempels om de volgorde van gebeurtenissen samen te brengen.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-113">Cyberforensic investigations often rely on time stamps to piece together the sequence of events.</span></span> <span data-ttu-id="9c5e0-114">Het is belangrijk dat uw systeem de juiste tijdzone-instellingen weerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-114">It’s important that your system reflects the correct time zone settings.</span></span>

<span data-ttu-id="9c5e0-115">Microsoft Defender voor Eindpunt kan Coordinated Universal Time (UTC) of lokale tijd weergeven.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-115">Microsoft Defender for Endpoint can display either Coordinated Universal Time (UTC) or local time.</span></span>

<span data-ttu-id="9c5e0-116">De huidige tijdzone-instelling wordt weergegeven in het menu Microsoft Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-116">Your current time zone setting is shown in the Microsoft Defender for Endpoint menu.</span></span> <span data-ttu-id="9c5e0-117">U kunt de weergegeven tijdzone wijzigen in het **menu Tijdzone.**</span><span class="sxs-lookup"><span data-stu-id="9c5e0-117">You can change the displayed time zone in the **Time zone** menu.</span></span>

![Pictogram Tijdzone-instellingen2](images/atp-time-zone-menu.png)<span data-ttu-id="9c5e0-119">.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-119">.</span></span>

### <a name="utc-time-zone"></a><span data-ttu-id="9c5e0-120">UTC-tijdzone</span><span class="sxs-lookup"><span data-stu-id="9c5e0-120">UTC time zone</span></span>
<span data-ttu-id="9c5e0-121">Microsoft Defender voor Eindpunt gebruikt standaard UTC-tijd.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-121">Microsoft Defender for Endpoint uses UTC time by default.</span></span>

<span data-ttu-id="9c5e0-122">Als u de tijdzone van Microsoft Defender voor eindpunt instelt op UTC, worden alle systeemtijdstempels (waarschuwingen, gebeurtenissen en andere) weergegeven in UTC voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-122">Setting the Microsoft Defender for Endpoint time zone to UTC will display all system timestamps (alerts, events, and others) in UTC for all users.</span></span> <span data-ttu-id="9c5e0-123">Dit kan beveiligingsanalisten die op verschillende locaties over de hele wereld werken helpen om dezelfde tijdstempels te gebruiken tijdens het onderzoeken van gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-123">This can help security analysts working in different locations across the globe to use the same time stamps while investigating events.</span></span>

### <a name="local-time-zone"></a><span data-ttu-id="9c5e0-124">Lokale tijdzone</span><span class="sxs-lookup"><span data-stu-id="9c5e0-124">Local time zone</span></span>
<span data-ttu-id="9c5e0-125">U kunt ervoor kiezen om voor Microsoft Defender voor Eindpunt lokale tijdzone-instellingen te laten gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-125">You can choose to have Microsoft Defender for Endpoint use local time zone settings.</span></span> <span data-ttu-id="9c5e0-126">Alle waarschuwingen en gebeurtenissen worden weergegeven met uw lokale tijdzone.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-126">All alerts and events will be displayed using your local time zone.</span></span>

<span data-ttu-id="9c5e0-127">De lokale tijdzone wordt overgenomen uit de regionale instellingen van uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-127">The local time zone is taken from your device’s regional settings.</span></span> <span data-ttu-id="9c5e0-128">Als u uw regionale instellingen wijzigt, wordt ook de tijdzone van Microsoft Defender voor eindpunt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-128">If you change your regional settings, the Microsoft Defender for Endpoint time zone will also change.</span></span> <span data-ttu-id="9c5e0-129">Als u deze instelling kiest, worden de tijdstempels die worden weergegeven in Microsoft Defender voor Eindpunt, uitgelijnd op lokale tijd voor alle Gebruikers van Microsoft Defender voor Eindpunten.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-129">Choosing this setting means that the timestamps displayed in Microsoft Defender for Endpoint will be aligned to local time for all Microsoft Defender for Endpoint users.</span></span> <span data-ttu-id="9c5e0-130">Analisten die zich op verschillende globale locaties bevinden, zien nu de waarschuwingen van Microsoft Defender voor eindpunten op basis van hun landinstellingen.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-130">Analysts located in different global locations will now see the Microsoft Defender for Endpoint alerts according to their regional settings.</span></span>

<span data-ttu-id="9c5e0-131">Het gebruik van lokale tijd kan handig zijn als de analisten zich op één locatie bevinden.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-131">Choosing to use local time can be useful if the analysts are located in a single location.</span></span> <span data-ttu-id="9c5e0-132">In dit geval is het mogelijk gemakkelijker om gebeurtenissen te correleren met lokale tijd, bijvoorbeeld wanneer een lokale gebruiker op een verdachte e-mailkoppeling heeft geklikt.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-132">In this case it might be easier to correlate events to local time, for example – when a local user clicked on a suspicious email link.</span></span>

### <a name="set-the-time-zone"></a><span data-ttu-id="9c5e0-133">De tijdzone instellen</span><span class="sxs-lookup"><span data-stu-id="9c5e0-133">Set the time zone</span></span>
<span data-ttu-id="9c5e0-134">De tijdzone van Microsoft Defender voor eindpunt is standaard ingesteld op UTC.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-134">The Microsoft Defender for Endpoint time zone is set by default to UTC.</span></span>
<span data-ttu-id="9c5e0-135">Als u de tijdzone instelt, worden ook de tijden voor alle Weergaven van Microsoft Defender voor eindpunten gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-135">Setting the time zone also changes the times for all Microsoft Defender for Endpoint views.</span></span>
<span data-ttu-id="9c5e0-136">De tijdzone instellen:</span><span class="sxs-lookup"><span data-stu-id="9c5e0-136">To set the time zone:</span></span>

1. <span data-ttu-id="9c5e0-137">Klik op **het pictogram Tijdzonemenu** ![ Tijdzone-instellingen3 ](images/atp-time-zone.png) .</span><span class="sxs-lookup"><span data-stu-id="9c5e0-137">Click the **Time zone** menu ![Time zone settings icon3](images/atp-time-zone.png).</span></span>
2. <span data-ttu-id="9c5e0-138">Selecteer de **timezone UTC-indicator.**</span><span class="sxs-lookup"><span data-stu-id="9c5e0-138">Select the **Timezone UTC** indicator.</span></span>
3. <span data-ttu-id="9c5e0-139">Selecteer **Timezone UTC** of uw lokale tijdzone, bijvoorbeeld -7:00.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-139">Select **Timezone UTC** or your local time zone, for example -7:00.</span></span>

### <a name="regional-settings"></a><span data-ttu-id="9c5e0-140">Regionale instellingen</span><span class="sxs-lookup"><span data-stu-id="9c5e0-140">Regional settings</span></span>
<span data-ttu-id="9c5e0-141">Als u verschillende datumindelingen wilt toepassen voor Microsoft Defender voor Eindpunt, gebruikt u landinstellingen voor Internet Explorer (IE) en Microsoft Edge (Edge).</span><span class="sxs-lookup"><span data-stu-id="9c5e0-141">To apply different date formats for Microsoft Defender for Endpoint, use regional settings for Internet Explorer (IE) and Microsoft Edge (Edge).</span></span> <span data-ttu-id="9c5e0-142">Als u een andere browser gebruikt, zoals Google Chrome, volgt u de vereiste stappen om de tijd- en datuminstellingen voor die browser te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-142">If you're using another browser such as Google Chrome, follow the required steps to change the time and date settings for that browser.</span></span> 


<span data-ttu-id="9c5e0-143">**Internet Explorer (IE) en Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="9c5e0-143">**Internet Explorer (IE) and Microsoft Edge**</span></span>

<span data-ttu-id="9c5e0-144">IE en Microsoft Edge gebruiken de **regio-instellingen** die zijn geconfigureerd in de optie **Klokken, Taal** en Regio in het Configuratiescherm.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-144">IE and Microsoft Edge use the **Region** settings configured in the **Clocks, Language, and Region** option in the Control panel.</span></span> 


#### <a name="known-issues-with-regional-formats"></a><span data-ttu-id="9c5e0-145">Bekende problemen met regionale indelingen</span><span class="sxs-lookup"><span data-stu-id="9c5e0-145">Known issues with regional formats</span></span>

<span data-ttu-id="9c5e0-146">**Datum- en tijdnotaties**</span><span class="sxs-lookup"><span data-stu-id="9c5e0-146">**Date and time formats**</span></span><br>
<span data-ttu-id="9c5e0-147">Er zijn enkele bekende problemen met de tijd- en datumnotatie.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-147">There are some known issues with the time and date formats.</span></span> <span data-ttu-id="9c5e0-148">Als u uw regionale instellingen configureert op iets anders dan de ondersteunde indelingen, is het mogelijk dat de portal uw instellingen niet correct wedt.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-148">If you configure your regional settings to anything other than the supported formats, the portal may not correctly reflect your settings.</span></span>

<span data-ttu-id="9c5e0-149">De volgende datum- en tijdnotaties worden ondersteund:</span><span class="sxs-lookup"><span data-stu-id="9c5e0-149">The following date and time formats are supported:</span></span>
- <span data-ttu-id="9c5e0-150">Datumnotatie MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="9c5e0-150">Date format MM/dd/yyyy</span></span>
- <span data-ttu-id="9c5e0-151">Datumnotatie dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="9c5e0-151">Date format dd/MM/yyyy</span></span>
- <span data-ttu-id="9c5e0-152">Tijdnotatie hh:mm:ss (12 uursnotatie)</span><span class="sxs-lookup"><span data-stu-id="9c5e0-152">Time format hh:mm:ss (12 hour format)</span></span>

<span data-ttu-id="9c5e0-153">De volgende datum- en tijdindelingen worden momenteel niet ondersteund:</span><span class="sxs-lookup"><span data-stu-id="9c5e0-153">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="9c5e0-154">Datumnotatie yyyy-MM-dd</span><span class="sxs-lookup"><span data-stu-id="9c5e0-154">Date format yyyy-MM-dd</span></span>
- <span data-ttu-id="9c5e0-155">Datumnotatie dd-MMM-yy</span><span class="sxs-lookup"><span data-stu-id="9c5e0-155">Date format dd-MMM-yy</span></span>
- <span data-ttu-id="9c5e0-156">Datumnotatie dd/MM/yy</span><span class="sxs-lookup"><span data-stu-id="9c5e0-156">Date format dd/MM/yy</span></span>
- <span data-ttu-id="9c5e0-157">Datumnotatie MM/dd/yy</span><span class="sxs-lookup"><span data-stu-id="9c5e0-157">Date format MM/dd/yy</span></span>
- <span data-ttu-id="9c5e0-158">Datumnotatie met yy.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-158">Date format with yy.</span></span> <span data-ttu-id="9c5e0-159">Toont alleen yyyy.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-159">Will only show yyyy.</span></span>
- <span data-ttu-id="9c5e0-160">Tijdnotatie HH:mm:ss (24 uursnotatie)</span><span class="sxs-lookup"><span data-stu-id="9c5e0-160">Time format HH:mm:ss (24 hour format)</span></span>

<span data-ttu-id="9c5e0-161">**Decimaal symbool dat wordt gebruikt in getallen**</span><span class="sxs-lookup"><span data-stu-id="9c5e0-161">**Decimal symbol used in numbers**</span></span><br>
<span data-ttu-id="9c5e0-162">Het gebruikte decimale symbool is altijd een punt,  zelfs als een komma is geselecteerd in de instellingen voor de notatie Getallen in **regio-instellingen.**</span><span class="sxs-lookup"><span data-stu-id="9c5e0-162">Decimal symbol used is always a dot, even if a comma is selected in  the **Numbers** format settings in **Region** settings.</span></span> <span data-ttu-id="9c5e0-163">15,5K wordt bijvoorbeeld weergegeven als 15,5K.</span><span class="sxs-lookup"><span data-stu-id="9c5e0-163">For example, 15,5K is displayed as 15.5K.</span></span>


