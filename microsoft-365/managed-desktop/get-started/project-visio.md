---
title: Microsoft Project of Microsoft Visio installeren op Microsoft Managed Desktop-apparaten
description: Informatie over het installeren van Microsoft Project of Microsoft Visio op Microsoft Managed Desktop-apparaten
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 30374e603350ecf9d5e5542263f004a22ccb0a67
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/14/2019
ms.locfileid: "42809149"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Microsoft Project of Microsoft Visio installeren op Microsoft Managed Desktop-apparaten

Microsoft Project en Microsoft Visio vereisen dat specifieke stappen worden geïnstalleerd op Microsoft Managed Desktop-apparaten. In dit onderwerp worden de vereisten en het installatieproces voor deze toepassingen vermeld.

## <a name="prerequisites"></a>Vereisten

Beheerders moeten controleren of ze aan deze voorwaarden voldoen:
- **Licentiehoeveelheden** - De juiste hoeveelheid Microsoft Project- en Microsoft Visio-licenties moet beschikbaar zijn voor uw gebruikers. Microsoft Managed Desktop ondersteunt momenteel alleen 64-bits versies van deze toepassingen. 
- **Licentienamen** - De juiste licentienamen voor deze toepassingen zijn:
    - **Microsoft Project** - Project Online Professional of Project Online Premium
    - **Microsoft Visio** - Visio Online-abonnement 2
- **Bedrijfsportaal** - De bedrijfsportal moet beschikbaar zijn in uw tenant voor uw gebruikers om deze toepassingen te installeren. Zie [Bedrijfsportaal als](company-portal.md)de bedrijfsportal niet in uw tenant is geïmplementeerd.

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Project en Visio implementeren voor beheerde desktopapparaten van Microsoft
Nadat u uw ondersteuningsverzoek hebt ingediend, maakt Microsoft Managed Desktop drie Azure AD-groepen en drie toepassingsimplementaties via Microsoft Intune om de apps naar uw tenant te implementeren.  

**Project en Visio implementeren**
1. **Een ondersteuningsverzoek indienen** IT-beheerders moeten een ondersteuningsverzoek indienen om deze toepassingen beschikbaar te maken voor hun gebruikers. Zie [Beheerdersondersteuning voor Microsoft Managed Desktop voor](../working-with-managed-desktop/admin-support.md)informatie over het contact opnemen met Microsoft Managed Desktop.
2. **Gebruikers toewijzen aan nieuwe Azure AD-groepen** Microsoft Managed Desktop maakt 3 Azure AD-groepen in uw tenant en 3 bijbehorende toepassingsimplementaties. IT-beheerders moeten de gebruikers toewijzen aan de juiste groepen.

>[!NOTE]
>Wijs gebruikers toe aan slechts één van deze Azure AD-groepen. 

Naam van Azure AD-groep | Welke gebruikers moeten toewijzen?   
 --- | ---
Modern Workplace-Office-Project_Install | Gebruikers die alleen Project nodig hebben
Moderne Workplace-Office-Visio_Install | Gebruikers die alleen Visio nodig hebben
Moderne Workplace-Office-Visio_Project_Install | Gebruikers die zowel Project als Visio nodig hebben

Eenmaal toegewezen aan deze groepen, zullen toepassingen beschikbaar zijn in de Bedrijfsportal. Het kan enkele minuten duren om te synchroniseren, maar dan kunnen uw gebruikers de apps installeren vanuit Bedrijfsportal. 

## <a name="communicate-changes"></a>Wijzigingen communiceren
Het is belangrijk dat IT-beheerders hun gebruikers laten weten hoe ze Project en Visio moeten installeren. Dit omvat: 
- Gebruikers op de hoogte stellen wanneer deze toepassingen voor hen beschikbaar zijn. 
- Instructies voor het installeren van deze toepassingen vanuit de Bedrijfsportal.

>[!NOTE]
>Gebruikers moeten alle Office-toepassingen sluiten voordat ze Microsoft Project of Microsoft Visio van Bedrijfsportal installeren. 
