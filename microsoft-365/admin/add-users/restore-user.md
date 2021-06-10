---
title: Een gebruiker herstellen
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: Binnen 30 dagen na het verwijderen van een gebruikersaccount kunt u het account en alle gegevens herstellen en kan de gebruiker zich aanmelden met hetzelfde account.
ms.openlocfilehash: f849fe8e403aa9a72eccb4dd65665ec9f33618d1
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779648"
---
# <a name="restore-a-user"></a>Een gebruiker herstellen
   
Wanneer u een gebruikersaccount binnen 30 dagen na verwijderen herstelt, worden het account en alle bijbehorende gegevens hersteld. De gebruiker kan zich met hetzelfde werk- of schoolaccount aanmelden. Het postvak wordt volledig hersteld. [Neem contact met ons op](../../business-video/get-help-support.md) als u wilt weten na hoeveel dagen een specifiek gebruikersaccount niet meer kan worden hersteld.
  
Hier zijn een paar tips:
  
- Zorg ervoor dat licenties beschikbaar zijn om toe te wijzen aan het account.
    
- Als uw bedrijf Active Directory gebruikt voor instrutcions bij het herstellen van een gebruikersaccount, zie Hoe u problemen kunt oplossen met verwijderde gebruikersaccounts [in](/office365/troubleshoot/active-directory/restore-deleted-user-accounts)Office 365. 
    
## <a name="restore-one-or-more-user-accounts"></a>Een of meer gebruikersaccounts herstellen

U moet een globale beheerder Microsoft 365 beheerder van gebruikersbeheer zijn om deze stappen uit te voeren. 

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">verwijderde gebruikers.</a>

2. Selecteer **op de pagina** Verwijderde gebruikers de namen van de gebruikers die u wilt terugzetten en selecteer vervolgens **Herstellen.**
    
3. Volg de aanwijzingen om hun wachtwoord in te stellen en selecteer vervolgens **Herstellen.**
    
4. Als de gebruiker is hersteld, selecteert u **E-mail verzenden en sluiten.** Zie onderstaande instructies voor het herstellen van deze accounts als u te maken krijgt met een tegenstrijdigheid in de namen of proxyadressen.
    
Nadat u een gebruiker hebt hersteld, moet u ervoor zorgen dat u hen op de hoogte stelt dat hun wachtwoord is gewijzigd en dat u deze opvolgt.
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>Een gebruiker met een gebruikersnaamconflict herstellen

Een gebruikersnaamconflict doet zich voor wanneer u een gebruikersaccount verwijdert, een nieuw gebruikersaccount met dezelfde gebruikersnaam maakt (voor dezelfde gebruiker of voor een andere gebruiker met een soortgelijke naam) en daarna het verwijderde account wilt herstellen.
  
U kunt dit oplossen door het actieve gebruikersaccount te vervangen door het account dat u herstelt. U kunt ook een andere gebruikersnaam toewijzen aan het account dat u herstelt, zodat er niet twee accounts met dezelfde gebruikersnaam zijn. Hierna ziet u de stappen.

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">verwijderde gebruikers.</a>
  
2. Selecteer **op de pagina** Verwijderde gebruikers de namen van de gebruikers die u wilt herstellen en selecteer vervolgens **Herstellen.**
    
    > [!NOTE]
    > Als twee of meer gebruikers niet kunnen worden hersteld, wordt in een foutbericht aangegeven dat de herstelbewerking voor sommige gebruikers is mislukt. Kijk in het logbestand welke gebruikers niet zijn hersteld en herstel die accounts een voor een. 
  
3. Volg de aanwijzingen om het wachtwoord in te stellen en selecteer **Herstellen.**
    
4. In een bericht wordt aangegeven dat er een probleem is opgetreden bij het herstellen van het account. Voer een van de volgende handelingen uit:
    
  - Annuleer het herstellen en geef de huidige actieve gebruiker een andere naam. Probeer vervolgens opnieuw te herstellen.
    
  - OF typ een nieuw primair e-mailadres voor de gebruiker en selecteer **Herstellen.**
    
5. Controleer het resultaat en selecteer vervolgens **Sluiten**.
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>Een gebruiker met een proxyadresconflict herstellen

Een proxy-adresconflict doet zich voor wanneer u een gebruikersaccount verwijdert dat een proxyadres bevat, hetzelfde proxyadres toewijst aan een ander account en daarna het verwijderde account wilt herstellen. Voer de onderstaande stappen uit om dit probleem op te lossen.
  
Hiervoor moet [u beheerdersmachtigingen](about-admin-roles.md) Microsoft 365. 

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">verwijderde gebruikers.</a>

2. Selecteer op de pagina **Verwijderde gebruikers** de gebruikers die u wilt herstellen en selecteer vervolgens **Herstellen**. 
    
3. Volg op **de** pagina Herstellen de instructies om het wachtwoord in te stellen en selecteer **Herstellen.** Alle conflicterende proxyadressen worden automatisch verwijderd van de gebruiker die u herstelt.
    
4. Controleer het resultaat en selecteer vervolgens **Sluiten**.

## <a name="related-content"></a>Verwante onderwerpen

[Een gebruiker verwijderen](delete-a-user.md) (artikel)\
[Beheerdersrollen toewijzen](assign-admin-roles.md) (video)\
[Licenties toewijzen aan gebruikers](../manage/assign-licenses-to-users.md) (artikel)
