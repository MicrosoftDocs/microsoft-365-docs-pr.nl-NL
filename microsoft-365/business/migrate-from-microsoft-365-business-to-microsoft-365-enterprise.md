---
title: Migreren van Microsoft 365 Business naar Microsoft 365 E3
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Lees hoe u uw bedrijf kunt over verplaatsen van Microsoft 365 Business Premium naar Microsoft 365 E3.
ms.openlocfilehash: 019a422bb879389f42a32cf30f9a8094f776078a
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126196"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Migreren van Microsoft 365 Business Premium naar Microsoft 365 E3

Microsoft 365 Business Premium biedt alles wat u nodig hebt voor uw kleine bedrijf, door de beste cloudproductiviteitsapps in de cloud te combineren met eenvoudig apparaatbeheer en -beveiliging waarmee uw werknemers hun beste werk kunnen doen. In sommige gevallen moet u echter mogelijk uw Microsoft 365 Business Premium-abonnement migreren naar Microsoft 365 E3. 

Uw bedrijf is bijvoorbeeld groter geworden en heeft meer dan 300 licenties nodig (gefeliciteerd trouwens).

Of uw bedrijf heeft bedrijfsfuncties nodig, zoals Microsoft 365-apps voor ondernemingen, Windows 10 Enterprise E3 of ENTERPRISE Client Access-licenties (CAL's).

Upgraden is eenvoudig: u kunt de upgrade [starten vanuit het beheercentrum.](../commerce/subscriptions/upgrade-to-different-plan.md) Al uw gegevens en configuratie in uw huidige abonnement blijven behouden. U hoeft niets te doen om u voor te bereiden op de migratie en daarna niets te doen, behalve profiteren van de nieuwe functies.

>[!Note]
>U kunt ook een Microsoft 365 Business Premium-abonnement gebruiken voor maximaal 300 seats en een Microsoft 365 E3-abonnement voor meer dan 300 seats krijgen. Microsoft Defender voor Office 365 is echter niet opgenomen in Microsoft 365 E3. Voeg extra Defender voor Office 365-licenties toe, zodat alle gebruikers binnen het bereik van uw Defender voor Office 365-beveiligingsbeveiliging een licentie krijgen.
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Verschillen tussen Microsoft 365 Business Premium en Microsoft 365 Enterprise

In deze tabel ziet u de verschillen tussen Microsoft 365 Business Premium en Microsoft 365 E3.

| Functie    | Ondersteuning in Microsoft 365 Business Premium    | Ondersteuning in Microsoft 365 E3 | 
|:-------|:-----|:-----|
| **On-premises**        | | | 
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise E3| 
| Office-apps*    | [Microsoft 365-apps voor bedrijven](#office-365-business)    | Microsoft 365-apps voor ondernemingen | 
| **Productiviteitsapps voor de cloud**        | | | 
| Exchange Online en Outlook    | 50 GB opslaglimiet per postvak en onbeperkte Archivering van Exchange Online    | 100 GB opslaglimiet per postvak en onbeperkte Exchange Online-archivering | 
| Teams    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| OneDrive voor Bedrijven    | 1 TB opslaglimiet per gebruiker    | Onbeperkt | 
| Yammer, SharePoint Online, Planner, Stream    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| MileIQ    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Bedreigingsbeveiliging**        | | | 
| Mogelijkheden voor het verminderen van aanvallen op het oppervlak    | [Bekijk deze lijst](#threat-protection) | Enterprise-beheer van hardware-isolatie voor Microsoft Edge | 
| Defender voor Office 365-abonnement 1 | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | Niet inbegrepen, maar kan worden toegevoegd aan | 
| **Identiteitsbeheer**        | | | 
| Selfservice voor het opnieuw instellen van wachtwoorden voor hybride Azure Active Directory-accounts (Azure AD), Azure AD Multi-Factor Authentication (MFA), Voorwaardelijke toegang, terugschrijven van wachtwoorden voor on-premises identiteiten|     ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| Cloud App Discovery, Azure AD Connect Health    |     | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Office 365-apps Sign-On (SSO): 10 apps per gebruiker (SaaS-apps in galerie, zoals Salesforce)* | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Premium 1 SSO: geen limiet (on-premises apps via Azure AD-toepassingsproxy en niet-galerie-apps met Self-Service-app-integratiesjablonen)    |     | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| **Apparaat- en app-beheer**        | | | 
| Microsoft Intune, Windows Autopilot|     ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
|VDA (Virtual Desktop Access)    |  |     ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
|Windows Virtual Desktop (WVD)    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png) |     ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
|SCA (Shared Computer Activation)    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png) |     ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| Microsoft Desktop Optimization-pakket    | |     ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| **Gegevensbeveiliging**        | | | 
| Office 365 Preventie van gegevensverlies, Azure Information Protection Plan 1    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| Window Information Protection voor eindpunt DLP    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| **Client Access License (CAL-rechten)**    | | |     
| Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)| |         ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| **Compliance**        | | | 
| Onbeperkt archiveren van e-mail    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| Compliancebeheer    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| eDiscovery    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| In-place wacht- en juridische procedure    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| MrM-bewaarlabels (Messaging Records Management) en bewaarbeleid    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
||||

\* Gebruikers aan wie toegang is toegewezen tot SaaS-apps, kunnen toegang krijgen tot maximaal 10 apps. Beheerders kunnen eenmalige aanmelding configureren en gebruikerstoegang tot verschillende SaaS-apps wijzigen, maar toegang tot eenmalige aanmelding is slechts toegestaan voor tien apps per gebruiker tegelijk. Alle Office 365-apps worden als één app geteld.

## <a name="migration"></a>Migratie

Als u wilt migreren, werkt u samen met uw partner om uw Microsoft 365 Business Premium-abonnement en licenties over te zetten naar een geschikt Microsoft 365 E3-abonnement met de licenties.

In de volgende secties wordt beschreven welke wijzigingen u moet aanbrengen, indien van orde, en wat u na de migratie kunt doen.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Configuratie en gegevens van Microsoft 365-abonnement

U hoeft geen wijzigingen aan te brengen in uw huidige abonnement of gegevens voordat u gaat migreren, waaronder:

- Abonnementsconfiguratie, zoals DNS-domeinnamen.
- Gebruikers- en groepsaccounts en verificatie-instellingen, zoals meervoudige verificatie of beleidsregels voor voorwaardelijke toegang.
- Configuraties voor productiviteitsservice en de gegevens, zoals Teams, Exchange Online-postvakken, SharePoint Online-sites, mappen van OneDrive voor Bedrijven en OneNote-notitieblokken.

Uw gebruikers kunnen nu onbeperkte opslag krijgen in de postvakken van Exchange Online en de mappen van OneDrive voor Bedrijven.

U kunt Cloud App Discovery, Azure AD Connect Health en SSO gaan gebruiken voor meer dan tien apps.

>[!Note]
>Gebruikers die zijn gemigreerd naar Microsoft 365 E3 kunnen MileIQ niet meer gebruiken.
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Bedreigingsbeveiliging

Windows 10 Business omvat de volgende beveiligingen:

- Integriteits afdwingen van opstartproces van besturingssysteem
- Integriteits afdwingen van gevoelige besturingssystemen
- Geavanceerde beveiligingsleed en risicobeperking van misbruik zonder dagen
- Op reputatie gebaseerde netwerkbeveiliging voor Microsoft Edge, Internet Explorer en Chrome
- Firewall op basis van host
- Ransomware-risico's
- Hardwaregebaseerd isolatie voor Microsoft Edge
- Toepassingsbesturingselement mogelijk gemaakt door Intelligent Security Graph
- Apparaatbesturing (USB)
- Netwerkbeveiliging voor internetrisico's
- Regels voor het voorkomen van inbreuken hosten

Windows 10 Enterprise E3 bevat ook bedrijfsbeheer van hardwaregebaseerd isolatie voor Microsoft Edge.

>[!Note]
>Gebruikers die naar Microsoft 365 E3 zijn gemigreerd, moeten elk een Microsoft Defender voor Office 365-licentie hebben voor verdere bedreigingsbeveiliging. Zorg ervoor dat u extra Defender-licenties voor Office 365-licenties koopt, zodat alle gebruikers binnen het bereik van uw Defender voor Office 365-agenten een licentie hebben. 
>

### <a name="device-management-with-intune"></a>Apparaatbeheer met Intune

U hoeft geen wijzigingen aan te brengen in uw huidige Intune-configuratie voordat u gaat migreren. Dit omvat geregistreerde apparaten en instellingen voor apparaten en apps.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business Premium bevat Windows 10 Business, dat u kunt installeren met Windows AutoPilot. Wanneer u migreert naar Microsoft 365 E3, omvat elke gebruikerslicentie Windows 10 Enterprise E3, die u ook kunt installeren met Windows Autopilot.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365-apps voor bedrijven

De Microsoft 365 Apps voor Bedrijven-client die op uw apparaten is geïnstalleerd, wordt automatisch gebruikt met de functies van Microsoft 365 Apps voor ondernemingen. Na de migratie kunt u nu het volgende gebruiken:

 - Ondersteuning voor groepsbeleid
 - Spreadsheets vergelijken en inquire
 - Bedrijfsinformatie

