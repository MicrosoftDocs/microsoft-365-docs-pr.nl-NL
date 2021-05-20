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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Meer informatie over het instellen van registersleutels om moderne verificatie in te schakelen voor apparaten waarop Microsoft Office 2013 zijn geïnstalleerd.
ms.openlocfilehash: d358cb2ffb4284a51779e5a7c1dc894052b9ebc0
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572283"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten

Als u moderne verificatie wilt inschakelen voor Windows-apparaten waarop Office 2013 is geïnstalleerd, moet u bepaalde registersleutels instellen.
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>Moderne verificatie voor Office 2013-clients inschakelen

> [!NOTE]
> Moderne verificatie is al ingeschakeld voor Office 2016-clients. U hoeft geen registersleutels in te stellen voor Office 2016. 
  
Als u moderne verificatie wilt inschakelen voor Windows-apparaten, zoals laptops en tablets, waarop Microsoft Office 2013 is geïnstalleerd, moet u de volgende registersleutels instellen. De sleutels moeten worden ingesteld op elk apparaat waarop u de moderne verificatie wilt inschakelen:
  
|**Registersleutel**|**Type**|**Value** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Algemeen\Identiteit\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
   
Nadat u de registersleutels hebt ingesteld, kunt u Office apps voor 2013-apparaten instellen om [multifactorauthenticatie (MFA)](set-up-multi-factor-authentication.md) met Microsoft 365 te gebruiken. 
  
Als u momenteel bent aangemeld met een van de client-apps, moet u zich afmelden en opnieuw aanmelden om de wijziging te effectueren. Anders zijn de MRU- en roaminginstellingen niet beschikbaar tot de ADAL-identiteit is vastgesteld.
  
## <a name="disable-modern-authentication-on-devices"></a>Moderne verificatie uitschakelen op apparaten

Als u moderne verificatie wilt uitschakelen op een apparaat, stelt u de volgende registersleutels in op het apparaat:
  
|**Registersleutel**|**Type**|**Value**|
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Algemeen\Identiteit\EnableADAL |REG_DWORD|0|
   
## <a name="related-content"></a>Verwante onderwerpen

[Meld u aan bij Office 2013 met een tweede verificatiemethode](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) (artikel)

[Outlook vraagt om wachtwoord en gebruikt geen moderne verificatie om verbinding te maken met Office 365](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) (artikel)

