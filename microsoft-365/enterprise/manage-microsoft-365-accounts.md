---
title: Microsoft 365-gebruikersaccounts beheren
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Meer informatie over het beheren van gebruikersaccounts van Microsoft 365.
ms.openlocfilehash: a7b6d89a0f66605dde168b85d74fcd8e513afc15
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327757"
---
# <a name="manage-microsoft-365-user-accounts"></a>Microsoft 365-gebruikersaccounts beheren

U kunt op verschillende manieren Microsoft 365-gebruikersaccounts beheren, afhankelijk van de configuratie. U kunt gebruikersaccounts beheren in het [Microsoft 365-Beheercentrum](https://docs.microsoft.com/microsoft-365/admin/add-users/), [PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md), in Active Directory Domain Services (AD DS) of in de Beheerportal van Azure Active Directory (Azure AD). 

Zodra u Microsoft 365 hebt aangeschaft, kunt u het Microsoft 365-Beheercentrum en PowerShell gebruiken voor het beheren van accounts. Wanneer u Cloud Identities beheert, heeft elke persoon in uw organisatie een eigen gebruikersaccountnaam en-wachtwoord. Als u wilt integreren met uw on-premises infrastructuur en gebruikersaccounts wilt synchroniseren met Microsoft 365, kunt u Azure AD Connect gebruiken om de identiteit en wachtwoorden voor de SSO-functionaliteit (eenmalige aanmelding) te kunnen synchroniseren.
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>Plannen waar en hoe u uw gebruikersaccounts beheert

Waar en hoe u uw gebruikersaccounts kunt beheren, is afhankelijk van het identiteits model dat u wilt gebruiken voor uw Microsoft 365. De twee algemene modellen zijn alleen in de Cloud en hybride.
  
### <a name="cloud-only"></a>Alleen in de cloud

U maakt en beheert gebruikers in het Microsoft 365-Beheercentrum. U kunt ook PowerShell of het Azure AD-Beheercentrum gebruiken. 
    
### <a name="hybrid"></a>Hybride

Gebruikersaccounts worden gesynchroniseerd met Microsoft 365 vanuit AD DS, dus moet u on-premises hulpmiddelen voor AD DS gebruiken voor het beheren van gebruikersaccounts. 
    
## <a name="managing-accounts"></a>Accounts beheren

Wanneer u bepaalt op welke manier uw organisatie accounts gaat maken en beheren, kunt u de volgende vereisten overwegen:
  
- De software voor adreslijstsynchronisatie moet zijn geïnstalleerd op servers in uw on-premises omgeving om de identiteiten te verbinden tussen Microsoft 365 en de AD DS.
    
- Voor de optie voor het synchroniseren van directory's, waaronder opties voor SSO, moet uw AD DS-kenmerken voldoen aan standaarden. Welke kenmerken worden gebruikt in de adreslijst en welke opschoonactie (indien aanwezig) is vereist in [voorbereiding voor adreslijstsynchronisatie met Microsoft 365](prepare-for-directory-synchronization.md). 
    
- Plan hoe u Microsoft 365-accounts gaat maken.
    
De volgende tabel bevat een overzicht van de verschillende hulpprogramma's voor accountbeheer.
    
|Readiness|Opmerkingen|
|:-----|:-----|
|Microsoft 365-beheercentrum  <br/> |[Gebruikers afzonderlijk of bulksgewijs toevoegen](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) <br/>  Biedt een eenvoudige webinterface voor het toevoegen en wijzigen van gebruikersaccounts.  <br/>  Kan niet worden gebruikt om gebruikers te wijzigen als adreslijstsynchronisatie is ingeschakeld (locatie en licentietoewijzing kunnen worden ingesteld).  <br/>  Kan niet worden gebruikt met opties voor eenmalige aanmelding.  <br/> |
|Windows PowerShell  <br/> |[Microsoft 365 beheren met Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=698471) <br/>  Hiermee kunt u gebruikers toevoegen in bulk gebruikers met behulp van een Windows PowerShell-script.  <br/>  Kan worden gebruikt om de locatie en licenties toe te wijzen aan accounts, ongeacht hoe de accounts worden gemaakt.  <br/> |
|Bulk Import  <br/> |[Meerdere gebruikers tegelijk toevoegen](add-several-users-at-the-same-time.md) <br/>  U kunt een CSV-bestand importeren als u een groep gebruikers wilt toevoegen aan Microsoft 365.  <br/>  Kan niet worden gebruikt met opties voor eenmalige aanmelding.  <br/> |
|Azure AD  <br/> |U krijgt een gratis editie van Azure AD met uw abonnement op Microsoft 365. U kunt functies zoals het zelf opnieuw instellen van wachtwoorden voor Cloud gebruikers en het aanpassen van de aanmeldings-en toegangsvenster pagina's uitvoeren met behulp van de gratis editie. U kunt een upgrade uitvoeren naar de Basic-editie, Azure AD Premium P1 of Azure AD Premium P2 voor uitgebreide functionaliteit. Zie [Azure AD-edities](https://go.microsoft.com/fwlink/p/?LinkId=698465) voor een lijst met ondersteunde functies.  <br/> |
|Adreslijstsynchronisatie  <br/> |[Uw on-premises id's integreren met Azure AD](https://go.microsoft.com/fwlink/p/?LinkID=624168) <br/>  Voor adreslijstsynchronisatie met of zonder Wachtwoordsynchronisatie gebruikt u [Azure AD Connect met snelle instellingen](https://go.microsoft.com/fwlink/p/?LinkID=698537).  <br/>  Voor meerdere forests en opties voor eenmalige aanmelding gebruikt u [aangepaste installatie van Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).  <br/>  Biedt de infrastructuur die nodig is om eenmalige aanmelding in te schakelen.  <br/>  Vereist voor veel hybride scenario's, zoals gefaseerde migratie en hybride uitwisseling  <br/>  Synchroniseert beveiliging en groepen met e-mail in uw AD DS.  <br/> |
|||
   
- Ongeacht de manier waarop u de gebruikersaccounts wilt toevoegen aan Microsoft 365, moet u diverse account functies beheren, zoals het toewijzen van licenties, het opgeven van de locatie, enzovoort. U kunt deze functies lange termijn beheren via het Microsoft 365-Beheercentrum of u kunt ook [gebruikersaccounts maken met PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=717083).
    
    Als u ervoor kiest om alle gebruikers toe te voegen en te beheren in het Beheercentrum, moet u de locatie opgeven en licenties toewijzen tegelijk met het maken van het Microsoft 365-account. Daarom is het niet veel planning nodig.
    
    > [!IMPORTANT]
    > Bij het maken van een account in Microsoft 365 zonder een licentie toe te wijzen (bijvoorbeeld naar SharePoint Online), betekent dit dat de eigenaar van het account het Microsoft 365-centrum kan weergeven, maar geen toegang heeft tot de services binnen het abonnement van uw bedrijf. Wanneer u een locatie en de licentie hebt toegewezen, wordt het account gerepliceerd naar de service of services die u hebt toegewezen. Gebruikers kunnen zich aanmelden bij hun account en gebruikmaken van de services die u eraan hebt toegewezen. 
  
## <a name="see-also"></a>Zie ook

[Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/add-users)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)  
