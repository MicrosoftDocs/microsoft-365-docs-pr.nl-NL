---
title: IOS-en Android-apparaten registreren in uw Microsoft 365 voor Enterprise-testomgeving
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
description: Gebruik deze test lab-handleiding om apparaten in uw Microsoft 365-test omgeving te registreren en deze extern te beheren.
ms.openlocfilehash: 3736934dbb62e84aad6a91fcd1d65b4a47ef8637
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487694"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>IOS-en Android-apparaten registreren in uw Microsoft 365 voor Enterprise-testomgeving

*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*

In dit artikel wordt beschreven hoe u eenvoudige functies voor het beheren van mobiele apparaten voor iOS-en Android-apparaten registreert en test in uw Microsoft 365 voor Enterprise testomgeving.

Voor het registreren van iOS-en Android-apparaten in de testomgeving, moet u drie stappen uitvoeren:
- [Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: uw iOS-en Android-apparaten registreren](#phase-2-enroll-your-ios-and-android-devices)
- [Fase 3: uw iOS-en Android-apparaten extern beheren](#phase-3-manage-your-ios-and-android-devices-remotely)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken

Als u iOS-en Android-apparaten op een lichte manier wilt registreren met de minimumvereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Als u iOS-en Android-apparaten wilt registreren in een gesimuleerde onderneming, volgt u de instructies in [Pass Through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Voor het testen van geautomatiseerde licentie-en groepslidmaatschappen is de gesimuleerde Enterprise testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest. Dit is een optie, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en u kunt experimenteren in een omgeving die een typische organisatie voorstelt.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fase 2: uw iOS-en Android-apparaten registreren

Gebruik eerst de instructies in [installeren en meld u aan bij de bedrijfsportal-app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) om de app Microsoft intune Company portal aan te passen aan uw testomgeving.

Volg vervolgens de instructies in [toegang tot uw bedrijfsbronnen instellen](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) om een IOS-apparaat in te schrijven.

Volg vervolgens de instructies in [uw Android-apparaat in intune registreren](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) om een Android-apparaat in te schrijven.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fase 3: uw iOS-en Android-apparaten extern beheren

Microsoft intune biedt de functies voor het opnieuw instellen van wachtwoorden voor extern vergrendelen. Als iemand zijn of haar apparaat kwijtraakt, kunt u het toestel extern vergrendelen. Als iemand zijn of haar wachtwoord vergeet, kunt u dit extern opnieuw instellen.
  
Een iOS-of Android-apparaat op afstand vergrendelen:

1. Meld u aan bij de Azure-Portal [https://portal.azure.com](https://portal.azure.com) met de referenties van uw globale beheerdersaccount.
2. Voer in het zoekvak van de Azure-Portal **intune** in en selecteer vervolgens **intune**.
3. Klik op **apparaten > alle apparaten**.
4. Selecteer in de lijst met apparaten een iOS-of Android-apparaat en selecteer vervolgens de actie op **afstand vergrendelen** .
    
De wachtwoordcode extern opnieuw instellen:

1. Meld u indien nodig aan bij de Azure-Portal [https://portal.azure.com](https://portal.azure.com) met de referenties van uw globale beheerdersaccount.
2. Voer in het zoekvak van de Azure-Portal **intune** in en selecteer vervolgens **intune**.
3. Selecteer **Devices**  >  **alle apparaten**.
4. Selecteer in de lijst met apparaten die u beheert een iOS-of Android-apparaat, selecteer **... **En selecteer vervolgens de actie op de computer met de actie **wachtwoordcode verwijderen** .

Zie [beschikbare acties voor apparaten](https://docs.microsoft.com/intune/device-management#available-device-actions)voor een extra proef.
    
## <a name="next-step"></a>Volgende stap

Verken de extra functies en mogelijkheden van het [beheer van mobiele apparaten](m365-enterprise-test-lab-guides.md#mobile-device-management) in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)
  
[Beleid voor apparaatcompatibiliteit voor uw Microsoft 365 voor Enterprise testomgeving](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)
