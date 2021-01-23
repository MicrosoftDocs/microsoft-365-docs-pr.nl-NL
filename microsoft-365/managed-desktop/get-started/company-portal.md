---
title: InTune-bedrijfs portal installeren op apparaten
description: Info over het installeren van de bedrijfsportal-app op Microsoft beheerde bureaublad apparaten
keywords: Microsoft Managed Desktop, Microsoft 365, Company Portal
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bddf46e451408e4f17e58cc62186b7cd6cefb382
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939282"
---
# <a name="install-intune-company-portal-on-devices"></a>InTune-bedrijfs portal installeren op apparaten

Voor Microsoft Managed Desktop moet de IT-beheerder intune Company Portal installeren voor hun gebruikers met Microsoft beheerde bureaublad apparaten. Hier volgen enkele voordelen voor uw organisatie:
- Gebruikers hebben één locatie om de beschikbare toepassingen te zoeken en te installeren. 
- IT-beheerders kunnen toepassingen organiseren op basis van categorieën voor hun gebruikers.  
- Voor sommige toepassingen (zoals Microsoft Project en Microsoft Visio) is bedrijfs portal vereist voor de implementatie met Microsoft Managed Desktop.
- IT-beheerders kunnen de bedrijfs portal voor hun organisatie aanpassen. Dit omvat merk afbeelding, toevoegen in lokale ondersteunings contactpersonen, en meer. Zie [de Microsoft intune Company Portal-app configureren](https://docs.microsoft.com/intune/company-portal-app)voor meer informatie.   

In dit onderwerp worden de stappen beschreven voor de implementatie van de intune-bedrijfs portal naar Microsoft beheerde bureaubladgebruikers. Het algehele proces ziet er als volgt uit:
1. Bedrijfs portal in Microsoft Store voor bedrijven kopen en synchroniseren met intune
2. Bedrijfs portal aan uw gebruikers toewijzen
3. Wijziging communiceren met uw gebruikers

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Stap 1: de bedrijfs portal van Microsoft Store voor bedrijven kopen en synchroniseren met intune
Voor informatie over het aanschaffen van de apps en het synchroniseren met intune raadpleegt u [Microsoft Store for Business-Apps](deploy-apps.md#msfb-apps) in *apps implementeren voor Microsoft Managed Desktop devices*.

Dit onderwerp bevat informatie over het volgende: 
- Bedrijfs portal kopen via Microsoft Store voor bedrijven 
- Synchronisatie tussen intune en Microsoft Store voor bedrijven afdwingen
- Actieve synchronisatie tussen intune en Microsoft Store voor bedrijven controleren 

## <a name="step-2---assign-company-portal-to-your-users"></a>Stap 2-de bedrijfs portal aan uw gebruikers toewijzen
Als u de registratie volgt in Microsoft Managed Desktop, wordt de bedrijfs portal automatisch geïmplementeerd voor uw Tenant en installeert u de app op Microsoft beheerde bureaublad apparaten in uw organisatie.

## <a name="step-3---communicate-change-to-your-users"></a>Stap 3: de wijziging doorgeven aan uw gebruikers
Als IT-beheerder voor uw organisatie, is het belangrijk om uw gebruikers te laten weten hoe ze de bedrijfs portal in uw organisatie kunnen gebruiken. Microsoft Managed Desktop adviseert:
- Stappen voor het installeren van toepassingen vanuit de bedrijfs portal. Zie [apps op uw apparaat installeren en delen](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)voor meer informatie.
- Hoe u aanvragen naar IT-beheerders verzendt voor toepassingen die momenteel niet beschikbaar zijn. Zie [een app voor werk of school aanvragen](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)voor meer informatie.  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Stappen om aan de slag te gaan met Microsoft Managed Desktop

1. [Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal](add-admin-contacts.md)
2. [Voorwaardelijke toegang aanpassen](conditional-access.md)
3. [Licenties toewijzen](assign-licenses.md)
4. InTune Company Portal (dit onderwerp) implementeren
5. [Enterprise State Roaming inschakelen](enterprise-state-roaming.md)
6. [Apparaten instellen](set-up-devices.md)
7. [Uw gebruikers voorbereiden om apparaten te gebruiken](get-started-devices.md)
8. [Apps implementeren](deploy-apps.md)
