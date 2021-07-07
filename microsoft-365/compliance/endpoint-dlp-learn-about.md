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
ms.openlocfilehash: c97368dd48515dc787dbac66aa93844889efbdbc
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314414"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="b6be2-104">Meer informatie over Microsoft 365 Eindpunt-DLP</span><span class="sxs-lookup"><span data-stu-id="b6be2-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="b6be2-105">U kunt preventie van gegevensverlies van Microsoft 365 (DLP) gebruiken om te controleren welke acties worden ondernomen op items die u vertrouwelijk vindt en om te voorkomen dat deze items per ongeluk worden gedeeld.</span><span class="sxs-lookup"><span data-stu-id="b6be2-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="b6be2-106">Zie voor meer informatie over DLP [Meer informatie over preventie van gegevensverlies](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="b6be2-106">For more information on DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="b6be2-107">**Preventie van gegevensverlies voor eindpunten)** (Eindpunt-DLP) is een uitbreiding voor de activiteitencontrole en beveiligingsmogelijkheden van DLP voor vertrouwelijke items op Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="b6be2-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="b6be2-108">Zodra apparaten zijn geregistreerd bij de Microsoft 365-complianceoplossingen, wordt de informatie over wat gebruikers met gevoelige items doen, zichtbaar in [Activiteitenverkenner](data-classification-activity-explorer.md) en kunt u beschermende maatregelen voor deze items afdwingen via [DLP-beleid](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="b6be2-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

> [!TIP]
> <span data-ttu-id="b6be2-109">Als u op zoek bent naar apparaatbesturing voor verwisselbare opslag, raadpleegt u [Microsoft Defender voor Eindpuntapparaatbesturing Removable Storage Access Control](../security/defender-endpoint/device-control-removable-storage-access-control.md#microsoft-defender-for-endpoint-device-control-removable-storage-access-control).</span><span class="sxs-lookup"><span data-stu-id="b6be2-109">If you are looking for device control for removable storage, see [Microsoft Defender for Endpoint Device Control Removable Storage Access Control](../security/defender-endpoint/device-control-removable-storage-access-control.md#microsoft-defender-for-endpoint-device-control-removable-storage-access-control).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="b6be2-110">EIndpuntactiviteiten die u kunt controleren en waarvoor u maatregelen kunt nemen</span><span class="sxs-lookup"><span data-stu-id="b6be2-110">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="b6be2-111">Met Microsoft Endpoint DLP kunt u de typen activiteiten die gebruikers uitvoeren op vertrouwelijke items, controleren en beheren op apparaten met Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b6be2-111">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>

|<span data-ttu-id="b6be2-112">Activiteit</span><span class="sxs-lookup"><span data-stu-id="b6be2-112">Activity</span></span> |<span data-ttu-id="b6be2-113">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="b6be2-113">Description</span></span>  | <span data-ttu-id="b6be2-114">Controleerbaar/beperkbaar</span><span class="sxs-lookup"><span data-stu-id="b6be2-114">Auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="b6be2-115">Naar cloudservice uploaden of openen via niet-toegestane browsers</span><span class="sxs-lookup"><span data-stu-id="b6be2-115">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="b6be2-116">Hiermee wordt gedetecteerd wanneer een gebruiker probeert om een item te uploaden naar een beperkt servicedomein of een item via een browser probeert te openen.</span><span class="sxs-lookup"><span data-stu-id="b6be2-116">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="b6be2-117">Als ze een browser gebruiken die in DLP is opgenomen als een niet-toegestaan browser, wordt de uploadactiviteit geblokkeerd en wordt de gebruiker omgeleid naar Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="b6be2-117">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="b6be2-118">Edge Chromium staat vervolgens het uploaden of de toegang toe of blokkeert het op basis van de configuratie van het DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="b6be2-118">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="b6be2-119">controleerbaar en beperkbaar</span><span class="sxs-lookup"><span data-stu-id="b6be2-119">auditable and restrictable</span></span>|
|<span data-ttu-id="b6be2-120">kopiëren naar andere app</span><span class="sxs-lookup"><span data-stu-id="b6be2-120">copy to other app</span></span>    |<span data-ttu-id="b6be2-121">Hiermee wordt gedetecteerd wanneer een gebruiker informatie uit een beveiligd item probeert te kopiëren en vervolgens te plakken in een andere app, of in een ander proces of item.</span><span class="sxs-lookup"><span data-stu-id="b6be2-121">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="b6be2-122">Het kopiëren en plakken van gegevens binnen dezelfde app, hetzelfde proces of item wordt niet gedetecteerd door deze activiteit.</span><span class="sxs-lookup"><span data-stu-id="b6be2-122">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="b6be2-123">controleerbaar en beperkbaar</span><span class="sxs-lookup"><span data-stu-id="b6be2-123">auditable and restrictable</span></span>|
|<span data-ttu-id="b6be2-124">kopiëren naar verwisselbare USB-media</span><span class="sxs-lookup"><span data-stu-id="b6be2-124">copy to USB removable media</span></span> |<span data-ttu-id="b6be2-125">Detecteert wanneer een gebruiker een item of gegevens probeert te kopiëren naar een verwisselbaar medium of USB-apparaat.</span><span class="sxs-lookup"><span data-stu-id="b6be2-125">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="b6be2-126">controleerbaar en beperkbaar</span><span class="sxs-lookup"><span data-stu-id="b6be2-126">auditable and restrictable</span></span>|
|<span data-ttu-id="b6be2-127">kopiëren naar een netwerkshare</span><span class="sxs-lookup"><span data-stu-id="b6be2-127">copy to a network share</span></span>    |<span data-ttu-id="b6be2-128">Detecteert wanneer een gebruiker een item probeert te kopiëren naar een netwerkshare of een netwerkstation</span><span class="sxs-lookup"><span data-stu-id="b6be2-128">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="b6be2-129">controleerbaar en beperkbaar</span><span class="sxs-lookup"><span data-stu-id="b6be2-129">auditable and restrictable</span></span>|
|<span data-ttu-id="b6be2-130">een document afdrukken</span><span class="sxs-lookup"><span data-stu-id="b6be2-130">print a document</span></span>    |<span data-ttu-id="b6be2-131">Detecteert wanneer een gebruiker een beveiligd item probeert af te drukken op een lokale printer of netwerkprinter.</span><span class="sxs-lookup"><span data-stu-id="b6be2-131">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="b6be2-132">controleerbaar en beperkbaar</span><span class="sxs-lookup"><span data-stu-id="b6be2-132">auditable and restrictable</span></span>         |
|<span data-ttu-id="b6be2-133">kopiëren naar een externe sessie</span><span class="sxs-lookup"><span data-stu-id="b6be2-133">copy to a remote session</span></span>|<span data-ttu-id="b6be2-134">Detecteert wanneer een gebruiker een item naar een sessie op het extern bureaublad probeert te kopiëren</span><span class="sxs-lookup"><span data-stu-id="b6be2-134">Detects when a user attempts to copy an item to a remote desktop session</span></span> |  <span data-ttu-id="b6be2-135">controleerbaar en beperkbaar</span><span class="sxs-lookup"><span data-stu-id="b6be2-135">auditable and restrictable</span></span>|
|<span data-ttu-id="b6be2-136">kopiëren naar een Bluetooth-apparaat</span><span class="sxs-lookup"><span data-stu-id="b6be2-136">copy to a Bluetooth device</span></span>|<span data-ttu-id="b6be2-137">Detecteert wanneer een gebruiker een item naar een niet-toegestane Bluetooth-app probeert te kopiëren (zoals gedefinieerd in de lijst met niet-toegestane Bluetooth-apps in de instellingen voor DLP Endpoint).</span><span class="sxs-lookup"><span data-stu-id="b6be2-137">Detects when a user attempts to copy an item to an unallowed Bluetooth app (as defined in the list of unallowed Bluetooth aps in Endpoint DLP settings).</span></span>| <span data-ttu-id="b6be2-138">controleerbaar en beperkbaar</span><span class="sxs-lookup"><span data-stu-id="b6be2-138">auditable and restrictable</span></span>|
|<span data-ttu-id="b6be2-139">een item aanmaken</span><span class="sxs-lookup"><span data-stu-id="b6be2-139">create an item</span></span>|<span data-ttu-id="b6be2-140">Detecteert wanneer een gebruiker een item maakt</span><span class="sxs-lookup"><span data-stu-id="b6be2-140">Detects when a user creates an item</span></span>| <span data-ttu-id="b6be2-141">controleerbaar</span><span class="sxs-lookup"><span data-stu-id="b6be2-141">auditable</span></span>|
|<span data-ttu-id="b6be2-142">een item hernoemen</span><span class="sxs-lookup"><span data-stu-id="b6be2-142">rename an item</span></span>|<span data-ttu-id="b6be2-143">Detecteert wanneer een gebruiker de naam van een item wijzigt</span><span class="sxs-lookup"><span data-stu-id="b6be2-143">Detects when a user renames an item</span></span>| <span data-ttu-id="b6be2-144">controleerbaar</span><span class="sxs-lookup"><span data-stu-id="b6be2-144">auditable</span></span>|

## <a name="monitored-files"></a><span data-ttu-id="b6be2-145">Bewaakte bestanden</span><span class="sxs-lookup"><span data-stu-id="b6be2-145">Monitored files</span></span>

<span data-ttu-id="b6be2-146">Endpoint DLP ondersteunt de controle van deze bestandstypen:</span><span class="sxs-lookup"><span data-stu-id="b6be2-146">Endpoint DLP supports monitoring of these file types:</span></span>

- <span data-ttu-id="b6be2-147">Word-bestanden</span><span class="sxs-lookup"><span data-stu-id="b6be2-147">Word files</span></span>
- <span data-ttu-id="b6be2-148">PowerPoint-bestanden</span><span class="sxs-lookup"><span data-stu-id="b6be2-148">PowerPoint files</span></span>
- <span data-ttu-id="b6be2-149">Excel-bestanden</span><span class="sxs-lookup"><span data-stu-id="b6be2-149">Excel files</span></span>
- <span data-ttu-id="b6be2-150">PDF-bestanden</span><span class="sxs-lookup"><span data-stu-id="b6be2-150">PDF files</span></span>
- <span data-ttu-id="b6be2-151">.csv-bestand</span><span class="sxs-lookup"><span data-stu-id="b6be2-151">.csv files</span></span>
- <span data-ttu-id="b6be2-152">.tsv-bestanden</span><span class="sxs-lookup"><span data-stu-id="b6be2-152">.tsv files</span></span>
- <span data-ttu-id="b6be2-153">.txt-bestanden</span><span class="sxs-lookup"><span data-stu-id="b6be2-153">.txt files</span></span>
- <span data-ttu-id="b6be2-154">.rtf-bestanden</span><span class="sxs-lookup"><span data-stu-id="b6be2-154">.rtf files</span></span>
- <span data-ttu-id="b6be2-155">.c-bestanden</span><span class="sxs-lookup"><span data-stu-id="b6be2-155">.c files</span></span>
- <span data-ttu-id="b6be2-156">.class-bestanden</span><span class="sxs-lookup"><span data-stu-id="b6be2-156">.class files</span></span>
- <span data-ttu-id="b6be2-157">.cpp-bestanden</span><span class="sxs-lookup"><span data-stu-id="b6be2-157">.cpp files</span></span>
- <span data-ttu-id="b6be2-158">.cs-bestanden</span><span class="sxs-lookup"><span data-stu-id="b6be2-158">.cs files</span></span>
- <span data-ttu-id="b6be2-159">.h-bestanden</span><span class="sxs-lookup"><span data-stu-id="b6be2-159">.h files</span></span>
- <span data-ttu-id="b6be2-160">.java-bestanden</span><span class="sxs-lookup"><span data-stu-id="b6be2-160">.java files</span></span>

<span data-ttu-id="b6be2-161">Standaard worden de activiteiten voor deze bestandstypen door Endpoint DLP gecontroleerd, zelfs als er geen overeenkomstig beleid is.</span><span class="sxs-lookup"><span data-stu-id="b6be2-161">By default, endpoint DLP audits the activities for these file types, even if there isn't a policy match.</span></span> <span data-ttu-id="b6be2-162">Als u enkel de gegevens wilt controleren waarvoor overeenkomstig beleid bestaat, kunt u **Bestandsactiviteit altijd controleren voor apparaten** uitschakelen in de globale instellingen voor Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="b6be2-162">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span> <span data-ttu-id="b6be2-163">Als deze instelling is ingeschakeld, worden activiteiten met alle Word-, PowerPoint-, Excel-, PDF- en CSV-bestanden altijd gecontroleerd, zelfs als het apparaat niet aan een beleid is onderworpen.</span><span class="sxs-lookup"><span data-stu-id="b6be2-163">If this setting is on, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited even if the device is not targeted by any policy.</span></span>

<span data-ttu-id="b6be2-164">Endpoint DLP bewaakt activiteit op basis van MIME-type, zodat er zelfs activiteiten worden vastgelegd als de bestandsextensie wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="b6be2-164">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span>

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="b6be2-165">Wat is er nieuw in Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="b6be2-165">What's different in Endpoint DLP</span></span>

<span data-ttu-id="b6be2-166">Er zijn enkele extra concepten waar u rekening mee moet houden voordat u Endpoint DLP in gebruik gaat nemen.</span><span class="sxs-lookup"><span data-stu-id="b6be2-166">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="b6be2-167">Apparaatbeheer inschakelen</span><span class="sxs-lookup"><span data-stu-id="b6be2-167">Enabling Device management</span></span>

<span data-ttu-id="b6be2-168">Apparaatbeheer is de functie waarmee telemetrieverzamelingen van apparaten kunnen worden gebruikt en die beschikbaar wordt in nalevingsoplossingen van Microsoft 365, zoals Endpoint DLP en [Risicobeheer voor Insiders](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="b6be2-168">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="b6be2-169">U moet alle apparaten die u wilt gebruiken als locaties in het DLP-beleid onboarden.</span><span class="sxs-lookup"><span data-stu-id="b6be2-169">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b6be2-170">![apparaatbeheer inschakelen](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="b6be2-170">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="b6be2-171">Onboarding en offboarding worden verwerkt via scripts die u downloadt in het Apparaatbeheercentrum.</span><span class="sxs-lookup"><span data-stu-id="b6be2-171">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="b6be2-172">Het centrum heeft aangepaste scripts voor elk van deze implementatiemethoden:</span><span class="sxs-lookup"><span data-stu-id="b6be2-172">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="b6be2-173">lokaal script (maximaal 10 computers)</span><span class="sxs-lookup"><span data-stu-id="b6be2-173">local script (up to 10 machines)</span></span>
- <span data-ttu-id="b6be2-174">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="b6be2-174">Group policy</span></span>
- <span data-ttu-id="b6be2-175">System Center Configuration Manager (versie 1610 of later)</span><span class="sxs-lookup"><span data-stu-id="b6be2-175">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="b6be2-176">Mobile Device Management/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b6be2-176">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="b6be2-177">Scripts voor VDI-onboarding voor niet-permanente computers</span><span class="sxs-lookup"><span data-stu-id="b6be2-177">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b6be2-178">![pagina voor onboarding van apparaten](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="b6be2-178">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="b6be2-179">Gebruik de procedures in [Aan de slag met Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) om apparaten te onboarden.</span><span class="sxs-lookup"><span data-stu-id="b6be2-179">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="b6be2-180">Als u apparaten heeft geïmplementeerd via [Microsoft Defender for Endpoint](/windows/security/threat-protection/), dan worden deze apparaten automatisch weergegeven in de lijst met apparaten.</span><span class="sxs-lookup"><span data-stu-id="b6be2-180">If you have onboarded devices through [Microsoft Defender for Endpoint](/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b6be2-181">![lijst met beheerde apparaten](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="b6be2-181">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="b6be2-182">Endpoint DLP-gegevens weergeven</span><span class="sxs-lookup"><span data-stu-id="b6be2-182">Viewing Endpoint DLP data</span></span>

<span data-ttu-id="b6be2-183">U kunt waarschuwingen weergeven die zijn gerelateerd aan DLP-beleid afgedwongen op eindpuntapparaten. Ga daarvoor naar het [Dashboard DLP-waarschuwingenbeheer](dlp-configure-view-alerts-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b6be2-183">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b6be2-184">![Waarschuwingsinformatie](../media/Alert-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="b6be2-184">![Alert info](../media/Alert-info-1.png)</span></span>

<span data-ttu-id="b6be2-185">U kunt ook details van de bijbehorende gebeurtenis met uitgebreide metagegevens in hetzelfde dashboard bekijken</span><span class="sxs-lookup"><span data-stu-id="b6be2-185">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b6be2-186">![gebeurtenisinformatie](../media/Event-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="b6be2-186">![event info](../media/Event-info-1.png)</span></span>

<span data-ttu-id="b6be2-187">Zodra een apparaat is geïmplementeerd, wordt informatie over gecontroleerde activiteiten in Activity Explorer overgezet voordat u DLP-beleidsregels met apparaten als locatie configureert en implementeert.</span><span class="sxs-lookup"><span data-stu-id="b6be2-187">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b6be2-188">![endpoint dlp-gebeurtenissen in activity Explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="b6be2-188">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="b6be2-189">Endpoint DLP verzamelt uitgebreide informatie over gecontroleerde activiteiten.</span><span class="sxs-lookup"><span data-stu-id="b6be2-189">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="b6be2-190">Als een bestand bijvoorbeeld is gekopieerd naar een verwisselbaar USB-medium, ziet u deze kenmerken in de activiteitsdetails:</span><span class="sxs-lookup"><span data-stu-id="b6be2-190">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="b6be2-191">activiteitstype</span><span class="sxs-lookup"><span data-stu-id="b6be2-191">activity type</span></span>
- <span data-ttu-id="b6be2-192">client-IP</span><span class="sxs-lookup"><span data-stu-id="b6be2-192">client IP</span></span>
- <span data-ttu-id="b6be2-193">pad naar doelbestand</span><span class="sxs-lookup"><span data-stu-id="b6be2-193">target file path</span></span>
- <span data-ttu-id="b6be2-194">timestamp gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="b6be2-194">happened timestamp</span></span>
- <span data-ttu-id="b6be2-195">bestandsnaam</span><span class="sxs-lookup"><span data-stu-id="b6be2-195">file name</span></span>
- <span data-ttu-id="b6be2-196">gebruiker</span><span class="sxs-lookup"><span data-stu-id="b6be2-196">user</span></span>
- <span data-ttu-id="b6be2-197">bestandsextensie</span><span class="sxs-lookup"><span data-stu-id="b6be2-197">file extension</span></span>
- <span data-ttu-id="b6be2-198">bestandsgrootte</span><span class="sxs-lookup"><span data-stu-id="b6be2-198">file size</span></span>
- <span data-ttu-id="b6be2-199">type vertrouwelijke informatie (indien van toepassing)</span><span class="sxs-lookup"><span data-stu-id="b6be2-199">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="b6be2-200">sha1-waarde</span><span class="sxs-lookup"><span data-stu-id="b6be2-200">sha1 value</span></span>
- <span data-ttu-id="b6be2-201">sha256-waarde</span><span class="sxs-lookup"><span data-stu-id="b6be2-201">sha256 value</span></span>
- <span data-ttu-id="b6be2-202">vorige bestandsnaam</span><span class="sxs-lookup"><span data-stu-id="b6be2-202">previous file name</span></span>
- <span data-ttu-id="b6be2-203">locatie</span><span class="sxs-lookup"><span data-stu-id="b6be2-203">location</span></span>
- <span data-ttu-id="b6be2-204">bovenliggend</span><span class="sxs-lookup"><span data-stu-id="b6be2-204">parent</span></span>
- <span data-ttu-id="b6be2-205">bestandspad</span><span class="sxs-lookup"><span data-stu-id="b6be2-205">filepath</span></span>
- <span data-ttu-id="b6be2-206">type bronlocatie</span><span class="sxs-lookup"><span data-stu-id="b6be2-206">source location type</span></span>
- <span data-ttu-id="b6be2-207">platform</span><span class="sxs-lookup"><span data-stu-id="b6be2-207">platform</span></span>
- <span data-ttu-id="b6be2-208">apparaatnaam</span><span class="sxs-lookup"><span data-stu-id="b6be2-208">device name</span></span>
- <span data-ttu-id="b6be2-209">type doellocatie</span><span class="sxs-lookup"><span data-stu-id="b6be2-209">destination location type</span></span>
- <span data-ttu-id="b6be2-210">toepassing die de kopie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="b6be2-210">application that performed the copy</span></span>
- <span data-ttu-id="b6be2-211">Apparaat-id voor Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="b6be2-211">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="b6be2-212">fabrikant van verwisselbaar media-apparaat</span><span class="sxs-lookup"><span data-stu-id="b6be2-212">removable media device manufacturer</span></span>
- <span data-ttu-id="b6be2-213">model van verwisselbaar media-apparaat</span><span class="sxs-lookup"><span data-stu-id="b6be2-213">removable media device model</span></span>
- <span data-ttu-id="b6be2-214">serienummer van verwisselbaar media-apparaat</span><span class="sxs-lookup"><span data-stu-id="b6be2-214">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b6be2-215">![kopiëren naar usb-activiteitskenmerken](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="b6be2-215">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="b6be2-216">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="b6be2-216">Next steps</span></span>

<span data-ttu-id="b6be2-217">Nu u meer weet over Endpoint DLP, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="b6be2-217">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1. [<span data-ttu-id="b6be2-218">Aan de slag met Microsoft Eindpunt-DLP</span><span class="sxs-lookup"><span data-stu-id="b6be2-218">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
2. [<span data-ttu-id="b6be2-219">Eindpunt-DLP gebruiken</span><span class="sxs-lookup"><span data-stu-id="b6be2-219">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="b6be2-220">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b6be2-220">See also</span></span>

- [<span data-ttu-id="b6be2-221">Aan de slag met Microsoft Eindpunt-DLP</span><span class="sxs-lookup"><span data-stu-id="b6be2-221">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="b6be2-222">Eindpunt-DLP gebruiken</span><span class="sxs-lookup"><span data-stu-id="b6be2-222">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="b6be2-223">Meer informatie over preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="b6be2-223">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="b6be2-224">Een DLP-beleid maken, testen en afstemmen</span><span class="sxs-lookup"><span data-stu-id="b6be2-224">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="b6be2-225">Aan de slag met de activiteitenverkenner</span><span class="sxs-lookup"><span data-stu-id="b6be2-225">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="b6be2-226">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b6be2-226">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="b6be2-227">Insider Risk-beheer</span><span class="sxs-lookup"><span data-stu-id="b6be2-227">Insider Risk management</span></span>](insider-risk-management.md)
