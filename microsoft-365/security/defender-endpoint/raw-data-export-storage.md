---
title: Gebeurtenissen Microsoft 365 Defender streamen naar uw Storage account
description: Meer informatie over het configureren Microsoft 365 Defender om geavanceerde gebeurtenissen voor jagen te streamen naar uw Storage account.
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
ms.openlocfilehash: 9ec8c286828fd6b551bf76c8340b58c9a1407bba
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778207"
---
# <a name="configure--microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a>Configureer Microsoft 365 Defender om Advanced Hunting-gebeurtenissen te streamen naar uw Storage account

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="before-you-begin"></a>Voordat u begint:

1. Maak een [Storage account](/azure/storage/common/storage-account-overview) in uw tenant.

2. Meld u aan bij [uw Azure-tenant,](https://ms.portal.azure.com/)ga naar Abonnementen > Uw > **Resource Providers > Registreren bij Microsoft.Insights.**

## <a name="enable-raw-data-streaming"></a>Onbewerkte gegevensstreaming inschakelen:

1. Meld u aan [bij Microsoft 365 Defender-beveiligingscentrum](https://security.microsoft.com) als een ***Globale beheerder** _ of _*_Beveiligingsbeheerder_**.

2. Ga naar [de pagina Instellingen voor gegevensexport](https://security.microsoft.com/settings/mtp_settings/raw_data_export) in Microsoft Defender-beveiligingscentrum.

3. Klik op **Instellingen voor gegevensexport toevoegen.**

4. Kies een naam voor uw nieuwe instellingen.

5. Kies **Gebeurtenissen doorsturen om te Azure Storage.**

6. Typ uw **Storage accountresource-id**. Als u uw Storage **Account Resource-id** wilt downloaden, gaat u naar de pagina met Storage-account op het tabblad Eigenschappen van [azure portal](https://ms.portal.azure.com/) > > kopieert u de tekst onder Storage Account **Resource ID:**

   ![Afbeelding van gebeurtenishub resource-id1](images/storage-account-resource-id.png)

7. Kies de gebeurtenissen die u wilt streamen en klik op **Opslaan.**

## <a name="the-schema-of-the-events-in-the-storage-account"></a>Het schema van de gebeurtenissen in het Storage account:

- Er wordt een blobcontainer gemaakt voor elk gebeurtenistype: 

  ![Afbeelding van gebeurtenishub resource-id2](images/storage-account-event-schema.png)

- Het schema van elke rij in een blob is het volgende JSON: 

  ```
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }               
  ```

- Elke blob bevat meerdere rijen.

- Elke rij bevat de naam van de gebeurtenis, de tijd dat Defender voor Eindpunt de gebeurtenis heeft ontvangen, de tenant waar deze deel van uitmaken (u ontvangt alleen gebeurtenissen van uw tenant) en de gebeurtenis in JSON-indeling in een eigenschap genaamd 'eigenschappen'.

- Zie Geavanceerd overzicht van de Microsoft 365 Defender voor meer informatie over het schema van de gebeurtenissen [in Defender.](../defender/advanced-hunting-overview.md)


## <a name="data-types-mapping"></a>Gegevenstypen toewijzen:

Ga als volgt te werk om de gegevenstypen voor onze gebeurteniseigenschappen op te halen:

1. Meld u aan [bij Microsoft 365 beveiligingscentrum](https://security.microsoft.com) en ga naar [de pagina Geavanceerd zoeken.](https://security.microsoft.com/hunting-package)

2. Voer de volgende query uit om de gegevenstypentoewijzing voor elke gebeurtenis te krijgen: 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Hier volgt een voorbeeld voor apparaatgegevensgebeurtenis: 

  ![Afbeelding van gebeurtenishub resource-id3](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd jagen](../defender/advanced-hunting-overview.md)
- [Microsoft 365 Defender Streaming API](raw-data-export.md)
- [Gebeurtenissen Microsoft 365 Defender streamen naar uw Azure-opslagaccount](raw-data-export-storage.md)
- [Azure Storage Accountdocumentatie](/azure/storage/common/storage-account-overview)
