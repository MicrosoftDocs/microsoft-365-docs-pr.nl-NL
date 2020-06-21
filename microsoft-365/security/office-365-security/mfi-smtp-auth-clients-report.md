---
title: SMTP-verificatierapport voor clients
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
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer te weten komen over het smtp Auth-clientsrapport in het e-mailstroomdashboard in het Security & Compliance Center.
ms.openlocfilehash: 90d008bf775c692431fb5b832652ceb97f9fd760
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818817"
---
# <a name="smtp-auth-clients-report"></a>SMTP-verificatierapport voor clients

Het **SMTP Auth-klantenrapport** belicht het gebruik van het SMTP Auth-client submission protocol door gebruikers of systeemaccounts in uw organisatie. Dit verouderde protocol (dat het eindpunt smtp.office365.com) gebruikt, biedt alleen basisverificatie en is gevoelig voor gebruik door gecompromitteerde accounts om e-mail te verzenden.  Met dit rapport u controleren op ongebruikelijke activiteiten. Het toont ook de TLS-gebruiksgegevens voor clients of apparaten die SMTP Auth gebruiken.

De widget die wordt weergegeven in het dashboard van mailflows geeft het aantal gebruikers of serviceaccounts aan dat het SMTP Auth-protocol in de afgelopen 7 dagen heeft gebruikt.

![De KLANTEN VAN SMTP Auth rapporteren in het dashboard van de e-mailstroom in het Security & Compliance Center](../../media/smtp-auth-clients-report-selected.png)

Als u op de widget klikt, wordt een flyout geopend die een geaggregeerde weergave biedt van het TLS-gebruik en de volumes van de afgelopen week.

![De flyout in het SMTP Auth-klantenrapport](../../media/smtp-auth-clients-flyout.png)

Wanneer u op de koppeling **SMTP Auth-clientsrapport** klikt, ziet u twee hoofdpunten en twee gegevensweergaven. De gegevensdraaipunten zijn het **verzendvolume** en **TLS-gebruik.** De gegevensweergaven zijn de grafiek en de detailtabel.

In de weergave **Volume verzenden** wordt het aantal berichten weergegeven dat met SMTP Auth is verzonden voor het opgegeven tijdsbereik. U het bereik aanpassen door op **Filters**te klikken. De grafiek wordt georganiseerd door het afzenderdomein. U afzonderlijke gegevens voor elk domein bekijken door het domein te selecteren in de vervolgkeuzelijst **Gegevens weergeven voor** vervolgkeuzelijst.

![Volume verzenden in het SMTP Auth-klantenrapport](../../media/smtp-auth-clients-report-sending-volume.png)

U gedetailleerde informatie over de afzenders en het aantal berichten bekijken door op **tabel Details weergeven**te klikken. Als u wilt terugkeren naar de grafiek, klikt u op **Rapport weergeven**.

![Detailtabel voor verzenden van volume in het SMTP Auth-klantenrapport](../../media/smtp-auth-clients-report-details-sending-volume.png)

De pivot **van TLS-gebruik** is belangrijk vanwege de aanstaande afschaffing van TLS1.0 en TLS1.1 in Office 365. Veel oudere apparaten en toepassingen kunnen geen e-mail verzenden als ze alleen TLS1.0 kunnen gebruiken met SMTP Auth. Met deze draaifunctie u gebruikers en systeemaccounts identificeren en actie ondernemen die nog oudere versies van TLS gebruiken.

![TLS-gebruik in het SMTP Auth-klantenrapport](../../media/smtp-auth-clients-report-tls-usage.png)

U gedetailleerde informatie bekijken over de afzenders, de versies van TLS die ze gebruiken met SMTP Auth en hun bericht telt door te klikken op **tabel Details weergeven.** Als u wilt terugkeren naar de grafiek, klikt u op **Rapport weergeven**.

U ook een meer gedetailleerde versie van het rapport downloaden door op Rapport Aanvragen te klikken.

![Detailtabel voor TLS-gebruik in het SMTP Auth-clientsrapport](../../media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="related-topics"></a>Verwante onderwerpen

Zie [E-mailstroominzichten in het Security & Compliance Center](mail-flow-insights-v2.md)voor meer informatie over andere e-mailstroominzichten in het dashboard voor e-mailstromen.
