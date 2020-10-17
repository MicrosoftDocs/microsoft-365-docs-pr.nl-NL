---
title: Licentie en groepslidmaatschap voor uw Microsoft 365 voor Enterprise testomgeving automatiseren
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
description: Configureer licenties voor op groepen gebaseerde licenties en groepslidmaatschap voor dynamische groepen in uw Microsoft 365 voor Enterprise testomgeving.
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487574"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>Licentie en groepslidmaatschap voor uw Microsoft 365 voor Enterprise testomgeving automatiseren

*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*

Voor licenties op basis van een groep worden automatisch licenties toegewezen of verwijderd voor een gebruikersaccount op basis van groepslidmaatschap. Groepslidmaatschap voor dynamische groepen Hiermee voegt u leden toe of verwijdert u deze aan een groep op basis van de eigenschappen van gebruikersaccounts, zoals **afdeling** of **land**. In dit artikel wordt u stapsgewijs begeleid bij het toevoegen en verwijderen van groepsleden in uw Microsoft 365 voor Enterprise-testomgeving.

Het instellen van automatische licentieverlening en dynamisch groepslidmaatschap in uw Microsoft 365 voor Enterprise-testomgeving bestaat uit twee fasen:

- [Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: dynamisch groepslidmaatschap en automatische licentie configureren en testen](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken

Als u de geautomatiseerde licentie en groepslidmaatschap op een zeer lichte manier wilt testen aan de minimumvereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Als u automatische licentieverlening en groepslidmaatschap in een gesimuleerde onderneming wilt testen, volgt u de instructies in [Pass-Through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Voor het testen van geautomatiseerde licentie-en groepslidmaatschappen is de gesimuleerde Enterprise testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest. Dit wordt hier als optie geboden, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en experimenteert in een omgeving die een typische organisatie voorstelt.
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fase 2: dynamisch groepslidmaatschap en automatische licentie configureren en testen

Eerst maakt u een nieuwe groep genaamd verkoop en voegt u een regel voor dynamische groepslidmaatschappen toe, zodat gebruikersaccounts waarbij de **afdeling** is ingesteld op **verkoop** automatisch worden toegevoegd aan de verkoopgroep.

1. Meld u in een privé-exemplaar van uw internetbrowser aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) met het account van de globale beheerder van uw abonnement op microsoft 365 E5-test lab.
2. Ga op een apart tabblad van uw browser naar de Azure-Portal op [https://portal.azure.com](https://portal.azure.com) .
3. Voer in het vak Zoeken in de Azure-Portal **groepen** in en selecteer **groepen**.
4. Selecteer in het deelvenster **alle groepen** de optie **nieuwe groep**.
5. Selecteer bij **type groep**de optie **Microsoft 365**.
6. Voer in **groepsnaam** **verkopen**in.
7. Selecteer **dynamische gebruiker**bij **type lidmaatschap**.
8. Selecteer **dynamische gebruikers leden**.
9. In het deelvenster **dynamische lidmaatschapsregels** : 
   - Selecteer de eigenschap **afdeling** .
   - Selecteer de operator **gelijkteken** .
   - Voer in het vak **waarde de waarde** **verkoop**in.
10. Kies **Opslaan**.
11. Selecteer **Maken**. 

Vervolgens configureert u de groep verkoop, zodat leden automatisch de Microsoft 365 E5-licentie toewijzen.

1. Selecteer de groep **verkoop** en selecteer vervolgens **licenties**.
2. Selecteer in het deelvenster **licentietoewijzingen bijwerken** de optie **Microsoft 365 E5**en selecteer vervolgens **Opslaan**.
3. Sluit het tabblad Azure Portal in de browser.

Test vervolgens dynamisch groepslidmaatschap en automatische licentieverlening van de account gebruiker 4:

1. Selecteer op het tabblad **Start van Microsoft Office** in uw browser de optie **beheerder**.
2. Selecteer **actieve gebruikers**op het tabblad **Microsoft 365-Beheercentrum** .
3. Selecteer het account van de **gebruiker 4** op de pagina **actieve gebruikers** .
4. Selecteer in het deelvenster **gebruiker 4** de optie **bewerken** voor **product licenties**.
5. In het deelvenster **product licenties** schakelt u de **Microsoft 365 E5** -licentie uit **en selecteert u**vervolgens  >  **sluiten**.
6. Ga naar de eigenschappen van de account van de gebruiker 4 en zorg dat er geen productlicenties zijn toegewezen en dat er geen groepslidmaatschappen zijn.
7. Selecteer voor **contact gegevens**de optie **bewerken**.
8. Selecteer in het deelvenster **contactgegevens bewerken** de optie **contactgegevens**.
9. Voer in het vak **afdeling** de optie **verkoop**in **en selecteer vervolgens**  >  **sluiten**.
10. Wacht een paar minuten en selecteer vervolgens periodiek het pictogram **vernieuwen** in de rechterbovenhoek van het deelvenster account van gebruiker 4.

Voor tijd ziet u het volgende:

- De eigenschap **groepslidmaatschappen** bijgewerkt met de groep **verkoop** .
- Eigenschap **product licenties** bijgewerkt met de **Microsoft 365 E5** -licentie.

Zie de volgende artikelen voor meer informatie over het implementeren van dynamische groepslidmaatschappen en automatische licentieverlening in de productie:

- [Op groepen gebaseerde licentieverlening in azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Dynamische groepen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Identiteitskaart](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
