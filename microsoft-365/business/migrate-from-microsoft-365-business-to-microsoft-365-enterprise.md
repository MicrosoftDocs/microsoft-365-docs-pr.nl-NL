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
description: Meer informatie over het verplaatsen van uw bedrijf van Microsoft 365 Business Premium naar Microsoft 365 E3.
ms.openlocfilehash: 10630671f3deb7eff0ad0f601d301b90743ee35f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164508"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Migreren van Microsoft 365 Business Premium naar Microsoft 365 E3

Microsoft 365 Business Premium heeft alles wat u nodig hebt voor uw kleine bedrijf, door de beste productiviteitsapps in de cloud te combineren met eenvoudig apparaatbeheer en beveiliging waarmee uw werknemers hun beste werk kunnen doen. In sommige gevallen moet u echter mogelijk uw Microsoft 365 Business Premium-abonnement migreren naar Microsoft 365 E3. 

Uw bedrijf is bijvoorbeeld groter geworden en heeft meer dan 300 licenties nodig (gefeliciteerd trouwens).

Of uw bedrijf heeft bedrijfsfuncties nodig, zoals Microsoft 365 Apps voor ondernemingen, Windows 10 Enterprise E3 of Enterprise Client Access-licenties (CAL's).

Upgraden is eenvoudig: u kunt de upgrade starten [vanuit het beheercentrum.](../commerce/subscriptions/upgrade-to-different-plan.md) Al uw gegevens en configuratie in uw huidige abonnement blijven behouden. U hoeft niets te doen om u voor te bereiden op de migratie en daarna niets te doen, behalve profiteren van de nieuwe functies.

>[!Note]
>U kunt ook een Microsoft 365 Business Premium-abonnement voor maximaal 300 stoelen gebruiken en een Microsoft 365 E3-abonnement voor meer dan 300 seats krijgen. Microsoft Defender voor Office 365 is echter niet opgenomen in Microsoft 365 E3. Voor verdere bedreigingsbeveiliging moet u extra Defender voor Office 365-licenties toevoegen, zodat alle gebruikers in het bereik van uw Defender voor Office 365-agenten een licentie hebben.
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Verschillen tussen Microsoft 365 Business Premium en Microsoft 365 Enterprise

In deze tabel ziet u de verschillen tussen Microsoft 365 Business Premium en Microsoft 365 E3.

| Functie    | Ondersteuning in Microsoft 365 Business Premium    | Ondersteuning in Microsoft 365 E3 | 
|:-------|:-----|:-----|
| **On-premises**        | | | 
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise E3| 
| Office-apps*    | [Microsoft 365-apps voor bedrijven](#office-365-business)    | Microsoft 365-apps voor ondernemingen | 
| **Cloudproductiviteits-apps**        | | | 
| Exchange Online en Outlook    | 50 GB opslaglimiet per postvak en onbeperkte Archivering van Exchange Online    | 100 GB opslaglimiet per postvak en onbeperkte Archivering van Exchange Online | 
| Teams    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| OneDrive voor Bedrijven    | 1 TB opslaglimiet per gebruiker    | Onbeperkt | 
| Yammer, SharePoint Online, Planner, Stream    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| **Bedreigingsbeveiliging**        | | | 
| Surface Reduction-mogelijkheden voor aanvallen    | [Deze lijst bekijken](#threat-protection) | Enterprise management of hardware-based isolation for Microsoft Edge | 
| Defender voor Office 365 Abonnement 1 | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | Niet inbegrepen, maar kan worden toegevoegd aan | 
| **Identiteitsbeheer**        | | | 
| Selfservice password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Cloud App Discovery, Azure AD Connect Health    |     | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Office 365-apps Eenmalige Sign-On (SSO): 10 apps per gebruiker (SaaS-galerie-apps zoals Salesforce)* | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Premium 1 SSO: geen limiet (on-premises apps via Azure AD Application Proxy en niet-galerie-apps met Self-Service sjablonen voor app-integratie)    |     | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| **Apparaat- en app-beheer**        | | | 
| Microsoft Intune, Windows Autopilot|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
|VDA (Virtual Desktop Access)    |  |     ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
|Windows Virtual Desktop (WVD)    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png) |     ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
|Gedeelde computeractivering (SCA)    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png) |     ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Microsoft Desktop Optimization Package    | |     ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| **Gegevensbeveiliging**        | | | 
| Preventie van gegevensverlies in Office 365, Azure Information Protection Plan 1    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Vensterinformatiebeveiliging voor eindpunt DLP    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| **Client Access License (CAL-rechten)**    | | |     
| Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)| |         ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| **Compliance**        | | | 
| Onbeperkt e-mailarchiveren    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Compliancebeheer    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| eDiscovery    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| In-place hold and litigation hold    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Mrm-bewaarlabels (Messaging Records Management) en bewaarbeleid    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
||||

\* Gebruikers aan wie toegang is toegewezen tot SaaS-apps, kunnen toegang krijgen tot maximaal 10 apps. Beheerders kunnen de toegang van gebruikers tot verschillende SaaS-apps configureren en wijzigen, maar SSO-toegang is alleen toegestaan voor 10 apps per gebruiker tegelijk. Alle Office 365-apps worden als één app geteld.

## <a name="migration"></a>Migratie

Als u wilt migreren, werkt u samen met uw partner om uw Microsoft 365 Business Premium-abonnement en licenties te verplaatsen naar een geschikt Microsoft 365 E3-abonnement met de licenties.

In de volgende secties wordt beschreven welke wijzigingen u moet aanbrengen en wat u na de migratie kunt doen.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Configuratie en gegevens van microsoft 365-abonnementen

U hoeft geen wijzigingen aan te brengen in uw huidige abonnement of gegevens voordat u migreert, waaronder:

- Abonnementsconfiguratie, zoals DNS-domeinnamen.
- Gebruikers- en groepsaccounts en verificatie-instellingen, zoals meervoudige verificatie of beleid voor voorwaardelijke toegang.
- Productiviteitsserviceconfiguraties en hun gegevens, zoals Teams, Exchange Online-postvakken, SharePoint Online-sites, OneDrive voor Bedrijven-mappen en OneNote-notitieblokken.

Uw gebruikers kunnen nu onbeperkte opslagruimte gebruiken in de mappen Exchange Online en OneDrive voor Bedrijven.

U kunt Cloud App Discovery, Azure AD Connect Health en SSO gaan gebruiken voor meer dan 10 apps.

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Bedreigingsbeveiliging

Windows 10 Business bevat de volgende beveiligingen:

- Integriteitshandhaving van het opstarten van besturingssysteem
- Integriteitshandhaving van gevoelige besturingssystemen
- Geavanceerde kwetsbaarheid en zero-day exploit mitigaties
- Op reputatie gebaseerde netwerkbeveiliging voor Microsoft Edge, Internet Explorer en Chrome
- Host-based firewall
- Ransomware mitigaties
- Isolatie op basis van hardware voor Microsoft Edge
- Toepassingsbesturingselement mogelijk gemaakt door intelligent beveiligingsdiagram
- Apparaatbesturingselement (USB)
- Netwerkbeveiliging voor bedreigingen op het web
- Regels voor het voorkomen van inbraak hosten

Windows 10 Enterprise E3 bevat ook enterprise management van op hardware gebaseerde isolatie voor Microsoft Edge.

>[!Note]
>Gebruikers die zijn gemigreerd naar Microsoft 365 E3, hebben elk een Microsoft Defender voor Office 365-licentie nodig voor verdere bedreigingsbeveiliging. Zorg ervoor dat u extra Defender voor Office 365-licenties aanschaft, zodat alle gebruikers in het bereik van uw Defender voor Office 365-agenten een licentie hebben. 
>

### <a name="device-management-with-intune"></a>Apparaatbeheer met Intune

U hoeft geen wijzigingen aan te brengen in uw huidige Intune-configuratie voordat u migreert, waaronder geregistreerde apparaten en apparaat- en app-instellingen.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business Premium bevat Windows 10 Business, dat u kunt installeren met Windows AutoPilot. Wanneer u migreert naar Microsoft 365 E3, bevat elke gebruikerslicentie Windows 10 Enterprise E3, die u ook kunt installeren met Windows Autopilot.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365-apps voor bedrijven

Uw Microsoft 365 Apps voor Bedrijven-client die op uw apparaten is geïnstalleerd, wordt automatisch gebruikt met de functies van Microsoft 365 Apps voor bedrijven. Na de migratie kunt u nu het volgende gebruiken:

 - Ondersteuning voor groepsbeleid
 - Spreadsheets vergelijken en informeren
 - Bedrijfsinformatie

