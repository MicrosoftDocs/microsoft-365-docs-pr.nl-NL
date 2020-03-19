---
title: Afdrukbronnen voorbereiden voor Microsoft Managed Desktop
description: Belangrijke stappen om ervoor te zorgen dat afdrukken soepel werkt
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: a90d104915ecdd31d9ac35a6393fba74a3816ea8
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826429"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Afdrukbronnen voorbereiden voor Microsoft Managed Desktop

Terwijl u zich inschrijven voor Microsoft Managed Desktop, moet u uw afdrukvereisten evalueren en de juiste aanpak voor uw omgeving bepalen. Je hebt drie opties:
 
- Implementeer de hybride cloudprintoplossing van Microsoft om het voor Microsoft Managed Desktop-apparaten eenvoudig te maken printers te ontdekken. Zie [Hybride cloudafdrukken van Windows Server implementeren](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)voor meer informatie.
- Implementeer printers rechtstreeks met behulp van een aangepast PowerShell-script. Volg hiervoor de stappen in de sectie [Lokale printers instellen.](#set-up-local-printers)
- Gebruik een niet-Microsoft-cloudafdrukoplossing die compatibel is met Windows 10-apparaten die zijn gekoppeld aan een Azure Active Directory-domein. De oplossing moet voldoen aan de softwarevereisten voor Microsoft Managed Desktop. Zie [microsoft Managed Desktop-appvereisten](../service-description/mmd-app-requirements.md)voor meer informatie.
 
Als de printerstuurprogramma's in alle gevallen niet beschikbaar zijn in Microsoft Update of de Microsoft Store, moet u ze zelf verkrijgen en laten verpakken voor implementatie naar uw Microsoft Managed Desktop-apparaten met Microsoft Intune. Zie [Intune Standalone - Win32-appbeheer](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management) voor meer informatie

## <a name="set-up-local-printers"></a>Lokale printers instellen

Als u hebt besloten printers te implementeren met behulp van een aangepast PowerShell-script en de afdrukbronnen hebt voorbereid, voert u de volgende stappen uit om gedeelde printers te laten implementeren:

1.  Navigeer naar de microsoft managed desktopportal.
2.  Verzend een *printerimplementatie* met het label printer in het gedeelte **Ondersteuningsverzoeken > ondersteuning** van de beheerportal, met de volgende gegevens:
    - Alle UNC-paden naar gedeelde printerlocaties die moeten worden geïmplementeerd voor Beheerde Bureaubladapparaten van Microsoft
    - Gebruikersgroepen die toegang tot deze gedeelde printers vereisen
3.  Met behulp van de beheerdersportal laten we u weten wanneer de aanvraag is voltooid. In eerste instantie implementeren we de configuratie alleen op apparaten in de groep Testimplementatie.
4.  U moet testen en bevestigen of de configuratie werkt zoals u verwacht. Reageer met het tabblad **Discussie** in het ondersteuningsverzoek om ons te laten weten wanneer u uw test hebt voltooid.
5.  Vervolgens implementeren we de configuratie naar de andere implementatiegroepen.
