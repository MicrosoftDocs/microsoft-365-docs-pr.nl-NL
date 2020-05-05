---
title: Microsoft Project of Microsoft Visio installeren op Microsoft Managed Desktop-apparaten
description: Informatie over het installeren van Microsoft Project of Microsoft Visio op Microsoft Managed Desktop-apparaten
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 450dbcb08cd0636dae575ecd2d5e9abadc5ceb25
ms.sourcegitcommit: 44e685a0b193e89de5befb1e1a3740eb31931799
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44022094"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Microsoft Project of Microsoft Visio installeren op Microsoft Managed Desktop-apparaten

Microsoft Project en Microsoft Visio vereisen dat specifieke stappen worden geïnstalleerd op Microsoft Managed Desktop-apparaten. In dit onderwerp worden de vereisten en het installatieproces voor deze toepassingen documentaal.

## <a name="prerequisites"></a>Vereisten

Beheerders moeten controleren of ze aan deze vereisten voldoen:
- **Licentiehoeveelheden** : het juiste aantal Microsoft Project- en Microsoft Visio-licenties moet beschikbaar zijn voor uw gebruikers. Microsoft Managed Desktop ondersteunt momenteel alleen 64-bits versies van deze toepassingen. 
- **Licentienamen** - De juiste licentienamen voor deze toepassingen zijn:
    - **Microsoft Project** - Project Online Professional of Project Online Premium
    - **Microsoft Visio** - Visio Online-abonnement 2
- **Bedrijfsportal** - De bedrijfsportal moet beschikbaar zijn in uw tenant voor uw gebruikers om deze toepassingen te installeren. Zie [Bedrijfsportal](company-portal.md)als de bedrijfsportal niet is geïmplementeerd in uw tenant.

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Project- en Visio-apparaten implementeren voor Microsoft Managed Desktop-apparaten
Nadat u uw ondersteuningsaanvraag hebt ingediend, maakt Microsoft Managed Desktop drie Azure AD-groepen en drie toepassingsimplementaties via Microsoft Intune om de apps naar uw tenant te implementeren.  

**Project en Visio implementeren**
1. **Een ondersteuningsverzoek indienen** IT-beheerders moeten een ondersteuningsverzoek indienen om deze toepassingen beschikbaar te maken voor hun gebruikers. Zie [Beheerdersondersteuning voor Microsoft Managed Desktop voor](../working-with-managed-desktop/admin-support.md)informatie over het contact opnemen met Microsoft Managed Desktop.
2. **Gebruikers toewijzen aan nieuwe Azure AD-groepen** Microsoft Managed Desktop maakt 3 Azure AD-groepen in uw tenant en 3 bijbehorende toepassingsimplementaties. IT-beheerders moeten de gebruikers toewijzen aan de juiste groepen.

>[!NOTE]
>Gebruikers toewijzen aan slechts één van deze Azure AD-groepen. 

Azure AD-groepnaam | Welke gebruikers moeten worden toegewezen?   
 --- | ---
Moderne werkplek-office-Project_Install | Gebruikers die Project nodig hebben
Moderne werkplek-office-Visio_Install | Gebruikers die Visio nodig hebben

Zodra toepassingen aan deze groepen zijn toegewezen, zijn toepassingen beschikbaar in het bedrijfsportaal. Het kan een paar minuten duren om te synchroniseren, maar dan kunnen uw gebruikers de apps installeren via Company Portal. 

## <a name="communicate-changes"></a>Wijzigingen communiceren
Het is belangrijk dat IT-beheerders hun gebruikers laten weten hoe ze Project en Visio moeten installeren. Dit omvat: 
- Gebruikers op de hoogte stellen wanneer deze toepassingen voor hen beschikbaar zijn. 
- Instructies voor het installeren van deze toepassingen via de Bedrijfsportal.

>[!NOTE]
>Gebruikers moeten alle Office-toepassingen sluiten voordat ze Microsoft Project of Microsoft Visio vanuit Bedrijfsportal installeren. 
