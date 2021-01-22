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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lees hoe u uw domein kunt verplaatsen van Google Workspace naar Microsoft 365 voor Bedrijven.
ms.openlocfilehash: 23ca451cfdcb67898a10935101efedcdf360ef91
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925000"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Uw Google Workspace-domein toevoegen aan Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

Voeg uw Google Workspace-domein toe aan Microsoft 365 voor Bedrijven, zodat u uw zakelijke e-mailadres kunt blijven gebruiken.

## <a name="try-it"></a>Probeer het zelf!

1. Ga naar het [Microsoft 365-beheercentrum.](https://admin.microsoft.com)
1. Selecteer in het Microsoft 365-beheercentrum in **het** linkernavigatiemenu Alles **tonen,** Instellingen en vervolgens **Domeinen.**
1. Kies **Domein toevoegen,** voer uw domeinnaam in en selecteer **Dit domein gebruiken.** 
1. Kies, **Voeg een TXT-record toe** aan de DNS-records van de domeinen, selecteer **Doorgaan** en kopieer de TXT-waarde. 
1. Ga terug naar de [Google-beheerconsole,](https://admin.google.com)kies Domeinen **beheren,** **Details weergeven,** Domein **beheren,** **DNS** en schuif omlaag naar **aangepaste resourcerecords.**  
1. Open de vervolgkeuze van het recordtype, kies **TXT,** plak de TXT-waarde die u hebt gekopieerd en selecteer **Vervolgens Toevoegen.** 

    De update duurt meestal binnen enkele minuten, maar kan tot 48 uur duren. 
1. Ga terug naar het Microsoft 365-beheercentrum, selecteer **Verifiëren** en vervolgens **Sluiten.** 
1. Als u uw domein wilt instellen als het primaire e-mailadres voor uw gebruikers, selecteert u gebruikers **actieve** gebruikers in het  >  **linkernavigatienavigatiebalkje.** 
1. Kies een gebruiker, selecteer Gebruikersnaam en **e-mailadres beheren,** **Bewerken,** selecteer uw domein in de vervolgkeuze en selecteer vervolgens **Wijzigingen** **opslaan en Klaar.** 
1. Herhaal deze procedure voor elke gebruiker. 

    Wanneer u klaar bent, kunt u Office-apps installeren en uw e-mail- en agenda-items migreren naar Microsoft 365. 