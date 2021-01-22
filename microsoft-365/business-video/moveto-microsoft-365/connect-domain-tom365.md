---
title: Verbind uw domein met Microsoft 365
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informatie over het verbinden van uw domein met Microsoft 365.
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925108"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>Uw domein verbinden met Microsoft 365 voor Bedrijven

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

Nadat u Microsoft 365 hebt ingesteld en uw e-mailgegevens hebt verplaatst van Google Workspace, kunt u uw domein verbinden met Microsoft 365. 

Eerst moet u bestaande DNS-records van Google verwijderen, dan kunnen we nieuwe DNS-records van Microsoft 365 toevoegen.

## <a name="try-it"></a>Probeer het zelf!

1. Meld u aan bij uw Google Workspace-beheerconsole [admin.google.com.](https://admin.google.com)
1. Selecteer **Domeinen,** **Domeinen beheren,** **Details weergeven,** Domein **beheren** en **vervolgens DNS** in het linkernavigatiebalkje.
1. Schuif omlaag naar **Recordgegevens,** open **Google Workspace,** selecteer **Verwijderen** en **vervolgens opnieuw** Verwijderen.
1. Schuif omlaag naar **aangepaste resourcerecords** en verwijder bestaande DNS-records die worden weergegeven, inclusief records die u mogelijk eerder hebt gemaakt voor Microsoft 365.
1. Ga naar het [Microsoft 365-beheercentrum.](https://admin.microsoft.com)
1. Kies in het linkernavigatiemenu de optie **Alles tonen,** **Instellingen,** **Domeinen.**
1. Kies vervolgens uw standaarddomein.
1. Selecteer **Doorgaan met instellen** en kies Doorgaan om uw domein te **verbinden.**
1. Schuif omlaag om de DNS-records te bekijken die naar Google moeten worden gekopieerd.
1. Open **MX Records** en kopieer de record onder Adres of **waarde** naar.
1. Ga terug naar Google en open in de sectie **Aangepaste resourcerecords** het vervolgkeuzevak recordtype en selecteer **MX.**
1. Plak de **gekopieerde** record in het veld Gegevens.
1. Selecteer vervolgens **Toevoegen.**
1. Herhaal het proces voor CNAME- en TXT-records en voeg de waarden toe aan de pagina voor dns-beheer van Google.
1. Ga terug naar het Microsoft 365-beheercentrum en selecteer **Doorgaan.**

    Het instellen van uw domein is voltooid.