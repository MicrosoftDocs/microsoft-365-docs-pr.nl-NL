---
title: Uw Google Workspace-domein toevoegen
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
description: Meer informatie over het verplaatsen van uw domein van Google Workspace naar Microsoft 365 voor Bedrijven.
ms.openlocfilehash: 814e714527467bb6e7008ea141989f3117ddcdd8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578769"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Uw Google Workspace-domein toevoegen aan Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

Voeg uw Google Workspace-domein toe aan Microsoft 365 voor Bedrijven, zodat u uw zakelijke e-mailadres kunt blijven gebruiken.

## <a name="try-it"></a>Probeer het zelf!

1. Ga naar het [Microsoft 365-beheercentrum.](https://admin.microsoft.com)
1. Selecteer in het Microsoft 365-beheercentrum in het  linkernavigatiemenu De optie **Alles,** Instellingen en vervolgens **Domeinen tonen.**
1. Kies **Domein toevoegen,** voer uw domeinnaam in en selecteer **Dit domein gebruiken.** 
1. Kies, **Voeg een TXT-record toe aan de DNS-records** van domeinen, selecteer **Doorgaan** en kopieer de TXT-waarde. 
1. Ga terug naar [de Google-beheerconsole,](https://admin.google.com)kies **Domeinen,** Domeinen **beheren,** **Details** **weergeven,** Domein beheren, **DNS** en schuif omlaag naar **Aangepaste resourcerecords.** 
1. Open de vervolgkeuze van het recordtype, kies **TXT,** plak de TXT-waarde die u hebt gekopieerd en selecteer **Toevoegen.** 

    De update duurt meestal binnen enkele minuten, maar kan maximaal 48 uur duren. 
1. Ga terug naar het Microsoft 365-beheercentrum, selecteer **Verifiëren** en sluit **vervolgens**. 
1. Als u uw domein wilt instellen als de primaire e-mail voor uw gebruikers, selecteert u in de linkernavigatiebalk **Gebruikers**  >  **Actieve gebruikers.** 
1. Kies een gebruiker, selecteer **Gebruikersnaam en e-mail beheren**, **Bewerken**, selecteer uw domein in de vervolgkeuzekeuze en selecteer vervolgens **Wijzigingen** opslaan en **Klaar.** 
1. Herhaal dit proces voor elke gebruiker. 

    Wanneer u klaar bent, kunt u Office-apps installeren en uw e-mail- en agenda-items migreren naar Microsoft 365. 