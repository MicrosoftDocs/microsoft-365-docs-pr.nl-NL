---
title: Inzichten in wachtrijen in het dashboard E-mailstroom
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Beheerders kunnen informatie vinden over het gebruik van de widget Wachtrijen in het dashboard E-mailstroom in het beveiligings- &-compliancecentrum om de niet-geslaagde e-mailstroom naar hun on-premises of partnerorganisaties te controleren via uitgaande connectors.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ca8ee5ea37fa5a63b8035572059e419c400d66f3
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289435"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>Inzichten in wachtrijen in het & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Wanneer berichten niet vanuit uw organisatie via connectors naar uw on-premises e-mailservers of partnerservers kunnen worden verzonden, worden de berichten in de wachtrij geplaatst in Microsoft 365. Veelvoorkomende voorbeelden die deze voorwaarde veroorzaken zijn:

- De verbindingslijn is onjuist geconfigureerd.
- Er zijn netwerk- of firewallwijzigingen geweest in uw on-premises omgeving.

Microsoft 365 blijft 24 uur lang proberen de bestelling af te leveren. Na 24 uur verlopen de berichten en worden ze geretourneerd aan de afzenders in niet-bezorgingsrapporten (ook wel NDR's of niet-bezorgdberichten genoemd).

Als het e-mailvolume in de wachtrij de vooraf gedefinieerde drempel overschrijdt (de standaardwaarde is 200 berichten), is de informatie beschikbaar op de volgende locaties:

- Het **inzicht in wachtrijen** in [het dashboard E-mailstroom](mail-flow-insights-v2.md) in het [& Compliancecentrum.](https://protection.office.com) Zie de sectie [Queues insight in the Mail flow dashboard in](#queues-insight-in-the-mail-flow-dashboard) this article (Inzichten in wachtrijen in het dashboard van de e-mailstroom in dit artikel) voor meer informatie.

- Er wordt een waarschuwing weergegeven in **recente waarschuwingen** op het dashboard Waarschuwingen in het [& Compliancecentrum](https://protection.office.com)  \> **(dashboard Waarschuwingen** of <https://protection.office.com/alertsdashboard> ).

  ![Recente waarschuwingen in het dashboard Waarschuwingen in het beveiligings- & compliancecentrum](../../media/mfi-queued-messages-alert.png)

- Beheerders ontvangen een e-mailmelding op basis van de configuratie van het standaardwaarschuwingsbeleid met de naam Berichten **is vertraagd.** Zie de volgende sectie als u de instellingen voor meldingen voor deze waarschuwing wilt configureren.

  Zie Waarschuwingsbeleid in het beveiligings- en compliancecentrum & voor meer [informatie over waarschuwingsbeleid.](../../compliance/alert-policies.md)

## <a name="customize-queue-alerts"></a>Wachtrijwaarschuwingen aanpassen

1. Ga in [het & Compliancecentrum](https://protection.office.com)naar **Waarschuwingsbeleid** \> **voor** waarschuwingen of <https://protection.office.com/alertpolicies> open.

2. Zoek en **selecteer op de** pagina Waarschuwingsbeleid het beleid met de naam Berichten is **vertraagd.**

3. In de **flyout Bericht is vertraagd** die wordt geopend, kunt u de waarschuwing in- of uitschakelen en de instellingen voor meldingen configureren.

   ![Berichten zijn vertraagd waarschuwingsbeleid details van het beveiligings- & compliancecentrum](../../media/mfi-queued-messages-alert-policy.png)

   - **Status:** u kunt de waarschuwing in- of uitschakelen.

   - **E-mailontvangers** en **de limiet voor dagelijkse meldingen:** klik op Bewerken **om** de volgende instellingen te configureren:

4. Als u de instellingen voor meldingen wilt configureren, klikt u op **Bewerken.** Configureer **de volgende instellingen** in de flyout Beleid bewerken die wordt weergegeven:

   - **E-mailmeldingen verzenden:** de standaardwaarde is ingeschakeld.
   - **E-mailontvangers:** De standaardwaarde is **TenantAdmins.**
   - **Dagelijkse meldingslimiet:** de standaardwaarde is **Geen limiet.**
   - **Drempelwaarde:** de standaardwaarde is 200.

   ![Meldingsinstellingen in het beleid voor meldingen zijn vertraagd met details van het beveiligings- & compliancecentrum](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. Klik op Opslaan en sluiten wanneer u **klaar** **bent.**

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>Inzichten in wachtrijen in het dashboard E-mailstroom

Zelfs als het bericht in de wachtrij de drempelwaarde niet heeft overschreden  en een waarschuwing heeft gegenereerd, kunt u het inzichten in Wachtrijen in het [dashboard](mail-flow-insights-v2.md) E-mailstroom nog steeds gebruiken om berichten te zien die langer dan een uur in de wachtrij staan en actie te ondernemen voordat het aantal in de wachtrij geplaatste berichten te groot wordt.

![Widget Wachtrijen in het dashboard E-mailstroom in het & Compliancecentrum](../../media/mfi-queues-widget.png)

Als u op het aantal berichten in de widget klikt, wordt een **flyout** Berichten in de wachtrij met de volgende informatie weergegeven:

- **Aantal berichten in wachtrij**
- **Connectornaam:** klik op de naam van de connector om de connector te beheren in het Exchange-beheercentrum (EAC).
- **Wachttijd**
- **Oudste berichten verlopen**
- **Doelserver**
- **Laatste IP-adres**
- **Laatste fout**
- **Oplossing: er** zijn veelvoorkomende problemen en oplossingen beschikbaar. Als de koppeling **Nu oplossen beschikbaar** is, klikt u erop om het probleem op te lossen. Klik anders op beschikbare koppelingen voor meer informatie over de fout en mogelijke oplossingen.

![Details na klikken op Het inzichten in wachtrijen in het dashboard E-mailstroom](../../media/mfi-queues-details.png)

Dezelfde flyout wordt weergegeven nadat u op Wachtrij weergeven **hebt** geklikt in de details van een waarschuwing die **is vertraagd.**

![Details van vertraagde meldingen zijn vertraagd in het beveiligings- & compliancecentrum](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a>Zie ook

Zie inzichten in de e-mailstroom in het beveiligings- en compliancecentrum voor meer informatie & [inzichten in het dashboard E-mailstroom.](mail-flow-insights-v2.md)
