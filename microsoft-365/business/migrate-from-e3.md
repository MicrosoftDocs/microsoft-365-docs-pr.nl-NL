---
title: Migreren naar Microsoft 365 Business vanuit Office 365 E3
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Meer informatie over het verplaatsen van uw bedrijf naar Microsoft 365 Business Premium vanuit Office 365 E3.
ms.openlocfilehash: 3f9fd70b2d31b32027981e638de249d92e98ea08
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164528"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Migreren van Office 365 E3 naar Microsoft 365 Business Premium

Microsoft 365 Business Premium heeft alles wat u nodig hebt voor uw kleine bedrijf, waarbij de beste productiviteitsapps in de cloud worden gecombineerd met eenvoudig apparaatbeheer en beveiliging. Als u momenteel een Office 365 E3-abonnement hebt, maar niet meer dan 300 werknemers hebt, kunt u overwegen over te stappen op Microsoft 365 Business Premium voor extra beveiligingsfuncties.

Migreren is eenvoudig: eerst schakelt u over van licentie en blijven al uw gegevens en gebruikersgegevens in uw huidige abonnement behouden. Na de migratie moet u de functies instellen die worden toegevoegd in Microsoft 365 Business Premium.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Verschillen tussen Office 365 E3 en Microsoft 365 Business Premium

In deze tabel ziet u de verschillen tussen Microsoft 365 Business Premium en Office 365 E3.

| Functie    | Ondersteuning in Microsoft 365 Business Premium    | Ondersteuning in Office 365 E3 | 
|:-------|:-----|:-----|
| **On-premises**        | | | 
| Office-apps<sup>1</sup>    | Microsoft 365-apps voor bedrijven    | Microsoft 365-apps voor ondernemingen | 
| **Cloudproductiviteits-apps**        | | | 
| Exchange Online en Outlook    | 50 GB opslaglimiet per postvak en onbeperkte Archivering van Exchange Online    | 100 GB opslaglimiet per postvak en onbeperkte Archivering van Exchange Online | 
| Teams    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| OneDrive voor Bedrijven    | 1 TB opslaglimiet per gebruiker    | Onbeperkt | 
| Yammer, SharePoint Online, Planner, Stream    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| StaffHub    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| Outlook Customer Manager    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Bedreigingsbeveiliging**        | | | 
| Defender voor Office 365 Abonnement 1 | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | Niet inbegrepen, maar kan worden toegevoegd aan | 
| **Identiteitsbeheer**        | | | 
| Selfservice password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    |  | 
| **Apparaat- en app-beheer**        | | |
| Microsoft Intune, Windows AutoPilot|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| Activering van gedeelde computer|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png)| 
| Upgraderechten voor Windows 10 Pro van Win 7/8.1 Pro-licenties|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    || 
| **Gegevensbeveiliging**        | | |
|Preventie van gegevensverlies in Office 365|    ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)|![Inbegrepen bij Office 365 E3](../media/check-mark.png)|
|Azure Information Protection Plan 1, Bitlocker enforcement|![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)||
|Azure Information Protection Plan 1, Gevoeligheidslabels|![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)||
|**Client Access License (CAL-rechten)**|||
|Enterprise CAL Suite (Exchange, SharePoint, Skype)||![Inbegrepen bij Office 365 E3](../media/check-mark.png)|

<sup>1</sup> De Microsoft 365 Business Premium-versie van de Office-apps bevat geen volumeactivering via groepsbeleid, app-telemetrie, bijwerkbesturingselementen, spreadsheets vergelijken en informeren of bedrijfsinformatie.

## <a name="migration"></a>Migratie

Zie Abonnementen handmatig [](../commerce/subscriptions/change-plans-manually.md) wijzigen voor instructies als u slechts een paar personen naar Microsoft 365 Business Premium wilt verplaatsen om uw abonnement te migreren. U kunt ook [iedereen automatisch](../commerce/subscriptions/upgrade-to-different-plan.md)upgraden of samenwerken met een partner om uw E3-abonnement en licenties te verplaatsen naar een Microsoft 365 Business Premium-abonnement.
In de volgende secties worden de wijzigingen beschreven die u moet aanbrengen en wat u na de migratie kunt doen.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Configuratie en gegevens van office 365 E3-abonnement
U hoeft uw huidige abonnement of gegevens niet te wijzigen voordat u migreert, waaronder:

- Abonnementsconfiguratie, zoals DNS-records en domeinnamen.
- Gebruikers- en groepsaccounts en verificatie-instellingen, zoals meervoudige verificatie of beleid voor voorwaardelijke toegang.
- Productiviteitsserviceconfiguraties en hun gegevens, zoals Teams, Exchange Online-postvakken, SharePoint Online-sites, OneDrive voor Bedrijven-mappen en OneNote-notitieblokken.
- Office-toepassingen worden automatisch geschaald. Moderne licenties voor Office 365 controleren elke 72 uur de licentietoewijzing van de gebruiker en converteren Office-toepassingen naar de versie die overeenkomt met het gebruikersabonnement.

### <a name="windows-10"></a>Windows 10

Als windows nog niet is bijgewerkt met Windows Pro Creator, kunt u deze [upgraden naar Windows Pro Creators Update.](upgrade-to-windows-pro-creators-update.md)

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Beleidsregels instellen om gebruikersapparaten en bestanden te beveiligen

> [!NOTE]
> Als u Office 365 MDM-beleid en -apparaten in  stelt, worden deze apparaten weergegeven op de pagina Apparaten in het Microsoft 365-beheercentrum. Alle beleidsregels die u hebt ingesteld, worden weergegeven in de lijst met klassieke beleidsregels in de [Intune-portal.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)

Nadat u licenties hebt toegewezen aan Microsoft 365 Business Premium, kunt u de apparaten en bestanden van de gebruikers gaan beveiligen.

Als u iedereen in uw organisatie hebt geüpgraded naar Microsoft 365 Business Premium, ziet u de installatiewizard op de startpagina en kunt u de wizard [Microsoft 365 Business Premium](set-up.md) instellen volgen in de stappen voor de installatiewizard om bestanden en mobiele apparaten te beveiligen.

U kunt deze stappen ook voltooien op de pagina Apparaten:
  
1. Ga in het beheercentrum in het  linkernavigatienavigatiepunt naar \> **Apparatenbeleid.**
    
2. Kies op **de pagina** Apparaatbeleid de optie **Toevoegen**.
    
3. Geef in **het deelvenster** Beleid toevoegen het beleid een naam op en kies vervolgens een **type beleid** in de vervolgkeuzekeuze. 
    
     U kunt toepassingsbeleid instellen voor het beveiligen van bestanden op Android- en iPhone-apparaten, evenals Windows 10, en u kunt apparaatconfiguratiebeleid instellen voor windows 10-apparaten van het bedrijf. Zie de volgende koppelingen voor meer informatie:
    
  - [Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten](app-protection-settings-for-android-and-ios.md)
    
  - [Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten](protection-settings-for-windows-10-devices.md)
    
  - [Apparaatbeveiligingsinstellingen instellen voor Windows 10-pc's](protection-settings-for-windows-10-pcs.md)
  
4. Nadat u beleidsregels hebt ingesteld, kunnen u en uw werknemers apparaten instellen:
    
  - Zie [Windows-apparaten instellen voor Microsoft 365 Business Premium-gebruikers](set-up-windows-devices.md) voor stappen voor Windows-apparaten. 
    
  - Zie [Mobiele apparaten instellen voor Microsoft 365 Business Premium-gebruikers](set-up-mobile-devices.md) voor stappen voor Android-telefoons en iPhones. 
  
### <a name="mailbox-size"></a>Postvakgrootte

Microsoft 365 Business Premium heeft een opslaglimiet van 50 GB omdat hiervoor Exchange Online Plan 1 wordt gebruikt. Wanneer u migreert naar Microsoft 365 Business Premium, wordt u aangeraden om deze gebruiker een Exchange Online-abonnement 2 toe te wijzen en het Exchange Online-abonnement 1 te verwijderen omdat het niet haalbaar is om beide toe te wijzen.


### <a name="threat-protection"></a>Bedreigingsbeveiliging

Na de migratie naar Microsoft 365 Business Premium hebt u Defender voor Office 365. Zie [Microsoft Defender voor Office 365](../security/defender-365-security/defender-for-office-365.md) voor een overzicht. Zie Veilige koppelingen [instellen,](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)Veilige [](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)bijlagen instellen en [Anti-phishing instellen in Defender voor Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)om dit in te stellen.

### <a name="sensitivity-labels"></a>Vertrouwelijkheidslabels

Zie Overzicht van gevoeligheidslabels en het maken en beheren van [gevoeligheidslabels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video als u gevoeligheidslabels wilt gebruiken. [](../compliance/sensitivity-labels.md)
