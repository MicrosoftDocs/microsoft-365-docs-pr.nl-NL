---
title: Inzicht in nieuwe gebruikers die e-mails doorsturen
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Beheerders kunnen leren hoe ze het inzicht van nieuwe gebruikers voor het doorsturen van e-mail in het beveiligings- & compliancecentrum kunnen gebruiken om te onderzoeken wanneer gebruikers in hun organisatie berichten doorsturen naar nieuwe domeinen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 807df82ca80e851554db7b8f373a5ca4af02a391
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204489"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>Nieuwe gebruikers die inzicht in e-mail doorsturen in het beveiligings- & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Het is verdacht wanneer nieuwe gebruikersaccounts in uw organisatie plotseling e-mailberichten doorsturen naar externe domeinen.

De **nieuwe domeinen die** e-mailinzicht worden doorgestuurd in het beveiligings- & [compliancecentrum,](https://protection.office.com) worden u op de hoogte gehouden wanneer nieuwe gebruikers in uw organisatie berichten doorsturen naar externe domeinen. Deze voorwaarde kan aangeven dat gecompromitteerde beheerdersaccounts zijn gebruikt om de nieuwe gebruikers te maken. Zie Reageren op een gekromd [e-mailaccount](responding-to-a-compromised-email-account.md)als u vermoedt dat de accounts zijn gehackt.

Dit inzicht wordt alleen weergegeven wanneer het probleem wordt gedetecteerd en wordt weergegeven op de pagina [Rapport](view-mail-flow-reports.md#forwarding-report) doorsturen.

![Inzicht in nieuwe gebruikers die e-mails doorsturen](../../media/mfi-new-users-forwarding-email.png)

Wanneer u op de widget klikt, wordt er een flyout weergegeven waar u meer [](#forwarding-modifications-report) informatie over de doorgestuurde berichten kunt vinden, waaronder een koppeling naar het rapport Wijzigingen doorsturen, zoals verder wordt beschreven in dit artikel.

![Details flyout die wordt weergegeven nadat u hebt geklikt op het inzicht van nieuwe gebruikers voor het doorsturen van e-mail](../../media/mfi-new-users-forwarding-email-details.png)

U kunt ook naar deze detailspagina gaan wanneer u het inzicht selecteert nadat u op Alles weergeven hebt geklikt **in** het gebied Top **insights & aanbevelingen** op ( \> **Rapportendashboard** of <https://protection.office.com/insightdashboard> ).

U kunt op de **koppeling Rapport zien dat is** gekoppeld aan inzicht klikken om naar het rapport Wijzigingen doorsturen te gaan, zoals beschreven in de volgende sectie. 

## <a name="forwarding-modifications-report"></a>Rapport Wijzigingen doorsturen

Het **rapport Wijzigingen doorsturen bevat** details over berichten die automatisch worden doorgestuurd van afzenders in uw organisatie:

- Nieuw gemaakte accounts die berichten doorsturen naar externe domeinen.
- Accounts die berichten doorsturen naar externe domeinen die nooit zijn doorgestuurd naar andere afzenders in uw organisatie.

Deze typen doorgestuurde berichten kunnen een beveiligings- of compliancerisico opleveren, en kunnen gecompromitteerde accounts aangeven.

Het rapport bevat gegevens voor maximaal 90 dagen. Standaard worden in het rapport gegevens van de afgelopen 7 dagen weergegeven.

Dit rapport is niet rechtstreeks beschikbaar in het [e-mailstroomdashboard](mail-flow-insights-v2.md) of in het [dashboard Rapporten.](view-mail-flow-reports.md) Naast het klikken op de koppeling Rapport  bekijken **die is** gekoppeld aan de koppeling Inzicht in het inzicht van nieuwe gebruikers voor het doorsturen van e-mail, gaat u naar het rapport door:

- Klik op de **koppeling Meldingen doorsturen** in de details van de nieuwe domeinen die per e-mail [worden doorgestuurd.](mfi-new-domains-being-forwarded-email.md)
- Openen <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .

### <a name="report-view-for-the-forwarding-modifications-report"></a>Rapportweergave voor het rapport Wijzigingen doorsturen

De volgende grafieken zijn beschikbaar in de rapportweergave:

- **Gegevens voor: Nieuwe doorsturende gebruikers:**

  ![Weergave Nieuwe doorsturende gebruikers in het rapport Wijzigingen doorsturen](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **Gegevens voor: Nieuwe doorsturende domeinen:**

  ![Weergave Nieuwe doorgestuurde domeinen in het rapport Wijzigingen doorsturen](../../media/forwarding-modifications-report-new-forwarded-domains.png)

Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>Tabelweergave details voor het rapport Wijzigingen doorsturen

Als u op **Detailstabel weergeven klikt,** is de weergegeven informatie afhankelijk van de grafiek die u hebt bekeken:

- **Gegevens voor: Nieuwe doorsturende gebruikers:**

  - **Naam:** Het e-mailadres van de afzender.
  - **Type doorsturen**
  - **Adres van geadresseerde**
  - **Details**
  - **Aantal**
  - **Eerste doorgestuurde datum**

- **Gegevens voor: Nieuwe doorsturende domeinen:**

  - **Naam:** Het e-maildomein van de afzender.
  - **Type doorsturen**
  - **Adres van geadresseerde**
  - **Details**
  - **Aantal**
  - **Eerste doorgestuurde datum**

Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**

Als u een rij in de tabel selecteert, wordt een fly-out **Details** weergegeven met de volgende informatie:

- **Naam:** Dit is het e-mailadres van de afzender (van Gegevens weergeven **voor:** weergave Nieuwe doorsturende gebruikers) of het e-maildomein van de afzender (van Gegevens weergeven **voor:** Weergave Nieuwe doorsturende domeinen).
- **Type doorsturen**
- **Ontvanger**
- **Details**
- **Aantal**
- **Begindatum**
- **Aanbeveling:** Vanaf hier kunt u op de koppeling klikken om de gebruiker te beheren in het Microsoft 365-beheercentrum.

![Details flyout from the details table of the New forwarding users view in the Forwarding modifications report](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**

## <a name="related-topics"></a>Verwante onderwerpen

Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)
