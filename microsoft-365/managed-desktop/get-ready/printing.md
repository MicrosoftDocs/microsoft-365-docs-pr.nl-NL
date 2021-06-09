---
title: Afdrukbronnen voorbereiden voor Microsoft Managed Desktop
description: Belangrijke stappen om ervoor te zorgen dat afdrukken soepel verloopt
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 971644aafabda733bf745fae278bdfeeed3282e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574545"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Afdrukbronnen voorbereiden voor Microsoft Managed Desktop

Als u klaar bent om u aan te melden voor Microsoft Managed Desktop, moet u uw afdrukvereisten evalueren en de juiste aanpak voor uw omgeving bepalen. U hebt drie opties:
 
- Implementeer de Microsoft Universal Print-oplossing om het eenvoudig te maken Microsoft Managed Desktop printers te ontdekken. Zie Wat is universeel afdrukken [voor meer informatie.](/universal-print/fundamentals/universal-print-whatis)
- Implementeer printers rechtstreeks met een aangepast PowerShell-script. Volg de stappen in [de sectie Lokale printers](#set-up-local-printers) instellen.
- Gebruik een niet-Microsoft cloudprinter die compatibel is met Windows 10 apparaten die zijn verbonden met een Azure Active Directory domein. De oplossing moet voldoen aan de softwarevereisten voor Microsoft Managed Desktop. Zie voor meer informatie [Microsoft Managed Desktop app-vereisten.](../service-description/mmd-app-requirements.md)
 
Als de printerstuurprogramma's niet beschikbaar zijn via Microsoft Update of de Microsoft Store, moet u ze in alle gevallen zelf verkrijgen en ze laten verpakken voor implementatie naar uw Microsoft Managed Desktop-apparaten met Microsoft Intune. Zie [Intune Standalone - Win32 app management](/mem/intune/apps/apps-win32-app-management) voor meer informatie.

## <a name="set-up-local-printers"></a>Lokale printers instellen

Als u hebt besloten printers te implementeren met een aangepast PowerShell-script en de afdrukresources hebt voorbereid, volgt u de volgende stappen om gedeelde printers te implementeren:

1.  Ga naar de Microsoft Managed Desktop portal.
2.  Een aanvraag indienen met de naam *Printerimplementatie* in de **> ondersteuningsaanvragen** van de beheerportal, met de volgende details:
    - Alle UNC-paden naar gedeelde printerlocaties die moeten worden geïmplementeerd voor Microsoft Managed Desktop apparaten
    - Gebruikersgroepen die toegang nodig hebben tot deze gedeelde printers
3.  Via de beheerportal laten we u weten wanneer de aanvraag is voltooid. In eerste instantie implementeren we de configuratie alleen op apparaten in de groep Testimplementatie.
4.  U moet testen en controleren of de configuratie werkt zoals u verwacht. Reageer via het **tabblad Discussie** in het ondersteuningsverzoek om ons te laten weten wanneer u de test hebt voltooid.
5.  Vervolgens implementeren we de configuratie naar de andere implementatiegroepen.

## <a name="steps-to-get-ready"></a>Stappen om u klaar te maken

1. Controleer [Vereisten voor Microsoft Managed Desktop.](prerequisites.md)
2. Gebruik [gereedheidsbeoordelingshulpmiddelen.](readiness-assessment-tool.md)
3. [Vereisten voor gast-accounts](guest-accounts.md)
4. [Netwerkconfiguratie voor Microsoft Managed Desktop](network.md)
5. [Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Toegang voorbereiden tot on-premises bronnen voor Microsoft Managed Desktop](authentication.md)
7. [Apps in Microsoft Managed Desktop](apps.md)
8. [Toegewezen stations voorbereiden voor Microsoft Managed Desktop](mapped-drives.md)
9. [Afdrukbronnen voorbereiden voor Microsoft Managed Desktop](printing.md) (Dit artikel)
