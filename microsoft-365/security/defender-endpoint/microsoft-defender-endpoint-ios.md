---
title: Microsoft Defender voor Eindpunt op iOS
ms.reviewer: ''
description: Beschrijft hoe u Microsoft Defender voor Eindpunt in iOS installeert en gebruikt
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, overview, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: cbe2fb39221bd9907a3d690503a392edb019d61b
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194851"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>Microsoft Defender voor Eindpunt op iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

**Microsoft Defender voor Eindpunt op iOS** biedt bescherming tegen phishing en onveilige netwerkverbindingen van websites, e-mailberichten en apps. Alle waarschuwingen zijn beschikbaar via één deelvenster glas in de Microsoft Defender-beveiligingscentrum. De portal biedt beveiligingsteams een gecentraliseerde weergave van bedreigingen op iOS-apparaten, samen met andere platforms.

> [!CAUTION]
> Het uitvoeren van andere endpointbeveiligingsproducten van derden naast Defender voor Eindpunt in iOS kan waarschijnlijk prestatieproblemen en onvoorspelbare systeemfouten veroorzaken.

## <a name="pre-requisites"></a>Voorwaarden

**Voor eindgebruikers**

- Microsoft Defender for Endpoint-licentie die is toegewezen aan de eindgebruiker(s) van de app. Zie [Microsoft Defender voor endpoint-licentievereisten](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).

- **Voor geregistreerde apparaten:** Apparaten(en) zijn geregistreerd [via](/mem/intune/user-help/enroll-your-device-in-intune-ios) de Intune-bedrijfsportal app om intune-beleid voor apparaat compliance af te dwingen. Hiervoor moet aan de eindgebruiker een licentie Microsoft Intune toegewezen.
    - Intune-bedrijfsportal app kan worden gedownload vanuit de [Apple App Store.](https://apps.apple.com/us/app/intune-company-portal/id719171358)
    - Apple staat niet toe dat gebruikers worden omgeleid om andere apps te downloaden uit de App Store en daarom moet deze stap worden uitgevoerd door de gebruiker voordat deze wordt onboarding naar de Microsoft Defender voor Endpoint-app.

- **Voor niet-geregistreerde apparaten**: Apparaten(en) zijn geregistreerd bij Azure Active Directory. Hiervoor moet de eindgebruiker zijn aangemeld via de [Microsoft Authenticator app.](https://apps.apple.com/app/microsoft-authenticator/id983156458)

- Zie Licenties toewijzen aan gebruikers voor meer informatie over het toewijzen van [licenties.](/azure/active-directory/users-groups-roles/licensing-groups-assign)

**Voor beheerders**

- Toegang tot de Microsoft Defender-beveiligingscentrum portal.

- Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.

    > [!NOTE]
    > Microsoft Intune is de enige ondersteunde UEM-oplossing (Unified Endpoint Management) voor het implementeren van Microsoft Defender voor Eindpunt en het afdwingen van Defender voor endpoint-gerelateerde beleidsregels voor apparaat compliance in Intune.

**Systeemvereisten**

- iOS-apparaat met iOS 11.0 en hoger. iPad apparaten worden officieel ondersteund vanaf versie 1.1.15010101.

- Apparaat is geregistreerd met de Intune-bedrijfsportal [app](https://apps.apple.com/us/app/intune-company-portal/id719171358) of geregistreerd bij Azure Active Directory via [Microsoft Authenticator.](https://apps.apple.com/app/microsoft-authenticator/id983156458)

## <a name="installation-instructions"></a>Installatie-instructies

Implementatie van Microsoft Defender voor Endpoint op iOS kan via Microsoft Endpoint Manager (MEM) en zowel gecontroleerde als niet-bewaakte apparaten worden ondersteund. Eindgebruikers kunnen de app ook rechtstreeks installeren vanuit de [Apple App Store.](https://aka.ms/mdatpiosappstore)
Zie Microsoft Defender voor eindpunten implementeren in [iOS voor meer informatie.](ios-install.md)

## <a name="resources"></a>Middelen

- Blijf op de hoogte van aanstaande releases door naar Nieuw in Microsoft Defender voor Eindpunt op [iOS](ios-whatsnew.md) of onze blog te [gaan.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)

- Feedback geven via een in-app feedbacksysteem of via [de SecOps-portal](https://securitycenter.microsoft.com)

## <a name="next-steps"></a>Volgende stappen

- [Microsoft Defender voor eindpunt implementeren in iOS](ios-install.md)
- [Microsoft Defender voor eindpunt configureren voor iOS-functies](ios-configure-features.md)
