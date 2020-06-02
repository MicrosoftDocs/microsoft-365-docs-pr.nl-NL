---
title: Voorbereiden op implementatie van Office-clients door Microsoft 365 voor Bedrijven
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Lees hoe u de 32-bits Office-apps automatisch installeert op Windows 10-computers en deze up-to-date houdt.
ms.openlocfilehash: 2de492914edbde2afe593aac290c4a634b801443
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470942"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>Voorbereiden op implementatie van Office-clients door Microsoft 365 voor Bedrijven

Dit artikel is van toepassing op Microsoft 365 Business Premium.

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>De automatische installatie van Office-apps op clientcomputers voorbereiden

U Microsoft 365 Business Premium gebruiken om de 32-bits Office-apps automatisch op Windows 10-computers te installeren en ze actueel te houden met updates.
  
Automatische installatie werkt het beste als de computer van de eindgebruiker op Windows 10 Business staat en:
  
- geen bestaande Office-desktop-apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access en OneDrive) heeft.
    
    of
    
- er een bestaande versie van Office Klik-en-klaar is geïnstalleerd.
    
Om te bepalen of u de Klik-en-klaar-versie van Office hebt, gaat u in een Office-app naar **Bestand** \> **Account** ( **Office-Account** in Outlook). Als u **Office-updates** ziet zoals weergegeven in de volgende afbeelding, is de installatie uitgevoerd met Klik-en-Klaar. 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Wie profiteert van het hebben van deze functie**
  
De eindgebruiker waarvan de pc:
  
- **Heeft** een Windows 10 Business-gebruikerslicentie, een actieve Microsoft 365 voor zakelijke licentie, Windows 10 Creators Update en is verbonden met Azure Active Directory. 
    
- **Heeft geen** 64-bits Office-apps (bijvoorbeeld: Word, Excel, PowerPoint). Als 64-bits Office-apps vereist zijn, past deze functie niet goed omdat er geen ondersteuning is voor het activeren van een 64-bits 2016 Click-to-Run-versie van Office vanuit de Microsoft 365 voor zakelijke beheerconsole. 
    
- **geen** 2016 Windows Installer (MSI) zelfstandige apps (zoals Visio of Project) heeft. Microsoft 365 voor bedrijven upgradet Office naar de Klik-en-Klaar-versie van Office 2016 en dat werkt niet met zelfstandige Office 2016 MSI-apps. 
    
In de volgende tabel ziet u welke actie de eindgebruikers/beheerders moeten ondernemen, afhankelijk van hun beginstatus, om een succesvolle 32-bits Click-to-Run-versie van Office-implementatie te hebben vanuit de Microsoft 365 voor zakelijke beheerconsole.
  
|**Beginstatus van de Office-installatie**|**Actie voor de installatie van Microsoft 365 voor Bedrijven**|**Eindstatus**|
|:-----|:-----|:-----|
|Geen Office-suite geïnstalleerd  <br/> |Geen  <br/> |Office 2016 32-bits is geïnstalleerd met Klik-en-Werkscherm  <br/> |
|Bestaande 32-bits Klik-en-klaar-versie van Office (2016 of lager) en geen zelfstandige apps  <br/> |Geen  <br/> |Er is, zo nodig **\***, een upgrade uitgevoerd naar de meest recente 32-bits Klik-en-klaar-versie van Office 2016 <br/> |
|Bestaande Click-to-Run 32-bits versie van Office en Click-to-Run 32-bits of 64-bits zelfstandige Office-apps (bijvoorbeeld Visio, Project)  <br/> |Geen  <br/> |Zelfstandige apps worden niet beïnvloed. Suite is bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016  <br/> |
|Bestaande 32-bits Klik-en-klaar-versie van Office en 32-bits of 64-bits (behalve 2016) MSI zelfstandige Office-apps  <br/> |Geen  <br/> |Zelfstandige apps worden niet beïnvloed. Suite is bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016  <br/> ||||
|Een bestaande 64-bits Klik-en-klaar-versie van Office  <br/> |De 64-bits Office-apps verwijderen als deze in het ok zijn om deze te vervangen door 32-bits Office-apps  <br/> |Als 64-bits Office-apps worden verwijderd, wordt de 32-bits Klik-en-klaar-versie van Office 2016 geïnstalleerd  <br/> |
|Een bestaande MSI-installatie van Office 2016 met of zonder zelfstandige apps  <br/> |Verwijder MSI Office 2016.  <br/> |32-bits Klik-en-klaar-versie van Office 2016 is geïnstalleerd. Geen wijziging van zelfstandige apps  <br/> |
|Bestaande MSI-installatie van Office 2013 (of eerder) en/of zelfstandige Office-apps  <br/> |Geen  <br/> |32-bits Klik-en-klaar-versie van Office 2016 met de bestaande MSI-Office-installatie (en zelfstandige apps) bestaan naast elkaar  <br/> |
||||
   
 **(\*) Opmerking:** Wordt niet bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016 vanwege een bekende fout. Er is een oplossing aan de gang. 
  
