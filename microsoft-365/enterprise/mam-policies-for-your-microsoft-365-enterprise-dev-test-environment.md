---
title: Beleid voor apparaatnaleving voor uw Microsoft 365 Enterprise-testomgeving
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
description: Gebruik deze Test Lab-handleiding om intune-apparaatnalevingsbeleid toe te voegen aan uw Microsoft 365 Enterprise-testomgeving.
ms.openlocfilehash: 5ef39310ff74e5d5a38e8a5dd8c7ca24a126af58
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679024"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>Beleid voor apparaatnaleving voor uw Microsoft 365 Enterprise-testomgeving

*Deze testlabrichtlijn kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*

Met de instructies in dit artikel voegt u een intune-apparaatcompliancebeleid voor Windows 10-apparaten en Microsoft 365-apps voor bedrijven toe aan uw Microsoft 365 Enterprise-testomgeving.

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart met alle artikelen over de Microsoft 365 Enterprise-testlabrichtlijnen.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: uw Microsoft 365 Enterprise-testomgeving uitbouwen

Als u gewoon mam-beleid op een lichtgewicht manier wilt configureren met de minimumvereisten, volgt u de instructies in [lichtgewicht basisconfiguratie](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Als u MAM-beleid wilt configureren in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Voor het testen van geautomatiseerde licenties en groepslidmaatschap is niet de gesimuleerde bedrijfstestomgeving vereist, die een gesimuleerd intranet bevat dat is verbonden met internet en directorysynchronisatie voor een AD DS-forest (Active Directory Domain Services). Het wordt hier als optie aangeboden, zodat u geautomatiseerde licenties en groepslidmaatschap testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt. 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: Een beleid voor naleving van apparaten maken voor Windows 10-apparaten

In deze fase maakt u een beleid voor apparaatnaleving voor Windows 10-apparaten.
  
1. Ga naar de Office 365-portal op ( [https://portal.office.com](https://portal.office.com) ) en meld u aan bij uw Office 365-testlab-abonnement met uw algemene beheerdersaccount.
    
2. Open op een nieuw tabblad van uw browser de Azure-portal op [https://portal.azure.com](https://portal.azure.com) .

3. Typ **Intune** op het tabblad Azure-portal in uw browser in het zoekvak en klik op **Intune**.
    
4. Als u een **bericht Voor apparaatbeheer u nog niet hebt ingeschakeld,** klikt u erop in het deelvenster **Microsoft Intune.** Klik in het deelvenster **Autoriteit voor mobiel apparaatbeheer** op **Intune MDM-autoriteit**en klik vervolgens op **Kiezen**. Vernieuw het tabblad browser.
    
5. Klik in het linkernavigatiedeelvenster op **Groepen**.
    
6. In the **Groups-All groups** pane, click **+ New Group**.
    
7. Selecteer in het deelvenster **Groep** De optie **Office 365** of **Beveiliging** voor **groepstype?** typ **Gebruikers van beheerde Windows 10-apparaten** in **Naam,** selecteer **Toegewezen** in het **type Lidmaatschap**en klik op **Maken**. 
    
8. Klik op **Microsoft Intune**. Klik in het deelvenster **Microsoft Intune** in de lijst **Snelle taken** op **Een nalevingsbeleid maken**.
    
9. Klik in het deelvenster **Nalevingsbeleidsprofielen** op **Beleid maken**.
    
10. Typ **Windows 10**in het deelvenster **Beleid maken** in **Naam**. Selecteer in **Platform** **Windows 10 en hoger**op **OK** In het **deelvenster Nalevingsbeleid van Windows 10** en klik vervolgens op **Maken**. 
    
11. Klik op **Nalevingsbeleidsprofielen**en klik vervolgens op de naam **van het Windows 10-beleid.**
    
12. Klik in het deelvenster **Windows 10** op **Toewijzingen**en klik vervolgens op **Groepen selecteren om op te nemen**.
    
13. Klik in het deelvenster **Groepen selecteren dat u wilt opnemen** op de groep Gebruikers van beheerd Windows **10-apparaat** en klik vervolgens op **Selecteren**.
    
14. Klik **op Opslaan,** klik op **Microsoft Intune-Overzicht**en klik vervolgens op **Client-apps** in de linkernavigatie.
    
15. Klik in het deelvenster **Client-apps** op **Apps**en klik vervolgens op **Toevoegen**. 

16. Selecteer **app-type toevoegen in** het deelvenster App toevoegen en selecteer **vervolgens Windows 10** onder **Office 365 Suite**. **App type**

17. Selecteer **app-suitegegevens**in het deelvenster **App** toevoegen .
 
18. Typ **Microsoft 365-apps voor bedrijven** in het deelvenster App **Suite** in zowel **Suite-naam** als **suitebeschrijving.**
Klik op OK.

19. Selecteer **app-suite configureren**in het deelvenster **App toevoegen** en klik vervolgens op **OK**.

20. Selecteer **app-suite-instellingen**in het deelvenster **App** toevoegen .

21. Selecteer **voor Update-kanaal**de optie **Semijaarlijkse onderneming**en klik op **OK**.

22. Klik **in** het deelvenster App toevoegen op **Toevoegen**.

U hebt nu een beleid voor de naleving van het apparaat voor het testen van de geselecteerde apps in het nalevingsbeleid voor **Windows 10-apparaten** en voor leden van de groep Gebruikers van **beheerde Windows 10-apparaten.** Houd er rekening mee dat het selecteren van Office 365 als groepstype extra bronnen maakt. 
  
## <a name="next-step"></a>Volgende stap

Ontdek aanvullende functies en mogelijkheden voor het beheer van [mobiele apparaten](m365-enterprise-test-lab-guides.md#mobile-device-management) in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise Test Lab-gidsen](m365-enterprise-test-lab-guides.md).
  
[IOS- en Android-apparaten inschrijven in uw Microsoft 365 Enterprise-testomgeving](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Microsoft 365 Enterprise implementeren](deploy-microsoft-365-enterprise.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
