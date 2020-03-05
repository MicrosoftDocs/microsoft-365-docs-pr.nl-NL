---
title: Overzicht van de installatie
f1.keywords:
- NOCSH
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
- OKR_SMB_M365
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Meer informatie over de installatiestappen voor Microsoft 365 Business, van een abonnement, het toevoegen van een domein en gebruikers, tot het instellen van beveiligingsbeleid en meer.
ms.openlocfilehash: 75ef784a886de754e7550d9e86af1242209346dd
ms.sourcegitcommit: d6c871bf3f94d9299d22695f5dbaf25dc1bd6ff9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2020
ms.locfileid: "42417221"
---
# <a name="overview-of-setup"></a>Overzicht van de installatie

Bekijk een korte video over microsoft 365 Business setup.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Als u deze video nuttig vond, raadpleegt u dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

De meeste installatiestappen kunnen worden uitgevoerd in de installatiewizard, maar de andere opties worden ook weergegeven.

## <a name="step-1-add-your-domain-and-users"></a>Stap 1: Uw domein en gebruikers toevoegen

   - **[Voeg uw domein toe](set-up.md#add-your-domain-to-personalize-sign-in)** (als u uw domein hebt gekocht tijdens [het aanmelden,](sign-up.md)is deze stap al gedaan.)

    - **Gebruikers toevoegen**. U gebruikers op een van de drie manieren toevoegen:
        - In de [wizard](set-up.md#add-users-in-the-wizard).
        - Gebruik adreslijstsynchronisatie om [gebruikers toe te voegen met Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) als u een on-premises Active-map hebt.
        - U later ook [gebruikers toevoegen](add-users-m365b.md) in het beheercentrum.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Stap 2: Beveiligingsbeleid instellen en apparaten configureren 

  - Gebruik de [wizard Setup](set-up.md#protect-your-organization) om apparaatbeleid te configureren. 
  - U ze ook meer toevoegen of later bewerken in het [beheercentrum](view-policies-and-devices.md) en in de [Intune-portal.](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)
  - De installatiewizard stelt ook instellingen voor het voorkomen van bedreigingen en gegevensverlies in.
  
  Naast de beveiligingsinstellingen in de wizard Setup u uw beveiliging verhogen door de volgende instellingen toe te voegen:

- **Bescherming tegen malware e-mail**
- **ATP anti-phishing**
- **Exchange Online Archiving**
- **Azure-informatiebeveiliging (Plan1**)

Zie [de bescherming](increase-threat-protection.md) van bedreigingen vergroten en [nalevingsfuncties instellen](set-up-compliance.md)om aan de slag te gaan.

Bekijk ook [top 10 manieren om uw Microsoft 365 Business te beveiligen](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) voor een roadmap van beste beveiligingsprocedures.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Stap 3: Windows 10-apparaten instellen en beheren

Nadat u de wizard set-up hebt uitgevoerd, wilt u alle Windwos 10-computers in uw organisatie proctect.
  
- Windows 10 Pro is een [voorwaarde](pre-requisites-for-data-protection.md) voor Microsoft 365 Business, maar als u Windows 7 Pro, Windows 8 Pro of Windows 8.1 Pro hebt, geeft uw abonnement recht op een [upgrade naar Windows 10 Pro.](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)
- Volg de stappen in [beveiligde Windows 10-pc's](secure-win-10-pcs.md) om beleid voor Windows 10-apparaten in te stellen.

Wanneer u lid wordt van een Windows 10-apparaat op Azure AD, wordt het beleid dat u instelt voor Windows 10-computers erop toegepast. Zie [Windows-apparaten instellen voor Microsoft 365 Business-gebruikers](set-up-windows-devices.md)voor meer informatie.

## <a name="step-4-install-office-365-business"></a>Stap 4: Office 365 Bedrijven installeren
- U Office automatisch installeren in de Windows-apparaten met de [wizard Setup](set-up.md#deploy-office-365-client-apps).
- Laat gebruikers [Office-apps](https://docs.microsoft.com/office365/admin/setup/install-applications) voor Windows en apparaten installeren.
     
## <a name="advanced"></a>Geavanceerde
- **Autopilot gebruiken om nieuwe apparaten in te stellen**
            
     U [Windows Autopilot](add-autopilot-devices-and-profile.md) gebruiken om automatisch **nieuwe** Windows 10-apparaten voor een gebruiker te configureren, maar het is misschien gemakkelijker om een [partner](https://www.microsoft.com/solution-providers/search) te vinden die dit voor u kan doen. U ook naar [de Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)gaan en een expert op het gebied van cloudtechnologie vragen om nieuwe apparaten in te stellen die u koopt.

- **On-premises bronnen toegang**

     - Als uw organisatie On-premises gebruik maakt van Windows Server Active Directory, u Microsoft 365 Business instellen om uw Windows 10-apparaten te beschermen, terwijl u nog steeds toegang behoudt tot on-premises bronnen waarvoor lokale verificatie vereist is. Volg de stappen in [Windows 10-apparaten inschakelen die door Microsoft 365 Business moeten worden beheerd](manage-windows-devices.md) om dit in te stellen. Dit is de voorkeursmethode en apparaten in deze status worden hybride Azure AD-verbonden apparaten genoemd.

    - Als uw bedrijf een lokale Active Directory heeft die een aantal on-premises bronnen bevat (zoals bestandsshares en printers), u uw azure AD-apparaten toegang geven tot deze bronnen door de stappen hier te volgen: [On-premises bronnen openen vanaf een Azure AD-verbonden apparaat in Microsoft 365 Business](access-resources.md).

## <a name="see-also"></a>Zie ook

[Trainingsvideo's voor Microsoft 365 Business](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
