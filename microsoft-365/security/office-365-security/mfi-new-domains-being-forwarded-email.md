---
title: Inzicht in nieuwe domeinen waarnaar e-mails worden doorgestuurd
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Beheerders kunnen inzicht krijgen in de manier waarop u via de nieuwe domeinen e-mail informatie in het compliance-Dash & Board kunt gebruiken om te onderzoeken wanneer hun gebruikers berichten doorsturen naar externe domeinen waarnaar nooit is doorgestuurd.
ms.openlocfilehash: a72ffd001ea22972d9dc6c00af8a4dd7881386b7
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356941"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Nieuwe domeinen worden doorgestuurd via e-mail inzicht in de beveiligings & nalevings centrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Er zijn geldige zakelijke redenen voor het doorsturen van e-mailberichten naar externe geadresseerden in bepaalde domeinen. Het is echter ook verdacht Wanneer gebruikers in uw organisatie zich op een plotselinge plaats van berichten naar een domein kunnen doorsturen, ongeacht waar niemand in uw organisatie ooit berichten heeft doorgestuurd naar (een nieuw domein).

Dit kan betekenen dat de gebruikersaccounts zijn aangetast. Als u vermoedt dat de accounts zijn aangetast, raadpleegt u [reageren op een gemanipuleerd e-mailaccount](responding-to-a-compromised-email-account.md).

De **nieuwe domeinen waarnaar e-mail inzicht wordt doorgestuurd** in de [beveiliging & nalevings centrum](https://protection.office.com) u ontvangt een melding wanneer gebruikers in uw organisatie berichten doorsturen naar nieuwe domeinen.

Dit inzicht wordt alleen weergegeven als het probleem zich voordoet, en wordt weergegeven op de pagina voor het [doorsturen van rapporten](view-mail-flow-reports.md#forwarding-report) .

![Inzicht in nieuwe domeinen waarnaar e-mails worden doorgestuurd](../../media/mfi-new-domains-being-forwarded.png)

Wanneer u op de widget klikt, verschijnt er een flyout waar u meer informatie kunt vinden over de doorgestuurde berichten, waaronder een koppeling terug naar het [doorstuur rapport](view-mail-flow-reports.md#forwarding-report).

![Info-menu dat wordt weergegeven nadat u op de nieuwe domeinen wordt doorgestuurd](../../media/mfi-new-domains-being-forwarded-details.png)

U kunt deze detailpagina ook raadplegen wanneer u het inzicht selecteert nadat u op **AllesWeergeven** hebt geklikt in het gebied **belangrijkste inzichten &** gebied voor aanbevelingen (**Reports** \> **Dashboard** rapporten of <https://protection.office.com/insightdashboard> ).

Configureer een extern domein voor sommige of alle externe domeinen om te voorkomen dat u automatische doorstuur berichten doorschakelt naar externe domeinen. Zie [externe domeinen beheren in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)voor meer informatie.

## <a name="related-topics"></a>Verwante onderwerpen

Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).
