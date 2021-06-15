---
title: Voorbereiden op Office clientimplementatie per Microsoft 365 voor bedrijven
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Meer informatie over het automatisch installeren van de 32-bits Office apps op Windows 10 computers en deze bijgewerkt houden.
ms.openlocfilehash: 843be426d817da1173769b3b66dc4c054179f0fd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924222"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>Voorbereiden op Office clientimplementatie per Microsoft 365 voor bedrijven

Dit artikel is van toepassing op Microsoft 365 Business Premium.

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>De automatische installatie van Office-apps op clientcomputers voorbereiden

U kunt Microsoft 365 Business Premium gebruiken om de 32-bits apps Office op Windows 10 computers te installeren en deze op de hoogte te houden van updates.
  
Automatische installatie werkt het beste als de computer van de eindgebruiker is Windows 10 Business en:
  
- geen bestaande Office-desktop-apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access en OneDrive) heeft.
    
    of
    
- er een bestaande versie van Office Klik-en-klaar is geïnstalleerd.
    
Om te bepalen of u de Klik-en-klaar-versie van Office hebt, gaat u in een Office-app naar **Bestand** \> **Account** ( **Office-Account** in Outlook). Als u Office **in** de volgende afbeelding ziet, is de installatie uitgevoerd met Klik-en-Klaar. 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Wie voordeel van deze functie**
  
De eindgebruiker waarvan de pc:
  
- **Heeft** een Windows 10 Business gebruikerslicentie, een actieve licentie Microsoft 365 voor bedrijven, Windows 10 Creators Update en is lid van Azure Active Directory. 
    
- **Heeft geen** 64-bits Office apps (bijvoorbeeld: Word, Excel, PowerPoint). Als 64-bits Office-apps vereist zijn, is deze functie niet geschikt omdat er geen ondersteuning is voor het activeren van een 64-bits 2016 Klik-en-Werk-versie van Office vanaf de Microsoft 365 voor bedrijven-beheerconsole. 
    
- **geen** 2016 Windows Installer (MSI) zelfstandige apps (zoals Visio of Project) heeft. Microsoft 365 voor bedrijven upgrades Office de Klik-en-Klaar-versie van Office 2016 en dat werkt niet met zelfstandige Office 2016 MSI. 
    
In de volgende tabel ziet u welke actie de eindgebruikers/beheerders mogelijk moeten ondernemen, afhankelijk van hun begintoestand, om een succesvolle 32-bits Klik-en-Werk-versie van Office-implementatie te hebben vanaf de Microsoft 365 voor zakelijke beheerconsole.<br/>


|Beginstatus van de Office-installatie|Actie die moet worden ondernomen voordat Microsoft 365 voor bedrijven Office installeren|Eindstatus|
|:-----|:-----|:-----|
|Geen Office-suite geïnstalleerd  <br/> |Geen  <br/> |Office 32-bits 2016 is geïnstalleerd met behulp van Klik-en-Werk  <br/> |
|Bestaande 32-bits Klik-en-klaar-versie van Office (2016 of lager) en geen zelfstandige apps  <br/> |Geen  <br/> |Er is, zo nodig **\***, een upgrade uitgevoerd naar de meest recente 32-bits Klik-en-klaar-versie van Office 2016 <br/> |
|Bestaande 32-bits 32-bits versie van Office en 32 bits- of 64-bits zelfstandige Office-apps (bijvoorbeeld Visio, Project)  <br/> |Geen  <br/> |Zelfstandige apps worden niet beïnvloed. Suite is bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016  <br/> |
|Bestaande 32-bits Klik-en-klaar-versie van Office en 32-bits of 64-bits (behalve 2016) MSI zelfstandige Office-apps  <br/> |Geen  <br/> |Zelfstandige apps worden niet beïnvloed. Suite is bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016  <br/> |
|Een bestaande 64-bits Klik-en-klaar-versie van Office  <br/> |Verwijder de 64-bits Office apps, als u deze kunt vervangen door 32-bits Office apps  <br/> |Als 64-bits Office-apps worden verwijderd, wordt de 32-bits Klik-en-klaar-versie van Office 2016 geïnstalleerd  <br/> |
|Een bestaande MSI-installatie van Office 2016 met of zonder zelfstandige apps  <br/> |Verwijder MSI Office 2016.  <br/> |32-bits Klik-en-klaar-versie van Office 2016 is geïnstalleerd. Geen wijziging van zelfstandige apps  <br/> |
|Bestaande MSI-installatie van Office 2013 (of eerder) en/of zelfstandige Office-apps  <br/> |Geen  <br/> |32-bits Klik-en-klaar-versie van Office 2016 met de bestaande MSI-Office-installatie (en zelfstandige apps) bestaan naast elkaar  <br/> |
||||
   
 **(\*) Opmerking:** Wordt niet bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016 vanwege een bekende fout. Er wordt een oplossing uitgevoerd. 
  
