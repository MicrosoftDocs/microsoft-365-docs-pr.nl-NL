---
title: SMTP Auth-clients rapporteren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Beheerders kunnen meer te weten komen over het rapport SMTP Auth-clients in het dashboard van de e-mailstroom in het Security & Compliance Center.
ms.openlocfilehash: e80ee36fd7e94cc4dc2791f71ae594f0182b4269
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812788"
---
# <a name="smtp-auth-clients-report"></a>SMTP Auth-clients rapporteren

In het rapport **SMTP Auth-clients** wordt het gebruik van het SMTP Auth-clientindieningsprotocol door gebruikers of systeemaccounts in uw organisatie benadrukt. Dit verouderde protocol (dat het eindpunt smtp.office365.com) biedt alleen basisverificatie en is gevoelig voor gebruik door gecompromitteerde accounts om e-mail te verzenden.  Met dit rapport u controleren op ongebruikelijke activiteit. Het toont ook de TLS-gebruiksgegevens voor clients of apparaten die SMTP Auth gebruiken.

De widget die wordt weergegeven in het dashboard Mail Flow geeft het aantal gebruikers of serviceaccounts aan dat het SMTP Auth-protocol in de afgelopen 7 dagen heeft gebruikt.

![Het SMTP Auth-clients rapporteren in het dashboard van de e-mailstroom in het Security & Compliance Center](../../media/smtp-auth-clients-report-selected.png)

Als u op de widget klikt, wordt een flyout geopend die een geaggregeerde weergave biedt van het TLS-gebruik en de volumes van de afgelopen week.

![De flyout in het SMTP Auth-klantenrapport](../../media/smtp-auth-clients-flyout.png)

Wanneer u op de koppeling **SMTP Auth-klantenrapport** klikt, ziet u twee hoofdgegevensdraaipunten en twee gegevensweergaven. De gegevensdraaipunten zijn het **verzendvolume** en **tls-gebruik**. De gegevensweergaven zijn de grafiek en de detailstabel.

In de weergave **Volume verzenden** wordt het aantal berichten weergegeven dat is verzonden met SMTP Auth voor het opgegeven tijdsbereik. U het bereik aanpassen door op **Filters**te klikken. De grafiek is geordend op afzenderdomein. U afzonderlijke gegevens voor elk domein bekijken door het domein te selecteren in de **vervolgkeuzelijst Gegevens weergeven voor.**

![Volume verzenden in het SMTP Auth-klantenrapport](../../media/smtp-auth-clients-report-sending-volume.png)

U gedetailleerde informatie over de afzenders bekijken en hun berichttelt door op **de tabel Details weergeven**te klikken. Als u wilt terugkeren naar de grafiek, klikt u op **Rapport weergeven**.

![Detailstabel voor het verzenden van volume in het rapport SMTP Auth-clients](../../media/smtp-auth-clients-report-details-sending-volume.png)

De **TLS-gebruikspil** is belangrijk vanwege de aanstaande afschaffing van TLS1.0 en TLS1.1 in Office 365. Veel oudere apparaten en toepassingen kunnen geen e-mail verzenden als ze alleen TLS1.0 met SMTP Auth kunnen gebruiken. Met deze draaiknop u gebruikers en systeemaccounts identificeren en actie ondernemen die nog steeds oudere versies van TLS gebruiken.

![TLS-gebruik in het rapport SMTP Auth-clients](../../media/smtp-auth-clients-report-tls-usage.png)

U gedetailleerde informatie over de afzenders bekijken, de versies van TLS die ze gebruiken met SMTP Auth en hun bericht telt door op **de tabel Details weergeven**te klikken. Als u wilt terugkeren naar de grafiek, klikt u op **Rapport weergeven**.

U ook een meer gedetailleerde versie van het rapport downloaden door op Rapport aanvragen te klikken.

![Detailstabel voor TLS-gebruik in het rapport SMTP Auth-clients](../../media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="see-also"></a>Zie ook

Zie Inzicht in [e-mailstroom in het Security & Compliance Center](mail-flow-insights-v2.md)voor meer informatie over andere e-mailstroominzichten in het dashboard voor e-mailstromen.
