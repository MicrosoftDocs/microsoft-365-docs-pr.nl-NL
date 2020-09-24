---
title: Een sjabloon maken en gebruiken om gebruikers toe te voegen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
- MET150
- MOE150
description: U kunt een sjabloon maken en gebruiken om tijd te besparen en instellingen te normaliseren wanneer u meerdere gebruikers toevoegt.
ms.openlocfilehash: 92d3bd68a57291586da27eb2d578a26c53d20d78
ms.sourcegitcommit: 1522a6471e0c5254a6d0f592e1f4dfacd1dd473a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/24/2020
ms.locfileid: "48245855"
---
# <a name="create-and-use-a-template-to-add-users"></a>Een sjabloon maken en gebruiken om gebruikers toe te voegen

U kunt een sjabloon maken en gebruiken om tijd te besparen en instellingen te normaliseren wanneer u meerdere gebruikers toevoegt. Sjablonen zijn vooral handig als u gebruikers hebt met een groot aantal gemeenschappelijke eigenschappen, zoals de gebruikers die dezelfde rol hebben en op dezelfde locatie werken en de personen die dezelfde software nodig hebben. U hebt bijvoorbeeld een team van ondersteuningstechnici die in hetzelfde kantoor werken.  

## <a name="create-a-template"></a>Een sjabloon maken

Sjablonen zijn gemakkelijk te maken &mdash; u kunt **gebruikers**  >  **Active users**  >  **sjablonen**van gebruikers selecteren en vervolgens **een sjabloon toevoegen** aan de vervolgkeuzelijst selecteren, of u kunt een nieuwe gebruiker toevoegen en wanneer u klaar bent, kunt u het item opslaan als een sjabloon.

Wanneer u een sjabloon maakt na het toevoegen van een gebruiker, worden de waarden die u hebt gekozen voor de volgende instellingen opgeslagen in de sjabloon:

- Domain name
- Keuze van wachtwoordinstellingen: u kunt ervoor kiezen om wachtwoorden te maken of deze automatisch te laten genereren
- Eenmalige wachtwoord keuze: u kunt ervoor zorgen dat de gebruiker een nieuw wachtwoord moet maken na de eerste keer aanmelden
- Locatie van licentie
- Licentie keuzes
- Toepassingsopties
- Rol
- Meeste profielinformatie, zoals het **taak profiel**, de **afdeling**, het **Office**- **telefoonnummer**en het **adres** 

De volgende informatie is specifiek voor de gebruiker en wordt niet opgeslagen in de sjabloon:

- Voor-en achternaam
- Weergavenaam
- Gebruikersnaam
- Het wachtwoord in het e-mailbericht en de e-mail waarnaar het wachtwoord wordt verzonden, verzenden
- Mobiel telefoonnummer

Als u geen gegevens invoert voor een instelling in een sectie, wordt deze waarde leeg en wordt deze instelling niet weergegeven in de sjabloon. Als u bijvoorbeeld de **functie** leeg laat wanneer u de sjabloon controleert en wanneer u de sjabloon gebruikt, wordt de **functie** helemaal niet weergegeven. Als u alle instellingen voor de **profiel** sectie leeg laat, wordt in de sectie **profiel** de **waarde geen** weergegeven die u hebt opgegeven in de uiteindelijke sjabloon.

Wanneer u een sjabloon maakt door de optie **een sjabloon toevoegen** te selecteren, kunt u kiezen welke waarden u wilt invullen. Als u niets hebt ingevuld, wordt dit weergegeven als **geen** van de sjablonen.

## <a name="use-a-template-to-add-a-user"></a>Een sjabloon gebruiken om een gebruiker toe te voegen

Een bestaande sjabloon gebruiken om een gebruiker toe te voegen:

1. Selecteer **gebruikers**  >  **actieve gebruikers**in het Beheercentrum.

2. Selecteer **gebruikerssjablonen**en selecteer vervolgens een sjabloon in de vervolgkeuzelijst. (De lijst bevat alleen de sjablonen die u hebt gemaakt, niet de sjablonen die zijn gemaakt door andere beheerders.)

 > [!NOTE]
 > U kunt ook een sjabloon gebruiken om een gebruiker toe te voegen door **gebruikerssjablonen**te selecteren  >  ,**sjablonen**te selecteren, een sjabloon te selecteren en vervolgens **sjabloon gebruiken**te kiezen.

3. Voer de stappen uit om een gebruiker te maken van de sjabloon die u hebt geselecteerd.

> [!NOTE]
> Als u niet over voldoende licenties beschikt voor een gebruiker die u toevoegt en uw betalingsgegevens beschikbaar zijn, trachten we een andere licentie te kopen met uw bestaande betaalgegevens. Als uw betalingsinformatie niet beschikbaar is, wordt de gebruiker gemaakt als een gebruiker zonder licentie.

## <a name="manage-templates"></a>Sjablonen beheren

U kunt eenvoudig sjablonen die u niet meer nodig hebt, verwijderen en nieuwe sjablonen toevoegen. Een sjabloon verwijderen:

1. Selecteer **gebruikers**  >  **actieve gebruikers**in het Beheercentrum.

2. Selecteer **sjablonen**en selecteer vervolgens **sjablonen beheren** in de vervolgkeuzelijst.

3. Er verschijnt een lijst met sjablonen. U kunt op een van de volgende manieren een sjabloon verwijderen:
    - Selecteer een of meer sjablonen en selecteer vervolgens **verwijderen**. 
    - Selecteer de drie puntjes rechts van de naam van de sjabloon en selecteer vervolgens **verwijderen**.
    - Selecteer de naam van de sjabloon. Wanneer de sjabloon Details aan de rechterkant van het scherm worden weergegeven, selecteert u **sjabloon verwijderen**.

## <a name="related-articles"></a>Verwante artikelen

[Gebruikers toevoegen en licenties toewijzen](add-users.md)

[Een voormalige werknemer verwijderen uit Microsoft 365](remove-former-employee.md)
  
