---
title: Een sjabloon maken en gebruiken om gebruikers toe te voegen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
description: U kunt een sjabloon maken en gebruiken om tijd te besparen en instellingen te standaardiseren wanneer u meerdere gebruikers toevoegt.
ms.openlocfilehash: 3ce70f6d37036a2f71bdc2d41bfb5677a54b8db9
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579384"
---
# <a name="create-and-use-a-template-to-add-users"></a>Een sjabloon maken en gebruiken om gebruikers toe te voegen

U kunt een sjabloon maken en gebruiken om tijd te besparen en instellingen te standaardiseren wanneer u meerdere gebruikers toevoegt. Sjablonen zijn vooral handig als u gebruikers hebt die veel algemene eigenschappen delen, zoals gebruikers die dezelfde rol hebben en op dezelfde locatie werken en gebruikers die dezelfde software nodig hebben. U hebt bijvoorbeeld een team van ondersteuningstechnici die in hetzelfde kantoor werken.  

## <a name="create-a-template"></a>Een sjabloon maken

Sjablonen zijn eenvoudig te maken. U kunt Gebruikers actieve gebruikers gebruikerssjablonen selecteren en vervolgens Een sjabloon toevoegen selecteren in de vervolgkeuzelijst, of u kunt een nieuwe gebruiker toevoegen en wanneer u klaar bent, kunt u de vermelding opslaan als &mdash;   >    >  sjabloon. 

Wanneer u een sjabloon maakt nadat u een gebruiker hebt toegevoegd, worden de waarden die u voor de volgende instellingen kiest, opgeslagen in de sjabloon:

- Domain name
- Keuze voor wachtwoordinstellingen: u kunt ervoor kiezen wachtwoorden te maken of deze automatisch te laten genereren
- Een een time password choice: u kunt de gebruiker verplichten een nieuw wachtwoord te maken na de eerste aanmelding
- Licentielocatie
- Licentieopties
- Toepassingsopties
- Rol
- De meeste profielgegevens, zoals **Functieprofiel,** **Afdeling,** **Office,** **Office telefoon** en **Adres van straat** 

De volgende informatie is specifiek voor de gebruiker en wordt niet opgeslagen in de sjabloon:

- Voor- en achternaam
- Weergavenaam
- Gebruikersnaam
- Keuze voor het verzenden van het wachtwoord in e-mail en naar wie het wachtwoord-e-mailbericht wordt verzonden
- Mobiel telefoonnummer

Als u ervoor kiest geen gegevens in te voeren voor een instelling in een sectie, is deze waarde leeg en wordt deze instelling niet weergegeven in de sjabloon. Als u bijvoorbeeld de functie **functie** leeg laat, wanneer u de sjabloon bekijkt en de sjabloon **gebruikt,** wordt de functie helemaal niet weergegeven. Als u alle **profielsectie-instellingen**  leeg laat, wordt in de sectie Profiel **Geen** weergegeven in de uiteindelijke sjabloon.

Wanneer u een sjabloon maakt door de optie Een sjabloon toevoegen **te** selecteren, kunt u kiezen welke waarden u wilt voltooien. Alles wat leeg blijft, wordt weergegeven als **Geen in** de sjabloon.

## <a name="use-a-template-to-add-a-user"></a>Een sjabloon gebruiken om een gebruiker toe te voegen

Een bestaande sjabloon gebruiken om een gebruiker toe te voegen:

1. Selecteer in het beheercentrum **Gebruikers**  >  **Actieve gebruikers**.

2. Selecteer **Gebruikerssjablonen** en selecteer vervolgens een sjabloon in de vervolgkeuzelijst. (De lijst bevat alleen de sjablonen die u hebt gemaakt, niet de sjablonen die door andere beheerders zijn gemaakt.)

   > [!NOTE]
   > U kunt ook een sjabloon gebruiken om een gebruiker toe te voegen door Gebruikerssjablonen te selecteren Sjablonen beheren, een sjabloon te selecteren en  >  vervolgens Sjabloon gebruiken **te selecteren.**

3. Volg de stappen om een gebruiker te maken op basis van de sjabloon die u hebt geselecteerd.

   > [!NOTE]
   > Als u onvoldoende licenties beschikbaar hebt voor een gebruiker die u toevoegt en uw betalingsgegevens beschikbaar zijn, proberen we een andere licentie te kopen met uw bestaande betalingsgegevens. Als uw betalingsgegevens niet beschikbaar zijn, wordt de gebruiker gemaakt als gebruiker zonder toestemming.

## <a name="manage-templates"></a>Sjablonen beheren

U kunt alleen sjablonen verwijderen die u niet meer nodig hebt en nieuwe sjablonen toevoegen. Een sjabloon verwijderen:

1. Selecteer in het beheercentrum **Gebruikers**  >  **Actieve gebruikers**.

2. Selecteer **Sjablonen** en selecteer **vervolgens sjablonen beheren** in de vervolgkeuzelijst.

3. Er wordt een lijst met sjablonen weergegeven. U kunt een sjabloon op een van de volgende opties verwijderen:
    - Selecteer een of meer sjablonen en selecteer **vervolgens Verwijderen.** 
    - Selecteer de drie puntjes rechts van de naam van de sjabloon en selecteer **vervolgens Verwijderen.**
    - Selecteer de naam van de sjabloon. Wanneer de sjabloondetails aan de rechterkant van het scherm worden weergegeven, selecteert u **Sjabloon verwijderen.**

## <a name="related-articles"></a>Aanverwante artikelen

[Tegelijkertijd gebruikers toevoegen en licenties toewijzen](add-users.md)

[Een voormalige werknemer verwijderen uit Microsoft 365](remove-former-employee.md)
  
