---
title: Microsoft Defender voor Eindpunt op Android
ms.reviewer: ''
description: Beschrijft hoe u Microsoft Defender voor Eindpunt op Android installeert en gebruikt
keywords: microsoft, defender, Microsoft Defender for Endpoint, android, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: ceccd9e3c8a8137f672e7be519675034a84c7881
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055111"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a>Microsoft Defender voor Eindpunt op Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

In dit onderwerp wordt beschreven hoe u Defender voor Eindpunt op Android kunt installeren, configureren, bijwerken en gebruiken.

> [!CAUTION]
> Het uitvoeren van andere endpointbeveiligingsproducten van derden naast Defender voor Eindpunt op Android kan waarschijnlijk prestatieproblemen en onvoorspelbare systeemfouten veroorzaken.


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a>Microsoft Defender voor Eindpunt installeren op Android

### <a name="prerequisites"></a>Vereisten

-   **Voor eindgebruikers**

    -   Microsoft Defender for Endpoint-licentie die is toegewezen aan de eindgebruiker(s) van de app. Zie [Microsoft Defender voor endpoint-licentievereisten](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

    -   Intune-bedrijfsportal app kan worden gedownload van [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) en is beschikbaar op het Android-apparaat.

        -   Bovendien kunnen apparaat(en) worden geregistreerd [via](/mem/intune/user-help/enroll-device-android-company-portal) de app Intune-bedrijfsportal om intune-beleid voor apparaat compliance af te dwingen. Hiervoor moet aan de eindgebruiker een licentie Microsoft Intune toegewezen.

    -   Zie Licenties toewijzen aan gebruikers voor meer informatie over het toewijzen van [licenties.](/azure/active-directory/users-groups-roles/licensing-groups-assign)
        

-   **Voor beheerders**

    -   Toegang tot de Microsoft Defender-beveiligingscentrum portal.

        > [!NOTE]
        > Microsoft Intune is de enige ondersteunde MDM-oplossing (Mobile Device Management) voor de implementatie van Microsoft Defender voor Eindpunt op Android. Momenteel worden alleen geregistreerde apparaten ondersteund voor het afdwingen van Defender voor Eindpunt op android-gerelateerde apparaat compliancebeleid in Intune. 

    -   Access [Microsoft Endpoint Manager beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431), om de app te implementeren voor geregistreerde gebruikersgroepen in uw organisatie.
        
### <a name="network-requirements"></a>Netwerkvereisten

- Als Microsoft Defender voor Eindpunt op Android werkt wanneer deze is verbonden met een netwerk, moet de firewall/proxy worden geconfigureerd om toegang tot URL's van [de Microsoft Defender-service](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)voor eindpunten in te stellen.

### <a name="system-requirements"></a>Systeemvereisten

-   Mobiele telefoons met Android 6.0 en hoger. **Tablets en andere mobiele apparaten met Android worden momenteel niet ondersteund.** 

-   Intune-bedrijfsportal app wordt gedownload van [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) en geïnstalleerd. Apparaatinschrijving is vereist om intune-beleid voor apparaat compliance af te dwingen.

### <a name="installation-instructions"></a>Installatie-instructies

Microsoft Defender voor Eindpunt op Android ondersteunt installatie op beide modi van geregistreerde apparaten, de oudere apparaatbeheerder en Android Enterprise-modi.
**Op dit moment worden apparaten met een persoonlijk eigendom met werkprofiel en volledig beheerde gebruikersapparaatinschrijvingen van bedrijven ondersteund in Android Enterprise. Ondersteuning voor andere Android Enterprise-modi wordt aangekondigd wanneer u klaar bent.**

De implementatie van Microsoft Defender voor Eindpunt op Android is via Microsoft Intune (MDM).
Zie Microsoft Defender voor Eindpunt implementeren op Android met Microsoft Intune voor [meer Microsoft Intune.](android-intune.md)


> [!NOTE]
> **Microsoft Defender voor Eindpunt voor Android is nu beschikbaar op [Google Play.](https://play.google.com/store/apps/details?id=com.microsoft.scmx)** <br> U kunt verbinding maken met Google Play vanuit Intune om microsoft Defender voor eindpunt-app te implementeren, in de verschillende registratiemodi voor Apparaatbeheerder en Android Enterprise. 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>Microsoft Defender configureren voor Eindpunt op Android

Richtlijnen voor het configureren van Microsoft Defender voor Endpoint voor Android-functies zijn beschikbaar in Microsoft Defender voor eindpunt [configureren op Android-functies.](android-configure.md)



## <a name="related-topics"></a>Verwante onderwerpen
- [Microsoft Defender voor Eindpunt op Android implementeren via Microsoft Intune](android-intune.md)
- [Microsoft Defender voor Eindpunt in Android-functies configureren](android-configure.md)

