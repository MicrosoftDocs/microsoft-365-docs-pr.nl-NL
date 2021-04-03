---
title: Instellingen voor app-beveiliging valideren op Android- of iOS-apparaten
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Meer informatie over het valideren van de beveiligingsinstellingen van de Microsoft 365 Business Premium-app op uw Android- of iOS-apparaten.
ms.openlocfilehash: a0a4a6e6cff59f66a506929e97c99d361472a68b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578062"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a>Instellingen voor app-beveiliging valideren op Android- of iOS-apparaten

Volg de instructies in de volgende secties om instellingen voor app-beveiliging te valideren op Android- of iOS-apparaten.
  
## <a name="android"></a>Android
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Controleer of de instellingen voor app-beveiliging werken op gebruikersapparaten

Nadat u [app-configuraties voor Android-apparaten hebt ingesteld](app-protection-settings-for-android-and-ios.md) om de apps te beschermen, kunt u deze stappen uitvoeren om te controleren of de gekozen instellingen goed werken. 
  
Controleer eerst of het beleid van toepassing is op de app waarin u het gaat valideren.
  
1. Ga in het Microsoft 365 Business [Premium-beheercentrum](https://portal.office.com)naar  \> **Beleidsbeleid bewerken.**
    
2. Kies **Toepassingsbeleid voor Android** voor de instellingen die u hebt gemaakt bij de installatie of een ander beleid dat u hebt gemaakt, en controleer of dit bijvoorbeeld is afgedwongen voor Outlook. 
    
    ![Shows all the apps for which this policy protects files.](../media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a>Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps valideren

Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Toegangsbeheer Office-documenten**, vouw **Beheren hoe gebruikers Office-bestanden op mobiele apparaten openen** uit en zorg ervoor dat **Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps** is ingesteld op **Aan**.
  
![Zorg ervoor dat de pincode of vingerafdruk vereisen voor toegang tot Office-apps is ingesteld op Aan.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. Open Outlook op het Android-apparaat van de gebruiker en meld u aan met de Microsoft 365 Business Premium-referenties van de gebruiker.
    
2. U wordt ook gevraagd een pincode in te voeren of een vingerafdruk te gebruiken.
    
    ![Enter a PIN on your Android device to access Office apps.](../media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Pincode opnieuw instellen na aantal mislukte pogingen valideren

Kies **in** het deelvenster  Beleid bewerken de optie Bewerken naast Toegangsbesturingselement **voor Office-documenten,** vouw Beheren hoe gebruikers Toegang krijgen tot **Office-bestanden** op mobiele apparaten uit en zorg ervoor dat **Pincode** opnieuw instellen nadat het aantal mislukte pogingen is ingesteld op een nummer. Dit is standaard 5. 
  
1. Open Outlook op het Android-apparaat van de gebruiker en meld u aan met de Microsoft 365 Business Premium-referenties van de gebruiker.
    
2. Voer net zo vaak een onjuiste pincode in als is aangegeven in het beleid. U ziet een prompt met de melding **Pincode pogingslimiet bereikt om** de pincode opnieuw in te stellen. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. Druk op **Pincode opnieuw instellen**. U wordt gevraagd u aan te melden met de Microsoft 365 Business Premium-referenties van de gebruiker en vervolgens een nieuwe pincode in te stellen.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven valideren

Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Beveiliging bij verlies of diefstal van apparaten**, vouw **Werkbestanden beveiligen bij verlies of diefstal van apparaten** uit en zorg ervoor dat **Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven** is ingesteld op **Aan**.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. Open Outlook op het Android-apparaat van de gebruiker en meld u aan met de Microsoft 365 Business Premium-referenties van de gebruiker en voer desgevraagd een pincode in.
    
2. Open een e-mailbericht met een bijlage en tik op het pictogram Pijl-omlaag naast de gegevens van de bijlage.
    
    ![Tap the down arrow next to an attachment to try to save it.](../media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    U ziet Niet **opslaan op apparaat** onder aan het scherm. 
    
    ![Warning text that indicates cannot save a file locally to an Android.](../media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > Opslaan in OneDrive voor Bedrijven is op dit moment niet ingeschakeld voor Android, zodat u alleen ziet dat lokaal opslaan is geblokkeerd. 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Vereisen dat gebruikers zich opnieuw aanmelden als Office-apps inactief zijn geweest gedurende een opgegeven tijd valideren

Kies **in** het deelvenster  Beleid bewerken de optie Bewerken naast Toegangsbeheer voor **Office-documenten,** vouw Beheren hoe gebruikers Toegang krijgen tot **Office-bestanden** op mobiele apparaten uit en zorg ervoor dat Gebruikers opnieuw moeten aanmelden nadat **Office-apps** niet actief zijn geweest, is ingesteld op een aantal minuten. Dit is standaard 30 minuten. 
  
1. Open Outlook op het Android-apparaat van de gebruiker en meld u aan met de Microsoft 365 Business Premium-referenties van de gebruiker en voer desgevraagd een pincode in.
    
2. U ziet nu het Postvak IN van Outlook. Gebruik het Android-apparaat minimaal 30 minuten niet (of een andere tijdsduur, langer dan wat u hebt opgegeven in het beleid). Het apparaat wordt waarschijnlijk gedimd.
    
3. Open Outlook opnieuw op het Android-apparaat.
    
4. U wordt gevraagd uw pincode in te voeren voordat u Outlook opnieuw kunt openen.
    
### <a name="validate-protect-work-files-with-encryption"></a>Werkbestanden beveiligen met versleuteling valideren

Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Beveiliging bij verlies of diefstal van apparaten**, vouw **Werkbestanden beveiligen bij verlies of diefstal van apparaten** uit en zorg ervoor dat **Werkbestanden beveiligen met versleuteling** is ingesteld op **Aan** en **Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven** is ingesteld op **Uit**.
  
1. Open Outlook op het Android-apparaat van de gebruiker en meld u aan met de Microsoft 365 Business Premium-referenties van de gebruiker en voer desgevraagd een pincode in.
    
2. Open een e-mailbericht met een paar bijlagen in het afbeeldingsbestand.
    
3. Tik op het pictogram Pijl-omlaag naast de informatie van de bijlage om die op te slaan.
    
    ![Tap the down arrow to save the figure file to the Android device.](../media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. U wordt mogelijk gevraagd om toegang toe te staan voor Outlook tot de foto's, media en bestanden op uw apparaat. Tik op **Toestaan**.
    
5. Kies onderaan het scherm **Opslaan op apparaat** en open vervolgens de **Galerie** -app. 
    
6. U ziet een versleutelde foto (of meer als u meerdere bijlagen met afbeeldingsbestanden hebt opgeslagen) in de lijst. Dit wordt mogelijk weergegeven in de lijst met afbeeldingen als een grijs vierkant met een wit uitroepteken binnen een witte cirkel in het midden van het grijze vak.
    
    ![An encrypted image file in the Gallery app.](../media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a>iOS
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Controleer of de instellingen voor app-beveiliging werken op gebruikersapparaten

Nadat u [app-configuraties voor iOS-apparaten hebt ingesteld](app-protection-settings-for-android-and-ios.md) om apps te beschermen, kunt u deze stappen uitvoeren om te controleren of de gekozen instellingen goed werken. 
  
Controleer eerst of het beleid van toepassing is op de app waarin u het gaat valideren.
  
1. Ga in het Microsoft 365 Business [Premium-beheercentrum](https://portal.office.com)naar  \> **Beleidsbeleid bewerken.**
    
2. Kies **Toepassingsbeleid voor iOS** voor de instellingen die u hebt gemaakt bij de installatie of een ander beleid dat u hebt gemaakt, en controleer of dit is afgedwongen voor outlook bijvoorbeeld. 
    
    ![Shows all the apps for which this policy protects files.](../media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a>Een pincode vereisen om toegang te krijgen tot Office-apps valideren

Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Toegangsbeheer Office-documenten**, vouw **Beheren hoe gebruikers Office-bestanden op mobiele apparaten openen** uit en zorg ervoor dat **Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps** is ingesteld op **Aan**.
  
![Zorg ervoor dat de pincode of vingerafdruk vereisen voor toegang tot Office-apps is ingesteld op Aan.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. Open Outlook op het iOS-apparaat van de gebruiker en meld u aan met de Microsoft 365 Business Premium-referenties van de gebruiker.
    
2. U wordt ook gevraagd een pincode in te voeren of een vingerafdruk te gebruiken.
    
    ![Enter a PIN on your IOS device to access Office apps.](../media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Pincode opnieuw instellen na aantal mislukte pogingen valideren

Kies **in** het deelvenster  Beleid bewerken de optie Bewerken naast Toegangsbesturingselement **voor Office-documenten,** vouw Beheren hoe gebruikers Toegang krijgen tot **Office-bestanden** op mobiele apparaten uit en zorg ervoor dat **Pincode** opnieuw instellen nadat het aantal mislukte pogingen is ingesteld op een nummer. Dit is standaard 5. 
  
1. Open Outlook op het iOS-apparaat van de gebruiker en meld u aan met de Microsoft 365 Business Premium-referenties van de gebruiker.
    
2. Voer net zo vaak een onjuiste pincode in als is aangegeven in het beleid. U ziet een prompt met de melding **Pincode pogingslimiet bereikt om** de pincode opnieuw in te stellen. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. Druk op **OK**. U wordt gevraagd u aan te melden met de Microsoft 365 Business Premium-referenties van de gebruiker en vervolgens een nieuwe pincode in te stellen.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven valideren

Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Beveiliging bij verlies of diefstal van apparaten**, vouw **Werkbestanden beveiligen bij verlies of diefstal van apparaten** uit en zorg ervoor dat **Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven** is ingesteld op **Aan**.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. Open Outlook op het iOS-apparaat van de gebruiker en meld u aan met de Microsoft 365 Business Premium-referenties van de gebruiker en voer desgevraagd een pincode in.
    
2. Open een e-mailbericht met een bijlage, open de bijlage en kies **Opslaan** onderaan het scherm. 
    
    ![Tap the Save option after you open an attachment to try to save it.](../media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. U ziet alleen een optie voor OneDrive voor Bedrijven. Zo niet, tikt **u op Account** toevoegen en **selecteert u OneDrive voor Bedrijven** in het scherm **Opslagaccount** toevoegen. Geef microsoft 365 Business Premium van de eindgebruiker op om u aan te melden wanneer u daarom wordt gevraagd. 
    
    Tik op **Opslaan** en selecteer **OneDrive voor Bedrijven**.
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Vereisen dat gebruikers zich opnieuw aanmelden als Office-apps inactief zijn geweest gedurende een opgegeven tijd valideren

Kies **in** het deelvenster  Beleid bewerken de optie Bewerken naast Toegangsbeheer voor **Office-documenten,** vouw Beheren hoe gebruikers Toegang krijgen tot **Office-bestanden** op mobiele apparaten uit en zorg ervoor dat Gebruikers opnieuw moeten aanmelden nadat **Office-apps** niet actief zijn geweest, is ingesteld op een aantal minuten. Dit is standaard 30 minuten. 
  
1. Open Outlook op het iOS-apparaat van de gebruiker en meld u aan met de Microsoft 365 Business Premium-referenties van de gebruiker en voer desgevraagd een pincode in.
    
2. U ziet nu het Postvak IN van Outlook. Gebruik het iOS-apparaat minimaal 30 minuten niet (of een andere tijdsduur, langer dan wat u hebt opgegeven in het beleid). Het apparaat wordt waarschijnlijk gedimd.
    
3. Open Outlook opnieuw op het iOS-apparaat.
    
4. U wordt gevraagd uw pincode in te voeren voordat u Outlook opnieuw kunt openen.
    
### <a name="validate-protect-work-files-with-encryption"></a>Werkbestanden beveiligen met versleuteling valideren

Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Beveiliging bij verlies of diefstal van apparaten**, vouw **Werkbestanden beveiligen bij verlies of diefstal van apparaten** uit en zorg ervoor dat **Werkbestanden beveiligen met versleuteling** is ingesteld op **Aan** en **Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven** is ingesteld op **Uit**.
  
1. Open Outlook op het iOS-apparaat van de gebruiker en meld u aan met de Microsoft 365 Business Premium-referenties van de gebruiker en voer desgevraagd een pincode in.
    
2. Open een e-mailbericht met een paar bijlagen in het afbeeldingsbestand.
    
3. Tik op de bijlage en tik vervolgens op de optie **Opslaan** eronder. 
    
4. Open de app **Foto's** vanuit het beginscherm. U ziet een versleutelde foto (of meer als u meerdere bijlagen met afbeeldingsbestanden hebt opgeslagen) die is opgeslagen, maar die wel is versleuteld. 
    
---

