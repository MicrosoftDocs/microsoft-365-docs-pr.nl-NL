---
title: Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Leer registersleutels instellen om moderne verificatie in te schakelen voor apparaten waarop Microsoft Office 2013 is geïnstalleerd.
ms.openlocfilehash: 8edcedefc04d5018b8b61022c26cbe027f7c24a9
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779963"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten

Als u moderne verificatie wilt inschakelen voor Windows-apparaten waarop Office 2013 is geïnstalleerd, moet u bepaalde registersleutels instellen.
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>Moderne verificatie voor Office 2013-clients inschakelen

> [!NOTE]
> Moderne verificatie is al ingeschakeld voor Office 2016-clients. U hoeft geen registersleutels in te stellen voor Office 2016. 
  
To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:
  
|**Registersleutel**|**Type**|**Value** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
   
Zodra u de registersleutels hebt ingesteld, u Office 2013-apparaten-apps instellen op [multifactorauthenticatie (MFA)](set-up-multi-factor-authentication.md) met Microsoft 365. 
  
If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.
  
## <a name="disable-modern-authentication-on-devices"></a>Moderne verificatie uitschakelen op apparaten

Als u moderne verificatie wilt uitschakelen op een apparaat, stelt u de volgende registersleutels in op het apparaat:
  
|**Registersleutel**|**Type**|**Value**|
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL |REG_DWORD|0|
   
## <a name="related-articles"></a>Verwante artikelen
[Aanmelden bij Office 2013 met een tweede verificatiemethode](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

  

