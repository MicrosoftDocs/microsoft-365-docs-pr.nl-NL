---
title: Gebruikersaccounts Microsoft 365 beheren
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
description: Meer informatie over het beheren Microsoft 365 gebruikersaccounts.
ms.openlocfilehash: c0387bf50228e0eeb763b4807b15c8d57e02eeac
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909560"
---
# <a name="manage-microsoft-365-user-accounts"></a>Gebruikersaccounts Microsoft 365 beheren

U kunt uw Microsoft 365 op verschillende manieren beheren, afhankelijk van uw configuratie. U kunt gebruikersaccounts beheren in [het Microsoft 365-beheercentrum](../admin/add-users/index.yml), [PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md), in Ad DS (Active Directory Domain Services) of in de Azure Active Directory (Azure AD)-beheerportal. 

Zodra u een account Microsoft 365, kunnen het Microsoft 365 en PowerShell worden gebruikt om accounts te beheren. Bij het beheren van cloudidentiteiten heeft elke persoon in uw organisatie een afzonderlijke gebruikersnaam en wachtwoord. Als u wilt integreren met uw on-premises infrastructuur en gebruikersaccounts wilt laten synchroniseren met Microsoft 365, kunt u Azure AD Verbinding maken gebruiken om identiteiten en wachtwoorden te synchroniseren voor eenmalige aanmeldingsfunctionaliteit (SSO).
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>Plannen voor waar en hoe u uw gebruikersaccounts gaat beheren

Waar en hoe u uw gebruikersaccounts kunt beheren, is afhankelijk van het identiteitsmodel dat u wilt gebruiken voor uw Microsoft 365. De twee algemene modellen zijn alleen-in de cloud en hybride.
  
### <a name="cloud-only"></a>Alleen in de cloud

U maakt en beheert gebruikers in het Microsoft 365 beheercentrum. U kunt ook PowerShell of het Azure AD-beheercentrum gebruiken. 
    
### <a name="hybrid"></a>Hybride

Gebruikersaccounts worden gesynchroniseerd met Microsoft 365 van AD DS, dus u moet on-premises AD DS-hulpprogramma's gebruiken om gebruikersaccounts te beheren. 
    
## <a name="managing-accounts"></a>Accounts beheren

Wanneer u bepaalt op welke manier uw organisatie accounts gaat maken en beheren, moet u rekening houden met de volgende vereisten:
  
- De adreslijstsynchronisatiesoftware moet worden geïnstalleerd op servers in uw on-premises omgeving om de identiteiten tussen uw Microsoft 365 en uw AD DS te verbinden.
    
- Voor elke optie voor adreslijstsynchronisatie, inclusief SSO-opties, moeten uw AD DS-kenmerken voldoen aan standaarden. De details van de kenmerken die in uw adreslijst worden gebruikt en welke opschoning (indien nodig) nodig zijn, worden beschreven in Voorbereiden op [adreslijstsynchronisatie](prepare-for-directory-synchronization.md)voor Microsoft 365. 
    
- Plan hoe u een account gaat Microsoft 365 maken.
    
De volgende tabel bevat de verschillende hulpprogramma's voor accountbeheer.
    
|Hulpmiddel|Opmerkingen|
|:-----|:-----|
|Microsoft 365-beheercentrum  <br/> |[Gebruikers afzonderlijk of bulksgewijs toevoegen](../admin/add-users/add-users.md) <br/>  Biedt een eenvoudige webinterface om gebruikersaccounts toe te voegen en te wijzigen.  <br/>  Kan niet worden gebruikt om gebruikers te wijzigen als adreslijstsynchronisatie is ingeschakeld (locatie en licentietoewijzing kunnen worden ingesteld).  <br/>  Kan niet worden gebruikt met SSO-opties.  <br/> |
|Windows PowerShell  <br/> |[Beheer Microsoft 365 met Windows PowerShell](./manage-microsoft-365-with-microsoft-365-powershell.md) <br/>  Hiermee kunt u gebruikers in bulkgebruikers toevoegen met een Windows PowerShell script.  <br/>  Kan worden gebruikt om locatie en licenties toe te wijzen aan accounts, ongeacht hoe de accounts worden gemaakt.  <br/> |
|Bulkimport  <br/> |[Meerdere gebruikers tegelijk toevoegen](add-several-users-at-the-same-time.md) <br/>  Hiermee kunt u een CSV-bestand importeren om een groep gebruikers toe te voegen aan Microsoft 365.  <br/>  Kan niet worden gebruikt met SSO-opties.  <br/> |
|Azure AD  <br/> |U krijgt een gratis versie van Azure AD met uw Microsoft 365 abonnement. U kunt functies zoals selfservicewachtwoord opnieuw instellen voor cloudgebruikers en het aanpassen van de pagina's Aanmelden en Access Panel uitvoeren met de gratis versie. U kunt een upgrade uitvoeren naar de basisversie, Azure AD Premium P1 of Azure AD Premium P2. Zie [Azure AD-versies](/azure/active-directory/fundamentals/active-directory-whatis) voor de lijst met ondersteunde functies.  <br/> |
|Adreslijstsynchronisatie  <br/> |[Uw on-premises identiteiten integreren met Azure AD](/azure/active-directory/hybrid/whatis-hybrid-identity) <br/>  Voor adreslijstsynchronisatie met of zonder wachtwoordsynchronisatie gebruikt u [Azure AD-Verbinding maken met express-instellingen.](/azure/active-directory/hybrid/how-to-connect-install-express)  <br/>  Voor meerdere forests en SSO-opties gebruikt u [Aangepaste installatie van Azure AD-Verbinding maken.](/azure/active-directory/hybrid/how-to-connect-install-custom)  <br/>  Biedt de infrastructuur die nodig is om eenmalige aanmelding in te stellen.  <br/>  Vereist voor veel hybride scenario's, zoals gefaseerd migratie en hybride Exchange  <br/>  Hiermee worden beveiligings- en e-mailgroepen gesynchroniseerd vanuit uw AD DS.  <br/> |
|||
   
- Ongeacht hoe u de gebruikersaccounts wilt toevoegen aan Microsoft 365, moet u verschillende accountfuncties beheren, zoals het toewijzen van licenties, het opgeven van locatie, en dergelijke. Deze functies kunnen op lange termijn worden beheerd vanuit het Microsoft 365 beheercentrum of u kunt ook [gebruikersaccounts maken met PowerShell.](./create-user-accounts-with-microsoft-365-powershell.md)
    
    Als u ervoor kiest om al uw gebruikers toe te voegen en te beheren via het beheercentrum, geeft u de locatie op en wijst u licenties toe tegelijk met het maken van het Microsoft 365 account. Hierdoor is er niet veel planning nodig.
    
    > [!IMPORTANT]
    > Het maken van accounts in Microsoft 365 zonder een licentie toe te wijzen (bijvoorbeeld aan SharePoint Online) betekent dat de eigenaar van het account het Microsoft 365-centrum kan bekijken, maar geen toegang heeft tot een van de services binnen het abonnement van uw bedrijf. Nadat u een locatie en de licentie hebt toegewezen, wordt het account gerepliceerd naar de service of services die u hebt toegewezen. De gebruiker kan zich aanmelden bij zijn of haar account en de services gebruiken die u aan hen hebt toegewezen. 
  
## <a name="see-also"></a>Zie ook

[Microsoft 365-beheercentrum](../admin/add-users/index.yml)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)