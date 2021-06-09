---
title: IOS-/iPadOS- en Android-apparaten registreren in uw Microsoft 365 voor bedrijfstestomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Gebruik deze Test Lab Guide om apparaten in te schrijven in uw Microsoft 365 testomgeving en ze op afstand te beheren.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367081"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>IOS- en Android-apparaten registreren in uw Microsoft 365 voor bedrijfstestomgeving

*Deze testlaborator kan alleen worden gebruikt Microsoft 365 voor bedrijfstestomgevingen.*

In dit artikel wordt beschreven hoe u eenvoudige mogelijkheden voor mobiel apparaatbeheer voor iOS/iPadOS- en Android-apparaten kunt registreren en testen in uw Microsoft 365 voor bedrijfstestomgeving.

Het registreren van iOS-/iPadOS- en Android-apparaten in uw testomgeving omvat drie fasen:
- [Fase 1: uw Microsoft 365 voor bedrijfstestomgeving](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Uw iOS-/iPadOS- en Android-apparaten registreren](#phase-2-enroll-your-ios-and-android-devices)
- [Fase 3: Uw iOS/iPadOS- en Android-apparaten op afstand beheren](#phase-3-manage-your-ios-and-android-devices-remotely)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Voor een visuele kaart van alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide stack, gaat u naar Microsoft 365 voor [enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365 voor bedrijfstestomgeving

Als u iOS-/iPadOS- en Android-apparaten op een lichtgewicht manier wilt registreren met de minimumvereisten, volgt u de instructies in [de lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u iOS/iPadOS- en Android-apparaten wilt registreren in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Voor het testen van geautomatiseerde licenties en groepslidmaatschap is geen gesimuleerde testomgeving voor ondernemingen vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services). Het wordt hier als een optie aangeboden, zodat u geautomatiseerde licenties en groepslidmaatschap kunt testen en u erop kunt experimenteren in een omgeving die een normale organisatie vertegenwoordigt.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fase 2: Uw iOS- en Android-apparaten registreren

Als u een MDM-oplossing (Mobile Device Management) overweegt om uw apparaten te beheren, kunt u deze Microsoft Intune. Wanneer u met een MDM-provider werkt, inclusief Intune, worden apparaten 'geregistreerd'. Wanneer ze zijn geregistreerd, ontvangen ze de functies en instellingen die u configureert. 

In Intune zijn er een aantal manieren om uw iOS-/iPadOS- en Android-apparaten in te schrijven. U kunt de inschrijvingsoptie kiezen die het beste werkt voor uw organisatie. Zie de volgende artikelen voor meer informatie en richtlijnen:

- [Implementatiehandleiding: IOS- en iPadOS-apparaten registreren in Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [Implementatiehandleiding: Android-apparaten registreren in Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-android)

Als u Klaar bent om Intune te gebruiken voor apparaatbeheer en wat richtlijnen wilt, kunnen de volgende informatie u helpen:

- [Overzicht van apparaatbeheer](/mem/intune/fundamentals/what-is-device-management)
- [Zelfstudie: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [Implementatiehandleiding: Instellen of verplaatsen naar Microsoft Intune](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fase 3: Uw iOS- en Android-apparaten op afstand beheren

Microsoft Intune biedt de functie Voor het opnieuw instellen van toegangscodes op afstand. Als iemand zijn of haar apparaat kwijt is, kunt u het apparaat op afstand vergrendelen. Als iemand zijn wachtwoordcode vergeet, kunt u deze op afstand opnieuw instellen.

- Zie Apparaten op afstand vergrendelen met Intune als u een iOS/iPadOS- of Android-apparaat op afstand [wilt vergrendelen.](/mem/intune/remote-actions/device-remote-lock)
- Zie Een apparaatcode opnieuw instellen of verwijderen [in Intune](/mem/intune/remote-actions/device-passcode-reset)om de wachtwoordcode op afstand opnieuw in te stellen.

Zie beschikbare apparaatacties voor extra taken die u op afstand [kunt uitvoeren.](/mem/intune/remote-actions/device-management#available-device-actions)
    
## <a name="next-step"></a>Volgende stap

Ontdek extra [functies en mogelijkheden](m365-enterprise-test-lab-guides.md#mobile-device-management) voor mobiel apparaatbeheer in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)
  
[Apparaat compliancebeleid voor uw Microsoft 365 voor bedrijfstestomgeving](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)
