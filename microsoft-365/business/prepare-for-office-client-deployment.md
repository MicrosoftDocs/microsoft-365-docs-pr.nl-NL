---
title: Bereid u voor op de implementatie van de Office-client door Microsoft 365 Business
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Meer informatie over het automatisch installeren van de 32-bits Office-apps op Windows 10-computers en deze up-to-date te houden.
ms.openlocfilehash: fa5b2ce1852ebdb1e76c1fa844793fee56af3d68
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593614"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a>Bereid u voor op de implementatie van de Office-client door Microsoft 365 Business

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>De automatische installatie van Office-apps op clientcomputers voorbereiden

U Microsoft 365 Business gebruiken om de 32-bits Office-apps automatisch op Windows 10-computers te installeren en ze actueel te houden met updates.
  
Automatische installatie werkt het beste als de computer van de eindgebruiker zich op Windows 10 Business bevindt en:
  
- geen bestaande Office-desktop-apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access en OneDrive) heeft.
    
    of
    
- er een bestaande versie van Office Klik-en-klaar is geïnstalleerd.
    
Om te bepalen of u de Klik-en-klaar-versie van Office hebt, gaat u in een Office-app naar **Bestand** \> **Account** ( **Office-Account** in Outlook). Als u **Office-updates** ziet zoals weergegeven in de volgende afbeelding, is de installatie uitgevoerd met Klik-en-Klaar. 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Wie profiteert van het hebben van deze functie**
  
De eindgebruiker waarvan de pc:
  
- **een** gebruikerslicentie voor Windows 10 Business, een actieve Microsoft 365 Business-licentie, Windows 10 Creators-update heeft en is verbonden met Azure Active Directory. 
    
- **Heeft geen** 64-bits Office-apps (bijvoorbeeld Word, Excel, PowerPoint). Als er 64-bits Office-apps nodig zijn, past deze functie niet goed omdat er geen ondersteuning is voor het activeren van een 64-bits 2016 Click-to-Run-versie van Office vanaf de Microsoft 365 Business-beheerconsole. 
    
- **geen** 2016 Windows Installer (MSI) zelfstandige apps (zoals Visio of Project) heeft. Microsoft 365 Business werkt Office uit naar de Click-to-Run-versie van Office 2016 en dat werkt niet met zelfstandige Windows-apps van Office 2016. 
    
In de volgende tabel ziet u welke actie de eindgebruikers/beheerders mogelijk moeten uitvoeren, afhankelijk van hun beginstatus, om een succesvolle 32-bits Klik-naar-uitvoering-versie van Office-implementatie te hebben vanaf de microsoft 365 Business-beheerconsole.
  
|**Beginstatus van de Office-installatie**|**Actie die moet worden uitgevoerd voor de Microsoft 365 Business-installatie van Office**|**Eindstatus**|
|:-----|:-----|:-----|
|Geen Office-suite geïnstalleerd  <br/> |Geen  <br/> |Office 2016 32-bits is geïnstalleerd met Klik-en-werk  <br/> |
|Bestaande 32-bits Klik-en-klaar-versie van Office (2016 of lager) en geen zelfstandige apps  <br/> |Geen  <br/> |Er is, zo nodig **\***, een upgrade uitgevoerd naar de meest recente 32-bits Klik-en-klaar-versie van Office 2016 <br/> |
|Bestaande 32-bits versie van Office en Click-to-Run 32-bits of 64-bits zelfstandige Office-apps (bijvoorbeeld Visio, Project)  <br/> |Geen  <br/> |Zelfstandige apps worden niet beïnvloed. Suite is bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016  <br/> |
|Bestaande 32-bits Klik-en-klaar-versie van Office en 32-bits of 64-bits (behalve 2016) MSI zelfstandige Office-apps  <br/> |Geen  <br/> |Zelfstandige apps worden niet beïnvloed. Suite is bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016  <br/> ||||
|Een bestaande 64-bits Klik-en-klaar-versie van Office  <br/> |Verwijder de 64-bits Office-apps als het goed is om ze te vervangen door 32-bits Office-apps  <br/> |Als 64-bits Office-apps worden verwijderd, wordt de 32-bits Klik-en-klaar-versie van Office 2016 geïnstalleerd  <br/> |
|Een bestaande MSI-installatie van Office 2016 met of zonder zelfstandige apps  <br/> |Verwijder MSI Office 2016.  <br/> |32-bits Klik-en-klaar-versie van Office 2016 is geïnstalleerd. Geen wijziging van zelfstandige apps  <br/> |
|Bestaande MSI-installatie van Office 2013 (of eerder) en/of zelfstandige Office-apps  <br/> |Geen  <br/> |32-bits Klik-en-klaar-versie van Office 2016 met de bestaande MSI-Office-installatie (en zelfstandige apps) bestaan naast elkaar  <br/> |
||||
   
 **(\*) Opmerking:** Wordt niet bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016 vanwege een bekende fout. Er is een oplossing aan de gang. 
  