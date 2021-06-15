---
title: Instellingen voor app-beveiliging valideren voor Windows 10 pc's
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
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Lees hoe u kunt controleren of Microsoft 365 instellingen voor app-beveiliging voor bedrijven van kracht zijn geweest op de apparaten van Windows 10 gebruikers.
ms.openlocfilehash: 464a246a0da65dcffeb70946287ce4fa0e67ae7c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925254"
---
# <a name="validate-device-protection-settings-for-windows-10-pcs"></a>Apparaatbeveiligingsinstellingen voor Windows 10 pc's valideren

## <a name="verify-that-windows-10-device-policies-are-set"></a>Controleren of Windows 10-apparaatbeleid is ingesteld

Nadat u [apparaatbeleid hebt ingesteld](protection-settings-for-windows-10-pcs.md), kan het enkele uren duren voordat het beleid van kracht wordt op apparaten van gebruikers. U kunt controleren of het beleid van kracht is door verschillende schermen met Windows-instellingen te bekijken op de apparaten van gebruikers. Omdat de gebruikers de instellingen Bijwerken en Windows bijwerken en Windows Defender Antivirus op hun Windows 10-apparaten niet kunnen wijzigen, worden veel opties grijs weergegeven.
  
1. Ga naar **Instellingen** \> **&amp; Beveiligingsupdate Windows** Opties voor opnieuw opstarten bijwerken en controleer of alle instellingen grijs worden \>  \>  weergegeven. 
    
    ![Alle opties voor opnieuw opstarten worden grijs weergegeven.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Ga naar **Instellingen** \> **&amp; Beveiligingsupdate Windows** Geavanceerde opties bijwerken en controleer of alle instellingen grijs worden \>  \>  weergegeven. 
    
    ![Windows Geavanceerde updates zijn allemaal grijs weergegeven.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.
    
    Controleer of u het bericht (rood) kunt zien dat sommige instellingen zijn verborgen of beheerd door uw organisatie en dat alle opties grijs worden weergegeven.
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**. 
    
5. Controleer of alle opties grijs worden weergegeven. 
    
    ![De instellingen voor virus- en bedreigingsbeveiliging worden grijs weergegeven.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Verwante onderwerpen

[Microsoft 365 voor zakelijke documentatie en resources](./index.yml)
  
[Aan de slag met Microsoft 365 voor bedrijven](microsoft-365-business-overview.md)
  
[Beheer Microsoft 365 voor bedrijven](manage.md)
  
[Instellingen voor apparaatbeveiliging instellen voor Windows 10-pc's](protection-settings-for-windows-10-pcs.md)
