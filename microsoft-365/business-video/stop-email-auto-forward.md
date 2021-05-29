---
title: Automatisch doorsturen van e-mailberichten stoppen
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Meer informatie over het stoppen van het automatisch doorsturen van e-mailberichten door een e-mailstroomregel te maken om diefstal van bedrijfsgegevens te voorkomen.
ms.openlocfilehash: 82e4c80b0edc501889e0fc4dc28f1ec1ad703568
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706472"
---
# <a name="stop-email-auto-forward"></a>E-mail automatisch doorsturen stoppen

## <a name="watch-stop-auto-forwarding-emails"></a>Kijken: Het automatisch doorsturen van e-mailberichten stoppen

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Als een hacker toegang krijgt tot het postvak van een gebruiker, kunnen ze de e-mail van de gebruiker automatisch doorsturen naar een buitenadres en bedrijfseigen gegevens stelen. U kunt dit stoppen door een regel voor de e-mailstroom te maken.

## <a name="try-it"></a>Probeer het zelf!

1. Selecteer in Microsoft 365 beheercentrum Exchange **,** **e-mailstroom** en  selecteer op het tabblad Regels het plusteken en kies **een nieuwe regel maken.**
1. Selecteer **Meer opties.** De nieuwe regel een naam geven.
1. Open vervolgens de vervolgkeuzekeuze voor het **toepassen van deze regel als**, selecteer **de** afzender en is vervolgens **extern intern**.
1. Selecteer **Binnen de organisatie** en klik vervolgens op **OK.**
1. Kies **voorwaarde toevoegen,** open de vervolgkeuzekeuze, selecteer **De berichteigenschappen** en voeg **vervolgens het berichttype toe.**
1. Open de **vervolgkeuze** van het type bericht, kies **Automatisch doorsturen** en vervolgens **OK.**
1. Open de **vervolgkeuzeop** Doe het volgende, selecteer **Het bericht blokkeren** en weiger het bericht en voeg een uitleg **toe.**
1. Voer de berichttekst in voor uw uitleg en selecteer **OK.**
1. Schuif naar de onderkant en selecteer **Opslaan.**

    Uw regel is gemaakt en hackers kunnen berichten niet meer automatisch doorsturen.

## <a name="related-content"></a>Verwante inhoud

[Een ander e-mailalias toevoegen voor een gebruiker](../admin/email/add-another-email-alias-for-a-user.md) (artikel)\
[Doorsturen van e‑mail configureren in Microsoft 365](../admin/email/configure-email-forwarding.md) (artikel)\
[Problemen met e-mailbezorging](/exchange/troubleshoot/email-delivery/email-delivery-issues) zoeken en oplossen als Office 365 voor zakelijke beheerder (artikel)