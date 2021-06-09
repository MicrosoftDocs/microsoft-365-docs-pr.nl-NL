---
title: Installatie Microsoft Project of Microsoft Visio op Microsoft Managed Desktop apparaten
description: Informatie over het installeren van Microsoft Project of Microsoft Visio op Microsoft Managed Desktop apparaten
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c04bcdf846bafaa7838ef5932c8de595f5035992
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950530"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Installatie Microsoft Project of Microsoft Visio op Microsoft Managed Desktop apparaten

Microsoft Project en Microsoft Visio moeten specifieke stappen worden geïnstalleerd op Microsoft Managed Desktop apparaten. Dit onderwerp documenteert de vereisten en het installatieproces voor deze toepassingen.

## <a name="prerequisites"></a>Vereisten

Beheerders moeten controleren of ze aan deze vereisten voldoen:
- **Licentiehoeveelheden:** de juiste hoeveelheid Microsoft Project microsoft-Visio moet beschikbaar zijn voor uw gebruikers. Microsoft Managed Desktop ondersteunt momenteel alleen 64-bits versies van deze toepassingen. 
- **Licentienamen:** de juiste licentienamen voor deze toepassingen zijn:
    - **Microsoft Project** - Project Online Professional of Project Online Premium
    - **Microsoft Visio** - Visio Online Plan 2
- **Bedrijfsportal-** De Bedrijfsportal moet beschikbaar zijn in uw tenant zodat uw gebruikers deze toepassingen kunnen installeren. Als de Bedrijfsportal niet is geïmplementeerd in uw tenant, bekijkt [u Bedrijfsportal.](company-portal.md)

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Implementatie Project en Visio voor Microsoft Managed Desktop apparaten
Microsoft Managed Desktop worden Microsoft Project en Microsoft Visio als twee Win32-toepassingen in Microsoft Intune. We maken ook twee groepen in Azure Active Directory die worden toegewezen aan de bijbehorende toepassing met de bedoeling 'Beschikbaar'. 

**Uw Project en Visio** Voeg de gebruiker toe aan de juiste groep en de toepassing wordt beschikbaar in de Bedrijfsportal. Het kan enkele minuten duren voordat de synchronisatie is, maar uw gebruikers kunnen de apps vervolgens installeren vanaf Bedrijfsportal. 

Naam van Azure AD-groep | Welke gebruikers moeten worden toegewezen?   
 --- | ---
Modern Workplace-Office-Project_Install | Gebruikers die een Project
Modern Workplace-Office-Visio_Install | Gebruikers die een Visio

## <a name="communicate-changes"></a>Wijzigingen communiceren
It-beheerders moeten hun gebruikers laten weten hoe ze Project en Visio. Dit zijn: 
- Gebruikers op de hoogte stellen wanneer deze toepassingen voor hen beschikbaar zijn. 
- Instructies voor het installeren van deze toepassingen vanaf de Bedrijfsportal.
