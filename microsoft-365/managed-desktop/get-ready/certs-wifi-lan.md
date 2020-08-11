---
title: Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop
description: Certificaats/WiFi/LAN
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
ms.openlocfilehash: 7a0af5db4e18bc46436ace6f9fefefc18f0ccd68
ms.sourcegitcommit: 51f040a4edb8dd52521a5d7b0f7a975986a1af10
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2020
ms.locfileid: "46608273"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop  
 
Verificatie op basis van certificaten is een algemene vereiste voor klanten die gebruikmaken van Microsoft Managed Desktop. Het is mogelijk dat u certificaten nodig hebt voor toegang tot Wi-Fi of LAN, om verbinding te maken met VPN-oplossingen of voor toegang tot interne bronnen in uw organisatie.   
 
Aangezien beheerde bureaublad apparaten van Microsoft lid zijn van Azure Active Directory (Azure AD) en worden beheerd door Microsoft intune, moet u dergelijke certificaten implementeren met behulp van een Simple Certificate Enrollment Protocol (Simple Certificate Enrollment Protocol) of een PKCS-certificaat (Public Key Cryptography Standard) die is geïntegreerd met intune.    
 
## <a name="certificate-requirements"></a>Certificaatvereisten 
 
Basiscertificaten zijn vereist voor de implementatie van certificaten via een SCEP-of PKCS-infrastructuur. Voor andere toepassingen en services in uw organisatie gelden mogelijk basiscertificaten voor de implementatie van de beheerde bureaublad apparaten van Microsoft.    
 
Voordat u SCEP-of PKCS-certificaten implementeert op Microsoft Managed Desktop, moet u vereisten verzamelen voor elke service waarvoor een certificaat voor een gebruiker of apparaat in uw organisatie is vereist. U kunt dit eenvoudiger maken door een van de volgende plannings sjablonen te gebruiken:  
 
- [PKCS certificaatsjabloon](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [SCEP-certificaatsjabloon](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

>[!NOTE]
>Op dit moment worden alleen SCEP-certificaatprofielen ondersteund voor de implementatie van Wi-Fi-profielen voor de implementatie van Wi-Fi-profielen met een EAP-type. PKCS-certificaatprofielen worden niet ondersteund. Zie [Wi-Fi-instellingen voor Windows 10-apparaten toevoegen in intune](https://docs.microsoft.com/intune/wi-fi-settings-windows) voor naslaginformatie.

  
## <a name="wi-fi-connectivity-requirements"></a>Vereisten voor Wi-Fi-connectiviteit

Als u wilt dat een apparaat automatisch wordt geleverd met de vereiste Wi-Fi-configuratie voor uw Enterprise-netwerk, hebt u mogelijk een Wi-Fi-configuratieprofiel nodig. U kunt Microsoft Managed Desktop configureren om deze profielen op uw apparaten te implementeren. Als u het lokale domein nodig hebt voor uw netwerkbeveiliging, moet u mogelijk eerst uw Wi-Fi-netwerkinfrastructuur evalueren zodat u zeker weet dat het compatibel is met Microsoft Managed Desktop-apparaten (door Microsoft beheerde bureaublad apparaten zijn alleen Azure AD-joins). 
 
Voordat u een WiFi-configuratie implementeert voor Microsoft Managed Desktop-apparaten, moet u de vereisten van uw organisatie voor elk Wi-Fi-netwerk verzamelen. U kunt dit eenvoudiger maken door deze WiFi- [profielsjabloon](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)te gebruiken.
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Vereisten voor kabelverbindingen en 802.1 x-verificatie 
 
Als u 802.1 x-verificatie gebruikt om de toegang vanaf apparaten te beveiligen met een LAN, moet u de vereiste configuratiegegevens voor de Microsoft beheerde bureaublad apparaten opgeven. Microsoft-bureaublad apparaten met Windows 10, versie 1809 of hoger worden ondersteund voor de implementatie van een 802.1 x-configuratie via de provider van WiredNetwork Configuration service provider. Zie [WIREDNETWORK CSP](https://docs.microsoft.com/windows/client-management/mdm/wirednetwork-csp) -documentatie voor meer informatie. 
 
Voordat u een bekabeld netwerkconfiguratie profiel implementeert op Microsoft beheerde bureaublad apparaten, verzamelt u de vereisten van uw organisatie voor uw bekabeld bedrijfsnetwerk. Ga hiervoor als volgt te werk: 
 
 
1. Meld u aan bij een apparaat waarop uw bestaande 802.1 x-profiel is geconfigureerd en verbonden is met het LAN-netwerk.  
2. Open een opdrachtprompt met beheerdersreferenties. 
3. Zoek de interfacenaam van de LAN door de **interface interface voor netsh interface weergeven**uit te voeren. 
4. Exporteer de XML-profiel-XML door de **map Netsh Local exportmap-profielmap uit te voeren.  Interface = "interface_name"**. 
5. Als u uw geëxporteerde profiel op Microsoft Managed desktop device moet testen, voert u **Netsh LAN add profile filename = "PATH_AND_FILENAME.xml" interface = "INTERFACE_NAME"** uit. 
 
 
## <a name="deploy-certificate-infrastructure"></a>De certificaatinfrastructuur implementeren  
 
Als u al een bestaande SCEP of PKCS-infrastructuur met intune hebt en deze aan uw eisen voldoet, kunt u deze ook gebruiken voor Microsoft Managed Desktop. Als er nog geen SCEP-of PKCS-infrastructuur bestaat, moet u er een voorbereiden.  
 
Zie voor meer informatie [een certificaatprofiel configureren voor uw apparaten in Microsoft intune](https://docs.microsoft.com/intune/certificates-configure). 
 
 
 
## <a name="deploy-a-lan-profile"></a>Een LAN-profiel implementeren 
 
Nadat het LAN-profiel is geëxporteerd, kunt u het beleid voor het Microsoft-beheerpakket voorbereiden aan de hand van de volgende stappen:   
 
1. Maak een aangepast profiel in Microsoft intune voor het LAN-profiel met behulp van de volgende instellingen (Zie [aangepaste instellingen voor Windows 10-apparaten gebruiken in intune](https://docs.microsoft.com/intune/custom-settings-windows-10)). Selecteer in **aangepaste instellingen voor oma-URI**de optie **toevoegen**en voer de volgende waarden in: 
    - Naam: *modern Workplace-Windows 10 LAN-profiel* 
    - Beschrijving: Geef een beschrijving op voor een overzicht van de instelling en andere belangrijke informatie. 
    - OMA-URI (hoofdlettergevoelig): Enter *./device/Vendor/MSFT/WiredNetwork/LanXML*
    - Gegevenstype: Selecteer **reeks (XML-bestand)**. 
    - Aangepaste XML: upload het geëxporteerde XML-bestand.
2. Een ondersteuningsverzoek indienen bij Microsoft beheerde bureaublad activiteiten met behulp van de beheerde portal van Microsoft van Microsoft DOOR Microsoft beheerde bureaublad activiteiten wordt u gelaat wanneer de aanvraag is voltooid via het ondersteuningsverzoek in de beheerportal.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Certificaten en Wi-Fi/VPN-profiel implementeren 
 
 
Voer de volgende stappen uit om certificaten en profielen te implementeren:

1. Maak een profiel voor elk van de basis-en tussenliggende certificaten (Zie [vertrouwde certificaatprofielen maken](https://docs.microsoft.com/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles). Voor elk van deze profielen moet een beschrijving zijn opgenomen met een vervaldatum in de notatie DD-MM-JJJJ. **Certificaatprofielen zonder vervaldatum worden niet geïmplementeerd.**
2. Maak een profiel voor elke SCEP-of PKCS-certificaat (Zie [een SCEP-certificaatprofiel](https://docs.microsoft.com/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) maken of [een PKCS-certificaatprofiel maken](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) elk van deze profielen moet een beschrijving hebben van een vervaldatum in de notatie dd-mm-jjjj. **Certificaatprofielen zonder vervaldatum worden niet geïmplementeerd.**
3. Maak een profiel voor elk zakelijk WiFi-netwerk (Zie [Wi-Fi-instellingen voor Windows 10 en nieuwere apparaten](https://docs.microsoft.com/intune/wi-fi-settings-windows)).
4. Maak een profiel voor elke bedrijfs VPN (Zie [instellingen van Windows 10 en Windows Holographic-apparaat om VPN-verbindingen toe te voegen met intune](https://docs.microsoft.com/intune/vpn-settings-windows-10)).
5. U kunt een ondersteuningsaanvraag getiteld ' Certificate Deployment ' of ' Wi-Fi-installatie van profielen ' verzenden naar Microsoft Managed Desktop IT Operations via de Microsoft Managed Desktop-Portal DOOR Microsoft beheerde bureaublad activiteiten wordt u gelaat wanneer de aanvraag is voltooid via het ondersteuningsverzoek in de beheerportal. 
 
 
