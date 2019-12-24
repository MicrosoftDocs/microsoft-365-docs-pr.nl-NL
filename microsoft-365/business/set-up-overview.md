---
title: Overzicht van instellingen
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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Overzicht van de installatie stappen voor Microsoft 365 Business.
ms.openlocfilehash: 4aca617015cceb85ca35c8d8ada7b83d1416d959
ms.sourcegitcommit: 178ecb21cacdeaf440f3df2fe6e539e9127fcf15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/23/2019
ms.locfileid: "40850799"
---
# <a name="overview-of-setup"></a>Overzicht van instellingen

Bekijk een korte video over Microsoft 365 Business Setup.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Als u deze video nuttig vond, Bekijk dan de [complete trainingreeks voor kleine bedrijven en die nieuw bij Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

De meeste installatie stappen kunnen worden uitgevoerd in de installatiewizard, maar de andere opties worden ook weergegeven.

## <a name="step-1-add-your-domain-and-users"></a>Stap 1: Voeg uw domein en gebruikers toe

   - **[Voeg uw domein toe](set-up.md#add-your-domain-to-personalize-sign-in)** (als u uw domein heeft gekocht tijdens het [Aanmelden](sign-up.md), is deze stap al gedaan.)

    - **Gebruikers toevoegen**. U op de volgende drie manieren gebruikers toevoegen:
        - In de [wizard](set-up.md#add-users-in-the-wizard).
        - Gebruik adreslijstsynchronisatie om [gebruikers toe te voegen met behulp van Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) als u een on-premises Active Directory hebt.
        - U ook [gebruikers later toevoegen](add-users-m365b.md) in het Admin Center.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Stap 2: beveiligingsbeleid instellen en apparaten configureren 

  - Gebruik de [wizard Setup](set-up.md#protect-your-organization) om apparaatbeleid te configureren. 
  - U ook meer toevoegen of later bewerken in het [Beheercentrum](view-policies-and-devices.md) en in de [intune-Portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).
  - De instelwizard stelt ook de instellingen voor preventie van bescherming en gegevensverlies in.
  
  Naast de beveiligingsinstellingen in de installatiewizard u de beveiliging verhogen door de volgende instellingen toe te voegen:

- **E-malware bescherming**
- **ATP anti-phishing**
- **Exchange Online Archiving**
- **Azure Information Protection (Plan1**)

Zie [Geavanceerd beveiligingsbeleid instellen](set-up-advanced-security.md)om aan de slag te gaan.

Zie ook [de Top 10-manieren om uw Microsoft 365-bedrijf te beveiligen](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) voor een roadmap van de beste beveiligingspraktijken.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Stap 3: Windows 10-apparaten instellen en beheren

Nadat u de wizard instellen hebt uitgevoerd, wilt u alle Windwos 10-computers in uw organisatie proctect.
  
- Windows 10 Pro is een [vereiste](pre-requisites-for-data-protection.md) voor microsoft 365 Business, maar als u Windows 7 Pro, Windows 8 Pro of Windows 8,1 Pro hebt, geeft uw abonnement u recht op een [upgrade naar Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).
- Volg de stappen in [beveiligde Windows 10-pc's](secure-win-10-pcs.md) om beleid in te stellen voor Windows 10-apparaten.

Wanneer u lid wordt van een Windows 10-apparaat naar Azure AD, wordt het beleid dat u voor Windows 10-computers hebt ingesteld op deze toegepast. Zie [Windows-apparaten instellen voor Microsoft 365 zakelijke gebruikers](set-up-windows-devices.md)voor meer informatie.

## <a name="step-4-install-office-365-business"></a>Stap 4: Installeer Office 365 Business
- U Office op de Windows-apparaten automatisch installeren met behulp van de [wizard Setup](set-up.md#deploy-office-365-client-apps).
- Laat gebruikers [Office-apps](https://docs.microsoft.com/office365/admin/setup/install-applications) voor Windows en apparaten installeren.
     
## <a name="advanced"></a>Geavanceerde
- **Autopilot gebruiken om nieuwe apparaten in te stellen**
            
     U [Windows Autopilot](add-autopilot-devices-and-profile.md) gebruiken voor het automatisch vooraf configureren van **nieuwe** Windows 10-apparaten voor een gebruiker, maar het is misschien gemakkelijker om een [partner](https://www.microsoft.com/solution-providers/search) die dit voor u kan doen. U ook naar de [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)gaan en een cloudtechnologie-expert vragen om nieuwe apparaten in te stellen die u aanschaft.

- **Toegang tot on-premises bronnen**

     - Als uw organisatie gebruikmaakt van on-premises Windows Server Active Directory, u Microsoft 365 Business instellen om uw Windows 10-apparaten te beveiligen, terwijl u nog steeds toegang hebt tot on-premises bronnen waarvoor lokale verificatie is vereist. Volg de stappen in [Windows 10-apparaten met een domein verbinding inschakelen die door Microsoft 365 Business worden beheerd](manage-windows-devices.md) om dit in te stellen. Dit is de voorkeursmethode en apparaten in deze status worden hybride Azure AD gekoppelde apparaten genoemd.

    - Als uw bedrijf een lokale Active Directory heeft die bepaalde on-premises bronnen bevat (zoals bestandsshares en printers), u uw Azure AD-gekoppelde apparaten toegang geven tot deze resources door de stappen hier te volgen: [toegang tot on-premises resources van een Azure AD-apparaat in Microsoft 365 Business](access-resources.md).

## <a name="see-also"></a>Zie ook

[Microsoft 365 zakelijke trainingsvideo's](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
