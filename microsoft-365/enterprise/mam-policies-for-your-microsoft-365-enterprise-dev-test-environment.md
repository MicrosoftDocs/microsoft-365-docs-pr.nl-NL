---
title: Beleid voor apparaatcompatibiliteit voor uw Microsoft 365 voor Enterprise testomgeving
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
description: U kunt deze test lab-handleiding gebruiken om beleid voor het naleving van intune-apparaten toe te voegen aan de testomgeving van Microsoft 365.
ms.openlocfilehash: 3c77a7ea8ddc5120a2ce53fa0834dab213502657
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686752"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Beleid voor apparaatcompatibiliteit voor uw Microsoft 365 voor Enterprise testomgeving

*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*

Met de instructies in dit artikel voegt u het nalevingsbeleid van een intune-apparaat voor Windows 10-apparaten en Microsoft 365-apps voor Enterprise toe aan uw Microsoft 365 voor Enterprise-testomgeving.

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klik op [Hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken

Als u het MAM-beleid slechts op een lichte manier met de minimumvereisten wilt configureren, volgt u de instructies in de [basisconfiguratie](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Als u het MAM-beleid in een gesimuleerde Enterprise wilt configureren, volgt u de instructies in [Pass-to-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Voor het testen van de geautomatiseerde licentie-en groepslidmaatschappen is de gesimuleerde Enterprise testomgeving niet vereist, waaronder een gesimuleerd intranet dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest. U kunt dit hier opgeven als optie, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en experimenteert in een omgeving die een typische organisatie voorstelt. 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: een beleid voor naleving van apparaten maken voor Windows 10-apparaten

In deze fase maakt u een beleid voor naleving van apparaten voor Windows 10-apparaten.
  
1. Ga naar het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) , Meld u aan bij uw microsoft 365-test abonnement met uw globale beheerdersaccount.
    
2. Open de Azure-Portal op een nieuw tabblad van uw browser [https://portal.azure.com](https://portal.azure.com) .

3. Ga naar het tabblad Azure Portal in uw browser, typ **intune** in het zoekvak en klik vervolgens op **intune**.
    
4. Als u in het **Microsoft intune** -venster geen optie voor **Apparaatbeheer hebt ingeschakeld** , klikt u erop. Klik in het deelvenster voor het **beheer van mobiele apparaten** op **intune MDM-autoriteit**en klik vervolgens op **kiezen**. Vernieuw het tabblad browser.
    
5. Klik in het linker navigatiedeelvenster op **groepen**.
    
6. Klik in het deelvenster **groepen-alle groepen** op **+ nieuwe groep**.
    
7. Selecteer in het deelvenster **groep** de tekst **Microsoft 365** of **beveiliging** voor **groepstype?**, typ **beheerd Windows 10-apparaat gebruikers** in **naam**, selecteer **toegewezen aan** **lidmaatschaps type**en klik vervolgens op **maken**. 
    
8. Klik op **Microsoft intune**. Klik in het deelvenster **Microsoft intune** in de lijst **snelle taken** op **een nalevingsbeleid maken**.
    
9. Klik in het deelvenster **profielen voor nalevingsbeleid** op **beleid maken**.
    
10. Typ **Windows 10**in het deelvenster **beleid maken** onder **naam**. In **platform**selecteert u **Windows 10 en hoger**, klikt u op **OK** in het venster **Windows 10-nalevingsbeleid** en vervolgens op **maken**. 
    
11. Klik op **profielen voor nalevingsbeleid**en klik vervolgens op de naam van het **Windows 10** -beleid.
    
12. Klik in het deelvenster **Windows 10** op **opdrachten**en vervolgens op **groepen selecteren om op te nemen**.
    
13. Klik in het deelvenster **groepen selecteren om** op te nemen op de groep gebruikers van de **beheerde Windows 10-apparaten** en klik vervolgens op **selecteren**.
    
14. Klik achtereenvolgens op **Opslaan**, **Microsoft intune-overzicht**en **client toepassingen** in de linkernavigatiebalk.
    
15. Klik in het deelvenster **client toepassingen** op **apps**en klik vervolgens op **toevoegen**. 

16. Selecteer in het deelvenster **app toevoegen** de optie **app-type**en selecteer vervolgens **Windows 10** onder **Microsoft 365 Suite**.

17. Selecteer in het deelvenster **app toevoegen** de gegevens van de **app-Suite**.
 
18. Typ in het deelvenster **gegevens van app-Suite** **Microsoft 365-apps for Enterprise** in **naam van Suite** en **Suite-beschrijving**.
Klik op OK.

19. Selecteer in het deelvenster **app toevoegen** de optie **app-Suite configureren**en klik vervolgens op **OK**.

20. Selecteer **app Suite-instellingen**in het deelvenster **app toevoegen** .

21. Selecteer voor **Update kanaal**de optie **Semi-Annual Enterprise**en klik vervolgens op **OK**.

22. Klik in het deelvenster **app toevoegen** op **toevoegen**.

U beschikt nu over een apparaatcompatibiliteit voor het testen van de geselecteerde apps in het nalevingsbeleid voor **Windows 10** -apparaten en de leden van de groep gebruikers van de **beheerde Windows 10-apparaat** . Houd er rekening mee dat Microsoft 365 wordt geselecteerd als groepstype, om aanvullende bronnen te maken. 
  
## <a name="next-step"></a>Volgende stap

Verken de extra functies en mogelijkheden van het [beheer van mobiele apparaten](m365-enterprise-test-lab-guides.md#mobile-device-management) in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Proefversie van Microsoft 365 voor Enterprise test lab](m365-enterprise-test-lab-guides.md).
  
[IOS-en Android-apparaten registreren in uw Microsoft 365 voor Enterprise-testomgeving](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
