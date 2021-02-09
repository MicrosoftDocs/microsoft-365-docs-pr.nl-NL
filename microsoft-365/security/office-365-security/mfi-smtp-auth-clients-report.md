---
title: Inzichten en rapporten van SMTP-auth-clients in het dashboard van de e-mailstroom
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
description: Beheerders kunnen informatie krijgen over het gebruik van het inzicht smtp-verificatie in het dashboard E-mailstroom in het beveiligings- &-compliancecentrum om e-mail afzenders in hun organisatie te controleren die gebruikmaken van geverifieerde SMTP -verificatie (SMTP AUTH) om e-mailberichten te verzenden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3476ee2f9388245fb105a0910fa7b7d11ec3aeee
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150241"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>Inzichten en rapportage van SMTP-auth-clients in het beveiligings- & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender voor Office 365-abonnement 1 en abonnement 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Het inzicht van **SMTP Auth-clients** in het dashboard voor de [e-mailstroom](mail-flow-insights-v2.md) en het bijbehorende rapport [SMTP Auth-clients](#smtp-auth-clients-report) in het [beveiligings- & Compliancecentrum](https://protection.office.com) belicht het gebruik van het SMTP AUTH-clientverzendingsprotocol door gebruikers of systeemaccounts in uw organisatie. Dit oude protocol (dat gebruikmaakt van het eindpunt smtp.office365.com) biedt alleen basisverificatie en is gevoelig voor gebruik door gekromde accounts voor het verzenden van e-mail. Met het inzicht en rapport kunt u controleren op ongebruikelijke activiteiten voor SMTP AUTH-e-mailinzending. Hier worden ook de gebruiksgegevens van TLS voor clients of apparaten met SMTP-AUTH gebruikt.

De widget geeft het aantal gebruikers of serviceaccounts aan dat de afgelopen zeven dagen het SMTP-auth-protocol heeft gebruikt.

![Widget SMTP-auth-clients in het dashboard E-mailstroom in het & Compliancecentrum](../../media/mfi-smtp-auth-clients-report-widget.png)

Als u op het aantal berichten in de widget klikt, wordt een flyout voor **SMTP-auth-clients** weergegeven. De flyout biedt een samengevoegde weergave van het TLS-gebruik en de volumes van de afgelopen week.

![Flyout details na klikken op de widget SMTP Auth clients in the Mail flow dashboard](../../media/mfi-smtp-auth-clients-report-details.png)

U kunt klikken op de koppeling voor het **rapport SMTP-auth-clients** om naar het rapport SMTP-auth-clients te gaan, zoals wordt beschreven in de volgende sectie.

## <a name="smtp-auth-clients-report"></a>SMTP-verificatierapport voor clients

### <a name="report-view-for-the-smtp-auth-clients-report"></a>Rapportweergave voor het rapport SMTP-auth-clients

Standaard worden in het rapport gegevens van de afgelopen zeven dagen weergegeven, maar de gegevens zijn beschikbaar voor de afgelopen 90 dagen.

De sectie Overzicht bevat de volgende grafieken:

- Gegevens weergeven **op: Volume verzenden:** In de grafiek ziet u standaard het aantal SMTP Auth-clientberichten dat is verzonden vanuit alle domeinen ( Gegevens weergeven **voor:** Alle afzenderdomeinen is standaard geselecteerd). U kunt de resultaten filteren op een  specifiek afzenderdomein door te klikken op Gegevens tonen voor en het domein van de afzender te selecteren in de vervolgkeuzelijst. Als u een specifiek gegevenspunt (dag) aanwijzert, wordt het aantal berichten weergegeven.

  ![Volumeweergave verzenden in het rapport SMTP-auth-clients in het & compliancecentrum](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- **Gegevens weergeven met: TLS-gebruik:** in de grafiek ziet u het percentage TLS-gebruik voor alle berichten van de SMTP-auth-client in de geselecteerde periode. In deze grafiek kunt u gebruikers en systeemaccounts identificeren en actie ondernemen die nog steeds oudere versies van TLS gebruiken.

  ![Weergave TLS-gebruik in het rapport SMTP-auth-clients in het & compliancecentrum](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**

Klik **op Rapport aanvragen** om een gedetailleerdere versie van het rapport in een e-mailbericht te ontvangen. U kunt het datumbereik opgeven en de geadresseerden die het rapport moeten ontvangen.

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>Tabelweergave Details voor het rapport SMTP-auth-clients

Als u op **de tabel Details weergeven klikt,** is de informatie die wordt weergegeven afhankelijk van de grafiek die u bekijkt:

- **Gegevens weergeven met: Volume verzenden:** de volgende informatie wordt weergegeven in een tabel:

  - **Adres afzender**
  - **Aantal berichten**

  Als u een rij selecteert, worden dezelfde details weergegeven in een flyout.

- **Gegevens weergeven met: TLS-gebruik:** de volgende informatie wordt weergegeven in een tabel:

  - **Adres afzender**
  - **TLS1.0%**<sup>\*</sup>
  - **TLS1.1%**<sup>\*</sup>
  - **TLS1.2%**<sup>\*</sup>
  - **Aantal berichten**

  <sup>\*</sup> In deze kolom ziet u zowel het percentage als het aantal berichten van de afzender.

Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**

Als u een rij selecteert, worden soortgelijke details weergegeven in een flyout:

![Flyout Details uit de detailtabel van de weergave TLS-gebruik in het rapport SMTP Auth-clients](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

Klik **op Rapport aanvragen** om een gedetailleerdere versie van het rapport in een e-mailbericht te ontvangen. U kunt het datumbereik opgeven en de geadresseerden die het rapport moeten ontvangen.

Als u wilt teruggaan naar de rapportweergave, klikt u **op Rapport weergeven.**

## <a name="related-topics"></a>Verwante onderwerpen

Zie inzichten in de e-mailstroom in het beveiligings- en compliancecentrum voor meer informatie & [inzichten in het dashboard E-mailstroom.](mail-flow-insights-v2.md)
