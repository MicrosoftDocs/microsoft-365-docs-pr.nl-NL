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
description: Meer informatie over hoe u uw bedrijf kunt overzetten van Microsoft 365 Business Premium naar Microsoft 365 E3.
ms.openlocfilehash: 874da0d35759c8af4c3ee2ca4a1bdfa90a91627c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842195"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Migreren van Microsoft 365 Business Premium naar Microsoft 365 E3

Microsoft 365 Business Premium biedt alles wat u nodig hebt voor uw kleine bedrijf en combineert de beste productiviteitstoepassingen in de Cloud, met eenvoudige Apparaatbeheer en beveiliging, zodat uw werknemers de beste werk kunnen doen. In sommige gevallen moet u uw abonnement op Microsoft 365 Business Premium ook migreren naar Microsoft 365 E3. 

Uw bedrijf is bijvoorbeeld gekweekt en u hebt meer dan 300 licenties nodig (Gefeliciteerd).

Of uw bedrijf heeft ondernemingsfuncties nodig, zoals Microsoft 365-apps voor Enterprise, Windows 10 Enterprise E3 of Enterprise Client Access licenties.

Een upgrade is eenvoudig: u kunt de upgrade starten [vanuit het Beheercentrum](../commerce/subscriptions/upgrade-to-different-plan.md). Al uw gegevens en configuratie in uw huidige abonnement blijven behouden. U hoeft niets te doen om de migratie te voorbereiden en niets later te doen, tenzij u de nieuwe functies gaat gebruiken.

>[!Note]
>U kunt ook een Microsoft 365 Business Premium-abonnement voor maximaal 300 stoelen gebruiken en een Microsoft 365 E3-abonnement kopen voor meer dan 300 seats. Microsoft Defender voor Office 365 is echter niet opgenomen in Microsoft 365 E3. Voor een voortdurende bedreigingsbeveiliging moet u extra Defender voor Office 365-licenties toevoegen, zodat alle gebruikers in het bereik van uw 365 voor Office een licentie voor u zijn.
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Verschillen tussen Microsoft 365 Business Premium en Microsoft 365 Enterprise

In deze tabel ziet u de verschillen tussen Microsoft 365 Business Premium en Microsoft 365 E3.

| Functie    | Ondersteuning in Microsoft 365 Business Premium    | Ondersteuning in Microsoft 365 E3 | 
|:-------|:-----|:-----|
| **On-premises**        | | | 
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise E3| 
| Office-apps *    | [Microsoft 365-apps voor bedrijven](#office-365-business)    | Microsoft 365-apps voor ondernemingen | 
| **Apps voor Cloud productiviteit**        | | | 
| Exchange Online en Outlook    | 50 GB opslaglimiet per postvak en onbeperkt Exchange Online archivering    | 100 GB opslaglimiet per postvak en onbeperkt Exchange Online archivering | 
| Teams    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| OneDrive voor Bedrijven    | 1 TB opslaglimiet per gebruiker    | Begrensd | 
| Yammer, SharePoint Online, planner, stream    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| Outlook Customer Manager, MileIQ    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Bedreigingsbeveiliging**        | | | 
| Minder mogelijkheden voor oppervlakte van aanval    | [Bekijk deze lijst](#threat-protection) | Enterprise-beheer van hardwarematige isolatie voor Microsoft Edge | 
| Abonnement 1 voor Office 365 | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | Niet inbegrepen, maar kan worden toegevoegd aan | 
| **Identiteitsbeheer**        | | | 
| Selfservice voor wachtwoordherstel voor hybride Azure Active Directory-accounts (Azure AD), Azure multi-factor Authentication (MFA), voorwaardelijke toegang, wachtwoord terugschrijven voor on-premises id's|     ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| Detectie van Cloud apps, Azure AD Connect Health    |     | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Office 365-apps eenmalige Sign-On (SSO): 10 apps per gebruiker (Galerie SaaS-apps zoals Salesforce) * | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Premium 1 SSO: geen limiet (on-premises apps via Azure AD-toepassings proxy en niet-galerij-apps met beSelf-Service hulp van sjablonen voor de integratie van apps)    |     | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| **Apparaten en apps beheren**        | | | 
| Microsoft intune, Windows auto pilot|     ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
|Toegang tot virtueel bureaublad (VDA)    |  |     ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
|Windows virtueel bureaublad (WVD)    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png) |     ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
|Een SCA (gedeelde computer activering)    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png) |     ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| Microsoft Desktop optimaliserings pakket    | |     ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| **Gegevensbeveiliging**        | | | 
| Office 365 preventie van gegevensverlies, Azure Information Protection (abonnement 1)    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| Windows-informatiebescherming voor DLP-eindpunttoewijzer    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| **Licentie voor client toegang (CAL-rechten)**    | | |     
| Enterprise CAL suite (Exchange, SharePoint, Skype, Windows, Microsoft endpoint Configuration Manager, Windows Rights Management)| |         ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| **Compliance**        | | | 
| Onbeperkt e-mail archivering    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| Compliancebeheer    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| eDiscovery    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| Bewaren en ter plaatse bewaren    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
| Tags van het bewaarbeleid voor MRM en bewaren van berichten    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Microsoft 365 E3](../media/check-mark.png) | 
||||

\* Gebruikers aan wie toegang is verleend tot SaaS-apps, kunnen EENMALIGe toegang krijgen tot maximaal 10 apps. Beheerders kunnen eenmalige aanmelding configureren en gebruikers toegang tot verschillende SaaS-apps wijzigen, maar SSO-toegang wordt alleen toegestaan voor 10 apps per gebruiker. Alle Office 365-apps worden als één app geteld.

## <a name="migration"></a>Migratie

Als u wilt migreren, werkt u met uw partner om uw abonnement op Microsoft 365 Business Premium te verplaatsen en licenties te verplaatsen naar een geschikt Microsoft 365 E3-abonnement met de licenties.

In de volgende secties wordt beschreven welke wijzigingen u moet aanbrengen, indien van toepassing, en wat u na de migratie kunt doen.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Configuratie van Microsoft 365-abonnement en-gegevens

U hoeft geen wijzigingen aan te brengen in uw huidige abonnement of gegevens vóór de overstap, waaronder:

- Configuratie van het abonnement, zoals DNS-domeinnamen.
- Accounts en verificatie-instellingen van gebruikers en groepen, zoals multi-factor Authentication of regels voor voorwaardelijke toegang.
- Productiviteits serviceconfiguraties en hun gegevens, zoals teams, Exchange Online-postvakken, SharePoint Online-sites, OneDrive voor bedrijven-mappen en OneNote-notitieblokken.

Uw gebruikers kunnen nu onbeperkt bewaren in de mappen Exchange Online en OneDrive voor bedrijven.

U kunt de detectie van Cloud apps, Azure AD Connect Health en SSO voor meer dan 10 apps gaan gebruiken.

>[!Note]
>Gebruikers die zijn gemigreerd naar Microsoft 365 E3, kunnen niet langer gebruikmaken van Outlook Customer Manager en MileIQ.
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Bedreigingsbeveiliging

Windows 10 Business omvat deze beveiligingsmaatregelen:

- Integriteitscontrole voor het opstartproces van het besturingssysteem
- Integriteits handhaving van gevoelige besturings onderdelen
- Geavanceerd beveiligingslek en het oplossen van problemen met Zero Day
- Computerbeveiliging op basis van reputatie voor Microsoft Edge, Internet Explorer en Chrome
- Op host gebaseerde firewall
- Ransomware-beperkingen
- Hardwarematige isolatie voor Microsoft Edge
- Toepassings besturingselement ingeschakeld door de intelligente beveiligings grafiek
- Apparaatbesturing (USB)
- Netwerkbeveiliging voor op internet gebaseerde bedreigingen
- Regels voor preventie van bescherming hosten

Windows 10 Enterprise E3 omvat ook Enterprise-beheer van hardwarematige isolatie voor Microsoft Edge.

>[!Note]
>Gebruikers die zijn gemigreerd naar Microsoft 365 E3, hebben elk een Microsoft Defender for Office 365-licentie nodig voor de voortdurende beveiliging van de bedreiging. Zorg ervoor dat u extra licenties voor de versie van Defender voor Office 365 koopt, zodat alle gebruikers in het bereik van uw 365 voor Office een licentie voor u zijn. 
>

### <a name="device-management-with-intune"></a>Apparaatbeheer met intune

U hoeft geen wijzigingen aan te brengen in uw huidige intune-configuratie voordat deze worden gemigreerd, waaronder geregistreerde apparaten en apparaat-en app-instellingen.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business Premium omvat Windows 10 Business, dat u kunt installeren met Windows auto pilot. Wanneer u migreert naar Microsoft 365 E3, bevat elke gebruikerslicentie Windows 10 Enterprise E3, dat u ook kunt installeren met de automatische proefversie van Windows.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365-apps voor bedrijven

Uw Microsoft 365 apps voor bedrijven-client op uw apparaten wordt automatisch gestart met de functies van Microsoft 365-apps voor Enterprise. Na de migratie kunt u nu het volgende gebruiken:

 - Volume activering via Groepsbeleid
 - App-telemetrie
 - Besturingselementen bijwerken
 - Spreadsheets vergelijken en opvragen
 - Bedrijfsinformatie

