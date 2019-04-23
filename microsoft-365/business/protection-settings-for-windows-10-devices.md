---
title: Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Informatie over het maken van een beleid voor het beheer van app en werkbestanden op Windows 10-apparaten te beschermen.
ms.openlocfilehash: 289c6a74f6ccb53f6a833612a7b4a5bcddd3ea56
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278161"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a>Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten

## <a name="create-an-app-management-policy-for-windows-10"></a>Beleid voor app-beheer maken voor Windows 10

Als uw gebruikers persoonlijke Windows 10-apparaten gebruiken voor hun werk, kunt u de gegevens op die apparaten ook beschermen.
  
1. Het aanmelden bij [admin center](https://go.microsoft.com/fwlink/p/?linkid=837890) met de globale Administrator-referenties. Kies de tegel **Beheerder** om naar het beheercentrum te gaan. 
    
2. Kies op de Linkernavigatie **apparaten** \> **beleid** \> **toevoegen**.

3. Voer in het deelvenster **Beleid toevoegen** een unieke naam in voor dit beleid. 
    
4. Kies onder **Type beleid** de optie **Toepassingsbeheer voor Windows 10**.
    
5. Under ** Device type **, choose either **Personal** or **Company Owned**.
    
6. De optie **Werkbestanden versleutelen** is automatisch ingeschakeld. 
    
7. Stel **Voorkomen dat gebruikers bedrijfsgegevens kopiëren naar persoonlijke bestanden en afdwingen dat werkbestanden worden opgeslagen in OneDrive voor Bedrijven** in op **Aan** als u niet wilt dat de gebruikers werkbestanden opslaan op hun pc. 
    
8. Vouw de **beheren hoe gebruikers toegang kunnen krijgen tot Office-bestanden op apparaten** \> de gewenste instellingen te configureren. De **manier waarop gebruikers toegang kunnen krijgen tot Office-apparaten op mobiele apparaten beheren** is standaard **uitgeschakeld** , maar het is aanbevolen dat u **deze functie inschakelen** en accepteer de standaardwaarden. Zie de [beschikbare instellingen](#available-settings)voor meer informatie. 
    
    U kunt altijd de koppeling **Standaardwaarden herstellen** gebruiken om terug te keren naar de standaardinstelling. 
    
9. Vouw **Gegevens herstellen op Windows-apparaten** uit. U wordt aangeraden de optie **in te schakelen**.
    
    Voordat u naar de locatie van het certificaat voor de gegevensherstelagent kunt bladeren, moet u deze eerst maken. Zie [Een certificaat voor een gegevensherstelagent voor het Encrypting File System (EFS) maken en verifiëren](https://go.microsoft.com/fwlink/p/?linkid=853700) voor instructies.
    
    Werkbestanden worden standaard versleuteld met een geheime code die wordt opgeslagen op het apparaat en die gekoppeld is aan het profiel van de gebruiker. Alleen de gebruiker kan het bestand openen en ontsleutelen. Als een apparaat zoekraakt of als een gebruiker wordt verwijderd, kan een bestand echter blijven steken in versleutelde toestand. Het certificaat van de Gegevensherstelagent (DRA - Data Recovery Agent) kan door een beheerder worden gebruikt om het bestand te ontsleutelen.
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. Vouw **Meer netwerk- en cloudlocaties beveiligen** uit als u extra domeinen of SharePoint Online-locaties wilt toevoegen om ervoor te zorgen dat bestanden in alle weergegeven apps worden beveiligd. Als u meerdere items moet opgeven voor een veld, gebruikt u een puntkomma (;) tussen de items. 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Bepaal nu **Voor wie zijn deze instellingen?** Als u niet de standaardbeveiligingsgroep **Alle gebruikers** wilt gebruiken, kiest u **Wijzigen**, zoekt u de beveiligingsgroep die deze instellingen krijgt \> **Selecteren**.
    
12. Kies ten slotte **Toevoegen** om het beleid op te slaan en dit toe te wijzen aan apparaten. 
    
## <a name="available-settings"></a>Beschikbare instellingen

De volgende instellingen zijn beschikbaar om te beheren hoe gebruikers toegang hebben tot Office-werkbestanden.
  
Zie [Hoe beveiligingsfuncties in Microsoft 365 Business zijn toegewezen aan Intune-instellingen](map-protection-features-to-intune-settings.md) voor meer informatie.
  
|**Instelling**|**Beschrijving**|
|:-----|:-----|
|Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps  <br/> |Als deze instelling is **ingeschakeld**, moeten gebruikers een extra vorm van verificatie gebruiken, naast het verstrekken van gebruikersnaam en wachtwoord, voordat ze de Office-apps op hun mobiele apparaat kunnen gebruiken.  <br/> |
|Pincode opnieuw instellen wanneer het aanmelden ... keer mislukt  <br/> |Om te voorkomen dat een niet-geautoriseerde gebruiker een pincode kan raden, wordt de pincode opnieuw ingesteld na het aantal door u opgegeven verkeerde aanmeldpogingen.  <br/> |
|Vereisen dat gebruikers zich opnieuw aanmelden als Office-apps inactief zijn geweest gedurende  <br/> |Met deze instelling wordt bepaald hoelang gebruikers inactief kunnen zijn voordat hun wordt gevraagd zich opnieuw aan te melden.  <br/> |
   

