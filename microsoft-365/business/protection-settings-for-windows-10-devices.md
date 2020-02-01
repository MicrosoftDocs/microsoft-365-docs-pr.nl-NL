---
title: Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Meer informatie over het maken van een app-beheerbeleid en het beveiligen van werkbestanden op Windows 10-apparaten.
ms.openlocfilehash: 703f63fc1c90966eb8412886e82670af3e9d6f62
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593531"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a>Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten

## <a name="create-an-app-management-policy-for-windows-10"></a>Beleid voor app-beheer maken voor Windows 10

Als uw gebruikers persoonlijke Windows 10-apparaten gebruiken voor hun werk, kunt u de gegevens op die apparaten ook beschermen.
  
1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>beheercentrum bij . 
    
2. Kies op het linkernavigatiescherm het **beleid** \> **Voor apparaten** \> **toevoegen**.

3. Voer in het deelvenster **Beleid toevoegen** een unieke naam in voor dit beleid. 
    
4. Kies onder **Type beleid** de optie **Toepassingsbeheer voor Windows 10**.
    
5. Kies onder **Apparaattype** **de** optie Persoonlijk of **eigendom van het bedrijf**.
    
6. De optie **Werkbestanden versleutelen** is automatisch ingeschakeld. 
    
7. Stel **Voorkomen dat gebruikers bedrijfsgegevens kopiëren naar persoonlijke bestanden en afdwingen dat werkbestanden worden opgeslagen in OneDrive voor Bedrijven** in op **Aan** als u niet wilt dat de gebruikers werkbestanden opslaan op hun pc. 
    
9. **Gegevens herstellen op Windows-apparaten uitvouwen.** We raden je aan hem **aan**te zetten.
    
    Voordat u naar de locatie van het certificaat voor de gegevensherstelagent kunt bladeren, moet u deze eerst maken. Zie [EFS-certificaat (Encrypting File System(EFS) Data Recovery Agent (ENCRYPT) for](https://go.microsoft.com/fwlink/p/?linkid=853700)instructions.
    
    Werkbestanden worden standaard versleuteld met een geheime code die wordt opgeslagen op het apparaat en die gekoppeld is aan het profiel van de gebruiker. Alleen de gebruiker kan het bestand openen en ontsleutelen. Als een apparaat zoekraakt of als een gebruiker wordt verwijderd, kan een bestand echter blijven steken in versleutelde toestand. Een beheerder kan het DRA-certificaat (Data Recovery Agent) gebruiken om het bestand te decoderen.
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. Vouw **extra netwerk- en cloudlocaties beveiligen** uit als u extra domeinen of SharePoint Online-locaties wilt toevoegen om ervoor te zorgen dat bestanden in alle vermelde apps worden beveiligd. Als u meerdere items moet opgeven voor een veld, gebruikt u een puntkomma (;) tussen de items.
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Bepaal nu **Voor wie zijn deze instellingen?** Als u niet de standaardbeveiligingsgroep **Alle gebruikers** wilt gebruiken, kiest u **Wijzigen**, zoekt u de beveiligingsgroep die deze instellingen krijgt \> **Selecteren**.
    
12. Kies ten slotte **Toevoegen** om het beleid op te slaan en dit toe te wijzen aan apparaten. 