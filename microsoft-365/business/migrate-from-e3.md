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
search.appverid:
- BCS160
- MET150
description: Meer informatie over het verplaatsen van uw bedrijf naar Microsoft 365 Business vanuit Office 365 E3.
ms.openlocfilehash: b86a163792aa71f0bca115ab918e0800acc0427d
ms.sourcegitcommit: 9c335d110e0b499501edc8a31b987641819118a1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2020
ms.locfileid: "42811673"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business"></a>Migreren van Office 365 E3 naar Microsoft 365 Business 

Microsoft 365 Business heeft alles wat u nodig hebt voor uw kleine bedrijf en combineert de beste cloudgebaseerde productiviteitsapps met eenvoudig apparaatbeheer en beveiliging. Als u momenteel een Office 365 E3-abonnement hebt, maar niet meer dan 300 werknemers hebt, u overwegen over te schakelen naar Microsoft 365 Business voor extra beveiligingsfuncties.

Migreren is eenvoudig: eerst wisselt u van licentie en worden al uw gegevens en gebruikersgegevens in uw huidige abonnement onderhouden. Na de migratie moet u de functies instellen die zijn toegevoegd in Microsoft 365 Business.

## <a name="differences-between-office-365-e3-and-microsoft-365-business"></a>Verschillen tussen Office 365 E3 en Microsoft 365 Business

In deze tabel ziet u de verschillen tussen Microsoft 365 Business en Office 365 E3.

| Functie    | Ondersteuning in Microsoft 365 Business    | Ondersteuning in Office 365 E3 | 
|:-------|:-----|:-----|
| **On-premises**        | | | 
| Office-apps<sup>1</sup>    | Office 365 Business    | Office 365 ProPlus | 
| **Cloud productiviteits-apps**        | | | 
| Exchange Online en Outlook    | 50 GB opslaglimiet per postvak en onbeperkt Exchange Online Archiveren    | 100 GB opslaglimiet per postvak en onbeperkt Exchange Online Archiveren | 
| Teams    | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| OneDrive voor Bedrijven    | 1 TB opslaglimiet per gebruiker    | Onbeperkt | 
| Yammer, SharePoint Online, Planner, Stream    | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| StaffHub (StaffHub)    | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| Outlook Customer Manager, MileIQ    | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | | 
| **Bescherming tegen bedreigingen**        | | | 
| ATP-abonnement (Advanced Threat Protection) van Office 365 (Advanced Threat Protection) | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | Niet inbegrepen, maar kan worden toegevoegd op | 
| **Identiteitsbeheer**        | | | 
| Selfservice wachtwoord opnieuw instellen voor hybride Azure Active Directory (Azure AD)-accounts, Azure multi-factor authenticatie (MFA), Voorwaardelijke toegang, wachtwoord terugschrijven voor on-premises identiteiten|     ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    |  | 
| **Apparaat- en appbeheer**        | | |
| Microsoft Intune, Windows AutoPilot|     ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    |  |
| Activering van gedeelde computers|     ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png)| 
| Upgraderechten naar Windows 10 Pro vanaf Win 7/8.1 Pro-licenties|     ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    || 
| **Informatiebescherming**        | | |
|Preventie van gegevensverlies van Office 365|    ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)|![Inbegrepen bij Office 365 E3](../media/check-mark.png)|
|Azure Information Protection Plan 1, Bitlocker handhaving|![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)||
|Azure Information Protection Plan 1, Gevoeligheidslabels|![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)||
|**Clienttoegangslicentie (CAL-rechten)**|||
|Enterprise CAL Suite (Exchange, SharePoint, Skype)||![Inbegrepen bij Office 365 E3](../media/check-mark.png)|

<sup>1</sup> De Microsoft 365 Business-versie van de Office-apps bevat geen volumeactivering via groepsbeleid, telemetrie van apps, updatebesturingselementen, spreadsheetvergelijken en informeren, of business Intelligence.

## <a name="migration"></a>Migratie

Zie Plannen handmatig [wijzigen](../commerce/subscriptions/change-plans-manually.md) voor instructies als u slechts een paar mensen naar Microsoft 365 Business wilt verplaatsen. U iedereen ook [automatisch upgraden](../commerce/subscriptions/upgrade-to-different-plan.md)of met een partner samenwerken om uw E3-abonnement en licenties te verplaatsen naar een Microsoft 365 Business-abonnement.
In de volgende secties worden de eventuele wijzigingen beschreven die u moet aanbrengen en wat u na de migratie doen.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Configuratie en gegevens van Office 365 E3-abonnementen
U hoeft geen wijzigingen aan te brengen in uw huidige abonnement of gegevens voordat u migreert, waaronder:

- Abonnementsconfiguratie, zoals DNS-records en domeinnamen.
- Gebruikers- en groepsaccounts en verificatie-instellingen, zoals multifactorauthenticatie of beleid voor voorwaardelijke toegang.
- Productiviteitsserviceconfiguraties en hun gegevens, zoals Teams, Exchange Online-postvakken, SharePoint Online-sites, OneDrive voor Bedrijven-mappen en OneNote-notitieblokken.

### <a name="windows-10"></a>Windows 10

Als uw Windows nog niet op windows Pro Creator-update staat, [kunt u deze upgraden naar Windows Pro Creators Update.](upgrade-to-windows-pro-creators-update.md)

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Beleidsregels instellen om gebruikersapparaten en bestanden te beschermen

> [!NOTE]
> Als u Office 365 MDM-beleid en -apparaten instelt, worden deze apparaten weergegeven op de pagina **Apparaten** in het Microsoft 365-beheercentrum. Alle beleidsregels die u instelt, worden weergegeven in de lijst met klassieke beleidsregels in de [Intune-portal.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)

Nadat u licenties hebt toegewezen aan Microsoft 365 Business, u beginnen met het beveiligen van de apparaten en bestanden van de gebruikers.

Als u iedereen in uw organisatie hebt geüpgraded naar Microsoft 365 Business, ziet u de wizard Setup op de startpagina en u de stappen [Microsoft 365 Business instellen in de](set-up.md) wizard Setup om bestanden en mobiele apparaten te beveiligen.

U de volgende stappen ook uitvoeren op de pagina Apparaten:
  
1. Ga in het beheercentrum in de linkernavigatienaar \> **Apparatenbeleid**. **Devices**
    
2. Kies op de pagina **Apparaatbeleid** de optie **Toevoegen**.
    
3. Geef het beleid in het deelvenster **Beleid toevoegen** een naam en kies vervolgens een **beleidstype** in de vervolgkeuzelijst. 
    
     U toepassingsbeleid instellen voor het beveiligen van bestanden op Android- en iPhone-apparaten, evenals Windows 10, en u apparaatconfiguratiebeleid instellen voor Windows 10-apparaten die eigendom zijn van het bedrijf. Zie de volgende links voor meer informatie:
    
  - [Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten](app-protection-settings-for-android-and-ios.md)
    
  - [Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten](protection-settings-for-windows-10-devices.md)
    
  - [Instellingen voor apparaatbeveiliging instellen voor Windows 10-pc's](protection-settings-for-windows-10-pcs.md)
  
4. Zodra u beleid hebt ingesteld, kunnen u en uw medewerkers apparaten instellen:
    
  - Zie [Windows-apparaten instellen voor Microsoft 365 Business-gebruikers](set-up-windows-devices.md) voor stappen voor Windows-apparaten. 
    
  - Zie [Mobiele apparaten instellen voor Microsoft 365 Business-gebruikers](set-up-mobile-devices.md) voor stappen voor Android-telefoons en iPhones. 

### <a name="threat-protection"></a>Bescherming tegen bedreigingen

Nadat u naar Microsoft 365 Business bent gemigreerd, beschikt u over Office 365 ATP. Zie [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) voor een overzicht. Zie [atp-veilige koppelingen instellen,](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa) [ATP-veilige bijlagen instellen](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)en [ATP-antiphishing instellen](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).

### <a name="sensitivity-labels"></a>Gevoeligheidslabels

Zie [Overzicht van gevoeligheidslabels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) maken en beheren als u gevoeligheidslabels wilt gebruiken om gevoeligheidslabels te [gebruiken.](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)
