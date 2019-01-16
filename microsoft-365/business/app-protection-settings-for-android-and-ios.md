---
title: Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Informatie over het maken, bewerken, of verwijderen van een beleid voor het beheer van app en werkbestanden op Android of iOS apparaten te beschermen.
ms.openlocfilehash: ed03227496120369b94bf2396974eebfd7798678
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "26983662"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten

## <a name="create-an-app-management-policy"></a>Beleid voor app-beheer maken

1. Meld u aan bij [Microsoft 365 Business](https://portal.office.com) met globale-beheerdersreferenties. 
    
2. Kies in het beheercentrum op de kaart **Apparaatbeleid** de optie **Beleid toevoegen**.
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. Voer in het deelvenster **Beleid toevoegen** een unieke naam in voor dit beleid. 
    
4. Kies onder **Type beleid** de optie **Toepassingsbeheer voor Android** of **Toepassingsbeheer voor iOS**, afhankelijk van de set beleidsregels die u wilt maken. 
    
5. Vouw **Werkbestanden beveiligen bij verlies of diefstal van apparaten** en **Beheren hoe gebruikers Office-bestanden op mobiele apparaten openen** uit \> configureer de instellingen op de gewenste manier. De optie **Beheren hoe gebruikers Office-bestanden op mobiele apparaten openen** is standaard **Uit**. U wordt echter aangeraden de optie in te stellen op **Aan** en de standaardwaarden te accepteren. Zie [Beschikbare instellingen](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings) voor meer informatie. 
    
    U kunt altijd de koppeling **Standaardwaarden herstellen** gebruiken om terug te keren naar de standaardinstelling. 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. Bepaal nu **Voor wie zijn deze instellingen?** Als u niet de standaardbeveiligingsgroep **Alle gebruikers** wilt gebruiken, kiest u **Wijzigen**, zoekt u de beveiligingsgroep die deze instellingen krijgt \> **Selecteren**.
    
7. Kies ten slotte **Gereed** om het beleid op te slaan en dit toe te wijzen aan apparaten. 
    
## <a name="edit-an-app-management-policy"></a>Beleid voor app-beheer bewerken

1. Kies op de kaart **beleid** **beleid bewerken**.
    
2. Kies in het deelvenster **Beleid bewerken** het beleid dat u wilt wijzigen 
    
3. Kies **Bewerken** naast elke instelling om de waarden in het beleid te wijzigen. Wanneer u een waarde wijzigt, wordt dit automatisch opgeslagen in het beleid 
    
4. Wanneer u klaar bent, sluit u het deelvenster **Beleid bewerken**. 
    
## <a name="delete-an-app-management-policy"></a>Beleid voor app-beheer verwijderen

1. Kies op de kaart **Beleid** de optie **Beleid verwijderen**.
    
2. Kies het beleid dat u wilt verwijderen in het deelvenster **beleid verwijderen** \> **selecteren**en vervolgens **bevestigen** verwijderen van het beleid of het beleid dat u hebt gekozen. 
    
## <a name="available-settings"></a>Beschikbare instellingen

De volgende tabellen bevatten gedetailleerde informatie over de beschikbare instellingen voor het beveiligen van werkbestanden op apparaten en de instellingen waarmee wordt bepaald hoe gebruikers toegang hebben tot Office-bestanden op hun mobiele apparaten.
  
 Zie [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) (Hoe beveiligingsfuncties in Microsoft 365 Business zijn toegewezen aan Intune-instellingen) voor meer informatie. 
  
### <a name="settings-that-protect-work-files"></a>Instellingen voor het beveiligen van werkbestanden

De volgende instellingen zijn beschikbaar voor het beveiligen van werkbestanden bij verlies of diefstal van het apparaat van een gebruiker:
  
|||
|:-----|:-----|
|Instelling  <br/> |Beschrijving  <br/> |
|Werkbestanden van een inactief apparaat verwijderen na zoveel dagen  <br/> |Als een apparaat het aantal dagen dat u hier opgeeft, niet wordt gebruikt, worden werkbestanden die op het apparaat zijn opgeslagen, automatisch verwijderd.  <br/> |
|Afdwingen dat gebruikers alle werkbestanden opslaan in OneDrive voor Bedrijven  <br/> |Als deze instelling is **ingeschakeld**, is OneDrive voor Bedrijven de enige beschikbare opslaglocatie voor werkbestanden.  <br/> |
|Werkbestanden versleutelen  <br/> |Laat deze instelling **ingeschakeld**, zodat werkbestanden worden beveiligd met versleuteling. Zelfs bij verlies of diefstal van het apparaat kan niemand de bedrijfsgegevens lezen.  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Instellingen waarmee wordt bepaald hoe gebruikers toegang hebben tot Office-bestanden op mobiele apparaten

De volgende instellingen zijn beschikbaar om te beheren hoe gebruikers toegang hebben tot Office-werkbestanden:
  
|||
|:-----|:-----|
|Instelling  <br/> |Beschrijving  <br/> |
|Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps  <br/> |Als deze instelling is **ingeschakeld**, moeten gebruikers een extra vorm van verificatie gebruiken, naast het verstrekken van gebruikersnaam en wachtwoord, voordat ze de Office-apps op hun mobiele apparaat kunnen gebruiken.  <br/> |
|Pincode opnieuw instellen wanneer het aanmelden ... keer mislukt  <br/> |Om te voorkomen dat een niet-geautoriseerde gebruiker een pincode kan raden, wordt de pincode opnieuw ingesteld na het aantal door u opgegeven verkeerde aanmeldpogingen.  <br/> |
|Vereisen dat gebruikers zich opnieuw aanmelden als Office-apps inactief zijn geweest gedurende  <br/> |Met deze instelling wordt bepaald hoelang gebruikers inactief kunnen zijn voordat hun wordt gevraagd zich opnieuw aan te melden.  <br/> |
|Toegang weigeren tot werkbestanden op jailbroken of geroote apparaten  <br/> |Slimme gebruikers hebben mogelijk een jailbroken of geroot apparaat. Dit betekent dat de gebruiker het besturingssysteem kan aanpassen, waardoor het apparaat gevoeliger kan worden voor malware. Deze apparaten worden geblokkeerd wanneer deze instelling **Aan** is.  <br/> |
|Gebruikers toestaan om inhoud uit Office-apps te kopiëren naar persoonlijke apps  <br/> |Wij staan toe dat dit standaard, maar als de instelling **ingeschakeld is**, de gebruiker informatie in een werkbestand kan kopiëren naar een bestand met persoonlijke. Als de instelling **uitgeschakeld is**, wordt de gebruiker om gegevens te kopiëren van een werk-rekening in een persoonlijke account of een persoonlijke app kan zijn.<br/> |
   

  

