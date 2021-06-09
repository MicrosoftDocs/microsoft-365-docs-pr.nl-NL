---
title: De status van de sensor controleren in Microsoft Defender voor eindpunt
description: Controleer de sensortoestand op apparaten om te bepalen welke sensorgegevens onjuist zijn geconfigureerd, niet actief of niet worden gemeld.
keywords: sensor, sensortoestand, verkeerd geconfigureerd, inactief, geen sensorgegevens, sensorgegevens, communicatiesproblemen
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 0361b7956339670d006c9f050274e07d4e979bca
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904162"
---
# <a name="check-sensor-health-state-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="a9f04-104">Status van sensor controleren in Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="a9f04-104">Check sensor health state in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a9f04-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a9f04-105">**Applies to:**</span></span>
- [<span data-ttu-id="a9f04-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="a9f04-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a9f04-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a9f04-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a9f04-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="a9f04-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a9f04-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="a9f04-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-checksensor-abovefoldlink)

<span data-ttu-id="a9f04-110">De **tegel Apparaten met sensorproblemen** vindt u op het dashboard Beveiligingsbewerkingen.</span><span class="sxs-lookup"><span data-stu-id="a9f04-110">The **Devices with sensor issues** tile is found on the Security Operations dashboard.</span></span> <span data-ttu-id="a9f04-111">Deze tegel bevat informatie over de mogelijkheid van het afzonderlijke apparaat om sensorgegevens te verstrekken en te communiceren met de Defender for Endpoint-service.</span><span class="sxs-lookup"><span data-stu-id="a9f04-111">This tile provides information on the individual device’s ability to provide sensor data and communicate with the Defender for Endpoint service.</span></span> <span data-ttu-id="a9f04-112">Het rapport geeft aan hoeveel apparaten aandacht nodig hebben en helpt u problematische apparaten te identificeren en actie te ondernemen om bekende problemen op te lossen.</span><span class="sxs-lookup"><span data-stu-id="a9f04-112">It reports how many devices require attention and helps you identify problematic devices and take action to correct known issues.</span></span>

<span data-ttu-id="a9f04-113">Er zijn twee statusindicatoren op de tegel die informatie bevatten over het aantal apparaten dat niet correct rapporteert aan de service:</span><span class="sxs-lookup"><span data-stu-id="a9f04-113">There are two status indicators on the tile that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="a9f04-114">**Verkeerd geconfigureerd:** deze apparaten kunnen gedeeltelijk sensorgegevens rapporteren aan de Defender voor Eindpunt-service en kunnen configuratiefouten hebben die moeten worden gecorrigeerd.</span><span class="sxs-lookup"><span data-stu-id="a9f04-114">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="a9f04-115">**Inactief:** apparaten die de afgelopen maand meer dan zeven dagen zijn gestopt met rapporteren aan de Defender voor Eindpunt-service.</span><span class="sxs-lookup"><span data-stu-id="a9f04-115">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="a9f04-116">Als u op een van de groepen klikt, gaat u naar de lijst **Apparaten,** gefilterd op basis van uw keuze.</span><span class="sxs-lookup"><span data-stu-id="a9f04-116">Clicking any of the groups directs you to **Devices list**, filtered according to your choice.</span></span>

![Schermafbeelding van apparaten met tegel sensorproblemen](images/atp-devices-with-sensor-issues-tile.png)

<span data-ttu-id="a9f04-118">In **de lijst Apparaten** kunt u de lijst met statusstatussen filteren op de volgende status:</span><span class="sxs-lookup"><span data-stu-id="a9f04-118">On **Devices list**, you can filter the health state list by the following status:</span></span>
- <span data-ttu-id="a9f04-119">**Actief:** apparaten die actief rapporteren aan de Defender for Endpoint-service.</span><span class="sxs-lookup"><span data-stu-id="a9f04-119">**Active** - Devices that are actively reporting to the Defender for Endpoint service.</span></span>
- <span data-ttu-id="a9f04-120">**Verkeerd geconfigureerd:** deze apparaten kunnen gedeeltelijk sensorgegevens rapporteren aan de Service Defender voor eindpunt, maar er zijn configuratiefouten die moeten worden gecorrigeerd.</span><span class="sxs-lookup"><span data-stu-id="a9f04-120">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service but have configuration errors that need to be corrected.</span></span> <span data-ttu-id="a9f04-121">Verkeerd geconfigureerde apparaten kunnen een of een combinatie van de volgende problemen hebben:</span><span class="sxs-lookup"><span data-stu-id="a9f04-121">Misconfigured devices can have either one or a combination of the following issues:</span></span>
  - <span data-ttu-id="a9f04-122">**Geen sensorgegevens:** apparaten zijn gestopt met het verzenden van sensorgegevens.</span><span class="sxs-lookup"><span data-stu-id="a9f04-122">**No sensor data** - Devices has stopped sending sensor data.</span></span> <span data-ttu-id="a9f04-123">Beperkte waarschuwingen kunnen worden geactiveerd vanaf het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a9f04-123">Limited alerts can be triggered from the device.</span></span>
  - <span data-ttu-id="a9f04-124">**Communicatie met een beperking:** de mogelijkheid om te communiceren met een apparaat is beperkt.</span><span class="sxs-lookup"><span data-stu-id="a9f04-124">**Impaired communications** - Ability to communicate with device is impaired.</span></span> <span data-ttu-id="a9f04-125">Het verzenden van bestanden voor uitgebreide analyse, het blokkeren van bestanden, het isoleren van apparaten van het netwerk en andere acties waarvoor communicatie met het apparaat is vereist, werkt mogelijk niet.</span><span class="sxs-lookup"><span data-stu-id="a9f04-125">Sending files for deep analysis, blocking files, isolating device from network and other actions that require communication with the device may not work.</span></span>
- <span data-ttu-id="a9f04-126">**Inactief:** apparaten die niet meer rapporteren aan de Defender voor Endpoint-service.</span><span class="sxs-lookup"><span data-stu-id="a9f04-126">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service.</span></span>

<span data-ttu-id="a9f04-127">U kunt ook de hele lijst in CSV-indeling downloaden met de **functie** Exporteren.</span><span class="sxs-lookup"><span data-stu-id="a9f04-127">You can also download the entire list in CSV format using the **Export** feature.</span></span> <span data-ttu-id="a9f04-128">Zie De lijst Apparaten weergeven en ordenen voor meer informatie over [filters.](machines-view-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a9f04-128">For more information on filters, see [View and organize the Devices list](machines-view-overview.md).</span></span>

>[!NOTE]
><span data-ttu-id="a9f04-129">Exporteert de lijst in CSV-indeling om de ongefilterde gegevens weer te geven.</span><span class="sxs-lookup"><span data-stu-id="a9f04-129">Export the list in CSV format to display the unfiltered data.</span></span> <span data-ttu-id="a9f04-130">Het CSV-bestand bevat alle apparaten in de organisatie, ongeacht de filtering die wordt toegepast in de weergave zelf en kan een aanzienlijke hoeveelheid tijd kosten om te downloaden, afhankelijk van hoe groot uw organisatie is.</span><span class="sxs-lookup"><span data-stu-id="a9f04-130">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself and can take a significant amount of time to download, depending on how large your organization is.</span></span>

![Schermafbeelding van de lijstpagina Apparaten](images/atp-devices-list-page.png)

<span data-ttu-id="a9f04-132">U kunt de apparaatgegevens bekijken wanneer u op een verkeerd geconfigureerd of inactief apparaat klikt.</span><span class="sxs-lookup"><span data-stu-id="a9f04-132">You can view the device details when you click on a misconfigured or inactive device.</span></span>

## <a name="related-topic"></a><span data-ttu-id="a9f04-133">Verwant onderwerp</span><span class="sxs-lookup"><span data-stu-id="a9f04-133">Related topic</span></span>
- [<span data-ttu-id="a9f04-134">Ongezonde sensoren in Defender voor eindpunt oplossen</span><span class="sxs-lookup"><span data-stu-id="a9f04-134">Fix unhealthy sensors in Defender for Endpoint</span></span>](fix-unhealthy-sensors.md)
