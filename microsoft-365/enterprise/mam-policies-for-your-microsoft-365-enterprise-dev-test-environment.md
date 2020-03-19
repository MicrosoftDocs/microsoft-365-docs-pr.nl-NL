---
title: Nalevingsbeleid voor apparaten voor uw Microsoft 365 Enterprise-testomgeving
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Gebruik deze Test Lab Guide om intune-beleid voor apparaatnaleving toe te voegen aan uw Microsoft 365 Enterprise-testomgeving.
ms.openlocfilehash: b0b8bd2d76a3959bbcca749545d9a16e50491d20
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812029"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>Nalevingsbeleid voor apparaten voor uw Microsoft 365 Enterprise-testomgeving

*Deze Test Lab Guide kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*

Met de instructies in dit artikel voegt u een Intune-beleid voor apparaatnaleving toe voor Windows 10-apparaten en Office 365 ProPlus aan uw Microsoft 365 Enterprise-testomgeving.

![Lab-handleidingen testen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de Microsoft 365 Enterprise Test Lab Guide stack.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Uw Microsoft 365 Enterprise-testomgeving uitbouwen

Als u alleen mam-beleid op een lichtgewicht manier wilt configureren met de minimale vereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u MAM-beleid wilt configureren in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Voor het testen van geautomatiseerde licenties en groepslidmaatschap is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services). Het wordt hier als optie verstrekt, zodat u geautomatiseerde licenties en groepslidmaatschap testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt. 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: Een beleid voor naleving van apparaten voor apparaten met apparaten voor apparaten met apparaten maken

In deze fase maakt u een nalevingsbeleid voor apparaten voor apparaten met apparaten voor apparaten met een apparaat.
  
1. Ga naar de Office 365-portal op ([https://portal.office.com](https://portal.office.com)) en meld u aan bij uw Office 365-testlababonnement met uw wereldwijde beheerdersaccount.
    
2. Open de Azure-portal op een nieuw [https://portal.azure.com](https://portal.azure.com)tabblad van uw browser op .

3. Typ **Intune** in het zoekvak op het tabblad Azure-portal in uw browser en klik op **Intune**.
    
4. Als u een **bericht Voor apparaatbeheer u nog niet** hebt ingeschakeld In het deelvenster Microsoft **Intune** klikt u erop. Klik in het **deelvenster Autoriteit voor beheer** van mobiele apparaten op **MDM-autoriteit inafstemmen**en klik vervolgens op **Kiezen**. Het tabblad browser vernieuwen.
    
5. Klik in het linkernavigatiedeelvenster op **Groepen**.
    
6. In the **Groups-All groups** pane, click **+ New Group**.
    
7. Selecteer **in** het deelvenster Groep de optie Office **365** of **Beveiliging** voor **Name** **groepstype?** **Managed Windows 10 device users** **Assigned** **Membership type** **Create** 
    
8. Klik **op Microsoft Intune**. Klik in het deelvenster **Microsoft Intune** in de lijst **Snelle taken** op **Een nalevingsbeleid maken**.
    
9. Klik in het deelvenster **Nalevingsbeleidsprofielen** op **Beleid maken**.
    
10. Typ **Windows 10**in het deelvenster **Beleid maken** in **Naam**. Selecteer **in Platform**Windows **10 en hoger**op **OK** in het deelvenster **Nalevingsbeleid van Windows 10** en klik vervolgens op **Maken**. 
    
11. Klik op **Nalevingsbeleidsprofielen**en klik vervolgens op de naam van het **Windows 10-beleid.**
    
12. Klik in het deelvenster **Windows 10** op **Toewijzingen**en klik vervolgens op **Groepen selecteren om op te nemen**.
    
13. Klik in het **deelvenster Selecteren om op te nemen** op de groep **Beheerde gebruikers van Windows 10-apparaten** en klik vervolgens op **Selecteren**.
    
14. Klik **op Opslaan,** klik op **Microsoft Intune-Overzicht**en klik vervolgens op **Client-apps** in de linkernavigatie.
    
15. Klik in het deelvenster **Client-apps** op **Apps**en klik vervolgens op **Toevoegen**. 

16. Selecteer **app-type** toevoegen in het deelvenster **App**toevoegen en selecteer **Vervolgens Windows 10** onder **Office 365 Suite**.

17. Selecteer **App-suitegegevens**in het deelvenster **App toevoegen** .
 
18. Typ **Office 365 ProPlus** in het deelvenster **App Suite-informatie** in zowel **Suite-naam** als **suitebeschrijving**.
Klik op OK.

19. Selecteer **app-suite configureren**in het deelvenster **App toevoegen** en klik op **OK**.

20. Selecteer **App-instellingen**in het deelvenster **App toevoegen** .

21. Selecteer **Halfjaarlijks**kanaal voor **Bijwerken**en klik op **OK**.

22. Klik **in** het deelvenster App toevoegen op **Toevoegen**.

U hebt nu een beleid voor apparaatnaleving voor het testen van de geselecteerde apps in het nalevingsbeleid voor **Windows 10-apparaten** en voor leden van de groep Beheerde gebruikers van **Windows 10-apparaten.** Houd er rekening mee dat het selecteren van Office 365 als groepstype extra bronnen zal opleveren. 
  
## <a name="next-step"></a>Volgende stap

Ontdek extra functies en mogelijkheden voor het beheer van [mobiele apparaten](m365-enterprise-test-lab-guides.md#mobile-device-management) in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise Test Lab-handleidingen](m365-enterprise-test-lab-guides.md).
  
[IOS- en Android-apparaten inschrijven in uw Microsoft 365 Enterprise-testomgeving](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Microsoft 365 Enterprise implementeren](deploy-microsoft-365-enterprise.md)

[Enterprise Mobility + Beveiliging (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
