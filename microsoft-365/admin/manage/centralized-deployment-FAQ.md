---
title: Veelgestelde vragen over Gecentraliseerde implementatie
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Bekijk de antwoorden op veelgestelde vragen over gecentraliseerde implementatie vanaf de Microsoft 365-beheercentrum.
ms.openlocfilehash: 0da9ec9595fd433abe1e2e2ae3f2e3a0c6b3b9b5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228002"
---
# <a name="centralized-deployment-faq"></a>Veelgestelde vragen over Gecentraliseerde implementatie

Gecentraliseerde implementatie is de aanbevolen manier voor een Office 365-beheerder om Office-invoegingen (Word, Excel, PowerPoint en Outlook) te implementeren voor gebruikers en groepen binnen een organisatie, mits de organisatie voldoet aan alle vereisten voor het gebruik van Gecentraliseerde implementatie, zoals beschreven in dit artikel.   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>Hoe weet ik of mijn organisatie is ingesteld voor gecentraliseerde implementatie?  

Gecentraliseerde implementatie van invoegvoegingen vereist dat gebruikers Microsoft 365-apps voor ondernemingen gebruiken (en zijn aangemeld bij Office met hun organisatielogboekreferenties) en Exchange Online postvakken. Uw abonnementslijst moet zich in of federatief aan Azure Active Directory.  
 
Gecentraliseerde implementatie wordt alleen ondersteund voor onlinepostvakken. De implementatie van on-premises postvakken wordt niet Exchange ondersteund.

U kunt de compatibiliteitscontrole voor gecentraliseerde implementatie gebruiken [](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)   om te bepalen of uw abonnement in aanmerking komt. 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>Hoe doelt u gebruikerstoewijzingen voor invoeggebruik met Gecentraliseerde implementatie?  

Gecentraliseerde implementatie ondersteunt opdrachten aan afzonderlijke gebruikers, groepen en iedereen in de tenant. Gecentraliseerde implementatie kan worden gebruikt voor gebruikers in groepen op het hoogste niveau of groepen zonder bovenliggende groepen, maar niet voor gebruikers in geneste groepen of groepen met bovenliggende groepen. Gecentraliseerde implementatie maakt ook deel uit van Azure Active Directory groepen, Office 365 groepen, distributielijsten en beveiligingsgroepen.  

Het is beter om groepentoewijzingen te gebruiken in plaats van afzonderlijke gebruikerstoewijzingen voor eenvoudiger beheer.
 
Zie Gebruikers- en [groepstoewijzingen voor meer informatie.](./centralized-deployment-of-add-ins.md#user-and-group-assignments)  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>Hoe lang duurt het voordat invoegvoegingen voor alle gebruikers worden opdagen?  

Het kan tot 24 uur duren voordat een invoeging wordt voor alle gebruikers. Het kan even lang duren voor invoeg-updates, wijzigingen van in- of uitschakelen of verwijderingen van invoegvoegingen. 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>Hoe beheer ik als beheerder de gebruikerstoegang tot invoegingen voor mijn organisatie?

Voor eenvoudige implementatie van invoegvoegingen voor gebruikers, groepen of voor uw hele organisatie, raden we beheerders aan gecentraliseerde implementatie te gebruiken.

Zie voor meer informatie over het beheren van gebruikerstoegang:
 - [Invoegdownloads voorkomen door de Office store uit te schakelen voor alle clients (behalve Outlook)](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [Geef de beheerders en gebruikers op die invoegvoegingen kunnen installeren en beheren voor Outlook](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>Bieden gecentraliseerde implementatie beheerders de flexibiliteit om de implementatiemethode voor Outlook te kiezen?  

Ja. Gecentraliseerde implementatie biedt beheerders de flexibiliteit om een van de drie implementatiemethoden voor Outlook te kiezen tijdens de implementatie van invoegvoegingen:

**Opgelost (standaard)**   De invoegvoegvoeging wordt automatisch geïmplementeerd voor de toegewezen gebruikers en kan niet worden verwijderd.  
 
**Beschikbaar** Gebruikers kunnen de invoegvoegingspagina Outlook door startpagina te kiezen > Meer invoegvoegingen downloaden **> beheerd door de beheerder.**
 
**Optioneel** De invoegvoegvoeging wordt automatisch geïmplementeerd voor de toegewezen gebruikers, maar ze kunnen ervoor kiezen deze te verwijderen.  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>Kunnen beheerders lob-invoegvoegingen (Line-of-Business) bijwerken?  

Ja. Beheerders kunnen een nieuw manifestbestand uploaden ter ondersteuning van metagegevenswijzigingen voor door beheerders geïmplementeerde LOB-invoegingen. De invoegtoepassingen worden bijgewerkt de volgende keer dat de Office wordt gestart. De webtoepassing kan elk moment worden gewijzigd.  
 
Zie [line-of-business-invoegvoeging voor meer informatie.](./manage-addins-in-the-admin-center.md)  

## <a name="can-admins-turn-off-add-ins"></a>Kunnen beheerders invoegvoegingen uitschakelen?  

Ja. Beheerders kunnen de invoegvoegingen die ze voor alle gebruikers implementeren in- of uitschakelen vanuit het Microsoft-beheercentrum.

Zie Invoeg staten [voor meer informatie.](./manage-addins-in-the-admin-center.md#add-in-states)  

##  <a name="can-admins-delete-or-remove-add-ins"></a>Kunnen beheerders invoegingen verwijderen of verwijderen?

Ja. Beheerders kunnen invoegingen die ze voor alle gebruikers hebben geïmplementeerd, verwijderen uit het Microsoft-beheercentrum.

Zie Een [invoeging verwijderen voor meer informatie.](./manage-addins-in-the-admin-center.md#delete-an-add-in) 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>Kunnen beheerders betaalde invoegvoegingen implementeren vanuit de Office Store met gecentraliseerde implementatie? 

Nee. U kunt op dit moment geen betaalde invoegvoegingen implementeren vanuit de Office Store met gecentraliseerde implementatie.  
 
We raden u aan contact op te zoeken met de isv-ontwikkelaar voor de betaalde invoegvoeging om een manifestbestand of een URL aan te vragen. De tenantbeheerder kan de invoegvoeging vervolgens implementeren als een LOB-invoegvoeging met gecentraliseerde implementatie.
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>Welke beheerdersrol heb ik nodig om invoegingen voor mijn organisatie te beheren?  

Globale beheerder is de aanbevolen rol met volledige toegang tot de levenscyclus van het invoegbeheer. Als u de persoon bent die uw abonnement Microsoft 365 Zakelijk, bent u de globale beheerder. 
 
Uw abonnement wordt geleverd met een set beheerdersrollen die u kunt toewijzen aan andere gebruikers in uw organisatie. Elke beheerdersrol wordt toekend aan algemene zakelijke functies en geeft personen in uw organisatie machtigingen om specifieke taken uit te voeren in de Microsoft 365-beheercentrum.  
 
Zie Beheerdersrollen toewijzen voor [meer informatie.](../add-users/assign-admin-roles.md) 
