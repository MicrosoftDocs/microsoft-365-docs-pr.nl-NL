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
ms.openlocfilehash: b96ae78b0f2decfe7b2c6f695a4456ac93919c35
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772457"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a>Configureer Microsoft 365 Defender om Advanced Hunting-gebeurtenissen te streamen naar uw Azure Event Hubs

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a>Voordat u begint:

1. Maak een [gebeurtenishub](/azure/event-hubs/) in uw tenant.

2. Meld u aan bij [uw Azure-tenant,](https://ms.portal.azure.com/)ga naar Abonnementen > Uw > **Resource Providers > Registreren bij Microsoft.Insights.**

3. Maak een naamruimte voor gebeurtenishubs, ga naar **Event Hubs > Toevoegen** en selecteer de prijslaag, doorvoereenheden en Auto-Opdrijven die geschikt zijn voor verwachte belasting. Zie Prijzen [- Event Hubs | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).  

4. Wanneer de naamruimte van de gebeurtenishub is gemaakt, moet u de App Registration Service Principal toevoegen als lezer, Azure Event Hubs Data Receiver en de gebruiker die zich als inzender bij Microsoft 365 Defender zal aanmelden (dit kan ook op resourcegroep- of abonnementsniveau). Ga naar **Naamruimte voor gebeurtenishubs > Access-besturingselement (IAM) > Toevoegen** en verifiëren onder **Rolwijsingen.**

## <a name="enable-raw-data-streaming"></a>Onbewerkte gegevensstreaming inschakelen:

1. Meld u aan bij [het Microsoft 365 Defender-beveiligingscentrum](https://security.microsoft.com) als een ***Globale beheerder** _ of _*_Beveiligingsbeheerder_**.

2. Ga naar de pagina [Instellingen voor gegevensexport.](https://security.microsoft.com/settings/mtp_settings/raw_data_export)

3. Klik op **Toevoegen.**

4. Kies een naam voor uw nieuwe instellingen.

5. Kies **Gebeurtenissen doorsturen naar Azure Event Hubs**.

6. U kunt selecteren of u de gebeurtenisgegevens wilt exporteren naar één gebeurtenishub of als u elke gebeurtenistabel wilt exporteren naar een andere even hub in de naamruimte van de gebeurtenishub. 

7. Als u de gebeurtenisgegevens naar één gebeurtenishub wilt exporteren, voert u de naam van de **gebeurtenishub** en de **resource-id Voor gebeurtenishub in.**

   Als u de **resource-id Event Hubs** wilt downloaden, gaat u naar de naamruimtepagina van Azure Event Hubs op het tabblad [Azure](https://ms.portal.azure.com/)Properties > kopieert u de tekst onder  >   **Resource-id:**

   ![Afbeelding van gebeurtenishubresource Id1](../defender-endpoint/images/event-hub-resource-id.png)

8. Kies de gebeurtenissen die u wilt streamen en klik op **Opslaan.**

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a>Het schema van de gebeurtenissen in Azure Event Hubs:

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

- Elk bericht van de gebeurtenishub in Azure Event Hubs bevat een lijst met records.

- Elke record bevat de naam van de gebeurtenis, de tijd dat Microsoft 365 Defender de gebeurtenis heeft ontvangen, de tenant waar deze deel van uitmaken (u ontvangt alleen gebeurtenissen van uw tenant) en de gebeurtenis in JSON-indeling in een eigenschap genaamd **"** eigenschappen ".

- Zie Geavanceerd overzicht van de Microsoft 365 Defender voor meer informatie over het schema van de gebeurtenissen [in Defender.](advanced-hunting-overview.md)

- In Advanced Hunting heeft de **tabel DeviceInfo** een kolom met de naam **MachineGroep** die de groep van het apparaat bevat. Hier wordt elke gebeurtenis ook gedecoreerd met deze kolom. 

9. Als u elke gebeurtenistabel wilt exporteren  naar een andere gebeurtenishub, laat u de naam van de hub Gebeurtenis leeg en Microsoft 365 Defender de rest.


## <a name="data-types-mapping"></a>Gegevenstypen toewijzen:

Ga als volgt te werk om de gegevenstypen voor gebeurteniseigenschappen op te halen:

1. Meld u aan [bij Microsoft 365 beveiligingscentrum](https://security.microsoft.com) en ga naar [de pagina Geavanceerd zoeken.](https://security.microsoft.com/hunting-package)

2. Voer de volgende query uit om de gegevenstypentoewijzing voor elke gebeurtenis te krijgen:
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Hier volgt een voorbeeld voor apparaatgegevensgebeurtenis: 

  ![Afbeelding van gebeurtenishubresource Id2](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd jagen](advanced-hunting-overview.md)
- [Microsoft 365 Defender-streaming-API](streaming-api.md)
- [Gebeurtenissen Microsoft 365 Defender streamen naar uw Azure-opslagaccount](streaming-api-storage.md)
- [Documentatie van Azure Event Hubs](/azure/event-hubs/)
- [Verbindingsproblemen oplossen - Azure Event Hubs](/azure/event-hubs/troubleshooting-guide)
