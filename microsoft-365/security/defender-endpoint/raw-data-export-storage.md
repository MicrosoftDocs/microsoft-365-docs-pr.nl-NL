---
title: Microsoft Defender voor eindpuntgebeurtenissen streamen naar uw opslagaccount
description: Meer informatie over het configureren van Microsoft Defender ATP om advanced hunting-gebeurtenissen te streamen naar uw Opslagaccount.
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
ms.openlocfilehash: 9f1eb79bbf617afad58b7e4d70e1f40e422f9046
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058186"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a>Microsoft Defender voor eindpunt configureren voor het streamen van advanced hunting-gebeurtenissen naar uw opslagaccount

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a>Voordat u begint:

1. Maak een [Opslagaccount](https://docs.microsoft.com/azure/storage/common/storage-account-overview) in uw tenant.

2. Meld u aan bij [uw Azure-tenant](https://ms.portal.azure.com/), ga naar Abonnementen > Uw abonnement > **Resource Providers > Registreren bij Microsoft.insights.**

## <a name="enable-raw-data-streaming"></a>Onbewerkte gegevensstreaming inschakelen:

1. Meld u aan bij [de Microsoft Defender for Endpoint-portal](https://securitycenter.windows.com) als een * Globale **beheerder** _ of _*_Beveiligingsbeheerder_**.

2. Ga naar [de pagina Instellingen voor gegevensexport](https://securitycenter.windows.com/interoperability/dataexport) in het Microsoft Defender-beveiligingscentrum.

3. Klik op **Instellingen voor gegevensexport toevoegen.**

4. Kies een naam voor uw nieuwe instellingen.

5. Kies **Gebeurtenissen doorsturen naar Azure Storage.**

6. Typ uw **resource-id voor opslagaccount.** Als u uw opslagaccountresource-id wilt **downloaden,** gaat u naar de pagina Opslagaccount op het tabblad Eigenschappen van [Azure Portal](https://ms.portal.azure.com/) > > kopieert u de tekst onder **Opslagaccountresource-id:**

   ![Afbeelding van gebeurtenishub resource-id1](images/storage-account-resource-id.png)

7. Kies de gebeurtenissen die u wilt streamen en klik op **Opslaan.**

## <a name="the-schema-of-the-events-in-the-storage-account"></a>Het schema van de gebeurtenissen in het opslagaccount:

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

## <a name="data-types-mapping"></a>Gegevenstypen toewijzen:

Ga als volgt te werk om de gegevenstypen voor onze gebeurteniseigenschappen op te halen:

1. Meld u aan [bij het Microsoft Defender-beveiligingscentrum](https://securitycenter.windows.com) en ga naar [de pagina Geavanceerd zoeken.](https://securitycenter.windows.com/hunting-package)

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
- [Documentatie over Azure Storage-account](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
