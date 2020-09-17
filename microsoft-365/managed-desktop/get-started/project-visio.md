---
title: Microsoft Project of Microsoft Visio installeren op de beheerde bureaublad apparaten van Microsoft
description: Info over het installeren van Microsoft Project of Microsoft Visio op desktop computers met Microsoft beheerd
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
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Microsoft Project of Microsoft Visio installeren op de beheerde bureaublad apparaten van Microsoft

In Microsoft Project en Microsoft Visio zijn bepaalde stappen vereist voor het installeren van op Microsoft beheerde bureaublad apparaten. In dit onderwerp worden de vereisten en installatieprocessen voor deze toepassingen gedocumenteerd.

## <a name="prerequisites"></a>Vereisten

Beheerders moet controleren of ze aan de volgende vereisten voldoen:
- **Aantal licenties** : de juiste hoeveelheid Microsoft Project-en Microsoft Visio-licenties moeten beschikbaar zijn voor uw gebruikers. Microsoft Managed Desktop biedt momenteel alleen ondersteuning voor 64-bits versies van deze toepassingen. 
- **Licentie namen** : de juiste licentie namen voor deze toepassingen zijn:
    - **Microsoft Project** -project online Professional of project online Premium
    - **Microsoft Visio** -Visio online-abonnement 2
- **Bedrijfsportal** : de bedrijfsportal moet beschikbaar zijn in uw Tenant, zodat uw gebruikers deze toepassingen kunnen installeren. Zie [Company Portal](company-portal.md)als de bedrijfs portal niet is geïmplementeerd in uw Tenant.

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Project en Visio voor Microsoft beheerde bureaublad apparaten implementeren
Microsoft Managed Desktop zal Microsoft Project en Microsoft Visio toevoegen als twee Win32-toepassingen in Microsoft intune. U maakt ook twee groepen in azure Active Directory, die aan de bijbehorende toepassing wordt toegewezen met de beschikbaarheid ' beschikbare '. 

**Project en Visio implementeren** Voeg de gebruiker toe aan de juiste groep en de toepassing wordt beschikbaar in de bedrijfs portal. Het kan een paar minuten duren voor synchronisatie, maar de gebruikers kunnen de apps van de bedrijfs portal installeren. 

Naam van Azure AD-groep | Welke gebruikers moeten ze toewijzen?   
 --- | ---
Modern Workplace-Office-Project_Install | Gebruikers die project nodig hebben
Modern Workplace-Office-Visio_Install | Gebruikers die Visio nodig hebben

## <a name="communicate-changes"></a>Wijzigingen doorgeven
Het is belangrijk dat IT-beheerders hun gebruikers laten weten hoe ze project en Visio moeten installeren. Dit omvat: 
- Gebruikers op de hoogte stellen van de beschikbare toepassingen. 
- Instructies voor het installeren van deze toepassingen via de bedrijfs portal.
