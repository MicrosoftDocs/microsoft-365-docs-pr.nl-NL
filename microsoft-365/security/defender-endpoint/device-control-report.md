---
title: De gegevens van uw organisatie beveiligen met apparaatbesturingselement
description: Controleer de gegevensbeveiliging van uw organisatie via apparaatbeheerrapporten.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.author: dansimp
author: dansimp
ms.reviewer: dansimp
ms.topic: article
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: ee8e7be20076bde41867981008e53a70c134e47e
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893725"
---
# <a name="protect-your-organizations-data-with-device-control"></a><span data-ttu-id="ab261-103">De gegevens van uw organisatie beveiligen met apparaatbesturingselement</span><span class="sxs-lookup"><span data-stu-id="ab261-103">Protect your organization’s data with device control</span></span>

<span data-ttu-id="ab261-104">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2069559)</span><span class="sxs-lookup"><span data-stu-id="ab261-104">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2069559)</span></span>

<span data-ttu-id="ab261-105">Microsoft Defender voor Endpoint-apparaatbesturingselement beschermt tegen gegevensverlies door mediagebruik door apparaten in uw organisatie te controleren en te beheren, zoals het gebruik van verwisselbare opslagapparaten en USB-stations.</span><span class="sxs-lookup"><span data-stu-id="ab261-105">Microsoft Defender for Endpoint device control protects against data loss, by monitoring and controlling media use by devices in your organization, such as the use of removable storage devices and USB drives.</span></span>

<span data-ttu-id="ab261-106">Met het apparaatbesturingselementrapport kunt u gebeurtenissen bekijken die betrekking hebben op mediagebruik, zoals:</span><span class="sxs-lookup"><span data-stu-id="ab261-106">With the device control report, you can view events that relate to media usage, such as:</span></span>

- <span data-ttu-id="ab261-107">**Auditgebeurtenissen:** Geeft het aantal auditgebeurtenissen weer dat optreedt wanneer externe media zijn verbonden.</span><span class="sxs-lookup"><span data-stu-id="ab261-107">**Audit events:** Shows the number of audit events that occur when external media is connected.</span></span>
- <span data-ttu-id="ab261-108">**Beleidsgebeurtenissen:** Toont het aantal beleidsgebeurtenissen dat optreedt wanneer een apparaatbesturingselementbeleid wordt geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="ab261-108">**Policy events:** Shows the number of policy events that occur when a device control policy is triggered.</span></span>

> [!NOTE]
> <span data-ttu-id="ab261-109">De auditgebeurtenis voor het bijhouden van mediagebruik is standaard ingeschakeld voor apparaten die zijn ingeschakeld bij Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="ab261-109">The audit event to track media usage is enabled by default for devices onboarded to Microsoft Defender for Endpoint.</span></span>

## <a name="understanding-the-audit-events"></a><span data-ttu-id="ab261-110">De auditgebeurtenissen begrijpen</span><span class="sxs-lookup"><span data-stu-id="ab261-110">Understanding the audit events</span></span>

<span data-ttu-id="ab261-111">De auditgebeurtenissen zijn:</span><span class="sxs-lookup"><span data-stu-id="ab261-111">The audit events include:</span></span>

- <span data-ttu-id="ab261-112">**USB-station mount and unmount:** Auditgebeurtenissen die worden gegenereerd wanneer een USB-station is bevestigd of losgekoppeld.</span><span class="sxs-lookup"><span data-stu-id="ab261-112">**USB drive mount and unmount:** Audit events that are generated when a USB drive is mounted or unmounted.</span></span>
- <span data-ttu-id="ab261-113">**PnP:** Auditgebeurtenissen voor het aansluiten en afspelen worden gegenereerd wanneer verwisselbare opslag, een printer of Bluetooth-media is verbonden.</span><span class="sxs-lookup"><span data-stu-id="ab261-113">**PnP:** Plug and Play audit events are generated when removable storage, a printer, or Bluetooth media is connected.</span></span>

## <a name="monitor-device-control-security"></a><span data-ttu-id="ab261-114">Beveiliging van apparaatbesturingselementen controleren</span><span class="sxs-lookup"><span data-stu-id="ab261-114">Monitor device control security</span></span>

<span data-ttu-id="ab261-115">Apparaatbesturingselement in Microsoft Defender voor Eindpunt biedt beveiligingsbeheerders hulpmiddelen waarmee ze de beveiliging van apparaatbeheer van hun organisatie kunnen bijhouden via rapporten.</span><span class="sxs-lookup"><span data-stu-id="ab261-115">Device control in Microsoft Defender for Endpoint empowers security administrators with tools that enable them to track their organization’s device control security through reports.</span></span> <span data-ttu-id="ab261-116">U kunt het apparaatbesturingselementrapport vinden in het Microsoft 365-beveiligingscentrum door naar **Rapporten > Apparaatbeveiliging te gaan.**</span><span class="sxs-lookup"><span data-stu-id="ab261-116">You can find the device control report in the Microsoft 365 security center by going to **Reports > Device protection**.</span></span>

<span data-ttu-id="ab261-117">De apparaatbeveiligingskaart op het dashboard **Rapporten** toont het aantal auditgebeurtenissen dat per mediatype is gegenereerd, in de afgelopen 180 dagen.</span><span class="sxs-lookup"><span data-stu-id="ab261-117">The Device protection card on the **Reports** dashboard shows the number of audit events generated by media type, over the last 180 days.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ab261-118">![DeviceControlReportCard](images/devicecontrolcard.png)</span><span class="sxs-lookup"><span data-stu-id="ab261-118">![DeviceControlReportCard](images/devicecontrolcard.png)</span></span>

<span data-ttu-id="ab261-119">De **knop Details weergeven** toont meer gegevens over mediagebruik op de **rapportpagina van het apparaatbesturingselement.**</span><span class="sxs-lookup"><span data-stu-id="ab261-119">The **View details** button shows more media usage data in the **device control report** page.</span></span>

<span data-ttu-id="ab261-120">De pagina bevat een dashboard met een samengevoegd aantal gebeurtenissen per type en een lijst met gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="ab261-120">The page provides a dashboard with aggregated number of events per type and a list of events.</span></span> <span data-ttu-id="ab261-121">Beheerders kunnen filteren op tijdbereik, naam van mediaklasse en apparaat-id.</span><span class="sxs-lookup"><span data-stu-id="ab261-121">Administrators can filter on time range, media class name, and device ID.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ab261-122">![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)</span><span class="sxs-lookup"><span data-stu-id="ab261-122">![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)</span></span>

<span data-ttu-id="ab261-123">Wanneer u een gebeurtenis selecteert, wordt er een flyout weergegeven met meer informatie:</span><span class="sxs-lookup"><span data-stu-id="ab261-123">When you select an event, a flyout appears that shows you more information:</span></span>

- <span data-ttu-id="ab261-124">**Algemene details:** Datum, actiemodus en het beleid van deze gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="ab261-124">**General details:** Date, Action mode, and the policy of this event.</span></span>
- <span data-ttu-id="ab261-125">**Media-informatie:** Mediagegevens omvatten Medianaam, Klasnaam, Class GUID, Apparaat-id, Leverancier-id, Volume, Serienummer en Bustype.</span><span class="sxs-lookup"><span data-stu-id="ab261-125">**Media information:** Media information includes Media name, Class name, Class GUID, Device ID, Vendor ID, Volume, Serial number, and Bus type.</span></span>
- <span data-ttu-id="ab261-126">**Locatiegegevens:** Apparaatnaam en MDATP-apparaat-id.</span><span class="sxs-lookup"><span data-stu-id="ab261-126">**Location details:** Device name and MDATP device ID.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ab261-127">![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)</span><span class="sxs-lookup"><span data-stu-id="ab261-127">![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)</span></span>

<span data-ttu-id="ab261-128">Als u realtimeactiviteiten voor deze media in de hele organisatie wilt zien, selecteert u **de knop Geavanceerd zoeken** openen.</span><span class="sxs-lookup"><span data-stu-id="ab261-128">To see real-time activity for this media across the organization, select the **Open Advanced hunting** button.</span></span> <span data-ttu-id="ab261-129">Dit omvat een ingesloten, vooraf gedefinieerde query.</span><span class="sxs-lookup"><span data-stu-id="ab261-129">This includes an embedded, pre-defined query.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ab261-130">![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)</span><span class="sxs-lookup"><span data-stu-id="ab261-130">![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)</span></span>

<span data-ttu-id="ab261-131">Als u de beveiliging van het apparaat wilt zien, selecteert u de **knop Apparaatpagina** openen in de flyout.</span><span class="sxs-lookup"><span data-stu-id="ab261-131">To see the security of the device, select the **Open device page** button on the flyout.</span></span> <span data-ttu-id="ab261-132">Met deze knop wordt de pagina apparaatentiteit geopend.</span><span class="sxs-lookup"><span data-stu-id="ab261-132">This button opens the device entity page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ab261-133">![DeviceEntityPage](images/Devicesecuritypage.png)</span><span class="sxs-lookup"><span data-stu-id="ab261-133">![DeviceEntityPage](images/Devicesecuritypage.png)</span></span>

## <a name="reporting-delays"></a><span data-ttu-id="ab261-134">Vertragingen melden</span><span class="sxs-lookup"><span data-stu-id="ab261-134">Reporting delays</span></span>

<span data-ttu-id="ab261-135">Het apparaatbesturingselementrapport kan een vertraging van 12 uur hebben vanaf het moment dat een mediaverbinding plaatsvindt tot het moment dat de gebeurtenis wordt weergegeven in de kaart of in de lijst met domeinen.</span><span class="sxs-lookup"><span data-stu-id="ab261-135">The device control report can have a 12-hour delay from the time a media connection occurs to the time the event is reflected in the card or in the domain list.</span></span>
