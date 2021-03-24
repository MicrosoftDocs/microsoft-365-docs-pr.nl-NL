---
title: Microsoft Defender voor eindpuntgebeurtenissen streamen naar Azure Event Hubs
description: Meer informatie over het configureren van Microsoft Defender ATP om advanced hunting-gebeurtenissen te streamen naar uw Event Hub.
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
ms.openlocfilehash: 231ba79e1d66eee263b6c1a4335f0a7b54eeb75d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058197"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a>Microsoft Defender voor Eindpunt configureren om geavanceerde gebeurtenissen te streamen naar uw Azure Event Hubs

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a>Voordat u begint:

1. Maak een [gebeurtenishub](https://docs.microsoft.com/azure/event-hubs/) in uw tenant.

2. Meld u aan bij [uw Azure-tenant](https://ms.portal.azure.com/), ga naar **Abonnementen > Uw abonnement > Resource Providers > Registreren bij **Microsoft.insights.**

## <a name="enable-raw-data-streaming"></a>Onbewerkte gegevensstreaming inschakelen:

1. Meld u aan bij [het Microsoft Defender-beveiligingscentrum](https://securitycenter.windows.com) als ***Globale beheerder** _ of _*_Beveiligingsbeheerder_**.

2. Ga naar de pagina [Instellingen voor gegevensexport](https://securitycenter.windows.com/interoperability/dataexport) in het Microsoft Defender-beveiligingscentrum.

3. Klik op **Instellingen voor gegevensexport toevoegen.**

4. Kies een naam voor uw nieuwe instellingen.

5. Kies **Gebeurtenissen doorsturen naar Azure Event Hubs**.

6. Typ de **naam van de gebeurtenishubs** en de **resource-id Event Hubs.**

   Als u de resource-id **Event Hubs** wilt downloaden, gaat u naar de naamruimtepagina van Azure Event Hubs op het tabblad Eigenschappen van [Azure](https://ms.portal.azure.com/) > > de tekst onder **Resource-id** kopiëren:

   ![Afbeelding van gebeurtenishubresource Id1](images/event-hub-resource-id.png)

7. Kies de gebeurtenissen die u wilt streamen en klik op **Opslaan.**

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a>Het schema van de gebeurtenissen in Azure Event Hubs:

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

- Elk bericht van de gebeurtenishub in Azure Event Hubs bevat een lijst met records.

- Elke record bevat de naam van de gebeurtenis, de tijd dat Microsoft Defender voor Eindpunt de gebeurtenis heeft ontvangen, de tenant waar deze deel van uitmaken (u ontvangt alleen gebeurtenissen van uw tenant) en de gebeurtenis in JSON-indeling in een eigenschap genaamd **"** eigenschappen ".

- Zie Geavanceerd overzicht van jagen voor meer informatie over het schema van Microsoft Defender voor [eindpuntgebeurtenissen.](advanced-hunting-overview.md)

- In Advanced Hunting heeft de **tabel DeviceInfo** een kolom met de naam **MachineGroep** die de groep van het apparaat bevat. Hier wordt elke gebeurtenis ook gedecoreerd met deze kolom. Zie [Apparaatgroepen voor](machine-groups.md) meer informatie.

## <a name="data-types-mapping"></a>Gegevenstypen toewijzen:

Ga als volgt te werk om de gegevenstypen voor gebeurteniseigenschappen op te halen:

1. Meld u aan [bij het Microsoft Defender-beveiligingscentrum](https://securitycenter.windows.com) en ga naar [de pagina Geavanceerd zoeken.](https://securitycenter.windows.com/hunting-package)

2. Voer de volgende query uit om de gegevenstypentoewijzing voor elke gebeurtenis te krijgen:
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Hier volgt een voorbeeld voor apparaatgegevensgebeurtenis: 

  ![Afbeelding van gebeurtenishubresource Id2](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd jagen](advanced-hunting-overview.md)
- [Microsoft Defender voor endpoint streaming API](raw-data-export.md)
- [Microsoft Defender voor eindpuntgebeurtenissen streamen naar uw Azure-opslagaccount](raw-data-export-storage.md)
- [Documentatie van Azure Event Hubs](https://docs.microsoft.com/azure/event-hubs/)
- [Verbindingsproblemen oplossen - Azure Event Hubs](https://docs.microsoft.com/azure/event-hubs/troubleshooting-guide)
