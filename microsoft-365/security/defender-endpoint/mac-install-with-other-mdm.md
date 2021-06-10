---
title: Implementatie met een ander MDM-systeem (Mobile Device Management) voor Microsoft Defender voor Eindpunt op Mac
description: Installeer Microsoft Defender voor Eindpunt op Mac op andere beheeroplossingen.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ca779fc4cc8c40adb25a0e95a9450f59954dc605
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933791"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-on-macos"></a>Implementatie met een ander MDM-systeem (Mobile Device Management) voor Microsoft Defender voor Eindpunt op macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a>Vereisten en systeemvereisten

Voordat u aan de slag gaat, bekijkt u de hoofdpagina van Microsoft Defender voor Eindpunt op [macOS](microsoft-defender-endpoint-mac.md) voor een beschrijving van vereisten en systeemvereisten voor de huidige softwareversie.


## <a name="approach"></a>Benadering

> [!CAUTION]

> Momenteel ondersteunt Microsoft officieel alleen Intune en JAMF voor de implementatie en het beheer van Microsoft Defender voor Eindpunt op macOS. Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de onderstaande informatie.

Als uw organisatie een MDM-oplossing (Mobile Device Management) gebruikt die niet officieel wordt ondersteund, betekent dit niet dat u Microsoft Defender voor Eindpunt niet kunt implementeren of uitvoeren op macOS.

Microsoft Defender voor Eindpunt voor macOS is niet afhankelijk van specifieke functies van leveranciers. Deze kan worden gebruikt met elke MDM-oplossing die de volgende functies ondersteunt:

- Een macOS .pkg implementeren op beheerde apparaten.
- MacOS-systeemconfiguratieprofielen implementeren op beheerde apparaten.
- Voer een willekeurig door de beheerder geconfigureerd hulpprogramma/script uit op beheerde apparaten.

De meeste moderne MDM-oplossingen bevatten deze functies, maar ze kunnen ze anders noemen.

U kunt Defender echter implementeren zonder de laatste vereiste uit de vorige lijst:

- U kunt de status niet op een gecentraliseerde manier verzamelen
- Als u Besluit Defender te verwijderen, moet u zich lokaal aanmelden bij het clientapparaat als beheerder

## <a name="deployment"></a>Implementatie

De meeste MDM-oplossingen gebruiken hetzelfde model voor het beheren van macOS-apparaten, met vergelijkbare terminologie. Gebruik [DE IMPLEMENTATIE OP BASIS VAN JAMF](mac-install-with-jamf.md) als sjabloon.

### <a name="package"></a>Pakket

Configureer de implementatie [van een vereist toepassingspakket,](mac-install-with-jamf.md)met het installatiepakket (wdav.pkg) gedownload van [Microsoft Defender-beveiligingscentrum.](mac-install-with-jamf.md)

Als u het pakket wilt implementeren in uw bedrijf, gebruikt u de instructies die zijn gekoppeld aan uw MDM-oplossing.

### <a name="license-settings"></a>Licentie-instellingen

Een [systeemconfiguratieprofiel instellen.](mac-install-with-jamf.md) 

Uw MDM-oplossing kan dit zoiets noemen als 'Aangepast Instellingen profiel', omdat Microsoft Defender voor Eindpunt op macOS geen deel uitmaakt van macOS.

Gebruik de lijst met eigenschappen, jamf/WindowsDefenderATPOnboarding.plist, die kan worden geëxtraheerd uit een onboarding-pakket dat is [gedownload van Microsoft Defender-beveiligingscentrum.](mac-install-with-jamf.md)
Uw systeem ondersteunt mogelijk een lijst met willekeurige eigenschappen in XML-indeling. U kunt het bestand jamf/WindowsDefenderATPOnboarding.plist zoals in dat geval uploaden.
U moet de lijst met eigenschappen mogelijk eerst converteren naar een andere indeling.

Meestal heeft uw aangepaste profiel een id, naam of domeinkenmerk. U moet precies 'com.microsoft.wdav.atp' voor deze waarde gebruiken.
MDM gebruikt het bestand om het instellingenbestand te implementeren naar **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** op een clientapparaat en Defender gebruikt dit bestand voor het laden van de onboarding-informatie.

### <a name="kernel-extension-policy"></a>Beleid voor kernelextensie

Een KEXT- of kernelextensiebeleid instellen. Gebruik teamaanduiding **UBF8T346G9** om kernelextensies van Microsoft toe te staan.

> [!CAUTION]
> Als uw omgeving uit M1-apparaten (Apple Silicon) bestaat, ontvangen deze machines geen configuratieprofielen met KEXT-beleid.
> Apple biedt geen ondersteuning voor KEXT op deze machines, de implementatie van een dergelijk profiel zou mislukken op M1-machines.

### <a name="system-extension-policy"></a>Systeemextensiebeleid

Een systeemextensiebeleid instellen. Gebruik teamaanduiding **UBF8T346G9** en keur de volgende bundelaanduidingen goed:

- com.microsoft.wdav.epsext
- com.microsoft.wdav.netext

### <a name="full-disk-access-policy"></a>Beleid voor volledige schijftoegang

Volledige schijftoegang verlenen aan de volgende onderdelen:

- Microsoft Defender voor Eindpunt
    - Id: `com.microsoft.wdav`
    - Id-type: bundel-id
    - Codevereiste: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

- Microsoft Defender voor endpoint-beveiligingsextensie
    - Id: `com.microsoft.wdav.epsext`
    - Id-type: bundel-id
    - Codevereiste: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

### <a name="network-extension-policy"></a>Beleid voor netwerkextensie

Als onderdeel van de mogelijkheden voor endpointdetectie en -antwoord controleert Microsoft Defender voor Eindpunt op macOS het socketverkeer en rapporteert deze informatie aan de Microsoft Defender-beveiligingscentrum portal. Met het volgende beleid kan de netwerkextensie deze functionaliteit uitvoeren.

- Filtertype: Invoegvoeginvoeging
- Id van de invoegbundel: `com.microsoft.wdav`
- Gegevensproviderbundel-id filteren: `com.microsoft.wdav.netext`
- Vereiste filtergegevensprovider: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
- Filterdozen: `true`

## <a name="check-installation-status"></a>Installatiestatus controleren

Voer [Microsoft Defender voor Eindpunt uit](mac-install-with-jamf.md) op een clientapparaat om de onboarding-status te controleren.
