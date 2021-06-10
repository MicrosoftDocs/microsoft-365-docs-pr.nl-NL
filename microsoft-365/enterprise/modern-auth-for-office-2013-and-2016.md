---
title: Hoe moderne verificatie werkt voor Office 2013- en 2016 Office-clienttoepassingen
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/1/2017
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- GMA150
- GPA150
- GEA150
- BCS160
ms.assetid: e4c45989-4b1a-462e-a81b-2a13191cf517
ms.collection:
- M365-security-compliance
description: Lees hoe Microsoft 365 moderne verificatiefuncties anders werken voor Office 2013- en 2016-client-apps.
ms.openlocfilehash: 3e402f5786a72f3703ab4a1a77df688176f7de61
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921664"
---
# <a name="how-modern-authentication-works-for-office-2013-office-2016-and-office-2019-client-apps"></a>Hoe moderne verificatie werkt voor Office 2013, Office 2016 en Office 2019-client-apps

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Lees dit artikel voor meer informatie over hoe Office 2013, Office 2016 en Office 2019 client-apps moderne verificatiefuncties gebruiken op basis van de verificatieconfiguratie op de Microsoft 365-tenant voor Exchange Online, SharePoint Online en Skype voor Bedrijven Online.

> [!NOTE]
> Oudere client-apps, zoals Office 2010 en Office voor Mac 2011, ondersteunen geen moderne verificatie en kunnen alleen worden gebruikt met basisverificatie.

## <a name="availability-of-modern-authentication-for-microsoft-365-services"></a>Beschikbaarheid van moderne verificatie voor Microsoft 365 services

Voor de Microsoft 365 services is de standaardtoestand van moderne verificatie:
  
- Deze **is** standaard Exchange Online ingeschakeld. Zie [Moderne verificatie in- of uitschakelen in Exchange Online](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) om deze uit of uit te schakelen. 
    
- Standaard **ingeschakeld** voor SharePoint Online. 
    
- Standaard **ingeschakeld** voor Skype voor Bedrijven Online. Zie [Skype voor Bedrijven Online inschakelen voor moderne verificatie ](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)om deze uit of uit te schakelen.

> [!NOTE]
> Voor tenants **die** vóór 1 augustus 2017 zijn gemaakt, is moderne verificatie standaard uitgeschakeld voor Exchange Online en Skype voor Bedrijven Online. 
    
## <a name="sign-in-behavior-of-office-client-apps"></a>Aanmeldingsgedrag van Office client-apps

Office 2013-clientapps ondersteunen standaard oudere verificatie. Verouderd betekent dat ze Microsoft Online-aanmeldingsassistent of basisverificatie ondersteunen. Als deze clients moderne verificatiefuncties kunnen gebruiken, moet de Windows registersleutels hebben ingesteld. Zie Moderne verificatie [inschakelen voor Office 2013](https://support.office.com/article/7dc1c01a-090f-4971-9677-f1b192d6c910)op Windows apparaten voor instructies.

Als u moderne verificatie wilt inschakelen voor Windows-apparaten, zoals laptops en tablets, waarop Microsoft Office 2013 is geïnstalleerd, moet u de volgende registersleutels instellen. De sleutels moeten worden ingesteld op elk apparaat waarop u de moderne verificatie wilt inschakelen:
  
|**Registersleutel**|**Type**|**Value** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
  
Lees [Moderne verificatie (ADAL)](./hybrid-modern-auth-overview.md) gebruiken met Skype voor Bedrijven voor meer informatie over hoe dit werkt met Skype voor Bedrijven. 
  
Office 2016- en Office 2019-clients ondersteunen standaard moderne verificatie en de client hoeft deze nieuwe stromen niet te gebruiken. Er is echter expliciete actie nodig om oudere verificatie te gebruiken.
  
Klik op de onderstaande koppelingen om te zien hoe Office 2013, Office 2016 en Office 2019 clientverificatie werkt met de Microsoft 365-services, afhankelijk van of moderne verificatie al dan niet is ingeschakeld.
  
- [Exchange Online](modern-auth-for-office-2013-and-2016.md#BK_EchangeOnline)
    
- [SharePoint Online](modern-auth-for-office-2013-and-2016.md#BK_SharePointOnline)
    
- [Skype voor Bedrijven Online](modern-auth-for-office-2013-and-2016.md#BK_SFBO)
    
<a name="BK_EchangeOnline"> </a>
### <a name="exchange-online"></a>Exchange Online

In de volgende tabel wordt het verificatiegedrag beschreven voor Office 2013, Office 2016 en Office 2019-client-apps wanneer ze verbinding maken met Exchange Online met of zonder moderne verificatie.
  
|Office client-app versie****|Registersleutel aanwezig?****|Moderne verificatie op?****|Verificatiegedrag met moderne verificatie ingeschakeld voor de tenant (standaard)****|Verificatiegedrag met moderne verificatie uitgeschakeld voor de tenant****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Nee, <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Ja  <br/> |Moderne verificatie vereist op Outlook 2013, 2016 of 2019. <br/> [Meer informatie](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Dwingt moderne verificatie binnen de Outlook client.<br/> |
|Office 2019  <br/> |Nee, of EnableADAL = 1  <br/> |Ja  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server een moderne verificatieverbinding weigert, wordt basisverificatie gebruikt. Server weigert moderne verificatie wanneer de tenant niet is ingeschakeld.  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server een moderne verificatieverbinding weigert, wordt basisverificatie gebruikt. Server weigert moderne verificatie wanneer de tenant niet is ingeschakeld.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server een moderne verificatieverbinding weigert, wordt basisverificatie gebruikt. Server weigert moderne verificatie wanneer de tenant niet is ingeschakeld.  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server een moderne verificatieverbinding weigert, wordt basisverificatie gebruikt. Server weigert moderne verificatie wanneer de tenant niet is ingeschakeld.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL=0  <br/> |Nee  <br/> |Basisverificatie  <br/> |Basisverificatie  <br/> |
|Office 2016  <br/> |Nee, <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Ja  <br/> |Moderne verificatie vereist in 2013, 2016 of 2019. <br/> [Meer informatie](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Dwingt moderne verificatie binnen de Outlook client.<br/> |
|Office 2016  <br/> |Nee, of EnableADAL = 1  <br/> |Ja  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server een moderne verificatieverbinding weigert, wordt basisverificatie gebruikt. Server weigert moderne verificatie wanneer de tenant niet is ingeschakeld.  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server een moderne verificatieverbinding weigert, wordt basisverificatie gebruikt. Server weigert moderne verificatie wanneer de tenant niet is ingeschakeld.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server een moderne verificatieverbinding weigert, wordt basisverificatie gebruikt. Server weigert moderne verificatie wanneer de tenant niet is ingeschakeld.  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server een moderne verificatieverbinding weigert, wordt basisverificatie gebruikt. Server weigert moderne verificatie wanneer de tenant niet is ingeschakeld.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL=0  <br/> |Nee  <br/> |Basisverificatie  <br/> |Basisverificatie  <br/> |
|Office 2013  <br/> |Nee  <br/> |Nee  <br/> |Basisverificatie  <br/> |Basisverificatie  <br/> |
|Office 2013  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server een moderne verificatieverbinding weigert, wordt basisverificatie gebruikt. Server weigert moderne verificatie wanneer de tenant niet is ingeschakeld.  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server een moderne verificatieverbinding weigert, wordt basisverificatie gebruikt. Server weigert moderne verificatie wanneer de tenant niet is ingeschakeld.  <br/> |
   
<a name="BK_SharePointOnline"> </a>
### <a name="sharepoint-online"></a>SharePoint Online

In de volgende tabel wordt het verificatiegedrag beschreven voor Office 2013, Office 2016 en Office 2019-client-apps wanneer ze verbinding maken met SharePoint Online met of zonder moderne verificatie.
  
|Office client-app versie****|Registersleutel aanwezig?****|Moderne verificatie op?****|Verificatiegedrag met moderne verificatie ingeschakeld voor de tenant (standaard)****|Verificatiegedrag met moderne verificatie uitgeschakeld voor de tenant****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Nee, of EnableADAL = 1  <br/> |Ja  <br/> |Alleen moderne verificatie.  <br/> |Kan geen verbinding maken.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Alleen moderne verificatie.  <br/> |Kan geen verbinding maken.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 0  <br/> |Nee  <br/> |Alleen Microsoft Online-aanmeldingsassistent.  <br/> |Alleen Microsoft Online-aanmeldingsassistent.  <br/> |
|Office 2016  <br/> |Nee, of EnableADAL = 1  <br/> |Ja  <br/> |Alleen moderne verificatie.  <br/> |Kan geen verbinding maken.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Alleen moderne verificatie.  <br/> |Kan geen verbinding maken.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 0  <br/> |Nee  <br/> |Alleen Microsoft Online-aanmeldingsassistent.  <br/> |Alleen Microsoft Online-aanmeldingsassistent.  <br/> |
|Office 2013  <br/> |Nee  <br/> |Nee  <br/> |Alleen Microsoft Online-aanmeldingsassistent.  <br/> |Alleen Microsoft Online-aanmeldingsassistent.  <br/> |
|Office 2013  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Alleen moderne verificatie.  <br/> |Kan geen verbinding maken.  <br/> |
   
### <a name="skype-for-business-online"></a>Skype voor Bedrijven Online
<a name="BK_SFBO"> </a>

In de volgende tabel wordt het verificatiegedrag beschreven voor Office 2013, Office 2016 en Office 2019-client-apps wanneer ze verbinding maken met Skype voor Bedrijven Online met of zonder moderne verificatie.
  
|Office client-app versie****|Registersleutel aanwezig?****|Moderne verificatie op?****|Verificatiegedrag met moderne verificatie ingeschakeld voor de tenant****|Verificatiegedrag met moderne verificatie uitgeschakeld voor de tenant (standaard)****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Nee, of EnableADAL = 1  <br/> |Ja  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server een moderne verificatieverbinding weigert, wordt Microsoft Online-aanmeldingsassistent gebruikt. Server weigert moderne verificatie wanneer Skype voor Bedrijven Online tenants niet zijn ingeschakeld.  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server een moderne verificatieverbinding weigert, wordt Microsoft Online-aanmeldingsassistent gebruikt. Server weigert moderne verificatie wanneer Skype voor Bedrijven Online tenants niet zijn ingeschakeld.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server een moderne verificatieverbinding weigert, wordt Microsoft Online-aanmeldingsassistent gebruikt. Server weigert moderne verificatie wanneer Skype voor Bedrijven Online tenants niet zijn ingeschakeld.  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server een moderne verificatieverbinding weigert, wordt Microsoft Online-aanmeldingsassistent gebruikt. Server weigert moderne verificatie wanneer Skype voor Bedrijven Online tenants niet zijn ingeschakeld.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 0  <br/> |Nee  <br/> |Alleen Microsoft Online-aanmeldingsassistent.  <br/> |Alleen Microsoft Online-aanmeldingsassistent.  <br/> |
|Office 2016  <br/> |Nee, of EnableADAL = 1  <br/> |Ja  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server een moderne verificatieverbinding weigert, wordt Microsoft Online-aanmeldingsassistent gebruikt. Server weigert moderne verificatie wanneer Skype voor Bedrijven Online tenants niet zijn ingeschakeld.  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server een moderne verificatieverbinding weigert, wordt Microsoft Online-aanmeldingsassistent gebruikt. Server weigert moderne verificatie wanneer Skype voor Bedrijven Online tenants niet zijn ingeschakeld.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server een moderne verificatieverbinding weigert, wordt Microsoft Online-aanmeldingsassistent gebruikt. Server weigert moderne verificatie wanneer Skype voor Bedrijven Online tenants niet zijn ingeschakeld.  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server een moderne verificatieverbinding weigert, wordt Microsoft Online-aanmeldingsassistent gebruikt. Server weigert moderne verificatie wanneer Skype voor Bedrijven Online tenants niet zijn ingeschakeld.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 0  <br/> |Nee  <br/> |Alleen Microsoft Online-aanmeldingsassistent.  <br/> |Alleen Microsoft Online-aanmeldingsassistent.  <br/> |
|Office 2013  <br/> |Nee  <br/> |Nee  <br/> |Alleen Microsoft Online-aanmeldingsassistent.  <br/> |Alleen Microsoft Online-aanmeldingsassistent.  <br/> |
|Office 2013  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server een moderne verificatieverbinding weigert, wordt Microsoft Online-aanmeldingsassistent gebruikt. Server weigert moderne verificatie wanneer Skype voor Bedrijven Online tenants niet zijn ingeschakeld.  <br/> |Alleen Microsoft Online-aanmeldingsassistent.  <br/> |
   
## <a name="see-also"></a>Zie ook

[Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten](../admin/security-and-compliance/enable-modern-authentication.md)

[Meervoudige verificatie instellen voor Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)

[Aanmelden bij Microsoft 365 met meervoudige verificatie](https://support.microsoft.com/office/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)

[Microsoft 365 Enterprise overzicht](microsoft-365-overview.md)