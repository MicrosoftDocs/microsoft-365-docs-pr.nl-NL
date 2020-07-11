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
description: Bekijk de antwoorden op veelgestelde vragen over gecentraliseerde implementatie vanuit het Microsoft 365-beheercentrum.
ms.openlocfilehash: b1b5ccbb5373bf5d536208efdfe487bc0c872f25
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/11/2020
ms.locfileid: "45102882"
---
# <a name="centralized-deployment-faq"></a>Veelgestelde vragen over Gecentraliseerde implementatie

Gecentraliseerde implementatie is de aanbevolen manier voor een Office 365-beheerder om Office-invoegtoepassingen (Word, Excel, PowerPoint en Outlook) te implementeren voor gebruikers en groepen binnen een organisatie, op voorwaarde dat de organisatie voldoet aan alle vereisten voor het gebruik van Gecentraliseerde implementatie zoals beschreven in dit artikel.   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>Hoe weet ik of mijn organisatie is ingesteld voor gecentraliseerde implementatie?  

Voor gecentraliseerde implementatie van invoegtoepassingen is vereist dat gebruikers Microsoft 365 Apps voor bedrijven gebruiken (en zijn aangemeld bij Office met behulp van hun inloggegevens voor organisatie) en dat ze Exchange Online-postvakken hebben. Uw abonnementsmap moet zich in Azure Active Directory bevinden of aan de federatieve toepassing hebben.  
 
Gecentraliseerde implementatie wordt alleen ondersteund voor online postvakken. Het biedt geen ondersteuning voor implementatie naar on-premises Exchange-postvakken.

U de [gecentraliseerde implementatiecompatibiliteitscontrole](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)gebruiken   om te bepalen of uw abonnement in aanmerking komt. 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>Hoe target u invoegtoepassingen met gecentraliseerde implementatie?  

Gecentraliseerde implementatie ondersteunt toewijzingen aan individuele gebruikers, groepen en iedereen in de tenant. Gecentraliseerde implementatie kan worden gebruikt voor gebruikers in groepen op het hoogste niveau of groepen zonder bovenliggende groepen, maar niet voor gebruikers in geneste groepen of groepen met bovenliggende groepen. Gecentraliseerde implementatie maakt ook deel uit van de meeste Azure Active Directory-groepen, waaronder Office 365-groepen, distributielijsten en beveiligingsgroepen.  

Het is beter om groepstoewijzingen te gebruiken in plaats van individuele gebruikerstoewijzing voor eenvoudiger beheer.
 
Zie [Toewijzingen voor gebruiker en groep](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments)voor meer informatie.  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>Hoe lang duurt het voordat invoegtoepassingen voor alle gebruikers worden weergegeven?  

Het kan tot 24 uur duren voordat een invoegtoepassing voor alle gebruikers wordt weergegeven. Het kan even veel tijd duren voor invoegupdates, wijzigingen bij het inschakelen of uitschakelen of invoegverruimen. 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>Hoe beheer ik als beheerder de gebruikerstoegang tot invoegtoepassingen voor mijn organisatie?

Voor eenvoudige implementatie van invoegtoepassingen voor gebruikers, groepen of uw hele organisatie raden we beheerders aan gecentraliseerde implementatie te gebruiken.

Zie voor meer informatie over het beheren van gebruikerstoegang:
 - [Downloads van invoegtoepassing voorkomen door de Office Store voor alle clients uit te schakelen (behalve Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [Geef de beheerders en gebruikers op die invoegtoepassingen voor Outlook kunnen installeren en beheren](https://docs.microsoft.com/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>Biedt gecentraliseerde implementatie beheerders de flexibiliteit om de implementatiemethode voor Outlook-invoegtoepassingen te kiezen?  

Ja. Gecentraliseerde implementatie biedt beheerders de flexibiliteit om een van de drie implementatiemethoden voor Outlook-invoegtoepassingen te kiezen tijdens de implementatie van de invoegtoepassing:

**Vast (standaard)**   De invoegtoepassing wordt automatisch geïmplementeerd voor de toegewezen gebruikers en kan deze niet verwijderen.  
 
**Beschikbaar** Gebruikers kunnen de invoegtoepassing in Outlook installeren door **home > Meer invoegtoepassingen te**kiezen > beheerde beheerder .
 
**Optioneel** De invoegtoepassing wordt automatisch geïmplementeerd voor de toegewezen gebruikers, maar ze kunnen ervoor kiezen deze te verwijderen.  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>Kunnen beheerders LOB-invoegtoepassingen (Line-of-Business) bijwerken?  

Ja. Beheerders kunnen een nieuw manifestbestand uploaden om wijzigingen in metagegevens te ondersteunen voor door beheerders geïmplementeerde LOB-invoegtoepassingen. De invoegtoepassing wordt bijgewerkt wanneer de Office-toepassingen de volgende keer worden gestart. De webtoepassing kan elk moment worden gewijzigd.  
 
Zie [line-of-business add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#more-about-office-add-ins-security)voor meer informatie.  

## <a name="can-admins-turn-off-add-ins"></a>Kunnen beheerders invoegtoepassingen uitschakelen?  

Ja. Beheerders kunnen de invoegtoepassingen die ze implementeren voor alle gebruikers van het Microsoft-beheercentrum in- of uitschakelen.

Zie [Invoegtoestanden](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#add-in-states)voor meer informatie .  

##  <a name="can-admins-delete-or-remove-add-ins"></a>Kunnen beheerders invoegtoepassingen verwijderen of verwijderen?

Ja. Beheerders kunnen invoegtoepassingen verwijderen die voor alle gebruikers zijn geïmplementeerd in het Microsoft-beheercentrum.

Zie [Een invoegtoepassing verwijderen](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#delete-an-add-in)voor meer informatie. 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>Kunnen beheerders betaalde invoegtoepassingen uit de Office Store implementeren met gecentraliseerde implementatie? 

Nee. U op dit moment geen betaalde invoegtoepassingen uit de Office Store implementeren met gecentraliseerde implementatie.  
 
We raden u aan contact op te nemen met de ISV-ontwikkelaar voor de betaalde invoegtoepassing om een manifestbestand of een URL aan te vragen. De tenantbeheerder kan de invoegtoepassing vervolgens implementeren als LOB-invoegtoepassing met behulp van gecentraliseerde implementatie.
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>Welke beheerdersrol heb ik nodig om invoegtoepassingen voor mijn organisatie te beheren?  

U moet de rol Global admin hebben om invoegtoepassingen te beheren. Als u de persoon bent die uw Microsoft 365 voor bedrijven-abonnement heeft gekocht, bent u de globale beheerder. 
 
Uw abonnement wordt geleverd met een reeks beheerdersrollen die u toewijzen aan andere gebruikers in uw organisatie. Elke beheerdersrol wordt toegewezen aan algemene bedrijfsfuncties en geeft mensen in uw organisatie machtigingen om specifieke taken uit te voeren in het Microsoft 365-beheercentrum.  
 
Zie [Beheerdersrollen toewijzen voor](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide)meer informatie.  
