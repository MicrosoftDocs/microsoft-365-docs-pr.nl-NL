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
description: Meer informatie over het verplaatsen van uw bedrijf naar Microsoft 365 Business Premium van Office 365 E3.
ms.openlocfilehash: 6571fb3ba53620fbb8b97d8f5fd76832f95b82c3
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515897"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Migreren van Office 365 E3 naar Microsoft 365 Business Premium 

Microsoft 365 Business Premium heeft alles wat u nodig hebt voor uw kleine bedrijf, waarbij u de beste cloudgebaseerde productiviteitsapps combineert met eenvoudig apparaatbeheer en beveiliging. Als u momenteel een Office 365 E3-abonnement hebt, maar niet meer dan 300 werknemers hebt, u overwegen over te stappen naar Microsoft 365 Business Premium voor extra beveiligingsfuncties.

Migreren is eenvoudig: eerst wisselt u van licentie en wordt al uw gegevens en gebruikersgegevens in uw huidige abonnement gehandhaafd. Na de migratie moet u de functies instellen die zijn toegevoegd in Microsoft 365 Business Premium.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Verschillen tussen Office 365 E3 en Microsoft 365 Business Premium

In deze tabel worden de verschillen tussen Microsoft 365 Business Premium en Office 365 E3 weergegeven.

| Functie    | Ondersteuning in Microsoft 365 Business Premium    | Ondersteuning in Office 365 E3 | 
|:-------|:-----|:-----|
| **On-premises**        | | | 
| Office-apps<sup>1</sup>    | Microsoft 365-apps voor bedrijven    | Microsoft 365-apps voor ondernemingen | 
| **Apps voor productiviteit in de cloud**        | | | 
| Exchange Online en Outlook    | Opslaglimiet van 50 GB per postvak en onbeperkte Exchange Online Archivering    | Opslaglimiet van 100 GB per postvak en onbeperkte Exchange Online Archivering | 
| Teams    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| OneDrive voor Bedrijven    | 1 TB opslaglimiet per gebruiker    | Onbeperkt | 
| Yammer, SharePoint Online, Planner, Stream    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| StaffHub    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| Outlook Customer Manager, MileIQ    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Bescherming tegen bedreigingen**        | | | 
| Atp-abonnement (Advanced Threat Protection) van Office 365 | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | Niet inbegrepen, maar kan worden toegevoegd op | 
| **Identiteitsbeheer**        | | | 
| Selfservice wachtwoordreset voor hybride Azure Active Directory-accounts (Azure AD), Azure multi-factor authentication (MFA), Voorwaardelijke toegang, terugschrijving van wachtwoorden voor on-premises identiteiten|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    |  | 
| **Apparaat- en appbeheer**        | | |
| Microsoft Intune, Windows AutoPilot|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| Activering van gedeelde computer|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png)| 
| Upgraderechten naar Windows 10 Pro vanaf Win 7/8.1 Pro-licenties|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    || 
| **Gegevensbeveiliging**        | | |
|Preventie van gegevensverlies in Office 365|    ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)|![Inbegrepen bij Office 365 E3](../media/check-mark.png)|
|Azure Information Protection Plan 1, handhaving van Bitlocker|![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)||
|Azure Information Protection Plan 1, gevoeligheidslabels|![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)||
|**Client Access License (CAL-rechten)**|||
|Enterprise CAL Suite (Exchange, SharePoint, Skype)||![Inbegrepen bij Office 365 E3](../media/check-mark.png)|

<sup>1</sup> De Microsoft 365 Business Premium-versie van de Office-apps bevat geen volumeactivering via Groepsbeleid, telemetrie voor apps, updatebesturingselementen, spreadsheetvergelijking en -onderzoek of business Intelligence.

## <a name="migration"></a>Migratie

Zie [Abonnementen handmatig wijzigen](../commerce/subscriptions/change-plans-manually.md) voor instructies als u slechts een paar personen wilt verplaatsen naar Microsoft 365 Business Premium als u uw abonnement wilt migreren. U ook [iedereen automatisch upgraden](../commerce/subscriptions/upgrade-to-different-plan.md)of samenwerken met een partner om uw E3-abonnement en licenties te verplaatsen naar een Microsoft 365 Business Premium-abonnement.
In de volgende secties worden de wijzigingen beschreven die u moet aanbrengen en wat u na de migratie doen.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Configuratie en gegevens van Office 365 E3-abonnementen
U hoeft geen wijzigingen aan te brengen in uw huidige abonnement of gegevens voordat u migreert, waaronder:

- Abonnementsconfiguratie, zoals DNS-records en domeinnamen.
- Gebruikers- en groepsaccounts en verificatie-instellingen, zoals meerfactorauthenticatie of beleid voor voorwaardelijke toegang.
- Configuraties van productiviteitsservice en hun gegevens, zoals Teams, Exchange Online-postvakken, SharePoint Online-sites, OneDrive voor Bedrijven-mappen en OneNote-notitieblokken.
- Office-toepassingen worden automatisch geschaald. Office 365-licenties controleren elke 72 uur de licentietoewijzing van de gebruiker en converteren Office-toepassingen naar de versie die overeenkomt met het gebruikersabonnement.

### <a name="windows-10"></a>Windows 10

Als uw Windows nog niet in windows Pro Creator-update staat, [kunt u deze bijwerken naar Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Beleid instellen om gebruikersapparaten en bestanden te beschermen

> [!NOTE]
> Als u Office 365 MDM-beleid en -apparaten instelt, worden deze apparaten weergegeven op de pagina **Apparaten** in het Microsoft 365-beheercentrum. Alle beleidsregels die u hebt ingesteld, worden weergegeven in de lijst met klassieke beleidsregels in de [Intune-portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).

Nadat u licenties hebt toegewezen aan Microsoft 365 Business Premium, u beginnen met het beveiligen van de apparaten en bestanden van de gebruikers.

Als u iedereen in uw organisatie hebt geüpgraded naar Microsoft 365 Business Premium, ziet u de wizard Setup op de startpagina en u de stappen [microsoft 365 Business Premium instellen](set-up.md) volgen in de wizard Setup om bestanden en mobiele apparaten te beschermen.

U deze stappen ook uitvoeren op de pagina Apparaten:
  
1. Ga in het beheercentrum in het **Devices** linkernavigatiesysteem naar \> **Apparaatbeleid**.
    
2. Kies Op de pagina **Apparaatbeleid** de optie **Toevoegen**.
    
3. Geef het beleid in **het deelvenster Polis toevoegen** een naam en kies vervolgens een **beleidstype** uit de vervolgkeuzelijst. 
    
     U toepassingsbeleid instellen voor het beveiligen van bestanden op Android- en iPhone-apparaten, evenals Windows 10, en u apparaatconfiguratiebeleid instellen voor Windows 10-apparaten die eigendom zijn van het bedrijf. Zie de volgende links voor meer informatie:
    
  - [Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten](app-protection-settings-for-android-and-ios.md)
    
  - [Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten](protection-settings-for-windows-10-devices.md)
    
  - [Instellingen voor apparaatbeveiliging instellen voor Windows 10-pc's](protection-settings-for-windows-10-pcs.md)
  
4. Zodra u beleid hebt ingesteld, kunnen u en uw medewerkers apparaten instellen:
    
  - Zie [Windows-apparaten instellen voor Microsoft 365 Business Premium-gebruikers](set-up-windows-devices.md) voor stappen voor Windows-apparaten. 
    
  - Zie [Mobiele apparaten instellen voor Microsoft 365 Business Premium-gebruikers](set-up-mobile-devices.md) voor stappen voor Android-telefoons en iPhones. 

### <a name="threat-protection"></a>Bedreigingsbeveiliging

Nadat u bent gemigreerd naar Microsoft 365 Business Premium, hebt u Office 365 ATP. Zie [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) voor een overzicht. Zie [VEILIGE ATP-koppelingen instellen,](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa) [ATP-veilige bijlagen instellen](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)en [ATP-antiphishing instellen.](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)

### <a name="sensitivity-labels"></a>Gevoeligheidslabels

Zie [Overzicht van gevoeligheidslabels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) en het maken en beheren van gevoeligheidslabels video als u wilt beginnen met het gebruik van [gevoeligheidslabels.](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)
