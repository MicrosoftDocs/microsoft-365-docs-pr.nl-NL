---
title: Een sjabloon maken en gebruiken om gebruikers toe te voegen
f1.keywords:
- NOCSH
ms.author: v-sharos
author: shars
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
description: U een sjabloon maken en gebruiken om tijd te besparen en instellingen te standaardiseren wanneer u meerdere gebruikers toevoegt.
ms.openlocfilehash: 3173d28f27acdf1a084137d36cd71894e94e9547
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387223"
---
# <a name="create-and-use-a-template-to-add-users"></a>Een sjabloon maken en gebruiken om gebruikers toe te voegen

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

U een sjabloon maken en gebruiken om tijd te besparen en instellingen te standaardiseren wanneer u meerdere gebruikers toevoegt. Sjablonen zijn vooral handig als u gebruikers hebt die veel algemene eigenschappen delen, zoals gebruikers die dezelfde rol hebben en op dezelfde locatie werken en degenen die dezelfde software nodig hebben. U hebt bijvoorbeeld een team van ondersteuningstechnici die in hetzelfde kantoor werken.  

## <a name="create-a-template"></a>Een sjabloon maken

Sjablonen zijn eenvoudig te maken &mdash; u **gebruikers**actieve gebruikers selecteren  >  **Active users**  >  **Gebruikerssjablonen**en vervolgens **een sjabloon toevoegen** in de vervolgkeuzelijst, of u een nieuwe gebruiker toevoegen en wanneer u klaar bent, hebt u de mogelijkheid om de vermelding als sjabloon op te slaan.

Wanneer u een sjabloon maakt nadat u een gebruiker hebt toegevoegd, worden de waarden die u kiest voor de volgende instellingen opgeslagen in de sjabloon:

- Domain name
- Keuze voor wachtwoordinstellingen: u ervoor kiezen om wachtwoorden te maken of deze automatisch te laten genereren
- Eenmalige wachtwoordkeuze: u van de gebruiker verlangen dat hij een nieuw wachtwoord maakt nadat hij zich eerst hebt aangemeld
- Licentielocatie
- Licentiekeuzes
- Toepassingsopties
- Rol
- De meeste profielinformatie, zoals **Functieprofiel**, **Afdeling,** **Bureau,** **Kantoortelefoon**en **Adres** 

De volgende informatie is gebruikersspecifiek en wordt niet opgeslagen in de sjabloon:

- Voor- en achternaam
- Weergavenaam
- Gebruikersnaam
- Keuze om het wachtwoord per e-mail te verzenden en naar wie de wachtwoorde-mail wordt verzonden
- Mobiel telefoonnummer

Als u ervoor kiest geen informatie in te voeren voor een instelling in een sectie, is die waarde leeg en wordt die instelling niet weergegeven in de sjabloon. Als u bijvoorbeeld **De functietitel** leeg laat, wanneer u uw sjabloon bekijkt en wanneer u uw sjabloon gebruikt, wordt **de functietitel** helemaal niet weergegeven. Als u alle instellingen van de **sectie Profiel** leeg laat, wordt in de sectie **Profiel** **geen weergegeven** in uw uiteindelijke sjabloon.

Wanneer u een sjabloon maakt door de optie **Een sjabloon toevoegen** te selecteren, u kiezen welke waarden u wilt voltooien. Alles wat leeg blijft, wordt weergegeven als **Geen** in de sjabloon.

## <a name="use-a-template-to-add-a-user"></a>Een sjabloon gebruiken om een gebruiker toe te voegen

Ga als lid van het werk om een bestaande sjabloon te gebruiken om een gebruiker toe te voegen:

1. Selecteer gebruikers actief **gebruikers**in het beheercentrum  >  **Active users**.

2. Selecteer **Gebruikerssjablonen**en selecteer vervolgens een sjabloon in de vervolgkeuzelijst. (De lijst bevat alleen de sjablonen die u hebt gemaakt, niet de sjablonen die door andere beheerders zijn gemaakt.)

 > [!NOTE]
 > U ook een sjabloon gebruiken om een gebruiker toe te voegen door **gebruikerssjablonen te**selecteren  >  **Sjablonen beheren,** een sjabloon te selecteren en vervolgens **sjabloon gebruiken**te selecteren.

3. Volg de stappen om een gebruiker te maken op basis van de geselecteerde sjabloon.

> [!NOTE]
> Als er onvoldoende licenties beschikbaar zijn voor een gebruiker die u toevoegt en uw betalingsgegevens beschikbaar zijn, proberen we een andere licentie te kopen met behulp van uw bestaande betalingsgegevens. Als uw betalingsgegevens niet beschikbaar zijn, wordt de gebruiker gemaakt als gebruiker zonder licentie.

## <a name="manage-templates"></a>Sjablonen beheren

U eenvoudig sjablonen verwijderen die u niet meer nodig hebt en nieuwe sjablonen toevoegen. Een sjabloon verwijderen:

1. Selecteer gebruikers actief **gebruikers**in het beheercentrum  >  **Active users**.

2. Selecteer **Sjablonen**en selecteer **Vervolgens Sjablonen beheren** in de vervolgkeuzelijst.

3. Er verschijnt een lijst met sjablonen. U een sjabloon verwijderen door een van de volgende handelingen uit te voeren:
    - Selecteer een of meer sjablonen en selecteer **Verwijderen**. 
    - Selecteer de drie puntjes rechts van de naam van de sjabloon en selecteer **Verwijderen**.
    - Selecteer de naam van de sjabloon. Wanneer de sjabloondetails aan de rechterkant van het scherm worden weergegeven, selecteert u **Sjabloon verwijderen**.

## <a name="related-articles"></a>Verwante artikelen

[Gebruikers afzonderlijk of in bulk toevoegen aan Microsoft 365](add-users.md)

[Een voormalige werknemer verwijderen uit Microsoft 365](remove-former-employee.md)
  
