---
title: Updates implementeren voor Microsoft Defender voor Eindpunt op Mac
description: Updates voor Microsoft Defender voor Eindpunt voor Mac beheren in bedrijfsomgevingen.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, updates, deploy
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 886195de38856306d69932446eae34212fe4bb0d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934499"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="338d0-104">Updates voor Microsoft Defender voor Eindpunt implementeren in macOS</span><span class="sxs-lookup"><span data-stu-id="338d0-104">Deploy updates for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="338d0-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="338d0-105">**Applies to:**</span></span>

- [<span data-ttu-id="338d0-106">Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="338d0-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="338d0-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="338d0-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="338d0-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="338d0-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="338d0-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="338d0-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="338d0-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="338d0-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="338d0-111">Microsoft publiceert regelmatig software-updates om de prestaties, beveiliging en nieuwe functies te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="338d0-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="338d0-112">Als u Microsoft Defender voor Eindpunt wilt bijwerken op macOS, wordt een programma met de naam Microsoft AutoUpdate (MAU) gebruikt.</span><span class="sxs-lookup"><span data-stu-id="338d0-112">To update Microsoft Defender for Endpoint on macOS, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="338d0-113">Mau controleert standaard automatisch dagelijks op updates, maar u kunt dit wijzigen in wekelijks, maandelijks of handmatig.</span><span class="sxs-lookup"><span data-stu-id="338d0-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![MAU-schermafbeelding](images/MDATP-34-MAU.png)

<span data-ttu-id="338d0-115">Als u besluit updates te implementeren met behulp van uw softwaredistributieprogramma's, moet u MAU configureren om handmatig te controleren op software-updates.</span><span class="sxs-lookup"><span data-stu-id="338d0-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="338d0-116">U kunt voorkeuren implementeren om te configureren hoe en wanneer MAU controleert op updates voor de Macs in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="338d0-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="338d0-117">Msupdate gebruiken</span><span class="sxs-lookup"><span data-stu-id="338d0-117">Use msupdate</span></span>

<span data-ttu-id="338d0-118">MAU bevat een opdrachtregelhulpmiddel, *msupdate* genoemd, dat is ontworpen voor IT-beheerders, zodat ze nauwkeuriger kunnen bepalen wanneer updates worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="338d0-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="338d0-119">Instructies voor het gebruik van dit hulpprogramma vindt u in [Office voor Mac bijwerken met msupdate.](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)</span><span class="sxs-lookup"><span data-stu-id="338d0-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="338d0-120">In MAU is de toepassingsaanduiding voor Microsoft Defender voor Eindpunt op macOS *WDAV00.*</span><span class="sxs-lookup"><span data-stu-id="338d0-120">In MAU, the application identifier for Microsoft Defender for Endpoint on macOS is *WDAV00*.</span></span> <span data-ttu-id="338d0-121">Als u de nieuwste updates voor Microsoft Defender voor Eindpunt voor macOS wilt downloaden en installeren, voert u de volgende opdracht uit vanuit een terminalvenster:</span><span class="sxs-lookup"><span data-stu-id="338d0-121">To download and install the latest updates for Microsoft Defender for Endpoint on macOS, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="338d0-122">Voorkeuren instellen voor Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="338d0-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="338d0-123">In deze sectie worden de meest voorkomende voorkeuren beschreven die kunnen worden gebruikt om MAU te configureren.</span><span class="sxs-lookup"><span data-stu-id="338d0-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="338d0-124">Deze instellingen kunnen als configuratieprofiel worden geïmplementeerd via de beheerconsole die uw bedrijf gebruikt.</span><span class="sxs-lookup"><span data-stu-id="338d0-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="338d0-125">Een voorbeeld van een configuratieprofiel wordt weergegeven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="338d0-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="338d0-126">De kanaalnaam instellen</span><span class="sxs-lookup"><span data-stu-id="338d0-126">Set the channel name</span></span>

<span data-ttu-id="338d0-127">Het kanaal bepaalt het type en de frequentie van updates die worden aangeboden via MAU.</span><span class="sxs-lookup"><span data-stu-id="338d0-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="338d0-128">Apparaten in `Beta` kunnen nieuwe functies uitproberen voordat apparaten in en `Preview` `Current` .</span><span class="sxs-lookup"><span data-stu-id="338d0-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="338d0-129">Het `Current` kanaal bevat de meest stabiele versie van het product.</span><span class="sxs-lookup"><span data-stu-id="338d0-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="338d0-130">Voorafgaand aan Microsoft AutoUpdate versie 4.29 hadden kanalen verschillende namen:</span><span class="sxs-lookup"><span data-stu-id="338d0-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="338d0-131">`Beta` is benoemd `InsiderFast` (Insider Fast)</span><span class="sxs-lookup"><span data-stu-id="338d0-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="338d0-132">`Preview` is benoemd `External` (Insider Slow)</span><span class="sxs-lookup"><span data-stu-id="338d0-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="338d0-133">`Current` is benoemd `Production`</span><span class="sxs-lookup"><span data-stu-id="338d0-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="338d0-134">Als u een voorbeeld van nieuwe functies wilt bekijken en vroegtijdig feedback wilt geven, wordt u aangeraden bepaalde apparaten in uw bedrijf te configureren op `Beta` of `Preview` .</span><span class="sxs-lookup"><span data-stu-id="338d0-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|<span data-ttu-id="338d0-135">Sectie</span><span class="sxs-lookup"><span data-stu-id="338d0-135">Section</span></span>|<span data-ttu-id="338d0-136">Waarde</span><span class="sxs-lookup"><span data-stu-id="338d0-136">Value</span></span>|
|:--|:--|
| <span data-ttu-id="338d0-137">**Domein**</span><span class="sxs-lookup"><span data-stu-id="338d0-137">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="338d0-138">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="338d0-138">**Key**</span></span> | <span data-ttu-id="338d0-139">Kanaalnaam</span><span class="sxs-lookup"><span data-stu-id="338d0-139">ChannelName</span></span> |
| <span data-ttu-id="338d0-140">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="338d0-140">**Data type**</span></span> | <span data-ttu-id="338d0-141">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="338d0-141">String</span></span> |
| <span data-ttu-id="338d0-142">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="338d0-142">**Possible values**</span></span> | <span data-ttu-id="338d0-143">Beta</span><span class="sxs-lookup"><span data-stu-id="338d0-143">Beta</span></span> <br/> <span data-ttu-id="338d0-144">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="338d0-144">Preview</span></span> <br/> <span data-ttu-id="338d0-145">Huidige</span><span class="sxs-lookup"><span data-stu-id="338d0-145">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="338d0-146">Met deze instelling wordt het kanaal gewijzigd voor alle toepassingen die worden bijgewerkt via Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="338d0-146">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="338d0-147">Als u het kanaal alleen wilt wijzigen voor Microsoft Defender voor Eindpunt in macOS, voert u de volgende opdracht uit nadat u het kanaal hebt vervangen door `[channel-name]` het gewenste kanaal:</span><span class="sxs-lookup"><span data-stu-id="338d0-147">To change the channel only for Microsoft Defender for Endpoint on macOS, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="338d0-148">Updatecontrolefrequentie instellen</span><span class="sxs-lookup"><span data-stu-id="338d0-148">Set update check frequency</span></span>

<span data-ttu-id="338d0-149">Wijzig hoe vaak MAU naar updates zoekt.</span><span class="sxs-lookup"><span data-stu-id="338d0-149">Change how often MAU searches for updates.</span></span>

|<span data-ttu-id="338d0-150">Sectie</span><span class="sxs-lookup"><span data-stu-id="338d0-150">Section</span></span>|<span data-ttu-id="338d0-151">Waarde</span><span class="sxs-lookup"><span data-stu-id="338d0-151">Value</span></span>|
|:--|:--|
| <span data-ttu-id="338d0-152">**Domein**</span><span class="sxs-lookup"><span data-stu-id="338d0-152">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="338d0-153">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="338d0-153">**Key**</span></span> | <span data-ttu-id="338d0-154">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="338d0-154">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="338d0-155">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="338d0-155">**Data type**</span></span> | <span data-ttu-id="338d0-156">Geheel getal</span><span class="sxs-lookup"><span data-stu-id="338d0-156">Integer</span></span> |
| <span data-ttu-id="338d0-157">**Standaardwaarde**</span><span class="sxs-lookup"><span data-stu-id="338d0-157">**Default value**</span></span> | <span data-ttu-id="338d0-158">720 (minuten)</span><span class="sxs-lookup"><span data-stu-id="338d0-158">720 (minutes)</span></span> |
| <span data-ttu-id="338d0-159">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="338d0-159">**Comment**</span></span> | <span data-ttu-id="338d0-160">Deze waarde wordt in minuten ingesteld.</span><span class="sxs-lookup"><span data-stu-id="338d0-160">This value is set in minutes.</span></span> |


### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="338d0-161">De interactie tussen MAU en updates wijzigen</span><span class="sxs-lookup"><span data-stu-id="338d0-161">Change how MAU interacts with updates</span></span>

<span data-ttu-id="338d0-162">Wijzig de manier waarop MAU zoekt naar updates.</span><span class="sxs-lookup"><span data-stu-id="338d0-162">Change how MAU searches for updates.</span></span>

|<span data-ttu-id="338d0-163">Sectie</span><span class="sxs-lookup"><span data-stu-id="338d0-163">Section</span></span>|<span data-ttu-id="338d0-164">Waarde</span><span class="sxs-lookup"><span data-stu-id="338d0-164">Value</span></span>|
|:--|:--|
| <span data-ttu-id="338d0-165">**Domein**</span><span class="sxs-lookup"><span data-stu-id="338d0-165">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="338d0-166">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="338d0-166">**Key**</span></span> | <span data-ttu-id="338d0-167">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="338d0-167">HowToCheck</span></span> |
| <span data-ttu-id="338d0-168">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="338d0-168">**Data type**</span></span> | <span data-ttu-id="338d0-169">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="338d0-169">String</span></span> |
| <span data-ttu-id="338d0-170">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="338d0-170">**Possible values**</span></span> | <span data-ttu-id="338d0-171">Handmatig</span><span class="sxs-lookup"><span data-stu-id="338d0-171">Manual</span></span> <br/> <span data-ttu-id="338d0-172">Automatisch controleren</span><span class="sxs-lookup"><span data-stu-id="338d0-172">AutomaticCheck</span></span> <br/> <span data-ttu-id="338d0-173">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="338d0-173">AutomaticDownload</span></span> |
| <span data-ttu-id="338d0-174">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="338d0-174">**Comment**</span></span> |  <span data-ttu-id="338d0-175">Houd er rekening mee dat AutomaticDownload indien mogelijk wordt gedownload en geruisloos wordt geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="338d0-175">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="338d0-176">Wijzigen of de knop Controleren op updates is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="338d0-176">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="338d0-177">Wijzig of lokale gebruikers kunnen klikken op de optie Controleren op updates in de gebruikersinterface van Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="338d0-177">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|<span data-ttu-id="338d0-178">Sectie</span><span class="sxs-lookup"><span data-stu-id="338d0-178">Section</span></span>|<span data-ttu-id="338d0-179">Waarde</span><span class="sxs-lookup"><span data-stu-id="338d0-179">Value</span></span>|
|:--|:--|
| <span data-ttu-id="338d0-180">**Domein**</span><span class="sxs-lookup"><span data-stu-id="338d0-180">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="338d0-181">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="338d0-181">**Key**</span></span> | <span data-ttu-id="338d0-182">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="338d0-182">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="338d0-183">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="338d0-183">**Data type**</span></span> | <span data-ttu-id="338d0-184">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="338d0-184">Boolean</span></span> |
| <span data-ttu-id="338d0-185">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="338d0-185">**Possible values**</span></span> | <span data-ttu-id="338d0-186">Waar (standaard)</span><span class="sxs-lookup"><span data-stu-id="338d0-186">True (default)</span></span> <br/> <span data-ttu-id="338d0-187">Onwaar</span><span class="sxs-lookup"><span data-stu-id="338d0-187">False</span></span> |


### <a name="disable-insider-checkbox"></a><span data-ttu-id="338d0-188">Selectievakje Insider uitschakelen</span><span class="sxs-lookup"><span data-stu-id="338d0-188">Disable Insider checkbox</span></span>

<span data-ttu-id="338d0-189">Ingesteld op waar om het 'Deelnemen aan het Office Insider-programma' te maken... selectievakje niet beschikbaar / grijs voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="338d0-189">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|<span data-ttu-id="338d0-190">Sectie</span><span class="sxs-lookup"><span data-stu-id="338d0-190">Section</span></span>|<span data-ttu-id="338d0-191">Waarde</span><span class="sxs-lookup"><span data-stu-id="338d0-191">Value</span></span>|
|:--|:--|
| <span data-ttu-id="338d0-192">**Domein**</span><span class="sxs-lookup"><span data-stu-id="338d0-192">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="338d0-193">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="338d0-193">**Key**</span></span> | <span data-ttu-id="338d0-194">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="338d0-194">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="338d0-195">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="338d0-195">**Data type**</span></span> | <span data-ttu-id="338d0-196">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="338d0-196">Boolean</span></span> |
| <span data-ttu-id="338d0-197">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="338d0-197">**Possible values**</span></span> | <span data-ttu-id="338d0-198">Onwaar (standaard)</span><span class="sxs-lookup"><span data-stu-id="338d0-198">False (default)</span></span> <br/> <span data-ttu-id="338d0-199">Waar</span><span class="sxs-lookup"><span data-stu-id="338d0-199">True</span></span> |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="338d0-200">De telemetrie beperken die wordt verzonden vanuit MAU</span><span class="sxs-lookup"><span data-stu-id="338d0-200">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="338d0-201">Instellen op onwaar om minimale heartbeatgegevens te verzenden, geen toepassingsgebruik en geen omgevingsgegevens.</span><span class="sxs-lookup"><span data-stu-id="338d0-201">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|<span data-ttu-id="338d0-202">Sectie</span><span class="sxs-lookup"><span data-stu-id="338d0-202">Section</span></span>|<span data-ttu-id="338d0-203">Waarde</span><span class="sxs-lookup"><span data-stu-id="338d0-203">Value</span></span>|
|:--|:--|
| <span data-ttu-id="338d0-204">**Domein**</span><span class="sxs-lookup"><span data-stu-id="338d0-204">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="338d0-205">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="338d0-205">**Key**</span></span> | <span data-ttu-id="338d0-206">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="338d0-206">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="338d0-207">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="338d0-207">**Data type**</span></span> | <span data-ttu-id="338d0-208">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="338d0-208">Boolean</span></span> |
| <span data-ttu-id="338d0-209">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="338d0-209">**Possible values**</span></span> | <span data-ttu-id="338d0-210">Waar (standaard)</span><span class="sxs-lookup"><span data-stu-id="338d0-210">True (default)</span></span> <br/> <span data-ttu-id="338d0-211">Onwaar</span><span class="sxs-lookup"><span data-stu-id="338d0-211">False</span></span> |


## <a name="example-configuration-profile"></a><span data-ttu-id="338d0-212">Voorbeeld van configuratieprofiel</span><span class="sxs-lookup"><span data-stu-id="338d0-212">Example configuration profile</span></span>

<span data-ttu-id="338d0-213">Het volgende configuratieprofiel wordt gebruikt om:</span><span class="sxs-lookup"><span data-stu-id="338d0-213">The following configuration profile is used to:</span></span>
- <span data-ttu-id="338d0-214">Het apparaat in het bètakanaal plaatsen</span><span class="sxs-lookup"><span data-stu-id="338d0-214">Place the device in the Beta channel</span></span>
- <span data-ttu-id="338d0-215">Updates automatisch downloaden en installeren</span><span class="sxs-lookup"><span data-stu-id="338d0-215">Automatically download and install updates</span></span>
- <span data-ttu-id="338d0-216">De knop Controleren op updates inschakelen in de gebruikersinterface</span><span class="sxs-lookup"><span data-stu-id="338d0-216">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="338d0-217">Gebruikers op het apparaat toestaan zich aan te melden bij de Insider-kanalen</span><span class="sxs-lookup"><span data-stu-id="338d0-217">Allow users on the device to enroll into the Insider channels</span></span>

### <a name="jamf"></a><span data-ttu-id="338d0-218">JAMF</span><span class="sxs-lookup"><span data-stu-id="338d0-218">JAMF</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Beta</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
</dict>
</plist>
```

### <a name="intune"></a><span data-ttu-id="338d0-219">Intune</span><span class="sxs-lookup"><span data-stu-id="338d0-219">Intune</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Beta</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```

<span data-ttu-id="338d0-220">Als u MAU wilt configureren, kunt u dit configuratieprofiel implementeren vanuit het beheerprogramma dat uw bedrijf gebruikt:</span><span class="sxs-lookup"><span data-stu-id="338d0-220">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="338d0-221">Upload dit configuratieprofiel vanuit JAMF en stel het voorkeursdomein in *op com.microsoft.autoupdate2.*</span><span class="sxs-lookup"><span data-stu-id="338d0-221">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="338d0-222">Upload dit configuratieprofiel vanuit Intune en stel de naam van het aangepaste configuratieprofiel in *op com.microsoft.autoupdate2.*</span><span class="sxs-lookup"><span data-stu-id="338d0-222">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="338d0-223">Resources</span><span class="sxs-lookup"><span data-stu-id="338d0-223">Resources</span></span>

- [<span data-ttu-id="338d0-224">msupdate-verwijzing</span><span class="sxs-lookup"><span data-stu-id="338d0-224">msupdate reference</span></span>](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
