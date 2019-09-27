---
title: Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Informatie over het maken, bewerken of verwijderen van een app-beheerbeleid en het beveiligen van werkbestanden op Android-of iOS-apparaten.
ms.openlocfilehash: 68a338ffb4f9b6cab16c677f80d27481ccec4bd8
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287690"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten

![Banner die naar https://aka.ms/aboutM365previewwijst.](media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a>Beleid voor app-beheer maken

1. Ga naar het Admin Center op <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
    
2. Kies in de linker navigatie \> **apparaatbeleidsregels** \> **toevoegen**. ****
  
3. Voer in het deelvenster **Beleid toevoegen** een unieke naam in voor dit beleid. 
    
4. Kies onder **Type beleid** de optie **Toepassingsbeheer voor Android** of **Toepassingsbeheer voor iOS**, afhankelijk van de set beleidsregels die u wilt maken. 
    
5. Vouw **werkbestanden beveiligen wanneer apparaten zijn verloren of gestolen** en **beheren hoe gebruikers toegang hebben tot Office-bestanden op mobiele apparaten** \> Configureer de instellingen hoe u wilt. De **gebruikers toegang tot Office-bestanden op mobiele apparaten beheren** is standaard **uitgeschakeld** , **maar het is** raadzaam deze functie in te schakelen en de standaardwaarden te accepteren. Zie de [beschikbare instellingen](#available-settings) voor meer informatie. 
    
    U kunt altijd de koppeling **Standaardwaarden herstellen** gebruiken om terug te keren naar de standaardinstelling. 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. Bepaal nu **Voor wie zijn deze instellingen?** Als u niet de standaardbeveiligingsgroep **Alle gebruikers** wilt gebruiken, kiest u **Wijzigen**, zoekt u de beveiligingsgroep die deze instellingen krijgt \> **Selecteren**.
    
7. Kies ten slotte **Gereed** om het beleid op te slaan en dit toe te wijzen aan apparaten. 
    
## <a name="edit-an-app-management-policy"></a>Beleid voor app-beheer bewerken

1. Kies **beleid bewerken**op de kaart **beleid** .
    
2. Kies in het deelvenster **Beleid bewerken** het beleid dat u wilt wijzigen 
    
3. Kies **Bewerken** naast elke instelling om de waarden in het beleid te wijzigen. Wanneer u een waarde wijzigt, wordt dit automatisch opgeslagen in het beleid 
    
4. Wanneer u klaar bent, sluit u het deelvenster **Beleid bewerken**. 
    
## <a name="delete-an-app-management-policy"></a>Beleid voor app-beheer verwijderen

1. Op de **beleid** pagina, kiest u een beleid en vervolgens **verwijderen**.
    
2. Kies in het deelvenster **beleid verwijderen** de optie **bevestigen** om het beleid of beleid te verwijderen dat u hebt gekozen. 
    
## <a name="available-settings"></a>Beschikbare instellingen

De volgende tabellen bevatten gedetailleerde informatie over de beschikbare instellingen voor het beveiligen van werkbestanden op apparaten en de instellingen waarmee wordt bepaald hoe gebruikers toegang hebben tot Office-bestanden op hun mobiele apparaten.
  
 Zie [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) (Hoe beveiligingsfuncties in Microsoft 365 Business zijn toegewezen aan Intune-instellingen) voor meer informatie. 
  
### <a name="settings-that-protect-work-files"></a>Instellingen voor het beveiligen van werkbestanden

De volgende instellingen zijn beschikbaar voor het beveiligen van werkbestanden bij verlies of diefstal van het apparaat van een gebruiker:
  
|||
|:-----|:-----|
|Instelling  <br/> |Beschrijving  <br/> |
|Werkbestanden van een inactief apparaat verwijderen na zoveel dagen  <br/> |Als een apparaat niet het aantal dagen wordt gebruikt dat u hier opgeeft, worden werkbestanden die op het apparaat zijn opgeslagen, automatisch verwijderd.  <br/> |
|Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven  <br/> |Als deze instelling is **ingeschakeld**, is OneDrive voor Bedrijven de enige beschikbare opslaglocatie voor werkbestanden.  <br/> |
|Werkbestanden versleutelen  <br/> |Laat deze instelling **ingeschakeld** zodat werkbestanden worden beveiligd door versleuteling. Zelfs bij verlies of diefstal van het apparaat kan niemand de bedrijfsgegevens lezen.  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Instellingen waarmee wordt bepaald hoe gebruikers toegang hebben tot Office-bestanden op mobiele apparaten

De volgende instellingen zijn beschikbaar om te bepalen hoe gebruikers toegang tot Office-werkbestanden hebben:
  
|||
|:-----|:-----|
|Instelling  <br/> |Beschrijving  <br/> |
|Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps  <br/> |Als deze instelling is **ingeschakeld**, moeten gebruikers een extra vorm van verificatie gebruiken, naast het verstrekken van gebruikersnaam en wachtwoord, voordat ze de Office-apps op hun mobiele apparaat kunnen gebruiken.  <br/> |
|Pincode opnieuw instellen wanneer het aanmelden ... keer mislukt  <br/> |Om te voorkomen dat een niet-geautoriseerde gebruiker een pincode kan raden, wordt de pincode opnieuw ingesteld na het aantal door u opgegeven verkeerde aanmeldpogingen.  <br/> |
|Vereisen dat gebruikers zich opnieuw aanmelden als Office-apps inactief zijn geweest gedurende  <br/> |Met deze instelling wordt bepaald hoelang gebruikers inactief kunnen zijn voordat hun wordt gevraagd zich opnieuw aan te melden.  <br/> |
|Toegang weigeren tot werkbestanden op jailbroken of geroote apparaten  <br/> |Slimme gebruikers hebben mogelijk een jailbroken of geroot apparaat. Dit betekent dat de gebruiker het besturingssysteem kan aanpassen, waardoor het apparaat gevoeliger zou kunnen worden voor malware. Deze apparaten worden geblokkeerd wanneer deze instelling is **ingeschakeld**.  <br/> |
|Gebruikers toestaan om inhoud uit Office-apps te kopiëren naar persoonlijke apps  <br/> |Dit is standaard toegestaan, maar als de instelling **Aan** is, kan de gebruiker gegevens uit een werkbestand kopiëren naar een persoonlijk bestand. Als de instelling **Uit** is, kan de gebruiker geen gegevens uit een werkbestand kopiëren naar een persoonlijke app of persoonlijk account.  <br/> |
   

  

