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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Meer informatie over de beveiligingsfuncties van Microsoft 365 Business Premium om uw gegevens op pc's, telefoons en tablets te beschermen.
ms.openlocfilehash: f04a998c74128edac306167617e073c412fce2ea
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198406"
---
# <a name="microsoft-365-business-premium-security-and-compliance-features"></a>Beveiligings- en compliancefuncties van Microsoft 365 Business Premium

Microsoft 365 Business Premium biedt vereenvoudigde beveiligingsfuncties om uw gegevens op pc's, telefoons en tablets te beschermen.
    
## <a name="microsoft-365-admin-center-security-features"></a>Beveiligingsfuncties van het Microsoft 365-beheercentrum

U kunt veel beveiligingsfuncties van Microsoft 365 Business Premium beheren in het beheercentrum, zodat u deze functies eenvoudiger kunt in- of uitschakelen. In het beheercentrum kunt u het volgende doen:
  
- [Instellingen voor toepassingsbeheer instellen voor Android- of iOS-apparaten.](app-protection-settings-for-android-and-ios.md) 
    
    Deze instellingen omvatten het verwijderen van bestanden van een inactief apparaat na een bepaalde periode, het versleutelen van werkbestanden, het vereisen dat gebruikers een pincode instellen, en dergelijke.
    
- [Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten.](protection-settings-for-windows-10-devices.md) 
    
    Deze instellingen kunnen worden toegepast op bedrijfsgegevens op zowel bedrijfsapparaten als persoonlijke apparaten.
    
- [Apparaatbeveiligingsinstellingen instellen voor Windows 10-apparaten.](protection-settings-for-windows-10-pcs.md) 
    
    U kunt [BitLocker-versleuteling](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions) inschakelen om gegevens te beschermen in geval van verlies of diefstal van een apparaat en [Windows Exploit Guard](/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection) inschakelen om geavanceerde beveiliging tegen ransomware te bieden. 
    
- [Bedrijfsgegevens van apparaten verwijderen](remove-company-data.md)
    
    U kunt bedrijfsgegevens op afstand wissen als een apparaat verloren gaat, wordt gestolen of als een werknemer uw bedrijf verlaat.
    
- [Windows 10-apparaten opnieuw instellen op de fabrieksinstellingen.](reset-devices-to-factory-settings.md) 
    
    U kunt alle Windows 10-apparaten met apparaatbeveiligingsinstellingen opnieuw instellen.
    
## <a name="additional-security-features"></a>Aanvullende beveiligingsfuncties 

De geavanceerde functies zijn beschikbaar in Microsoft 365 Business Premium voor de beveiliging van je business tegen cyber-dreigingen en de bescherming van gevoelige informatie.
  
- **[Microsoft Defender voor Office 365](../security/office-365-security/defender-for-office-365.md)**
    
    Microsoft Defender voor Office 365 helpt uw bedrijf te beschermen tegen geavanceerde phishing- en ransomware-aanvallen die zijn ontworpen om werknemers- of klantgegevens in gevaar te brengen. De volgende functies zijn:
    
  - Geavanceerde bijlagescanning en AI-analyse om gevaarlijke berichten te detecteren en te verwijderen.
    
  - Automatische controles van koppelingen in e-mail om te beoordelen of ze deel uitmaken van een phishing-regeling. Op deze manier kunt u geen toegang krijgen tot onveilige websites.

- **[De volledige mogelijkheden van Intune in de Azure-portal](/mem/intune/fundamentals/what-is-intune)**
    
    Als u toegang hebt tot het Intune-beheercentrum in de Azure-portal, kunt u extra beveiligingsfuncties instellen, zoals het beheer van MacOS-apparaten, iPhone- en Android-apparaten, samen met geavanceerd apparaatbeheer voor Windows, die niet beschikbaar zijn via het Microsoft 365-beheercentrum.
- **Dezelfde [voorwaardelijke toegang](/azure/active-directory/conditional-access/overview) als Azure AD Premium P1-abonnement**


    Voorwaardelijke toegang kan uw organisatie helpen beschermen tegen aanmeldingsrisico's, toegangspogingen vanuit een onverwacht netwerk of land, toegangspogingen van risicovolle apparaattypen, en meer. Beleid voor voorwaardelijke toegang wordt afgedwongen nadat de eerste verificatie is voltooid en er worden signalen van de eerste verificatiegebeurtenis gebruikt om te bepalen of de poging tot toegang moet worden goedgekeurd, geweigerd of dat er meer bewijs (zoals een tweede identificatieformulier) vereist is.

    De meegeleverde functies voor voorwaardelijke toegang zijn:

    - Access op basis van gebruikersnaam, groep en rol
    - Access [op basis van een app](/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [Toegang op basis van locatie;](/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration)  alleen toegang toestaan vanuit vertrouwde IP-bereiken of specifieke landen 
    - MFA vereisen voor toegang
    - Toegang blokkeren tot apps die gebruikmaken van [oudere verificatie](/azure/active-directory/conditional-access/block-legacy-authentication)
    - Apps vereisen om [Intune-appbeveiliging te gebruiken](/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - Aangepaste verificatie, zoals MFA bij externe providers, bijvoorbeeld DUO.
   
    Andere functies:
    - [Selfservice password reset voor](/azure/active-directory/authentication/concept-sspr-customization) hybride Azure AD
    
## <a name="compliance-features"></a>Compliancefuncties

Uw Microsoft 365 Business Premium-abonnement bevat functies die u helpen nalevings- en regelgevingsstandaarden te handhaven.

- **[Overzicht van beleid voor preventie van gegevensverlies](../compliance/data-loss-prevention-policies.md)** (DLP). 
    
    U kunt DLP zo instellen dat gevoelige informatie automatisch wordt gedetecteerd, zoals creditcardnummers, socialezekerheidsnummers, en dergelijke, om te voorkomen dat deze onbedoeld worden gedeeld buiten uw bedrijf.
    
- **[Exchange Online Archiving](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Met exchange Online Archiving-licentie kunnen berichten eenvoudig worden gearchiveerd met een continue back-up van gegevens. Alle e-mailberichten van een gebruiker, inclusief verwijderde items, worden op de e-mail op slaat voor het geval ze later nodig zijn voor detectie of herstel. Daarnaast kunt u verschillende bewaarbeleidsregels gebruiken om e-mailgegevens te bewaren voor juridische bewaring, eDiscovery of om te voldoen aan de nalevingsvereisten.
    
- **[Vertrouwelijkheidslabels](../compliance/sensitivity-labels.md)**

   Microsoft 365 Business Premium bevat alle functies van [Azure Information Protection Plan 1](https://go.microsoft.com/fwlink/p/?linkid=871407). Met dit plan kunt  u gevoeligheidslabels maken waarmee u de toegang tot gevoelige informatie in e-mail en documenten kunt bepalen, met besturingselementen zoals 'Niet doorsturen' en 'Niet kopiëren'. U kunt gevoelige informatie ook classificeren als 'Vertrouwelijk' en opgeven hoe gerubriceerde gegevens binnen en buiten het bedrijf kunnen worden gedeeld. Versleuteling op ondernemingsniveau is eenvoudig toe te passen op e-mail en documenten om uw gegevens privé te houden. U kunt ook de azure information protection-client-invoegvoeging voor Office-apps installeren. Zie Geïntegreerde [labelingclient voor Azure Information Protection voor meer informatie.](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history) Voor Gevoeligheidslabels installeert u **deAzInfoProtection_UL.exe.**

U kunt deze functies beheren in het Beveiligings &amp; compliancecentrum en het Intune-beheercentrum. Na een tijd worden de vereenvoudigde besturingselementen toegevoegd aan het Microsoft 365-beheercentrum.
  
    
## <a name="faq"></a>Veelgestelde vragen

 ### <a name="are-these-security-features-available-in-all-markets"></a>Zijn deze beveiligingsfuncties beschikbaar in alle markten?
  
Ja, deze functies zijn beschikbaar in alle markten waar Microsoft 365 Business Premium wordt verkocht.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Hoe vind ik het Beveiligings &amp; compliancecentrum?
  
1. [Meld u aan bij Microsoft 365 Business Premium](https://portal.microsoft.com/) met behulp van uw beheerdersreferenties. 
    
2. Zoek in het linkernavigatienavigatiecentrum **naar Beheercentra** en vouw deze uit. 
    
    ![Kies beheercentra in het linkernavigatiepunt in het Microsoft 365-beheercentrum.](../media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Kies **Beveiligings &amp; compliance om** naar het Beveiligings &amp; compliancecentrum te gaan.
