---
title: Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten
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
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Meer informatie over het maken, bewerken of verwijderen van een app-beheerbeleid en het beveiligen van werkbestanden op Android- of iOS-apparaten.
ms.openlocfilehash: c0c8883fb120db90d81e57fbb80206d6ce4eccbf
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593308"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten

![Banner die https://aka.ms/aboutM365previewwijzen op .](media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a>Beleid voor app-beheer maken

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>beheercentrum bij . 
    
2. Kies in het linkernavigatienav het **beleid** \> **Apparaten** \> **toevoegen**.
  
3. Voer in het deelvenster **Beleid toevoegen** een unieke naam in voor dit beleid. 
    
4. Kies onder **Beleidstype** **Toepassingsbeheer voor Android** of **Toepassingsbeheer voor iOS**, afhankelijk van welke set beleidsregels u wilt maken. 
    
5. Werkbestanden beveiligen uitbreiden **wanneer apparaten verloren of gestolen zijn en** beheer hoe gebruikers toegang krijgen tot **Office-bestanden op mobiele apparaten.** Configureer de instellingen zoals u dat wilt. **Beheren hoe gebruikers toegang krijgen tot Office-bestanden op mobiele apparaten** is standaard **uitgeschakeld,** maar we raden u aan deze **in** te schakelen en de standaardwaarden te accepteren. Zie [Beschikbare instellingen](#available-settings)voor meer informatie. 
    
    U kunt altijd de koppeling **Standaardwaarden herstellen** gebruiken om terug te keren naar de standaardinstelling. 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. Bepaal nu **Voor wie zijn deze instellingen?** Als u de standaardbeveiligingsgroep **All Users** niet **** wilt gebruiken, kiest u Wijzigen \> en kiest u de beveiligingsgroepen die deze instellingen krijgen **Selecteren**.
    
7. Kies ten slotte, **Klaar** om het beleid op te slaan en dit toe te wijzen aan apparaten. 
    
## <a name="edit-an-app-management-policy"></a>Beleid voor app-beheer bewerken

1. Kies op de **beleidskaart** **het beleid bewerken**.
    
2. Kies in het deelvenster **Beleid bewerken** het beleid dat u wilt wijzigen 
    
3. Kies **Bewerken** naast elke instelling om de waarden in het beleid te wijzigen. Wanneer u een waarde wijzigt, wordt deze automatisch opgeslagen in het beleid.
    
4. Als u klaar bent, sluit u het **beleidsvenster Bewerken.** 
    
## <a name="delete-an-app-management-policy"></a>Beleid voor app-beheer verwijderen

1. Kies op de pagina **Beleid** een beleid en **verwijder**.
    
2. Kies in het **deelvenster Beleid verwijderen** de optie **Bevestigen** om het gekozen beleid of beleid te verwijderen. 
    
## <a name="available-settings"></a>Beschikbare instellingen

In de volgende tabellen vindt u gedetailleerde informatie over de beschikbare instellingen om werkbestanden op apparaten te beveiligen en de instellingen die bepalen hoe gebruikers toegang krijgen tot Office-bestanden vanaf hun mobiele apparaten.
  
 Zie [Hoe beveiligingsfuncties in Microsoft 365 Business zijn toegewezen aan Intune-instellingen](map-protection-features-to-intune-settings.md) voor meer informatie. 
  
### <a name="settings-that-protect-work-files"></a>Instellingen voor het beveiligen van werkbestanden

De volgende instellingen zijn beschikbaar voor het beveiligen van werkbestanden bij verlies of diefstal van het apparaat van een gebruiker:
  
|||
|:-----|:-----|
|Instelling  <br/> |Beschrijving  <br/> |
|Werkbestanden van een inactief apparaat verwijderen na zoveel dagen  <br/> |Als een apparaat niet wordt gebruikt voor het aantal dagen dat u hier opgeeft, worden alle werkbestanden die op het apparaat zijn opgeslagen, automatisch verwijderd.  <br/> |
|Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven  <br/> |Als deze instelling **is ingeschakeld,** is de enige beschikbare opslaglocatie voor werkbestanden OneDrive voor Bedrijven.  <br/> |
|Werkbestanden versleutelen  <br/> |Laat deze instelling **ingeschakeld** zodat werkbestanden worden beveiligd door versleuteling. Zelfs als het apparaat verloren of gestolen is, kan niemand uw bedrijfsgegevens lezen.  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Instellingen die bepalen hoe gebruikers Office-bestanden op mobiele apparaten kunnen openen

De volgende instellingen zijn beschikbaar om te bepalen hoe gebruikers toegang tot Office-werkbestanden hebben:
  
|||
|:-----|:-----|
|Instelling  <br/> |Beschrijving  <br/> |
|Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps  <br/> |Als deze instelling **ingeschakeld** is, moeten gebruikers naast hun gebruikersnaam en wachtwoord een andere vorm van verificatie opgeven voordat ze Office-apps op hun mobiele apparaten kunnen gebruiken.<br/> |
|Pincode opnieuw instellen wanneer het aanmelden ... keer mislukt  <br/> |Om te voorkomen dat een niet-geautoriseerde gebruiker een pincode kan raden, wordt de pincode opnieuw ingesteld na het aantal door u opgegeven verkeerde aanmeldpogingen.  <br/> |
|Vereisen dat gebruikers zich opnieuw aanmelden als Office-apps inactief zijn geweest gedurende  <br/> |Met deze instelling bepaalt u hoe lang een gebruiker niet actief kan zijn voordat deze wordt gevraagd zich opnieuw aan te melden.  <br/> |
|Toegang weigeren tot werkbestanden op jailbroken of geroote apparaten  <br/> |Slimme gebruikers hebben mogelijk een jailbroken of geroot apparaat. Dit betekent dat de gebruiker het besturingssysteem kan aanpassen, waardoor het apparaat gevoeliger zou kunnen worden voor malware. Deze apparaten worden geblokkeerd wanneer deze instelling is **ingeschakeld**.  <br/> |
|Gebruikers toestaan om inhoud uit Office-apps te kopiëren naar persoonlijke apps  <br/> |Dit is standaard toegestaan, maar als de instelling **Aan** is, kan de gebruiker gegevens uit een werkbestand kopiëren naar een persoonlijk bestand. Als de instelling **Uit** is, kan de gebruiker geen gegevens uit een werkbestand kopiëren naar een persoonlijke app of persoonlijk account.  <br/> |
