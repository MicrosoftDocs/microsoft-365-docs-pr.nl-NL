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
ms.openlocfilehash: a25a47b81ce8c119e7aeb44660af32bb9cafb08a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685556"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>Licentie en groepslidmaatschap voor uw Microsoft 365 voor Enterprise testomgeving automatiseren

*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*

Voor licenties op basis van een groep worden automatisch licenties toegewezen of verwijderd voor een gebruikersaccount op basis van groepslidmaatschap. Groepslidmaatschap voor dynamische groepen Hiermee voegt u leden toe of verwijdert u deze aan een groep op basis van de eigenschappen van gebruikersaccounts, zoals afdeling of land. In dit artikel wordt u stapsgewijs begeleid bij het uitvoeren van de testomgeving van Microsoft 365 voor bedrijven.

Voor het instellen van automatische licentieverlening en dynamisch groepslidmaatschap in uw Microsoft 365 voor Enterprise testomgeving bestaan twee fasen:

1. Maak de testomgeving Microsoft 365 for Enterprise.
2. Dynamische groepslidmaatschappen en automatische licentieverlening configureren en testen.

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klik op [Hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken

Als u alleen de automatische licentieverlening en groepslidmaatschap op een lichte manier wilt testen aan de minimumvereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Als u automatische licentieverlening en groepslidmaatschap in een gesimuleerde onderneming wilt testen, volgt u de instructies in [Pass-Through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Voor het testen van de geautomatiseerde licentie-en groepslidmaatschappen is de gesimuleerde Enterprise testomgeving niet vereist, waaronder een gesimuleerd intranet dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest. U kunt dit hier opgeven als optie, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en experimenteert in een omgeving die een typische organisatie voorstelt. 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fase 2: dynamisch groepslidmaatschap en automatische licentie configureren en testen

Eerst maakt u een nieuwe verkoopgroep en voegt u een regel voor dynamische groepslidmaatschappen toe, zodat gebruikersaccounts waarbij de afdeling is ingesteld op verkoop, automatisch worden toegevoegd aan de groep verkopen.

1. Meld u met een persoonlijk exemplaar van uw Internet browser aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) met het account van de globale beheerder van uw abonnement op microsoft 365 E5-test lab.
2. Ga op een apart tabblad van uw browser naar de Azure-Portal op [https://portal.azure.com](https://portal.azure.com) .
3. Typ in het dialoogvenster van Azure Portal **groepen** in het zoekvak en klik vervolgens op **groepen**.
4. Klik in het deelvenster **alle groepen** op **nieuwe groep**.
5. Selecteer bij **type groep**de optie **Microsoft 365**.
6. Typ in **groepsnaam** **verkopen**.
7. Selecteer **dynamische gebruiker**bij **type lidmaatschap**.
8. Klik op **dynamische gebruikers leden**.
9. In het deelvenster **dynamische lidmaatschapsregels** : 
   - Selecteer de eigenschap **afdeling** .
   - Selecteer de operator **gelijkteken** .
   - Typ **verkoop** in **waarde**.
10. Klik op **Opslaan**.
11. Klik op **Maken**.

Vervolgens configureert u de groep verkoop, zodat leden automatisch de Microsoft 365 E5-licentie toewijzen.

1. Klik op de groep **verkoop** en klik vervolgens op **licenties**.
2. Selecteer in het deelvenster **licentietoewijzingen bijwerken** de optie **Microsoft 365 E5**en klik vervolgens op **Opslaan**.
3. Sluit het tabblad Microsoft Azure-portal in uw browser.

Test vervolgens dynamisch groepslidmaatschap en automatische licentieverlening op de account gebruiker 4. 

1. Klik op het tabblad **Start van Microsoft Office** in uw browser op **beheerder**.
2. Klik op het tabblad **Microsoft 365-Beheercentrum** op **actieve gebruikers**.
3. Klik op de pagina **actieve gebruikers** op de account **gebruiker 4** .
4. Klik in het deelvenster **gebruiker 4** op **bewerken** voor **product licenties**.
5. Schakel in het deelvenster **product licenties** de **Microsoft 365 E5** -licentie uit en klik op **Opslaan > sluiten**.
6. Ga naar de eigenschappen van de account van de gebruiker 4 en zorg dat er geen productlicenties zijn toegewezen en dat er geen groepslidmaatschappen zijn.
7. Klik op **bewerken** voor **contact gegevens**.
8. Klik in het deelvenster **contactgegevens bewerken** op **contactgegevens**.
9. In het veld **afdeling** typt u **verkoop**en klikt u op **Opslaan > sluiten**.
10. Wacht een paar minuten en klik vervolgens regelmatig op het pictogram Vernieuwen in de rechterbovenhoek van het deelvenster account van gebruiker 4. 

U ziet nu het volgende:

- De eigenschap **groepslidmaatschappen** bijgewerkt met de groep **verkoop** .
- Eigenschap **product licenties** bijgewerkt met de **Microsoft 365 E5** -licentie.

Zie de volgende artikelen voor meer informatie over het implementeren van dynamische groepslidmaatschappen en automatische licentieverlening in de productie:

- TBD AANKOPPELEN
- TBD AANKOPPELEN

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Identiteitskaart](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
