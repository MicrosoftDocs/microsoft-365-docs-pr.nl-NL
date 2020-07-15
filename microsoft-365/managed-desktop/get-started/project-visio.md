---
title: Microsoft Project of Microsoft Visio installeren op Microsoft Managed Desktop-apparaten
description: Informatie over het installeren van Microsoft Project of Microsoft Visio op Microsoft Managed Desktop-apparaten
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c8690db17c71fd5ce604fd9165fee7e54a41c639
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126825"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Microsoft Project of Microsoft Visio installeren op Microsoft Managed Desktop-apparaten

Voor Microsoft Project en Microsoft Visio moeten specifieke stappen worden geïnstalleerd op Microsoft Managed Desktop-apparaten. Dit onderwerp documenteert de vereisten en het installatieproces voor deze toepassingen.

## <a name="prerequisites"></a>Vereisten

Beheerders moeten controleren of ze aan deze voorwaarden voldoen:
- **Licentiehoeveelheden** - De juiste hoeveelheid Microsoft Project- en Microsoft Visio-licenties moet beschikbaar zijn voor uw gebruikers. Microsoft Managed Desktop ondersteunt momenteel alleen 64-bits versies van deze toepassingen. 
- **Licentienamen** - De juiste licentienamen voor deze toepassingen zijn:
    - **Microsoft Project** - Project Online Professional of Project Online Premium
    - **Microsoft Visio** - Visio Online Plan 2
- **Bedrijfsportal** - De Bedrijfsportal moet beschikbaar zijn in uw tenant voor uw gebruikers om deze toepassingen te installeren. Zie [Bedrijfsportal](company-portal.md).

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Project en Visio implementeren voor Microsoft Managed Desktop-apparaten
Microsoft Managed Desktop voegt Microsoft Project en Microsoft Visio toe als twee Win32-toepassingen in Microsoft Intune. We maken ook twee groepen in Azure Active Directory die worden toegewezen aan de bijbehorende toepassing met de intentie 'Beschikbaar'. 

**Project en Visio implementeren** Voeg de gebruiker toe aan de juiste groep en de toepassing wordt beschikbaar in de bedrijfsportal. Het kan enkele minuten duren voordat de synchronisatie is, maar uw gebruikers kunnen de apps installeren vanuit Company Portal. 

Azure AD-groepnaam | Welke gebruikers moeten ze toewijzen?   
 --- | ---
Moderne Workplace-Office-Project_Install | Gebruikers die Project nodig hebben
Moderne Workplace-Office-Visio_Install | Gebruikers die Visio nodig hebben

## <a name="communicate-changes"></a>Wijzigingen communiceren
Het is belangrijk voor IT-beheerders om hun gebruikers te laten weten hoe project en Visio te installeren. Dit omvat: 
- Gebruikers op de hoogte stellen wanneer deze toepassingen voor hen beschikbaar zijn. 
- Instructies voor het installeren van deze toepassingen vanuit de Bedrijfsportal.
