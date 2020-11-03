---
title: Functies voor beveiliging en compliance van Microsoft 365 Business Premium
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
description: Meer informatie over de beveiligingsfuncties die worden geleverd bij Microsoft 365 Business Premium om uw gegevens op Pc's, telefoons en tablets te beschermen.
ms.openlocfilehash: 587d80c27f867a387c901d23f4ec05f3c5905bf6
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843483"
---
# <a name="microsoft-365-business-premium-security-and-compliance-features"></a>Functies voor beveiliging en compliance van Microsoft 365 Business Premium

Microsoft 365 Business Premium biedt eenvoudige beveiligingsfuncties waarmee u uw gegevens op Pc's, telefoons en tablets kunt beschermen.
    
## <a name="microsoft-365-admin-center-security-features"></a>Beveiligingsfuncties van het Microsoft 365-Beheercentrum

U kunt een groot aantal beveiligingsfuncties in Microsoft 365 Business Premium beheren in het Beheercentrum, zodat u een eenvoudige manier om deze functies in of uit te schakelen. In het Beheercentrum kunt u het volgende doen:
  
- [Instellingen voor toepassingsbeheer instellen voor Android-of IOS-apparaten](app-protection-settings-for-android-and-ios.md) . 
    
    Met deze instellingen kunt u bestanden van een inactief apparaat verwijderen na een ingestelde periode, het versleutelen van werkbestanden, zodat gebruikers een pincode moeten instellen, enzovoort.
    
- [Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten](protection-settings-for-windows-10-devices.md) . 
    
    Deze instellingen kunnen worden toegepast op bedrijfsgegevens op bedrijfseigen of persoonlijke apparaten.
    
- [Beveiligingsinstellingen voor apparaten instellen voor Windows 10-apparaten](protection-settings-for-windows-10-pcs.md) 
    
    U kunt [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405) -versleuteling inschakelen om gegevens te beschermen voor het geval een apparaat gaat verloren of gestolen, en [Windows exploit Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection) inschakelen voor een geavanceerde beveiliging voor Ransomware. 
    
- [Bedrijfsgegevens van apparaten verwijderen](remove-company-data.md)
    
    U kunt bedrijfsgegevens Extern wissen als een apparaat gaat verloren, gestolen of een werknemer laat uw bedrijf verlaten.
    
- [De fabrieksinstellingen van Windows 10-apparaten herstellen](reset-devices-to-factory-settings.md) . 
    
    U kunt alle Windows 10-apparaten herstellen waarop de instellingen voor apparaat-beveiliging zijn toegepast.
    
## <a name="additional-security-features"></a>Aanvullende beveiligings functies 

Geavanceerde functies in Microsoft 365 Business Premium zijn beschikbaar om u te helpen uw bedrijf te beschermen tegen een Cyber-Threat en gevoelige informatie te beschermen.
  
- **[Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)**
    
    Microsoft Defender voor Office 365 helpt uw bedrijf te beschermen tegen een verfijnde phishing-en Ransomware-aanval, zodat medewerkers of klantengegevens kunnen binnendringen. Functies zijn onder andere:
    
  - Geavanceerde bijlage scan en AI-krachtige analyse voor het detecteren en verwijderen van schadelijke berichten.
    
  - Automatische controle van koppelingen in een e-mail om te beoordelen of ze deel uitmaken van een malafide programma. Dit houdt in dat u toegang hebt tot onveilige websites.

- **[De volledige functionaliteit van intune in de Azure-Portal](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Als u het intune-Beheercentrum opent in de Azure-Portal, kunt u extra beveiligingsfuncties instellen, zoals het beheer van MacOS-apparaten, iPhone en Android-apparaten, en die niet beschikbaar zijn via het Microsoft 365-Beheercentrum.
- **Dezelfde [voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) als Azure AD Premium P1-abonnement**


    Met behulp van voorwaardelijke toegang kunt u uw organisatie beschermen tegen een onverwacht risico, de toegang tot pogingen van een onverwacht netwerk of een andere landinstelling, toegang krijgen tot de typen risico apparatuur, enzovoort. Beleidsregels voor voorwaardelijke toegang worden afgedwongen na voltooiing van de eerste authenticatie, en het gebruik van signalen van de eerste verificatiegebeurtenis om te bepalen of de gevraagde toegang moet worden goedgekeurd, geweigerd of als er meer controle nodig is, zoals een tweede vorm van identificatie.

    Voor de functies voor voorwaardelijke toegang zijn de volgende opties beschikbaar:

    - Toegang op basis van gebruikersnaam, groep en rol
    - Toegang [op basis van een app](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [Toegang op basis van locatie](https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration);  alleen toegang toestaan vanuit vertrouwde IP-bereiken of bepaalde landen 
    - MFA vereisen voor toegang
    - Toegang tot apps via [oudere verificatie](https://docs.microsoft.com/azure/active-directory/conditional-access/block-legacy-authentication) blokkeren
    - Apps moeten worden gebruikt in de bescherming van de [intune-app](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - Aangepaste verificatie, zoals MFA met leveranciers van derden, bijvoorbeeld DUO.
   
    Andere functies:
    - [Selfservice voor wachtwoordherstel](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-customization) voor hybride Azure AD
    
## <a name="compliance-features"></a>Nalevings functies

Uw Microsoft 365 Business Premium-abonnement bevat functies waarmee u normen en normen voor naleving en regulering kunt bijhouden.

- **[Overzicht van beleidsregels voor preventie van gegevensverlies](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)** (DLP). 
    
    U kunt DLP instellen om te voorkomen dat gevoelige informatie, zoals creditcardnummers, nummers voor sofi-nummers, en dergelijke, om te voorkomen dat anderen buiten uw bedrijf onbedoeld delen.
    
- **[Exchange Online Archiving](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Met de licentie voor archivering met Exchange Online kunnen berichten eenvoudig worden gearchiveerd met continue gegevensback-up. Het bevat alle e-mailberichten van een gebruiker, inclusief verwijderde items, voor het geval ze later worden gebruikt voor ontdekking of herstel. Daarnaast kunt u een ander bewaarbeleid gebruiken om e-mail gegevens te bewaren voor beantwoordings regels, eDiscovery of om aan nalevingsvereisten te voldoen.
    
- **[Vertrouwelijkheidslabels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)**

   Microsoft 365 Business Premium omvat alle functies van [Azure Information Protection (abonnement 1](https://go.microsoft.com/fwlink/p/?linkid=871407)). Met dit abonnement kunt u tekstrisico **labels** maken waarmee u de toegang tot gevoelige informatie in e-mail en documenten kunt beheren, met besturingselementen als niet doorsturen en niet kopiëren. U kunt ook gevoelige informatie classificeren als vertrouwelijk en opgeven hoe geclassificeerde informatie buiten en binnen het bedrijf kan worden gedeeld. Bedrijfskwaliteit versleuteling is eenvoudig van toepassing op e-mail en documenten om uw informatie privé te houden. U kunt ook de clienttoepassing voor Azure Information Protection voor Office-apps installeren. Zie voor meer informatie de uitgebreide [client voor Azure Information Protection (Unified labels](https://docs.microsoft.com/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)). Voor de tekstlabels, installeert u de **AzInfoProtection_UL.exe**.

U kunt deze functies beheren in het beveiligings &amp; conformiteitscentrum en het intune-Beheercentrum. In de loop van de tijd worden de vereenvoudigde besturingselementen toegevoegd aan het Microsoft 365-Beheercentrum.
  
    
## <a name="faq"></a>Veelgestelde vragen

 ### <a name="are-these-security-features-available-in-all-markets"></a>Zijn deze beveiligingsfuncties beschikbaar in alle landen/regio's?
  
Ja, deze functies zijn beschikbaar in alle landen waar Microsoft 365 Business Premium wordt verkocht.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Hoe kan ik het beveiligings &amp; conformiteitscentrum vinden?
  
1. [Meld u aan bij Microsoft 365 Business Premium](https://portal.microsoft.com/) met uw beheerdersreferenties. 
    
2. Zoek **beheer centra** in het linkerdeel centrum en vouw dit uit. 
    
    ![Kies beheer centra in het linker navigatieonderdeel in het Microsoft 365-Beheercentrum.](../media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Kies **beveiligings &amp; naleving** om naar het beveiligings &amp; compliance-centrum te gaan.
