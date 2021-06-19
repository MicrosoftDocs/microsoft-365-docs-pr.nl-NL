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
ms.openlocfilehash: fa61e2fd0591d375a17bad6e166a76c1ca40862e
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028881"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="fc35a-104">Configureer Microsoft 365 Defender advanced hunting-gebeurtenissen te streamen naar uw Storage account</span><span class="sxs-lookup"><span data-stu-id="fc35a-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fc35a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="fc35a-105">**Applies to:**</span></span>
- [<span data-ttu-id="fc35a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc35a-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a><span data-ttu-id="fc35a-107">Voordat u begint:</span><span class="sxs-lookup"><span data-stu-id="fc35a-107">Before you begin:</span></span>

1. <span data-ttu-id="fc35a-108">Maak een [Storage account](/azure/storage/common/storage-account-overview) in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="fc35a-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="fc35a-109">Meld u aan bij [uw Azure-tenant](https://ms.portal.azure.com/), ga naar Abonnementen > Uw abonnement **> Resource Providers > Registreren bij Microsoft.Insights.**</span><span class="sxs-lookup"><span data-stu-id="fc35a-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="fc35a-110">Onbewerkte gegevensstreaming inschakelen:</span><span class="sxs-lookup"><span data-stu-id="fc35a-110">Enable raw data streaming:</span></span>

1. <span data-ttu-id="fc35a-111">Meld u aan [bij Microsoft 365 Defender beveiligingscentrum](https://security.microsoft.com) als een ***Globale beheerder** _ of _*_Beveiligingsbeheerder_\*\*.</span><span class="sxs-lookup"><span data-stu-id="fc35a-111">Log in to [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="fc35a-112">Ga naar [de pagina Instellingen voor gegevensexport](https://security.microsoft.com/settings/mtp_settings/raw_data_export) in Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="fc35a-112">Go to [Data export settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export) in Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="fc35a-113">Klik op **Instellingen voor gegevensexport toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="fc35a-113">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="fc35a-114">Kies een naam voor uw nieuwe instellingen.</span><span class="sxs-lookup"><span data-stu-id="fc35a-114">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="fc35a-115">Kies **Gebeurtenissen doorsturen om te Azure Storage.**</span><span class="sxs-lookup"><span data-stu-id="fc35a-115">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="fc35a-116">Typ uw **Storage accountresource-id**.</span><span class="sxs-lookup"><span data-stu-id="fc35a-116">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="fc35a-117">Als u uw Storage **Account Resource-id** wilt downloaden, gaat u naar de pagina met Storage-account op het tabblad Eigenschappen van [azure portal](https://ms.portal.azure.com/) > > kopieert u de tekst onder Storage Account **Resource ID:**</span><span class="sxs-lookup"><span data-stu-id="fc35a-117">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage Account Resource ID**:</span></span>

   ![Afbeelding van gebeurtenishub resource-id1](../defender-endpoint/images/storage-account-resource-id.png)

7. <span data-ttu-id="fc35a-119">Kies de gebeurtenissen die u wilt streamen en klik op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="fc35a-119">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="fc35a-120">Het schema van de gebeurtenissen in het Storage account:</span><span class="sxs-lookup"><span data-stu-id="fc35a-120">The schema of the events in the Storage account:</span></span>

- <span data-ttu-id="fc35a-121">Er wordt een blobcontainer gemaakt voor elk gebeurtenistype:</span><span class="sxs-lookup"><span data-stu-id="fc35a-121">A blob container will be created for each event type:</span></span> 

  ![Afbeelding van gebeurtenishub resource-id2](../defender-endpoint/images/storage-account-event-schema.png)

- <span data-ttu-id="fc35a-123">Het schema van elke rij in een blob is het volgende JSON:</span><span class="sxs-lookup"><span data-stu-id="fc35a-123">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="fc35a-124">Elke blob bevat meerdere rijen.</span><span class="sxs-lookup"><span data-stu-id="fc35a-124">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="fc35a-125">Elke rij bevat de naam van de gebeurtenis, de tijd dat Defender voor Eindpunt de gebeurtenis heeft ontvangen, de tenant waar deze deel van uitmaken (u ontvangt alleen gebeurtenissen van uw tenant) en de gebeurtenis in JSON-indeling in een eigenschap genaamd 'eigenschappen'.</span><span class="sxs-lookup"><span data-stu-id="fc35a-125">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="fc35a-126">Zie Geavanceerd overzicht van de Microsoft 365 Defender voor meer informatie over het schema [van Microsoft 365 Defender gebeurtenissen.](../defender/advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="fc35a-126">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>


## <a name="data-types-mapping"></a><span data-ttu-id="fc35a-127">Gegevenstypen toewijzen</span><span class="sxs-lookup"><span data-stu-id="fc35a-127">Data types mapping</span></span>

<span data-ttu-id="fc35a-128">Ga als volgt te werk om de gegevenstypen voor onze gebeurteniseigenschappen op te halen:</span><span class="sxs-lookup"><span data-stu-id="fc35a-128">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="fc35a-129">Meld u aan [bij Microsoft 365 beveiligingscentrum](https://security.microsoft.com) en ga naar [de pagina Geavanceerd zoeken.](https://security.microsoft.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="fc35a-129">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="fc35a-130">Voer de volgende query uit om de gegevenstypentoewijzing voor elke gebeurtenis te krijgen:</span><span class="sxs-lookup"><span data-stu-id="fc35a-130">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="fc35a-131">Hier volgt een voorbeeld voor apparaatgegevensgebeurtenis:</span><span class="sxs-lookup"><span data-stu-id="fc35a-131">Here is an example for Device Info event:</span></span> 

  ![Afbeelding van gebeurtenishub resource-id3](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="fc35a-133">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="fc35a-133">Related topics</span></span>
- [<span data-ttu-id="fc35a-134">Overzicht van geavanceerd jagen</span><span class="sxs-lookup"><span data-stu-id="fc35a-134">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="fc35a-135">Microsoft 365 Defender Streaming-API</span><span class="sxs-lookup"><span data-stu-id="fc35a-135">Microsoft 365 Defender Streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="fc35a-136">Gebeurtenissen Microsoft 365 Defender naar uw Azure-opslagaccount streamen</span><span class="sxs-lookup"><span data-stu-id="fc35a-136">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="fc35a-137">Azure Storage Accountdocumentatie</span><span class="sxs-lookup"><span data-stu-id="fc35a-137">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
