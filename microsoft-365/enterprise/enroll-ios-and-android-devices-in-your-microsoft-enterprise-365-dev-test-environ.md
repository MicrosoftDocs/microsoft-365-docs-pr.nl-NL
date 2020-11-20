---
title: IOS-iPadOS en Android-apparaten registreren in uw Microsoft 365 voor Enterprise-testomgeving
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
description: Gebruik deze test lab-handleiding om apparaten in uw Microsoft 365-test omgeving te registreren en deze extern te beheren.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367081"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>IOS-en Android-apparaten registreren in uw Microsoft 365 voor Enterprise-testomgeving

*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*

In dit artikel wordt uitgelegd hoe u eenvoudige functies voor het beheren van mobiele apparaten voor iOS-en iPadOS-en Android-apparaten registreert en test in uw Microsoft 365 voor Enterprise testomgeving.

Voor het registreren van iOS-en iPadOS en Android-apparaten in de testomgeving, moet u drie stappen uitvoeren:
- [Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: uw iOS-en iPadOS-en Android-apparaten registreren](#phase-2-enroll-your-ios-and-android-devices)
- [Fase 3: uw iOS-en iPadOS en Android-apparaten extern beheren](#phase-3-manage-your-ios-and-android-devices-remotely)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken

Als u een iOS-iPadOS en Android-apparaat op een lichte manier wilt registreren met de minimale vereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Als u iOS-iPadOS en Android-apparaten wilt registreren in een gesimuleerde Enterprise-versie, volgt u de instructies in [Pass-Through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Voor het testen van geautomatiseerde licentie-en groepslidmaatschappen is de gesimuleerde Enterprise testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest. Dit is een optie, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en u kunt experimenteren in een omgeving die een typische organisatie voorstelt.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fase 2: uw iOS-en Android-apparaten registreren

Als u een MDM-oplossing (Mobile Device Management) overweegt om uw apparaten te beheren, kunt u Microsoft intune gebruiken. Wanneer u met een MDM-provider werkt, waaronder intune, zijn de optie ' ingeschreven '. Wanneer u zich registreert, ontvangen ze de functies en instellingen die u configureert. 

In intune zijn er een aantal manieren om uw iOS-iPadOS en Android-apparaten te registreren. U kunt de optie voor inschrijving kiezen die het meest geschikt is voor uw organisatie. Zie de volgende artikelen voor meer informatie en richtlijnen:

- [Implementatiehandleiding: iOS-en iPadOS-apparaten registreren in Microsoft intune](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [Implementatiehandleiding: Android-apparaten registreren in Microsoft intune](/mem/intune/fundamentals/deployment-guide-enrollment-android)

Als u klaar bent om intune te gebruiken voor Apparaatbeheer en bepaalde richtlijnen wilt, kunt u de volgende informatie raadplegen:

- [Overzicht van apparaats beheer](/mem/intune/fundamentals/what-is-device-management)
- [Zelfstudie: procedure intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [Implementatiehandleiding: installatie of verplaatsing naar Microsoft intune](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fase 3: uw iOS-en Android-apparaten extern beheren

Microsoft intune biedt de functie voor het opnieuw instellen van wachtwoorden voor extern vergrendelen. Als iemand zijn of haar apparaat kwijtraakt, kunt u het toestel extern vergrendelen. Als iemand zijn of haar wachtwoord vergeet, kunt u dit extern opnieuw instellen.

- Als u een iOS-iPadOS of Android-apparaat extern wilt vergrendelen, raadpleegt u [apparaten extern vergrendelen met intune](/mem/intune/remote-actions/device-remote-lock).
- Als u de wachtwoordcode extern opnieuw wilt instellen, raadpleegt u de [wachtwoordcode van een apparaat in intune opnieuw instellen of verwijderen](/mem/intune/remote-actions/device-passcode-reset).

Zie [beschikbare Apparaatinstellingen](/mem/intune/remote-actions/device-management#available-device-actions)voor andere taken die u extern kunt uitvoeren.
    
## <a name="next-step"></a>Volgende stap

Verken de extra functies en mogelijkheden van het [beheer van mobiele apparaten](m365-enterprise-test-lab-guides.md#mobile-device-management) in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)
  
[Beleid voor apparaatcompatibiliteit voor uw Microsoft 365 voor Enterprise testomgeving](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)
