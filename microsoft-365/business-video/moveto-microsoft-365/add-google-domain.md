---
title: Uw Google Workspace-domein toevoegen
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
description: Meer informatie over het verplaatsen van uw domein van Google Workspace naar Microsoft 365 voor bedrijven.
ms.openlocfilehash: 1abc05867147d2b52e26804918e8247053b5e1d5
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794674"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Uw Google Workspace-domein toevoegen aan Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

Voeg uw Google Workspace-domein toe aan Microsoft 365 voor bedrijven, zodat u uw zakelijke e-mailadres kunt blijven gebruiken.

## <a name="try-it"></a>Probeer het zelf!

1. Ga naar het [Microsoft 365-Beheercentrum](https://admin.microsoft.com).
1. Selecteer in het Microsoft 365-Beheercentrum in het linkernavigatievenster de optie **AllesWeergeven**, **instellingen** en **domeinen**.
1. Kies **domein toevoegen**, voer uw domeinnaam in en selecteer vervolgens **dit domein gebruiken**. 
1. Kies **een TXT-record toevoegen aan de DNS-records van het domein**, selecteer **Doorgaan** en kopieer de txt-waarde. 
1. Ga terug naar de [Google-beheer console](https://admin.google.com), kies **domeinen**, **domeinen beheren**, **Details weergeven**, **domeinen beheren**, **DNS** en schuif vervolgens omlaag naar **aangepaste bronrecords**. 
1. Open de vervolgkeuzelijst recordtype, kies **txt**, plak de txt-waarde die u hebt gekopieerd en selecteer vervolgens **toevoegen**. 

    De update duurt doorgaans binnen enkele minuten, maar kan 48 uur duren. 
1. Ga terug naar het Microsoft 365-Beheercentrum, selecteer **verifiëren** en vervolgens **sluiten**. 
1. Als u uw domein wilt instellen als het primaire e-mailadres voor uw gebruikers, selecteert u in het linkernavigatievenster **gebruikers**  >  **actieve gebruikers**. 
1. Kies een gebruiker, selecteer **gebruikersnaam en E-mail beheren**, **bewerken**, selecteer uw domein in de vervolgkeuzelijst en selecteer vervolgens **gereed** om wijzigingen op te **slaan**. 
1. Herhaal dit proces voor elke gebruiker. 

    Wanneer u klaar bent, kunt u Office-apps installeren en uw e-mail-en agenda-items migreren naar Microsoft 365. 