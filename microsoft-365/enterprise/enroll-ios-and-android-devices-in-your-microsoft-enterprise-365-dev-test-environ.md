---
title: IOS- en Android-apparaten inschrijven in uw Microsoft 365 Enterprise-testomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Gebruik deze Test Lab Guide om apparaten in te schrijven in uw Microsoft 365-testomgeving en deze op afstand te beheren.
ms.openlocfilehash: ae6ff9e704fc239638b5951a95ae23c45e85b7be
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805668"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a>IOS- en Android-apparaten inschrijven in uw Microsoft 365 Enterprise-testomgeving

*Deze Test Lab Guide kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*

Door de instructies in dit artikel op te volgen, u de basismogelijkheden voor het beheer van mobiele apparaten voor iOS- en Android-apparaten inschrijven en testen in uw Microsoft 365 Enterprise-testomgeving.

![Test Lab-hulplijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de Microsoft 365 Enterprise Test Lab Guide stack.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Uw Microsoft 365 Enterprise-testomgeving uitbouwen

Als je iOS- en Android-apparaten alleen op een lichtgewicht manier wilt inschrijven met de minimumvereisten, volg dan de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u iOS- en Android-apparaten wilt inschrijven in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Het testen van geautomatiseerde licenties en groepslidmaatschap vereist niet de gesimuleerde bedrijfstestomgeving, die een gesimuleerd intranet bevat dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services). Het wordt hier als optie geleverd, zodat u geautomatiseerde licenties en groepslidmaatschap testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt. 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fase 2: Schrijf je iOS- en Android-apparaten in

Gebruik eerst de instructies in [Installeren en meld u aan bij de Bedrijfsportal-app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) om de Microsoft Intune Company Portal-app aan te passen aan uw testomgeving.

Gebruik vervolgens de instructies in [Het instellen van toegang tot uw bedrijfsbronnen](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) om een iOS-apparaat in te schrijven.

Gebruik vervolgens de instructies in [Schrijf je Android-apparaat in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) om een Android-apparaat in te schrijven.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fase 3: Beheer je iOS- en Android-apparaten op afstand

Microsoft Intune biedt zowel mogelijkheden voor het vergrendelen als het resetten van toegangscodes. Als iemand zijn apparaat verliest, u het apparaat op afstand vergrendelen. Als iemand zijn toegangscode vergeet, u deze op afstand opnieuw instellen.
  
Een iOS- of Android-apparaat op afstand vergrendelen:

1. Meld u aan bij [https://portal.azure.com](https://portal.azure.com) de Azure-portal met de referenties van uw globale beheerdersaccount.
2. Typ Op het tabblad Azure-portal in uw browser **Intune** in het zoekvak en klik vervolgens op **Intune**.
3. Klik op **Apparaten > alle apparaten**.
4. Klik in de lijst met apparaten op een iOS- of Android-apparaat en klik vervolgens op de actie **Extern vergrendelen.**

    
Ga als reactie op het instellen van de toegangscode op afstand:

1. Meld u indien nodig aan [https://portal.azure.com](https://portal.azure.com) bij de Azure-portal met de referenties van uw globale beheerdersaccount.
2. Typ Op het tabblad Azure-portal in uw browser **Intune** in het zoekvak en klik vervolgens op **Intune**.
3. Klik op **Apparaten > alle apparaten**.
4. Klik in de lijst met apparaten die u beheert op een iOS- of Android-apparaat en kies **... Meer**. Kies vervolgens de externe actie **voor toegangscodes verwijderen.**

Zie [Beschikbare apparaatacties](https://docs.microsoft.com/intune/device-management#available-device-actions)voor extra experimenten.

    
## <a name="next-step"></a>Volgende stap

Ontdek extra functies en mogelijkheden [voor het beheer](m365-enterprise-test-lab-guides.md#mobile-device-management) van mobiele apparaten in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise Test Lab-handleidingen](m365-enterprise-test-lab-guides.md)
  
[Apparaatnalevingsbeleid voor uw Microsoft 365 Enterprise-testomgeving](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Microsoft 365 Enterprise implementeren](deploy-microsoft-365-enterprise.md)

