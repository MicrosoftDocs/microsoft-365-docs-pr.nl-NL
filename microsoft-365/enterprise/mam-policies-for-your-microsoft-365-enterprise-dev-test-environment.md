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
ms.openlocfilehash: c1de822e5a97416bd0c672d88f2902d8986638c8
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487410"
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

In deze fase maakt u een apparaatcompatibiliteit voor Windows 10-apparaten.
  
1. Ga naar het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) , Meld u aan bij uw microsoft 365-test abonnement met uw globale beheerdersaccount.
1. Open de Azure-Portal op een nieuw tabblad van uw browser [https://portal.azure.com](https://portal.azure.com) .
1. Voer in het zoekvak van de Azure-Portal **intune**in en selecteer vervolgens **intune**.
1. Als u in het **Microsoft intune** -venster geen optie voor **Apparaatbeheer hebt ingeschakeld** , kunt u deze selecteren. Selecteer in het deelvenster **Mobile Device Management Authority** de optie **intune MDM Authority**en selecteer vervolgens **Choose**.
1. Vernieuw het tabblad browser.
1. Selecteer **groepen**in het linker navigatiedeelvenster.
1. Selecteer in het deelvenster **groepen-alle groepen de** optie **+ nieuwe groep**.
1. Selecteer in het deelvenster **groep** de optie **Microsoft 365** of **beveiliging** voor **groepstype?**, Voer **beheerde gebruikers van Windows 10-apparaten** in **naam**in, selecteer **toegewezen aan** **lidmaatschaps type**en selecteer **maken**.
1. Selecteer **Microsoft intune**.
1. Selecteer in het deelvenster **Microsoft intune** in de lijst **snelle taken** de optie **een nalevingsbeleid maken**.
1. Selecteer in het deelvenster beleids **profielen voor compliance beleids** **regels maken**.
1. Voer in het deelvenster **beleid maken** in **naam** **Windows 10**in. In **platform**selecteert u **Windows 10 en later**, selecteert u **OK** in het deelvenster **nalevingsbeleid van Windows 10** en selecteert u **maken**.
1. Selecteer **profielen voor nalevingsbeleid**en selecteer vervolgens de naam van het **Windows 10** -beleid.
1. Selecteer in het deelvenster **Windows 10** **opdrachten**en selecteer **groepen selecteren om op te nemen**.
1. Selecteer in het deelvenster **groepen selecteren die moeten worden opgenomen** de groep gebruikers van de **beheerde Windows 10-apparaten** en selecteer vervolgens **selecteren**.
1. Selecteer **Opslaan**, selecteer **Microsoft intune-overzicht**en selecteer **client toepassingen** in de linkernavigatiebalk.
1. Selecteer **apps**in het deelvenster **client-apps** en selecteer vervolgens **toevoegen**.
1. Selecteer in het deelvenster **app toevoegen** de optie **app-type**en selecteer vervolgens **Windows 10** onder **Microsoft 365 Suite**.
1. Selecteer in het deelvenster **app toevoegen** de gegevens van de **app-Suite**.
1. Voer in het deelvenster met **app-Suite gegevens** de **Microsoft 365-apps voor Enterprise** in zowel **naam** als **Suite-beschrijving**in en selecteer **OK**.
1. Selecteer in het deelvenster **app toevoegen** de optie **app-Suite configureren**en selecteer vervolgens **OK**.
1. Selecteer **app Suite-instellingen**in het deelvenster **app toevoegen** .
1. Selecteer voor **Update kanaal**de optie **Semi-Annual Enterprise**en selecteer vervolgens **OK**.
1. Selecteer **toevoegen**in het deelvenster **app toevoegen** .

U beschikt nu over een apparaatcompatibiliteit voor het testen van de geselecteerde apps in het nalevingsbeleid voor **Windows 10** -apparaten en de leden van de groep gebruikers van de **beheerde Windows 10-apparaat** . Houd er rekening mee dat **Microsoft 365** wordt geselecteerd als groepstype, om aanvullende bronnen te maken.
  
## <a name="next-step"></a>Volgende stap

Verken de extra functies en mogelijkheden van het [beheer van mobiele apparaten](m365-enterprise-test-lab-guides.md#mobile-device-management) in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Proefversie van Microsoft 365 voor Enterprise test lab](m365-enterprise-test-lab-guides.md).
  
[IOS-en Android-apparaten registreren in uw Microsoft 365 voor Enterprise-testomgeving](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
