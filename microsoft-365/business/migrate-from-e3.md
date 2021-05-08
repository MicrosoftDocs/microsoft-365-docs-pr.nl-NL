---
title: Migreren naar Microsoft 365 Business van Office 365 E3
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Meer informatie over het verplaatsen van uw bedrijf Microsoft 365 Business Premium van Office 365 E3.
ms.openlocfilehash: f08b054473fdd63ec2372e81c776a1b64f89fe9d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244831"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Migreren van Office 365 E3 naar Microsoft 365 Business Premium

Microsoft 365 Business Premium heeft alles wat u nodig hebt voor uw kleine bedrijf, waarbij u de beste productiviteits-apps in de cloud combineert met eenvoudig apparaatbeheer en beveiliging. Als u momenteel een Office 365 E3-abonnement hebt, maar niet meer dan 300 werknemers hebt, kunt u overwegen over te schakelen naar Microsoft 365 Business Premium voor extra beveiligingsfuncties.

Migreren is eenvoudig: eerst schakelt u over van licentie en blijven al uw gegevens en gebruikersgegevens in uw huidige abonnement behouden. Na de migratie moet u de functies instellen die in de Microsoft 365 Business Premium.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Verschillen tussen Office 365 E3 en Microsoft 365 Business Premium

In deze tabel ziet u de verschillen tussen Microsoft 365 Business Premium en Office 365 E3.

| Functie    | Ondersteuning in Microsoft 365 Business Premium    | Ondersteuning in Office 365 E3 | 
|:-------|:-----|:-----|
| **On-premises**        | | | 
| Office apps<sup>1</sup>    | Microsoft 365-apps voor bedrijven    | Microsoft 365 Apps voor ondernemingen | 
| **Cloudproductiviteits-apps**        | | | 
| Exchange Online en Outlook    | 50 GB opslaglimiet per postvak en onbeperkte Exchange Online Archiving    | 100 GB opslaglimiet per postvak en onbeperkte Exchange Online Archiving | 
| Teams    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| OneDrive voor Bedrijven    | 1 TB opslaglimiet per gebruiker    | Onbeperkt | 
| Yammer, SharePoint Online, Planner, Stream    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| StaffHub    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| MileIQ    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Bedreigingsbeveiliging**        | | | 
| Defender voor Office 365 Abonnement 1 | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | Niet inbegrepen, maar kan worden toegevoegd aan | 
| **Identiteitsbeheer**        | | | 
| Selfservice password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    |  | 
| **Apparaat- en app-beheer**        | | |
| Microsoft Intune, Windows AutoPilot|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| Activering van gedeelde computer|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png)| 
| Upgraderechten voor Windows 10 Pro van Win 7/8.1 Pro licenties|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    || 
| **Gegevensbeveiliging**        | | |
|Office 365 Preventie van gegevensverlies|    ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)|![Inbegrepen bij Office 365 E3](../media/check-mark.png)|
|Azure Information Protection Plan 1, BitLocker afdwingen|![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)||
|Azure Information Protection Plan 1, Gevoeligheidslabels|![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)||
|**Client Access License (CAL-rechten)**|||
|Enterprise CAL Suite (Exchange, SharePoint, Skype)||![Inbegrepen bij Office 365 E3](../media/check-mark.png)|

<sup>1</sup> De Microsoft 365 Business Premium van de Office-apps bevat geen volumeactivering via groepsbeleid, app-telemetrie, bijwerkbesturingselementen, spreadsheets vergelijken en informeren, of bedrijfsinformatie.

## <a name="migration"></a>Migratie

Zie Abonnementen handmatig [](../commerce/subscriptions/change-plans-manually.md) wijzigen voor instructies als u slechts een paar personen wilt verplaatsen naar Microsoft 365 Business Premium. U kunt ook [iedereen automatisch upgraden](../commerce/subscriptions/upgrade-to-different-plan.md)of samenwerken met een partner om uw E3-abonnement en licenties te verplaatsen naar een Microsoft 365 Business Premium abonnement.
In de volgende secties worden de wijzigingen beschreven die u moet aanbrengen en wat u na de migratie kunt doen.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Office 365 Configuratie en gegevens van E3-abonnement
U hoeft uw huidige abonnement of gegevens niet te wijzigen voordat u migreert, waaronder:

- Abonnementsconfiguratie, zoals DNS-records en domeinnamen.
- Gebruikers- en groepsaccounts en verificatie-instellingen, zoals meervoudige verificatie of beleid voor voorwaardelijke toegang.
- Productiviteitsserviceconfiguraties en hun gegevens, zoals Teams, Exchange Online postvakken, SharePoint Online-sites, OneDrive voor Bedrijven mappen en OneNote notitieblokken.
- Office toepassingen worden automatisch geschaald. Office 365 moderne licenties controleert de licentietoewijzing van de gebruiker om de 72 uur en converteert Office toepassingen naar de versie die overeenkomt met het gebruikersabonnement.

### <a name="windows-10"></a>Windows 10

Als uw Windows nog niet aan de creator-update Windows Pro, kunt u deze upgraden [naar Windows Pro Creators Update.](upgrade-to-windows-pro-creators-update.md)

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Beleidsregels instellen om gebruikersapparaten en bestanden te beveiligen

> [!NOTE]
> Als u Office 365 MDM-beleid en -apparaten in stelt, worden  deze apparaten weergegeven op de pagina Apparaten in het Microsoft 365 beheercentrum. Alle beleidsregels die u hebt ingesteld, worden weergegeven in de lijst met klassieke beleidsregels in de [Intune-portal.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)

Nadat u licenties hebt toegewezen aan Microsoft 365 Business Premium, kunt u de apparaten en bestanden van de gebruikers gaan beveiligen.

Als u iedereen in uw organisatie hebt geüpgraded naar Microsoft 365 Business Premium, ziet u de installatiewizard op de startpagina en kunt u de Microsoft 365 Business Premium instellen volgen [in](set-up.md) de stappen voor de installatiewizard om bestanden en mobiele apparaten te beveiligen.

U kunt deze stappen ook voltooien op de pagina Apparaten:
  
1. Ga in het beheercentrum in het  linkernavigatienavigatiepunt naar \> **Apparatenbeleid.**
    
2. Kies op **de pagina** Apparaatbeleid de optie **Toevoegen**.
    
3. Geef in **het deelvenster** Beleid toevoegen het beleid een naam op en kies vervolgens een **type beleid** in de vervolgkeuzekeuze. 
    
     U kunt toepassingsbeleid instellen voor het beveiligen van bestanden op Android- en iPhone-apparaten, evenals Windows 10, en u kunt apparaatconfiguratiebeleid instellen voor bedrijfsapparaten Windows 10 apparaten. Zie de volgende koppelingen voor meer informatie:
    
  - [Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten](app-protection-settings-for-android-and-ios.md)
    
  - [Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten](protection-settings-for-windows-10-devices.md)
    
  - [Apparaatbeveiligingsinstellingen instellen voor Windows 10 pc's](protection-settings-for-windows-10-pcs.md)
  
4. Nadat u beleidsregels hebt ingesteld, kunnen u en uw werknemers apparaten instellen:
    
  - Zie [Het instellen van Windows apparaten voor Microsoft 365 Business Premium gebruikers](set-up-windows-devices.md) voor stappen voor Windows apparaten. 
    
  - Zie [Mobiele apparaten instellen voor Microsoft 365 Business Premium gebruikers voor](set-up-mobile-devices.md) stappen voor Android-telefoons en iPhones. 
  
### <a name="mailbox-size"></a>Postvakgrootte

Microsoft 365 Business Premium heeft een opslaglimiet van 50 GB voor het gebruik van Exchange Online abonnement 1. Als een van uw gebruikers meer dan 50 GB postvakopslag heeft tijdens het migreren naar Microsoft 365 Business Premium, wordt u aangeraden deze gebruiker een Exchange Online-abonnement 2 toe te wijzen en het Exchange Online-abonnement 1 te verwijderen omdat het niet haalbaar is om beide toe te wijzen.


### <a name="threat-protection"></a>Bedreigingsbeveiliging

Na de migratie naar Microsoft 365 Business Premium, hebt u Defender voor Office 365. Zie [Microsoft Defender voor Office 365](../security/office-365-security/defender-for-office-365.md) voor een overzicht. Zie Het instellen van [Safe Koppelingen](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)instellen, Safe [Bijlagen](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)instellen en [Anti-phishing instellen in Defender](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)voor Office 365.

### <a name="sensitivity-labels"></a>Vertrouwelijkheidslabels

Zie Overzicht van gevoeligheidslabels en het maken en beheren van [gevoeligheidslabels](../business-video/create-sensitivity-labels.md) video als u gevoeligheidslabels wilt gebruiken. [](../compliance/sensitivity-labels.md)
