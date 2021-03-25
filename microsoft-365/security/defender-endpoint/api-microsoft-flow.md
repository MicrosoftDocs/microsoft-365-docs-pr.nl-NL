---
title: Microsoft Defender ATP Flow-connector
ms.reviewer: ''
description: Gebruik Microsoft Defender ATP Flow-connector om de beveiliging te automatiseren en een stroom te maken die wordt geactiveerd wanneer er een nieuwe waarschuwing op uw tenant wordt geplaatst.
keywords: flow, ondersteunde api's, api, Microsoft flow, query, automatisering
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
ms.openlocfilehash: 6fd210ddfb8e3ab6e4f1f4ffc0635c8b813e3a07
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163385"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a>Microsoft Power Automate (voorheen Microsoft Flow) en Azure-functies

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Het automatiseren van beveiligingsprocedures is een standaardvereiste voor elk modern Beveiligingscentrum. Het ontbreken van professionele cyberverdedigers dwingt SOC om op de meest efficiënte manier te werken en automatisering is een must. Microsoft Power Automate ondersteunt verschillende connectors die daar precies voor zijn gemaakt. U kunt binnen enkele minuten een end-to-end procedureautomatisering maken.

Microsoft Defender API heeft een officiële Stroomconnector met veel mogelijkheden.

![Afbeelding van referenties bewerken1](images/api-flow-0.png)

> [!NOTE]
> Zie Licenties voor [premium-connectors](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors)voor meer informatie over licentievoorwaarden voor premium connectors.


## <a name="usage-example"></a>Gebruiksvoorbeeld

In het volgende voorbeeld wordt gedemonstreerd hoe u een stroom maakt die wordt geactiveerd op elk moment dat er een nieuwe waarschuwing op uw tenant plaatsvindt.

1. Meld u aan [bij Microsoft Power Automate.](https://flow.microsoft.com)

2. Ga naar **Mijn stromen**  >  **Nieuw**  >  **geautomatiseerd-van leeg**.

    ![Afbeelding van referenties bewerken2](images/api-flow-1.png)

3. Kies een naam voor uw stroom, zoek naar 'Microsoft Defender ATP Triggers' als trigger en selecteer vervolgens de nieuwe trigger Waarschuwingen.

    ![Afbeelding van referenties bewerken3](images/api-flow-2.png)

Nu hebt u een stroom die wordt geactiveerd telkens wanneer er een nieuwe waarschuwing wordt gegeven.

![Afbeelding van referenties bewerken4](images/api-flow-3.png)

Het enige wat u nu hoeft te doen, is uw volgende stappen kiezen.
U kunt het apparaat bijvoorbeeld isoleren als de ernst van de waarschuwing hoog is en er een e-mailbericht over verzenden.
De waarschuwingstrigger bevat alleen de waarschuwings-id en de machine-id. U kunt de verbindingslijn gebruiken om deze entiteiten uit te vouwen.

### <a name="get-the-alert-entity-using-the-connector"></a>De entiteit Waarschuwing ontvangen met behulp van de verbindingslijn

1. Kies **Microsoft Defender ATP** voor de nieuwe stap.

2. Kies **Waarschuwingen - Eén waarschuwings-API ontvangen.**

3. Stel de **waarschuwings-id** van de laatste stap in als **Invoer.**

    ![Afbeelding van referenties bewerken5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a>Het apparaat isoleren als de ernst van de waarschuwing hoog is

1. Voorwaarde **toevoegen** als een nieuwe stap.

2. Controleer of de ernst van de waarschuwing **gelijk is aan** Hoog.

   Zo ja, voeg dan de **MICROSOFT Defender ATP - Machineactie isoleren** toe met de machine-id en een opmerking.

    ![Afbeelding van referenties bewerken6](images/api-flow-5.png)

3. Voeg een nieuwe stap toe voor het e-mailen over de waarschuwing en de isolatie. Er zijn meerdere e-mailconnectoren die heel eenvoudig te gebruiken zijn, zoals Outlook of Gmail.

4. Sla uw stroom op.

U kunt ook een geplande stroom **maken** met geavanceerde query's en nog veel meer.

## <a name="related-topic"></a>Gerelateerd onderwerp
- [Microsoft Defender voor eindpunt-API's](apis-intro.md)
