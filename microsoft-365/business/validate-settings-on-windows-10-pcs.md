---
title: Beveiligingsinstellingen voor apps op Windows 10-pc's valideren
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
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Meer informatie over het valideren van beveiligingsinstellingen voor Microsoft 365 Business-apps op Windows 10-apparaten.
ms.openlocfilehash: 1762382aec00a80e006cf38b66c28d02c0c25989
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42056642"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Instellingen voor apparaatbeveiliging controleren op Windows 10-pc's

## <a name="verify-that-windows-10-device-policies-are-set"></a>Controleren of Windows 10-apparaatbeleid is ingesteld

Nadat u [apparaatbeleid hebt ingesteld](protection-settings-for-windows-10-pcs.md), kan het enkele uren duren voordat het beleid van kracht wordt op apparaten van gebruikers. U kunt controleren of het beleid van kracht is door verschillende schermen met Windows-instellingen te bekijken op de apparaten van gebruikers. Omdat de gebruikers de instellingen voor Windows Update en Windows Defender Antivirus op hun Windows 10-apparaten niet kunnen wijzigen, worden veel opties grijs weergegeven.
  
1. Ga **naar** \> **Instellingen Beveiligingsupdateopties &amp; ** \> **Windows Update** \> Opnieuw **opstarten** en bevestig dat alle instellingen grijs zijn. 
    
    ![Alle opties voor opnieuw opstarten zijn grijs weergegeven.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Ga naar **Beveiligingsupdate instellingen** \> \> ** &amp; Windows** **Update** \> **Geavanceerde opties** en bevestig dat alle instellingen grijs zijn. 
    
    ![Windows Advanced-updates opties zijn allemaal grijs.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.
    
    Controleer of u het bericht (in het rood) zien dat sommige instellingen zijn verborgen of beheerd door uw organisatie en dat alle opties grijs zijn.
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**. 
    
5. Controleer of alle opties grijs zijn. 
    
    ![De instellingen voor virus- en bedreigingsbeveiliging zijn grijs.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Gerelateerde onderwerpen

[Documentatie en informatiebronnen voor Microsoft 365 Business (Engelstalig)](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Aan de slag met Microsoft 365 Business](microsoft-365-business-overview.md)
  
[Microsoft 365 Business beheren](manage.md)
  
[Instellingen voor apparaatbeveiliging instellen voor Windows 10-pc's](protection-settings-for-windows-10-pcs.md)
  

