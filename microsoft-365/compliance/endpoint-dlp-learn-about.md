---
title: Meer informatie over Microsoft 365 Eindpunt-DLP
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'Microsoft 365 Preventie van gegevensverlies voor eindpunten breidt de controle van bestandsactiviteiten en beschermende maatregelen uit voor deze bestanden naar eindpunten. Bestanden worden zichtbaar gemaakt in de compliance-oplossingen van Microsoft 365 '
ms.openlocfilehash: b5aa6c737bc54129ce49378a7dcaf81e9d5c612f
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162898"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="cb266-104">Meer informatie over Microsoft 365 Eindpunt-DLP</span><span class="sxs-lookup"><span data-stu-id="cb266-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="cb266-105">U kunt preventie van gegevensverlies van Microsoft 365 (DLP) gebruiken om te controleren welke acties worden ondernomen op items die u vertrouwelijk vindt en om te voorkomen dat deze items per ongeluk worden gedeeld.</span><span class="sxs-lookup"><span data-stu-id="cb266-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="cb266-106">Zie voor meer informatie over DLP [Meer informatie over preventie van gegevensverlies](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="cb266-106">For more information on DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="cb266-107">**Preventie van gegevensverlies voor eindpunten)** (Eindpunt-DLP) is een uitbreiding voor de activiteitencontrole en beveiligingsmogelijkheden van DLP voor vertrouwelijke items op Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="cb266-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="cb266-108">Zodra apparaten zijn geregistreerd bij de Microsoft 365-complianceoplossingen, wordt de informatie over wat gebruikers met gevoelige items doen, zichtbaar in [Activiteitenverkenner](data-classification-activity-explorer.md) en kunt u beschermende maatregelen voor deze items afdwingen via [DLP-beleid](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="cb266-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="cb266-109">EIndpuntactiviteiten die u kunt controleren en waarvoor u maatregelen kunt nemen</span><span class="sxs-lookup"><span data-stu-id="cb266-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="cb266-110">Met Microsoft Endpoint DLP kunt u de typen activiteiten die gebruikers uitvoeren op vertrouwelijke items, controleren en beheren op apparaten met Windows 10.</span><span class="sxs-lookup"><span data-stu-id="cb266-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> 

|<span data-ttu-id="cb266-111">Activiteit</span><span class="sxs-lookup"><span data-stu-id="cb266-111">Activity</span></span> |<span data-ttu-id="cb266-112">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="cb266-112">Description</span></span>  | <span data-ttu-id="cb266-113">Controleerbaar/beperkbaar</span><span class="sxs-lookup"><span data-stu-id="cb266-113">Auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="cb266-114">Naar cloudservice uploaden of openen via niet-toegestane browsers</span><span class="sxs-lookup"><span data-stu-id="cb266-114">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="cb266-115">Hiermee wordt gedetecteerd wanneer een gebruiker probeert om een item te uploaden naar een beperkt servicedomein of een item via een browser probeert te openen.</span><span class="sxs-lookup"><span data-stu-id="cb266-115">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="cb266-116">Als ze een browser gebruiken die in DLP is opgenomen als een niet-toegestaan browser, wordt de uploadactiviteit geblokkeerd en wordt de gebruiker omgeleid naar Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="cb266-116">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="cb266-117">Edge Chromium staat vervolgens het uploaden of de toegang toe of blokkeert het op basis van de configuratie van het DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="cb266-117">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="cb266-118">controleerbaar en beperkbaar</span><span class="sxs-lookup"><span data-stu-id="cb266-118">auditable and restrictable</span></span>|
|<span data-ttu-id="cb266-119">kopiëren naar andere app</span><span class="sxs-lookup"><span data-stu-id="cb266-119">copy to other app</span></span>    |<span data-ttu-id="cb266-120">Hiermee wordt gedetecteerd wanneer een gebruiker informatie uit een beveiligd item probeert te kopiëren en vervolgens te plakken in een andere app, of in een ander proces of item.</span><span class="sxs-lookup"><span data-stu-id="cb266-120">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="cb266-121">Het kopiëren en plakken van gegevens binnen dezelfde app, hetzelfde proces of item wordt niet gedetecteerd door deze activiteit.</span><span class="sxs-lookup"><span data-stu-id="cb266-121">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="cb266-122">controleerbaar en beperkbaar</span><span class="sxs-lookup"><span data-stu-id="cb266-122">auditable and restrictable</span></span>|
|<span data-ttu-id="cb266-123">kopiëren naar verwisselbare USB-media</span><span class="sxs-lookup"><span data-stu-id="cb266-123">copy to USB removable media</span></span> |<span data-ttu-id="cb266-124">Detecteert wanneer een gebruiker een item of gegevens probeert te kopiëren naar een verwisselbaar medium of USB-apparaat.</span><span class="sxs-lookup"><span data-stu-id="cb266-124">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="cb266-125">controleerbaar en beperkbaar</span><span class="sxs-lookup"><span data-stu-id="cb266-125">auditable and restrictable</span></span>|
|<span data-ttu-id="cb266-126">kopiëren naar een netwerkshare</span><span class="sxs-lookup"><span data-stu-id="cb266-126">copy to a network share</span></span>    |<span data-ttu-id="cb266-127">Detecteert wanneer een gebruiker een item probeert te kopiëren naar een netwerkshare of een netwerkstation</span><span class="sxs-lookup"><span data-stu-id="cb266-127">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="cb266-128">controleerbaar en beperkbaar</span><span class="sxs-lookup"><span data-stu-id="cb266-128">auditable and restrictable</span></span>|
|<span data-ttu-id="cb266-129">een document afdrukken</span><span class="sxs-lookup"><span data-stu-id="cb266-129">print a document</span></span>    |<span data-ttu-id="cb266-130">Detecteert wanneer een gebruiker een beveiligd item probeert af te drukken op een lokale printer of netwerkprinter.</span><span class="sxs-lookup"><span data-stu-id="cb266-130">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="cb266-131">controleerbaar en beperkbaar</span><span class="sxs-lookup"><span data-stu-id="cb266-131">auditable and restrictable</span></span>         |
|<span data-ttu-id="cb266-132">kopiëren naar een externe sessie</span><span class="sxs-lookup"><span data-stu-id="cb266-132">copy to a remote session</span></span>|<span data-ttu-id="cb266-133">Detecteert wanneer een gebruiker een item naar een sessie op het extern bureaublad probeert te kopiëren</span><span class="sxs-lookup"><span data-stu-id="cb266-133">Detects when a user attempts to copy an item to a remote desktop session</span></span> |  <span data-ttu-id="cb266-134">controleerbaar en beperkbaar</span><span class="sxs-lookup"><span data-stu-id="cb266-134">auditable and restrictable</span></span>|
|<span data-ttu-id="cb266-135">kopiëren naar een Bluetooth-apparaat</span><span class="sxs-lookup"><span data-stu-id="cb266-135">copy to a Bluetooth device</span></span>|<span data-ttu-id="cb266-136">Detecteert wanneer een gebruiker een item naar een niet-toegestane Bluetooth-app probeert te kopiëren (zoals gedefinieerd in de lijst met niet-toegestane Bluetooth-apps in de instellingen voor DLP Endpoint).</span><span class="sxs-lookup"><span data-stu-id="cb266-136">Detects when a user attempts to copy an item to an unallowed Bluetooth app (as defined in the list of unallowed Bluetooth aps in Endpoint DLP settings).</span></span>| <span data-ttu-id="cb266-137">controleerbaar en beperkbaar</span><span class="sxs-lookup"><span data-stu-id="cb266-137">auditable and restrictable</span></span>|
|<span data-ttu-id="cb266-138">een item aanmaken</span><span class="sxs-lookup"><span data-stu-id="cb266-138">create an item</span></span>|<span data-ttu-id="cb266-139">Detecteert wanneer een gebruiker een item maakt</span><span class="sxs-lookup"><span data-stu-id="cb266-139">Detects when a user creates an item</span></span>| <span data-ttu-id="cb266-140">controleerbaar</span><span class="sxs-lookup"><span data-stu-id="cb266-140">auditable</span></span>|
|<span data-ttu-id="cb266-141">een item hernoemen</span><span class="sxs-lookup"><span data-stu-id="cb266-141">rename an item</span></span>|<span data-ttu-id="cb266-142">Detecteert wanneer een gebruiker de naam van een item wijzigt</span><span class="sxs-lookup"><span data-stu-id="cb266-142">Detects when a user renames an item</span></span>| <span data-ttu-id="cb266-143">controleerbaar</span><span class="sxs-lookup"><span data-stu-id="cb266-143">auditable</span></span>|

 ## <a name="monitored-files"></a><span data-ttu-id="cb266-144">Bewaakte bestanden</span><span class="sxs-lookup"><span data-stu-id="cb266-144">Monitored files</span></span>

<span data-ttu-id="cb266-145">Endpoint DLP ondersteunt de controle van deze bestandstypen:</span><span class="sxs-lookup"><span data-stu-id="cb266-145">Endpoint DLP supports monitoring of these file types:</span></span>

- <span data-ttu-id="cb266-146">Word-bestanden</span><span class="sxs-lookup"><span data-stu-id="cb266-146">Word files</span></span>
- <span data-ttu-id="cb266-147">PowerPoint-bestanden</span><span class="sxs-lookup"><span data-stu-id="cb266-147">PowerPoint files</span></span>
- <span data-ttu-id="cb266-148">Excel-bestanden</span><span class="sxs-lookup"><span data-stu-id="cb266-148">Excel files</span></span>
- <span data-ttu-id="cb266-149">PDF-bestanden</span><span class="sxs-lookup"><span data-stu-id="cb266-149">PDF files</span></span>
- <span data-ttu-id="cb266-150">.csv-bestand</span><span class="sxs-lookup"><span data-stu-id="cb266-150">.csv files</span></span>
- <span data-ttu-id="cb266-151">.tsv-bestanden</span><span class="sxs-lookup"><span data-stu-id="cb266-151">.tsv files</span></span>
- <span data-ttu-id="cb266-152">.txt-bestanden</span><span class="sxs-lookup"><span data-stu-id="cb266-152">.txt files</span></span>
- <span data-ttu-id="cb266-153">.rtf-bestanden</span><span class="sxs-lookup"><span data-stu-id="cb266-153">.rtf files</span></span>
- <span data-ttu-id="cb266-154">.c-bestanden</span><span class="sxs-lookup"><span data-stu-id="cb266-154">.c files</span></span>
- <span data-ttu-id="cb266-155">.class-bestanden</span><span class="sxs-lookup"><span data-stu-id="cb266-155">.class files</span></span>
- <span data-ttu-id="cb266-156">.cpp-bestanden</span><span class="sxs-lookup"><span data-stu-id="cb266-156">.cpp files</span></span>
- <span data-ttu-id="cb266-157">.cs-bestanden</span><span class="sxs-lookup"><span data-stu-id="cb266-157">.cs files</span></span>
- <span data-ttu-id="cb266-158">.h-bestanden</span><span class="sxs-lookup"><span data-stu-id="cb266-158">.h files</span></span>
- <span data-ttu-id="cb266-159">.java-bestanden</span><span class="sxs-lookup"><span data-stu-id="cb266-159">.java files</span></span>
 
<span data-ttu-id="cb266-160">Standaard worden de activiteiten voor deze bestandstypen door Endpoint DLP gecontroleerd, zelfs als er geen overeenkomstig beleid is.</span><span class="sxs-lookup"><span data-stu-id="cb266-160">By default, endpoint DLP audits the activities for these file types, even if there isn't a policy match.</span></span> <span data-ttu-id="cb266-161">Als u enkel de gegevens wilt controleren waarvoor overeenkomstig beleid bestaat, kunt u **Bestandsactiviteit altijd controleren voor apparaten** uitschakelen in de globale instellingen voor Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="cb266-161">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span> <span data-ttu-id="cb266-162">Als deze instelling is ingeschakeld, worden activiteiten met alle Word-, PowerPoint-, Excel-, PDF- en CSV-bestanden altijd gecontroleerd, zelfs als het apparaat niet aan een beleid is onderworpen.</span><span class="sxs-lookup"><span data-stu-id="cb266-162">If this setting is on, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited even if the device is not targeted by any policy.</span></span>

<span data-ttu-id="cb266-163">Endpoint DLP bewaakt activiteit op basis van MIME-type, zodat er zelfs activiteiten worden vastgelegd als de bestandsextensie wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="cb266-163">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span> 

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="cb266-164">Wat is er nieuw in Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="cb266-164">What's different in Endpoint DLP</span></span>

<span data-ttu-id="cb266-165">Er zijn enkele extra concepten waar u rekening mee moet houden voordat u Endpoint DLP in gebruik gaat nemen.</span><span class="sxs-lookup"><span data-stu-id="cb266-165">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="cb266-166">Apparaatbeheer inschakelen</span><span class="sxs-lookup"><span data-stu-id="cb266-166">Enabling Device management</span></span>

<span data-ttu-id="cb266-167">Apparaatbeheer is de functie waarmee telemetrieverzamelingen van apparaten kunnen worden gebruikt en die beschikbaar wordt in nalevingsoplossingen van Microsoft 365, zoals Endpoint DLP en [Risicobeheer voor Insiders](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="cb266-167">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="cb266-168">U moet alle apparaten die u wilt gebruiken als locaties in het DLP-beleid onboarden.</span><span class="sxs-lookup"><span data-stu-id="cb266-168">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cb266-169">![apparaatbeheer inschakelen](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="cb266-169">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="cb266-170">Onboarding en offboarding worden verwerkt via scripts die u downloadt in het Apparaatbeheercentrum.</span><span class="sxs-lookup"><span data-stu-id="cb266-170">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="cb266-171">Het centrum heeft aangepaste scripts voor elk van deze implementatiemethoden:</span><span class="sxs-lookup"><span data-stu-id="cb266-171">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="cb266-172">lokaal script (maximaal 10 computers)</span><span class="sxs-lookup"><span data-stu-id="cb266-172">local script (up to 10 machines)</span></span>
- <span data-ttu-id="cb266-173">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="cb266-173">Group policy</span></span>
- <span data-ttu-id="cb266-174">System Center Configuration Manager (versie 1610 of later)</span><span class="sxs-lookup"><span data-stu-id="cb266-174">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="cb266-175">Mobile Device Management/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="cb266-175">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="cb266-176">Scripts voor VDI-onboarding voor niet-permanente computers</span><span class="sxs-lookup"><span data-stu-id="cb266-176">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cb266-177">![pagina voor onboarding van apparaten](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="cb266-177">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="cb266-178">Gebruik de procedures in [Aan de slag met Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) om apparaten te onboarden.</span><span class="sxs-lookup"><span data-stu-id="cb266-178">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="cb266-179">Als u apparaten heeft geïmplementeerd via [Microsoft Defender for Endpoint](/windows/security/threat-protection/), dan worden deze apparaten automatisch weergegeven in de lijst met apparaten.</span><span class="sxs-lookup"><span data-stu-id="cb266-179">If you have onboarded devices through [Microsoft Defender for Endpoint](/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cb266-180">![lijst met beheerde apparaten](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="cb266-180">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="cb266-181">Endpoint DLP-gegevens weergeven</span><span class="sxs-lookup"><span data-stu-id="cb266-181">Viewing Endpoint DLP data</span></span>

<span data-ttu-id="cb266-182">U kunt waarschuwingen weergeven die zijn gerelateerd aan DLP-beleid afgedwongen op eindpuntapparaten. Ga daarvoor naar het [Dashboard DLP-waarschuwingenbeheer](dlp-configure-view-alerts-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cb266-182">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cb266-183">![Waarschuwingsinformatie](../media/Alert-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="cb266-183">![Alert info](../media/Alert-info-1.png)</span></span>

<span data-ttu-id="cb266-184">U kunt ook details van de bijbehorende gebeurtenis met uitgebreide metagegevens in hetzelfde dashboard bekijken</span><span class="sxs-lookup"><span data-stu-id="cb266-184">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cb266-185">![gebeurtenisinformatie](../media/Event-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="cb266-185">![event info](../media/Event-info-1.png)</span></span>

<span data-ttu-id="cb266-186">Zodra een apparaat is geïmplementeerd, wordt informatie over gecontroleerde activiteiten in Activity Explorer overgezet voordat u DLP-beleidsregels met apparaten als locatie configureert en implementeert.</span><span class="sxs-lookup"><span data-stu-id="cb266-186">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cb266-187">![endpoint dlp-gebeurtenissen in activity Explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="cb266-187">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="cb266-188">Endpoint DLP verzamelt uitgebreide informatie over gecontroleerde activiteiten.</span><span class="sxs-lookup"><span data-stu-id="cb266-188">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="cb266-189">Als een bestand bijvoorbeeld is gekopieerd naar een verwisselbaar USB-medium, ziet u deze kenmerken in de activiteitsdetails:</span><span class="sxs-lookup"><span data-stu-id="cb266-189">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="cb266-190">activiteitstype</span><span class="sxs-lookup"><span data-stu-id="cb266-190">activity type</span></span>
- <span data-ttu-id="cb266-191">client-IP</span><span class="sxs-lookup"><span data-stu-id="cb266-191">client IP</span></span>
- <span data-ttu-id="cb266-192">pad naar doelbestand</span><span class="sxs-lookup"><span data-stu-id="cb266-192">target file path</span></span>
- <span data-ttu-id="cb266-193">timestamp gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="cb266-193">happened timestamp</span></span>
- <span data-ttu-id="cb266-194">bestandsnaam</span><span class="sxs-lookup"><span data-stu-id="cb266-194">file name</span></span>
- <span data-ttu-id="cb266-195">gebruiker</span><span class="sxs-lookup"><span data-stu-id="cb266-195">user</span></span>
- <span data-ttu-id="cb266-196">bestandsextensie</span><span class="sxs-lookup"><span data-stu-id="cb266-196">file extension</span></span>
- <span data-ttu-id="cb266-197">bestandsgrootte</span><span class="sxs-lookup"><span data-stu-id="cb266-197">file size</span></span>
- <span data-ttu-id="cb266-198">type vertrouwelijke informatie (indien van toepassing)</span><span class="sxs-lookup"><span data-stu-id="cb266-198">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="cb266-199">sha1-waarde</span><span class="sxs-lookup"><span data-stu-id="cb266-199">sha1 value</span></span>
- <span data-ttu-id="cb266-200">sha256-waarde</span><span class="sxs-lookup"><span data-stu-id="cb266-200">sha256 value</span></span>
- <span data-ttu-id="cb266-201">vorige bestandsnaam</span><span class="sxs-lookup"><span data-stu-id="cb266-201">previous file name</span></span>
- <span data-ttu-id="cb266-202">locatie</span><span class="sxs-lookup"><span data-stu-id="cb266-202">location</span></span>
- <span data-ttu-id="cb266-203">bovenliggend</span><span class="sxs-lookup"><span data-stu-id="cb266-203">parent</span></span>
- <span data-ttu-id="cb266-204">bestandspad</span><span class="sxs-lookup"><span data-stu-id="cb266-204">filepath</span></span>
- <span data-ttu-id="cb266-205">type bronlocatie</span><span class="sxs-lookup"><span data-stu-id="cb266-205">source location type</span></span>
- <span data-ttu-id="cb266-206">platform</span><span class="sxs-lookup"><span data-stu-id="cb266-206">platform</span></span>
- <span data-ttu-id="cb266-207">apparaatnaam</span><span class="sxs-lookup"><span data-stu-id="cb266-207">device name</span></span>
- <span data-ttu-id="cb266-208">type doellocatie</span><span class="sxs-lookup"><span data-stu-id="cb266-208">destination location type</span></span>
- <span data-ttu-id="cb266-209">toepassing die de kopie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="cb266-209">application that performed the copy</span></span>
- <span data-ttu-id="cb266-210">Apparaat-id voor Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="cb266-210">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="cb266-211">fabrikant van verwisselbaar media-apparaat</span><span class="sxs-lookup"><span data-stu-id="cb266-211">removable media device manufacturer</span></span>
- <span data-ttu-id="cb266-212">model van verwisselbaar media-apparaat</span><span class="sxs-lookup"><span data-stu-id="cb266-212">removable media device model</span></span>
- <span data-ttu-id="cb266-213">serienummer van verwisselbaar media-apparaat</span><span class="sxs-lookup"><span data-stu-id="cb266-213">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cb266-214">![kopiëren naar usb-activiteitskenmerken](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="cb266-214">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="cb266-215">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="cb266-215">Next steps</span></span>

<span data-ttu-id="cb266-216">Nu u meer weet over Endpoint DLP, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="cb266-216">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="cb266-217">Aan de slag met preventie van gegevensverlies in Microsoft Endpoint </span><span class="sxs-lookup"><span data-stu-id="cb266-217">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="cb266-218">Eindpunt-DLP gebruiken</span><span class="sxs-lookup"><span data-stu-id="cb266-218">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="cb266-219">Zie ook</span><span class="sxs-lookup"><span data-stu-id="cb266-219">See also</span></span>

- [<span data-ttu-id="cb266-220">Aan de slag met Microsoft Eindpunt-DLP</span><span class="sxs-lookup"><span data-stu-id="cb266-220">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="cb266-221">Eindpunt-DLP gebruiken</span><span class="sxs-lookup"><span data-stu-id="cb266-221">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="cb266-222">Meer informatie over preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="cb266-222">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="cb266-223">Een DLP-beleid maken, testen en afstemmen</span><span class="sxs-lookup"><span data-stu-id="cb266-223">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="cb266-224">Aan de slag met Activity Explorer</span><span class="sxs-lookup"><span data-stu-id="cb266-224">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="cb266-225">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="cb266-225">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="cb266-226">Insider Risk-beheer</span><span class="sxs-lookup"><span data-stu-id="cb266-226">Insider Risk management</span></span>](insider-risk-management.md)