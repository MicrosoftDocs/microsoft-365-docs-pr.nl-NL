---
title: Printbronnen voorbereiden voor Microsoft Managed Desktop
description: Belangrijke stappen om ervoor te zorgen dat werk soepel verloopt
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 5198691a38b179a5491a36de95531edb9f32d691
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2020
ms.locfileid: "48322221"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Printbronnen voorbereiden voor Microsoft Managed Desktop

Als u klaar bent om u aan te melden bij Microsoft Managed Desktop, evalueert u de afdrukvereisten en bepaalt u de juiste aanpak voor de omgeving. U hebt drie opties:
 
- Implementeer de Microsoft Universal Print-oplossing zodat Microsoft de beheerde bureaublad apparaten gemakkelijk kunnen detecteren. Zie [Wat is universeel afdrukken](https://docs.microsoft.com/universal-print/fundamentals/universal-print-whatis)voor meer informatie.
- Gebruik rechtstreeks een aangepaste PowerShell-script om printers te implementeren. Voer de stappen uit in de sectie [lokale printers instellen](#set-up-local-printers) om dit te doen.
- Gebruik een niet-Microsoft Cloud printing-oplossing die compatibel is met Windows 10-apparaten die lid zijn van een Azure Active Directory-domein. De oplossing moet voldoen aan de softwarevereisten voor Microsoft Managed Desktop. Zie vereisten voor de [beheerde bureaubladtoepassing van Microsoft](../service-description/mmd-app-requirements.md)voor meer informatie.
 
Als de printerstuurprogramma's niet beschikbaar zijn in Microsoft Update of in de Microsoft Store, kunt u deze in alle gevallen zelf verkrijgen en ze laten inpakken voor implementatie met Microsoft intune voor Microsoft Managed Desktop-apparaten. Zie voor meer informatie [intune standalone-Win32®-app beheren](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Lokale printers instellen

Als u hebt besloten om printers te implementeren met behulp van een aangepast PowerShell-script en de afdrukbronnen hebt voorbereid, voert u deze stappen uit om gedeelde printers te implementeren:

1.  Ga naar de Microsoft beheerde bureaublad Portal.
2.  Verzend een aanvraag met de naam *printer implementatie* in **ondersteunings-en ondersteuningsverzoeken >** ondersteuningsverzoeken van de beheer Portal, mits deze gegevens worden verstrekt:
    - Alle UNC-paden naar gedeelde printerlocaties die moeten worden geïmplementeerd voor Microsoft beheerde bureaublad apparaten
    - Gebruikersgroepen die toegang hebben tot deze gedeelde printers
3.  Met de beheer Portal laten we u weten wanneer de aanvraag is voltooid. In eerste instantie implementeren we de configuratie alleen op apparaten in de implementatiegroep testen.
4.  U moet testen en controleren of de configuratie werkt zoals u verwacht. Antwoord met het tabblad **discussie** in het ondersteuningsverzoek om ons te laten weten wanneer u klaar bent met het testen.
5.  Vervolgens implementeren we de configuratie naar de andere implementatie groepen.
