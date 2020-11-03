---
title: Overzicht van instelling
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Meer informatie over de installatiestappen voor Microsoft 365 Business Premium, van een abonnement, het toevoegen van een domein en gebruikers, het instellen van beveiligingsbeleid en meer.
ms.openlocfilehash: 8ec01a58d1a15d5c4aa1cef8b81518b474630d8b
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841129"
---
# <a name="overview-of-setup"></a>Overzicht van instelling

Bekijk een korte video over het instellen van Microsoft 365 Business Premium.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Als je deze video nuttig vond, raadpleeg dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

U kunt de meeste installatiestappen uitvoeren in de begeleide installatie, maar de andere opties worden ook weergegeven.

## <a name="step-1-add-your-domain-and-users"></a>Stap 1: uw domein en gebruikers toevoegen

   - **[Uw domein toevoegen](set-up.md#add-your-domain-to-personalize-sign-in)** (als u uw domein hebt gekocht tijdens de [registratie](sign-up.md), is deze stap al gereed.)

   - **Gebruikers toevoegen** . U kunt gebruikers op de volgende drie manieren toevoegen:
        - In de [begeleide setup](set-up.md#add-users-in-the-wizard).
        - Gebruik adreslijstsynchronisatie om [gebruikers toe te voegen met behulp van Azure AD Connect](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) als u een on-premises Active Directory hebt.
        - U kunt ook [gebruikers later toevoegen](add-users-m365b.md) in het Beheercentrum.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Stap 2: beveiligingsbeleid instellen en apparaten configureren 

  - Met behulp van de [Guided Setup](set-up.md#protect-your-organization) de beleidsregels voor apparaten configureren. 
  - U kunt ze later ook toevoegen of bewerken in het [Beheercentrum](view-policies-and-devices.md) en in de [intune-Portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).
  - Met de installatiewizard kunt u ook instellingen voor basisbeveiliging en preventie van gegevensverlies instellen.
  
  Naast de beveiligingsinstellingen van de wizard Setup kunt u de beveiliging verhogen door de volgende instellingen toe te voegen:

- **Beveiliging tegen ongewenste e-mail**
- **ATP anti-phishing**
- **Exchange Online Archiving**
- **Azure-informatiebescherming (Plan1** )

Zie de [bedreigings bescherming](increase-threat-protection.md) en de [compliance-functies instellen](set-up-compliance.md)om aan de slag te gaan.

Zie ook [de tien beste manieren om uw abonnement op Microsoft 365 Business Premium te beschermen](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) voor een overzicht van de best mogelijke beveiligingsmaatregelen.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Stap 3: Windows 10-apparaten instellen en beheren

Wanneer u klaar bent met de installatie, kunt u alle computers met Windows 10 in uw organisatie beveiligen.
  
- Windows 10 Pro is een [vereiste](pre-requisites-for-data-protection.md) voor microsoft 365 Business Premium, maar als u Windows 7 Pro, Windows 8 Pro of Windows 8,1 Pro hebt, geeft uw abonnement u recht op een [upgrade naar Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).
- Volg de stappen in een [veilig Windows 10](secure-win-10-pcs.md) -apparaat om het beleid voor Windows 10-apparaten in te stellen.

Wanneer u deelneemt aan een Windows 10-apparaat aan Azure AD, worden de beleidsregels die u instelt voor Windows 10-computers toegepast. Zie [Windows-apparaten instellen voor Microsoft 365-gebruikers](set-up-windows-devices.md)voor meer informatie.

## <a name="step-4-install-microsoft-365-apps-for-business"></a>Stap 4: Microsoft 365-apps voor bedrijven installeren
- U kunt Office automatisch installeren op de Windows-apparaten met behulp van de [installatiewizard](set-up.md#deploy-office-365-client-apps).
- Laat gebruikers [Office-apps](https://docs.microsoft.com/office365/admin/setup/install-applications) voor Windows en apparaten installeren.
     
## <a name="advanced"></a>Advanced
- **Auto Pilot gebruiken om nieuwe apparaten in te stellen**
            
     U kunt de [Windows auto pilot](add-autopilot-devices-and-profile.md) gebruiken om **nieuwe** Windows 10-apparaten automatisch vooraf te configureren voor een gebruiker, maar het is mogelijk makkelijker om een [partner](https://www.microsoft.com/solution-providers/search) te krijgen die dit voor u kan doen. U kunt ook naar [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)gaan en een expert voor de Cloud Technology vragen om nieuwe apparaten die u koopt in te stellen.

- **Toegang tot on-premises bronnen**

     - Als uw organisatie Windows Server Active Directory on-premises gebruikt, kunt u Microsoft 365 Business Premium instellen voor de bescherming van uw Windows 10-apparaten, terwijl u nog steeds toegang hebt tot on-premises bronnen waarvoor lokale verificatie is vereist. Voer de stappen uit in [Windows 10-apparaten die aan een domein zijn toegevoegd om te worden beheerd door Microsoft 365 Business Premium](manage-windows-devices.md) om dit in te stellen. Dit is de methode van de voorkeur en de apparaten in deze status worden hybride, Azure AD aangevoegde apparaten genoemd.

    - Als uw bedrijf een lokale Active Directory heeft met een aantal on-premises resources (zoals bestanden en printers), kunt u uw Azure Active Directory-apparaten toegang verlenen tot de bronnen door deze stappen te volgen: [on-premises resources openen vanuit een Azure AD-domein dat is gekoppeld aan Microsoft 365 Business Premium](access-resources.md).

## <a name="see-also"></a>Zie ook

[Trainingsvideo's voor Microsoft 365 voor bedrijven](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
