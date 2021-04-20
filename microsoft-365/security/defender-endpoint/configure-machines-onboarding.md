---
title: Apparaten in gebruik nemen bij Microsoft Defender voor Eindpunt
description: Houd onboarding bij van door Intune beheerde apparaten naar Microsoft Defender voor Eindpunt en verhoog de onboardingsnelheid.
keywords: onboard, Intune management, MDATP, WDATP, Microsoft Defender, Windows Defender, advanced threat protection, configuration management
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5e20c424f15561c8b6f0544b80aca6e30c56409d
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893327"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a>Apparaten in gebruik nemen bij Microsoft Defender voor Eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Elk onboarded apparaat voegt een extra EDR-sensor (EndPoint Detection and Response) toe en vergroot de zichtbaarheid van inbreukactiviteiten in uw netwerk. Onboarding zorgt er ook voor dat een apparaat kan worden gecontroleerd op kwetsbare onderdelen, evenals beveiligingsconfiguratieproblemen en kritieke herstelacties kan ontvangen tijdens aanvallen.

Voordat u onboarding van apparaten kunt bijhouden en beheren:
- [Uw apparaten registreren voor Intune-beheer](configure-machines.md#enroll-devices-to-intune-management)
- [Zorg ervoor dat u de benodigde machtigingen hebt](configure-machines.md#obtain-required-permissions)

## <a name="discover-and-track-unprotected-devices"></a>Niet-beveiligde apparaten ontdekken en bijhouden

De **Onboarding-kaart** biedt een overzicht op hoog niveau van uw onboardingsnelheid door het aantal Windows 10-apparaten dat daadwerkelijk is ge onboarded bij Defender for Endpoint te vergelijken met het totale aantal door Intune beheerde Windows 10-apparaten.

![Onboarding-kaart voor apparaatconfiguratiebeheer](images/secconmgmt_onboarding_card.png)<br>
*Kaart met onboarded-apparaten in vergelijking met het totale aantal door Intune beheerde Windows 10-apparaten*

>[!NOTE]
>Als u Security Center Configuration Manager, het onboarding-script of andere onboarding-methoden hebt gebruikt die geen Intune-profielen gebruiken, kunnen er gegevensverschillen zijn. Als u deze verschillen wilt oplossen, maakt u een bijbehorend Intune-configuratieprofiel voor Defender voor endpoint-onboarding en wijst u dat profiel toe aan uw apparaten.

## <a name="onboard-more-devices-with-intune-profiles"></a>Meer apparaten aan boord met Intune-profielen

Defender voor Eindpunt biedt verschillende handige opties voor [het onboarden van Windows 10-apparaten.](onboard-configure.md) Voor door Intune beheerde apparaten kunt u echter Intune-profielen gebruiken om de Defender for Endpoint-sensor eenvoudig te implementeren om apparaten te selecteren, zodat deze apparaten effectief aan de service worden ge onboardd.

Selecteer op **de Onboarding-kaart** **Meer apparaten onboarden om** een profiel op Intune te maken en toe te wijzen. De koppeling brengt u naar de pagina apparaat compliance op Intune, die een vergelijkbaar overzicht biedt van uw onboarding-status.

![Microsoft Defender ATP-apparaat compliancepagina op Intune-apparaatbeheer](images/secconmgmt_onboarding_1deviceconfprofile.png)<br>
   *Microsoft Defender ATP-apparaat compliancepagina op Intune-apparaatbeheer*

>[!TIP]
>U kunt ook navigeren naar de compliancepagina van Defender voor eindpunten in de [Microsoft Azure-portal](https://portal.azure.com/) van **Alle services > Intune > Apparaat compliance > Microsoft Defender ATP.**

>[!NOTE]
> Als u de meest recente apparaatgegevens wilt bekijken, klikt u op Lijst met **apparaten zonder ATP-sensor.**

Maak op de pagina apparaat compliance een configuratieprofiel speciaal voor de implementatie van de Defender for Endpoint-sensor en wijs dat profiel toe aan de apparaten die u wilt onboarden. U kunt dit doen door het volgende te doen:

- Selecteer **Een apparaatconfiguratieprofiel maken om ATP-sensor** te configureren om te beginnen met een vooraf gedefinieerd apparaatconfiguratieprofiel.
- Maak het apparaatconfiguratieprofiel vanaf het begin.

Lees voor meer informatie [over het gebruik van intune-apparaatconfiguratieprofielen voor onboard-apparaten naar Defender voor Eindpunt.](https://docs.microsoft.com/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile)

>Wilt u Microsoft Defender ATP ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a>Verwante onderwerpen
- [Controleren of uw apparaten juist zijn geconfigureerd](configure-machines.md)
- [Naleving van de beveiligingslijn defender voor eindpunt verhogen](configure-machines-security-baseline.md)
- [Asr-regelimplementatie en -detecties optimaliseren](configure-machines-asr.md)
