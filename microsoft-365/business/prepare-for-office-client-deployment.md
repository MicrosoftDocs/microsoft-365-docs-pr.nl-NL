---
title: Bereid u voor op de implementatie van de Office-client door Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Informatie over het automatisch installeren van de 32-bits Office-apps op Windows 10-computers en deze op de hoogte houden.
ms.openlocfilehash: fe1f946e4a216050e533604afa7c6e74e7b5980f
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288390"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a>Bereid u voor op de implementatie van de Office-client door Microsoft 365 Business

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>De automatische installatie van Office-apps op clientcomputers voorbereiden

U kunt met Microsoft 365 Business automatisch de 32-bits Office-apps installeren op computers met Windows 10 en ze bijwerken met updates.
  
Dit werkt het beste als de computer van de eindgebruiker Windows 10 Business uitvoert en:
  
- geen bestaande Office-desktop-apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access en OneDrive) heeft.
    
    of
    
- er een bestaande versie van Office Klik-en-klaar is geïnstalleerd.
    
Om te bepalen of u de Klik-en-klaar-versie van Office hebt, gaat u in een Office-app naar **Bestand** \> **Account** ( **Office-Account** in Outlook). Als u Office-updates kunt zien zoals in de volgende afbeelding wordt weergegeven, is de installatie gedaan met behulp van Klik-en-klaar. 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Wie heeft er voordeel van deze functie?**
  
De eindgebruiker waarvan de pc:
  
- **een** gebruikerslicentie voor Windows 10 Business, een actieve Microsoft 365 Business-licentie, Windows 10 Creators-update heeft en is verbonden met Azure Active Directory. 
    
- **geen** 64-bits Office-apps heeft (bijvoorbeeld: Word, Excel, PowerPoint). Als de 64-bits Office-apps vereist zijn, sluit deze functie niet goed aan, omdat er geen ondersteuning is voor het genereren van een 64-bits 2016 Klik-en-klaar-versie van Office vanaf de Microsoft 365 Business-beheerconsole. 
    
- **geen** 2016 Windows Installer (MSI) zelfstandige apps (zoals Visio of Project) heeft. Microsoft 365 Business upgradet Office naar de Klik-en-klaar-versie van Office 2016 en die werkt niet met zelfstandige apps van Office 2016 MSI. 
    
In de volgende tabel ziet u de actie die de eindgebruikers/beheerders mogelijk uit moeten voeren, afhankelijk van hun beginstatus, om een succesvolle 32-bits Klik-en-klaar-versie van Office te implementeren vanaf de Microsoft 365 Business-beheerconsole.
  
|**Beginstatus van de Office-installatie**|**Actie die moet worden uitgevoerd voor de Microsoft 365 Business-installatie van Office**|**Eindstatus**|
|:-----|:-----|:-----|
|Geen Office-suite geïnstalleerd  <br/> |Geen  <br/> |32-bits Office 2016 is geïnstalleerd met behulp van klik-en-klaar  <br/> |
|Bestaande 32-bits Klik-en-klaar-versie van Office (2016 of lager) en geen zelfstandige apps  <br/> |Geen  <br/> |Er is, zo nodig **\***, een upgrade uitgevoerd naar de meest recente 32-bits Klik-en-klaar-versie van Office 2016 <br/> |
|Bestaande 32-bits Klik-en-klaar-versie van Office en 32-bits of 64-bits Klik-en-klaar zelfstandige Office-apps (bijvoorbeeld, Visio, Project)  <br/> |Geen  <br/> |Zelfstandige apps worden niet beïnvloed. Suite is bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016  <br/> |
|Bestaande 32-bits Klik-en-klaar-versie van Office en 32-bits of 64-bits (behalve 2016) MSI zelfstandige Office-apps  <br/> |Geen  <br/> |Zelfstandige apps worden niet beïnvloed. Suite is bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016  <br/> ||||
|Een bestaande 64-bits Klik-en-klaar-versie van Office  <br/> |Verwijder de 64-bits Office-apps als deze vervangen kunnen worden door 32-bits Office-apps  <br/> |Als 64-bits Office-apps worden verwijderd, wordt de 32-bits Klik-en-klaar-versie van Office 2016 geïnstalleerd  <br/> |
|Een bestaande MSI-installatie van Office 2016 met of zonder zelfstandige apps  <br/> |Verwijder MSI Office 2016.  <br/> |32-bits Klik-en-klaar-versie van Office 2016 is geïnstalleerd. Geen wijziging van zelfstandige apps  <br/> |
|Bestaande MSI-installatie van Office 2013 (of eerder) en/of zelfstandige Office-apps  <br/> |Geen  <br/> |32-bits Klik-en-klaar-versie van Office 2016 met de bestaande MSI-Office-installatie (en zelfstandige apps) bestaan naast elkaar  <br/> |
||||
   
 **(\*) Opmerking:** Wordt niet bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016 vanwege een bekende fout. Er wordt aan de oplossing gewerkt. 
  


