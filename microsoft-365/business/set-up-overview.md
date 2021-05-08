---
title: Overzicht van instelling
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Lees de installatiestappen voor Microsoft 365 Business Premium, van een abonnement, het toevoegen van een domein en gebruikers tot het instellen van beveiligingsbeleid en meer.
ms.openlocfilehash: 008a5c51698589667acc0d01649f67dab33b4c58
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245059"
---
# <a name="overview-of-setup"></a>Overzicht van instelling

Bekijk een korte video over het Microsoft 365 Business Premium instellen.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Als je deze video nuttig vond, raadpleeg dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](../business-video/index.yml).

De meeste installatiestappen kunnen worden uitgevoerd in de begeleide installatie, maar de andere opties worden ook weergegeven.

## <a name="step-1-add-your-domain-and-users"></a>Stap 1: Uw domein en gebruikers toevoegen

   - **[Voeg uw domein](set-up.md#add-your-domain-to-personalize-sign-in)** toe (als u uw domein hebt gekocht tijdens het [aanmelden,](sign-up.md)is deze stap al gedaan.)

   - **Gebruikers toevoegen.** U kunt gebruikers op een van de drie manieren toevoegen:
        - In de [begeleide installatie](set-up.md#add-users-in-the-wizard).
        - Gebruik adreslijstsynchronisatie om gebruikers toe te voegen met [Azure AD-Verbinding maken](../enterprise/set-up-directory-synchronization.md) als u een on-premises Active Directory hebt.
        - U kunt later [ook gebruikers toevoegen](../admin/add-users/add-users.md) in het beheercentrum.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Stap 2: Beveiligingsbeleid instellen en apparaten configureren 

  - Gebruik de [geleide instelling om](set-up.md#protect-your-organization) apparaatbeleid te configureren. 
  - U kunt er ook meer toevoegen of later bewerken in het [beheercentrum](view-policies-and-devices.md) en in de [Intune-portal.](/intune/tutorial-walkthrough-intune-portal)
  - De installatiewizard stelt ook basisinstellingen voor bedreigingsbeveiliging en preventie van gegevensverlies in.
  
  Naast de beveiligingsinstellingen in de installatiewizard kunt u uw beveiliging verhogen door de volgende instellingen toe te voegen:

- **Beveiliging tegen e-mail malware**
- **Anti-phishing in Defender voor Office 365**
- **Exchange Online Archiving**
- **Azure Information Protection (Plan1**)

Zie Bedreigingsbeveiliging [vergroten en](increase-threat-protection.md) compliancefuncties instellen om aan de slag te [gaan.](set-up-compliance.md)

Bekijk ook [de tien belangrijkste manieren om uw](/office365/admin/security-and-compliance/secure-your-business-data) Microsoft 365 Business Premium te beveiligen voor een routekaart met de beste beveiligingsprocedures.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Stap 3: Apparaten instellen en Windows 10 beheren

Nadat u de begeleide installatie hebt voltooid, wilt u alle Windows 10 computers in uw organisatie beschermen.
  
- Windows 10 Pro is een [](pre-requisites-for-data-protection.md) vereiste voor Microsoft 365 Business Premium, maar als u Windows 7 Pro, Windows 8 Pro of Windows 8.1 Pro hebt, geeft uw abonnement u recht op een [upgrade naar Windows 10 Pro.](./upgrade-to-windows-pro-creators-update.md)
- Volg de stappen in [beveiligde Windows 10 pc's om](secure-win-10-pcs.md) beleid in te stellen voor Windows 10 apparaten.

Wanneer u een apparaat Windows 10 Azure AD, worden de beleidsregels die u voor Windows 10 computers hebt ingesteld, toegepast op het apparaat. Zie Voor meer informatie [Het instellen van Windows apparaten voor Microsoft 365 gebruikers.](set-up-windows-devices.md)

## <a name="step-4-install-microsoft-365-apps-for-business"></a>Stap 4: Microsoft 365-apps voor bedrijven
- U kunt automatisch Office installeren in de Windows apparaten met behulp van de [installatiewizard.](set-up.md#deploy-office-365-client-apps)
- Gebruikers kunnen [Office apps voor](/office365/admin/setup/install-applications) Windows en apparaten installeren.
     
## <a name="advanced"></a>Advanced
- **Autopilot gebruiken om nieuwe apparaten in te stellen**
            
     U kunt [Windows Autopilot](add-autopilot-devices-and-profile.md) gebruiken om automatisch nieuwe **Windows 10-apparaten** voor een gebruiker te configureren, maar het is misschien gemakkelijker om een [partner](https://www.microsoft.com/solution-providers/search) te vinden die dit voor u kan doen. U kunt ook naar [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)en een cloudtechnologiedeskundige vragen om nieuwe apparaten in te stellen die u koopt.

- **Toegang tot on-premises bronnen**

     - Als uw organisatie on-premises Windows Server Active Directory gebruikt, kunt u Microsoft 365 Business Premium instellen om uw Windows 10-apparaten te beveiligen, met behoud van toegang tot on-premises resources waarvoor lokale verificatie vereist is. Volg de stappen in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set this up. Dit is de voorkeursmethode en apparaten in deze status worden verbonden met hybride Azure AD-apparaten genoemd.

    - Als uw bedrijf een lokale Active Directory heeft die een aantal on-premises resources bevat (zoals bestandsaandelen en printers), kunt u uw apparaten met Azure AD toegang geven tot deze bronnen door de volgende stappen te volgen: On-premises resources openen vanaf een [azure AD-apparaat in Microsoft 365 Business Premium](access-resources.md).

## <a name="related-content"></a>Verwante onderwerpen

[Microsoft 365 voor zakelijke trainingsvideo's](../business-video/index.yml) (koppelingspagina)