---
title: Microsoft Defender voor eindpuntgebeurtenissen streamen naar Azure Event Hubs
description: Meer informatie over het configureren van Microsoft Defender voor Eindpunt om Geavanceerde gebeurtenissen voor jagen te streamen naar uw Event Hub.
keywords: raw data export, streaming API, API, Azure Event Hubs, Azure Storage, Storage Account, Advanced Hunting, raw data sharing
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
ms.custom: api
ms.openlocfilehash: 03b19f3af3c140729db2b5d51bb7ae11d906497b
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771643"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a><span data-ttu-id="fc791-104">Microsoft Defender voor Eindpunt configureren om geavanceerde gebeurtenissen te streamen naar uw Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="fc791-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Azure Event Hubs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fc791-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="fc791-105">**Applies to:**</span></span>

- [<span data-ttu-id="fc791-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="fc791-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="fc791-107">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="fc791-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fc791-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="fc791-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="fc791-109">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="fc791-109">Before you begin</span></span>

1. <span data-ttu-id="fc791-110">Maak een [gebeurtenishub](/azure/event-hubs/) in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="fc791-110">Create an [event hub](/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="fc791-111">Meld u aan bij [uw Azure-tenant](https://ms.portal.azure.com/), ga naar \*\*Abonnementen > Uw abonnement > Resource Providers > Registreren bij \*\*Microsoft.insights\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="fc791-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to \*\*Subscriptions > Your subscription > Resource Providers > Register to \*\*Microsoft.insights\*\*\*\*.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="fc791-112">Onbewerkte gegevensstreaming inschakelen</span><span class="sxs-lookup"><span data-stu-id="fc791-112">Enable raw data streaming</span></span>

1. <span data-ttu-id="fc791-113">Meld u aan bij [de Microsoft Defender-beveiligingscentrum](https://securitycenter.windows.com) als een ***Globale beheerder** _ of _*_Beveiligingsbeheerder_\*\*.</span><span class="sxs-lookup"><span data-stu-id="fc791-113">Log in to the [Microsoft Defender Security Center](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="fc791-114">Ga naar de [pagina Instellingen voor gegevensexport](https://securitycenter.windows.com/interoperability/dataexport) op Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="fc791-114">Go to the [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="fc791-115">Klik op **Instellingen voor gegevensexport toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="fc791-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="fc791-116">Kies een naam voor uw nieuwe instellingen.</span><span class="sxs-lookup"><span data-stu-id="fc791-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="fc791-117">Kies **Gebeurtenissen doorsturen naar Azure Event Hubs**.</span><span class="sxs-lookup"><span data-stu-id="fc791-117">Choose **Forward events to Azure Event Hubs**.</span></span>

6. <span data-ttu-id="fc791-118">Typ de **naam van de gebeurtenishubs** en de **resource-id Event Hubs.**</span><span class="sxs-lookup"><span data-stu-id="fc791-118">Type your **Event Hubs name** and your **Event Hubs resource ID**.</span></span>

   <span data-ttu-id="fc791-119">Als u de resource-id **Event Hubs** wilt downloaden, gaat u naar de naamruimtepagina van Azure Event Hubs op het tabblad Eigenschappen van [Azure](https://ms.portal.azure.com/) > > de tekst onder **Resource-id** kopiëren:</span><span class="sxs-lookup"><span data-stu-id="fc791-119">In order to get your **Event Hubs resource ID**, go to your Azure Event Hubs namespace page on [Azure](https://ms.portal.azure.com/) > properties tab > copy the text under **Resource ID**:</span></span>

   ![Afbeelding van gebeurtenishubresource Id1](images/event-hub-resource-id.png)

7. <span data-ttu-id="fc791-121">Kies de gebeurtenissen die u wilt streamen en klik op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="fc791-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a><span data-ttu-id="fc791-122">Het schema van de gebeurtenissen in Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="fc791-122">The schema of the events in Azure Event Hubs</span></span>

```
{
    "records": [
                    {
                        "time": "<The time WDATP received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <WDATP Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- <span data-ttu-id="fc791-123">Elk bericht van de gebeurtenishub in Azure Event Hubs bevat een lijst met records.</span><span class="sxs-lookup"><span data-stu-id="fc791-123">Each event hub message in Azure Event Hubs contains list of records.</span></span>

- <span data-ttu-id="fc791-124">Elke record bevat de naam van de gebeurtenis, de tijd dat Microsoft Defender voor Eindpunt de gebeurtenis heeft ontvangen, de tenant waar deze deel van uitmaken (u ontvangt alleen gebeurtenissen van uw tenant) en de gebeurtenis in JSON-indeling in een eigenschap genaamd **"** eigenschappen ".</span><span class="sxs-lookup"><span data-stu-id="fc791-124">Each record contains the event name, the time Microsoft Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="fc791-125">Zie Geavanceerd overzicht van jagen voor meer informatie over het schema van Microsoft Defender voor [eindpuntgebeurtenissen.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="fc791-125">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="fc791-126">In Advanced Hunting heeft de **tabel DeviceInfo** een kolom met de naam **MachineGroep** die de groep van het apparaat bevat.</span><span class="sxs-lookup"><span data-stu-id="fc791-126">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="fc791-127">Hier wordt elke gebeurtenis ook gedecoreerd met deze kolom.</span><span class="sxs-lookup"><span data-stu-id="fc791-127">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="fc791-128">Zie [Apparaatgroepen voor](machine-groups.md) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="fc791-128">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="fc791-129">Gegevenstypen toewijzen</span><span class="sxs-lookup"><span data-stu-id="fc791-129">Data types mapping</span></span>

<span data-ttu-id="fc791-130">Ga als volgt te werk om de gegevenstypen voor gebeurteniseigenschappen op te halen:</span><span class="sxs-lookup"><span data-stu-id="fc791-130">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="fc791-131">Meld u aan [bij Microsoft Defender-beveiligingscentrum](https://securitycenter.windows.com) en ga naar de pagina [Geavanceerd zoeken.](https://securitycenter.windows.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="fc791-131">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="fc791-132">Voer de volgende query uit om de gegevenstypentoewijzing voor elke gebeurtenis te krijgen:</span><span class="sxs-lookup"><span data-stu-id="fc791-132">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="fc791-133">Hier volgt een voorbeeld voor apparaatgegevensgebeurtenis:</span><span class="sxs-lookup"><span data-stu-id="fc791-133">Here is an example for Device Info event:</span></span> 

  ![Afbeelding van gebeurtenishubresource Id2](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="fc791-135">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="fc791-135">Related topics</span></span>
- [<span data-ttu-id="fc791-136">Overzicht van geavanceerd jagen</span><span class="sxs-lookup"><span data-stu-id="fc791-136">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fc791-137">Microsoft Defender voor endpoint streaming API</span><span class="sxs-lookup"><span data-stu-id="fc791-137">Microsoft Defender for Endpoint streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="fc791-138">Microsoft Defender voor eindpuntgebeurtenissen streamen naar uw Azure-opslagaccount</span><span class="sxs-lookup"><span data-stu-id="fc791-138">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="fc791-139">Documentatie van Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="fc791-139">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="fc791-140">Verbindingsproblemen oplossen - Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="fc791-140">Troubleshoot connectivity issues - Azure Event Hubs</span></span>](/azure/event-hubs/troubleshooting-guide)