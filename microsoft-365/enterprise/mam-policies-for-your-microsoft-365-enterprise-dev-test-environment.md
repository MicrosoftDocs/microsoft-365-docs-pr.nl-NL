---
title: Beleid voor apparaatcompatibiliteit voor uw Microsoft 365 voor Enterprise testomgeving
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: U kunt deze test lab-handleiding gebruiken om beleid voor het naleving van intune-apparaten toe te voegen aan de testomgeving van Microsoft 365.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367093"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Beleid voor apparaatcompatibiliteit voor uw Microsoft 365 voor Enterprise testomgeving

*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*

In dit artikel wordt uitgelegd hoe u een intune-apparaatcompatibiliteit voor Windows 10-apparaten en Microsoft 365-apps voor Enterprise toevoegt aan uw Microsoft 365 voor Enterprise testomgeving.

Het nalevingsbeleid van een intune-apparaat bestaat uit twee fasen:
- [Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: een beleid voor naleving van apparaten maken voor Windows 10-apparaten](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken

Als u het MAM-beleid op slechts een lichte manier met de minimumvereisten wilt configureren, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Als u het MAM-beleid in een gesimuleerde Enterprise wilt configureren, volgt u de instructies in [Pass-to-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Voor het testen van geautomatiseerde licentie-en groepslidmaatschappen is de gesimuleerde Enterprise testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest. Dit wordt hier als optie geboden, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en experimenteert in een omgeving die een typische organisatie voorstelt.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: een beleid voor naleving van apparaten maken voor Windows 10-apparaten

In deze fase maakt u een beleid voor naleving van apparaten voor Windows 10-apparaten. In deze fase wordt Microsoft intune en het [Beheercentrum van Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) gebruikt om een groep toe te voegen en een nalevingsbeleid te maken.

1. Ga naar het [Microsoft 365-Beheercentrum](https://admin.microsoft.com)en meld u aan bij uw microsoft 365-test abonnement met uw globale beheerdersaccount. Selecteer het Beheercentrum voor **eindpunten** van de beheerder. Het [Beheercentrum voor eindpunten](https://go.microsoft.com/fwlink/?linkid=2109431) wordt geopend.

    Als u een bericht ziet dat vergelijkbaar is met de optie **Apparaatbeheer** weergeven, selecteert u intune als de MDM-autoriteit. Voor de specifieke stappen raadpleegt u [de service voor het beheer van mobiele apparaten instellen](/mem/intune/fundamentals/mdm-authority-set).

    Het Beheercentrum voor eindpunten van het Beheercentrum voor apparaten en de app-beheer. Voor een rondleiding van dit Beheercentrum raadpleegt u [Zelfstudie: procedure intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).

2. In **groepen** voegt u een nieuwe **Microsoft 365** of **beveiligings** groep met de naam **beheerde gebruikers van Windows 10-apparaten** met een **toegewezen** lidmaatschaps type toe. In de volgende stappen wijst u uw compliance-beleid toe aan deze groep. 

    Voor de specifieke stappen en voor informatie over **Microsoft 365** of **beveiligings** groepen, raadpleegt [u groepen toevoegen om gebruikers en apparaten te ordenen](/mem/intune/fundamentals/groups-add).

3. Maak in **apparaten** een nalevingsbeleid voor Windows 10. Wijs dit beleid toe aan de groep gebruikers van de **beheerde Windows 10-apparaten** die u hebt gemaakt.

    In uw beleid kunt u eenvoudige wachtwoorden blokkeren, een firewall vereisen, de Microsoft Defender malware-service uitvoeren en nog veel meer. Het nalevingsbeleid bevat meestal de basisinstellingen, of het minimum aantal voor elk apparaat.

    Voor de specifieke stappen en voor informatie over de beschikbare compliance-instellingen die u kunt configureren, raadpleegt u [nalevingsbeleid gebruiken om regels in te stellen voor apparaten die u beheert](/mem/intune/protect/device-compliance-get-started).

Wanneer u klaar bent, beschikt u over een beleid voor apparaatcompatibiliteit voor het testen van leden in de groep gebruikers van de **beheerde Windows 10-apparaten** .
  
## <a name="next-step"></a>Volgende stap

Verken de extra functies en mogelijkheden van het [beheer van mobiele apparaten](m365-enterprise-test-lab-guides.md#mobile-device-management) in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Proefversie van Microsoft 365 voor Enterprise test lab](m365-enterprise-test-lab-guides.md).
  
[IOS-en Android-apparaten registreren in uw Microsoft 365 voor Enterprise-testomgeving](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
