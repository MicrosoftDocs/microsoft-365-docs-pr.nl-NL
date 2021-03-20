---
title: Aan de slag met Microsoft 365 voor Bedrijven
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Meer informatie over Microsoft 365 voor Bedrijven, hoe u dit kunt instellen en hoe u de apparaten en pc's van uw gebruikers voorbereidt om ervoor te zorgen dat ze worden beschermd door Microsoft 365 voor Bedrijven.
ms.openlocfilehash: 9430dc7aa637be3fdb833150b83e96caacc82170
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912957"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Aan de slag met Microsoft 365 voor Bedrijven

## <a name="what-is-microsoft-365-for-business"></a>Wat is Microsoft 365 voor Bedrijven

Microsoft 365 voor Bedrijven is een uitgebreide set hulpprogramma's voor bedrijfsproductiviteit en samenwerking, zoals Outlook, Word, Excel en andere Office-producten, die altijd up-to-date zijn. U kunt uw werkbestanden op al uw iOS-, Android- en Windows 10-apparaten beveiligen met bedrijfsbeveiliging die eenvoudig te beheren is.

Bekijk deze video voor een kort overzicht van Microsoft 365 voor Bedrijven.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 voor Bedrijven is bedoeld voor maximaal 300 licenties. Als u meer licenties nodig hebt, raadpleegt u de documentatie bij [Microsoft 365 Enterprise](../enterprise/index.yml) voor meer informatie. 
  
## <a name="get-microsoft-365-for-business"></a>Microsoft 365 voor Bedrijven krijgen

- Als u een partner hebt, krijgen ze Microsoft 365 voor Bedrijven: [Microsoft 365 voor](get-microsoft-365-business.md)Bedrijven krijgen vanuit microsoft partnercentrum.
    
- Als u geen partner hebt en Microsoft 365 voor Bedrijven wilt kopen, kunt u [deze hier kopen.](https://www.microsoft.com/microsoft-365/business)
    
## <a name="set-up-microsoft-365-for-business"></a>Microsoft 365 voor bedrijven instellen

 **Overzicht van de set-up van Microsoft 365 voor Bedrijven Suite**
  
In het volgende diagram wordt beschreven hoe beheerders Microsoft 365 voor Bedrijven instellen. Ook worden de stappen beschreven voor het voorbereiden van Windows-pc's voor Microsoft 365 voor Bedrijven. U kunt ook nieuwe apparaten toevoegen in het Microsoft 365-beheercentrum met [Windows AutoPilot.](add-autopilot-devices-and-profile.md) U kunt AutoPilot gebruiken om nieuwe apparaten in te stellen en vooraf te configureren, zodat ze klaar zijn voor productief gebruik zodra een gebruiker zich aanmeld met de referenties van Microsoft 365 voor Bedrijven.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Bekijk deze video voor een overzicht van de installatie van Microsoft 365 voor Bedrijven.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Als je deze video nuttig vond, raadpleeg dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: Microsoft 365 voor Bedrijven instellen (beheerder)

Meld u aan bij [het Microsoft 365-beheercentrum](https://portal.office.com/adminportal/home) met uw globale beheerdersreferenties en volg de volgende stappen om Microsoft 365 voor Bedrijven in te stellen. 
  
1. [Vereisten voor het beveiligen van gegevens op apparaten met Microsoft 365 voor Bedrijven](pre-requisites-for-data-protection.md)
    
    Lees eerst de vereisten om ervoor te zorgen dat uw apparaten klaar zijn voor Microsoft 365 voor Bedrijven.
    
2. [De installatiewizard gebruiken om Microsoft 365 voor Bedrijven in te stellen](set-up.md)
    
    Als u permanent van een lokale **Active Directory** naar de cloud gaat, kunt u naar het Microsoft 365-beheercentrum gaan en de installatiewizard gebruiken om uw gebruikers handmatig toe te voegen, of u kunt een een-tijdssynchronisatie uitvoeren met Azure AD Connect. U kunt dit op twee manieren doen: 
    
    - Als u ook een Exchange 2010-, Exchange 2013- of Exchange 2016-server hebt, kunt u Minimaal hybride gebruiken om Exchange-postvakken snel te migreren naar [Microsoft 365.](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate) De minimale hybride stappen omvatten een een time sync van gebruikers met Azure AD en e-mailmigratie van on-premises naar de cloud. Nadat de e-mailmigratie is voltooid, wordt de adreslijstsynchronisatie automatisch uitgeschakeld wanneer u deze methode gebruikt.
    
    - Gebruik de wizard Adreslijstsynchronisatie om uw gebruikers te synchroniseren met de cloud. Volg de stappen in [Adreslijstsynchronisatie instellen voor Microsoft 365](../enterprise/set-up-directory-synchronization.md) om dit proces te voltooien. Nadat u uw gebruikers hebt gesynchroniseerd met de cloud, moet u [adreslijstsynchronisatie uitschakelen voor Microsoft 365.](../enterprise/turn-off-directory-synchronization.md)
    
    U moet ook elke gebruiker die op deze manier is toegevoegd, een licentie geven aan Microsoft 365 voor Bedrijven. U kunt dit doen in de [installatiewizard](set-up.md) of u kunt [licenties toewijzen aan gebruikers.](../admin/manage/assign-licenses-to-users.md)
    
### <a name="2-prepare-mobile-devices"></a>2: Mobiele apparaten voorbereiden

Volg de stappen in Mobiele apparaten instellen voor gebruikers van [Microsoft 365](set-up-mobile-devices.md) voor Bedrijven om Office-apps op apparaten te installeren en ervoor te zorgen dat ze zijn beveiligd door Microsoft 365 voor Bedrijven. 
  
### <a name="3-prepare-pcs"></a>3: Pc's voorbereiden

Beheerders kunnen instellingen voor nieuwe Windows 10-pc's vooraf selecteren met [Windows AutoPilot.](add-autopilot-devices-and-profile.md) Gebruikers kunnen hun bestaande of nieuwe Windows 10-apparaten instellen door de stappen in dit onderwerp te volgen: Windows-pc's instellen voor Gebruikers van [Microsoft 365 voor Bedrijven.](set-up-windows-devices.md) Voor bestaande apparaten kunnen gebruikers desgewenst **bestanden verplaatsen** [naar OneDrive voor Bedrijven.](move-files-to-onedrive.md) Ze kunnen ook hulpprogramma's van derden gebruiken om bestanden die zijn gekoppeld aan Windows-profiel te verplaatsen naar OneDrive.
  
Als uw organisatie on-premises Gebruikmaakt van Windows Server Active Directory, kunt u Microsoft 365 voor Bedrijven instellen om uw Windows 10-apparaten te beveiligen, terwijl u nog steeds toegang hebt tot on-premises resources waarvoor lokale verificatie vereist is. Volg de stappen in [Windows 10-apparaten](manage-windows-devices.md) met een domein inschakelen die moeten worden beheerd door Microsoft 365 voor Bedrijven om dit in te stellen. Deze methode heeft de voorkeur en apparaten in deze status worden **verbonden met hybride Azure AD-apparaten genoemd.** 
  
Als u een lokale Active Directory met enkele on-premises resources (zoals bestandsaandelen en printers) behoudt, kunt u uw apparaten met **Azure AD toegang** geven tot deze bronnen door de volgende stappen te volgen: On-premises resources openen vanaf een apparaat met Azure [AD-ondersteuning in Microsoft 365](access-resources.md)voor Bedrijven.
  
  
## <a name="contact-support"></a>Contact opnemen met de ondersteuning

 **Ga als volgt te werk als u contact wilt opnemen met Ondersteuning:**
  
- Neem contact op met uw partner.
    
- Als beheerder van Microsoft 365 voor Bedrijven hebt u toegang tot ons klantenserviceteam: Contact opnemen met ondersteuning voor **[zakelijke producten - Help voor beheerders](../admin/contact-support-for-business-products.md)**
    
## <a name="see-also"></a>Zie ook

[Microsoft 365 voor bedrijven-documentatie en -bronnen](./index.yml)
  
[Microsoft 365 voor Bedrijven beheren](manage.md)[Migreren naar Microsoft 365 voor Bedrijven](migrate-to-microsoft-365-business.md)

[Trainingsvideo's voor Microsoft 365 voor bedrijven](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)