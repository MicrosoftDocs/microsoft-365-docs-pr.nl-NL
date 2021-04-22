---
title: Microsoft Defender voor endpoint-API's-verbinding met Power BI
ms.reviewer: ''
description: Maak een BI-rapport (Power Business Intelligence) boven microsoft Defender voor eindpunt-API's.
keywords: api's, ondersteunde api's, Power BI, rapporten
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 7c99267d75c89b3484d207cd763131e4bcc91527
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935039"
---
# <a name="create-custom-reports-using-power-bi"></a>Aangepaste rapporten maken met Power BI

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

In deze sectie leert u een Power BI-rapport maken op de top van Defender voor eindpunt-API's.

In het eerste voorbeeld wordt gedemonstreerd hoe u Power BI koppelt aan advanced hunting API en in het tweede voorbeeld wordt een verbinding met onze OData-API's gedemonstreerd, zoals MachineActies of Waarschuwingen.

## <a name="connect-power-bi-to-advanced-hunting-api"></a>Power BI verbinden met advanced hunting API

- Microsoft Power BI openen

- Klik **op Lege**  >  **gegevensquery opvragen**

    ![Afbeelding van lege query maken](images/power-bi-create-blank-query.png)

- Klik **op Geavanceerde editor**

    ![Afbeelding van geopende geavanceerde editor](images/power-bi-open-advanced-editor.png)

- Kopieer het onderstaande en plak deze in de editor:

```
    let 
        AdvancedHuntingQuery = "DeviceEvents | where ActionType contains 'Anti' | limit 20",

        HuntingUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries",

        Response = Json.Document(Web.Contents(HuntingUrl, [Query=[key=AdvancedHuntingQuery]])),

        TypeMap = #table(
            { "Type", "PowerBiType" },
            {
                { "Double",   Double.Type },
                { "Int64",    Int64.Type },
                { "Int32",    Int32.Type },
                { "Int16",    Int16.Type },
                { "UInt64",   Number.Type },
                { "UInt32",   Number.Type },
                { "UInt16",   Number.Type },
                { "Byte",     Byte.Type },
                { "Single",   Single.Type },
                { "Decimal",  Decimal.Type },
                { "TimeSpan", Duration.Type },
                { "DateTime", DateTimeZone.Type },
                { "String",   Text.Type },
                { "Boolean",  Logical.Type },
                { "SByte",    Logical.Type },
                { "Guid",     Text.Type }
            }),

        Schema = Table.FromRecords(Response[Schema]),
        TypedSchema = Table.Join(Table.SelectColumns(Schema, {"Name", "Type"}), {"Type"}, TypeMap , {"Type"}),
        Results = Response[Results],
        Rows = Table.FromRecords(Results, Schema[Name]),
        Table = Table.TransformColumnTypes(Rows, Table.ToList(TypedSchema, (c) => {c{0}, c{2}}))

    in Table

```

- Klik **op Klaar**

- Klik **op Referenties bewerken**

    ![Afbeelding van referenties bewerken0](images/power-bi-edit-credentials.png)

- Organisatieaccount **selecteren**  >  **Aanmelden**

    ![Afbeelding van setreferenties1](images/power-bi-set-credentials-organizational.png)

- Voer uw referenties in en wacht totdat u bent aangemeld

- Klik op **Verbinding maken**

    ![Afbeelding van setreferenties2](images/power-bi-set-credentials-organizational-cont.png)

- De resultaten van de query worden nu weergegeven als tabel en u kunt er visualisaties op maken.

- U kunt deze tabel dupliceren, de naam ervan wijzigen en de query Geavanceerd zoeken binnen bewerken om eventuele gegevens op te halen.

## <a name="connect-power-bi-to-odata-apis"></a>Power BI verbinden met OData-API's

- Het enige verschil met het bovenstaande voorbeeld is de query in de editor. 

- Kopieer het onderstaande en plak deze in de editor om alle **machineacties uit** uw organisatie te halen:

```
    let

        Query = "MachineActions",

        Source = OData.Feed("https://api.securitycenter.microsoft.com/api/" & Query, null, [Implementation="2.0", MoreColumns=true])
    in
        Source

```

- U kunt hetzelfde doen voor **waarschuwingen** en **machines.**

- U kunt OData-query's ook gebruiken voor queryfilters, zie [OData-query's gebruiken](exposed-apis-odata-samples.md)


## <a name="power-bi-dashboard-samples-in-github"></a>Power BI-dashboardvoorbeelden in GitHub
Zie de [Power BI-rapportsjablonen](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI)voor meer informatie.

## <a name="sample-reports"></a>Voorbeeldrapporten
Bekijk de voorbeelden van het Microsoft Defender voor Endpoint Power BI-rapport. Zie Door codevoorbeelden bladeren voor [meer informatie.](https://docs.microsoft.com/samples/browse/?products=mdatp)


## <a name="related-topic"></a>Verwant onderwerp
- [Defender voor eindpunt-API's](apis-intro.md)
- [Geavanceerde API voor opsporing](run-advanced-query-api.md)
- [OData-query's gebruiken](exposed-apis-odata-samples.md)
