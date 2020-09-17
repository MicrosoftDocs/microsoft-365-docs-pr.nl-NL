---
title: Veelgestelde vragen over Gecentraliseerde implementatie
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
description: Bekijk de antwoorden op veelgestelde vragen over gecentraliseerde implementatie in het Microsoft 365-Beheercentrum.
ms.openlocfilehash: 555496f15663b6607ebc785498bdc94b5e51b9c9
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948686"
---
# <a name="centralized-deployment-faq"></a>Veelgestelde vragen over Gecentraliseerde implementatie

Gecentraliseerde implementatie is de aanbevolen manier voor een Office 365-beheerder om Office-invoegtoepassingen (Word, Excel, PowerPoint en Outlook) te implementeren voor gebruikers en groepen binnen een organisatie, mits de organisatie voldoet aan alle vereisten voor het gebruik van gecentraliseerde implementatie zoals in dit artikel wordt beschreven.   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>Hoe weet ik of mijn organisatie is geconfigureerd voor gecentraliseerde implementatie?  

Gecentraliseerde implementatie van invoegtoepassingen vereist dat gebruikers Microsoft 365-apps gebruiken voor Enterprise (en zijn aangemeld bij Office met hun organisatie inlog referenties) en Exchange Online-postvakken hebben. Uw abonnements gids moet zich in de map bevinden, of federatief, Azure Active Directory.  
 
Gecentraliseerde implementatie wordt alleen ondersteund voor Online postvakken. Het biedt geen ondersteuning voor de implementatie van on-premises Exchange-postvakken.

U kunt de [compatibiliteitscontrole voor gecentraliseerde implementatie](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)gebruiken   om te bepalen of uw abonnement in aanmerking komt. 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>Hoe kan ik de Gebruikerstoewijzingen van de invoegtoepassing richten met gecentraliseerde implementatie?  

Gecentraliseerde implementatie ondersteunt opdrachten voor afzonderlijke gebruikers, groepen en iedereen in de Tenant. Gecentraliseerde implementatie kan worden gebruikt voor gebruikers in groepen van het hoogste niveau of groepen zonder bovenliggende groepen, maar niet voor gebruikers in geneste groepen of groepen met bovenliggende groepen. Gecentraliseerde implementatie maakt ook deel uit van de meeste Azure Active Directory-groepen, waaronder Office 365-groepen, distributielijsten en beveiligingsgroepen.  

U kunt beter de toewijzingen groepen gebruiken in plaats van afzonderlijke gebruikers opdrachten voor eenvoudiger beheer.
 
Zie [toewijzingen van gebruikers en groepen](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments)voor meer informatie.  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>Hoe lang duurt het voordat invoegtoepassingen worden weergegeven voor alle gebruikers?  

Het kan tot 24 uur duren voordat een invoegtoepassing voor alle gebruikers wordt weergegeven. Het kan even duren voor updates van de invoegtoepassing, de wijzigingen van de optie voor het in-of uitschakelen van de invoegtoepassing of het verwijderen van de invoegtoepassing. 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>Hoe kan ik de toegang van gebruikers tot invoegtoepassingen voor mijn organisatie beheren?

Voor een eenvoudige implementatie van invoegtoepassingen aan gebruikers, groepen en de hele organisatie raden wij beheerders aan gecentraliseerde implementatie te gebruiken.

Zie voor meer informatie over het beheren van gebruikers toegang:
 - [Downloads van invoegtoepassingen voorkomen door Office Store op alle clients uit te schakelen (met uitzondering van Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [Beheerders en gebruikers opgeven die invoegtoepassingen voor Outlook kunnen installeren en beheren](https://docs.microsoft.com/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>Zorgt gecentraliseerde implementatie voor beheerders de flexibiliteit voor het kiezen van de implementatiemethode voor Outlook-invoegtoepassingen?  

Ja. Gecentraliseerde implementatie biedt beheerders de flexibiliteit voor het kiezen van een van de volgende drie implementatiemethoden voor Outlook-invoegtoepassingen tijdens de implementatie van invoegtoepassingen:

**Vast (standaard)**   De invoegtoepassing wordt automatisch geïmplementeerd voor de toegewezen gebruikers en kan deze niet verwijderen.  
 
**Beschikbaar** Gebruikers kunnen de invoegtoepassing in Outlook installeren door **start > meer invoegtoepassingen voor het beheren van beheerders te kiezen > beheerbare beheerder**.
 
**Optioneel** De invoegtoepassing wordt automatisch geïmplementeerd voor de toegewezen gebruikers, maar ze kunnen de optie wel verwijderen.  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>Kunnen beheerdersupdate van line-of-Business-invoegtoepassingen (LOB) toevoegen?  

Ja. Beheerders kunnen een nieuw manifestbestand uploaden om wijzigingen in de metagegevens van door de beheerder geïmplementeerde LOB-invoegtoepassingen te ondersteunen. De invoegtoepassing wordt bijgewerkt wanneer de Office-toepassingen de volgende keer worden gestart. De webtoepassing kan elk moment worden gewijzigd.  
 
Zie [line-of-Business-invoegtoepassing](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#more-about-office-add-ins-security)voor meer informatie.  

## <a name="can-admins-turn-off-add-ins"></a>Kunnen beheerders invoegtoepassingen uitschakelen?  

Ja. Beheerders kunnen de invoegtoepassingen die ze voor alle gebruikers implementeren, in-of uitschakelen via het Microsoft-Beheercentrum.

Zie [Staten van invoegtoepassingen](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#add-in-states)voor meer informatie.  

##  <a name="can-admins-delete-or-remove-add-ins"></a>Kunnen beheerders invoegtoepassingen verwijderen of verwijderen?

Ja. Beheerders kunnen invoegtoepassingen verwijderen die ze voor alle gebruikers in het Microsoft-Beheercentrum hebben geïmplementeerd.

Zie [een invoegtoepassing verwijderen](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#delete-an-add-in)voor meer informatie. 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>Kunnen beheerders betaalde invoegtoepassingen implementeren vanuit de Office Store met behulp van gecentraliseerde implementatie? 

Nee. Op dit moment kunt u betaalde invoegtoepassingen in de Office Store niet implementeren met behulp van gecentraliseerde implementatie.  
 
We raden u aan om bij de ISV-ontwikkelaar voor de betaalde invoegtoepassing een manifestbestand of een URL aan te vragen. De tenantbeheerder kan de invoegtoepassing vervolgens implementeren als een LOB-invoegtoepassing met gecentraliseerde implementatie.
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>Welke beheerdersrol heb ik nodig voor het beheren van invoegtoepassingen voor mijn organisatie?  

Globale beheerder is de aanbevolen rol met volledige toegang tot de beheer levensduur van de invoegtoepassing. Andere beheerdersrollen hebben een beperkte toegang tot de implementatie levensduur van de invoegtoepassing. Als u de persoon bent die uw abonnement op Microsoft 365 for Business heeft aangeschaft, bent u de globale beheerder. 
 
Uw abonnement bevat een reeks beheerdersrollen die u kunt toewijzen aan andere gebruikers in uw organisatie. Elke beheerdersrol is toegewezen aan veelvoorkomende zakelijke functies en geeft personen in uw organisatie machtigingen voor het uitvoeren van bepaalde taken in het Microsoft 365-Beheercentrum.  
 
Zie [beheerdersrollen toewijzen](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide)voor meer informatie.  


