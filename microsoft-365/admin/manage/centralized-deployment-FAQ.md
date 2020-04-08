---
title: Veelgestelde vragen over gecentraliseerde implementatie
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
description: Bekijk de antwoorden op veelgestelde vragen over gecentraliseerde implementatie vanuit het Microsoft 365-beheercentrum.
ms.openlocfilehash: 313e1dd7481ccdd8bbf7531d5b7433f8bbd54e38
ms.sourcegitcommit: 732bb72a0b5ae09cb39536185aa29d6097ec72fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2020
ms.locfileid: "43188972"
---
# <a name="centralized-deployment-faq"></a>Veelgestelde vragen over gecentraliseerde implementatie

Gecentraliseerde implementatie is de aanbevolen manier voor een Office 365-beheerder om Office-invoegtoepassing (Word, Excel, PowerPoint en Outlook) te implementeren voor gebruikers en groepen binnen een organisatie, op voorwaarde dat de organisatie voldoet aan alle vereisten voor het gebruik van gecentraliseerde implementatie zoals beschreven in dit artikel.   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>Hoe weet ik of mijn organisatie is ingesteld voor gecentraliseerde implementatie?  

Voor een gecentraliseerde implementatie van invoegingen moeten gebruikers Office 365 ProPlus gebruiken (en zijn aangemeld bij Office met hun inloggegevens voor de organisatie) en exchange online-postvakken hebben. Uw abonnementsmap moet zich in Azure Active Directory bevinden of worden gefedereerd.  
 
Gecentraliseerde implementatie wordt alleen ondersteund voor online postvakken. Het ondersteunt geen implementatie naar on-premises Exchange-postvakken.
 
U de [office 365-controlecompatibiliteitscontrole](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker) voor gecentraliseerde implementatie gebruiken om te bepalen of uw abonnement in aanmerking komt. 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>Hoe target u invoegtoepassinggebruikerstoewijzingen met gecentraliseerde implementatie?  

Gecentraliseerde implementatie ondersteunt toewijzingen aan individuele gebruikers, groepen en iedereen in de tenant. Gecentraliseerde implementatie kan worden gebruikt voor gebruikers in groepen of groepen op het hoogste niveau zonder bovenliggende groepen, maar niet voor gebruikers in geneste groepen of groepen met bovenliggende groepen. Gecentraliseerde implementatie maakt ook deel uit van de meeste Azure Active Directory-groepen, waaronder Office 365-groepen, distributielijsten en beveiligingsgroepen.  

Het is beter om groepstoewijzingen te gebruiken in plaats van individuele gebruikerstoewijzing voor eenvoudiger beheer.
 
Zie [Gebruikers- en groepstoewijzingen](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments)voor meer informatie.  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>Hoe lang duurt het voordat invoegingen voor alle gebruikers worden weergegeven?  

Het kan tot 24 uur duren voordat een invoegtoepassing voor alle gebruikers wordt weergegeven. Het kan evenveel tijd in beslag nemen voor invoegupdates, wijzigingen vanaf het in- of uitschakelen of invoegingsverwijderingen. 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>Hoe beheer ik als beheerder de toegang van de gebruiker tot invoegingen voor mijn organisatie?

Voor eenvoudige implementatie van invoegingen voor gebruikers, groepen of uw hele organisatie, raden we beheerders aan gecentraliseerde implementatie te gebruiken.

Zie voor meer informatie over het beheren van gebruikerstoegang </br>[Invoegdownloads voorkomen door de Office Store voor alle clients uit te schakelen (behalve Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook) en </br>[Geef de beheerders en gebruikers op die invoegingen voor Outlook kunnen installeren en beheren.](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins?redirectedfrom=MSDN)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>Biedt gecentraliseerde implementatie beheerders de flexibiliteit om de implementatiemethode voor Outlook-invoegins te kiezen?  

Ja. Gecentraliseerde implementatie biedt beheerders de flexibiliteit om een van de drie implementatiemethoden te kiezen voor Outlook-invoegtoepassing tijdens de invoegtoepassing:

**Fixed (Default)**   The inis is automatically ployed to the assigned users, they cannot remove it.  
 
**Beschikbaar** Gebruikers kunnen de invoegtoepassing in Outlook installeren door Home > Get More-ins te kiezen > beheerde beheerder.   
 
**Optioneel** De invoegtoepassing wordt automatisch geïmplementeerd voor de toegewezen gebruikers, maar ze kunnen ervoor kiezen om de invoeging te verwijderen.  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>Kunnen beheerders lob-invoegingen (Line-of-Business) bijwerken?  

Ja. Beheerders kunnen een nieuw manifestbestand uploaden ter ondersteuning van metagegevenswijzigingen voor door de beheerder geïmplementeerde LOB-invoegingen. De invoegtoepassing wordt bijgewerkt wanneer de Office-toepassingen de volgende keer worden gestart. De webtoepassing kan elk moment worden gewijzigd.  
 
Zie [line-of-business add-in voor](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#security-of-office-add-ins)meer informatie.  

## <a name="can-admins-turn-off-add-ins"></a>Kunnen beheerders invoegtoepassing uitschakelen?  

Ja. Beheerders kunnen de invoegingen die ze implementeren voor alle gebruikers vanuit het Microsoft-beheercentrum in- of uitschakelen.

Zie [Invoegstatussen voor](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#add-in-states)meer informatie .  

##  <a name="can-admins-delete-or-remove-add-ins"></a>Kunnen beheerders invoegfouten verwijderen of verwijderen?

Ja. Beheerders kunnen invoegingen die ze hebben geïmplementeerd voor alle gebruikers verwijderen uit het Microsoft-beheercentrum.

Zie [De invoegtoepassing verwijderen](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#delete-the-add-in)voor meer informatie . 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>Kunnen beheerders betaalde invoegingen implementeren vanuit de Office Store met behulp van gecentraliseerde implementatie? 

Nee. U op dit moment geen betaalde invoegingen uit de Office Store implementeren met gecentraliseerde implementatie.  
 
We raden u aan contact op te nemen met de ISV-ontwikkelaar voor de betaalde invoegtoepassing om een manifestbestand of een URL aan te vragen. De tenantbeheerder kan de invoegtoepassing vervolgens implementeren als EEN LOB-invoegtoepassing met behulp van gecentraliseerde implementatie.
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>Welke beheerdersrol heb ik nodig om invoegingen voor mijn organisatie te beheren?  

U moet de globale beheerrol hebben om invoegingen te beheren. Als u de persoon bent die uw Microsoft 365 voor Bedrijven-abonnement heeft gekocht, bent u de globale beheerder. 
 
Uw abonnement wordt geleverd met een reeks beheerdersrollen die u toewijzen aan andere gebruikers in uw organisatie. Elke beheerrol wordt toegewezen aan algemene bedrijfsfuncties en geeft mensen in uw organisatie machtigingen om specifieke taken uit te voeren in het Microsoft 365-beheercentrum.  
 
Zie [Beheerdersrollen toewijzen](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide)voor meer informatie .  