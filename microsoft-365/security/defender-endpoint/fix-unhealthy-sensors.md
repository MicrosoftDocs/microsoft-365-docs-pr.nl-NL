---
title: Ongezonde sensoren in Microsoft Defender voor eindpunt oplossen
description: Fix device sensors that are reporting as misconfigured or inactive so that the service receives data from the device.
keywords: verkeerd geconfigureerd, inactief, fix sensor, sensor health, no sensor data, sensor data, sensor data, impaired communications, communication
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
ms.date: 11/06/2020
ms.technology: mde
ms.openlocfilehash: c4cdc80170b49a111f476d2d17222c41e2b5c55f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935363"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="6136d-104">Ongezonde sensoren in Microsoft Defender voor eindpunt oplossen</span><span class="sxs-lookup"><span data-stu-id="6136d-104">Fix unhealthy sensors in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6136d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="6136d-105">**Applies to:**</span></span>
- [<span data-ttu-id="6136d-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="6136d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6136d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6136d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="6136d-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="6136d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6136d-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="6136d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-fixsensor-abovefoldlink)

<span data-ttu-id="6136d-110">Apparaten die zijn gecategoriseerd als onjuist geconfigureerd of inactief, kunnen worden gemarkeerd vanwege verschillende oorzaken.</span><span class="sxs-lookup"><span data-stu-id="6136d-110">Devices that are categorized as misconfigured or inactive can be flagged due to varying causes.</span></span> <span data-ttu-id="6136d-111">In deze sectie worden enkele uitleg gegeven over de oorzaak van de mogelijke inactiviteit of onjuiste configuratie van een apparaat.</span><span class="sxs-lookup"><span data-stu-id="6136d-111">This section provides some explanations as to what might have caused a device to be categorized as inactive or misconfigured.</span></span>

## <a name="inactive-devices"></a><span data-ttu-id="6136d-112">Inactieve apparaten</span><span class="sxs-lookup"><span data-stu-id="6136d-112">Inactive devices</span></span>

<span data-ttu-id="6136d-113">Een inactief apparaat wordt niet per se gemarkeerd vanwege een probleem.</span><span class="sxs-lookup"><span data-stu-id="6136d-113">An inactive device is not necessarily flagged due to an issue.</span></span> <span data-ttu-id="6136d-114">De volgende acties op een apparaat kunnen ertoe leiden dat een apparaat wordt gecategoriseerd als inactief:</span><span class="sxs-lookup"><span data-stu-id="6136d-114">The following actions taken on a device can cause a device to be categorized as inactive:</span></span>

### <a name="device-is-not-in-use"></a><span data-ttu-id="6136d-115">Apparaat is niet in gebruik</span><span class="sxs-lookup"><span data-stu-id="6136d-115">Device is not in use</span></span>

<span data-ttu-id="6136d-116">Als het apparaat om welke reden dan ook niet langer dan zeven dagen is gebruikt, blijft het in de portal de status 'Inactief'.</span><span class="sxs-lookup"><span data-stu-id="6136d-116">If the device has not been in use for more than seven days for any reason, it will remain in an ‘Inactive’ status in the portal.</span></span>

### <a name="device-was-reinstalled-or-renamed"></a><span data-ttu-id="6136d-117">Apparaat is opnieuw geïnstalleerd of hernoemd</span><span class="sxs-lookup"><span data-stu-id="6136d-117">Device was reinstalled or renamed</span></span>
<span data-ttu-id="6136d-118">Een opnieuw geïnstalleerd of hernoemd apparaat genereert een nieuwe apparaatentiteit in Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="6136d-118">A reinstalled or renamed device will generate a new device entity in Microsoft Defender Security Center.</span></span> <span data-ttu-id="6136d-119">De vorige apparaatentiteit blijft behouden met de status 'Inactief' in de portal.</span><span class="sxs-lookup"><span data-stu-id="6136d-119">The previous device entity will remain with an ‘Inactive’ status in the portal.</span></span> <span data-ttu-id="6136d-120">Als u een apparaat opnieuw hebt geïnstalleerd en het Defender for Endpoint-pakket hebt geïmplementeerd, zoekt u naar de naam van het nieuwe apparaat om te controleren of het apparaat normaal rapporteert.</span><span class="sxs-lookup"><span data-stu-id="6136d-120">If you reinstalled a device and deployed the Defender for Endpoint package, search for the new device name to verify that the device is reporting normally.</span></span>

### <a name="device-was-offboarded"></a><span data-ttu-id="6136d-121">Apparaat is offboarded</span><span class="sxs-lookup"><span data-stu-id="6136d-121">Device was offboarded</span></span>
<span data-ttu-id="6136d-122">Als het apparaat buiten het bord is geplaatst, wordt het nog steeds weergegeven in de lijst met apparaten.</span><span class="sxs-lookup"><span data-stu-id="6136d-122">If the device was offboarded, it will still appear in devices list.</span></span> <span data-ttu-id="6136d-123">Na zeven dagen moet de status van het apparaat worden gewijzigd in inactief.</span><span class="sxs-lookup"><span data-stu-id="6136d-123">After seven days, the device health state should change to inactive.</span></span>

### <a name="device-is-not-sending-signals"></a><span data-ttu-id="6136d-124">Apparaat verstuurt geen signalen</span><span class="sxs-lookup"><span data-stu-id="6136d-124">Device is not sending signals</span></span>
<span data-ttu-id="6136d-125">Als het apparaat om welke reden dan ook geen signalen meer dan zeven dagen naar een van de Kanalen van Microsoft Defender voor Eindpunt verstuurt, inclusief voorwaarden die onder verkeerd geconfigureerde apparatenclassificatie vallen, kan een apparaat als inactief worden beschouwd.</span><span class="sxs-lookup"><span data-stu-id="6136d-125">If the device is not sending any signals for more than seven days to any of the Microsoft Defender for Endpoint channels for any reason including conditions that fall under misconfigured devices classification, a device can be considered inactive.</span></span> 

<span data-ttu-id="6136d-126">Verwacht u dat een apparaat de status 'Actief' heeft?</span><span class="sxs-lookup"><span data-stu-id="6136d-126">Do you expect a device to be in ‘Active’ status?</span></span> <span data-ttu-id="6136d-127">[Open een ondersteuningsticket](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).</span><span class="sxs-lookup"><span data-stu-id="6136d-127">[Open a support ticket](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).</span></span>

## <a name="misconfigured-devices"></a><span data-ttu-id="6136d-128">Onjuist geconfigureerde apparaten</span><span class="sxs-lookup"><span data-stu-id="6136d-128">Misconfigured devices</span></span>
<span data-ttu-id="6136d-129">Verkeerd geconfigureerde apparaten kunnen verder worden geclassificeerd als:</span><span class="sxs-lookup"><span data-stu-id="6136d-129">Misconfigured devices can further be classified to:</span></span>
- <span data-ttu-id="6136d-130">Communicatie met verminderde werking</span><span class="sxs-lookup"><span data-stu-id="6136d-130">Impaired communications</span></span>
- <span data-ttu-id="6136d-131">Geen sensorgegevens</span><span class="sxs-lookup"><span data-stu-id="6136d-131">No sensor data</span></span>

### <a name="impaired-communications"></a><span data-ttu-id="6136d-132">Communicatie met verminderde werking</span><span class="sxs-lookup"><span data-stu-id="6136d-132">Impaired communications</span></span>
<span data-ttu-id="6136d-133">Deze status geeft aan dat er beperkte communicatie is tussen het apparaat en de service.</span><span class="sxs-lookup"><span data-stu-id="6136d-133">This status indicates that there's limited communication between the device and the service.</span></span>

<span data-ttu-id="6136d-134">De volgende voorgestelde acties kunnen helpen bij het oplossen van problemen met een verkeerd geconfigureerd apparaat met communicatieproblemen:</span><span class="sxs-lookup"><span data-stu-id="6136d-134">The following suggested actions can help fix issues related to a misconfigured device with impaired communications:</span></span>

- [<span data-ttu-id="6136d-135">Controleer of het apparaat een internetverbinding heeft</span><span class="sxs-lookup"><span data-stu-id="6136d-135">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="6136d-136">Voor de Microsoft Defender for Endpoint-sensor moet Microsoft Windows HTTP (WinHTTP) sensorgegevens rapporteren en communiceren met de Microsoft Defender for Endpoint-service.</span><span class="sxs-lookup"><span data-stu-id="6136d-136">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="6136d-137">Clientconnectiviteit verifiëren met URL's van Microsoft Defender voor endpoint-service</span><span class="sxs-lookup"><span data-stu-id="6136d-137">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  <span data-ttu-id="6136d-138">Controleer of de proxyconfiguratie is voltooid, of WinHTTP kan ontdekken en communiceren via de proxyserver in uw omgeving, en of de proxyserver verkeer toestaat naar de URL's van de Microsoft Defender-service voor eindpunten.</span><span class="sxs-lookup"><span data-stu-id="6136d-138">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

<span data-ttu-id="6136d-139">Als u corrigerende acties hebt ondernomen en de apparaatstatus nog steeds niet is geconfigureerd, [opent u een ondersteuningsticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="6136d-139">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

### <a name="no-sensor-data"></a><span data-ttu-id="6136d-140">Geen sensorgegevens</span><span class="sxs-lookup"><span data-stu-id="6136d-140">No sensor data</span></span>
<span data-ttu-id="6136d-141">Een verkeerd geconfigureerd apparaat met de status 'Geen sensorgegevens' heeft communicatie met de service, maar kan slechts gedeeltelijke sensorgegevens rapporteren.</span><span class="sxs-lookup"><span data-stu-id="6136d-141">A misconfigured device with status ‘No sensor data’ has communication with the service but can only report partial sensor data.</span></span>
<span data-ttu-id="6136d-142">Volg theses actions to correct known issues related to a misconfigured device with status 'No sensor data':</span><span class="sxs-lookup"><span data-stu-id="6136d-142">Follow theses actions to correct known issues related to a misconfigured device with status ‘No sensor data’:</span></span>

- [<span data-ttu-id="6136d-143">Controleer of het apparaat een internetverbinding heeft</span><span class="sxs-lookup"><span data-stu-id="6136d-143">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="6136d-144">Voor de Microsoft Defender for Endpoint-sensor moet Microsoft Windows HTTP (WinHTTP) sensorgegevens rapporteren en communiceren met de Microsoft Defender for Endpoint-service.</span><span class="sxs-lookup"><span data-stu-id="6136d-144">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="6136d-145">Clientconnectiviteit verifiëren met URL's van Microsoft Defender voor endpoint-service</span><span class="sxs-lookup"><span data-stu-id="6136d-145">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  <span data-ttu-id="6136d-146">Controleer of de proxyconfiguratie is voltooid, of WinHTTP kan ontdekken en communiceren via de proxyserver in uw omgeving, en of de proxyserver verkeer toestaat naar de URL's van de Microsoft Defender-service voor eindpunten.</span><span class="sxs-lookup"><span data-stu-id="6136d-146">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

- [<span data-ttu-id="6136d-147">Controleren of de diagnostische gegevensservice is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="6136d-147">Ensure the diagnostic data service is enabled</span></span>](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
<span data-ttu-id="6136d-148">Als de apparaten niet correct rapporteren, moet u mogelijk controleren of de diagnostische Windows 10 is ingesteld op automatisch starten en wordt uitgevoerd op het eindpunt.</span><span class="sxs-lookup"><span data-stu-id="6136d-148">If the devices aren't reporting correctly, you might need to check that the Windows 10 diagnostic data service is set to automatically start and is running on the endpoint.</span></span>

- [<span data-ttu-id="6136d-149">Ervoor zorgen dat Microsoft Defender Antivirus niet is uitgeschakeld door beleid</span><span class="sxs-lookup"><span data-stu-id="6136d-149">Ensure that Microsoft Defender Antivirus is not disabled by policy</span></span>](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
<span data-ttu-id="6136d-150">Als op uw apparaten een antimalwareclient van derden wordt uitgevoerd, moet het elmalware-stuurprogramma (Early Launch Antimalware Microsoft Defender Antivirus Early Launch Antimalware( ELAM) van Defender for Endpoint worden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="6136d-150">If your devices are running a third-party antimalware client, the Defender for Endpoint agent needs the Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver to be enabled.</span></span>

<span data-ttu-id="6136d-151">Als u corrigerende acties hebt ondernomen en de apparaatstatus nog steeds niet is geconfigureerd, [opent u een ondersteuningsticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="6136d-151">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

## <a name="see-also"></a><span data-ttu-id="6136d-152">Zie ook</span><span class="sxs-lookup"><span data-stu-id="6136d-152">See also</span></span>
- [<span data-ttu-id="6136d-153">Status van sensor controleren in Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="6136d-153">Check sensor health state in Microsoft Defender for Endpoint</span></span>](check-sensor-status.md)
