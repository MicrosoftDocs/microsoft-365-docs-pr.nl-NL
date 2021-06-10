---
title: Inzicht in nieuwe domeinen waarnaar e-mails worden doorgestuurd
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Beheerders kunnen leren hoe ze het inzicht van de nieuwe domeinen die per e-mail worden doorgestuurd, kunnen gebruiken in het e-mailstroomdashboard in het beveiligings- & compliancecentrum om te onderzoeken wanneer hun gebruikers berichten doorsturen naar externe domeinen die nog nooit zijn doorgestuurd naar.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2f3a5f125a045176f152ccd079ebe7f7e40bc39f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204039"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Nieuwe domeinen die inzicht krijgen in e-mail doorgestuurd in het Beveiligings- & Compliance center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Er zijn geldige zakelijke redenen om e-mailberichten door te sturen naar externe geadresseerden in specifieke domeinen. Het is echter verdacht wanneer gebruikers in uw organisatie plotseling berichten doorsturen naar een domein waar niemand in uw organisatie ooit berichten heeft doorgestuurd naar (een nieuw domein).

Deze voorwaarde kan aangeven dat de gebruikersaccounts zijn gehackt. Zie Reageren op een gekromd [e-mailaccount](responding-to-a-compromised-email-account.md)als u vermoedt dat de accounts zijn gehackt.

De **nieuwe domeinen die e-mailinzicht** worden doorgestuurd in het beveiligings- & [compliancecentrum,](https://protection.office.com) worden u op de hoogte gehouden wanneer gebruikers in uw organisatie berichten doorsturen naar nieuwe domeinen.

Dit inzicht wordt alleen weergegeven wanneer het probleem wordt gedetecteerd en wordt weergegeven op de pagina [Rapport](view-mail-flow-reports.md#forwarding-report) doorsturen.

![Inzicht in nieuwe domeinen waarnaar e-mails worden doorgestuurd](../../media/mfi-new-domains-being-forwarded.png)

Wanneer u op de widget klikt, wordt er een flyout weergegeven waar u meer informatie over de doorgestuurde berichten kunt vinden, waaronder een koppeling naar [het rapport Doorsturen.](view-mail-flow-reports.md#forwarding-report)

![Details flyout that appears after clicking on the New domains being forwarded email insight (Details flyout that appears after clicking on the New domains being forwarded email insight](../../media/mfi-new-domains-being-forwarded-details.png)

U kunt ook naar deze detailspagina gaan wanneer u het inzicht selecteert nadat u op Alles weergeven hebt geklikt **in** het gebied Top **insights & aanbevelingen** op ( \> **Rapportendashboard** of <https://protection.office.com/insightdashboard> ).

Als u wilt voorkomen dat berichten automatisch worden doorgestuurd naar externe domeinen, configureert u een extern domein voor sommige of alle externe domeinen. Zie Externe domeinen beheren in Exchange Online voor [meer Exchange Online.](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)

## <a name="related-topics"></a>Verwante onderwerpen

Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)