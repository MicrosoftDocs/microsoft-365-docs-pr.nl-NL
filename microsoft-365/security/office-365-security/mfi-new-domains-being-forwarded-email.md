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
description: Beheerders kunnen in het dashboard E-mailstroom in het beveiligings- &-compliancecentrum informatie vinden over het gebruik van de nieuwe domeinen die e-mailinzichten worden doorgestuurd om te onderzoeken wanneer gebruikers berichten doorsturen naar externe domeinen die nooit zijn doorgestuurd.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a4429f1657861091082fdfaedb52c85cec3a0cc1
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150597"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Nieuwe domeinen die e-mailinzichten worden doorgestuurd in het beveiligings- & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender voor Office 365-abonnement 1 en abonnement 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Er zijn geldige zakelijke redenen om e-mailberichten door te sturen naar externe geadresseerden in bepaalde domeinen. Het is echter verdacht als gebruikers in uw organisatie plotseling beginnen met het doorsturen van berichten naar een domein waar niemand in uw organisatie ooit berichten naar heeft doorgestuurd (een nieuw domein).

Deze voorwaarde kan aangeven dat de gebruikersaccounts zijn gehackt. Als u vermoedt dat de accounts zijn gehackt, bekijkt u Hoe u [reageert op een gekromd e-mailaccount.](responding-to-a-compromised-email-account.md)

De **nieuwe domeinen die e-mailinzichten** worden doorgestuurd in het [beveiligings- & compliancecentrum](https://protection.office.com) melden u wanneer gebruikers in uw organisatie berichten naar nieuwe domeinen doorsturen.

Dit inzicht wordt alleen weergegeven wanneer het probleem is gedetecteerd en wordt weergegeven op de [pagina Doorsturen-rapport.](view-mail-flow-reports.md#forwarding-report)

![Inzicht in nieuwe domeinen waarnaar e-mails worden doorgestuurd](../../media/mfi-new-domains-being-forwarded.png)

Wanneer u op de widget klikt, wordt er een flyout weergegeven waar u meer informatie over de doorgestuurde berichten kunt vinden, inclusief een koppeling naar het [rapport Doorsturen.](view-mail-flow-reports.md#forwarding-report)

![Flyout details die wordt weergegeven nadat u op de nieuwe domeinen hebt geklikt die e-mailinzicht worden doorgestuurd](../../media/mfi-new-domains-being-forwarded-details.png)

U komt ook op deze detailpagina wanneer u het inzicht selecteert nadat u op Alles weergeven **hebt** geklikt in het gebied topinzichten **&** gebied met aanbevelingen op (**Dashboard** Rapporten of \>  <https://protection.office.com/insightdashboard> ).

Als u wilt voorkomen dat berichten automatisch worden doorgestuurd naar externe domeinen, configureert u een extern domein voor bepaalde of alle externe domeinen. Zie Externe domeinen beheren [in Exchange Online voor meer informatie.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)

## <a name="related-topics"></a>Verwante onderwerpen

Voor informatie over andere inzichten in het dashboard voor de e-mailstroom, bekijkt u inzichten in de e-mailstroom in het & [compliancecentrum.](mail-flow-insights-v2.md)
