---
title: Beveiligings- en compliancefuncties van Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-security-compliance
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Meer informatie over de beveiligingsfuncties die worden geleverd met Microsoft 365 Business Premium om uw gegevens op pc's, telefoons en tablets te beveiligen.
ms.openlocfilehash: 35eb0ac1dce216ccc557fc629ddb5d2df50e7134
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635139"
---
# <a name="microsoft-365-business-premium-security-and-compliance-features"></a>Beveiligings- en compliancefuncties van Microsoft 365 Business Premium

Microsoft 365 Business Premium biedt vereenvoudigde beveiligingsfuncties om uw gegevens op pc's, telefoons en tablets te beveiligen.
    
## <a name="microsoft-365-admin-center-security-features"></a>Beveiligingsfuncties van microsoft 365-beheercentrum

[![Etiket om u te laten weten dat het beheercentrum wordt gewijzigd en meer informatie vindt u op aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

U veel van de microsoft 365 Business Premium-beveiligingsfuncties beheren in het beheercentrum, waardoor u deze functies eenvoudig in- of uitschakelen. In het beheercentrum u het volgende doen:
  
- [Instellingen voor toepassingsbeheer instellen voor Android- of iOS-apparaten](app-protection-settings-for-android-and-ios.md) . 
    
    Deze instellingen omvatten het verwijderen van bestanden van een inactief apparaat na een bepaalde periode, het versleutelen van werkbestanden, waarbij gebruikers een pincode moeten instellen, enzovoort.
    
- [Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten](protection-settings-for-windows-10-devices.md) . 
    
    Deze instellingen kunnen worden toegepast op bedrijfsgegevens op zowel apparaten die eigendom zijn van het bedrijf als op apparaten die eigendom zijn van het bedrijf.
    
- [Instellingen voor apparaatbeveiliging instellen voor Windows 10-apparaten](protection-settings-for-windows-10-pcs.md) . 
    
    U [BitLocker-versleuteling](https://go.microsoft.com/fwlink/p/?linkid=871405) inschakelen om gegevens te beschermen in het geval een apparaat verloren of wordt gestolen, en [Windows Exploit Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection) in staat stellen geavanceerde bescherming te bieden tegen ransomware. 
    
- [Bedrijfsgegevens van apparaten verwijderen](remove-company-data.md)
    
    U bedrijfsgegevens op afstand wissen als een apparaat verloren, gestolen of een werknemer uw bedrijf verlaat.
    
- [Windows 10-apparaten opnieuw instellen naar hun fabrieksinstellingen.](reset-devices-to-factory-settings.md) 
    
    U alle Windows 10-apparaten waarop apparaatbeveiligingsinstellingen zijn toegepast, opnieuw instellen.
    
## <a name="additional-security-features"></a>Aanvullende beveiligings functies 

Geavanceerde functies in Microsoft 365 Business Premium zijn beschikbaar om u te helpen uw bedrijf te beschermen tegen cyberbedreigingen en gevoelige informatie te beschermen.
  
- **[Office 365 Advanced Threat Protection](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    Advanced Threat Protection (ATP) helpt uw bedrijf te beschermen tegen geavanceerde phishing- en ransomware-aanvallen die zijn ontworpen om werknemers- of klantgegevens te compromitteren. Functies zijn onder andere:
    
  - Geavanceerde attachmentscanning en AI-gestuurde analyse om gevaarlijke berichten te detecteren en te verwijderen.
    
  - Automatische controles van links in e-mail om te beoordelen of ze deel uitmaken van een phishing-regeling. Dit houdt u te beschermen tegen toegang tot onveilige websites.

- **[De volledige mogelijkheden van Intune in de Azure-portal](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Als u toegang krijgt tot het Intune-beheercentrum in de Azure-portal, u extra beveiligingsfuncties instellen, zoals het beheer van MacOS-apparaten, iPhone- en Android-apparaten, samen met geavanceerd apparaatbeheer voor Windows, die niet beschikbaar zijn via het Microsoft 365-beheercentrum.
- **Dezelfde [voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) als Azure AD Premium P1-abonnement**


    Voorwaardelijke toegang kan uw organisatie beschermen tegen aanmeldingsrisico's, toegangspogingen van een onverwacht netwerk of een landinstelling, toegangspogingen van riskante apparaattypen, enzovoort. Beleid voor voorwaardelijke toegang wordt afgedwongen nadat de eerste verificatie is voltooid en gebruikt signalen van de eerste verificatiegebeurtenis om te bepalen of de poging tot toegang moet worden goedgekeurd, geweigerd of of er meer bewijs (zoals een tweede vorm van identificatie) vereist is.

    De inbegrepen voorwaardelijke toegangsfuncties zijn:

    - Toegang op basis van gebruikersnaam, groep en rol
    - Toegang [op basis van een app](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [Toegang op basis van locatie](https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration);  alleen toegang toestaan vanuit vertrouwde IP-bereiken of specifieke landen 
    - MFA vereisen voor toegang
    - Toegang blokkeren tot apps die [verouderde verificatie](https://docs.microsoft.com/azure/active-directory/conditional-access/block-legacy-authentication) gebruiken
    - Apps vereisen tp gebruik [Intune-app-beveiliging](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - Aangepaste authenticatie zoals MFA bij externe providers, bijvoorbeeld DUO.
   
    Andere functies:
    - [Selfservice wachtwoord opnieuw instellen](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-customization) voor hybride Azure AD
    
## <a name="compliance-features"></a>Nalevingsfuncties

Uw Microsoft 365 Business Premium-abonnement bevat functies waarmee u de nalevings- en regelgevingsnormen handhaven.

- **[Overzicht van het beleid ter voorkoming van gegevensverlies](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)** (DLP). 
    
    U DLP zo instellen dat gevoelige informatie, zoals creditcardnummers, burgerservicenummers enzovoort, automatisch wordt gedetecteerd om te voorkomen dat ze onbedoeld buiten uw bedrijf worden gedeeld.
    
- **[Exchange Online Archiving](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Exchange Online Archiveren licentie maakt het mogelijk berichten gemakkelijk te archiveren met continue back-up van gegevens. Het slaat alle e-mails van een gebruiker op, inclusief verwijderde items, voor het geval ze later nodig zijn voor ontdekking of restauratie. Daarnaast u verschillende bewaarbeleidsregels gebruiken om e-mailgegevens te bewaren voor procesblokkeringen, eDiscovery of om te voldoen aan de nalevingsvereisten.
    
- **[Gevoeligheidslabels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)**

   Microsoft 365 Business Premium bevat alle functies van [Azure Information Protection Plan 1.](https://go.microsoft.com/fwlink/p/?linkid=871407) Met dit plan u **gevoeligheidslabels** maken waarmee u de toegang tot gevoelige informatie in e-mail en documenten beheren, met besturingselementen zoals 'Niet doorsturen' en 'Niet kopiëren'. U gevoelige informatie ook classificeren als 'Vertrouwelijk' en opgeven hoe geclassificeerde informatie buiten en binnen het bedrijf kan worden gedeeld. Versleuteling op bedrijfsniveau is eenvoudig toe te passen op e-mail en documenten om uw gegevens privé te houden. U ook de azure information protection-client-invoegtoepassing voor Office-apps installeren. Zie [Azure Information Protection unified labeling client](https://docs.microsoft.com/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)voor meer informatie. Installeer voor gevoeligheidslabels de **AzInfoProtection_UL.exe**.

U deze functies &amp; beheren in het Security Compliance center en het Intune-beheercentrum. Na verloop van tijd worden de vereenvoudigde besturingselementen toegevoegd aan het Microsoft 365-beheercentrum.
  
    
## <a name="faq"></a>Veelgestelde vragen

 ### <a name="are-these-security-features-available-in-all-markets"></a>Zijn deze beveiligingsfuncties beschikbaar in alle markten?
  
Ja, deze functies zijn beschikbaar in alle markten waar Microsoft 365 Business Premium wordt verkocht.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Hoe vind ik &amp; het Security Compliance center?
  
1. [Meld u aan bij Microsoft 365 Business Premium](https://portal.microsoft.com/) met uw beheerdersreferenties. 
    
2. Zoek in de **linkernavigatie-centra** en breid deze uit. 
    
    ![Kies Beheercentra in de linkernavigatiebalk in het Microsoft 365-beheercentrum.](../media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Kies ** &amp; Security Compliance** om &amp; naar security compliance center te gaan.
