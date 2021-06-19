---
title: Gebeurtenissen Microsoft 365 Defender naar uw Storage-account
description: Meer informatie over het configureren van Microsoft 365 Defender voor het streamen van Advanced Hunting-gebeurtenissen naar uw Storage account.
keywords: raw data export, streaming API, API, Event Hubs, Azure storage, storage account, Advanced Hunting, raw data sharing
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
ms.openlocfilehash: 656387e60bac90c7e9de4852779948dabce0efe3
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029655"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="e4dd9-104">Configureer Microsoft 365 Defender advanced hunting-gebeurtenissen te streamen naar uw Storage account</span><span class="sxs-lookup"><span data-stu-id="e4dd9-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e4dd9-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e4dd9-105">**Applies to:**</span></span>
- [<span data-ttu-id="e4dd9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4dd9-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="e4dd9-107">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="e4dd9-107">Before you begin</span></span>

1. <span data-ttu-id="e4dd9-108">Maak een [Storage account](/azure/storage/common/storage-account-overview) in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="e4dd9-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="e4dd9-109">Meld u aan bij [uw Azure-tenant](https://ms.portal.azure.com/), ga naar Abonnementen > Uw abonnement **> Resource Providers > Registreren bij Microsoft.Insights.**</span><span class="sxs-lookup"><span data-stu-id="e4dd9-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="e4dd9-110">Onbewerkte gegevensstreaming inschakelen</span><span class="sxs-lookup"><span data-stu-id="e4dd9-110">Enable raw data streaming</span></span>

1. <span data-ttu-id="e4dd9-111">Meld u aan bij de Microsoft 365 Defender portal ( <https://security.microsoft.com> ) als een \* Globale **beheerder** _ of _\*_Beveiligingsbeheerder_\*\*.</span><span class="sxs-lookup"><span data-stu-id="e4dd9-111">Log in to the Microsoft 365 Defender portal (<https://security.microsoft.com>) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="e4dd9-112">Ga naar **Instellingen** \> **Microsoft 365 Defender** \> **Streaming API**.</span><span class="sxs-lookup"><span data-stu-id="e4dd9-112">Go to **Settings** \> **Microsoft 365 Defender** \> **Streaming API**.</span></span> <span data-ttu-id="e4dd9-113">Als u rechtstreeks naar de **pagina Streaming API wilt** gaan, gebruikt u <https://security.microsoft.com/settings/mtp_settings/raw_data_export> .</span><span class="sxs-lookup"><span data-stu-id="e4dd9-113">To go directly to the **Streaming API** page, use <https://security.microsoft.com/settings/mtp_settings/raw_data_export>.</span></span>

3. <span data-ttu-id="e4dd9-114">Klik op **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="e4dd9-114">Click **Add**.</span></span>

4. <span data-ttu-id="e4dd9-115">Configureer de volgende instellingen in de flyout **Add new Streaming API settings** that appears:</span><span class="sxs-lookup"><span data-stu-id="e4dd9-115">In the **Add new Streaming API settings** flyout that appears, configure the following settings:</span></span>
   1. <span data-ttu-id="e4dd9-116">**Naam:** Kies een naam voor uw nieuwe instellingen.</span><span class="sxs-lookup"><span data-stu-id="e4dd9-116">**Name**: Choose a name for your new settings.</span></span>
   2. <span data-ttu-id="e4dd9-117">Selecteer **Gebeurtenissen doorsturen om Azure Storage.**</span><span class="sxs-lookup"><span data-stu-id="e4dd9-117">Select **Forward events to Azure Storage**.</span></span>
   3. <span data-ttu-id="e4dd9-118">Typ uw **Storage accountresource-id** in het vak Account **Storage resource-id** dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e4dd9-118">In the **Storage Account Resource ID** box that appears, type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="e4dd9-119">Als u uw **accountresource-Storage** wilt downloaden, opent u de Azure-portal op , klikt u op Storage accounts naar het tabblad Eigenschappen om de tekst onder accountresource-id <https://portal.azure.com>  \> Storage \> **kopiëren.**</span><span class="sxs-lookup"><span data-stu-id="e4dd9-119">To get your **Storage Account Resource ID**, open the Azure portal at <https://portal.azure.com>, click **Storage accounts** \> go to the properties tab \> copy the text under **Storage Account Resource ID**.</span></span>

      ![Afbeelding van gebeurtenishub resource-id1](../defender-endpoint/images/storage-account-resource-id.png)

   4. <span data-ttu-id="e4dd9-121">Kies in **de flyout Nieuwe streaming API-instellingen** toevoegen de **gebeurtenistypen** die u wilt streamen.</span><span class="sxs-lookup"><span data-stu-id="e4dd9-121">Back on the **Add new Streaming API settings** flyout, choose the **Event types** that you want to stream.</span></span>

   <span data-ttu-id="e4dd9-122">Wanneer u klaar bent, klikt u op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="e4dd9-122">When you're finished, click **Submit**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="e4dd9-123">Het schema van de gebeurtenissen in het Storage account</span><span class="sxs-lookup"><span data-stu-id="e4dd9-123">The schema of the events in the Storage account</span></span>

- <span data-ttu-id="e4dd9-124">Er wordt een blobcontainer gemaakt voor elk gebeurtenistype:</span><span class="sxs-lookup"><span data-stu-id="e4dd9-124">A blob container will be created for each event type:</span></span>

  ![Afbeelding van gebeurtenishub resource-id2](../defender-endpoint/images/storage-account-event-schema.png)

- <span data-ttu-id="e4dd9-126">Het schema van elke rij in een blob is het volgende JSON:</span><span class="sxs-lookup"><span data-stu-id="e4dd9-126">The schema of each row in a blob is the following JSON:</span></span>

  ```JSON
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }
  ```

- <span data-ttu-id="e4dd9-127">Elke blob bevat meerdere rijen.</span><span class="sxs-lookup"><span data-stu-id="e4dd9-127">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="e4dd9-128">Elke rij bevat de naam van de gebeurtenis, de tijd dat Defender voor Eindpunt de gebeurtenis heeft ontvangen, de tenant waar deze deel van uitmaken (u ontvangt alleen gebeurtenissen van uw tenant) en de gebeurtenis in JSON-indeling in een eigenschap genaamd 'eigenschappen'.</span><span class="sxs-lookup"><span data-stu-id="e4dd9-128">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="e4dd9-129">Zie Geavanceerd overzicht van de Microsoft 365 Defender voor meer informatie over het schema [van Microsoft 365 Defender gebeurtenissen.](../defender/advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e4dd9-129">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="e4dd9-130">Gegevenstypen toewijzen</span><span class="sxs-lookup"><span data-stu-id="e4dd9-130">Data types mapping</span></span>

<span data-ttu-id="e4dd9-131">Ga als volgt te werk om de gegevenstypen voor onze gebeurteniseigenschappen op te halen:</span><span class="sxs-lookup"><span data-stu-id="e4dd9-131">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="e4dd9-132">Meld u aan bij de Microsoft 365 Defender portal <https://security.microsoft.com> () en ga naar **Hunting** \> **Advanced hunting.**</span><span class="sxs-lookup"><span data-stu-id="e4dd9-132">Log in to the Microsoft 365 Defender portal (<https://security.microsoft.com>) and go to **Hunting** \> **Advanced hunting**.</span></span> <span data-ttu-id="e4dd9-133">Als u rechtstreeks naar de pagina **Geavanceerd wilt gaan,** gebruikt u <security.microsoft.com/advanced-hunting>.</span><span class="sxs-lookup"><span data-stu-id="e4dd9-133">To go directly to the **Advanced hunting** page, use <security.microsoft.com/advanced-hunting>.</span></span>

2. <span data-ttu-id="e4dd9-134">Voer op **het** tabblad Query de volgende query uit om de gegevenstypentoewijzing voor elke gebeurtenis te krijgen:</span><span class="sxs-lookup"><span data-stu-id="e4dd9-134">On the **Query** tab, run the following query to get the data types mapping for each event:</span></span>

   ```text
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- <span data-ttu-id="e4dd9-135">Hier volgt een voorbeeld voor apparaatgegevensgebeurtenis:</span><span class="sxs-lookup"><span data-stu-id="e4dd9-135">Here is an example for Device Info event:</span></span>

  ![Afbeelding van gebeurtenishub resource-id3](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="e4dd9-137">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="e4dd9-137">Related topics</span></span>

- [<span data-ttu-id="e4dd9-138">Overzicht van geavanceerd jagen</span><span class="sxs-lookup"><span data-stu-id="e4dd9-138">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="e4dd9-139">Microsoft 365 Defender Streaming-API</span><span class="sxs-lookup"><span data-stu-id="e4dd9-139">Microsoft 365 Defender Streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="e4dd9-140">Gebeurtenissen Microsoft 365 Defender naar uw Azure-opslagaccount streamen</span><span class="sxs-lookup"><span data-stu-id="e4dd9-140">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="e4dd9-141">Azure Storage Accountdocumentatie</span><span class="sxs-lookup"><span data-stu-id="e4dd9-141">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
