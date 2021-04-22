---
title: Microsoft Defender voor Eindpunt op Android - Privacyinformatie
description: Privacybesturingselementen, het configureren van beleidsinstellingen die van invloed zijn op privacy en informatie over de diagnostische gegevens die worden verzameld in Microsoft Defender voor Eindpunt op Android.
keywords: microsoft, defender, Microsoft Defender for Endpoint, android, privacy, diagnostic
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1aaae2970cfb2f6da82507eefa87c8d0e2227661
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939622"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a>Microsoft Defender voor Eindpunt op Android - Privacyinformatie

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


Defender voor Eindpunt op Android verzamelt gegevens van uw geconfigureerde Android-apparaten en slaat deze op in dezelfde tenant waar u Defender voor Eindpunt hebt. De gegevens worden verzameld om Defender voor Eindpunt voor Android veilig, up-to-date te houden, te presteren zoals verwacht en om de service te ondersteunen.

Zie Microsoft Defender for [Endpoint data storage and privacy (Microsoft Defender for Endpoint data storage and privacy) voor meer informatie over gegevensopslag.](data-storage-privacy.md)

Er worden gegevens verzameld om Defender voor Eindpunt voor Android veilig, up-to-date te houden, te presteren zoals verwacht en om de service te ondersteunen.

## <a name="required-data"></a>Vereiste gegevens 

Vereiste gegevens bestaan uit gegevens die nodig zijn om Defender voor Eindpunt voor Android te laten werken zoals verwacht. Deze gegevens zijn essentieel voor de werking van de service en kunnen gegevens bevatten die betrekking hebben op de eindgebruiker, de organisatie, het apparaat en apps. Hier is een lijst met de typen gegevens die worden verzameld:

### <a name="app-information"></a>App-informatie

Informatie over **kwaadaardige** Android-toepassingspakketten (APK's) op het apparaat, waaronder

-  Installatiebron
-  Opslaglocatie (bestandspad) van de APK
-  Tijd van installatie, grootte van APK en machtigingen

### <a name="web-page--network-information"></a>Webpagina/netwerkgegevens

- Volledige URL van de website alleen wanneer een schadelijke verbinding of webpagina wordt gedetecteerd.
- Verbindingsgegevens
- Protocoltype (zoals HTTP, HTTPS, enzovoort)


### <a name="device-and-account-information"></a>Apparaat- en accountgegevens

- Apparaatgegevens, zoals datum &, Android-versie, OEM-model, CPU-informatie en apparaataanduiding
- Apparaataanduiding is een van de volgende:
    - Wi-Fi mac-adres van adapter
    - [Android-id](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (zoals gegenereerd door Android op het moment van de eerste keer opstarten van het apparaat)
    - Willekeurig gegenereerde, wereldwijd unieke id (GUID)

- Tenant-, apparaat- en gebruikersgegevens
    -   Azure Active Directory (AD) Device ID en Azure User ID: Uniek identificeert het apparaat, gebruiker respectievelijk bij Azure Active Directory.

    -   Azure tenant-id - GUID die uw organisatie identificeert in Azure Active Directory

    -   Microsoft Defender for Endpoint org ID - Unieke id die is gekoppeld aan de onderneming waar het apparaat deel van uitmaken. Hiermee kan Microsoft bepalen of problemen van invloed zijn op een selecte set ondernemingen en hoeveel ondernemingen van invloed zijn 

    -   Gebruikersnaam : e-mail-id van de gebruiker

### <a name="product-and-service-usage-data"></a>Gegevens over product- en servicegebruik

De volgende gegevens worden alleen verzameld voor de Microsoft Defender for Endpoint-app die op het apparaat is geïnstalleerd. 

-   App-pakketgegevens, waaronder de status van de naam, versie en app-upgrade

-   Acties uitgevoerd in de app

-   Informatie over bedreigingsdetectie, zoals bedreigingsnaam, categorie, enzovoort.

-   Crashrapportlogboeken die zijn gegenereerd door Android

## <a name="optional-data"></a>Optionele gegevens

Optionele gegevens omvatten diagnostische gegevens en feedbackgegevens. Optionele diagnostische gegevens: aanvullende gegevens voor het maken van productverbeteringen en het verstrekken van uitgebreide informatie voor het detecteren, diagnosticeren en oplossen van problemen. Optionele diagnostische gegevens omvatten:

-   App-, CPU- en netwerkgebruik

-   Status van het apparaat vanuit het app-perspectief, inclusief scanstatus, tijdsinstellingen scannen, app-machtigingen verleend en upgradestatus

-   Functies die zijn geconfigureerd door de beheerder

-   Basisinformatie over de browsers op het apparaat

**Feedbackgegevens** worden verzameld via in-app feedback van de gebruiker

-   Het e-mailadres van de gebruiker als hij of zij ervoor kiest om het op te geven

-   Feedbacktype (glimlach, frons, idee) en eventuele feedback van de gebruiker
