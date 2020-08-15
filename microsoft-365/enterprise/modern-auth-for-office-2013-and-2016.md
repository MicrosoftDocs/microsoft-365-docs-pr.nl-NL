---
title: Hoe moderne verificatie werkt voor Office 2013-en Office 2016-clienttoepassingen
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
description: Meer informatie over de manieren waarop Microsoft 365 moderne verificatiefuncties werken voor Office 2013-en 2016-clienttoepassingen.
ms.openlocfilehash: 62aa04e295c2734d705f22bd2f62c6bc5e622426
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689506"
---
# <a name="how-modern-authentication-works-for-office-2013-office-2016-and-office-2019-client-apps"></a>Hoe moderne verificatie werkt voor Office 2013-, Office 2016-en Office 2019-clienttoepassingen

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

In dit artikel vindt u meer informatie over hoe Office 2013, Office 2016 en Office 2019 client-apps gebruikmaken van moderne verificatiefuncties op basis van de verificatieconfiguratie op de Microsoft 365-Tenant voor Exchange Online, SharePoint Online en Skype voor bedrijven online.

> [!NOTE]
> Oudere clienttoepassingen, zoals Office 2010 en Office voor Mac 2011, ondersteunen moderne verificatie niet en kunnen alleen worden gebruikt met basisverificatie.

## <a name="availability-of-modern-authentication-for-microsoft-365-services"></a>Beschikbaarheid van moderne verificatie voor Microsoft 365-Services

Voor de Microsoft 365-Services is de standaardstatus van moderne verificatie als volgt:
  
- Standaard **ingeschakeld voor Exchange** online. Zie [moderne verificatie in Exchange Online in-of uitschakelen](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) om de functie uit te schakelen of aan te zetten. 
    
- Standaard **ingeschakeld voor** SharePoint Online. 
    
- Standaard **ingeschakeld voor Skype voor bedrijven** online. Zie [Skype voor bedrijven online inschakelen voor moderne verificatie ](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)als u deze functie wilt in-of uitschakelen.

> [!NOTE]
> Voor tenants die zijn gemaakt **vóór** 1 augustus 2017, is moderne verificatie **standaard uitgeschakeld voor** Exchange Online en Skype voor bedrijven online.
    
## <a name="sign-in-behavior-of-office-client-apps"></a>Aanmeldings gedrag van Office-clienttoepassingen

Client-apps van Office 2013 ondersteunen standaard een oudere verificatie. Verouderd betekent dat ze de Microsoft Online-aanmeldhulp of basisverificatie ondersteunen. Om ervoor te hebben dat deze clients moderne verificatiefuncties kunnen gebruiken, moet de Windows-clientregister sleutels hebben ingesteld. Voor instructies raadpleegt u [moderne verificatie inschakelen voor Office 2013 op Windows-apparaten](https://support.office.com/article/7dc1c01a-090f-4971-9677-f1b192d6c910).

Als u moderne verificatie wilt inschakelen voor Windows-apparaten, zoals laptops en tablets, waarop Microsoft Office 2013 is geïnstalleerd, moet u de volgende registersleutels instellen. De sleutels moeten worden ingesteld op elk apparaat waarop u de moderne verificatie wilt inschakelen:
  
|**Registersleutel**|**Type**|**Value** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
  
Meer informatie [over het gebruik van moderne verificatie (ADAL) met Skype voor bedrijven](https://go.microsoft.com/fwlink/p/?LinkId=785431) voor meer informatie over hoe dit werkt met Skype voor bedrijven. 
  
Office 2016 en Office 2019-clients bieden standaard ondersteuning voor moderne verificatie en u hoeft geen actie te ondernemen voor de client om deze nieuwe stromen te gebruiken. Er is echter wel expliciete actie vereist voor het gebruik van oudere verificatie.
  
Klik op de onderstaande koppelingen voor meer informatie over hoe Office 2013, Office 2016 en de clientverificatie van Office 2019 werken met de Microsoft 365-Services, afhankelijk van of moderne verificatie is ingeschakeld.
  
- [Exchange Online](modern-auth-for-office-2013-and-2016.md#BK_EchangeOnline)
    
- [SharePoint Online](modern-auth-for-office-2013-and-2016.md#BK_SharePointOnline)
    
- [Skype voor Bedrijven Online](modern-auth-for-office-2013-and-2016.md#BK_SFBO)
    
<a name="BK_EchangeOnline"> </a>
### <a name="exchange-online"></a>Exchange Online

In de volgende tabel wordt het verificatie gedrag beschreven voor Office 2013-, Office 2016-en Office 2019-clienttoepassingen wanneer ze verbinding maken met Exchange Online met of zonder moderne verificatie.
  
|Versie van Office-clienttoepassing * * * *|Registersleutel aanwezig? * * * *|Moderne verificatie ingeschakeld? * * * *|Verificatie gedrag met moderne verificatie ingeschakeld voor de Tenant (standaard) * * * *|Verificatie gedrag met moderne verificatie uitgeschakeld voor de Tenant * * * *|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Enkel <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Ja  <br/> |Zorgt voor moderne verificatie voor Outlook 2013, 2016 of 2019. <br/> [Meer informatie](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Zorgt voor moderne authenticatie binnen de Outlook-client.<br/> |
|Office 2019  <br/> |Nee, of EnableADAL = 1  <br/> |Ja  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server geen moderne verificatie verbinding weigert, wordt basisverificatie gebruikt. Server weigert moderne verificatie wanneer de Tenant niet is ingeschakeld.  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server geen moderne verificatie verbinding weigert, wordt basisverificatie gebruikt. Server weigert moderne verificatie wanneer de Tenant niet is ingeschakeld.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server geen moderne verificatie verbinding weigert, wordt basisverificatie gebruikt. Server weigert moderne verificatie wanneer de Tenant niet is ingeschakeld.  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server geen moderne verificatie verbinding weigert, wordt basisverificatie gebruikt. Server weigert moderne verificatie wanneer de Tenant niet is ingeschakeld.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 0  <br/> |Nee  <br/> |Basisverificatie  <br/> |Basisverificatie  <br/> |
|Office 2016  <br/> |Enkel <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Ja  <br/> |Zorgt voor moderne verificatie voor 2013, 2016 of 2019. <br/> [Meer informatie](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Zorgt voor moderne authenticatie binnen de Outlook-client.<br/> |
|Office 2016  <br/> |Nee, of EnableADAL = 1  <br/> |Ja  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server geen moderne verificatie verbinding weigert, wordt basisverificatie gebruikt. Server weigert moderne verificatie wanneer de Tenant niet is ingeschakeld.  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server geen moderne verificatie verbinding weigert, wordt basisverificatie gebruikt. Server weigert moderne verificatie wanneer de Tenant niet is ingeschakeld.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server geen moderne verificatie verbinding weigert, wordt basisverificatie gebruikt. Server weigert moderne verificatie wanneer de Tenant niet is ingeschakeld.  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server geen moderne verificatie verbinding weigert, wordt basisverificatie gebruikt. Server weigert moderne verificatie wanneer de Tenant niet is ingeschakeld.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 0  <br/> |Nee  <br/> |Basisverificatie  <br/> |Basisverificatie  <br/> |
|Office 2013  <br/> |Nee  <br/> |Nee  <br/> |Basisverificatie  <br/> |Basisverificatie  <br/> |
|Office 2013  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server geen moderne verificatie verbinding weigert, wordt basisverificatie gebruikt. Server weigert moderne verificatie wanneer de Tenant niet is ingeschakeld.  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server geen moderne verificatie verbinding weigert, wordt basisverificatie gebruikt. Server weigert moderne verificatie wanneer de Tenant niet is ingeschakeld.  <br/> |
   
<a name="BK_SharePointOnline"> </a>
### <a name="sharepoint-online"></a>SharePoint Online

In de volgende tabel wordt het verificatie gedrag beschreven voor Office 2013-, Office 2016-en Office 2019-clienttoepassingen wanneer ze verbinding maken met SharePoint Online met of zonder moderne verificatie.
  
|Versie van Office-clienttoepassing * * * *|Registersleutel aanwezig? * * * *|Moderne verificatie ingeschakeld? * * * *|Verificatie gedrag met moderne verificatie ingeschakeld voor de Tenant (standaard) * * * *|Verificatie gedrag met moderne verificatie uitgeschakeld voor de Tenant * * * *|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Nee, of EnableADAL = 1  <br/> |Ja  <br/> |Alleen moderne verificatie.  <br/> |Er kan geen verbinding worden gemaakt.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Alleen moderne verificatie.  <br/> |Er kan geen verbinding worden gemaakt.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 0  <br/> |Nee  <br/> |Alleen Microsoft Online aanmeldhulp.  <br/> |Alleen Microsoft Online aanmeldhulp.  <br/> |
|Office 2016  <br/> |Nee, of EnableADAL = 1  <br/> |Ja  <br/> |Alleen moderne verificatie.  <br/> |Er kan geen verbinding worden gemaakt.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Alleen moderne verificatie.  <br/> |Er kan geen verbinding worden gemaakt.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 0  <br/> |Nee  <br/> |Alleen Microsoft Online aanmeldhulp.  <br/> |Alleen Microsoft Online aanmeldhulp.  <br/> |
|Office 2013  <br/> |Nee  <br/> |Nee  <br/> |Alleen Microsoft Online aanmeldhulp.  <br/> |Alleen Microsoft Online aanmeldhulp.  <br/> |
|Office 2013  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Alleen moderne verificatie.  <br/> |Er kan geen verbinding worden gemaakt.  <br/> |
   
### <a name="skype-for-business-online"></a>Skype voor Bedrijven Online
<a name="BK_SFBO"> </a>

In de volgende tabel wordt het verificatie gedrag beschreven voor Office 2013-, Office 2016-en Office 2019-clienttoepassingen wanneer ze verbinding maken met Skype voor bedrijven online met of zonder moderne verificatie.
  
|Versie van Office-clienttoepassing * * * *|Registersleutel aanwezig? * * * *|Moderne verificatie ingeschakeld? * * * *|Verificatie gedrag met moderne verificatie ingeschakeld voor de Tenant * * * *|Verificatie gedrag met moderne verificatie uitgeschakeld voor de Tenant (standaard) * * * *|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Nee, of EnableADAL = 1  <br/> |Ja  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server geen moderne verificatie verbinding weigert, wordt Microsoft Online-aanmeldhulp gebruikt. Server weigert moderne verificatie wanneer tenants van Skype voor bedrijven online niet zijn ingeschakeld.  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server geen moderne verificatie verbinding weigert, wordt Microsoft Online-aanmeldhulp gebruikt. Server weigert moderne verificatie wanneer tenants van Skype voor bedrijven online niet zijn ingeschakeld.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server geen moderne verificatie verbinding weigert, wordt Microsoft Online-aanmeldhulp gebruikt. Server weigert moderne verificatie wanneer tenants van Skype voor bedrijven online niet zijn ingeschakeld.  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server geen moderne verificatie verbinding weigert, wordt Microsoft Online-aanmeldhulp gebruikt. Server weigert moderne verificatie wanneer tenants van Skype voor bedrijven online niet zijn ingeschakeld.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 0  <br/> |Nee  <br/> |Alleen Microsoft Online aanmeldhulp.  <br/> |Alleen Microsoft Online aanmeldhulp.  <br/> |
|Office 2016  <br/> |Nee, of EnableADAL = 1  <br/> |Ja  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server geen moderne verificatie verbinding weigert, wordt Microsoft Online-aanmeldhulp gebruikt. Server weigert moderne verificatie wanneer tenants van Skype voor bedrijven online niet zijn ingeschakeld.  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server geen moderne verificatie verbinding weigert, wordt Microsoft Online-aanmeldhulp gebruikt. Server weigert moderne verificatie wanneer tenants van Skype voor bedrijven online niet zijn ingeschakeld.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server geen moderne verificatie verbinding weigert, wordt Microsoft Online-aanmeldhulp gebruikt. Server weigert moderne verificatie wanneer tenants van Skype voor bedrijven online niet zijn ingeschakeld.  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server geen moderne verificatie verbinding weigert, wordt Microsoft Online-aanmeldhulp gebruikt. Server weigert moderne verificatie wanneer tenants van Skype voor bedrijven online niet zijn ingeschakeld.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 0  <br/> |Nee  <br/> |Alleen Microsoft Online aanmeldhulp.  <br/> |Alleen Microsoft Online aanmeldhulp.  <br/> |
|Office 2013  <br/> |Nee  <br/> |Nee  <br/> |Alleen Microsoft Online aanmeldhulp.  <br/> |Alleen Microsoft Online aanmeldhulp.  <br/> |
|Office 2013  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Moderne verificatie wordt eerst geprobeerd. Als de server geen moderne verificatie verbinding weigert, wordt Microsoft Online-aanmeldhulp gebruikt. Server weigert moderne verificatie wanneer tenants van Skype voor bedrijven online niet zijn ingeschakeld.  <br/> |Alleen Microsoft Online aanmeldhulp.  <br/> |
   
## <a name="see-also"></a>Zie ook

[Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)

[Meervoudige verificatie instellen voor Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)

[Meld u aan bij Microsoft 365 met multi-factor Authentication](https://support.microsoft.com/office/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)

[Overzicht van Microsoft 365 Enterprise](microsoft-365-overview.md)
