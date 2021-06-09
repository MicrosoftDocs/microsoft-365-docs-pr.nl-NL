---
title: Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop
description: Certificaatvereisten en wi-fi-connectiviteit
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: a59add6f6821824f189703b3dedd35fda313ec31
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574581"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop  
 
Verificatie op basis van certificaten is een veelvoorkomende vereiste voor klanten die Microsoft Managed Desktop. Mogelijk hebt u certificaten nodig voor toegang tot Wi-Fi of LAN, om verbinding te maken met VPN-oplossingen of voor toegang tot interne resources in uw organisatie.   
 
Omdat Microsoft Managed Desktop-apparaten zijn verbonden met Azure Active Directory (Azure AD) en worden beheerd door Microsoft Intune, moet u dergelijke certificaten implementeren met behulp van een SCEP-certificaat (Simple Certificate Enrollment Protocol) of een PKCS-certificaatinfrastructuur (Public Key Cryptography Standard) die is geïntegreerd met Intune.    
 
## <a name="certificate-requirements"></a>Certificaatvereisten 
 
Basiscertificaten zijn vereist voor het implementeren van certificaten via een SCEP- of PKCS-infrastructuur. Voor andere toepassingen en services in uw organisatie moeten mogelijk hoofdcertificaten worden geïmplementeerd op uw Microsoft Managed Desktop apparaten.    
 
Voordat u SCEP- of PKCS-certificaten implementeert voor Microsoft Managed Desktop, moet u vereisten verzamelen voor elke service die een gebruikers- of apparaatcertificaat in uw organisatie vereist. U kunt deze activiteit vergemakkelijken door een van de volgende planningssjablonen te gebruiken:  
 
- [PKCS-certificaatsjabloon](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [SCEP-certificaatsjabloon](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi connectiviteitsvereisten

Als u wilt toestaan dat een apparaat automatisch wordt geleverd met de vereiste Wi-Fi voor uw bedrijfsnetwerk, hebt u mogelijk een Wi-Fi configuratieprofiel nodig. U kunt de Microsoft Managed Desktop zo configureren dat deze profielen worden geïmplementeerd op uw apparaten. Als uw netwerkbeveiliging vereist dat apparaten deel uitmaken van het lokale domein, moet u mogelijk ook uw Wi-Fi-netwerkinfrastructuur evalueren om ervoor te zorgen dat deze compatibel is met Microsoft Managed Desktop-apparaten (Microsoft Managed Desktop-apparaten zijn alleen verbonden met Azure AD). 
 
Voordat u een configuratie Wi-Fi implementeren op Microsoft Managed Desktop apparaten, moet u de vereisten van uw organisatie voor elk netwerk Wi-Fi verzamelen. U kunt deze WiFi-profielsjabloon gebruiken om deze activiteit [gemakkelijker te maken.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Vereisten voor bekabelde connectiviteit en 802.1x-verificatie 
 
Als u 802.1x-verificatie gebruikt om toegang te beveiligen van apparaten tot uw lokale netwerk (LAN), moet u de vereiste configuratiegegevens naar uw Microsoft Managed Desktop-apparaten. Microsoft Managed Desktop apparaten met Windows 10, versie 1809 of hoger ondersteuning voor het implementeren van een 802.1x-configuratie via de WiredNetwork configuration service provider (CSP). Zie [WiredNetwork CSP-documentatie voor](/windows/client-management/mdm/wirednetwork-csp) meer informatie. 
 
Voordat u een bekabeld netwerkconfiguratieprofiel implementeert Microsoft Managed Desktop apparaten, verzamelt u de vereisten van uw organisatie voor uw bekabelde bedrijfsnetwerk. Ga hiervoor als volgt te werk: 
 
 
1. Meld u aan bij een apparaat dat uw bestaande 802.1x-profiel heeft geconfigureerd en is verbonden met het LAN-netwerk.  
2. Open een opdrachtprompt met beheerdersreferenties. 
3. Zoek de naam van de LAN-interface door **de interface van de netsh-interface weer te geven.** 
4. Exporteert het LAN-profiel XML door **netsh lan export profielmap= uit te voeren.  Interface="interface_name"**. 
5. Als u uw geëxporteerde profiel wilt testen op Microsoft Managed Desktop apparaat, kunt u **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME" uitvoeren.** 
 
 
## <a name="deploy-certificate-infrastructure"></a>Certificaatinfrastructuur implementeren  
 
Als u al een bestaande SCEP- of PKCS-infrastructuur met Intune hebt en deze benadering aan uw vereisten voldoet, kunt u deze ook gebruiken voor Microsoft Managed Desktop. Als er nog geen SCEP- of PKCS-infrastructuur bestaat, moet u er een voorbereiden.  
 
Zie Een certificaatprofiel [configureren voor uw apparaten in](/intune/certificates-configure)Microsoft Intune. 
 
 
 
## <a name="deploy-a-lan-profile"></a>Een LAN-profiel implementeren 
 
Nadat uw LAN-profiel is geëxporteerd, kunt u het beleid voorbereiden op Microsoft Managed Desktop door de volgende stappen uit te voeren:   
 
1. Maak een aangepast profiel in Microsoft Intune voor het LAN-profiel met behulp van de volgende instellingen (zie Aangepaste instellingen gebruiken voor Windows 10 [apparaten in Intune).](/intune/custom-settings-windows-10) Selecteer **in Aangepaste OMA-URI-Instellingen** toevoegen **en** voer de volgende waarden in: 
    - Naam: *Modern Workplace-Windows 10 LAN-profiel* 
    - Beschrijving: Voer een beschrijving in met een overzicht van de instelling en andere belangrijke details. 
    - OMA-URI (case sensitive): Enter *./Device/Vendor/MSFT/WiredNetwork/LanXML*
    - Gegevenstype: selecteer **Tekenreeks (XML-bestand)**. 
    - Aangepaste XML: Upload het geëxporteerde XML-bestand.
2. Een ondersteuningsaanvraag indienen Microsoft Managed Desktop IT-bewerkingen uitvoeren met behulp van de Microsoft Managed Desktop-beheerportal om het configuratieprofiel te bekijken en te implementeren in 'Moderne werkplekapparaten – test'. Microsoft Managed Desktop It Operations laat u weten wanneer de aanvraag is voltooid via de ondersteuningsaanvraag in de beheerportal.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Certificaten en wi-fi/VPN-profiel implementeren 
 
 
Als u certificaten en profielen wilt implementeren, volgt u de volgende stappen:

1. Maak een profiel voor elk van de hoofd- en tussenliggende certificaten (zie [Vertrouwde certificaatprofielen maken.](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles) Elk van deze profielen moet een beschrijving hebben met een vervaldatum in de DD/MM/YYYY-indeling. **Certificaatprofielen zonder vervaldatum worden niet geïmplementeerd.**
2. Maak een profiel voor elke SCEP- of PKCS-certificaten (zie Een [SCEP-certificaatprofiel](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) maken of Een [PKCS-certificaatprofiel](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)maken) Elk van deze profielen moet een beschrijving hebben met een vervaldatum in de DD/MM/YYYY-indeling. **Certificaatprofielen zonder vervaldatum worden niet geïmplementeerd.**
3. Maak een profiel voor elk bedrijfs wifi-netwerk (zie [Wi-Fi-instellingen voor](/intune/wi-fi-settings-windows)Windows 10 en latere apparaten).
4. Maak een profiel voor elke zakelijke VPN (zie Windows 10 en Windows Holographic device settings to add [VPN connections using Intune](/intune/vpn-settings-windows-10)).
5. Verzend een ondersteuningsaanvraag met de titel 'Implementatie van certificaten' Microsoft Managed Desktop 'Implementatie van wi-fi-profiel' bij Microsoft Managed Desktop IT-bewerkingen met behulp van de Microsoft Managed Desktop-beheerportal om het configuratieprofiel te bekijken en te implementeren in 'Moderne werkplekapparaten - test'. Microsoft Managed Desktop It Operations laat u weten wanneer de aanvraag is voltooid via de ondersteuningsaanvraag in de beheerportal. 
 
## <a name="steps-to-get-ready"></a>Stappen om u klaar te maken

1. Controleer [Vereisten voor Microsoft Managed Desktop.](prerequisites.md)
2. Gebruik [gereedheidsbeoordelingshulpmiddelen.](readiness-assessment-tool.md)
3. [Vereisten voor gast-accounts](guest-accounts.md)
4. [Netwerkconfiguratie voor Microsoft Managed Desktop](network.md)
5. [Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop](certs-wifi-lan.md) (dit artikel)
6. [Toegang voorbereiden tot on-premises bronnen voor Microsoft Managed Desktop](authentication.md)
7. [Apps in Microsoft Managed Desktop](apps.md)
8. [Toegewezen stations voorbereiden voor Microsoft Managed Desktop](mapped-drives.md)
9. [Afdrukbronnen voorbereiden voor Microsoft Managed Desktop](printing.md) 
