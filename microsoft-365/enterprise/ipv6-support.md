---
title: IPv6-ondersteuning in Office 365-services
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/10/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: 'Overzicht: Beschrijft IPv6-ondersteuning in Microsoft Office 365 onderdelen en in Office 365 overheidsaanbiedingen.'
ms.openlocfilehash: 7f06ed6f8df2c6552ee0a331ad958bca289d0a09
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909680"
---
# <a name="ipv6-support-in-office-365-services"></a>IPv6-ondersteuning in Office 365-services

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Office 365 ondersteunt zowel IPv6 als IPv4; Niet alle functies Office 365 zijn echter volledig ingeschakeld met IPv6. Dit betekent dat u zowel IPv4 als IPv6 moet gebruiken om verbinding te maken met Office 365. Als u uw uitgaande verkeer filtert naar Office 365, vindt u de volledige lijst met IPv6-adressen die worden ondersteund door Office 365 in het artikel Office 365 URL's en [IP-adresbereiken.](urls-and-ip-address-ranges.md) Nadat uw netwerk is geconfigureerd en de juiste IPv6-adressen zijn toegestaan, kunt u het Office 365 [IPv6-testplan](https://go.microsoft.com/fwlink/?LinkId=293447) downloaden vanuit het Microsoft Downloadcentrum.
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>IPv6-ondersteuning in Office 365 abonnementsservice

### <a name="exchange-online-and-ipv6"></a>Exchange Online en IPv6

Als het programma dat u gebruikt om verbinding te maken met Exchange Online IPv6 ondersteunt, wordt IPv6 standaard gebruikt op zowel bekabelde als draadloze netwerken. Als u de communicatie wilt Exchange Online, gebruikt u de IP-adresbereiken in Office 365 [URL's en IP-adresbereiken.](urls-and-ip-address-ranges.md)
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online en IPv6

 **Office 365 Government G1/G3/G4/K1** Als het programma dat u gebruikt om verbinding te maken met SharePoint Online IPv6 ondersteunt, wordt standaard geprobeerd IPv6 te gebruiken.
  
 **Openbare cloud met meerdere tenants** Microsoft schakelt SharePoint online IPv6 op uw verzoek in. U moet de IP-adressen met cidr-noteerde ip-adressen voor de DNS-infrastructuur van uw organisatie verstrekken. Houd er rekening mee dat deze DNS-infrastructuur niet kan worden gedeeld door andere organisaties, zodat IPv6 kan worden ingeschakeld voor uw tenant. Nadat IPv6 is ingeschakeld en het programma dat u gebruikt om verbinding te maken met SharePoint Online IPv6 ondersteunt, wordt IPv6 standaard gebruikt.
  
Als het programma dat u gebruikt om verbinding te maken met SharePoint Online IPv6 ondersteunt, wordt IPv6 standaard gebruikt op zowel bekabelde als draadloze netwerken. Als u de communicatie naar SharePoint Online wilt controleren, gebruikt u de IP-adresbereiken in Office 365 [URL's en IP-adresbereiken.](urls-and-ip-address-ranges.md)
  
 **Office 365 Government G1/G3/G4/K1** Als het programma dat u gebruikt om verbinding te maken met SharePoint Online IPv6 ondersteunt, wordt standaard geprobeerd IPv6 te gebruiken.
  
### <a name="skype-for-business-and-ipv6"></a>Skype voor Bedrijven en IPv6

Houd er rekening mee dat IPv6 niet wordt ondersteund in Skype voor Bedrijven en niet meer kan worden ingeschakeld.

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams en IPV6

Microsoft Teams Directe routering ondersteunt alleen IPv4. De Microsoft Teams service en client ondersteunen zowel IPv4 als IPv6. Als u de communicatie wilt Microsoft Teams, gebruikt u de IP-adresbereiken in Office 365 [URL's en IP-adresbereiken.](urls-and-ip-address-ranges.md)
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection en IPv6

Exchange Online Protection (EOP) ondersteunt IPv6 als de overdracht plaatsvindt via Transport Layer Security Protocol. Gebruik voor het EOP-bereik [Office 365 URL's en IP-adresbereiken.](urls-and-ip-address-ranges.md)
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>IPv6-ondersteuning voor Office 365 overheidsaanbiedingen

Office 365 IPv6-ondersteuning voor overheidsaanbiedingen voldoet aan de Office of Management and Budget (OMB) Memo for Chief Information Officers of Executive Departments and Agencies, evenals de federale overheid Adoption of Internet Protocol Version 6 (IPv6) memo. [Microsoft Office 365 voor overheid](https://go.microsoft.com/fwlink/p/?LinkId=325414) is een service met meerdere tenants die gegevens van de Amerikaanse overheid opgeslagen in een gescheiden communitycloud. Net als Office 365 biedt het product productiviteits- en samenwerkingsservices, zoals Exchange Online, Skype voor Bedrijven, SharePoint Online en Microsoft 365-apps voor ondernemingen. 

De Microsoft Office 365 overheidsaanbiedingen zijn alleen van toepassing voor 2013 en hoger. Voor meer informatie over het Office 365 overheidsaanbiedingen, zie Aankondiging Office 365 voor de [overheid: Een](https://go.microsoft.com/fwlink/p/?LinkId=325414)Amerikaanse Government Community Cloud. International Traffic in Arms Regulations (ITAR) is een reeks Amerikaanse overheidsvoorschriften die de export en import van defensiegerelateerde artikelen en services op de United [States Munitions List (USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415)bepalen. 

Microsoft Office 365 for Enterprises biedt speciale hostingservices voor Microsoft-productiviteitsoplossingen ter ondersteuning van de beveiligings-, privacy- en nalevingsvereisten voor Amerikaanse federale agentschappen die een FISMA-certificering (Federal Information Security Management) vereisen en commerciële entiteiten die onderworpen zijn aan ITAR.
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>Dingen waar u rekening mee moet houden bij het gebruik van IPv6 en Office 365

U wordt aangeraden IPv6 niet uit te schakelen. Zie dit artikel met [richtlijnen voor meer informatie.](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users) Als u wilt bepalen welke IP-versies in uw netwerk worden gebruikt, gaat u als volgt te werk:
  
- Als de weergave van de **IPConfig-opdracht** bij de opdrachtprompt rijen bevat met de naam 'IPv6-adres' of 'Tijdelijk IPv6-adres', hebt u IPv6 in uw omgeving.

- Als alle IPv6-adressen beginnen met 'fe80' en overeenkomen met rijen met de naam 'Link-Local IPv6 Address', hebt u geen IPv6 in uw omgeving.

Deze overwegingen kunnen van toepassing zijn op uw netwerk:
  
- De openbare abonnementsservice biedt geen ondersteuning voor aankopen met een creditcard via IPv6. Dit geldt niet voor de Government Community Cloud (GCC) omdat overheden Enterprise Agreement (EA) licenties hebben.

- IPv6 biedt geen ondersteuning voor sommige RMS-scenario's (Rights Management Services).

- IPv6 biedt geen ondersteuning voor BlackBerry® Enterprise Server (BES), omdat BlackBerry geen ondersteuning biedt voor IPv6.

- Als u Active Directory Federation Services (AD FS) gebruikt met Office 365, wordt reclame maken voor het AD FS-netwerk-eindpunt niet ondersteund Office 365 met IPv6. U moet AAAA-records niet opnemen in de AD FS DNS-vermelding bij het gebruik van Exchange Online. 

Met deze korte koppeling kunt u teruggaan: [https://aka.ms/o365ip6]()
  
## <a name="see-also"></a>Zie ook

[IPv6 Learning Roadmap](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[IPv6 Survival Guide](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)