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
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Meer informatie over het verplaatsen van uw bedrijf van Microsoft 365 Business Premium naar Microsoft 365 E3.
ms.openlocfilehash: a41b27b91bd049abb2231a397a328f4f53af9500
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633173"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Migreren van Microsoft 365 Business Premium naar Microsoft 365 E3

Microsoft 365 Business Premium heeft alles wat u nodig hebt voor uw kleine bedrijf en combineert de beste cloudgebaseerde productiviteitsapps met eenvoudig apparaatbeheer en beveiliging waarmee uw werknemers hun beste werk kunnen doen. In sommige gevallen moet u echter uw Microsoft 365 Business Premium-abonnement migreren naar Microsoft 365 E3. 

Uw bedrijf is bijvoorbeeld gegroeid en heeft meer dan 300 licenties nodig (gefeliciteerd, trouwens).

Of uw bedrijf heeft bedrijfsfuncties nodig, zoals Microsoft 365 Apps voor ondernemingen, Windows 10 Enterprise E3 of Enterprise Client Access-licenties (CAL's).

Upgraden is eenvoudig: u de upgrade starten [vanuit het beheercentrum.](../commerce/subscriptions/upgrade-to-different-plan.md) Al uw gegevens en configuratie in uw huidige abonnement worden onderhouden. Er is niets voor u te doen om voor te bereiden op de migratie en niets te doen daarna, behalve profiteren van de nieuwe functies.

>[!Note]
>U ook een Microsoft 365 Business Premium-abonnement gebruiken voor maximaal 300 zitplaatsen en een Microsoft 365 E3-abonnement krijgen voor meer dan 300 zitplaatsen. Office 365 ATP is echter niet inbegrepen bij Microsoft 365 E3. Voor voortdurende bescherming tegen bedreigingen moet u extra Office 365 ATP-licenties toevoegen, zodat alle gebruikers in het bereik van uw Office 365 ATP-politieeen licentie hebben.
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Verschillen tussen Microsoft 365 Business Premium en Microsoft 365 Enterprise

In deze tabel ziet u de verschillen tussen Microsoft 365 Business Premium en Microsoft 365 E3.

| Functie    | Ondersteuning in Microsoft 365 Business Premium    | Ondersteuning in Microsoft 365 E3 | 
|:-------|:-----|:-----|
| **On-premises**        | | | 
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise E3| 
| Office-apps*    | [Microsoft 365 Apps voor bedrijven](#office-365-business)    | Microsoft 365 Apps voor bedrijven | 
| **Cloud productiviteits-apps**        | | | 
| Exchange Online en Outlook    | 50 GB opslaglimiet per postvak en onbeperkt Exchange Online-archivering    | 100 GB opslaglimiet per postvak en onbeperkt Exchange Online-archivering | 
| Teams    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| OneDrive voor Bedrijven    | 1 TB opslaglimiet per gebruiker    | Onbeperkt | 
| Yammer, SharePoint Online, Planner, Stream    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Outlook Customer Manager, MileIQ    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Bescherming tegen bedreigingen**        | | | 
| Mogelijkheden om oppervlaktereductie aan te vallen    | [Bekijk deze lijst](#threat-protection) | Enterprise management van hardwaregebaseerde isolatie voor Microsoft Edge | 
| ATP-abonnement (Advanced Threat Protection) van Office 365 (Advanced Threat Protection) | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | Niet inbegrepen, maar kan worden toegevoegd op | 
| **Identiteitsbeheer**        | | | 
| Selfservice wachtwoord opnieuw instellen voor hybride Azure Active Directory (Azure AD)-accounts, Azure multi-factor authenticatie (MFA), Voorwaardelijke toegang, wachtwoord terugschrijven voor on-premises identiteiten|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Detectie van cloud-apps, Azure AD Connect-status    |     | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Office 365-apps Single Sign-On (SSO): 10 apps per gebruiker (Galerij SaaS-apps zoals Salesforce)* | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Premium 1 SSO: geen limiet (On-premises apps via Azure AD Application Proxy en non-gallery apps met Self-Service App Integration templates)    |     | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| **Apparaat- en appbeheer**        | | | 
| Microsoft Intune, Windows Autopilot|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
|VDA (Virtual Desktop Access)    |  |     ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
|Windows Virtueel bureaublad (WVD)    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png) |     ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
|SCA (Shared Computer Activation)    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png) |     ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Microsoft Desktop Optimalisatie Pakket    | |     ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| **Gegevensbeveiliging**        | | | 
| Preventie van gegevensverlies van Office 365, Azure Information Protection Plan 1    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Vensterinformatiebeveiliging voor eindpunt DLP    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| **Clienttoegangslicentie (CAL-rechten)**    | | |     
| Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)| |         ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| **Compliance**        | | | 
| Onbeperkt e-mailarchiveren    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Compliance Score/Compliance Manager    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| eDiscovery    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| In-place hold en litigation hold    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| MrM-bewaartags (Messaging Records Management) en bewaarbeleid    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
||||

\*Gebruikers aan wie toegang is gekregen tot SaaS-apps, kunnen Toegang krijgen tot maximaal 10 apps. Beheerders kunnen SSO configureren en de toegang van gebruikers tot verschillende SaaS-apps wijzigen, maar SSO-toegang is slechts toegestaan voor 10 apps per gebruiker tegelijk. Alle Office 365-apps worden als één app geteld.

## <a name="migration"></a>Migratie

Als u wilt migreren, werkt u samen met uw partner om uw Microsoft 365 Business Premium-abonnement en licenties te verplaatsen naar een geschikt Microsoft 365 E3-abonnement met zijn licenties.

In de volgende secties wordt beschreven welke wijzigingen u eventueel moet aanbrengen en wat u na de migratie doen.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Configuratie en gegevens van Microsoft 365-abonnementen

U hoeft geen wijzigingen aan te brengen in uw huidige abonnement of gegevens voordat u migreert, waaronder:

- Abonnementsconfiguratie, zoals DNS-domeinnamen.
- Gebruikers- en groepsaccounts en verificatie-instellingen, zoals multifactorauthenticatie of beleid voor voorwaardelijke toegang.
- Productiviteitsserviceconfiguraties en hun gegevens, zoals Teams, Exchange Online-postvakken, SharePoint Online-sites, OneDrive voor Bedrijven-mappen en OneNote-notitieblokken.

Uw gebruikers kunnen nu onbeperkt worden opgeslagen in de mappen Exchange Online en OneDrive voor Bedrijven.

U Cloud App Discovery, Azure AD Connect Health en SSO gaan gebruiken voor meer dan 10 apps.

>[!Note]
>Gebruikers die zijn gemigreerd naar Microsoft 365 E3, kunnen Outlook Customer Manager en MileIQ niet meer gebruiken.
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Bedreigingsbeveiliging

Windows 10 Business bevat de volgende beveiligingen:

- Integriteitshandhaving van het opstartproces van het besturingssysteem
- Integriteitshandhaving van gevoelige bedrijfsonderdelen
- Geavanceerde kwetsbaarheid en zero-day exploit mitigaties
- Netwerkbeveiliging op basis van reputatie voor Microsoft Edge, Internet Explorer en Chrome
- Firewall op basis van host
- Ransomware mitigaties
- Hardwarematige isolatie voor Microsoft Edge
- Toepassingsbesturingselement aangedreven door de intelligent beveiligingsgrafiek
- Apparaatbediening (USB)
- Netwerkbeveiliging voor webgebaseerde bedreigingen
- Regels voor inbraakpreventie

Windows 10 Enterprise E3 bevat ook bedrijfsbeheer van hardwaregebaseerde isolatie voor Microsoft Edge.

>[!Note]
>Gebruikers die zijn gemigreerd naar Microsoft 365 E3 hebben elk een Office 365 ATP-licentie nodig voor voortdurende bescherming tegen bedreigingen. Zorg ervoor dat u extra Office 365 ATP-licenties aanschaft, zodat alle gebruikers in het bereik van uw Office 365 ATP-politie een licentie hebben. 
>

### <a name="device-management-with-intune"></a>Apparaatbeheer met Intune

U hoeft geen wijzigingen aan te brengen in uw huidige Intune-configuratie voordat u migreert, inclusief ingeschreven apparaten en apparaat- en app-instellingen.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business Premium bevat Windows 10 Business, dat u installeren met Windows AutoPilot. Wanneer u migreert naar Microsoft 365 E3, bevat elke gebruikerslicentie Windows 10 Enterprise E3, die u ook installeren met Windows Autopilot.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365 Apps voor bedrijven

Uw Microsoft 365 Apps for business-client die op uw apparaten is geïnstalleerd, gebruikt automatisch de functies van Microsoft 365 Apps voor bedrijven. Na de migratie u nu het:

 - Volumeactivering via groepsbeleid
 - App-telemetrie
 - Besturingselementen bijwerken
 - Spreadsheet vergelijken en informeren
 - Business intelligence

