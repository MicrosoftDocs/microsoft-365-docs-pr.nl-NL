---
title: Updates implementeren voor Microsoft Defender ATP voor Mac
description: Updates voor Microsoft Defender ATP voor Mac beheren in bedrijfsomgevingen.
keywords: microsoft, defender, atp, mac, updates, deploy
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
ms.openlocfilehash: 99f507ad381ee21ba91753716439180fafe37c24
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059414"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="a9f1f-104">Updates implementeren voor Microsoft Defender voor Eindpunt voor Mac</span><span class="sxs-lookup"><span data-stu-id="a9f1f-104">Deploy updates for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a9f1f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-105">**Applies to:**</span></span>

- [<span data-ttu-id="a9f1f-106">Microsoft Defender voor Eindpunt voor Mac</span><span class="sxs-lookup"><span data-stu-id="a9f1f-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="a9f1f-107">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="a9f1f-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a9f1f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a9f1f-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a9f1f-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="a9f1f-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a9f1f-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="a9f1f-111">Microsoft publiceert regelmatig software-updates om de prestaties, beveiliging en nieuwe functies te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="a9f1f-112">Als u Microsoft Defender voor Eindpunt voor Mac wilt bijwerken, wordt een programma met de naam Microsoft AutoUpdate (MAU) gebruikt.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-112">To update Microsoft Defender for Endpoint for Mac, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="a9f1f-113">Mau controleert standaard automatisch dagelijks op updates, maar u kunt dit wijzigen in wekelijks, maandelijks of handmatig.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![MAU-schermafbeelding](images/MDATP-34-MAU.png)

<span data-ttu-id="a9f1f-115">Als u besluit updates te implementeren met behulp van uw softwaredistributieprogramma's, moet u MAU configureren om handmatig te controleren op software-updates.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="a9f1f-116">U kunt voorkeuren implementeren om te configureren hoe en wanneer MAU controleert op updates voor de Macs in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="a9f1f-117">Msupdate gebruiken</span><span class="sxs-lookup"><span data-stu-id="a9f1f-117">Use msupdate</span></span>

<span data-ttu-id="a9f1f-118">MAU bevat een opdrachtregelhulpmiddel, *msupdate* genoemd, dat is ontworpen voor IT-beheerders, zodat ze nauwkeuriger kunnen bepalen wanneer updates worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="a9f1f-119">Instructies voor het gebruik van dit hulpprogramma vindt u in [Office voor Mac bijwerken met msupdate.](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)</span><span class="sxs-lookup"><span data-stu-id="a9f1f-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="a9f1f-120">In MAU is de toepassingsaanduiding voor Microsoft Defender voor Eindpunt voor Mac *WDAV00*.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-120">In MAU, the application identifier for Microsoft Defender for Endpoint for Mac is *WDAV00*.</span></span> <span data-ttu-id="a9f1f-121">Als u de nieuwste updates voor Microsoft Defender voor Eindpunt voor Mac wilt downloaden en installeren, voert u de volgende opdracht uit vanuit een terminalvenster:</span><span class="sxs-lookup"><span data-stu-id="a9f1f-121">To download and install the latest updates for Microsoft Defender for Endpoint for Mac, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="a9f1f-122">Voorkeuren instellen voor Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="a9f1f-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="a9f1f-123">In deze sectie worden de meest voorkomende voorkeuren beschreven die kunnen worden gebruikt om MAU te configureren.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="a9f1f-124">Deze instellingen kunnen als configuratieprofiel worden geïmplementeerd via de beheerconsole die uw bedrijf gebruikt.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="a9f1f-125">Een voorbeeld van een configuratieprofiel wordt weergegeven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="a9f1f-126">De kanaalnaam instellen</span><span class="sxs-lookup"><span data-stu-id="a9f1f-126">Set the channel name</span></span>

<span data-ttu-id="a9f1f-127">Het kanaal bepaalt het type en de frequentie van updates die worden aangeboden via MAU.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="a9f1f-128">Apparaten in `Beta` kunnen nieuwe functies uitproberen voordat apparaten in en `Preview` `Current` .</span><span class="sxs-lookup"><span data-stu-id="a9f1f-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="a9f1f-129">Het `Current` kanaal bevat de meest stabiele versie van het product.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="a9f1f-130">Voorafgaand aan Microsoft AutoUpdate versie 4.29 hadden kanalen verschillende namen:</span><span class="sxs-lookup"><span data-stu-id="a9f1f-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="a9f1f-131">`Beta` is benoemd `InsiderFast` (Insider Fast)</span><span class="sxs-lookup"><span data-stu-id="a9f1f-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="a9f1f-132">`Preview` is benoemd `External` (Insider Slow)</span><span class="sxs-lookup"><span data-stu-id="a9f1f-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="a9f1f-133">`Current` is benoemd `Production`</span><span class="sxs-lookup"><span data-stu-id="a9f1f-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="a9f1f-134">Als u een voorbeeld van nieuwe functies wilt bekijken en vroegtijdig feedback wilt geven, wordt u aangeraden bepaalde apparaten in uw bedrijf te configureren op `Beta` of `Preview` .</span><span class="sxs-lookup"><span data-stu-id="a9f1f-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|||
|:--|:--|
| <span data-ttu-id="a9f1f-135">**Domein**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-135">**Domain**</span></span> | <span data-ttu-id="a9f1f-136">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="a9f1f-136">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="a9f1f-137">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-137">**Key**</span></span> | <span data-ttu-id="a9f1f-138">Kanaalnaam</span><span class="sxs-lookup"><span data-stu-id="a9f1f-138">ChannelName</span></span> |
| <span data-ttu-id="a9f1f-139">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-139">**Data type**</span></span> | <span data-ttu-id="a9f1f-140">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a9f1f-140">String</span></span> |
| <span data-ttu-id="a9f1f-141">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-141">**Possible values**</span></span> | <span data-ttu-id="a9f1f-142">Beta</span><span class="sxs-lookup"><span data-stu-id="a9f1f-142">Beta</span></span> <br/> <span data-ttu-id="a9f1f-143">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="a9f1f-143">Preview</span></span> <br/> <span data-ttu-id="a9f1f-144">Huidige</span><span class="sxs-lookup"><span data-stu-id="a9f1f-144">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="a9f1f-145">Met deze instelling wordt het kanaal gewijzigd voor alle toepassingen die worden bijgewerkt via Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-145">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="a9f1f-146">Als u het kanaal alleen wilt wijzigen voor Microsoft Defender voor Eindpunt voor Mac, voert u de volgende opdracht uit nadat u het kanaal hebt `[channel-name]` vervangen door het gewenste kanaal:</span><span class="sxs-lookup"><span data-stu-id="a9f1f-146">To change the channel only for Microsoft Defender for Endpoint for Mac, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="a9f1f-147">Updatecontrolefrequentie instellen</span><span class="sxs-lookup"><span data-stu-id="a9f1f-147">Set update check frequency</span></span>

<span data-ttu-id="a9f1f-148">Wijzig hoe vaak MAU naar updates zoekt.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-148">Change how often MAU searches for updates.</span></span>

|||
|:--|:--|
| <span data-ttu-id="a9f1f-149">**Domein**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-149">**Domain**</span></span> | <span data-ttu-id="a9f1f-150">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="a9f1f-150">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="a9f1f-151">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-151">**Key**</span></span> | <span data-ttu-id="a9f1f-152">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="a9f1f-152">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="a9f1f-153">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-153">**Data type**</span></span> | <span data-ttu-id="a9f1f-154">Geheel getal</span><span class="sxs-lookup"><span data-stu-id="a9f1f-154">Integer</span></span> |
| <span data-ttu-id="a9f1f-155">**Standaardwaarde**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-155">**Default value**</span></span> | <span data-ttu-id="a9f1f-156">720 (minuten)</span><span class="sxs-lookup"><span data-stu-id="a9f1f-156">720 (minutes)</span></span> |
| <span data-ttu-id="a9f1f-157">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-157">**Comment**</span></span> | <span data-ttu-id="a9f1f-158">Deze waarde wordt in minuten ingesteld.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-158">This value is set in minutes.</span></span> |
|||

### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="a9f1f-159">De interactie tussen MAU en updates wijzigen</span><span class="sxs-lookup"><span data-stu-id="a9f1f-159">Change how MAU interacts with updates</span></span>

<span data-ttu-id="a9f1f-160">Wijzig de manier waarop MAU zoekt naar updates.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-160">Change how MAU searches for updates.</span></span>

|||
|:--|:--|
| <span data-ttu-id="a9f1f-161">**Domein**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-161">**Domain**</span></span> | <span data-ttu-id="a9f1f-162">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="a9f1f-162">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="a9f1f-163">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-163">**Key**</span></span> | <span data-ttu-id="a9f1f-164">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="a9f1f-164">HowToCheck</span></span> |
| <span data-ttu-id="a9f1f-165">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-165">**Data type**</span></span> | <span data-ttu-id="a9f1f-166">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a9f1f-166">String</span></span> |
| <span data-ttu-id="a9f1f-167">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-167">**Possible values**</span></span> | <span data-ttu-id="a9f1f-168">Handmatig</span><span class="sxs-lookup"><span data-stu-id="a9f1f-168">Manual</span></span> <br/> <span data-ttu-id="a9f1f-169">Automatisch controleren</span><span class="sxs-lookup"><span data-stu-id="a9f1f-169">AutomaticCheck</span></span> <br/> <span data-ttu-id="a9f1f-170">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="a9f1f-170">AutomaticDownload</span></span> |
| <span data-ttu-id="a9f1f-171">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-171">**Comment**</span></span> |  <span data-ttu-id="a9f1f-172">Houd er rekening mee dat AutomaticDownload indien mogelijk wordt gedownload en geruisloos wordt geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-172">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |
|||

### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="a9f1f-173">Wijzigen of de knop Controleren op updates is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="a9f1f-173">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="a9f1f-174">Wijzig of lokale gebruikers kunnen klikken op de optie Controleren op updates in de gebruikersinterface van Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-174">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|||
|:--|:--|
| <span data-ttu-id="a9f1f-175">**Domein**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-175">**Domain**</span></span> | <span data-ttu-id="a9f1f-176">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="a9f1f-176">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="a9f1f-177">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-177">**Key**</span></span> | <span data-ttu-id="a9f1f-178">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="a9f1f-178">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="a9f1f-179">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-179">**Data type**</span></span> | <span data-ttu-id="a9f1f-180">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="a9f1f-180">Boolean</span></span> |
| <span data-ttu-id="a9f1f-181">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-181">**Possible values**</span></span> | <span data-ttu-id="a9f1f-182">Waar (standaard)</span><span class="sxs-lookup"><span data-stu-id="a9f1f-182">True (default)</span></span> <br/> <span data-ttu-id="a9f1f-183">Onwaar</span><span class="sxs-lookup"><span data-stu-id="a9f1f-183">False</span></span> |
|||

### <a name="disable-insider-checkbox"></a><span data-ttu-id="a9f1f-184">Selectievakje Insider uitschakelen</span><span class="sxs-lookup"><span data-stu-id="a9f1f-184">Disable Insider checkbox</span></span>

<span data-ttu-id="a9f1f-185">Ingesteld op waar om het 'Deelnemen aan het Office Insider-programma' te maken... selectievakje niet beschikbaar / grijs voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-185">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|||
|:--|:--|
| <span data-ttu-id="a9f1f-186">**Domein**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-186">**Domain**</span></span> | <span data-ttu-id="a9f1f-187">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="a9f1f-187">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="a9f1f-188">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-188">**Key**</span></span> | <span data-ttu-id="a9f1f-189">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="a9f1f-189">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="a9f1f-190">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-190">**Data type**</span></span> | <span data-ttu-id="a9f1f-191">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="a9f1f-191">Boolean</span></span> |
| <span data-ttu-id="a9f1f-192">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-192">**Possible values**</span></span> | <span data-ttu-id="a9f1f-193">Onwaar (standaard)</span><span class="sxs-lookup"><span data-stu-id="a9f1f-193">False (default)</span></span> <br/> <span data-ttu-id="a9f1f-194">Waar</span><span class="sxs-lookup"><span data-stu-id="a9f1f-194">True</span></span> |
|||

### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="a9f1f-195">De telemetrie beperken die wordt verzonden vanuit MAU</span><span class="sxs-lookup"><span data-stu-id="a9f1f-195">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="a9f1f-196">Instellen op onwaar om minimale heartbeatgegevens te verzenden, geen toepassingsgebruik en geen omgevingsgegevens.</span><span class="sxs-lookup"><span data-stu-id="a9f1f-196">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|||
|:--|:--|
| <span data-ttu-id="a9f1f-197">**Domein**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-197">**Domain**</span></span> | <span data-ttu-id="a9f1f-198">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="a9f1f-198">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="a9f1f-199">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-199">**Key**</span></span> | <span data-ttu-id="a9f1f-200">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="a9f1f-200">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="a9f1f-201">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-201">**Data type**</span></span> | <span data-ttu-id="a9f1f-202">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="a9f1f-202">Boolean</span></span> |
| <span data-ttu-id="a9f1f-203">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="a9f1f-203">**Possible values**</span></span> | <span data-ttu-id="a9f1f-204">Waar (standaard)</span><span class="sxs-lookup"><span data-stu-id="a9f1f-204">True (default)</span></span> <br/> <span data-ttu-id="a9f1f-205">Onwaar</span><span class="sxs-lookup"><span data-stu-id="a9f1f-205">False</span></span> |
|||

## <a name="example-configuration-profile"></a><span data-ttu-id="a9f1f-206">Voorbeeld van configuratieprofiel</span><span class="sxs-lookup"><span data-stu-id="a9f1f-206">Example configuration profile</span></span>

<span data-ttu-id="a9f1f-207">Het volgende configuratieprofiel wordt gebruikt om:</span><span class="sxs-lookup"><span data-stu-id="a9f1f-207">The following configuration profile is used to:</span></span>
- <span data-ttu-id="a9f1f-208">Het apparaat in het bètakanaal plaatsen</span><span class="sxs-lookup"><span data-stu-id="a9f1f-208">Place the device in the Beta channel</span></span>
- <span data-ttu-id="a9f1f-209">Updates automatisch downloaden en installeren</span><span class="sxs-lookup"><span data-stu-id="a9f1f-209">Automatically download and install updates</span></span>
- <span data-ttu-id="a9f1f-210">De knop Controleren op updates inschakelen in de gebruikersinterface</span><span class="sxs-lookup"><span data-stu-id="a9f1f-210">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="a9f1f-211">Gebruikers op het apparaat toestaan zich aan te melden bij de Insider-kanalen</span><span class="sxs-lookup"><span data-stu-id="a9f1f-211">Allow users on the device to enroll into the Insider channels</span></span>

### <a name="jamf"></a><span data-ttu-id="a9f1f-212">JAMF</span><span class="sxs-lookup"><span data-stu-id="a9f1f-212">JAMF</span></span>

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

### <a name="intune"></a><span data-ttu-id="a9f1f-213">Intune</span><span class="sxs-lookup"><span data-stu-id="a9f1f-213">Intune</span></span>

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

<span data-ttu-id="a9f1f-214">Als u MAU wilt configureren, kunt u dit configuratieprofiel implementeren vanuit het beheerprogramma dat uw bedrijf gebruikt:</span><span class="sxs-lookup"><span data-stu-id="a9f1f-214">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="a9f1f-215">Upload dit configuratieprofiel vanuit JAMF en stel het voorkeursdomein in *op com.microsoft.autoupdate2.*</span><span class="sxs-lookup"><span data-stu-id="a9f1f-215">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="a9f1f-216">Upload dit configuratieprofiel vanuit Intune en stel de naam van het aangepaste configuratieprofiel in *op com.microsoft.autoupdate2.*</span><span class="sxs-lookup"><span data-stu-id="a9f1f-216">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="a9f1f-217">Resources</span><span class="sxs-lookup"><span data-stu-id="a9f1f-217">Resources</span></span>

- [<span data-ttu-id="a9f1f-218">msupdate-verwijzing</span><span class="sxs-lookup"><span data-stu-id="a9f1f-218">msupdate reference</span></span>](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
