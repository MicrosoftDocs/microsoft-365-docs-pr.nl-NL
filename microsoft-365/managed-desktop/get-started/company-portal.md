---
title: Intune Company Portal installeren op apparaten
description: Informatie over het installeren van de bedrijfsportal-app op Microsoft Managed Desktop-apparaten
keywords: Microsoft Managed Desktop, Microsoft 365, Bedrijfsportal
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 371656168f32db86ff32f187736d59dbd5dbe749
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529693"
---
# <a name="install-intune-company-portal-on-on-devices"></a>InTune-bedrijfsportal installeren op apparaten

Microsoft Managed Desktop vereist dat IT-beheerders Intune Company Portal installeren voor hun gebruikers met Microsoft Managed Desktop-apparaten. Hier zijn enkele voordelen voor uw organisatie:
- Gebruikers hebben één plek om beschikbare toepassingen te bekijken en te installeren. 
- IT-beheerders kunnen toepassingen organiseren op categorieën voor hun gebruikers.  
- Voor sommige toepassingen (zoals Microsoft Project en Microsoft Visio) moet Bedrijfportal worden geïmplementeerd met Microsoft Managed Desktop.
- IT-beheerders kunnen Bedrijfsportal aanpassen voor hun organisatie. Dit omvat merkbeeldvorming, het toevoegen van lokale ondersteuningscontacten en meer. Zie [De Microsoft Intune Company Portal-app configureren](https://docs.microsoft.com/intune/company-portal-app)voor meer informatie.   

In dit onderwerp wordt het proces voor het implementeren van de Intune Company Portal voor uw Microsoft Managed Desktop-gebruikers documenteert. Het totale proces ziet er als volgt uit:
1. Bedrijfsportal kopen in De Microsoft Store voor Bedrijven en synchroniseer met Intune
2. Bedrijfsportal toewijzen aan uw gebruikers
3. Wisselgeld doorgeven aan uw gebruikers

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Stap 1 - Bedrijfsportal kopen in Microsoft Store voor Bedrijven en synchroniseren met Intune
Zie [Microsoft Store voor Bedrijven-apps](deploy-apps.md#msfb-apps) in Apps implementeren in Apps implementeren op *Microsoft Managed Desktop-apparaten voor*informatie over de aankoop van de apps en synchronisatie met Intune.

In dit onderwerp vindt u informatie over het plaatsen van: 
- Bedrijfsportal kopen in de Microsoft Store voor Bedrijven 
- Synchronisatie tussen Intune en Microsoft Store voor Bedrijven forceren
- Actieve synchronisatie tussen Intune en Microsoft Store voor Bedrijven verifiëren 

## <a name="step-2---assign-company-portal-to-your-users"></a>Stap 2 - Bedrijfsportal toewijzen aan uw gebruikers
Dien een ondersteuningsverzoek in bij Microsoft Managed Desktop Operations via de Microsoft Managed Desktop Admin-portal. Vraag in het ondersteuningsverzoek om Bedrijfsportal toe te wijzen aan uw gebruikers. Microsoft Managed Desktop implementeert Bedrijfsportal naar uw tenant en installeert de app op Microsoft Managed Desktop-apparaten in uw organisatie.

Zie Beheerdersondersteuning voor Microsoft Managed Desktop voor meer informatie over het indienen van [ondersteuningsaanvragen](../working-with-managed-desktop/admin-support.md)bij Microsoft Managed Desktop.

## <a name="step-3---communicate-change-to-your-users"></a>Stap 3 - Wissel wijzigingen door uw gebruikers
Als IT-beheerder voor uw organisatie is het belangrijk om uw gebruikers te laten weten hoe ze Bedrijfsportal in uw organisatie kunnen gebruiken. Microsoft Managed Desktop raadt aan:
- Stappen voor het installeren van toepassingen vanuit de Bedrijfsportal. Zie [Apps installeren en delen op uw apparaat voor](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)meer informatie.
- Aanvragen verzenden naar IT-beheerders voor toepassingen die momenteel niet beschikbaar zijn. Zie [Een app aanvragen voor werk of school voor](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)meer informatie.  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Stappen om aan de slag te gaan met Microsoft Managed Desktop

1. [Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal](add-admin-contacts.md)
2. [Voorwaardelijke toegang aanpassen](conditional-access.md)
3. [Licenties toewijzen](assign-licenses.md)
4. Intune Company Portal implementeren (dit onderwerp)
5. [Enterprise State Roaming inschakelen](enterprise-state-roaming.md)
6. [Apparaten instellen](set-up-devices.md)
7. [Uw gebruikers voorbereiden om apparaten te gebruiken](get-started-devices.md)
8. [Apps implementeren](deploy-apps.md)
