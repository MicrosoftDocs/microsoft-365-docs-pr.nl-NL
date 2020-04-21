---
title: Een gebruiker herstellen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: Meer informatie over het herstellen van verwijderde gebruikersaccounts en alle bijbehorende gegevens.
ms.openlocfilehash: 78766f1f6708665271361d542372aa945b0a7e29
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43624056"
---
# <a name="restore-a-user"></a>Een gebruiker herstellen
   
Wanneer u een gebruikersaccount binnen 30 dagen na verwijderen herstelt, worden het account en alle bijbehorende gegevens hersteld. De gebruiker kan zich met hetzelfde werk- of schoolaccount aanmelden. Het postvak wordt volledig hersteld. [Neem contact met ons op](../contact-support-for-business-products.md) als u wilt weten na hoeveel dagen een specifiek gebruikersaccount niet meer kan worden hersteld.
  
Hier zijn een paar tips:
  
- Controleer of er licenties beschikbaar zijn om aan het account toe te wijzen.
    
- Zie [Problemen met verwijderde gebruikersaccounts oplossen in Office 365](https://support.microsoft.com/kb/2619308) als uw bedrijf Active Directory gebruikt voor instructies over het herstellen van gebruikersaccounts. 
    
## <a name="restore-one-or-more-user-accounts"></a>Een of meer gebruikersaccounts herstellen

U moet een algemene beheerder of beheerder van het beheer van Microsoft 365 zijn om deze stappen uit te voeren. 
  
 
::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar **de** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Gebruikers verwijderde gebruikers.</a>

::: moniker-end

::: moniker range="o365-germany"

1. Ga naar het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=848041)en selecteer **Gebruikers** \> **verwijderde gebruikers**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga naar het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=850627)en selecteer **Gebruikers** \> **verwijderde gebruikers**.

::: moniker-end

2. Selecteer **op de** pagina Verwijderde gebruikers de namen van de gebruikers die u wilt herstellen en selecteer **Vervolgens Herstellen**.
    
 
3. Volg de aanwijzingen om hun wachtwoord in te stellen en selecteer **Herstellen**.
    
4. Als de gebruiker is hersteld, selecteert u **E-mail verzenden en sluiten**. Zie onderstaande instructies voor het herstellen van deze accounts als u te maken krijgt met een tegenstrijdigheid in de namen of proxyadressen.
    
Nadat u een gebruiker hebt hersteld, moet u deze laten weten dat hun wachtwoord is gewijzigd en dat u deze met hen opvolgt.
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>Een gebruiker met een gebruikersnaamconflict herstellen
<a name="RestoreUserNameConflict"> </a>

Een gebruikersnaamconflict doet zich voor wanneer u een gebruikersaccount verwijdert, een nieuw gebruikersaccount met dezelfde gebruikersnaam maakt (voor dezelfde gebruiker of voor een andere gebruiker met een soortgelijke naam) en daarna het verwijderde account wilt herstellen.
  
U kunt dit oplossen door het actieve gebruikersaccount te vervangen door het account dat u herstelt. U kunt ook een andere gebruikersnaam toewijzen aan het account dat u herstelt, zodat er niet twee accounts met dezelfde gebruikersnaam zijn. Hierna ziet u de stappen.
  

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar **de** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Gebruikers verwijderde gebruikers.</a>

::: moniker-end

::: moniker range="o365-germany"

1. Ga naar het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=848041)en selecteer **Gebruikers** \> **verwijderde gebruikers**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga naar het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=850627)en selecteer **Gebruikers** \> **verwijderde gebruikers**.

::: moniker-end

  
2. Selecteer **op de** pagina Verwijderde gebruikers de namen van de gebruikers die u wilt herstellen en selecteer **Vervolgens Herstellen**.
    
    > [!NOTE]
    > Als twee of meer gebruikers niet kunnen worden hersteld, wordt in een foutbericht aangegeven dat de herstelbewerking voor sommige gebruikers is mislukt. Kijk in het logbestand welke gebruikers niet zijn hersteld en herstel die accounts een voor een. 
  
3. Volg de aanwijzingen om het wachtwoord in te stellen en selecteer **Herstellen**.
    
4. In een bericht wordt aangegeven dat er een probleem is opgetreden bij het herstellen van het account. Voer een van de volgende handelingen uit:
    
  - Annuleer het herstellen en geef de huidige actieve gebruiker een andere naam. Probeer vervolgens opnieuw te herstellen.
    
  - OF, typ een nieuw primair e-mailadres voor de gebruiker en selecteer **Herstellen**.
    
5. Controleer het resultaat en selecteer vervolgens **Sluiten**.
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>Een gebruiker met een proxyadresconflict herstellen

Een proxy-adresconflict doet zich voor wanneer u een gebruikersaccount verwijdert dat een proxyadres bevat, hetzelfde proxyadres toewijst aan een ander account en daarna het verwijderde account wilt herstellen. Voer de onderstaande stappen uit om dit probleem op te lossen.
  
Hiervoor moet [u beheerdersmachtigingen](about-admin-roles.md) in Microsoft 365 hebben. 
  

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar **de** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Gebruikers verwijderde gebruikers.</a>

::: moniker-end

::: moniker range="o365-germany"

Ga naar het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=848041)en selecteer **Gebruikers** \> **verwijderde gebruikers**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga naar het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=850627)en selecteer **Gebruikers** \> **verwijderde gebruikers**.

::: moniker-end

2. Selecteer op de pagina **Verwijderde gebruikers** de gebruikers die u wilt herstellen en selecteer vervolgens **Herstellen**. 
    
3. Volg **op** de pagina Herstellen de instructies om het wachtwoord in te stellen en selecteer **Herstellen**. Alle conflicterende proxyadressen worden automatisch verwijderd van de gebruiker die u herstelt.
    
4. Controleer het resultaat en selecteer vervolgens **Sluiten**.

## <a name="related-articles"></a>Verwante artikelen

[Een gebruiker verwijderen](delete-a-user.md)
  
