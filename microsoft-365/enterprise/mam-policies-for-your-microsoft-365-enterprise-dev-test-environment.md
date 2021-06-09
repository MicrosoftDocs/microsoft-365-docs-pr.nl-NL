---
title: Apparaat compliancebeleid voor uw Microsoft 365 voor bedrijfstestomgeving
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
description: Gebruik deze testlaboratoriumhandleiding om intune-beleid voor apparaat compliance toe te voegen aan uw Microsoft 365 voor bedrijfstestomgeving.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367093"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Apparaat compliancebeleid voor uw Microsoft 365 voor bedrijfstestomgeving

*Deze testlaborator kan alleen worden gebruikt Microsoft 365 voor bedrijfstestomgevingen.*

In dit artikel wordt beschreven hoe u een intune-apparaat compliancebeleid voor Windows 10 apparaten en Microsoft 365-apps voor ondernemingen toevoegt aan uw Microsoft 365 voor bedrijfstestomgeving.

Het toevoegen van een Intune-beleid voor apparaat compliance omvat twee fasen:
- [Fase 1: uw Microsoft 365 voor bedrijfstestomgeving](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Een apparaat compliancebeleid maken voor Windows 10 apparaten](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Voor een visuele kaart van alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide stack, gaat u naar Microsoft 365 voor [enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365 voor bedrijfstestomgeving

Als u MAM-beleid alleen op een lichtgewicht manier wilt configureren met de minimumvereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u MAM-beleid wilt configureren in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Voor het testen van geautomatiseerde licenties en groepslidmaatschap is geen gesimuleerde testomgeving voor ondernemingen vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services). Het wordt hier als een optie aangeboden, zodat u geautomatiseerde licenties en groepslidmaatschap kunt testen en erop kunt experimenteren in een omgeving die een normale organisatie vertegenwoordigt.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: Een apparaat compliancebeleid maken voor Windows 10 apparaten

In deze fase maakt u een apparaat compliancebeleid voor Windows 10 apparaten. In deze fase Microsoft Intune en het [Microsoft Endpoint Manager beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) gebruikt om een groep toe te voegen en een compliancebeleid te maken.

1. Ga naar het [Microsoft 365-beheercentrum](https://admin.microsoft.com)en meld u aan bij uw Microsoft 365 testlaboratorium met uw globale beheerdersaccount. Selecteer het **Endpoint Manager** beheercentrum. Het [Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) wordt geopend.

    Als er een bericht wordt weergegeven dat lijkt op **U** hebt apparaatbeheer nog niet ingeschakeld, selecteert u Intune als de MDM-autoriteit. Zie De autoriteit voor mobiel apparaatbeheer instellen voor de [specifieke stappen.](/mem/intune/fundamentals/mdm-authority-set)

    Het Endpoint Manager beheercentrum richt zich op apparaatbeheer en app-beheer. Zie [Zelfstudie: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).

2. Voeg **in** Groepen een nieuwe **groep** Microsoft 365 **of** beveiligingsgroep met de naam Beheerd **Windows 10 apparaatgebruikers** toe, met een type **Toegewezen** lidmaatschap. In de volgende stappen wijst u uw compliancebeleid toe aan deze groep. 

    Zie Groepen toevoegen om gebruikers en apparaten te ordenen **voor meer informatie over** Microsoft 365 of [beveiligingsgroepen.](/mem/intune/fundamentals/groups-add) 

3. Maak **in Apparaten** een Windows 10 compliancebeleid. Wijs dit beleid toe aan **de groep Windows 10 apparaten die u** hebt gemaakt.

    In uw beleid kunt u eenvoudige wachtwoorden blokkeren, een firewall vereisen, de Microsoft Defender Antimalware-service uitvoeren en meer. Een compliancebeleid bevat meestal de basisinstellingen of het absolute minimum dat elk apparaat moet hebben.

    Zie Compliancebeleid gebruiken om regels in te stellen voor apparaten die u beheert voor de specifieke stappen en voor informatie over de beschikbare nalevingsinstellingen die u kunt [configureren.](/mem/intune/protect/device-compliance-get-started)

Wanneer u klaar bent, hebt u een apparaat compliancebeleid voor het testen van leden in de groep Windows 10 **apparaatgebruikers.**
  
## <a name="next-step"></a>Volgende stap

Ontdek extra [functies en mogelijkheden](m365-enterprise-test-lab-guides.md#mobile-device-management) voor mobiel apparaatbeheer in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 voor enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).
  
[IOS- en Android-apparaten registreren in uw Microsoft 365 voor bedrijfstestomgeving](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
