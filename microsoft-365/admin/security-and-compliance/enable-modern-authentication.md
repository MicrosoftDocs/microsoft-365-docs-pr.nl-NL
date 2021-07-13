---
title: Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten
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
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Informatie over het instellen van registersleutels om moderne verificatie in te schakelen voor apparaten Microsoft Office 2013 zijn geïnstalleerd.
ms.openlocfilehash: 8bfe515fefed9d58f140a67e53ce0d078457aa72
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393653"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten

Als u moderne verificatie wilt inschakelen voor Windows-apparaten waarop Office 2013 is geïnstalleerd, moet u bepaalde registersleutels instellen.
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>Moderne verificatie voor Office 2013-clients inschakelen

> [!NOTE]
> Moderne verificatie is al ingeschakeld voor Office 2016-clients. U hoeft geen registersleutels in te stellen voor Office 2016. 
  
Als u moderne verificatie wilt inschakelen voor Windows-apparaten, zoals laptops en tablets, waarop Microsoft Office 2013 is geïnstalleerd, moet u de volgende registersleutels instellen. De sleutels moeten worden ingesteld op elk apparaat waarop u de moderne verificatie wilt inschakelen:
  
|**Registersleutel**|**Type**|**Value** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
   
Nadat u de registersleutels hebt ingesteld, kunt u Office 2013-apparaten instellen op het gebruik van meervoudige verificatie [(MFA)](set-up-multi-factor-authentication.md) met Microsoft 365. 
  
Als u momenteel bent aangemeld met een van de client-apps, moet u zich afmelden en opnieuw aanmelden om de wijziging te effectueren. Anders zijn de MRU- en roaminginstellingen niet beschikbaar tot de ADAL-identiteit is vastgesteld.
  
## <a name="disable-modern-authentication-on-devices"></a>Moderne verificatie uitschakelen op apparaten

Als u moderne verificatie wilt uitschakelen op een apparaat, stelt u de volgende registersleutels in op het apparaat:
  
|**Registersleutel**|**Type**|**Value**|
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL |REG_DWORD|0|
   
## <a name="related-content"></a>Verwante inhoud

[Meld u aan bij Office 2013 met een tweede verificatiemethode](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) (artikel)\
[Outlook vraagt om wachtwoord en gebruikt geen](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) moderne verificatie om verbinding te maken met Office 365 (artikel)

