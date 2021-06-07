---
title: Gebeurtenissen Microsoft 365 Defender streamen naar Azure Event Hubs
description: Meer informatie over het configureren Microsoft 365 Defender om Geavanceerde gebeurtenissen voor jagen te streamen naar uw Event Hub.
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
ms.openlocfilehash: 82a2e5cc3555dd3f444e7a1fc1b7126603bea489
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778219"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a><span data-ttu-id="4b646-104">Configureer Microsoft 365 Defender om Advanced Hunting-gebeurtenissen te streamen naar uw Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="4b646-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Azure Event Hubs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4b646-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4b646-105">**Applies to:**</span></span>
- [<span data-ttu-id="4b646-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b646-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



## <a name="before-you-begin"></a><span data-ttu-id="4b646-107">Voordat u begint:</span><span class="sxs-lookup"><span data-stu-id="4b646-107">Before you begin:</span></span>

1. <span data-ttu-id="4b646-108">Maak een [gebeurtenishub](/azure/event-hubs/) in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="4b646-108">Create an [event hub](/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="4b646-109">Meld u aan bij [uw Azure-tenant,](https://ms.portal.azure.com/)ga naar Abonnementen > Uw > **Resource Providers > Registreren bij Microsoft.Insights.**</span><span class="sxs-lookup"><span data-stu-id="4b646-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

3. <span data-ttu-id="4b646-110">Maak een naamruimte voor gebeurtenishubs, ga naar **Event Hubs > Toevoegen** en selecteer de prijslaag, doorvoereenheden en Auto-Opdrijven die geschikt zijn voor verwachte belasting.</span><span class="sxs-lookup"><span data-stu-id="4b646-110">Create an Event Hub Namespace, go to **Event Hubs > Add** and select the pricing tier, throughput units and Auto-Inflate appropriate for expected load.</span></span> <span data-ttu-id="4b646-111">Zie Prijzen [- Event Hubs | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span><span class="sxs-lookup"><span data-stu-id="4b646-111">For more information, see [Pricing - Event Hubs | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span></span>  

4. <span data-ttu-id="4b646-112">Wanneer de naamruimte van de gebeurtenishub is gemaakt, moet u de App Registration Service Principal toevoegen als lezer, Azure Event Hubs Data Receiver en de gebruiker die zich als inzender bij Microsoft 365 Defender zal aanmelden (dit kan ook op resourcegroep- of abonnementsniveau).</span><span class="sxs-lookup"><span data-stu-id="4b646-112">Once the event hub namespace is created you will need to add the App Registration Service Principal as Reader, Azure Event Hubs Data Receiver and the user who will be logging into Microsoft 365 Defender as Contributor (this can also be done at Resource Group or Subscription level).</span></span> <span data-ttu-id="4b646-113">Ga naar **Naamruimte voor gebeurtenishubs > Access-besturingselement (IAM) > Toevoegen** en verifiëren onder **Rolwijsingen.**</span><span class="sxs-lookup"><span data-stu-id="4b646-113">Go to **Event hubs namespace > Access control (IAM) > Add** and verify under **Role assignements**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="4b646-114">Onbewerkte gegevensstreaming inschakelen:</span><span class="sxs-lookup"><span data-stu-id="4b646-114">Enable raw data streaming:</span></span>

1. <span data-ttu-id="4b646-115">Meld u aan bij [het Microsoft 365 Defender-beveiligingscentrum](https://security.microsoft.com) als een ***Globale beheerder** _ of _*_Beveiligingsbeheerder_\*\*.</span><span class="sxs-lookup"><span data-stu-id="4b646-115">Log in to the [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="4b646-116">Ga naar de pagina [Instellingen voor gegevensexport.](https://security.microsoft.com/settings/mtp_settings/raw_data_export)</span><span class="sxs-lookup"><span data-stu-id="4b646-116">Go to the [Data export settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export).</span></span>

3. <span data-ttu-id="4b646-117">Klik op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="4b646-117">Click on **Add**.</span></span>

4. <span data-ttu-id="4b646-118">Kies een naam voor uw nieuwe instellingen.</span><span class="sxs-lookup"><span data-stu-id="4b646-118">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="4b646-119">Kies **Gebeurtenissen doorsturen naar Azure Event Hubs**.</span><span class="sxs-lookup"><span data-stu-id="4b646-119">Choose **Forward events to Azure Event Hubs**.</span></span>

6. <span data-ttu-id="4b646-120">U kunt selecteren of u de gebeurtenisgegevens wilt exporteren naar één gebeurtenishub of als u elke gebeurtenistabel wilt exporteren naar een andere even hub in de naamruimte van de gebeurtenishub.</span><span class="sxs-lookup"><span data-stu-id="4b646-120">You can select if you want to export the event data to a single event hub, or to export each event table to a different even hub in your event hub namespace.</span></span> 

7. <span data-ttu-id="4b646-121">Als u de gebeurtenisgegevens naar één gebeurtenishub wilt exporteren, voert u de naam van de **gebeurtenishub** en de **resource-id Voor gebeurtenishub in.**</span><span class="sxs-lookup"><span data-stu-id="4b646-121">To export the event data to a single event hub, Enter your **Event Hub name** and your **Event Hub resource ID**.</span></span>

   <span data-ttu-id="4b646-122">Als u de **resource-id Event Hubs** wilt downloaden, gaat u naar de naamruimtepagina van Azure Event Hubs op het tabblad [Azure](https://ms.portal.azure.com/)Properties > kopieert u de tekst onder  >   **Resource-id:**</span><span class="sxs-lookup"><span data-stu-id="4b646-122">To get your **Event Hubs resource ID**, go to your Azure Event Hubs namespace page on [Azure](https://ms.portal.azure.com/) > **Properties** tab > copy the text under **Resource ID**:</span></span>

   ![Afbeelding van gebeurtenishubresource Id1](images/event-hub-resource-id.png)

8. <span data-ttu-id="4b646-124">Kies de gebeurtenissen die u wilt streamen en klik op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="4b646-124">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a><span data-ttu-id="4b646-125">Het schema van de gebeurtenissen in Azure Event Hubs:</span><span class="sxs-lookup"><span data-stu-id="4b646-125">The schema of the events in Azure Event Hubs:</span></span>

```
{
    "records": [
                    {
                        "time": "<The time Microsoft 365 Defender received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- <span data-ttu-id="4b646-126">Elk bericht van de gebeurtenishub in Azure Event Hubs bevat een lijst met records.</span><span class="sxs-lookup"><span data-stu-id="4b646-126">Each event hub message in Azure Event Hubs contains list of records.</span></span>

- <span data-ttu-id="4b646-127">Elke record bevat de naam van de gebeurtenis, de tijd dat Microsoft 365 Defender de gebeurtenis heeft ontvangen, de tenant waar deze deel van uitmaken (u ontvangt alleen gebeurtenissen van uw tenant) en de gebeurtenis in JSON-indeling in een eigenschap genaamd **"** eigenschappen ".</span><span class="sxs-lookup"><span data-stu-id="4b646-127">Each record contains the event name, the time Microsoft 365 Defender received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="4b646-128">Zie Geavanceerd overzicht van de Microsoft 365 Defender voor meer informatie over het schema van de gebeurtenissen [in Defender.](../defender/advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4b646-128">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="4b646-129">In Advanced Hunting heeft de **tabel DeviceInfo** een kolom met de naam **MachineGroep** die de groep van het apparaat bevat.</span><span class="sxs-lookup"><span data-stu-id="4b646-129">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="4b646-130">Hier wordt elke gebeurtenis ook gedecoreerd met deze kolom.</span><span class="sxs-lookup"><span data-stu-id="4b646-130">Here every event will be decorated with this column as well.</span></span> 

9. <span data-ttu-id="4b646-131">Als u elke gebeurtenistabel wilt exporteren  naar een andere gebeurtenishub, laat u de naam van de hub Gebeurtenis leeg en Microsoft 365 Defender de rest.</span><span class="sxs-lookup"><span data-stu-id="4b646-131">To export each event table to a different event hub, simply leave the **Event hub name** empty, and Microsoft 365 Defender will do the rest.</span></span>


## <a name="data-types-mapping"></a><span data-ttu-id="4b646-132">Gegevenstypen toewijzen:</span><span class="sxs-lookup"><span data-stu-id="4b646-132">Data types mapping:</span></span>

<span data-ttu-id="4b646-133">Ga als volgt te werk om de gegevenstypen voor gebeurteniseigenschappen op te halen:</span><span class="sxs-lookup"><span data-stu-id="4b646-133">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="4b646-134">Meld u aan [bij Microsoft 365 beveiligingscentrum](https://security.microsoft.com) en ga naar [de pagina Geavanceerd zoeken.](https://security.microsoft.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="4b646-134">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="4b646-135">Voer de volgende query uit om de gegevenstypentoewijzing voor elke gebeurtenis te krijgen:</span><span class="sxs-lookup"><span data-stu-id="4b646-135">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="4b646-136">Hier volgt een voorbeeld voor apparaatgegevensgebeurtenis:</span><span class="sxs-lookup"><span data-stu-id="4b646-136">Here is an example for Device Info event:</span></span> 

  ![Afbeelding van gebeurtenishubresource Id2](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="4b646-138">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="4b646-138">Related topics</span></span>
- [<span data-ttu-id="4b646-139">Overzicht van geavanceerd jagen</span><span class="sxs-lookup"><span data-stu-id="4b646-139">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="4b646-140">Microsoft 365 Defender-streaming-API</span><span class="sxs-lookup"><span data-stu-id="4b646-140">Microsoft 365 Defender streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="4b646-141">Gebeurtenissen Microsoft 365 Defender streamen naar uw Azure-opslagaccount</span><span class="sxs-lookup"><span data-stu-id="4b646-141">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="4b646-142">Documentatie van Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="4b646-142">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="4b646-143">Verbindingsproblemen oplossen - Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="4b646-143">Troubleshoot connectivity issues - Azure Event Hubs</span></span>](/azure/event-hubs/troubleshooting-guide)
