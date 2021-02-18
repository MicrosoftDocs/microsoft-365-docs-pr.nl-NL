---
title: Rapport over niet-bezorging in het dashboard E-mailstroom
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie vinden over het gebruik van het rapport Niet-bezorgingsdetails in het dashboard E-mailstroom in het beveiligings- & Compliancecentrum om de meest voorkomende foutcodes in rapporten over niet-bezorging (ook wel NDR's of niet-bezorgdberichten genoemd) van afzenders in uw organisatie te controleren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0e31e7dfcbd3c0cacaa6020464ed315f466a849b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287887"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>Rapport over niet-levering in het beveiligings- & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Het rapport Niet-bezorging in het [dashboard E-mailstroom](mail-flow-insights-v2.md) in het [beveiligings- &-compliancecentrum](https://protection.office.com) bevat de meest voorkomende foutcodes in rapporten over **niet-bezorging** (ook wel NDR's of niet-bezorgdberichten genoemd) voor gebruikers in uw organisatie. Dit rapport bevat de details van NR's, zodat u problemen met de bezorging van e-mail kunt oplossen.

![Widget Rapport over niet-bezorging in het dashboard E-mailstroom in het & Compliancecentrum](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>Rapportweergave voor het rapport Niet-bezorging

Als u op de widget **Rapport over niet-bezorging** klikt, gaat u naar het rapport **Niet-bezorging.**

Standaard wordt de activiteit voor alle foutcodes weergegeven. Als u op **Gegevens tonen klikt,** kunt u een specifieke foutcode selecteren in de vervolgkeuzepagina.

Als u op een bepaalde dag in de grafiek de muisaanwijzer over een bepaalde kleur (foutcode) beweegt, ziet u het totale aantal berichten voor de fout.

![Rapportweergave in het rapport Niet-geaccepteerd domein](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>Tabelweergave Details voor het rapport Niet-bezorging

Als u in **een rapportweergave op Detailtabel** weergeven klikt, wordt de volgende informatie weergegeven:

- **Datum**
- **Rapportcode voor niet-bezorging**
- **Aantal**
- **Voorbeeldberichten:** de bericht-e-mailberichten van een steekproef van beïnvloede berichten.

Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**

Als u het rapport voor een bepaald datumbereik per e-mail wilt versturen naar een of meer geadresseerden, klikt u op **Downloaden aanvragen.**

Wanneer u een rij in de tabel selecteert, wordt een flyout met de volgende informatie weergegeven:

- **Datum**
- **Rapportcode voor niet-bezorging:** klik op de koppeling voor meer informatie over de oorzaken en oplossingen voor de specifieke foutcode.
- **Aantal**
- **Voorbeeldberichten:** u kunt op **Voorbeeldberichten weergeven** klikken om de [resultaten](message-trace-scc.md) van bericht traceren voor een voorbeeld van de betreffende berichten te bekijken.

![Flyout Details na het selecteren van een rij in de tabelweergave Details in het rapport Niet-bezorging](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>Verwante onderwerpen

Zie inzichten in de e-mailstroom in het beveiligings- en compliancecentrum voor meer informatie & [inzichten in het dashboard E-mailstroom.](mail-flow-insights-v2.md)
