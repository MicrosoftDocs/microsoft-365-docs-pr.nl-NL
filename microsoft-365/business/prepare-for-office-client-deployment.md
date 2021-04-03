---
title: Voorbereiden op office-clientimplementatie door Microsoft 365 voor Bedrijven
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
description: Lees hoe u de 32-bits Office-apps automatisch installeert op Windows 10-computers en deze op de hoogte houdt.
ms.openlocfilehash: 868d06fadfef0f55b41131b7fdfbb368b9128405
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580049"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>Voorbereiden op office-clientimplementatie door Microsoft 365 voor Bedrijven

Dit artikel is van toepassing op Microsoft 365 Business Premium.

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>De automatische installatie van Office-apps op clientcomputers voorbereiden

U kunt Microsoft 365 Business Premium gebruiken om de 32-bits Office-apps automatisch te installeren op Windows 10-computers en deze op de hoogte te houden van updates.
  
Automatische installatie werkt het beste als de computer van de eindgebruiker zich op Windows 10 Business en:
  
- geen bestaande Office-desktop-apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access en OneDrive) heeft.
    
    of
    
- er een bestaande versie van Office Klik-en-klaar is geïnstalleerd.
    
Om te bepalen of u de Klik-en-klaar-versie van Office hebt, gaat u in een Office-app naar **Bestand** \> **Account** ( **Office-Account** in Outlook). Als u **Office-updates** ziet zoals wordt weergegeven in de volgende afbeelding, is de installatie uitgevoerd met Klik-en-Klaar. 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Wie profiteert van deze functie**
  
De eindgebruiker waarvan de pc:
  
- **Heeft**  een windows 10 Business-gebruikerslicentie, een actieve licentie voor Microsoft 365 voor Bedrijven, Windows 10 Creators Update en is verbonden met Azure Active Directory. 
    
- **Heeft geen** 64-bits Office-apps (bijvoorbeeld: Word, Excel, PowerPoint). Als 64-bits Office-apps vereist zijn, is deze functie niet geschikt omdat er geen ondersteuning is voor het activeren van een 64-bits 2016 Klik-en-Werk-versie van Office vanaf de Microsoft 365 voor Bedrijven-beheerconsole. 
    
- **geen** 2016 Windows Installer (MSI) zelfstandige apps (zoals Visio of Project) heeft. Microsoft 365 voor Bedrijven upgradet Office naar de Klik-en-Klaar-versie van Office 2016 en dat werkt niet met zelfstandige Office 2016 MSI-apps. 
    
In de volgende tabel ziet u welke actie de eindgebruikers/beheerders mogelijk moeten ondernemen, afhankelijk van hun begintoestand, om een succesvolle 32-bits Klik-en-Werk-versie van Office-implementatie te hebben vanaf de Microsoft 365 voor Bedrijven-beheerconsole.
  
|**Beginstatus van de Office-installatie**|**Actie ondernemen voordat Microsoft 365 voor Bedrijven Office wordt geïnstalleerd**|**Eindstatus**|
|:-----|:-----|:-----|
|Geen Office-suite geïnstalleerd  <br/> |Geen  <br/> |Office 2016 32-bits wordt geïnstalleerd met behulp van Klik-en-Werk  <br/> |
|Bestaande 32-bits Klik-en-klaar-versie van Office (2016 of lager) en geen zelfstandige apps  <br/> |Geen  <br/> |Er is, zo nodig **\***, een upgrade uitgevoerd naar de meest recente 32-bits Klik-en-klaar-versie van Office 2016 <br/> |
|Bestaande 32-bits 32 bitsversie van Office en 32 bits- of 64-bits zelfstandige Office-apps (bijvoorbeeld Visio, Project)  <br/> |Geen  <br/> |Zelfstandige apps worden niet beïnvloed. Suite is bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016  <br/> |
|Bestaande 32-bits Klik-en-klaar-versie van Office en 32-bits of 64-bits (behalve 2016) MSI zelfstandige Office-apps  <br/> |Geen  <br/> |Zelfstandige apps worden niet beïnvloed. Suite is bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016  <br/> ||||
|Een bestaande 64-bits Klik-en-klaar-versie van Office  <br/> |Verwijder de 64-bits Office-apps als u ze wilt vervangen door 32 bits Office-apps  <br/> |Als 64-bits Office-apps worden verwijderd, wordt de 32-bits Klik-en-klaar-versie van Office 2016 geïnstalleerd  <br/> |
|Een bestaande MSI-installatie van Office 2016 met of zonder zelfstandige apps  <br/> |Verwijder MSI Office 2016.  <br/> |32-bits Klik-en-klaar-versie van Office 2016 is geïnstalleerd. Geen wijziging van zelfstandige apps  <br/> |
|Bestaande MSI-installatie van Office 2013 (of eerder) en/of zelfstandige Office-apps  <br/> |Geen  <br/> |32-bits Klik-en-klaar-versie van Office 2016 met de bestaande MSI-Office-installatie (en zelfstandige apps) bestaan naast elkaar  <br/> |
||||
   
 **(\*) Opmerking:** Wordt niet bijgewerkt naar de 32-bits Klik-en-klaar-versie van Office 2016 vanwege een bekende fout. Er wordt een oplossing uitgevoerd. 
  
