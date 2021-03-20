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
description: Meer informatie over de Algemene verordening gegevensbescherming (AVG) die van toepassing is op de persoonlijke gegevens van minderjarigen.
ms.openlocfilehash: c49ea719bc85166cc8082200eb833273b0ab5835
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915252"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>Minderjarigen en het verkrijgen van invoegtoepassingen uit de Store

De Algemene Verordening Gegevensbescherming (AVG) is een Europese verordening die in werking treedt op 25 mei 2018. De AVG biedt gebruikers rechten en beveiliging van hun gegevens. Eén van de aspecten van de AVG is dat persoonsgegevens van minderjarigen niet kunnen worden verzonden naar partijen die niet zijn goedgekeurd door de ouders of voogd. Wat de specifieke leeftijd is om iemand als minderjarig aan te merken, hangt af van het gebied waar de persoon zich bevindt.
  
In de Verenigde Staten, Zuid-Korea, het Verenigd Koninkrijk en de Europese Unie zijn er bijvoorbeeld wettelijke voorschriften voor ouderlijke toestemming. In deze gebieden wordt een minderjarige geblokkeerd (via Azure Active Directory) om nieuwe Office-invoegtoepassingen in de Store te verkrijgen en eerder aangeschafte invoegtoepassingen uit te voeren. In landen zonder wettelijke voorschriften zijn er geen downloadbeperkingen.
  
Een gebruiker wordt als minderjarige aangemerkt op basis van gegevens die zijn opgegeven in Azure Active Directory. De organisatiebeheerder is verantwoordelijk voor het declareren van de wettelijke leeftijdsgroep en de ouderlijke toestemming voor die gebruiker.
  
Als de ouder/voogd toestemming geeft voor een minderjarige met een specifieke invoegvoeging, kan de organisatiebeheerder gecentraliseerde implementatie gebruiken om die invoegvoeging te implementeren voor alle minderjarigen die toestemming hebben.
  
Als u wilt dat uw school of organisatie voldoet aan de AVG-vereisten voor minderjarigen, moet een van de volgende versies van Office zijn geïmplementeerd in uw school/organisatie.
 
 **Voor Word, Excel, PowerPoint en Project**: 

|**Platform** <br/> |**Buildnummer** <br/> |
|:-----|:-----|
|Microsoft 365 Apps for enterprise (Current Channel)  <br/> |9001.2138   <br/> |
|Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)  <br/> |8431.2159  <br/> |
|Office 2016 voor Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 voor Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 voor Mac  <br/> |16.11.18020200  <br/> |
|Webversie van Office  <br/> |N.v.t.  <br/> |
   
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
  
Word, Excel en PowerPoint 2013 voor Windows ondersteunen dezelfde secundaire controles als Active Directory Authentication Library (ADAL) is ingeschakeld. Er zijn twee opties voor naleving, zoals hierna wordt beschreven.
  
- **ADAL inschakelen**. In dit artikel wordt uitgelegd hoe u ADAL voor Office 2013 kunt inschakelen: Moderne verificatie van [Microsoft 365 gebruiken met Office-clients.](../../enterprise/modern-auth-for-office-2013-and-2016.md)<br/>U hebt ook de registersleutels nodig om ADAL in te schakelen, zoals wordt beschreven in [Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten](../security-and-compliance/enable-modern-authentication.md).<br/>Daarnaast moet u deze updates van april voor Office 2013 installeren:
    
  - [Beschrijving van de beveiligingsupdate voor Outlook 2013: 10 april 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [3 april 2018, update voor Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Schakel ADAL niet in.** Als u ADAL niet kunt inschakelen in Office 2013, is het onze aanbeveling om groepsbeleid te gebruiken om de Store voor de Office-clients uit te schakelen. Informatie over het uitschakelen van de app voor Office-instellingen vindt u [hier](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15)).

## <a name="related-articles"></a>Verwante artikelen

[Invoegtoepassingen implementeren in het beheercentrum](./manage-deployment-of-add-ins.md)

[Invoegtoepassingen beheren in het beheercentrum](./manage-addins-in-the-admin-center.md)
