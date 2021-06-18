---
title: Technische naslaginformatie over versleuteling
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
- Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Meer informatie over de verschillende certificaten, technologieën en TLS-coderingssuites (Transport Layer Security) die worden gebruikt voor versleuteling in Office 365 en Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2b2257338ab214ccdaa08f1aa8f322aad98d7c8b
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007547"
---
# <a name="technical-reference-details-about-encryption"></a>Technische naslaginformatie over versleuteling

Raadpleeg dit artikel voor meer informatie over certificaten, technologieën en TLS-coderingssuites die worden gebruikt voor [versleuteling in Office 365.](encryption.md) In dit artikel vindt u ook informatie over geplande afzettingen.
  
- Zie Versleuteling in Office [365](encryption.md)als u overzichtsgegevens zoekt.
- Zie Versleuteling instellen in [Office 365 Enterprise](set-up-encryption.md)als u op zoek bent naar installatiegegevens.
- Zie [Cipher Suites in TLS/SSL (Schannel SSP) voor](/windows/desktop/SecAuthN/cipher-suites-in-schannel)informatie over cipher suites die worden ondersteund door specifieke versies van Windows.

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Eigendom en beheer van Microsoft Office 365-certificaten

U hoeft geen certificaten voor Office 365 te kopen of te onderhouden. In plaats daarvan gebruikt Office 365 eigen certificaten.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Huidige versleutelingsstandaarden en geplande afzettingen

Office 365 controleert regelmatig ondersteunde versleutelingsstandaarden om de beste versleuteling te bieden. Soms worden oude standaarden afgeschaft als ze verouderd en minder veilig worden. In dit artikel worden momenteel ondersteunde cijfersuites en andere standaarden en details over geplande afzettingen beschreven.

## <a name="fips-compliance-for-office-365"></a>FIPS-naleving voor Office 365

Alle cipher-suites die worden ondersteund door Office 365, gebruiken algoritmen die acceptabel zijn onder FIPS 140-2. Office 365 neemt FIPS-validaties over van Windows (via Schannel). Zie [Cipher Suites in TLS/SSL (Schannel SSP) voor](/windows/desktop/SecAuthN/cipher-suites-in-schannel)meer informatie over Schannel.
  
## <a name="versions-of-tls-supported-by-office-365"></a>Versies van TLS die worden ondersteund door Office 365

TLS en SSL die vóór TLS zijn gebruikt, zijn cryptografische protocollen die communicatie via een netwerk beveiligen met behulp van beveiligingscertificaten om een verbinding tussen computers te versleutelen. Office 365 ondersteunt TLS-versie 1.2 (TLS 1.2).

TLS versie 1.3 (TLS 1.3) wordt momenteel niet ondersteund.

> [!IMPORTANT]
> Let op: TLS-versies worden afgeschaft en dat afgeschafte  versies niet mogen worden gebruikt wanneer nieuwere versies beschikbaar zijn. Als voor uw oudere services geen TLS 1.0 of 1.1 is vereist, moet u deze uitschakelen.
  
## <a name="support-for-tls-10-and-11-deprecation"></a>Ondersteuning voor de intrekking van TLS 1.0 en 1.1

Office 365 is op 31 oktober 2018 gestopt met het ondersteunen van TLS 1.0 en 1.1. We hebben het uitschakelen van TLS 1.0 en 1.1 voltooid in GCC High- en DoD-omgevingen. We zijn begonnen met het uitschakelen van TLS 1.0 en 1.1 voor Worldwide- en GCC-omgevingen vanaf 15 oktober 2020 en gaan de komende weken en maanden verder met de uitrol.

Voor een veilige verbinding met Office 365- en Microsoft 365-services gebruiken alle combinaties van clientservers en browserservers TLS 1.2 en moderne cipher-suites. Mogelijk moet u bepaalde combinaties van client-server en browserserver bijwerken. Zie Voorbereiden op het verplichte gebruik van [TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)voor meer informatie over de gevolgen van deze wijziging.
  
## <a name="deprecating-support-for-3des"></a>Ondersteuning voor 3DES afgeschaft

Sinds 31 oktober 2018 biedt Office 365 geen ondersteuning meer voor het gebruik van 3DES-coderingssuites voor communicatie met Office 365. Meer specifiek biedt Office 365 geen ondersteuning meer voor de TLS_RSA_WITH_3DES_EDE_CBC_SHA cipher suite. Sinds 28 februari 2019 is deze coderingssuite uitgeschakeld in Office 365. Clients en servers die communiceren met Office 365 moeten een of meer van de ondersteunde cijfers ondersteunen. Zie TLS-coderingssuites die worden ondersteund [door Office 365](#tls-cipher-suites-supported-by-office-365)voor een lijst met ondersteunde cijfers.
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Sha-1-certificaatondersteuning in Office 365 afgeschaft

Sinds juni 2016 accepteert Office 365 geen SHA-1-certificaat meer voor uitgaande of binnenkomende verbindingen. Gebruik SHA-2 (Secure Hash Algorithm 2) of een sterker hashing-algoritme in de certificaatketen.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>TLS-coderingssuites die worden ondersteund door Office 365

TLS gebruikt *coderingssuites*, verzamelingen versleutelingsalgoritmen, om veilige verbindingen tot stand te brengen. Office 365 ondersteunt de cijfersuites die in de volgende tabel worden vermeld. De tabel bevat de cijfersuites in volgorde van sterkte, met als eerste de sterkste cijfersuite.

Office 365 reageert op een verbindingsaanvraag door eerst verbinding te maken met de veiligste coderingssuite. Als de verbinding niet werkt, probeert Office 365 de op een na veiligste coderingssuite in de lijst, en ga zo maar door. De service blijft in de lijst staan totdat de verbinding wordt geaccepteerd. Wanneer Office 365 een verbinding aanvraagt, kiest de ontvangende service ook of TLS wordt gebruikt en welke coderingssuite moet worden gebruikt.

| Naam van cipher-suite | Sleuteluitwisselingsalgoritme/sterkte | Geheimhouding doorsturen | Cijfer/sterkte | Verificatiealgoritme/sterkte |
|:-----|:-----|:-----|:-----|:-----|
| TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384  <br/> | ECDH/192  <br/> | Ja  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256  <br/> | ECDH/128  <br/> | Ja  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384  <br/> | ECDH/192  <br/> | Ja  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256  <br/> | ECDH/128  <br/> | Ja  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA     <br/> | ECDH/192  <br/> | Ja  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA     <br/> | ECDH/128  <br/> | Ja  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_RSA_WITH_AES_256_GCM_SHA384        <br/> | RSA/112   <br/> | Nee   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_RSA_WITH_AES_128_GCM_SHA256        <br/> | RSA/112   <br/> | Nee   <br/> | AES/256  <br/> | RSA/112  <br/> |

De volgende coderingssuites ondersteunden TLS 1.0- en 1.1-protocollen tot de afzettingsdatum. Voor GCC High- en DoD-omgevingen was de afzettingsdatum 15 januari 2020. Voor Wereldwijde en GCC-omgevingen was die datum 15 oktober 2020.

| Protocollen | Naam van cipher-suite | Sleuteluitwisselingsalgoritme/sterkte | Geheimhouding doorsturen | Cijfer/sterkte | Verificatiealgoritme/sterkte | 
|:-----|:-----|:-----|:-----|:-----|:-----|
| TLS 1.0, 1.1, 1.2  <br/> | TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> | ECDH/192  <br/> | Ja  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> | ECDH/128  <br/> | Ja  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_256_CBC_SHA        <br/> | RSA/112   <br/> | Nee   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_128_CBC_SHA        <br/> | RSA/112   <br/> | Nee   <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> | RSA/112   <br/> | Nee   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> | RSA/112   <br/> | Nee   <br/> | AES/256  <br/> | RSA/112  <br/> |

Bepaalde Office 365-producten (waaronder Microsoft Teams) gebruiken [Azure Front Door](/azure/frontdoor/front-door-overview) om TLS-verbindingen te beëindigen en netwerkverkeer efficiënt te routeerden. Ten minste één van de coderingssuites die door [Azure Front Door via TLS 1.2](/azure/frontdoor/front-door-faq#what-are-the-current-cipher-suites-supported-by-azure-front-door-) worden ondersteund, moet zijn ingeschakeld om verbinding te maken met deze producten. Voor Windows 10 en hoger wordt u aangeraden een of beide ECDHE-coderingssuites in te stellen voor een betere beveiliging. Windows 7, 8 en 8.1 zijn niet compatibel met de ECDHE-coderingssuites van Azure Front Door en de DHE-cipher-suites zijn beschikbaar voor compatibiliteit met deze besturingssystemen.

## <a name="related-articles"></a>Verwante artikelen

[TLS Cipher Suites in Windows 10 v1903](/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Versleuteling in Office 365](encryption.md)
  
[Versleuteling instellen in Office 365 Enterprise](set-up-encryption.md)
  
[Schannel-implementatie van TLS 1.0 in windows-beveiligingsstatusupdate: 24 november 2015](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL Cryptographic Enhancements (Windows IT Center)](/previous-versions/windows/it-pro/windows-vista/cc766285(v=ws.10))
  
[Voorbereiden op TLS 1.2 in Office 365 en Office 365 GCC](/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)

[Wat worden de huidige cijfersuites ondersteund door Azure Front Door?](/azure/frontdoor/front-door-faq#what-are-the-current-cipher-suites-supported-by-azure-front-door-)
