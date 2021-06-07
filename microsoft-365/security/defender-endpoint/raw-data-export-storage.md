---
title: Microsoft Defender voor eindpuntgebeurtenissen streamen naar uw Storage account
description: Meer informatie over het configureren van Microsoft Defender voor Eindpunt voor het streamen van Advanced Hunting-gebeurtenissen naar uw Storage account.
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
ms.openlocfilehash: c280baaf3af6f9fcac6059bc2797910eb6c226fd
ms.sourcegitcommit: f0118e61e490496cb23189cc5c73b23e2ba939be
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52780175"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a>Microsoft Defender voor Eindpunt configureren om geavanceerde gebeurtenissen voor het zoeken naar uw Storage streamen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a>Voordat u begint

1. Maak een [Storage account](/azure/storage/common/storage-account-overview) in uw tenant.

2. Meld u aan bij [uw Azure-tenant](https://ms.portal.azure.com/), ga naar Abonnementen > Uw abonnement > **Resource Providers > Registreren bij Microsoft.insights.**

## <a name="enable-raw-data-streaming"></a>Onbewerkte gegevensstreaming inschakelen

1. Meld u aan bij [de Microsoft Defender for Endpoint-portal](https://securitycenter.windows.com) als een * Globale **beheerder** _ of _*_Beveiligingsbeheerder_**.

2. Ga naar [de pagina Instellingen voor gegevensexport](https://securitycenter.windows.com/interoperability/dataexport) op Microsoft Defender-beveiligingscentrum.

3. Klik op **Instellingen voor gegevensexport toevoegen.**

4. Kies een naam voor uw nieuwe instellingen.

5. Kies **Gebeurtenissen doorsturen om te Azure Storage.**

6. Typ uw **Storage accountresource-id**. Als u uw Storage **Account Resource-id** wilt downloaden, gaat u naar de pagina met Storage-account op het tabblad Eigenschappen van [azure portal](https://ms.portal.azure.com/) > > kopieert u de tekst onder Storage **accountresource-id:**

   ![Afbeelding van gebeurtenishub resource-id1](images/storage-account-resource-id.png)

7. Kies de gebeurtenissen die u wilt streamen en klik op **Opslaan.**

## <a name="the-schema-of-the-events-in-the-storage-account"></a>Het schema van de gebeurtenissen in het Storage account

- Er wordt een blobcontainer gemaakt voor elk gebeurtenistype: 

  ![Afbeelding van gebeurtenishub resource-id2](images/storage-account-event-schema.png)

- Het schema van elke rij in een blob is het volgende JSON: 

  ```
  {
          "time": "<The time WDATP received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <WDATP Advanced Hunting event as Json> }
  }               
  ```

- Elke blob bevat meerdere rijen.

- Elke rij bevat de naam van de gebeurtenis, de tijd dat Defender voor Eindpunt de gebeurtenis heeft ontvangen, de tenant waar deze deel van uitmaken (u ontvangt alleen gebeurtenissen van uw tenant) en de gebeurtenis in JSON-indeling in een eigenschap genaamd 'eigenschappen'.

- Zie Geavanceerd overzicht van jagen voor meer informatie over het schema van Microsoft Defender voor [eindpuntgebeurtenissen.](advanced-hunting-overview.md)

- In Advanced Hunting heeft de **tabel DeviceInfo** een kolom met de naam **MachineGroep** die de groep van het apparaat bevat. Hier wordt elke gebeurtenis ook gedecoreerd met deze kolom. Zie [Apparaatgroepen voor](machine-groups.md) meer informatie.

## <a name="data-types-mapping"></a>Gegevenstypen toewijzen

Ga als volgt te werk om de gegevenstypen voor onze gebeurteniseigenschappen op te halen:

1. Meld u aan [bij Microsoft Defender-beveiligingscentrum](https://securitycenter.windows.com) en ga naar de pagina [Geavanceerd zoeken.](https://securitycenter.windows.com/hunting-package)

2. Voer de volgende query uit om de gegevenstypentoewijzing voor elke gebeurtenis te krijgen: 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Hier volgt een voorbeeld voor apparaatgegevensgebeurtenis: 

  ![Afbeelding van gebeurtenishub resource-id3](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd jagen](advanced-hunting-overview.md)
- [Microsoft Defender voor Endpoint Streaming API](raw-data-export.md)
- [Microsoft Defender voor eindpuntgebeurtenissen streamen naar uw Azure-opslagaccount](raw-data-export-storage.md)
- [Azure Storage Accountdocumentatie](/azure/storage/common/storage-account-overview)