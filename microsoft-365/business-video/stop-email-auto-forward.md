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
description: Meer informatie over het stoppen van het automatisch doorsturen van e-mailberichten.
ms.openlocfilehash: f8bd599c7c8bca8d4789188acbcd3574b7473dcb
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903680"
---
# <a name="stop-email-auto-forward"></a>E-mail automatisch doorsturen stoppen

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Als een hacker toegang krijgt tot het postvak van een gebruiker, kunnen ze de e-mail van de gebruiker automatisch doorsturen naar een buitenadres en bedrijfseigen gegevens stelen. U kunt dit stoppen door een regel voor de e-mailstroom te maken.

## <a name="try-it"></a>Probeer het zelf!

1. Selecteer in het Microsoft 365-beheercentrum **Exchange**,  **e-mailstroom** en selecteer op het tabblad Regels het plusteken en kies **een nieuwe regel maken.**
1. Selecteer **Meer opties.** De nieuwe regel een naam geven.
1. Open vervolgens de vervolgkeuzekeuze voor het **toepassen van deze regel als**, selecteer **de** afzender en is vervolgens **extern intern**.
1. Selecteer **Binnen de organisatie** en klik vervolgens op **OK.**
1. Kies **voorwaarde toevoegen,** open de vervolgkeuzekeuze, selecteer **De berichteigenschappen** en voeg **vervolgens het berichttype toe.**
1. Open de **vervolgkeuze** van het type bericht, kies **Automatisch doorsturen** en vervolgens **OK.**
1. Open de **vervolgkeuzeop** Doe het volgende, selecteer **Het bericht blokkeren** en weiger het bericht en voeg een uitleg **toe.**
1. Voer de berichttekst in voor uw uitleg en selecteer **OK.**
1. Schuif naar de onderkant en selecteer **Opslaan.**

    Uw regel is gemaakt en hackers kunnen berichten niet meer automatisch doorsturen.

## <a name="related-content"></a>Verwante onderwerpen

[Een andere e-mailalias](https://docs.microsoft.com/microsoft-365/admin/email/add-another-email-alias-for-a-user) voor een gebruiker toevoegen (artikel) E-mail doorsturen [configureren in Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding) (artikel) Problemen met e-mailbezorging zoeken en oplossen als beheerder van [Office 365](https://docs.microsoft.com/exchange/troubleshoot/email-delivery/email-delivery-issues) voor Bedrijven (artikel)