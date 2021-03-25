---
title: Privacygegevens - Microsoft Defender voor Eindpunt voor iOS
ms.reviewer: ''
description: Beschrijft privacygegevens voor Microsoft Defender voor Eindpunt voor iOS
keywords: microsoft, defender, atp, ios, beleid, overzicht
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f3851d9ecc0a40a9fa52702ee187fb8a94a740c3
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186675"
---
# <a name="privacy-information---microsoft-defender-for-endpoint-for-ios"></a>Privacygegevens - Microsoft Defender voor Eindpunt voor iOS

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!NOTE]
> Defender voor Eindpunt voor iOS gebruikt een VPN om de functie Webbeveiliging te bieden. Dit is geen gewone VPN en is een lokale of self-looping VPN die geen verkeer buiten het apparaat neemt. **Microsoft of uw organisatie ziet uw browseactiviteit niet.**

Defender voor Eindpunt voor iOS verzamelt gegevens van uw geconfigureerde iOS-apparaten en slaat deze op in dezelfde tenant waar u Defender voor Eindpunt hebt. De gegevens worden verzameld om Defender voor Endpoint voor iOS veilig, up-to-date te houden, te presteren zoals verwacht en om de service te ondersteunen.

Zie Microsoft Defender for [Endpoint data storage and privacy (Microsoft Defender for Endpoint data storage and privacy) voor meer informatie over gegevensopslag.](data-storage-privacy.md)

## <a name="required-data"></a>Vereiste gegevens 

Vereiste gegevens bestaan uit gegevens die nodig zijn om Defender voor Eindpunt voor iOS te laten werken zoals verwacht. Deze gegevens zijn essentieel voor de werking van de service en kunnen gegevens bevatten die betrekking hebben op de eindgebruiker, de organisatie, het apparaat en apps. 

Hier is een lijst met de typen gegevens die worden verzameld: 

### <a name="web-page-or-network-information"></a>Webpagina- of netwerkgegevens 

- Domeinnaam van de website alleen wanneer een schadelijke verbinding of webpagina wordt gedetecteerd. 

### <a name="device-and-account-information"></a>Apparaat- en accountgegevens 

- Apparaatgegevens, zoals datum &, iOS-versie, CPU-informatie en apparaataanduiding, waarbij apparaataanduiding een van de volgende opties is: 

    - Wi-Fi mac-adres van adapter 

    - Willekeurig gegenereerde, wereldwijd unieke id (GUID) 

- Tenant-, apparaat- en gebruikersgegevens 

    - Azure Active Directory (AD) Device ID en Azure User ID : hiermee wordt het apparaat uniek geïdentificeerd, respectievelijk Gebruiker bij Azure Active Directory. 

    - Azure tenant-id - GUID die uw organisatie identificeert in Azure Active Directory. 

    - Microsoft Defender for Endpoint org ID - Unieke id die is gekoppeld aan de onderneming waar het apparaat deel van uitmaken. Hiermee kan Microsoft vaststellen of er problemen zijn die van invloed zijn op een selecte set ondernemingen en het aantal ondernemingen dat is beïnvloed. 

    - Gebruikersnaam : e-mail-id van de gebruiker. 

### <a name="product-and-service-usage-data"></a>Gegevens over product- en servicegebruik 

De volgende gegevens worden alleen verzameld voor de Microsoft Defender for Endpoint-app die op het apparaat is geïnstalleerd. 

- App-pakketgegevens, waaronder de status van de naam, versie en app-upgrade. 

- Acties in de app. 

- Crashrapportlogboeken die zijn gegenereerd door iOS. 

- Geheugengebruiksgegevens. 

## <a name="optional-data"></a>Optionele gegevens 

Optionele gegevens omvatten diagnostische gegevens en feedbackgegevens van de client. Optionele diagnostische gegevens: aanvullende gegevens voor het maken van productverbeteringen en het verstrekken van uitgebreide informatie voor het detecteren, diagnosticeren en oplossen van problemen. Deze gegevens zijn alleen voor diagnostische doeleinden en zijn niet vereist voor de service zelf. 

Optionele diagnostische gegevens omvatten: 

- App-, CPU- en netwerkgebruik voor Defender voor Eindpunt. 

- Functies die zijn geconfigureerd door de beheerder van Defender voor Eindpunt. 

Feedbackgegevens worden verzameld via feedback in de app die door de gebruiker wordt verstrekt. 

- Het e-mailadres van de gebruiker als hij of zij ervoor kiest het te verstrekken.

- Feedbacktype (lach, frons, idee) en eventuele feedback van de gebruiker. 

Zie Meer informatie over [Privacy voor meer informatie.](https://aka.ms/mdatpiosprivacystatement)


