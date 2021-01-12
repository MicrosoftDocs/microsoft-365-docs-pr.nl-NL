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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Leer hoe u uw domein verbindt met Microsoft 365.
ms.openlocfilehash: c7827b93b56560579b31bd2abb5a852467565103
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794602"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>Uw domein koppelen aan Microsoft 365 voor bedrijven

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

Wanneer u Microsoft 365 hebt ingesteld en uw e-mail gegevens uit Google Workspace hebt verplaatst, kunt u uw domein verbinden met Microsoft 365. 

U dient eerst bestaande DNS-records uit Google te verwijderen, dan kunnen we nieuwe DNS-records toevoegen in Microsoft 365.

## <a name="try-it"></a>Probeer het zelf!

1. Meld u aan bij uw Google Workspace-beheerconsole op [admin.Google.com](https://admin.google.com).
1. Selecteer **domeinen**, **domeinen beheren**, **Details weergeven**, **domein beheren** en **DNS** in de linkernavigatiebalk.
1. Schuif omlaag naar **synthetische records**, open **Google Workspace**, selecteer **verwijderen** en klik vervolgens nogmaals op **verwijderen** .
1. Schuif omlaag naar **aangepaste resource records** en verwijder eventuele bestaande DNS-records die worden weergegeven, inclusief de gegevens die u eerder hebt gemaakt voor microsoft 365.
1. Ga naar het [Microsoft 365-Beheercentrum](https://admin.microsoft.com).
1. Kies in het linkernavigatievenster de optie, **AllesWeergeven**, **instellingen**, **domeinen**.
1. Kies vervolgens uw standaarddomein.
1. Selecteer **Doorgaan met instellen** en kies  **Doorgaan** om uw domein te verbinden.
1. Schuif omlaag om de DNS-records weer te geven die moeten worden gekopieerd naar Google.
1. Open **MX-records** en kopieer onder **Points to address or value** de record.
1. Ga terug naar Google en open de vervolgkeuzelijst recordtype in de sectie **Custom resource records** en selecteer **MX**.
1. Plak de gekopieerde record in het veld **Data** .
1. Selecteer vervolgens **toevoegen**.
1. Herhaal het proces voor CNAME-en TXT-records en voeg de waarden toe op de pagina Google DNS Management.
1. Ga terug naar het Microsoft 365-Beheercentrum en selecteer **Doorgaan**.

    Het instellen van uw domein is voltooid.