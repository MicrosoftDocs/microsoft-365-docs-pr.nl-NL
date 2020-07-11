---
title: Minderjarigen en het verkrijgen van invoegtoepassingen uit de Store
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Meer informatie over de Algemene Verordening Gegevensbescherming (AVG) die de persoonsgegevens van minderjarigen regelt.
ms.openlocfilehash: dcf2c98906830e0007747e2dd90e67b9dc85a5bb
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103092"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>Minderjarigen en het verkrijgen van invoegtoepassingen uit de Store

The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018. It gives users rights to and protection of their data. One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved. The specific age defined as a minor depends on the region where the individual is located.
  
Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union. For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired. For countries without statutory regulations, there will be no download restrictions.
  
Een gebruiker wordt als minderjarige aangemerkt op basis van gegevens die zijn opgegeven in Azure Active Directory. De organisatiebeheerder is verantwoordelijk voor het declareren van de wettelijke leeftijdsgroep en de ouderlijke toestemming voor die gebruiker.
  
Als de ouder/voogd toestemming geeft aan een minderjarige met behulp van een specifieke invoegtoepassing, kan de organisatiebeheerder gecentraliseerde implementatie gebruiken om die invoegtoepassing te implementeren voor alle minderjarigen die toestemming hebben.
  
Als u wilt dat uw school of organisatie voldoet aan de AVG-vereisten voor minderjarigen, moet een van de volgende versies van Office zijn geïmplementeerd in uw school/organisatie.
 
 **Voor Word, Excel, PowerPoint en Project**: 

|**Platform** <br/> |**Buildnummer** <br/> |
|:-----|:-----|
|Microsoft 365-apps voor bedrijven (huidig kanaal)  <br/> |9001.2138   <br/> |
|Microsoft 365 Apps voor bedrijven (halfjaarlijks Bedrijfskanaal)  <br/> |8431.2159  <br/> |
|Office 2016 voor Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 voor Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 voor Mac  <br/> |16.11.18020200  <br/> |
|Office voor het web  <br/> |N.v.t.  <br/> |
   
 **Voor Outlook**: 
  
|**Platform** <br/> |**Buildnummer** <br/> |
|:-----|:-----|
|Outlook 2016 voor Windows (MSI)  <br/> |Buildnummer n.t.b.  <br/> |
|Outlook 2016 voor Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 voor Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook Mobile voor iOS  <br/> |2.75.0  <br/> |
|Outlook Mobile voor Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |N.v.t.  <br/> |

 **Vereisten voor Office 2013**
  
Word, Excel en PowerPoint 2013 voor Windows ondersteunen dezelfde selecties voor minderjarigen als Active Directory Authentication Library (ADAL) is ingeschakeld. Er zijn twee opties voor naleving, zoals hierna wordt beschreven.
  
- **ADAL inschakelen**. In dit artikel wordt uitgelegd hoe u ADAL voor Office 2013 inschakelen: [Microsoft 365 moderne verificatie gebruiken met Office-clients](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).<br/>U hebt ook de registersleutels nodig om ADAL in te schakelen, zoals wordt beschreven in [Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten](../security-and-compliance/enable-modern-authentication.md).<br/>Daarnaast moet u deze updates van april voor Office 2013 installeren:
    
  - [Beschrijving van de beveiligingsupdate voor Outlook 2013: 10 april 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [3 april 2018, update voor Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Schakel ADAL niet in.** Als u ADAL niet inschakelen in Office 2013, is het onze aanbeveling om groepsbeleid te gebruiken om de Store voor de Office-clients uit te schakelen. Informatie over het uitschakelen van de app voor Office-instellingen vindt u [hier](https://technet.microsoft.com/library/cc178992.aspx).

## <a name="related-articles"></a>Verwante artikelen

[Invoegtoepassingen implementeren in het beheercentrum](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[Invoegtoepassingen beheren in het beheercentrum](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
