---
title: Printbronnen voorbereiden voor Microsoft Managed Desktop
description: Belangrijke stappen om ervoor te zorgen dat afdrukken soepel verloopt
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1588a2c91bcbe0bd381acb6be4f9bd5562810860
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530245"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Printbronnen voorbereiden voor Microsoft Managed Desktop

Als u zich klaar maakt om u in te schrijven voor Microsoft Managed Desktop, moet u uw afdrukvereisten evalueren en de juiste aanpak voor uw omgeving bepalen. Je hebt drie opties:
 
- Implementeer de hybride cloudprintoplossing van Microsoft om microsoft Managed Desktop-apparaten eenvoudig printers te laten ontdekken. Zie [Windows Server Hybrid Cloud Print implementeren](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)voor meer informatie.
- Implementeer printers rechtstreeks met behulp van een aangepast PowerShell-script. Volg hiervoor de stappen in de sectie [Lokale printers instellen.](#set-up-local-printers)
- Gebruik een niet-Microsoft-cloudafdrukoplossing die compatibel is met Windows 10-apparaten die zijn gekoppeld aan een Azure Active Directory-domein. De oplossing moet voldoen aan de softwarevereisten voor Microsoft Managed Desktop. Zie [Microsoft Managed Desktop-appvereisten](../service-description/mmd-app-requirements.md)voor meer informatie .
 
Als de printerstuurprogramma's niet beschikbaar zijn via Microsoft Update of de Microsoft Store, moet u ze in alle gevallen zelf ophalen en laten verpakken voor implementatie naar uw Microsoft Managed Desktop-apparaten met Microsoft Intune. Zie [Intune Standalone - Win32-appbeheer voor](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management) meer informatie

## <a name="set-up-local-printers"></a>Lokale printers instellen

Als u hebt besloten printers te implementeren met behulp van een aangepast PowerShell-script en de afdrukbronnen hebt voorbereid, voert u de volgende stappen uit om gedeelde printers te laten implementeren:

1.  Navigeer naar de Microsoft Managed Desktop-portal.
2.  Dien een verzoek met het label *Printer-implementatie* in de sectie **Ondersteuningsaanvragen > ondersteuningsaanvragen** van de beheerportal, met de volgende gegevens:
    - Alle UNC-paden naar gedeelde printerlocaties die moeten worden geïmplementeerd voor Microsoft Managed Desktop-apparaten
    - Gebruikersgroepen die toegang tot deze gedeelde printers vereisen
3.  Via de beheerportal laten we je weten wanneer de aanvraag is voltooid. In eerste instantie implementeren we de configuratie alleen naar apparaten in de implementatiegroep Testen.
4.  U moet testen en bevestigen of de configuratie werkt zoals u verwacht. Beantwoord met het tabblad **Discussie** in het ondersteuningsverzoek om ons te laten weten wanneer u uw tests hebt voltooid.
5.  Vervolgens implementeren we de configuratie naar de andere implementatiegroepen.
