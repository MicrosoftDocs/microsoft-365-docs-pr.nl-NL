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
description: Beheerders kunnen in het beveiligings- &-compliancecentrum leren hoe ze het inzicht in e-mail doorsturen nieuwe gebruikers kunnen gebruiken om te onderzoeken wanneer gebruikers in hun organisatie berichten naar nieuwe domeinen doorsturen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7b86d726979991a55e7d4e43bf3581a4a664ee4f
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150253"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>Informatie over het doorsturen van e-mail door nieuwe gebruikers in het & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender voor Office 365-abonnement 1 en abonnement 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Het is verdacht als nieuwe gebruikersaccounts in uw organisatie plotseling beginnen met het doorsturen van e-mailberichten naar externe domeinen.

De **nieuwe domeinen die** e-mailinzichten worden doorgestuurd in het [beveiligings- &-compliancecentrum](https://protection.office.com) melden u wanneer nieuwe gebruikers in uw organisatie berichten naar externe domeinen doorsturen. Deze voorwaarde kan aangeven dat gekromde beheerdersaccounts zijn gebruikt om de nieuwe gebruikers te maken. Als u vermoedt dat de accounts zijn gehackt, bekijkt u Hoe u [reageert op een gekromd e-mailaccount.](responding-to-a-compromised-email-account.md)

Dit inzicht wordt alleen weergegeven wanneer het probleem is gedetecteerd en wordt weergegeven op de [pagina Doorsturen-rapport.](view-mail-flow-reports.md#forwarding-report)

![Inzicht in nieuwe gebruikers die e-mails doorsturen](../../media/mfi-new-users-forwarding-email.png)

Wanneer u op de widget klikt, wordt er een flyout weergegeven waar u meer [](#forwarding-modifications-report) informatie over de doorgestuurde berichten kunt vinden, inclusief een koppeling naar het rapport met doorgestuurde wijzigingen, zoals verder wordt beschreven in dit artikel.

![Flyout details die wordt weergegeven nadat u op het inzicht van e-mail doorsturen van Nieuwe gebruikers hebt geklikt](../../media/mfi-new-users-forwarding-email-details.png)

U komt ook op deze detailpagina wanneer u het inzicht selecteert nadat u op Alles weergeven **hebt** geklikt in het gebied topinzichten **&** gebied met aanbevelingen op (**Dashboard** Rapporten of \>  <https://protection.office.com/insightdashboard> ).

U kunt klikken op de koppeling Rapport **bekijken dat** is gekoppeld aan de koppeling Inzichten om naar het rapport Doorsturen-wijzigingen **te** gaan, zoals wordt beschreven in de volgende sectie.

## <a name="forwarding-modifications-report"></a>Forwarding modifications report

Het **rapport Met doorgestuurde wijzigingen bevat** informatie over berichten die automatisch worden doorgestuurd van afzenders in uw organisatie:

- Nieuw gemaakte accounts die berichten doorsturen naar externe domeinen.
- Accounts die berichten doorsturen naar externe domeinen die nooit zijn doorgestuurd door andere afzenders in uw organisatie.

Deze typen doorgestuurde berichten kunnen een beveiligings- of nalevingsrisico vormen, wat kan duiden op gekromde accounts.

Het rapport bevat gegevens voor maximaal 90 dagen. Standaard worden in het rapport gegevens van de afgelopen zeven dagen weergegeven.

Dit rapport is niet rechtstreeks beschikbaar in het [dashboard e-mailstroom](mail-flow-insights-v2.md) of in het [dashboard Rapporten.](view-mail-flow-reports.md) Naast het klikken op het rapport Bekijken  dat is gekoppeld aan **de koppeling** Inzicht in het inzicht van Nieuwe gebruikers voor het doorsturen van e-mail, gaat u naar het rapport door:

- Klik op de **koppeling rapport over doorsturen meldingen** in de details van de nieuwe domeinen die [e-mailinzicht worden doorgestuurd.](mfi-new-domains-being-forwarded-email.md)
- <https://protection.office.com/reportv2?id=MailFlowNewForwarding>Openen.

### <a name="report-view-for-the-forwarding-modifications-report"></a>Rapportweergave voor het rapport Met doorsturen

De volgende grafieken zijn beschikbaar in de rapportweergave:

- **Gegevens tonen voor: Nieuwe doorsturende gebruikers:**

  ![Weergave Nieuwe doorsturende gebruikers in het rapport Wijzigingen doorsturen](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **Gegevens tonen voor: Nieuwe doorsturen-domeinen:**

  ![Weergave Nieuwe doorgestuurde domeinen in het rapport Met doorsturen](../../media/forwarding-modifications-report-new-forwarded-domains.png)

Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>Detailtabelweergave voor het rapport Doorsturen van wijzigingen

Als u op **de tabel Details weergeven klikt,** is de informatie die wordt weergegeven afhankelijk van de grafiek die u bekijkt:

- **Gegevens tonen voor: Nieuwe doorsturende gebruikers:**

  - **Naam:** het e-mailadres van de afzender.
  - **Type doorsturen**
  - **Adres van geadresseerde**
  - **Details**
  - **Aantal**
  - **First forward date**

- **Gegevens tonen voor: Nieuwe doorsturen-domeinen:**

  - **Naam:** het e-maildomein van de afzender.
  - **Type doorsturen**
  - **Adres van geadresseerde**
  - **Details**
  - **Aantal**
  - **First forward date**

Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**

Als u een rij in de tabel selecteert, wordt een flyout **Details** weergegeven met de volgende informatie:

- **Naam:** dit is het e-mailadres van de afzender (van Weergave Gegevens weergeven **voor:** Weergave Nieuwe doorgestuurde gebruikers) of het e-maildomein van de afzender (van de weergave Gegevens weergeven **voor:** Nieuwe doorsturende domeinen).
- **Type doorsturen**
- **Ontvanger**
- **Details**
- **Aantal**
- **Begindatum**
- **Aanbeveling:** vanaf hier kunt u op de koppeling klikken om de gebruiker te beheren in het Microsoft 365-beheercentrum.

![Flyout Details uit de detailtabel van de weergave Nieuwe gebruikers voor doorsturen in het rapport Wijzigingen doorsturen](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

Als u wilt teruggaan naar de rapportweergave, klikt u **op Rapport weergeven.**

## <a name="related-topics"></a>Verwante onderwerpen

Voor informatie over andere inzichten in het dashboard voor de e-mailstroom, bekijkt u inzichten in de e-mailstroom in het & [compliancecentrum.](mail-flow-insights-v2.md)
