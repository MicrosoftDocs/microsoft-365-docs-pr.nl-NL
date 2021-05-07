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
ms.openlocfilehash: e7e50ea399cd694f512e0538de3f7e67c63ee0e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161961"
---
# <a name="technical-reference-details-about-encryption"></a>Technische naslaginformatie over versleuteling

Raadpleeg dit artikel voor meer informatie over certificaten, technologieën en TLS-coderingssuites die worden gebruikt voor [versleuteling in Office 365.](encryption.md) In dit artikel vindt u ook informatie over geplande afzettingen.
  
- Als u op zoek bent naar overzichtsgegevens, zie [Versleuteling in Office 365.](encryption.md)
- Zie Versleuteling instellen in Office 365 Enterprise als u op zoek [bent naar installatiegegevens.](set-up-encryption.md)
- Zie [Cipher Suites in TLS/SSL (Schannel SSP)](/windows/desktop/SecAuthN/cipher-suites-in-schannel)voor informatie over cipher suites die worden ondersteund door specifieke versies van Windows.

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 certificaateigenschap en -beheer

U hoeft geen certificaten te kopen of te onderhouden voor Office 365. In plaats Office 365 eigen certificaten gebruikt.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Huidige versleutelingsstandaarden en geplande afzettingen

Als u de beste versleuteling wilt bieden, Office 365 regelmatig ondersteunde versleutelingsstandaarden. Soms worden oude standaarden afgeschaft als ze verouderd en minder veilig worden. In dit artikel worden momenteel ondersteunde cijfersuites en andere standaarden en details over geplande afzettingen beschreven.

## <a name="fips-compliance-for-office-365"></a>FIPS-naleving voor Office 365

Alle cipher suites die worden ondersteund door Office 365 algoritmen gebruiken die acceptabel zijn onder FIPS 140-2. Office 365 neemt FIPS-validaties over van Windows (via Schannel). Zie [Cipher Suites in TLS/SSL (Schannel SSP) voor](/windows/desktop/SecAuthN/cipher-suites-in-schannel)meer informatie over Schannel.
  
## <a name="versions-of-tls-supported-by-office-365"></a>Versies van TLS die worden ondersteund door Office 365

TLS en SSL die vóór TLS zijn gebruikt, zijn cryptografische protocollen die communicatie via een netwerk beveiligen met behulp van beveiligingscertificaten om een verbinding tussen computers te versleutelen. Office 365 ondersteunt TLS versie 1.2 (TLS 1.2).

TLS versie 1.3 (TLS 1.3) wordt momenteel niet ondersteund.
  
## <a name="support-for-tls-10-and-11-deprecation"></a>Ondersteuning voor de intrekking van TLS 1.0 en 1.1

Office 365 ondersteuning van TLS 1.0 en 1.1 is gestopt op 31 oktober 2018. We hebben het uitschakelen van TLS 1.0 en 1.1 voltooid in GCC High- en DoD-omgevingen. We zijn begonnen met het uitschakelen van TLS 1.0 en 1.1 voor Worldwide- en GCC-omgevingen vanaf 15 oktober 2020 en gaan de komende weken en maanden verder met de uitrol.

Als u een veilige verbinding wilt Office 365 en Microsoft 365 services, gebruiken alle combinaties van clientservers en browserservers TLS 1.2 en moderne coderingssuites. Mogelijk moet u bepaalde combinaties van client-server en browserserver bijwerken. Zie Voorbereiden op het verplichte gebruik van [TLS 1.2 in](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)Office 365.
  
## <a name="deprecating-support-for-3des"></a>Ondersteuning voor 3DES afgeschaft

Sinds 31 oktober 2018 ondersteunt Office 365 geen gebruik meer van 3DES-coderingssuites voor communicatie met Office 365. Meer specifiek ondersteunt Office 365 niet langer de TLS_RSA_WITH_3DES_EDE_CBC_SHA codeersuite. Sinds 28 februari 2019 is deze cijfersuite uitgeschakeld in Office 365. Clients en servers die communiceren met Office 365 moeten een of meer van de ondersteunde cijfers ondersteunen. Zie [TLS-cijfersuites](#tls-cipher-suites-supported-by-office-365)die worden ondersteund door Office 365 voor een lijst met ondersteunde cijfers.
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Ondersteuning voor SHA-1-certificaten in Office 365

Sinds juni 2016 Office 365 geen SHA-1-certificaat meer voor uitgaande of binnenkomende verbindingen. Gebruik SHA-2 (Secure Hash Algorithm 2) of een sterker hashing-algoritme in de certificaatketen.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>TLS-coderingssuites die worden ondersteund door Office 365

TLS gebruikt *coderingssuites*, verzamelingen versleutelingsalgoritmen, om veilige verbindingen tot stand te brengen. Office 365 ondersteunt de cijfersuites die in de volgende tabel worden vermeld. De tabel bevat de cijfersuites in volgorde van sterkte, met als eerste de sterkste cijfersuite.

Office 365 reageert op een verbindingsaanvraag door eerst verbinding te maken met de veiligste codeersuite. Als de verbinding niet werkt, Office 365 de op een na veiligste coderingssuite in de lijst, en ga zo maar door. De service blijft in de lijst staan totdat de verbinding wordt geaccepteerd. Wanneer u een verbinding Office 365, kiest de ontvangende service of TLS wordt gebruikt en welke codeersuite moet worden gebruikt.

> [!IMPORTANT]
> Let op: TLS-versies worden afgeschaft en dat afgeschafte  versies niet mogen worden gebruikt wanneer nieuwere versies beschikbaar zijn. TLS 1.3 wordt momenteel niet ondersteund. Als voor uw oudere services geen TLS 1.0 of 1.1 is vereist, moet u deze uitschakelen.

| Cipher-suite | Sleuteluitwisselingsalgoritme/sterkte | Geheimhouding doorsturen | Cijfer/sterkte | Verificatiealgoritme |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|Ja <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|Ja <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|Ja <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|Ja <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|Ja <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|Ja <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |Nee <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |Nee <br/> |AES/256 <br/>|RSA/112 <br/> |

Deze coderingssuites ondersteunden TLS 1.0- en 1.1-protocollen tot de afzettingsdatum. Voor GCC High- en DoD-omgevingen was die afzettingsdatum 15 januari 2020 en voor Worldwide en GCC-omgevingen die datum 15 oktober 2020 was.

| Protocollen | Naam van cipher-suite | Sleuteluitwisselingsalgoritme/Sterkte | Ondersteuning voor doorsturen van geheimhouding | Verificatiealgoritme/Sterkte | Cijfer/sterkte |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |Ja  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |Ja  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |Nee  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |Nee  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |Nee   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |Nee   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-articles"></a>Verwante artikelen

[TLS Cipher Suites in Windows 10 v1903](/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Versleuteling in Office 365](encryption.md)
  
[Versleuteling instellen in Office 365 Enterprise](set-up-encryption.md)
  
[Schannel-implementatie van TLS 1.0 in Windows beveiligingsstatusupdate: 24 november 2015](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL Cryptographic Enhancements (Windows IT Center)](/previous-versions/windows/it-pro/windows-vista/cc766285(v=ws.10))
  
[Voorbereiden op TLS 1.2 in Office 365 en Office 365 GCC](/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)