---
title: Hulpprogramma's voor het beheren van Microsoft 365-gebruikersaccounts
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
description: Meer informatie over de hulpmiddelen die u kunt gebruiken en hoe u accounts van Microsoft 365 beheert.
ms.openlocfilehash: 205c61c0cff896f93069d225c84dc3086ca30eb5
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689441"
---
# <a name="tools-to-manage-microsoft-365-user-accounts"></a>Hulpprogramma's voor het beheren van Microsoft 365-gebruikersaccounts

U kunt Microsoft 365-gebruikers op verschillende manieren beheren, afhankelijk van de configuratie. U kunt gebruikers beheren in het [Microsoft 365-Beheercentrum](https://admin.microsoft.com), Windows PowerShell, in Active Directory Domain Services (AD DS) of in de beheerportal van Azure Active Directory (Azure AD). 

Zodra u Microsoft 365 hebt aangeschaft, kunt u het Beheercentrum en Windows PowerShell gebruiken om accounts te beheren. Wanneer u Cloud Identities beheert, heeft elke persoon in uw organisatie een afzonderlijke gebruikers-ID en een apart wachtwoord voor Microsoft 365. Als u wilt integreren met uw on-premises infrastructuur en gebruikersaccounts wilt synchroniseren met Microsoft 365, kunt u Azure AD Connect gebruiken om de functies voor eenmalige aanmelding te synchroniseren.
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>Plannen waar en hoe u uw gebruikersaccounts beheert

Waar en hoe u uw gebruikersaccounts kunt beheren, is afhankelijk van het identiteits model dat u wilt gebruiken voor uw Microsoft 365. De twee algemene modellen zijn Cloud verificatie en federatieve verificatie.
  
### <a name="cloud-authentication"></a>Cloud verificatie

- Cloud verificatie: gebruikers maken en beheren in het Microsoft 365-Beheercentrum. U kunt ook Windows PowerShell of Azure AD gebruiken. 
    
- Synchronisatie van wachtwoord hash (PHS) met naadloze eenmalige aanmelding: de eenvoudigste manier om verificatie in te schakelen voor AD DS-objecten in azure AD. Met PHS synchroniseert u uw AD DS-gebruikersaccount objecten met Microsoft 365 en beheert u de gebruikers on-premises. 
    
- Pass Through-verificatie (PTA) met naadloze eenmalige aanmelding biedt een eenvoudige wachtwoordvalidatie voor Azure AD Authentication-Services met behulp van een programma dat wordt uitgevoerd op een of meer on-premises servers, zodat de gebruikers direct met uw AD DS worden gevalideerd. 
    
### <a name="federated-authentication"></a>Federatieve verificatie

- Opties voor Federatie verificatie-hoofdzakelijk voor grote Enterprise-organisaties met meer ingewikkelde verificatievereisten, worden AD DS-objecten gesynchroniseerd met Microsoft 365 en gebruikersaccounts worden on-premises beheerd. 
    
- [Verificatie-en identiteitsproviders van derden](about-microsoft-365-identity.md) -AD DS-objecten kunnen worden gesynchroniseerd met microsoft 365 en toegang tot de Cloud wordt hoofdzakelijk beheerd door een externe identiteitsprovider (IDP). 
    
## <a name="managing-accounts"></a>Accounts beheren

Wanneer u bepaalt op welke manier uw organisatie accounts gaat maken en beheren, kunt u de volgende vereisten overwegen:
  
- De software voor adreslijstsynchronisatie moet zijn geïnstalleerd op servers in uw on-premises omgeving om de identiteiten te verbinden tussen Microsoft 365 en de AD DS.
    
- Voor de optie voor het synchroniseren van directory's, inclusief opties voor SSO, moet u de kenmerken van de AD DS-toepassing voldoen aan standaarden. Welke kenmerken er in uw adreslijst worden gebruikt en welke opschoonactie (indien van toepassing) moet worden beschreven in voor [bereidingen treffen om gebruikers via adreslijstsynchronisatie in te richten voor Microsoft 365](prepare-for-directory-synchronization.md). 
    
- Plan hoe u Microsoft 365-accounts gaat maken.
    
    De volgende tabel bevat een overzicht van de verschillende hulpprogramma's voor accountbeheer.
    
|**Optie**|**Opmerkingen**|
|:-----|:-----|
|Beheercentrum  <br/> |[Gebruikers afzonderlijk of bulksgewijs toevoegen](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) <br/>  Biedt een eenvoudige webinterface voor het toevoegen en wijzigen van gebruikersaccounts.  <br/>  Kan niet worden gebruikt om gebruikers te wijzigen als adreslijstsynchronisatie is ingeschakeld (locatie en licentietoewijzing kunnen worden ingesteld).  <br/>  Kan niet worden gebruikt met opties voor eenmalige aanmelding.  <br/> |
|Windows PowerShell  <br/> |[Microsoft 365 beheren met Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=698471) <br/>  Hiermee kunt u gebruikers toevoegen in bulk gebruikers met behulp van een Windows PowerShell-script.  <br/>  Kan worden gebruikt om de locatie en licenties toe te wijzen aan accounts, ongeacht hoe de accounts worden gemaakt.  <br/> |
|Bulk Import  <br/> |[Meerdere gebruikers tegelijk toevoegen](add-several-users-at-the-same-time.md) <br/>  U kunt een CSV-bestand importeren als u een groep gebruikers wilt toevoegen aan Microsoft 365.  <br/>  Kan niet worden gebruikt met opties voor eenmalige aanmelding.  <br/> |
|Azure AD  <br/> |U krijgt een gratis editie van Azure AD met uw abonnement op Microsoft 365. U kunt functies zoals het zelf opnieuw instellen van wachtwoorden voor Cloud gebruikers en het aanpassen van de aanmeldings-en toegangsvenster pagina's uitvoeren met behulp van de gratis editie. U kunt een upgrade uitvoeren naar de Basic-editie, Azure AD Premium P1 of Azure AD Premium P2 voor uitgebreide functionaliteit. Zie [Azure AD-edities](https://go.microsoft.com/fwlink/p/?LinkId=698465) voor een lijst met ondersteunde functies.  <br/> |
|Adreslijstsynchronisatie  <br/> |[Uw on-premises id's integreren met Azure AD](https://go.microsoft.com/fwlink/p/?LinkID=624168) <br/>  Voor adreslijstsynchronisatie met of zonder Wachtwoordsynchronisatie gebruikt u [Azure AD Connect met snelle instellingen](https://go.microsoft.com/fwlink/p/?LinkID=698537).  <br/>  Voor meerdere forests en opties voor eenmalige aanmelding gebruikt u [aangepaste installatie van Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).  <br/>  Biedt de infrastructuur die nodig is om eenmalige aanmelding in te schakelen.  <br/>  Vereist voor veel hybride scenario's:  <br/>  Gefaseerde migratie  <br/>  Hybride uitwisseling  <br/>  Synchroniseert beveiliging en groepen met e-mail in uw AD DS.  <br/> |
   
- Ongeacht de manier waarop u de gebruikersaccounts wilt toevoegen aan Microsoft 365, moet u diverse account functies beheren, zoals het toewijzen van licenties, het opgeven van de locatie, enzovoort. U kunt deze functies wel lang beheren vanuit het Beheercentrum of u kunt ook [gebruikersaccounts maken met PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=717083).
    
    Als u ervoor kiest om alle gebruikers toe te voegen en te beheren in het Beheercentrum, moet u de locatie opgeven en licenties toewijzen tegelijk met het maken van het Microsoft 365-account. Daarom is het niet veel planning nodig.
    
    > [!IMPORTANT]
    > Bij het maken van een account in Microsoft 365 zonder een licentie toe te wijzen (bijvoorbeeld naar SharePoint Online), betekent dit dat de eigenaar van het account het Microsoft 365-centrum kan weergeven, maar geen toegang heeft tot de services binnen het abonnement van uw bedrijf. Wanneer u een locatie en de licentie hebt toegewezen, wordt het account gerepliceerd naar de service of services die u hebt toegewezen. Gebruikers kunnen zich aanmelden bij hun account en gebruikmaken van de services die u eraan hebt toegewezen. 
  
## <a name="next-steps"></a>Volgende stappen

[Microsoft 365-integratie met on-premises omgevingen](microsoft-365-integration.md)
  
## <a name="see-also"></a>Zie ook

[Gebruikers en groepen beheren in Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users)
  
