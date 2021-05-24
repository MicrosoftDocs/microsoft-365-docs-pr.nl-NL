---
title: Een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365 beheercentrum
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Informatie over het maken, bewerken of verwijderen van een beveiligingsgroep.
ms.openlocfilehash: 7887a6371287ebef3a91cc1a37f2ed696df1948d
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623999"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a>Een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365 beheercentrum

Op de Microsoft 365 **groepen** kunt u groepen gebruikersaccounts maken die u kunt gebruiken om dezelfde machtigingen toe te wijzen in SharePoint Online en CRM Online. Een beheerder kan bijvoorbeeld een beveiligingsgroep maken om een bepaalde groep personen toegang te verlenen tot een SharePoint site. Alleen globale beheerders en beheerders van gebruikersbeheer hebben machtigingen voor het maken, bewerken of verwijderen van beveiligingsgroepen. Zie Beheerdersrollen toewijzen voor meer informatie over [beheerdersrollen.](../add-users/assign-admin-roles.md) 
  
Er zijn ook [Groepen in Exchange Online en SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) die u kunt gebruiken om e-mail te verzenden of machtigingen toe te wijzen aan een groep gebruikers, en [Groepen in Exchange Online en SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) waarmee u gebruikers rechten en toegang kunt geven tot sites en siteverzamelingen. 
  
> [!IMPORTANT]
>  Bent u van plan sitepostvakken te gebruiken? Alle gebruikers die zijn toegevoegd aan een SharePoint-site via een beveiligingsgroep in plaats van individueel, kunnen het sitepostvak alleen gebruiken vanuit SharePoint. Deze gebruikers hebben geen toegang tot het sitepostvak vanuit Outlook. Zie Groepen gebruiken Microsoft 365 in plaats van [teampostvakken](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)voor meer informatie. 
  
## <a name="manage-security-groups-in-the-admin-center"></a>Beveiligingsgroepen beheren in het beheercentrum

### <a name="add-a-security-group"></a>Een beveiligingsgroep toevoegen

1. Ga in Microsoft 365 beheercentrum naar de pagina  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groepengroepen.</a>
  
2. Selecteer op **de** pagina Groepen de optie **Een groep toevoegen.**
    
3. Kies op **de pagina Een groeptype** kiezen de optie **Beveiliging**. 
    
4. Volg de stappen om het maken van de groep te voltooien. 
 
### <a name="add-members-to-a-security-group"></a>Leden toevoegen aan een beveiligingsgroep
    
1. Selecteer de naam van de beveiligingsgroep op **de** pagina Groepen en selecteer op **het** tabblad Leden de optie Alle leden weergeven **en leden beheren.** 
    
2. Selecteer in het groepsdeelvenster Leden **toevoegen** en kies de persoon in de lijst  of typ de naam van de persoon die u wilt toevoegen in het vak Zoeken en selecteer **vervolgens Opslaan.**
    
    Als u leden wilt verwijderen, selecteert u de X naast de naam. 
  
### <a name="edit-a-security-group"></a>Een beveiligingsgroep bewerken

1. Ga in het beheercentrum  naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groepen groepen.</a>
  
2. Selecteer op **de** pagina Groepen de naam van de groep. 
    
3. Selecteer in het instellingenvenster **het** tabblad Algemeen of het tabblad **Leden** om groepsdetails of leden te bewerken.

### <a name="delete-a-security-group"></a>Een beveiligingsgroep verwijderen

1. Ga in het beheercentrum naar de pagina  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groepen groepen.</a>
    
2. Selecteer op **de** pagina Groepen de naam van de groep. 
    
3. Selecteer **Groep verwijderen** (pictogram wasetbin) en bevestig vervolgens door Verwijderen te **selecteren.**
    
    Selecteer **Sluiten zodra** de groep is verwijderd. 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a>Groepen in Exchange Online en SharePoint Online

Als u groepen gebruikers wilt maken zodat u tegelijkertijd e-mail naar hen kunt verzenden, kunt u dat doen in het Exchange-beheercentrum door naar **Beheerders** Exchange Groepen geadresseerden te \>  \>  \> **gaan.** Selecteer vervolgens **Nieuw** ![ toevoegen en selecteer het type groep dat u wilt ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) maken: 
  
- **Distributiegroep**: deze groep wordt gebruikt om berichten te verzenden naar een groep gebruikers. Het wordt ook wel een *distributiegroep met e-mail* of een *distributielijst genoemd.* Zie Distributiegroepen beheren voor [meer informatie.](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
    
- **Beveiligingsgroep**: deze groep kan worden gebruikt om berichten te verzenden naar een groep gebruikers of om toegangsrechten te verlenen aan resources. Deze groep wordt ook wel een *beveiligingsgroep met e-mail genoemd.* Zie Beveiligingsgroepen met [e-mail beheren](/Exchange/recipients/mail-enabled-security-groups)voor meer informatie.
    
- **Dynamische distributiegroep**: dit is een type distributiegroep waarbij de lijst met geadresseerden telkens opnieuw berekend wanneer u een bericht verzendt op basis van filters en voorwaarden die u opgeeft. Zie Dynamische distributiegroepen beheren voor [meer informatie.](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups)
    
Nadat u distributiegroepen en beveiligingsgroepen met e-mail hebt gemaakt in het Exchange beheercentrum, worden hun namen en gebruikerslijsten weergegeven op de pagina **Beveiligingsgroepen.** U kunt deze groepen op beide locaties verwijderen, maar u kunt ze alleen bewerken in het Exchange-beheercentrum. Dynamische distributiegroepen worden niet weergegeven op de pagina **Beveiligingsgroepen.** 
  
 SharePoint-groepen worden automatisch gemaakt wanneer u een siteverzameling maakt. De standaardgroepen gebruiken de standaardmachtigingsniveaus in SharePoint (soms ook wel SharePoint-rollen genaamd) om gebruikers rechten en toegang te verlenen. Zie Standaardgroepen in [SharePoint online SharePoint voor meer informatie.](/sharepoint/default-sharepoint-groups)
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a>Hoe verschilt een beveiligingsgroep van beveiligingsgroepen die ik maak in SharePoint?

Beveiligingsgroepen kunnen worden gebruikt met SharePoint, Exchange, MDM, Windows en meer. Een beveiligingsgroep die u in SharePoint maakt, wordt alleen erkend door die SharePoint-siteverzameling.
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a>Moet ik beveiligingsgroepen gebruiken om mijn organisatie te beveiligen?

Nee, dit is slechts een extra manier waarop u de beveiliging voor uw organisatie kunt beheren. U kunt altijd gebruikersmachtigingen en toegang tot sites op individuele basis verlenen. Met beveiligingsgroepen kunt u echter gemakkelijk grotere groepen gebruikers beheren.
  
## <a name="can-i-send-email-to-a-security-group"></a>Kan ik e-mail verzenden naar een beveiligingsgroep?

Ja. Maar als u groepen wilt gebruiken voor e-mail en samenwerking, raden we u aan in plaats daarvan een Microsoft 365 [maken.](../create-groups/create-groups.md) 

## <a name="related-content"></a>Verwante onderwerpen

[Een groep maken in het Microsoft 365 beheercentrum](../create-groups/create-groups.md) (artikel)\
[Uitleg over Microsoft 365 groepen aan uw gebruikers](../create-groups/explain-groups-knowledge-worker.md) (artikel)\
[Een groep beheren in het Microsoft 365 beheercentrum](../create-groups/manage-groups.md) (artikel)