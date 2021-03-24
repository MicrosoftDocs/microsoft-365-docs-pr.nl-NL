---
title: Inzicht en rapport van SMTP Auth-clients in het e-mailstroomdashboard
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
description: Beheerders kunnen leren hoe ze het SMTP Auth-inzicht en rapport kunnen gebruiken in het dashboard E-mailstroom in het beveiligings- & compliancecentrum om e-mail afzenders in hun organisatie te controleren die geverifieerde SMTP (SMTP AUTH) gebruiken om e-mailberichten te verzenden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a979f0e80fc303868bf2572974563323035fc4bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057250"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>Inzicht en rapport van SMTP Auth-clients in het Beveiligings- & Compliance center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

De **SMTP Auth-clients** in het [dashboard Mail flow](mail-flow-insights-v2.md) en het bijbehorende RAPPORT [SMTP Auth-clients](#smtp-auth-clients-report) in het [Beveiligings- & Compliancecentrum](https://protection.office.com) markeren het gebruik van het SMTP AUTH-clientverzendingsprotocol door gebruikers of systeemaccounts in uw organisatie. Dit oudere protocol (dat gebruikmaakt van het eindpunt smtp.office365.com) biedt alleen basisverificatie en is vatbaar voor gebruik door gecompromitteerde accounts om e-mail te verzenden. Met het inzicht en rapport kunt u controleren op ongebruikelijke activiteiten voor SMTP AUTH-e-mailinzendingen. Hier worden ook de TLS-gebruiksgegevens voor clients of apparaten met SMTP AUTH.

De widget geeft het aantal gebruikers of serviceaccounts aan dat de afgelopen 7 dagen het SMTP Auth-protocol heeft gebruikt.

![SMTP Auth-clients widget in het e-mailstroomdashboard in & Compliance center](../../media/mfi-smtp-auth-clients-report-widget.png)

Als u op het aantal berichten in de widget klikt, wordt er een flyout voor **SMTP Auth-clients** weergegeven. De flyout biedt een samengevoegde weergave van het TLS-gebruik en de volumes van de afgelopen week.

![Details flyout after clicking on the SMTP Auth clients widget in the Mail flow dashboard](../../media/mfi-smtp-auth-clients-report-details.png)

U kunt op de **koppeling SMTP Auth-clientsrapport** klikken om naar het rapport SMTP Auth-clients te gaan, zoals wordt beschreven in de volgende sectie.

## <a name="smtp-auth-clients-report"></a>SMTP-verificatierapport voor clients

### <a name="report-view-for-the-smtp-auth-clients-report"></a>Rapportweergave voor het rapport SMTP Auth-clients

Standaard worden in het rapport gegevens van de afgelopen 7 dagen weergegeven, maar gegevens zijn beschikbaar voor de afgelopen 90 dagen.

De overzichtssectie bevat de volgende grafieken:

- **Gegevens weergeven door:** Volume verzenden: Standaard wordt in de grafiek het aantal SMTP Auth-clientberichten weergegeven dat vanuit alle domeinen is verzonden ( Gegevens weergeven **voor:** Alle afzenderdomeinen is standaard geselecteerd). U kunt de resultaten filteren op een specifiek afzenderdomein door te klikken op **Gegevens** voor en het afzenderdomein in de vervolgkeuzelijst te selecteren. Als u een bepaald gegevenspunt (dag) met de muisaanwijzer beweegt, wordt het aantal berichten weergegeven.

  ![Volumeweergave verzenden in het rapport SMTP Auth-clients in het beveiligings- & compliancecentrum](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- **Gegevens weergeven op: TLS-gebruik:** In de grafiek ziet u het percentage TLS-gebruik voor alle SMTP Auth-clientberichten gedurende de geselecteerde periode. Met deze grafiek kunt u gebruikers en systeemaccounts identificeren en actie ondernemen die nog steeds oudere versies van TLS gebruiken.

  ![TLS-gebruiksweergave in het rapport SMTP Auth-clients in het beveiligings- & Compliancecentrum](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**

Klik **op Rapport aanvragen** om een gedetailleerdere versie van het rapport in een e-mailbericht te ontvangen. U kunt het datumbereik en de geadresseerden opgeven om het rapport te ontvangen.

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>Tabelweergave details voor het rapport SMTP Auth-clients

Als u op **Detailstabel weergeven klikt,** is de weergegeven informatie afhankelijk van de grafiek die u hebt bekeken:

- **Gegevens weergeven door: Volume verzenden:** De volgende gegevens worden weergegeven in een tabel:

  - **Adres afzender**
  - **Aantal berichten**

  Als u een rij selecteert, worden dezelfde details weergegeven in een flyout.

- **Gegevens weergeven op: TLS-gebruik:** De volgende gegevens worden weergegeven in een tabel:

  - **Adres afzender**
  - **TLS1,0%**<sup>\*</sup>
  - **TLS1,1%**<sup>\*</sup>
  - **TLS1,2%**<sup>\*</sup>
  - **Aantal berichten**

  <sup>\*</sup> In deze kolom ziet u het percentage en het aantal berichten van de afzender.

Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**

Als u een rij selecteert, worden soortgelijke details weergegeven in een flyout:

![Details flyout from the details table of the TLS usage view in the SMTP Auth clients report](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

Klik **op Rapport aanvragen** om een gedetailleerdere versie van het rapport in een e-mailbericht te ontvangen. U kunt het datumbereik en de geadresseerden opgeven om het rapport te ontvangen.

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**

## <a name="related-topics"></a>Verwante onderwerpen

Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)
