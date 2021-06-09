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
description: Meer informatie over het verbinden van uw domein met Microsoft 365.
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925108"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>Verbinding maken domein naar Microsoft 365 voor bedrijven

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

Nadat u uw e-Microsoft 365 hebt ingesteld en uw e-mailgegevens vanuit Google Workspace hebt verplaatst, kunt u uw domein verbinden met Microsoft 365. 

Eerst moet u bestaande DNS-records van Google verwijderen en vervolgens kunnen we nieuwe DNS-records toevoegen uit Microsoft 365.

## <a name="try-it"></a>Probeer het zelf!

1. Meld u aan bij uw Google Workspace-beheerconsole [admin.google.com.](https://admin.google.com)
1. Selecteer **Domeinen**, **Domeinen beheren**, Details **weergeven**, **Domein beheren** en vervolgens **DNS** in de linkernavigatie.
1. Schuif omlaag naar **Synthetische records,** open **Google Workspace,** selecteer **Verwijderen** en **vervolgens opnieuw** verwijderen.
1. Schuif omlaag naar **Aangepaste resourcerecords** en verwijder bestaande DNS-records die worden weergegeven, inclusief alle dns-records die u eerder hebt gemaakt voor Microsoft 365.
1. Ga naar het [Microsoft 365 beheercentrum.](https://admin.microsoft.com)
1. Kies in het linkernavigatieprogramma de optie **Alle**, **Instellingen**, **Domeinen.**
1. Kies vervolgens uw standaarddomein.
1. Selecteer **Doorgaan met** instellen en kies vervolgens Doorgaan om uw domein te **verbinden.**
1. Schuif omlaag om de DNS-records te bekijken die moeten worden gekopieerd naar Google.
1. Open **MX Records** en kopieer de record onder Adres of **waarde.**
1. Ga terug naar Google en open in de sectie **Aangepaste resourcerecords** de vervolgkeuze en selecteer **MX**.
1. Plak in **het** veld Gegevens de record die u hebt gekopieerd.
1. Selecteer vervolgens **Toevoegen**.
1. Herhaal het proces voor CNAME- en TXT-records en voeg de waarden toe op de pagina Dns-beheer van Google.
1. Ga terug naar het Microsoft 365 beheercentrum en selecteer **Doorgaan.**

    Uw domeinconfiguratie is voltooid.