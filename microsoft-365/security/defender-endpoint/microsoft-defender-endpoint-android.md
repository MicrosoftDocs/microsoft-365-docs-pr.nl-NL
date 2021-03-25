---
title: Microsoft Defender ATP voor Android
ms.reviewer: ''
description: Beschrijft hoe u Microsoft Defender ATP voor Android installeert en gebruikt
keywords: microsoft, defender, atp, android, installatie, implementeren, verwijderen, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e2432dc4aa2c67fadc9112512a080f24c0064df4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187611"
---
# <a name="microsoft-defender-for-endpoint-for-android"></a>Microsoft Defender voor Eindpunt voor Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

In dit onderwerp wordt beschreven hoe u Defender voor Eindpunt voor Android kunt installeren, configureren, bijwerken en gebruiken.

> [!CAUTION]
> Het uitvoeren van andere endpointbeveiligingsproducten van derden naast Defender voor Eindpunt voor Android kan waarschijnlijk prestatieproblemen en onvoorspelbare systeemfouten veroorzaken.


## <a name="how-to-install-microsoft-defender-for-endpoint-for-android"></a>Microsoft Defender voor Eindpunt voor Android installeren

### <a name="prerequisites"></a>Vereisten

-   **Voor eindgebruikers**

    -   Microsoft Defender for Endpoint-licentie die is toegewezen aan de eindgebruiker(s) van de app. Zie [Microsoft Defender voor endpoint-licentievereisten](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

    -   De Intune Company Portal-app kan worden gedownload van [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) en is beschikbaar op het Android-apparaat.

        -   Bovendien kunnen apparaat(en) worden geregistreerd [via](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) de Intune Company Portal-app om intune-beleid voor apparaat compliance af te dwingen. Hiervoor moet aan de eindgebruiker een Microsoft Intune-licentie worden toegewezen.

    -   Zie Licenties toewijzen aan gebruikers voor meer informatie over het toewijzen van [licenties.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)
        

-   **Voor beheerders**

    -   Toegang tot de microsoft Defender-beveiligingscentrumportal.

        > [!NOTE]
        > Microsoft Intune is de enige ondersteunde MDM-oplossing (Mobile Device Management) voor het implementeren van Microsoft Defender voor Eindpunt voor Android. Momenteel worden alleen geregistreerde apparaten ondersteund voor het afdwingen van het compliancebeleid voor Defender voor Eindpunt voor Android in Intune. 

    -   Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.

### <a name="system-requirements"></a>Systeemvereisten

-   Android-apparaten met Android 6.0 en hoger.
-   De Intune Company Portal-app wordt gedownload van [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) en geïnstalleerd. Apparaatinschrijving is vereist om intune-beleid voor apparaat compliance af te dwingen.

### <a name="installation-instructions"></a>Installatie-instructies

Microsoft Defender voor Eindpunt voor Android ondersteunt de installatie op beide modi van geregistreerde apparaten: de oudere modi Apparaatbeheerder en Android Enterprise.
**Op dit moment worden apparaten met een persoonlijk eigendom met een werkprofiel en volledig beheerde gebruikersapparaatinschrijvingen van het bedrijf ondersteund in Android Enterprise. Ondersteuning voor andere Android Enterprise-modi wordt aangekondigd wanneer u klaar bent.**

De implementatie van Microsoft Defender voor Eindpunt voor Android is via Microsoft Intune (MDM).
Zie Microsoft Defender voor Eindpunt voor Android implementeren met [Microsoft Intune](android-intune.md)voor meer informatie.


> [!NOTE]
> **Microsoft Defender voor Eindpunt voor Android is nu beschikbaar op [Google Play.](https://play.google.com/store/apps/details?id=com.microsoft.scmx)** <br> U kunt verbinding maken met Google Play vanuit Intune om microsoft Defender voor eindpunt-app te implementeren, in de verschillende registratiemodi voor Apparaatbeheerder en Android Enterprise. 

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-android"></a>Microsoft Defender configureren voor Eindpunt voor Android

Richtlijnen voor het configureren van Microsoft Defender voor endpoint voor Android-functies zijn beschikbaar in [Microsoft Defender configureren voor endpoint voor Android-functies.](android-configure.md)



## <a name="related-topics"></a>Verwante onderwerpen
- [Microsoft Defender voor eindpunt implementeren voor met Microsoft Intune](android-intune.md)
- [Microsoft Defender voor endpoint voor Android-functies configureren](android-configure.md)

