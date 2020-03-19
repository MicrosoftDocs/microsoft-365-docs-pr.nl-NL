---
title: Licentie- en groepslidmaatschap voor uw Microsoft 365 Enterprise-testomgeving automatiseren
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
ms.custom:
- TLG
- Ent_TLGs
description: Groepsgebaseerde licenties en dynamisch groepslidmaatschap configureren in uw Microsoft 365 Enterprise-testomgeving.
ms.openlocfilehash: 266ae8cb133eccf74ea75382b400ca8241782ec5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806816"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a>Licentie- en groepslidmaatschap voor uw Microsoft 365 Enterprise-testomgeving automatiseren

*Deze Test Lab Guide kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*

Groepslicenties worden automatisch toegeschreven of verwijderd licenties voor een gebruikersaccount op basis van groepslidmaatschap. Dynamisch groepslidmaatschap voegt leden toe of verwijdert leden aan een groep op basis van de eigenschappen van gebruikersaccounts, zoals Afdeling of Land. In dit artikel wordt een demonstratie van beide in uw Microsoft 365 Enterprise-testomgeving gegeven.

Er zijn twee fasen voor het instellen van automatisch licentie- en dynamisch groepslidmaatschap in uw Microsoft 365 Enterprise-testomgeving:

1. Maak de Microsoft 365 Enterprise-testomgeving.
2. Dynamisch groepslidmaatschap en automatische licenties configureren en testen.

![Lab-handleidingen testen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de Microsoft 365 Enterprise Test Lab Guide stack.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Uw Microsoft 365 Enterprise-testomgeving uitbouwen

Als u alleen geautomatiseerde licenties en groepslidmaatschap op een lichtgewicht manier wilt testen met de minimale vereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u geautomatiseerde licenties en groepslidmaatschap in een gesimuleerde onderneming wilt testen, volgt u de instructies in [pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Voor het testen van geautomatiseerde licenties en groepslidmaatschap is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services). Het wordt hier als optie verstrekt, zodat u geautomatiseerde licenties en groepslidmaatschap testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt. 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fase 2: Dynamisch groepslidmaatschap en automatische licenties configureren en testen

Eerst maakt u een nieuwe verkoopgroep en voegt u een dynamische groepslidmaatschapsregel toe, zodat gebruikersaccounts met de afdeling die is ingesteld op Verkoop automatisch worden toegevoegd aan de groep Verkoop.

1. Meld u met een privé-exemplaar van uw internetbrowser [https://portal.office.com](https://portal.office.com) aan bij de Office 365-portal met het globale beheerdersaccount van uw Microsoft 365 E5-testlababonnement.
2. Ga op een apart tabblad van uw [https://portal.azure.com](https://portal.azure.com)browser naar de Azure-portal op .
3. Typ in de Azure-portal **groepen** in het zoekvak en klik op **Groepen**.
4. Klik in het deelvenster **Alle groepen** op **Nieuwe groep**.
5. Selecteer **Office 365**in **Groepstype**.
6. Typ **Verkoop**in **groepsnaam**.
7. Selecteer **Dynamische gebruiker**in **lidmaatschapstype**.
8. Klik **op Dynamische gebruikersleden**.
9. Ga als volgt te werk in het deelvenster **Regels voor lidmaatschap van Dynamic:** 
   - Selecteer de eigenschap van de **afdeling.**
   - Selecteer de **operator Gelijken.**
   - Typ **Verkoop** in **waarde**.
10. Klik op **Opslaan**.
11. Klik **op Maken**.

Vervolgens configureert u de groep Verkoop, zodat leden automatisch de Microsoft 365 E5-licentie toegewezen krijgen.

1. Klik op de groep **Verkoop** en klik vervolgens op **Licenties**.
2. Selecteer **Microsoft 365 E5**in het deelvenster **Licentietoewijzingen** bijwerken en klik op **Opslaan**.
3. Sluit het tabblad Azure-portal in uw browser.

Vervolgens test u dynamisch groepslidmaatschap en automatische licenties op het account Gebruiker 4. 

1. Klik op het tabblad **Microsoft Office Start** in uw browser op **Beheerder**.
2. Klik op het tabblad **Microsoft 365-beheercentrum** op **Actieve gebruikers**.
3. Klik op de pagina **Actieve gebruikers** op het account **Gebruiker 4.**
4. Klik **in** het deelvenster Gebruiker 4 op **Bewerken** voor **productlicenties**.
5. Schakel in het deelvenster **Productlicenties** de **Microsoft 365 E5-licentie** uit en klik op **> sluiten opslaan**.
6. Controleer in de eigenschappen van het account Gebruiker 4 of er geen productlicenties zijn toegewezen en dat er geen groepslidmaatschappen zijn.
7. Klik **op Bewerken** voor **contactgegevens**.
8. Klik in het deelvenster **Contactgegevens bewerken** op **Contactgegevens**.
9. Typ **verkoop** in **Sales**het veld Afdeling en klik op **> sluiten opslaan**.
10. Wacht een paar minuten en klik vervolgens regelmatig op het vernieuwingspictogram rechtsboven in het accountvenster Gebruiker 4. 

Na verloop van tijd zou je de:

- **Groepslidmaatschappen,** bijgewerkt met de **groep Verkoop.**
- **Eigenschap productlicenties** bijgewerkt met de **Microsoft 365 E5-licentie.**

Bekijk deze stappen in de identiteitsfase voor informatie en koppelingen voor het implementeren van dynamisch groepslidmaatschap en automatische licenties in productie:

- [Automatische licenties instellen](identity-use-group-management.md#identity-group-license)
- [Dynamisch groepslidmaatschap instellen](identity-use-group-management.md#identity-dyn-groups)

## <a name="next-step"></a>Volgende stap

Ontdek extra [identiteitsfuncties](m365-enterprise-test-lab-guides.md#identity) en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Fase 2: Identiteit](identity-infrastructure.md)

[Microsoft 365 Enterprise Test Lab-handleidingen](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise-implementatie](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-documentatie](https://docs.microsoft.com/microsoft-365-enterprise/)
