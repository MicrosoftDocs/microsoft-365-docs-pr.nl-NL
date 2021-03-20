---
title: Automatiseer licenties en groepslidmaatschap voor uw microsoft 365 voor ondernemingstestomgeving
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
description: Configureer groepslicenties en dynamisch groepslidmaatschap in uw Microsoft 365 voor ondernemingstestomgeving.
ms.openlocfilehash: 26840e2884202a0fa9c4bb563f3d7c653482ef87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905366"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>Automatiseer licenties en groepslidmaatschap voor uw microsoft 365 voor ondernemingstestomgeving

*Deze testlaborator kan alleen worden gebruikt voor Microsoft 365 voor testomgevingen voor ondernemingen.*

Licenties op basis van groepen worden automatisch toegewezen of verwijderd voor een gebruikersaccount op basis van groepslidmaatschap. Dynamische groepslidmaatschap voegt leden toe aan een groep op basis van eigenschappen van gebruikersaccounts, zoals **Afdeling** of **Land.** In dit artikel wordt beschreven hoe u groepsleden toevoegt en verwijdert in uw microsoft 365 voor ondernemingstestomgeving.

Het instellen van lidmaatschap van automatische licenties en dynamische groepen in uw Microsoft 365-testomgeving voor ondernemingen omvat twee fasen:

- [Fase 1: Uw Microsoft 365 voor ondernemingstestomgeving opbouwen](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Dynamisch groepslidmaatschap en automatische licenties configureren en testen](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Ga naar [Microsoft 365 for enterprise Test Lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)Stack voor een visuele kaart voor alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide Stack.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Uw Microsoft 365 voor ondernemingstestomgeving opbouwen

Als u alleen geautomatiseerde licenties en groepslidmaatschap op een lichtgewicht manier wilt testen met de minimumvereisten, volgt u de instructies in De lichtgewicht [basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u geautomatiseerde licenties en groepslidmaatschap in een gesimuleerde onderneming wilt testen, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Voor het testen van geautomatiseerde licenties en groepslidmaatschap is geen gesimuleerde testomgeving voor ondernemingen vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services). Het wordt hier als een optie aangeboden, zodat u geautomatiseerde licenties en groepslidmaatschap kunt testen en erop kunt experimenteren in een omgeving die een normale organisatie vertegenwoordigt.
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fase 2: Dynamisch groepslidmaatschap en automatische licenties configureren en testen

Maak eerst een nieuwe groep met de naam Verkoop en voeg  een dynamische  groepslidmaatschapsregel toe, zodat gebruikersaccounts met de afdeling Die is ingesteld op Verkoop, automatisch deelnemen aan de groep Verkoop.

1. Meld u in een privé-exemplaar van uw internetbrowser aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met het globale beheerdersaccount van uw Microsoft 365 E5-testlaboratoriumabonnement.
2. Ga op een apart tabblad van uw browser naar de Azure-portal op [https://portal.azure.com](https://portal.azure.com) .
3. Voer in de Azure-portal **groepen** in het zoekvak in en selecteer vervolgens **Groepen.**
4. selecteer in **het deelvenster** Alle groepen de optie **Nieuwe groep**.
5. Selecteer **microsoft** **365** in groeptype .
6. Voer **in Groepsnaam** De **verkoop in.**
7. Selecteer **dynamische gebruiker in het type** **Lidmaatschap.**
8. Selecteer **Dynamische gebruikersleden.**
9. In het **deelvenster Dynamische lidmaatschapsregels:** 
   - Selecteer de **eigenschap afdeling.**
   - Selecteer de **operator Gelijk** aan.
   - Voer in **het** vak Waarde de tekst **Verkoop in.**
10. Kies **Opslaan**.
11. Selecteer **Maken**. 

Configureer vervolgens de groep Verkoop, zodat leden automatisch de Microsoft 365 E5-licentie krijgen toegewezen.

1. Selecteer de **groep** Verkoop en selecteer **vervolgens Licenties**.
2. Selecteer microsoft **365 E5** in het deelvenster **Licentietoewijzingen** bijwerken en selecteer **opslaan.**
3. Sluit in uw browser het tabblad Azure Portal.

Test vervolgens het dynamische groepslidmaatschap en automatische licenties voor het gebruikers 4-account:

1. Selecteer beheerder op het tabblad **Microsoft Office Home** in **uw** browser.
2. Selecteer actieve gebruikers op het tabblad **Microsoft 365-beheercentrum.** 
3. Selecteer op **de pagina** Actieve gebruikers het account **Gebruiker 4.**
4. Selecteer in het deelvenster Gebruiker **4** de optie **Bewerken** voor **productlicenties.**
5. Schakel in **het deelvenster Productlicenties** de **Microsoft 365 E5-licentie** uit en selecteer **vervolgens Sluiten**  >  **opslaan.**
6. Controleer in de eigenschappen van het Gebruikers 4-account of er geen productlicenties zijn toegewezen en dat er geen groepslidmaatschap is.
7. Selecteer Bewerken voor  **contactgegevens.**
8. Selecteer in **het deelvenster Contactgegevens** bewerken de optie **Contactgegevens**.
9. Voer in **het** vak Afdeling **verkoop in** en selecteer **vervolgens Sluiten**  >  **opslaan.**
10. Wacht een paar minuten en selecteer  vervolgens regelmatig het pictogram Vernieuwen in de rechterbovenhoek van het deelvenster Gebruikers 4-account.

Op tijd ziet u het volgende:

- **De eigenschap Groepslidmaatschap** is bijgewerkt met de **groep** Verkoop.
- **Eigenschap productlicenties** bijgewerkt met de **Microsoft 365 E5-licentie.**

Zie deze artikelen voor het implementeren van dynamisch groepslidmaatschap en automatische licenties in productie:

- [Groepslicenties in Azure Active Directory](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Dynamische groepen in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Routekaart voor identiteit](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Microsoft 365 enterprise-documentatie](/microsoft-365-enterprise/)