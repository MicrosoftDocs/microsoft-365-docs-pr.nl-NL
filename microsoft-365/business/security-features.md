---
title: Microsoft 365 zakelijke beveiligings-en compliancefuncties
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Informatie over de beveiligingsfuncties die bij Microsoft 365 Business worden geleverd.
ms.openlocfilehash: 8e45d5fdb6a78f3966c46542189aa30ddd80998e
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288450"
---
# <a name="microsoft-365-business-security-and-compliance-features"></a>Microsoft 365 zakelijke beveiligings-en compliancefuncties

Microsoft 365 Business biedt vereenvoudigde beveiligingsfuncties om uw gegevens op Pc's, telefoons en tablets te beveiligen.
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Beveiligingsfuncties van Microsoft 365 Business Admin Center

[![Label om u te laten weten dat het Admin Center is aan het veranderen en u meer informatie vinden op aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

U veel van de Microsoft 365 Business Security-functies beheren in het Admin Center, waarmee u een vereenvoudigde manier om deze functies in of uit te schakelen. In het Admin Center u het volgende doen:
  
  
- [Instellingen voor toepassingsbeheer instellen voor Android-of IOS-apparaten](app-protection-settings-for-android-and-ios.md) . 
    
    Deze instellingen omvatten het verwijderen van bestanden van een inactief apparaat na een bepaalde periode, het versleutelen van werkbestanden, vereisen dat gebruikers een pincode instellen, enz.
    
- [Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten](protection-settings-for-windows-10-devices.md) . 
    
    Deze instellingen kunnen worden toegepast op bedrijfsgegevens op zowel bedrijfseigen als persoonlijk eigendom apparaten.
    
- [Stel instellingen voor Apparaatbeveiliging in voor Windows 10-apparaten](protection-settings-for-windows-10-pcs.md) . 
    
    U [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405) -versleuteling inschakelen om gegevens te beschermen in het geval een apparaat is verloren of gestolen, en [Windows exploit Guard](https://go.microsoft.com/fwlink/p/?linkid=871404) inschakelen om geavanceerde bescherming tegen Ransomware te bieden. 
    
- [Bedrijfsgegevens van apparaten verwijderen](remove-company-data.md)
    
    U bedrijfsgegevens op afstand wissen als een apparaat is kwijtgeraakt, gestolen of als een werknemer uw bedrijf verlaat.
    
- [Reset Windows 10-apparaten naar hun fabrieksinstellingen](reset-devices-to-factory-settings.md) . 
    
    U alle Windows 10-apparaten waarop de instellingen voor apparaatbeveiliging zijn toegepast, opnieuw instellen.
    
## <a name="additional-security-features"></a>Aanvullende beveiligings functies 

Geavanceerde functies in Microsoft 365 Business zijn beschikbaar om u te helpen uw bedrijf te beschermen tegen cyberdreigingen en gevoelige informatie te beveiligen.
  
- **[Office 365 geavanceerde Bedreigingsbeveiliging](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    Advanced Threat Protection (ATP) helpt uw bedrijf te beschermen tegen geavanceerde phishing-en ransomwareaanvallen, ontworpen om medewerkers-of klantgegevens te compromitteren. De functies omvatten:
    
  - Geavanceerde bijlage scanning en AI-gedreven analyse om gevaarlijke berichten te detecteren en te verwijderen.
    
  - Automatische controles van links in e-mail om te beoordelen of ze deel uitmaken van een phishing-schema. Hierdoor blijft u veilig toegang krijgen tot onveilige websites.

- **[De volledige mogelijkheden van intune in azure Portal](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Toegang tot het intune-Beheercentrum in azure Portal stelt u in staat extra beveiligingsfuncties in te stellen, zoals het beheer van MacOS-apparaten, iPhone-en Android-apparaten, samen met Geavanceerd Apparaatbeheer voor Windows, die niet beschikbaar zijn via Microsoft 365 Business Admin Center.
- **Dezelfde [voorwaardelijke toegang](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/overview) als Azure AD P1-abonnement**

    Voorwaardelijke toegang kan helpen uw organisatie te beschermen tegen aanmeldingsrisico, toegang tot pogingen van een onverwacht netwerk of locale, toegangspogingen vormen riskante apparaattypen, enzovoort. Beleid voor voorwaardelijke toegang worden afgedwongen nadat de eerste verificatie is voltooid en maakt gebruik van signalen van de eerste verificatie gebeurtenis om te bepalen of de poging tot toegang moet worden goedgekeurd, weigert of f meer bewijs (zoals tweede vorm van identificatie) is Vereist.

    De functies voor voorwaardelijke toegang zijn:

    - Toegang op basis van gebruikersnaam, groep en rol
    - Toegang [op basis van een app](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [Toegang op basis van locatie](https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration);  alleen toegang via vertrouwde IP-bereiken of specifieke landen toestaan 
    - MFA vereisen voor toegang
    - Toegang tot apps blokkeren die gebruikmaken van [verouderde verificatie](https://docs.microsoft.com/azure/active-directory/conditional-access/block-legacy-authentication)
    - Apps vereisen TP gebruik [intune app Protection](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - Aangepaste verificatie, zoals MFA met derden-providers, bijvoorbeeld DUO.
   
    Andere functies:
    - [Self-service voor wachtwoordherstel](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-customization) voor hybride Azure AD
    
## <a name="compliance-features"></a>Nalevingsfuncties

Uw Microsoft 365 Business-abonnement bevat functies waarmee u nalevings-en regelgevings standaarden handhaven.

- **[Overzicht van beleid voor preventie van gegevensverlies](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)** (DLP). 
    
    U DLP instellen om automatisch gevoelige informatie te detecteren, zoals creditcardnummers, sociale-zekerheids nummers, enzovoort, om te voorkomen dat ze onbedoeld worden gedeeld buiten uw bedrijf.
    
- **[Exchange Online Archiving](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Met Exchange Online-archiverings licentie kunnen berichten eenvoudig worden gearchiveerd met doorlopende gegevensback-up. Het slaat alle e-mails van een gebruiker, met inbegrip van verwijderde items, in het geval ze later nodig zijn voor detectie of herstel. Daarnaast u verschillende bewaarbeleidsregels gebruiken om e-mail gegevens te bewaren voor juridische bewaring, eDiscovery of om te voldoen aan nalevingsvereisten.
    
- **[Azure Information Protection](https://go.microsoft.com/fwlink/p/?linkid=871406)**
    
    Informatiebeveiliging helpt u toegang te beheren tot gevoelige informatie in e-mail en documenten met besturingselementen zoals ' niet doorsturen ' en ' niet kopiëren '. U gevoelige informatie ook classificeren als ' vertrouwelijk ' en opgeven hoe gerubriceerde informatie kan worden gedeeld buiten en binnen het bedrijf. Versleuteling op ondernemingsniveau is eenvoudig toe te passen op e-mail en documenten om uw informatie privé te houden. Microsoft 365 Business bevat alle functies van [Azure Information Protection Plan 1](https://go.microsoft.com/fwlink/p/?linkid=871407). U ook de Azure Information Protection-Client-invoegtoepassingen voor Office-apps installeren. Zie voor meer informatie, [Azure Information Protection-client beheerdershandleiding](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide).

U deze functies beheren in het Security &amp; compliance Center en het intune Admin Center. Na verloop van tijd zullen de vereenvoudigde besturingselementen worden toegevoegd aan het Microsoft 365 Business Admin Center.
  
    
## <a name="faq"></a>Veelgestelde vragen

 ### <a name="are-these-security-features-available-in-all-markets"></a>Zijn deze beveiligingsfuncties beschikbaar in alle markten?
  
Ja, deze functies zijn beschikbaar in alle markten waar Microsoft 365 Business wordt verkocht.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Hoe vind ik het Security &amp; compliance Center?
  
1. [Meld u aan bij Microsoft 365 Business](https://portal.microsoft.com/) met behulp van uw beheerdersreferenties. 
    
2. Zoek in de linker navigatie **admin Centers** en vouw deze uit. 
    
    ![Kies in de linker NAV in het Microsoft 365 Admin Center, admin Centers.](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Kies ** &amp; naleving** van beveiliging om te gaan &amp; naar Security compliance Center.