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
description: Meer informatie over het verplaatsen van uw bedrijf van Microsoft 365 Business naar Microsoft 365 E3.
ms.openlocfilehash: 9e9cfcf2212faa69f600267e4f9bfd2391e3f4e5
ms.sourcegitcommit: 9c335d110e0b499501edc8a31b987641819118a1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2020
ms.locfileid: "42811671"
---
# <a name="migrate-from-microsoft-365-business-to-microsoft-365-e3"></a>Migreren van Microsoft 365 Business naar Microsoft 365 E3

Microsoft 365 Business heeft alles wat u nodig hebt voor uw kleine bedrijf en combineert de beste cloudgebaseerde productiviteitsapps met eenvoudig apparaatbeheer en -beveiliging waarmee uw medewerkers hun beste werk kunnen doen. In sommige gevallen moet u echter uw Microsoft 365 Business-abonnement migreren naar Microsoft 365 E3. 

Uw bedrijf is bijvoorbeeld gegroeid en heeft meer dan 300 licenties nodig (gefeliciteerd, trouwens).

Uw bedrijf heeft ook zakelijke functies nodig, zoals Office 365 ProPlus, Windows 10 Enterprise E3 of Enterprise Client Access Licenses (CALs).

Upgraden is eenvoudig: u de upgrade starten [vanuit het beheercentrum.](../commerce/subscriptions/upgrade-to-different-plan.md) Al uw gegevens en configuratie in uw huidige abonnement worden bijgehouden. Er is niets voor u om te doen om voor te bereiden op de migratie en niets te doen daarna, behalve profiteren van de nieuwe functies.

>[!Note]
>U ook een Microsoft 365 Business-abonnement gebruiken voor maximaal 300 zitplaatsen en een Microsoft 365 E3-abonnement voor meer dan 300 zitplaatsen. Office 365 ATP is echter niet inbegrepen bij Microsoft 365 E3. Voor voortdurende bescherming van bedreigingen moet u extra Office 365 ATP-licenties toevoegen, zodat alle gebruikers in het kader van uw Office 365 ATP-politiegegevens een licentie hebben.
>

## <a name="differences-between-microsoft-365-business-and-microsoft-365-enterprise"></a>Verschillen tussen Microsoft 365 Business en Microsoft 365 Enterprise

In deze tabel ziet u de verschillen tussen Microsoft 365 Business en Microsoft 365 E3.

| Functie    | Ondersteuning in Microsoft 365 Business    | Ondersteuning in Microsoft 365 E3 | 
|:-------|:-----|:-----|
| **On-premises**        | | | 
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise E3| 
| Office-apps*    | [Office 365 Business](#office-365-business)    | Office 365 ProPlus | 
| **Apps voor cloudproductiviteit**        | | | 
| Exchange Online en Outlook    | 50 GB opslaglimiet per postvak en onbeperkte Exchange Online-archivering    | 100 GB opslaglimiet per postvak en onbeperkte Exchange Online-archivering | 
| Teams    | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| OneDrive voor Bedrijven    | 1 TB opslaglimiet per gebruiker    | Onbeperkt | 
| Yammer, SharePoint Online, Planner, Stream    | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Outlook Customer Manager, MileIQ    | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | | 
| **Bescherming tegen bedreigingen**        | | | 
| Mogelijkheden voor vermindering van het oppervlak aanvallen    | [Bekijk deze lijst](#threat-protection) | Enterprise-beheer van hardwaregebaseerde isolatie voor Microsoft Edge | 
| Office 365 Advanced Threat Protection (ATP) Plan 1 | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | Niet inbegrepen, maar kan worden toegevoegd op | 
| **Identiteitsbeheer**        | | | 
| Selfservice wachtwoord opnieuw instellen voor hybride Azure Active Directory -accounts (Azure AD), Azure multi-factor authentication (MFA), Voorwaardelijke toegang, wachtwoordterugschrijfterugzet voor on-premises identiteiten|     ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Detectie van cloud-apps, Azure AD Connect-status    |     | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Office 365-apps Eenmalige aanmelding (SSO): 10 apps per gebruiker (Galerij SaaS-apps zoals Salesforce)* | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Premium 1 SSO: geen limiet (on-premises apps via Azure AD Application Proxy en niet-galerijapps met selfservice-app-integratiesjablonen)    |     | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| **Apparaat- en appbeheer**        | | | 
| Microsoft Intune, Windows Autopilot|     ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
|Virtuele desktoptoegang (VDA)    |  |     ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
|Windows Virtueel bureaublad (WVD)    | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png) |     ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
|Gedeelde computeractivering (SCA)    | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png) |     ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Microsoft Desktop-optimalisatiepakket    | |     ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| **Informatiebescherming**        | | | 
| Office 365-preventie van gegevensverlies, Azure Information Protection Plan 1    | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Venstergegevensbescherming voor eindpunt DLP    | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| **Client Access License (CAL-rechten)**    | | |     
| Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)| |         ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| **Naleving**        | | | 
| Onbeperkte e-mailarchivering    | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Compliance Score/Compliance Manager    | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| eDiscovery    | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| In-place hold en litigation hold    | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
| Mrm-bewaartags en bewaarbeleid (Messaging Records Management)    | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | ![Inbegrepen bij Microsoft 365 E3](../media/check-mark.png) | 
||||

\*Gebruikers die toegang hebben gekregen tot SaaS-apps, kunnen SSO-toegang krijgen tot maximaal 10 apps. Beheerders kunnen SSO configureren en de toegang van gebruikers wijzigen tot verschillende SaaS-apps, maar SSO-toegang is alleen toegestaan voor 10 apps per gebruiker tegelijk. Alle Office 365-apps worden als één app geteld.

## <a name="migration"></a>Migratie

Als u wilt migreren, werkt u samen met uw partner om uw Microsoft 365 Business-abonnement en licenties te verplaatsen naar een geschikt Microsoft 365 E3-abonnement met zijn licenties.

In de volgende secties worden beschreven welke wijzigingen u eventueel moet aanbrengen en wat u na de migratie doen.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365-abonnementsconfiguratie en -gegevens

U hoeft geen wijzigingen aan te brengen in uw huidige abonnement of gegevens voordat u migreert, waaronder:

- Abonnementsconfiguratie, zoals DNS-domeinnamen.
- Gebruikers- en groepsaccounts en verificatie-instellingen, zoals verificatie met meerdere factoren of beleid voor voorwaardelijke toegang.
- Productiviteitsserviceconfiguraties en hun gegevens, zoals Teams, Exchange Online-postvakken, SharePoint Online-sites, OneDrive voor Bedrijven-mappen en OneNote-notitieblokken.

Uw gebruikers kunnen nu onbeperkt opslaan in de Exchange Online-postvakken en OneDrive voor Bedrijven-mappen.

U cloudappdetectie, Azure AD Connect-status en SSO gebruiken voor meer dan 10 apps.

>[!Note]
>Gebruikers die zijn gemigreerd naar Microsoft 365 E3 kunnen Outlook Customer Manager en MileIQ niet meer gebruiken.
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Bescherming tegen bedreigingen

Windows 10 Business bevat de volgende beveiligingen:

- Integriteitshandhaving van het opstartproces van het besturingssysteem
- Integriteitshandhaving van gevoelige bedrijfsonderdelen
- Geavanceerde kwetsbaarheid en zero-day exploit mitigations
- Netwerkbeveiliging op basis van reputatie voor Microsoft Edge, Internet Explorer en Chrome
- Firewall op basis van host
- Ransomware mitigaties
- Hardwaregebaseerde isolatie voor Microsoft Edge
- Toepassingsbesturing aangedreven door de Intelligent Security Graph
- Apparaatbesturing (USB)
- Netwerkbescherming voor webgebaseerde bedreigingen
- Regels voor inbraakpreventie hosten

Windows 10 Enterprise E3 bevat ook enterprise management van hardwaregebaseerde isolatie voor Microsoft Edge.

>[!Note]
>Gebruikers die zijn gemigreerd naar Microsoft 365 E3 hebben elk een Office 365 ATP-licentie nodig voor voortdurende bescherming tegen bedreigingen. Zorg ervoor dat u extra Office 365 ATP-licenties aanschaft, zodat alle gebruikers in het kader van uw Office 365 ATP-politieeen licentie hebben. 
>

### <a name="device-management-with-intune"></a>Apparaatbeheer met Intune

U hoeft geen wijzigingen aan te brengen in uw huidige Intune-configuratie voordat u migreert, inclusief ingeschreven apparaten en apparaat- en app-instellingen.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business bevat Windows 10 Business, dat u installeren met Windows AutoPilot. Wanneer u migreert naar Microsoft 365 E3, bevat elke gebruikerslicentie Windows 10 Enterprise E3, die u ook installeren met Windows Autopilot.

<a name="office-365-business"></a>
### <a name="office-365-business"></a>Office 365 Business

Uw Office 365 Business-client die op uw apparaten is geïnstalleerd, gebruikt automatisch de functies van Office 365 ProPlus. Na migratie u nu het:

 - Volumeactivering via groepsbeleid
 - App-telemetrie
 - Besturingselementen bijwerken
 - Spreadsheet vergelijken en informeren
 - Business intelligence

