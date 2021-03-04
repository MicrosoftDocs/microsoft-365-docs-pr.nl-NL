---
title: Automatisch doorsturen van e-mailberichten stoppen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Lees hoe u het automatisch doorsturen van e-mailberichten kunt stoppen.
ms.openlocfilehash: ca4383a3f9d64a123955ebe005d0fad5819d3a5d
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421797"
---
# <a name="stop-email-auto-forward"></a>Automatisch doorsturen van e-mail stoppen

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Als een hacker toegang krijgt tot het postvak van een gebruiker, kan deze de e-mail van de gebruiker automatisch doorsturen naar een buitenadres en bedrijfseigen informatie stelen. U kunt dit stoppen door een regel voor de e-mailstroom te maken.

## <a name="try-it"></a>Probeer het zelf!

1. Selecteer Exchange,  de e-mailstroom in het Microsoft 365-beheercentrum en selecteer op het tabblad Regels het plusteken en kies een **nieuwe regel maken.**
1. Selecteer **Meer opties.** De nieuwe regel een naam geven.
1. Open vervolgens de vervolgkeuzepijt om **deze regel toe te passen** als, selecteer de afzender en is vervolgens extern **intern.** 
1. Selecteer **Binnen de organisatie en** vervolgens **OK.**
1. Kies **voorwaarde toevoegen,** open de vervolgkeuzekeuze, selecteer **De** berichteigenschappen en voeg vervolgens **het berichttype toe.**
1. Open de **vervolgkeuzekeuzegroep Berichttype** selecteren, kies **Automatisch doorsturen** en vervolgens **OK.**
1. Open de **volgende vervolgkeuze,** selecteer Het bericht **blokkeren,** weiger het bericht en **voeg een uitleg toe.**
1. Voer de berichttekst in voor uw uitleg en selecteer **vervolgens OK.**
1. Schuif naar beneden en selecteer **Opslaan.**

    De regel is aangemaakt en hackers kunnen geen berichten meer automatisch doorsturen.