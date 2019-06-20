---
title: Overzicht van instellen
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Overzicht van de stappen instellen voor Microsoft 365 Business.
ms.openlocfilehash: ae7ed0aab36a6e759e0f0c1fbc3d3183273a284e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/15/2019
ms.locfileid: "35086298"
---
# <a name="overview-of-setup"></a>Overzicht van de installatie

De meeste van de instellen van de stappen in de wizard setup kan worden uitgevoerd, maar de andere opties worden ook weergegeven.


## <a name="step-1-add-your-domain-and-users"></a>Stap 1: Uw domein en gebruikers toevoegen

   - **[Uw domein toevoegen](set-up.md#add-your-domain-to-personalize-sign-in)** (als u uw domein tijdens het [aanmelden](sign-up.md)hebt gekocht, wordt deze stap hebt gedaan.)

    - **Gebruikers toevoegen**. U kunt dit op een van de drie manieren doen:
        - In de [wizard](set-up.md#add-users-in-the-wizard).
        - Adreslijstsynchronisatie toevoegen van [gebruikers met Azure AD verbinding](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) gebruiken als u een Active directory op gebouwen.
        - U kunt ook [gebruikers later toevoegen](add-users-m365b.md) in het beheercentrum.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Stap 2: Instellen van beveiligingsbeleid en -apparaten configureren 

  - Gebruik de [wizard Setup van](set-up.md#set-up-security-policies-and-device-configurations) apparaat-en beveiligingsbeleid configureren. 
  - U kunt ook meer toevoegen of bewerken verderop in de [admin center](view-policies-and-devices.md) en in het [portal Intune](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).
  - Naast de instellingen in de wizard setup, kunt u de beveiliging vergroten door de volgende instellingen toe te voegen:

      - **E-mail beveiliging tegen ongewenste software**
      - **Geavanceerde bedreiging (ATB) veilige koppelingen**
      - **ATP veilige bijlagen**
      - **ATP anti-phishing**
      - **Exchange Online Archiving**
      - **Gegevensverlies voorkomen (DLP)**
      - **Azure informatiebeveiliging (Plan1**)

          Zie [Geavanceerde beveiligingsbeleid instellen](set-up-advanced-security.md)om op te halen is gestart.

        Zie ook de [top 10 manieren voor het beveiligen van uw bedrijf Microsoft 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) voor een overzicht van aanbevolen beveiligingsprocedures.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Stap 3: Instellen en beheren van apparaten in Windows 10

   Wanneer u een apparaat met Windows 10 naar Azure AD, krijg het beleid dat u in [stap 2](#step-2-set-up-security-policies-and-configure-devices) hebt ingesteld toegepast.

   - Windows 10 Pro is een [vereist item](pre-requisites-for-data-protection.md) voor Microsoft 365 Business, maar als u Windows 7 Pro, Windows 8 Pro of Windows 8.1 Pro hebt, uw abonnement hebt u recht op een [upgrade naar Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).
    - Gebruik de [wizard setup](set-up.md#set-up-security-policies-and-device-configurations) om beleid voor Windows 10-apparaten te configureren.

## <a name="stes-4-install-office-365-business"></a>Stes 4: Installatie van Office 365 Business
- Automatisch kunt in de Windows-apparaten u Office installeren met de [wizard setup](set-up.md#deploy-office-365-client-apps).
- Automatisch [Office installeren](auto-install-or-uninstall-office.md) vanaf het admin center.
- Laat de gebruikers [installeren Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) voor Windows en apparaten.
     
## <a name="advanced"></a>Geavanceerde
- **Automatische piloot gebruiken voor het instellen van nieuwe apparaten**
            
     U kunt [Windows Automatische piloot](add-autopilot-devices-and-profile.md) automatisch vooraf configureren voor een gebruiker **nieuwe** Windows 10-apparaten, maar is het misschien gemakkelijker om een [partner](https://www.microsoft.com/solution-providers/search) die dit voor u kan doen. U kunt ook gaat u naar de [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) en vragen een deskundige cloud-technologie nieuwe apparaten die u voor u aanschaft ingesteld.

- **Toegang op ruimten resources**

     - Als uw organisatie gebruikmaakt van Windows Server Active Directory op lokalen, kunt u Microsoft 365 Business instellen ter bescherming van uw Windows 10-apparaten, terwijl zij toch toegang tot bronnen voor ruimten die lokale verificatie vereisen. Volg de stappen in [Windows 10-apparaten worden beheerd door Microsoft 365 Business domein behoren](manage-windows-devices.md) tot dit instellen. Dit is de aanbevolen methode en apparaten in deze toestand worden genoemd hybride Azure AD verbonden apparaten.

    - Als uw bedrijf een lokale Active Directory met sommige op-ruimten (zoals bestandsshares en printers), u kunt uw Azure AD verbonden apparaten toegang geven tot deze bronnen door de stappen hier: [toegang op-premises resources uit een Azure AD verbonden apparaat in Microsoft 365 Business](access-resources.md).

  