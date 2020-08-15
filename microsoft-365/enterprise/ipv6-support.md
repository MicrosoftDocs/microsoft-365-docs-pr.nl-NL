---
title: IPv6-ondersteuning in Office 365-Services
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
description: 'Overzicht: hier wordt de IPv6-ondersteuning in Microsoft Office 365-onderdelen en in de Office 365-aanbiedingen voor de overheid beschreven.'
ms.openlocfilehash: c4ecd2ef26ecf660eb1d172b1951907724d2238a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689108"
---
# <a name="ipv6-support-in-office-365-services"></a>IPv6-ondersteuning in Office 365-Services

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

In Office 365 worden zowel IPv6 als IPv4 ondersteund. niet alle functies van Office 365 zijn echter volledig ingeschakeld met IPv6. Dit betekent dat u IPv4 en IPv6 moet gebruiken om verbinding te maken met Office 365. Als u uw uitgaande verkeer filtert naar Office 365, vindt u de volledige lijst met IPv6-adressen die worden ondersteund door Office 365 in het artikel [Office 365-url's en IP-](urls-and-ip-address-ranges.md)adresbereiken. Nadat het netwerk is geconfigureerd en de juiste IPv6-adressen zijn toegestaan, kunt u het [Office 365 IPv6-testplan](https://go.microsoft.com/fwlink/?LinkId=293447) downloaden van het Microsoft Downloadcentrum.
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>IPv6-ondersteuning in Office 365-abonnementsservice

### <a name="exchange-online-and-ipv6"></a>Exchange Online en IPv6

Als het programma dat u gebruikt om verbinding te maken met Exchange Online ondersteuning biedt voor IPv6, wordt standaard IPv6 gebruikt op zowel bekabelde als draadloze netwerken. Als u communicatie met Exchange Online wilt regelen, gebruikt u de IP-adresbereiken in [Office 365-url's en IP-](urls-and-ip-address-ranges.md)adresbereiken.
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online en IPv6

 **Office 365 Government G1/G3/G4/K1** Als het programma dat u gebruikt om verbinding te maken met SharePoint Online ondersteuning biedt voor IPv6, wordt standaard IPv6 gebruikt.
  
 **Openbare wolk met meerdere tenants** Microsoft schakelt SharePoint Online IPv6 op uw verzoek in. U moet de bekroonde IP-adressen voor de DNS-infrastructuur van uw organisatie invoeren. Houd er rekening mee dat deze DNS-infrastructuur niet kan worden gedeeld door andere organisaties voor IPv6 die moet worden ingeschakeld voor uw Tenant. Wanneer IPv6 is ingeschakeld, wordt in het programma dat u gebruikt om verbinding te maken met SharePoint, standaard IPv6 gebruikt.
  
Als het programma dat u gebruikt om verbinding te maken met SharePoint Online ondersteuning biedt voor IPv6, wordt standaard IPv6 gebruikt op zowel bekabelde als draadloze netwerken. Als u communicatie met SharePoint Online wilt beheren, gebruikt u de IP-adresbereiken in [Office 365-url's en IP-](urls-and-ip-address-ranges.md)adresbereiken.
  
 **Office 365 Government G1/G3/G4/K1** Als het programma dat u gebruikt om verbinding te maken met SharePoint Online ondersteuning biedt voor IPv6, wordt standaard IPv6 gebruikt.
  
### <a name="skype-for-business-and-ipv6"></a>Skype voor bedrijven en IPv6

Houd er rekening mee dat IPv6 niet in Skype voor bedrijven wordt ondersteund en niet meer kan worden ingeschakeld.
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection en IPv6

Exchange Online Protection (EOP) ondersteunt IPv6 als de transmissie plaatsvindt via het beveiligings protocol voor Transport Layer. Voor het EOP-bereik gebruikt u [Office 365-url's en IP-](urls-and-ip-address-ranges.md)adresbereiken.
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>IPv6-ondersteuning voor Office 365 Government-aanbiedingen

De IPv6-ondersteuning voor Office 365 IPv6 voor de aanbiedingen van de overheid in overeenstemming met de Office-OMB en de budget () memorandum voor senior informatie ambtenaren van leidinggevende afdelingen en agentschappen, en de aanneming van de overheid, en de aanneming van de overheid versie 6 (IPv6), en de nationale overheid. [Microsoft Office 365 voor de overheid](https://go.microsoft.com/fwlink/p/?LinkId=325414) is een service voor meerdere tenants die de gegevens van de overheid in een gemeeneerde wolk met bescheidte community's opslaat. Net als bij andere Office 365-aanbiedingen, biedt dit de productiviteits-en samenwerkingsservices, waaronder Exchange Online, Skype voor bedrijven, SharePoint Online en Microsoft 365-apps voor Enterprise. 

De aanbiedingen van Microsoft Office 365 Government zijn alleen van toepassing op 2013 en later. Zie voor meer informatie over de Office 365 Government-aanbiedingen de [aankondiging van Office 365 voor de overheid: een community-wolk met de VS-overheid](https://go.microsoft.com/fwlink/p/?LinkId=325414). Internationaal verkeer in de wapen reglementering (ITAR) is een set Amerikaanse Government verordeningen waarmee de export en de invoer van beveiligingskwesties en-diensten in de [Verenigde Staten Munitions List (USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415)wordt beheerd. 

Microsoft Office 365 voor ondernemingen biedt gespecialiseerde Microsoft-oplossingen voor Microsoft-productiviteits oplossingen ter ondersteuning van de vereisten voor beveiliging, privacy en compliance van Amerikaanse federale overheidsinstanties die wettelijk Information Security Management (FISMA)-certificering en commerciële entiteiten onderhevig hebben aan ITAR.
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>Aandachtspunten bij het gebruik van IPv6 en Office 365

U wordt aangeraden IPv6 niet uit te schakelen. Zie dit [artikel](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users)voor meer informatie. Ga als volgt te werk om te bepalen welke IP-versies worden gebruikt op uw netwerk:
  
- Als de weergave van de opdracht **ipconfig** op de opdrachtprompt rijen bevat met de naam IPv6-adres of tijdelijk IPv6-adres, gebruikt u IPv6 in uw omgeving.

- Als alle IPv6-adressen beginnen met ' FE80 ' en overeenkomen met rijen met de naam link-local IPv6-adres, gebruikt u IPv6 niet in uw omgeving.

Deze overwegingen kunnen van toepassing zijn op uw netwerk:
  
- De service openbare abonnement biedt geen ondersteuning voor aankopen met een creditcard via IPv6. Dit geldt niet voor de Government Community Cloud (GCC), omdat de overheid Enterprise Agreement (EA)-licentie heeft.

- IPv6 biedt geen ondersteuning voor een aantal RMS-scenario's (Rights Management Services).

- IPv6 biedt geen ondersteuning voor BlackBerry® Enterprise Server (BES) omdat BlackBerry geen ondersteuning biedt voor IPv6.

- Als u AD FS (Active Directory Federation Services) gebruikt met Office 365, adverteert u uw AD FS-netwerkeindpunt met Office 365 via IPv6 wordt niet ondersteund. U mag geen AAAA-records opnemen in de AD FS DNS-vermelding wanneer u Exchange Online gebruikt. 

Met deze korte koppeling kunt u teruggaan: [https://aka.ms/o365ip6](https://aka.ms/o365ip6)
  
## <a name="see-also"></a>Zie ook

[IPv6-leer schema](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[IPv6-gids voor overleving](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
