---
title: Microsoft Defender ATP voor iOS-overzicht
ms.reviewer: ''
description: Beschrijft hoe u MICROSOFT Defender ATP voor iOS installeert en gebruikt
keywords: microsoft, defender, atp, ios, overview, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: 1f20a81f5205c5734387214822fa87ac5cf9a09c
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698206"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>Microsoft Defender voor Eindpunt in iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

**Microsoft Defender voor Eindpunt op iOS** biedt bescherming tegen phishing en onveilige netwerkverbindingen van websites, e-mailberichten en apps. Alle waarschuwingen zijn beschikbaar via één deelvenster glas in het Microsoft Defender-beveiligingscentrum. De portal biedt beveiligingsteams een gecentraliseerde weergave van bedreigingen op iOS-apparaten, samen met andere platforms.

> [!CAUTION]
> Het uitvoeren van andere endpointbeveiligingsproducten van derden naast Defender voor Eindpunt in iOS kan waarschijnlijk prestatieproblemen en onvoorspelbare systeemfouten veroorzaken.

## <a name="pre-requisites"></a>Vereisten

**Voor eindgebruikers**

- Microsoft Defender for Endpoint-licentie die is toegewezen aan de eindgebruiker(s) van de app. Zie [Microsoft Defender voor endpoint-licentievereisten](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).

- Apparaat(en) zijn geregistreerd via [de](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) Intune Company Portal-app om intune-beleid voor apparaat compliance af te dwingen. Hiervoor moet aan de eindgebruiker een Microsoft Intune-licentie worden toegewezen.
    - De Intune Company Portal-app kan worden gedownload vanuit de [Apple App Store.](https://apps.apple.com/us/app/intune-company-portal/id719171358)
    - Apple staat niet toe dat gebruikers worden omgeleid om andere apps te downloaden uit de App Store en daarom moet deze stap worden uitgevoerd door de gebruiker voordat deze wordt onboarding naar de Microsoft Defender voor Endpoint-app.

- Zie Licenties toewijzen aan gebruikers voor meer informatie over het toewijzen van [licenties.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)

**Voor beheerders**

- Toegang tot de microsoft Defender-beveiligingscentrumportal.

    > [!NOTE]
    > Microsoft Intune is de enige ondersteunde MDM-oplossing (Mobile Device Management) voor de implementatie van Microsoft Defender voor Eindpunt in iOS. Momenteel worden alleen geregistreerde apparaten ondersteund voor het afdwingen van Defender voor Eindpunt op iOS-beleid voor apparaat compliance in Intune.

- Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.

**Systeemvereisten**

- iOS-apparaten met iOS 11.0 en hoger. iPad-apparaten worden officieel ondersteund vanaf versie 1.1.15010101.

- Apparaat is geregistreerd met de [Intune Company Portal-app](https://apps.apple.com/us/app/intune-company-portal/id719171358).

> [!NOTE]
> **Microsoft Defender ATP (Microsoft Defender for Endpoint) op iOS is nu beschikbaar in [de Apple App Store.](https://aka.ms/mdatpiosappstore)**

## <a name="installation-instructions"></a>Installatie-instructies

De implementatie van Microsoft Defender voor Eindpunt op iOS is via Microsoft Intune (MDM) en zowel gecontroleerde als niet-bewaakte apparaten worden ondersteund.
Zie Microsoft Defender voor eindpunten implementeren in [iOS voor meer informatie.](ios-install.md)

## <a name="resources"></a>Resources

- Blijf op de hoogte van aanstaande releases door naar Nieuw in Microsoft Defender voor Eindpunt op [iOS](ios-whatsnew.md) of onze blog te [gaan.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)

- Feedback geven via een in-app feedbacksysteem of via [de SecOps-portal](https://securitycenter.microsoft.com)

## <a name="next-steps"></a>Volgende stappen

- [Microsoft Defender voor eindpunt implementeren in iOS](ios-install.md)
- [Microsoft Defender voor eindpunt configureren voor iOS-functies](ios-configure-features.md)
