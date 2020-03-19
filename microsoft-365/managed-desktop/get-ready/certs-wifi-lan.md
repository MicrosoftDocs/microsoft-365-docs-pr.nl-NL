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
ms.openlocfilehash: 0c3edda92e28b45b7f7b48c1d5002014f71116f6
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42808430"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop  
 
Verificatie op basis van certificaten is een veelvoorkomende vereiste voor klanten die Microsoft Managed Desktop gebruiken. Mogelijk hebt u certificaten nodig om toegang te krijgen tot Wi-Fi of LAN, om verbinding te maken met VPN-oplossingen of om toegang te krijgen tot interne bronnen in uw organisatie.   
 
Omdat Microsoft Managed Desktop-apparaten zijn verbonden met Azure Active Directory (Azure AD) en worden beheerd door Microsoft Intune, moet u dergelijke certificaten implementeren met behulp van een SCEP (Simple Certificate Enrollment Protocol) of Public Key Cryptography Standard (PKCS) certificaatinfrastructuur die is geïntegreerd met Intune.    
 
## <a name="certificate-requirements"></a>Certificaatvereisten 
 
Rootcertificaten zijn vereist om certificaten te implementeren via een SCEP- of PKCS-infrastructuur. Voor andere toepassingen en services in uw organisatie moeten mogelijk basiscertificaten worden geïmplementeerd op uw Microsoft Managed Desktop-apparaten.    
 
Voordat u SCEP- of PKCS-certificaten implementeert op Microsoft Managed Desktop, moet u vereisten verzamelen voor elke service waarvoor een gebruikers- of apparaatcertificaat in uw organisatie vereist is. Om dit gemakkelijker te maken, u een van de volgende planningssjablonen gebruiken:  
 
- [PKCS-certificaatsjabloon](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [Sjabloon SCEP-certificaat](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

>[!NOTE]
>Momenteel worden alleen SCEP-certificaatprofielen ondersteund voor wi-fi-profielimplementatie naar Microsoft Managed Desktop wanneer u een EAP-type gebruikt. PKCS-certificaatprofielen worden niet ondersteund. Zie [Wi-Fi-instellingen voor Windows 10-apparaten toevoegen in Intune](https://docs.microsoft.com/intune/wi-fi-settings-windows) ter referentie.

  
## <a name="wi-fi-connectivity-requirements"></a>Vereisten voor wi-fi-connectiviteit

Om een apparaat automatisch te voorzien van de vereiste Wi-Fi-configuratie voor uw bedrijfsnetwerk, hebt u mogelijk een Wi-Fi-configuratieprofiel nodig. U Microsoft Managed Desktop configureren om deze profielen op uw apparaten te implementeren. Als voor uw netwerkbeveiliging vereist dat apparaten deel uitmaken van het lokale domein, moet u mogelijk ook uw Wi-Fi-netwerkinfrastructuur evalueren om te controleren of deze compatibel is met Microsoft Managed Desktop-apparaten (Microsoft Managed Desktop-apparaten zijn azure AD-aangesloten alleen). 
 
Voordat u een Wi-Fi-configuratie implementeert op Microsoft Managed Desktop-apparaten, moet u de vereisten van uw organisatie voor elk Wi-Fi-netwerk verzamelen. Om dit gemakkelijker te maken, u deze [WiFi-profielsjabloon](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)gebruiken.
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Vereisten voor bedrade connectiviteit en 802.1x-verificatie 
 
Als u 802.1x-verificatie gebruikt om de toegang van apparaten tot uw lan (local area network) te beveiligen, moet u de vereiste configuratiegegevens naar uw Microsoft Managed Desktop-apparaten pushen. Microsoft Managed Desktop-apparaten met Windows 10, versie 1809 of hoger ondersteunen de implementatie van een 802.1x-configuratie via de WiredNetwork configuration Service Provider (CSP). Zie De documentatie van [WiredNetwork CSP](https://docs.microsoft.com/windows/client-management/mdm/wirednetwork-csp) voor meer informatie. 
 
Voordat u een bekabeld netwerkconfiguratieprofiel implementeert op Microsoft Managed Desktop-apparaten, verzamelt u de vereisten van uw organisatie voor uw bedrade bedrijfsnetwerk. Ga hiervoor als volgt te werk: 
 
 
1. Meld u aan bij een apparaat waarop uw bestaande profiel van 802.1x is geconfigureerd en is verbonden met het LAN-netwerk.  
2. Open een opdrachtprompt met beheerdersreferenties. 
3. Zoek de LAN-interfacenaam door **de interface van de Netsh-interface weer te geven.** 
4. Exporteer de XML-LAN-profiel profiel door **de map netsh lan-exportprofiel uit te voeren=.  Interface="interface_name".** 
5. Als u uw geëxporteerde profiel moet testen op het Microsoft Managed Desktop-apparaat, voert u **netsh lan add profile filename="PATH_AND_FILENAME.xml"-interface="INTERFACE_NAME"** uit. 
 
 
## <a name="deploy-certificate-infrastructure"></a>Certificaatinfrastructuur implementeren  
 
Als u al een bestaande SCEP- of PKCS-infrastructuur hebt met Intune en dit voldoet aan uw vereisten, u deze ook gebruiken voor Microsoft Managed Desktop. Als er nog geen SCEP- of PKCS-infrastructuur bestaat, moet u er een voorbereiden.  
 
Zie [Een certificaatprofiel configureren voor uw apparaten in Microsoft Intune](https://docs.microsoft.com/intune/certificates-configure)voor meer informatie. 
 
 
 
## <a name="deploy-a-lan-profile"></a>Een LAN-profiel implementeren 
 
Zodra uw LAN-profiel is geëxporteerd, u het beleid voor Microsoft Managed Desktop voorbereiden door de volgende stappen te volgen:   
 
1. Maak een aangepast profiel in Microsoft Intune voor het LAN-profiel met behulp van de volgende instellingen (zie [Aangepaste instellingen voor Windows 10-apparaten gebruiken in Intune).](https://docs.microsoft.com/intune/custom-settings-windows-10) Selecteer **Toevoegen**in **aangepaste OMA-URI-instellingen**en voer vervolgens de volgende waarden in: 
    - Naam: *Modern Workplace-Windows 10 LAN-profiel* 
    - Beschrijving: Voer een beschrijving in die een overzicht geeft van de instelling en alle andere belangrijke details. 
    - OMA-URI (hoofdlettergevoelig): Enter *./Device/Vendor/MSFT/WiredNetwork/LanXML*
    - Gegevenstype: selecteer **Tekenreeks (XML-bestand).** 
    - Aangepaste XML: upload het geëxporteerde XML-bestand.
2. Dien een ondersteuningsverzoek in bij Microsoft Managed Desktop IT Operations via de Microsoft Managed Desktop Admin-portal om het configuratieprofiel te controleren en te implementeren in 'Moderne werkplekapparaten – Testen'. Microsoft Managed Desktop IT Operations laat u weten wanneer de aanvraag is voltooid via de ondersteuningsaanvraag in de beheerportal.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Certificaten en Wi-Fi/VPN-profiel implementeren 
 
 
Voer de volgende stappen uit om certificaten en profielen te implementeren:

1. Maak een profiel voor elk van de basis- en intermediatecertificaten (zie [Vertrouwde certificaatprofielen maken](https://docs.microsoft.com/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles). Elk van deze profielen moet een beschrijving hebben die een vervaldatum in dd/MM/YYYY-indeling bevat. **Certificaatprofielen zonder vervaldatum worden niet geïmplementeerd.**
2. Maak een profiel aan voor elke SCEP- of PKCS-certificaten (zie [Een SCEP-certificaatprofiel](https://docs.microsoft.com/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) maken of [Een PKCS-certificaatprofiel](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)maken) Elk van deze profielen moet een beschrijving hebben die een vervaldatum in dd/MM/YYYY-indeling bevat. **Certificaatprofielen zonder vervaldatum worden niet geïmplementeerd.**
3. Maak een profiel voor elk zakelijk WiFi-netwerk (zie [Wi-Fi-instellingen voor Windows 10- en latere apparaten).](https://docs.microsoft.com/intune/wi-fi-settings-windows)
4. Maak een profiel voor elke zakelijke VPN (zie [Windows 10- en Windows Holografische apparaatinstellingen om VPN-verbindingen toe te voegen met Intune).](https://docs.microsoft.com/intune/vpn-settings-windows-10)
5. Stuur een ondersteuningsaanvraag met de titel 'Implementatie van certificaten' of 'Wi-Fi-profielimplementatie' in bij Microsoft Managed Desktop IT Operations met behulp van de Microsoft Managed Desktop Admin-portal om het configuratieprofiel te controleren en te implementeren op 'Moderne werkplekapparaten – Test' ". Microsoft Managed Desktop IT Operations laat u weten wanneer de aanvraag is voltooid via de ondersteuningsaanvraag in de beheerportal. 
 
 
