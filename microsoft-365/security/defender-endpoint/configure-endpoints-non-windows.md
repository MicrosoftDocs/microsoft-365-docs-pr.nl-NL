---
title: Onboard non-Windows devices to the Microsoft Defender for Endpoint service
description: Configureer niet-Windows-apparaten, zodat ze sensorgegevens kunnen verzenden naar de MICROSOFT Defender ATP-service.
keywords: onboard non-Windows devices, macos, linux, device management, configure Windows ATP devices, configure Microsoft Defender for Endpoint devices
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c292c57c179a832728b03a7fc94fb7085d3ea0ec
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166075"
---
# <a name="onboard-non-windows-devices"></a>Onboard niet-Windows-apparaten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Platforms**
- macOS
- Linux

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

Defender voor Eindpunt biedt een gecentraliseerde beveiligingsbewerkingservaring voor Windows en niet-Windows-platforms. U kunt waarschuwingen van verschillende ondersteunde besturingssystemen (OS) zien in het Microsoft Defender-beveiligingscentrum en het netwerk van uw organisatie beter beveiligen. 

U moet de exacte Linux-distributies en macOS-versies kennen die compatibel zijn met Defender voor Eindpunt om de integratie te laten werken. Zie voor meer informatie:
- [Systeemvereisten voor Microsoft Defender voor Eindpunt voor Linux](microsoft-defender-endpoint-linux.md#system-requirements)  
- [Systeemvereisten voor Microsoft Defender voor Eindpunt voor Mac](microsoft-defender-endpoint-mac.md#system-requirements).

## <a name="onboarding-non-windows-devices"></a>Onboarding niet-Windows-apparaten
U moet de volgende stappen ondernemen om niet-Windows-apparaten aan te sluiten:
1. Selecteer uw voorkeursmethode voor onboarding:

   - Voor macOS-apparaten kunt u ervoor kiezen om aan boord te gaan via Microsoft Defender ATP of via een oplossing van derden. Zie Microsoft Defender voor Eindpunt voor Mac voor [meer informatie.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac)
   - Voor andere niet-Windows-apparaten kiest u **Onboard non-Windows-apparaten via integratie van derden.**   
       
     1. Selecteer in het navigatiedeelvenster **Interoperabiliteitspartners.**  >   Zorg ervoor dat de oplossing van derden wordt vermeld.

        2. Selecteer op **het tabblad Partnertoepassingen** de partner die uw niet-Windows-apparaten ondersteunt.

        3. Selecteer **Partnerpagina openen om** de pagina van de partner te openen. Volg de instructies op de pagina.

        4. Nadat u een account hebt gemaakt of een abonnement hebt genomen op de partneroplossing, moet u naar een fase gaan waarin een globale tenantbeheerder in uw organisatie wordt gevraagd een machtigingsaanvraag van de partnertoepassing te accepteren. Lees de machtigingsaanvraag zorgvuldig door om ervoor te zorgen dat het is uitgelijnd met de service die u nodig hebt. 

        
2. Voer een detectietest uit door de instructies van de oplossing van derden te volgen.

## <a name="offboard-non-windows-devices"></a>Offboard niet-Windows-apparaten

1. Volg de documentatie van derden om de externe oplossing los te koppelen van Microsoft Defender voor Eindpunt.

2. Verwijder machtigingen voor de oplossing van derden in uw Azure AD-tenant.
   1. Meld u aan bij de [Azure-portal.](https://portal.azure.com)
   2. Selecteer **Azure Active Directory > Enterprise Applications**.
   3. Selecteer de toepassing die u wilt offboarden.
   4. Selecteer de **knop** Verwijderen.


## <a name="related-topics"></a>Verwante onderwerpen
- [Onboard Windows 10-apparaten](configure-endpoints.md)
- [Onboard-servers](configure-server-endpoints.md)
- [Instellingen voor proxy- en internetverbinding configureren](configure-proxy-internet.md)
- [Problemen met de onboarding van Microsoft Defender voor eindpunten oplossen](troubleshoot-onboarding.md)
