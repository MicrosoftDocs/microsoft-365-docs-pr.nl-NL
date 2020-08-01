---
title: Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop
description: certs/wifi/lan
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
ms.openlocfilehash: c7c57861986d275165484ae726140720a75da88e
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530029"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop  
 
Verificatie op basis van certificaten is een veel voorkomende vereiste voor klanten die Microsoft Managed Desktop gebruiken. Mogelijk hebt u certificaten nodig om toegang te krijgen tot Wi-Fi of LAN, om verbinding te maken met VPN-oplossingen of om toegang te krijgen tot interne bronnen in uw organisatie.   
 
Omdat Microsoft Managed Desktop-apparaten zijn gekoppeld aan Azure Active Directory (Azure AD) en worden beheerd door Microsoft Intune, moet u dergelijke certificaten implementeren met behulp van een SCEP-certificaat (Simple Certificate Enrollment Protocol) of DE PKCS-certificaatinfrastructuur (Public Key Cryptography Standard) die is geïntegreerd met Intune.    
 
## <a name="certificate-requirements"></a>Certificaatvereisten 
 
Rootcertificaten zijn vereist om certificaten te implementeren via een SCEP- of PKCS-infrastructuur. Voor andere toepassingen en services in uw organisatie moeten mogelijk rootcertificaten worden geïmplementeerd op uw Microsoft Managed Desktop-apparaten.    
 
Voordat u SCEP- of PKCS-certificaten implementeert op Microsoft Managed Desktop, moet u vereisten verzamelen voor elke service waarvoor een gebruikers- of apparaatcertificaat in uw organisatie vereist is. Om dit gemakkelijker te maken, u een van de volgende planningssjablonen gebruiken:  
 
- [PKCS-certificaatsjabloon](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [SCEP-certificaatsjabloon](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

>[!NOTE]
>Momenteel worden alleen SCEP-certificaatprofielen ondersteund voor de implementatie van wi-fi-profielen naar Microsoft Managed Desktop wanneer u een EAP-type gebruikt. PKCS-certificaatprofielen worden niet ondersteund. Zie [Wi-Fi-instellingen toevoegen voor Windows 10-apparaten in Intune](https://docs.microsoft.com/intune/wi-fi-settings-windows) ter referentie.

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi-connectiviteitsvereisten

Als u wilt dat een apparaat automatisch wordt voorzien van de vereiste Wi-Fi-configuratie voor uw bedrijfsnetwerk, hebt u mogelijk een Wi-Fi-configuratieprofiel nodig. U Microsoft Managed Desktop configureren om deze profielen op uw apparaten te implementeren. Als voor uw netwerkbeveiliging apparaten deel moeten uitmaken van het lokale domein, moet u mogelijk ook uw Wi-Fi-netwerkinfrastructuur evalueren om te controleren of deze compatibel is met Microsoft Managed Desktop-apparaten (Microsoft Managed Desktop-apparaten zijn alleen azure AD-aangesloten). 
 
Voordat u een Wi-Fi-configuratie implementeert op Microsoft Managed Desktop-apparaten, moet u de vereisten van uw organisatie voor elk Wi-Fi-netwerk verzamelen. Om dit gemakkelijker te maken, u deze [WiFi-profielsjabloon](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)gebruiken.
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Vereiste bedrade connectiviteit en 802.1x-verificatie 
 
Als u 802.1x-verificatie gebruikt om de toegang van apparaten tot uw LAN in de omgevingsnetwerk (LAN) te beveiligen, moet u de vereiste configuratiegegevens naar uw Microsoft Managed Desktop-apparaten pushen. Microsoft Managed Desktop-apparaten met Windows 10, versie 1809 of hoger ondersteunen het implementeren van een 802.1x-configuratie via de WiredNetwork-configuratieserviceprovider (CSP). Zie [WiredNetwork CSP-documentatie](https://docs.microsoft.com/windows/client-management/mdm/wirednetwork-csp) voor meer informatie. 
 
Voordat u een bekabeld netwerkconfiguratieprofiel implementeert op Microsoft Managed Desktop-apparaten, verzamelt u de vereisten van uw organisatie voor uw bekabelde bedrijfsnetwerk. Ga hiervoor als volgt te werk: 
 
 
1. Meld u aan bij een apparaat waarop uw bestaande 802.1x-profiel is geconfigureerd en is verbonden met het LAN-netwerk.  
2. Open een opdrachtprompt met beheerdersreferenties. 
3. Zoek de naam van de LAN-interface door **de interface voor de weergeven**van netsh uit te voeren. 
4. Exporteer de XML van het LAN-profiel door **de map netsh lan-exportprofiel uit te voeren=.  Interface="interface_name"**. 
5. Als u uw geëxporteerde profiel moet testen op microsoft Managed Desktop-apparaat, voert u **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME"** uit. 
 
 
## <a name="deploy-certificate-infrastructure"></a>Certificaatinfrastructuur implementeren  
 
Als u al een bestaande SCEP- of PKCS-infrastructuur hebt met Intune en deze voldoet aan uw vereisten, u deze ook gebruiken voor Microsoft Managed Desktop. Als er nog geen SCEP- of PKCS-infrastructuur bestaat, moet u er een voorbereiden.  
 
Zie [Een certificaatprofiel configureren voor uw apparaten in Microsoft Intune voor](https://docs.microsoft.com/intune/certificates-configure)meer informatie. 
 
 
 
## <a name="deploy-a-lan-profile"></a>Een LAN-profiel implementeren 
 
Zodra uw LAN-profiel is geëxporteerd, u het beleid voor Microsoft Managed Desktop voorbereiden door de volgende stappen uit te voeren:   
 
1. Maak een aangepast profiel in Microsoft Intune voor het LAN-profiel met behulp van de volgende instellingen (zie [Aangepaste instellingen gebruiken voor Windows 10-apparaten in Intune](https://docs.microsoft.com/intune/custom-settings-windows-10)). Selecteer **toevoegen**in **aangepaste OMA-URI-instellingen**en voer de volgende waarden in: 
    - Naam: *Modern Workplace-Windows 10 LAN-profiel* 
    - Beschrijving: Voer een beschrijving in die een overzicht geeft van de instelling en andere belangrijke details. 
    - OMA-URI (gevalsgevoelig): Enter *./Device/Vendor/MSFT/WiredNetwork/LanXML*
    - Gegevenstype: selecteer **Tekenreeks (XML-bestand)**. 
    - Aangepaste XML: upload het geëxporteerde XML-bestand.
2. Dien een ondersteuningsverzoek in bij Microsoft Managed Desktop IT Operations met behulp van de Microsoft Managed Desktop Admin-portal om het configuratieprofiel te controleren en te implementeren in 'Modern Workplace Devices – Test'. Microsoft Managed Desktop IT Operations laat u weten wanneer het verzoek is voltooid via het ondersteuningsverzoek in de portal Beheerder.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Certificaten en Wi-Fi/VPN-profiel implementeren 
 
 
Voer de volgende stappen uit om certificaten en profielen te implementeren:

1. Maak een profiel aan voor elk van de Root- en Intermediate-certificaten (zie [Vertrouwde certificaatprofielen maken](https://docs.microsoft.com/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles). Elk van deze profielen moet een beschrijving hebben die een vervaldatum in de DD/MM/YYYY-indeling bevat. **Certificaatprofielen zonder vervaldatum worden niet geïmplementeerd.**
2. Een profiel maken voor elke SCEP- of PKCS-certificaten (zie [Een SCEP-certificaatprofiel maken](https://docs.microsoft.com/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) of [een PKCS-certificaatprofiel maken)](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)Elk van deze profielen moet een beschrijving bevatten met een vervaldatum in de DD/MM/YYYYY-indeling. **Certificaatprofielen zonder vervaldatum worden niet geïmplementeerd.**
3. Maak een profiel aan voor elk zakelijk WiFi-netwerk (zie [Wi-Fi-instellingen voor Windows 10 en hoger).](https://docs.microsoft.com/intune/wi-fi-settings-windows)
4. Maak een profiel aan voor elke zakelijke VPN (zie [Windows 10 en Windows Holographic device settings om VPN-verbindingen toe te voegen met Intune](https://docs.microsoft.com/intune/vpn-settings-windows-10)).
5. Dien een ondersteuningsverzoek met de titel 'Certificaatimplementatie' of 'Wi-Fi-profielimplementatie' in bij Microsoft Managed Desktop IT Operations met behulp van de Microsoft Managed Desktop Admin-portal om het configuratieprofiel te controleren en te implementeren voor 'Moderne werkplekapparaten – Test'. Microsoft Managed Desktop IT Operations laat u weten wanneer het verzoek is voltooid via het ondersteuningsverzoek in de portal Beheerder. 
 
 
