---
title: Rapport over niet-geaccepteerd domein in het dashboard e-mailstroom
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
description: Beheerders kunnen informatie vinden over het gebruik van het rapport Niet-geaccepteerd domein in het dashboard E-mailstroom in het beveiligings- & Compliancecentrum om berichten te controleren van uw on-premises organisatie waar het domein van de afzender niet is geconfigureerd in Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 573fb0ba2bf7981b6eb7df4eec7c8c4e5d596cac
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150818"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>Rapport over niet-geaccepteerd domein in het & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender voor Office 365-abonnement 1 en abonnement 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

In het rapport Niet-geaccepteerd domein in het [dashboard](mail-flow-insights-v2.md) E-mailstroom in het [beveiligings- & compliancecentrum](https://protection.office.com) wordt informatie weergegeven over berichten van uw **on-premises e-mailorganisatie** waarin het domein van de afzender niet is geconfigureerd als een geaccepteerd domein in uw Microsoft 365-organisatie.

Microsoft 365 kan deze berichten beperkt als we gegevens hebben om te bewijzen dat de bedoeling van deze berichten schadelijk is. Het is dus belangrijk dat u begrijpt wat er gebeurt en dat u het probleem kunt oplossen.

![Widget voor niet-geaccepteerd domein in het dashboard E-mailstroom in het & Compliancecentrum](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>Rapportweergave voor het rapport Niet-geaccepteerd domein

Als u op de grafiek klikt in de widget **Niet-geaccepteerd** domein, gaat u naar het rapport **Niet-geaccepteerd domein.**

Standaard wordt de activiteit voor alle betrokken verbindingslijnen weergegeven. Als u op **Gegevens tonen klikt,** kunt u een specifieke verbindingslijn selecteren in de vervolgkeuzepagina.

Als u de muisaanwijzer op een gegevenspunt (dag) in de grafiek beweegt, ziet u het totale aantal berichten voor de connector.

![Rapportweergave in het rapport Niet-geaccepteerd domein](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>Tabelweergave Details voor het rapport Niet-geaccepteerd domein

Als u in **een rapportweergave op Detailtabel** weergeven klikt, wordt de volgende informatie weergegeven:

- **Datum**
- **Naam van binnenkomende connector**
- **Afzenderdomein**
- **Aantal berichten**
- **Voorbeeldberichten:** de bericht-e-mailberichten van een steekproef van beïnvloede berichten.

Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**

Als u het rapport voor een bepaald datumbereik per e-mail wilt versturen naar een of meer geadresseerden, klikt u op **Downloaden aanvragen.**

Wanneer u een rij in de tabel selecteert, wordt een flyout met de volgende informatie weergegeven:

- **Datum**
- **Naam van binnenkomende connector**
- **Afzenderdomein**
- **Aantal berichten**
- **Voorbeeldberichten:** u kunt op **Voorbeeldberichten** weergeven klikken om de [resultaten](message-trace-scc.md) van bericht traceren voor een voorbeeld van de betreffende berichten te bekijken.

![Flyout Details na het selecteren van een rij in de tabelweergave Details in het rapport Niet-geaccepteerd domein](../../media/mfi-non-accepted-domain-report-details-flyout.png)

Als u wilt teruggaan naar de rapportweergave, klikt u **op Rapport weergeven.**

## <a name="related-topics"></a>Verwante onderwerpen

Voor informatie over andere inzichten in het dashboard voor de e-mailstroom, bekijkt u inzichten in de e-mailstroom in het & [compliancecentrum.](mail-flow-insights-v2.md)
