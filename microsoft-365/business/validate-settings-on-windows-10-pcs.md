---
title: Beveiligingsinstellingen voor apps op Windows 10-pc's valideren
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
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Informatie over het valideren van de beveiligingsinstellingen van Microsoft 365 Business app in Windows 10-apparaten.
ms.openlocfilehash: db05c86bd75cc30e22e025034a3dab478d0f5365
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/28/2018
ms.locfileid: "26982702"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Instellingen voor apparaatbeveiliging controleren op Windows 10-pc's

## <a name="verify-that-windows-10-device-policies-are-set"></a>Controleren of Windows 10-apparaatbeleid is ingesteld

Nadat u [apparaatbeleid hebt ingesteld](protection-settings-for-windows-10-pcs.md), kan het enkele uren duren voordat het beleid van kracht wordt op apparaten van gebruikers. U kunt controleren of het beleid van kracht is door verschillende schermen met Windows-instellingen te bekijken op de apparaten van gebruikers. Omdat de gebruikers niet de mogelijkheid hebben om de instellingen voor Windows Update en Windows Defender Antivirus te wijzigen op hun Windows 10-apparaten, worden veel van deze opties lichter gekleurd weergegeven.
  
1. Ga naar **Instellingen** \> **Update &amp; security** \> **Windows Update** \> **Opties voor opnieuw starten** en te bevestigen dat alle instellingen grijs worden weergegeven. 
    
    ![All the Restart options are greyed out.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Ga naar **Instellingen** \> **Update &amp; security** \> **Windows Update** \> **Geavanceerde opties** en Bevestig dat alle instellingen grijs worden weergegeven. 
    
    ![Windows Advanced updates options are all greyed out.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Ga naar **Instellingen** \> **Update &amp; security** \> **Windows Update** \> **Geavanceerde opties** \> **kiezen hoe updates worden geleverd**.
    
    Controleer of u het bericht (in het rood) ziet dat bepaalde instellingen zijn verborgen of worden beheerd door uw organisatie en dat alle opties lichter gekleurd worden weergegeven.
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. De Windows Defender om Beveiligingscentrum te openen, gaat u naar **Instellingen** \> **Update &amp; security** \> **Windows Defender** \> Klik **Open Windows Defender Security Center** op \> **Virus &amp; thread bescherming** \> **Virus &amp; beveiligingsinstellingen gevaar**. 
    
5. Controleer of alle opties lichter gekleurd worden weergegeven. 
    
    ![The Virus and threat protection settings are greyed out.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Verwante onderwerpen

[Microsoft 365 Business-documentatie en -informatiebronnen](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Aan de slag met Microsoft 365 Business](microsoft-365-business-overview.md)
  
[Microsoft 365 Business beheren](manage.md)
  
[Instellingen voor apparaatbeveiliging instellen voor Windows 10-pc's](protection-settings-for-windows-10-pcs.md)
  

