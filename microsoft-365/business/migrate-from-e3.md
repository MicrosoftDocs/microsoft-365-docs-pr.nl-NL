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
description: Meer informatie over hoe u uw bedrijf kunt overzetten naar Microsoft 365 Business Premium van Office 365 E3.
ms.openlocfilehash: f3f3894a2a5cb69f9f91825d89db4f4b857fac5c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295285"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Migreren van Office 365 E3 naar Microsoft 365 Business Premium 

Microsoft 365 Business Premium biedt alles wat u nodig hebt voor uw kleine bedrijf, waarbij de beste productiviteitstoepassingen voor de beste Cloud worden gecombineerd met eenvoudig Apparaatbeheer en beveiliging. Als u momenteel een Office 365 E3-abonnement hebt, maar niet meer dan 300 medewerkers hebt, kunt u overstappen op Microsoft 365 Business Premium voor extra beveiligingsfuncties.

Migratie is eenvoudig: eerst overstappen op een ander abonnement, worden alle gegevens en gebruikersgegevens in uw huidige abonnement bewaard. Na de migratie moet u de functies instellen die worden toegevoegd in Microsoft 365 Business Premium.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Verschillen tussen Office 365 E3 en Microsoft 365 Business Premium

In deze tabel ziet u de verschillen tussen Microsoft 365 Business Premium en Office 365 E3.

| Functie    | Ondersteuning in Microsoft 365 Business Premium    | Ondersteuning in Office 365 E3 | 
|:-------|:-----|:-----|
| **On-premises**        | | | 
| Office-apps<sup>1</sup>    | Microsoft 365-apps voor bedrijven    | Microsoft 365-apps voor ondernemingen | 
| **Apps voor Cloud productiviteit**        | | | 
| Exchange Online en Outlook    | 50 GB opslaglimiet per postvak en onbeperkt Exchange Online archivering    | 100 GB opslaglimiet per postvak en onbeperkt Exchange Online archivering | 
| Teams    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Office 365 E3](../media/check-mark.png) | 
| OneDrive voor Bedrijven    | 1 TB opslaglimiet per gebruiker    | Begrensd | 
| Yammer, SharePoint Online, planner, stream    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Office 365 E3](../media/check-mark.png) | 
| StaffHub    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Office 365 E3](../media/check-mark.png) | 
| Outlook Customer Manager, MileIQ    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Bedreigingsbeveiliging**        | | | 
| Office 365 Advanced Threat Protection (ATP)-abonnement 1 | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | Niet inbegrepen, maar kan worden toegevoegd aan | 
| **Identiteitsbeheer**        | | | 
| Selfservice voor wachtwoordherstel voor hybride Azure Active Directory-accounts (Azure AD), Azure multi-factor Authentication (MFA), voorwaardelijke toegang, wachtwoord terugschrijven voor on-premises id's|     ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    |  | 
| **Apparaten en apps beheren**        | | |
| Microsoft intune, Windows auto pilot|     ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| Gedeelde computeractivering|     ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Office 365 E3](../media/check-mark.png)| 
| Upgrade rechten voor Windows 10 Pro van Win 7/8.1 Pro-licenties|     ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    || 
| **Gegevensbeveiliging**        | | |
|Office 365 preventie van gegevensverlies|    ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)|![Inbegrepen in Office 365 E3](../media/check-mark.png)|
|Azure-informatie beschermings abonnement 1, BitLocker Enforcement|![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)||
|Azure Information Protection abonnement 1, vertrouwelijkheids labels|![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)||
|**Licentie voor client toegang (CAL-rechten)**|||
|Enterprise CAL suite (Exchange, SharePoint, Skype)||![Inbegrepen in Office 365 E3](../media/check-mark.png)|

<sup>1</sup> de microsoft 365 Business Premium-versie van de Office-apps omvat geen volumeactivering via Groepsbeleid, app-telemetrie, bijwerk besturingselementen, spreadsheets vergelijken en inquire of Business Intelligence.

## <a name="migration"></a>Migratie

Als u uw abonnement wilt migreren, raadpleegt u [abonnementen handmatig wijzigen](../commerce/subscriptions/change-plans-manually.md) voor instructies als u slechts enkele personen wilt overzetten naar microsoft 365 Business Premium. U kunt [iedereen ook automatisch upgraden](../commerce/subscriptions/upgrade-to-different-plan.md)of met een partner samenwerken om uw E3-abonnement en licenties te verplaatsen naar een abonnement op microsoft 365 Business Premium.
In de volgende secties wordt beschreven welke wijzigingen u moet aanbrengen, indien van toepassing, en wat u na de migratie kunt doen.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Configuratie en gegevens van Office 365 E3-abonnement
U hoeft geen wijzigingen aan te voeren voor uw huidige abonnement of gegevens vóór de overstap, waaronder:

- Configuratie van het abonnement, zoals DNS-records en domeinnamen.
- Accounts en verificatie-instellingen van gebruikers en groepen, zoals multi-factor Authentication of regels voor voorwaardelijke toegang.
- Productiviteits serviceconfiguraties en hun gegevens, zoals teams, Exchange Online-postvakken, SharePoint Online-sites, OneDrive voor bedrijven-mappen en OneNote-notitieblokken.
- Office-toepassingen worden automatisch aangepast. Met Office 365 modern Licensing wordt elke 72 uur de licentietoewijzing van de gebruiker gecontroleerd en worden de Office-toepassingen geconverteerd naar de versie die overeenkomt met het gebruikers abonnement.

### <a name="windows-10"></a>Windows 10

Als de Windows Update voor Windows Pro Creator nog niet is geïnstalleerd, kunt [u deze upgraden naar de Windows Pro Creators update](upgrade-to-windows-pro-creators-update.md).

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Beleidsregels instellen voor het beschermen van gebruikers apparaten en-bestanden

> [!NOTE]
> Als u een beleid en apparaten voor Office 365 MDM instelt, worden deze apparaten weergegeven op de pagina **apparaten** in het microsoft 365-Beheercentrum. Beleidsregels die u instelt, worden weergegeven in de lijst met klassieke beleidsregels in de [intune-Portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).

Nadat u licenties hebt toegewezen aan Microsoft 365 Business Premium, kunt u beginnen met de bescherming van de apparaten en bestanden van de gebruikers.

Als u iedereen in uw organisatie hebt bijgewerkt naar Microsoft 365 Business Premium, wordt de wizard Setup op de startpagina weergegeven en kunt u [Microsoft 365 Business Premium volgen via de installatiewizard van de wizard](set-up.md) om bestanden en mobiele apparaten te beschermen.

U kunt deze stappen ook voltooien op de pagina apparaten:
  
1. Ga in het Beheercentrum in het linkernavigatievenster naar **apparaten** \> **beleid**.
    
2. Kies **toevoegen**op de pagina **apparaatbeleid** .
    
3. Geef in het deelvenster **beleid toevoegen** een naam op voor het beleid en kies vervolgens een **beleidstype** in de vervolgkeuzelijst. 
    
     U kunt toepassingenbeleid instellen voor het beschermen van bestanden op Android-en iPhone-apparaten, en Windows 10, en u kunt beleidsinstellingen voor apparaatconfiguratie instellen voor bedrijfseigen Windows 10-apparaten. Voor meer informatie raadpleegt u de volgende koppelingen:
    
  - [Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten](app-protection-settings-for-android-and-ios.md)
    
  - [Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten](protection-settings-for-windows-10-devices.md)
    
  - [Instellingen voor apparaat-beveiliging instellen voor Windows 10-Pc's](protection-settings-for-windows-10-pcs.md)
  
4. Nadat u beleidsregels hebt ingesteld, kunnen u en uw werknemers apparaten instellen:
    
  - Zie [Windows-apparaten instellen voor Microsoft 365 Business Premium-gebruikers](set-up-windows-devices.md) voor stappen voor Windows-apparaten. 
    
  - Zie [mobiele apparaten instellen voor Microsoft 365 Business Premium-gebruikers](set-up-mobile-devices.md) voor stappen voor Android-telefoons en iPhones. 
  
### <a name="mailbox-size"></a>Postvakgrootte

Microsoft 365 Business Premium heeft een opslaglimiet van 50 GB omdat Exchange Online (abonnement 1) wordt gebruikt. Wanneer een van uw 50 gebruikers migreert naar Microsoft 365 Business Premium, wordt u aangeraden deze gebruiker een Exchange Online-abonnement 2 toe te wijzen en Exchange Online abonnement 1 te verwijderen, aangezien het niet haalbaar is om beide berichten toe te wijzen.


### <a name="threat-protection"></a>Bedreigingsbeveiliging

Na de migratie naar Microsoft 365 Business Premium hebt u Office 365 ATP. Zie [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) voor een overzicht. Als u deze instelling wilt instellen, raadpleegt u de [veilige koppelingen voor ATP instellen](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [veilige bijlagen van ATP instellen](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)en de [anti-phishing van ATP instellen](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).

### <a name="sensitivity-labels"></a>Vertrouwelijkheidslabels

Als u de palletlabels wilt gebruiken, raadpleegt u [overzicht van de palletlabels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) en de video over het [maken en beheren](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) van laag labels.
