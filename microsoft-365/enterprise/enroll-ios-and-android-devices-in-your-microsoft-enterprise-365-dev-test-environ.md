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
ms.openlocfilehash: b4a95b2c7e58239c0a8d0d3b5045e7337f43de6b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686008"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>IOS-en Android-apparaten registreren in uw Microsoft 365 voor Enterprise-testomgeving

*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*

Door de instructies in dit artikel te volgen, kunt u de functies voor het beheren van mobiele apparaten voor iOS-en Android-apparaten registreren en testen in uw Microsoft 365 voor Enterprise testomgeving.

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Klik op [Hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken

Als u alleen iOS-en Android-apparaten op een lichte manier wilt registreren met de minimumvereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Als u iOS-en Android-apparaten wilt registreren in een gesimuleerde onderneming, volgt u de instructies in [Pass Through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Voor het testen van de geautomatiseerde licentie-en groepslidmaatschappen is de gesimuleerde Enterprise testomgeving niet vereist, waaronder een gesimuleerd intranet dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest. U kunt dit hier opgeven als optie, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en experimenteert in een omgeving die een typische organisatie voorstelt. 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fase 2: uw iOS-en Android-apparaten registreren

Gebruik eerst de instructies in [installeren en meld u aan bij de bedrijfsportal-app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) om de app Microsoft intune Company portal aan te passen aan uw testomgeving.

Volg vervolgens de instructies in [toegang tot uw bedrijfsbronnen instellen](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) om een IOS-apparaat in te schrijven.

Volg vervolgens de instructies in [uw Android-apparaat in intune registreren](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) om een Android-apparaat in te schrijven.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fase 3: uw iOS-en Android-apparaten extern beheren

Microsoft intune biedt de functies voor het opnieuw instellen van wachtwoorden voor extern vergrendelen. Als iemand zijn of haar apparaat kwijtraakt, kunt u het apparaat extern vergrendelen. Als iemand zijn of haar wachtwoord vergeet, kunt u dit extern herstellen.
  
Een iOS-of Android-apparaat op afstand vergrendelen:

1. Meld u aan bij de Azure-Portal [https://portal.azure.com](https://portal.azure.com) met de referenties van uw globale beheerdersaccount.
2. Typ in het dialoogvenster van uw browser op het tabblad Azure Portal de tekst **intune** in het zoekvak en klik vervolgens op **intune**.
3. Klik op **apparaten > alle apparaten**.
4. Klik op een iOS-of Android-apparaat in de lijst met apparaten en klik vervolgens op de actie op **afstand vergrendelen** .

    
De wachtwoordcode extern opnieuw instellen:

1. Meld u indien nodig aan bij de Azure-Portal [https://portal.azure.com](https://portal.azure.com) met de referenties van uw globale beheerdersaccount.
2. Typ in het dialoogvenster van uw browser op het tabblad Azure Portal de tekst **intune** in het zoekvak en klik vervolgens op **intune**.
3. Klik op **apparaten > alle apparaten**.
4. Klik in de lijst met apparaten die u beheert op een iOS-of Android-apparaat en kies **... Meer informatie**. Kies vervolgens de actie op de computer met de actie **wachtwoordcode verwijderen** .

Zie [beschikbare acties voor apparaten](https://docs.microsoft.com/intune/device-management#available-device-actions)voor een extra proef.

    
## <a name="next-step"></a>Volgende stap

Verken de extra functies en mogelijkheden van het [beheer van mobiele apparaten](m365-enterprise-test-lab-guides.md#mobile-device-management) in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)
  
[Beleid voor apparaatcompatibiliteit voor uw Microsoft 365 voor Enterprise testomgeving](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

