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
description: Beheerders kunnen in het dashboard E-mailstroom in het beveiligings- &-compliancecentrum informatie vinden over het gebruik van de nieuwe domeinen die e-mailinzichten worden doorgestuurd om te onderzoeken wanneer hun gebruikers berichten doorsturen naar externe domeinen die nooit zijn doorgestuurd.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fd026b31b7cb678ff1f091579c67a3958b159c09
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289459"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Nieuwe domeinen die e-mailinzichten worden doorgestuurd in het beveiligings- & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Er zijn geldige zakelijke redenen om e-mailberichten door te sturen naar externe geadresseerden in bepaalde domeinen. Het is echter verdacht als gebruikers in uw organisatie plotseling beginnen met het doorsturen van berichten naar een domein waar niemand in uw organisatie ooit berichten naar heeft doorgestuurd (een nieuw domein).

Deze voorwaarde kan aangeven dat de gebruikersaccounts zijn gehackt. Als u vermoedt dat de accounts zijn gehackt, bekijkt u Hoe u [reageert op een gekromd e-mailaccount.](responding-to-a-compromised-email-account.md)

De **nieuwe domeinen die e-mailinzichten** worden doorgestuurd in het [beveiligings- & compliancecentrum](https://protection.office.com) melden u wanneer gebruikers in uw organisatie berichten doorsturen naar nieuwe domeinen.

Dit inzicht wordt alleen weergegeven wanneer het probleem is gedetecteerd en wordt weergegeven op de [pagina Doorsturen-rapport.](view-mail-flow-reports.md#forwarding-report)

![Inzicht in nieuwe domeinen waarnaar e-mails worden doorgestuurd](../../media/mfi-new-domains-being-forwarded.png)

Wanneer u op de widget klikt, wordt er een flyout weergegeven waar u meer informatie over de doorgestuurde berichten kunt vinden, inclusief een koppeling naar het [rapport Doorsturen.](view-mail-flow-reports.md#forwarding-report)

![Flyout details die wordt weergegeven nadat u op de nieuwe domeinen hebt geklikt die e-mailinzicht worden doorgestuurd](../../media/mfi-new-domains-being-forwarded-details.png)

U komt ook op deze detailpagina wanneer u het inzicht selecteert nadat u op Alles weergeven **hebt** geklikt in het gebied topinzichten **&** gebied met aanbevelingen op (**Dashboard** Rapporten of \>  <https://protection.office.com/insightdashboard> ).

Als u wilt voorkomen dat berichten automatisch worden doorgestuurd naar externe domeinen, configureert u een extern domein voor bepaalde of alle externe domeinen. Zie Externe domeinen beheren [in Exchange Online voor meer informatie.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)

## <a name="related-topics"></a>Verwante onderwerpen

Zie inzichten in de e-mailstroom in het beveiligings- en compliancecentrum voor meer informatie & [inzichten in het dashboard E-mailstroom.](mail-flow-insights-v2.md)
