---
title: Aan de slag met Microsoft 365 voor bedrijven
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Meer informatie Microsoft 365 voor bedrijven, hoe u dit kunt instellen en hoe u de apparaten en pc's van uw gebruikers voorbereidt om ervoor te zorgen dat ze worden beschermd door gebruikers Microsoft 365 voor bedrijven.
ms.openlocfilehash: 2ab0079da7a8f30d481cdb3d3dc6d165b4a19e99
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339285"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Aan de slag met Microsoft 365 voor bedrijven

## <a name="what-is-microsoft-365-for-business"></a>Wat is Microsoft 365 voor bedrijven

Microsoft 365 voor bedrijven is een uitgebreide set hulpprogramma's voor bedrijfsproductiviteit en samenwerking, zoals Outlook, Word, Excel en andere Office-producten, die altijd up-to-date zijn. U kunt uw werkbestanden op al uw iOS-, Android- en Windows 10-apparaten beveiligen met bedrijfsbeveiliging die eenvoudig te beheren is.

## <a name="watch-what-is-microsoft-365-business-premium"></a>Bekijken: Wat is Microsoft 365 Business Premium?

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 voor bedrijven is bedoeld voor maximaal 300 licenties. Als u meer licenties nodig hebt, raadpleegt u de documentatie bij [Microsoft 365 Enterprise](../enterprise/index.yml) voor meer informatie. 
  
## <a name="get-microsoft-365-for-business"></a>Een Microsoft 365 voor bedrijven

- Als u een partner hebt, krijgen ze Microsoft 365 voor bedrijven: Een Microsoft 365 voor bedrijven [krijgen vanuit microsoft partnercentrum.](get-microsoft-365-business.md)
    
- Als u geen partner hebt en een Microsoft 365 voor bedrijven wilt kopen, kunt u [deze hier kopen.](https://www.microsoft.com/microsoft-365/business)
    
## <a name="set-up-microsoft-365-for-business"></a>Microsoft 365 voor bedrijven instellen

 **Overzicht van Microsoft 365 voor bedrijven Suite instellen**
  
In het volgende diagram wordt beschreven hoe beheerders Microsoft 365 voor bedrijven. In deze beschrijving worden ook de stappen beschreven voor het voorbereiden Windows pc's voor Microsoft 365 voor bedrijven. U kunt ook nieuwe apparaten toevoegen in de Microsoft 365-beheercentrum met [Windows AutoPilot.](add-autopilot-devices-and-profile.md) U kunt AutoPilot gebruiken om nieuwe apparaten in te stellen en vooraf te configureren, zodat ze klaar zijn voor productief gebruik zodra een gebruiker zich aanmeld met hun Microsoft 365 voor zakelijke referenties.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

## <a name="watch-set-up-microsoft-365-business"></a>Kijken: Microsoft 365 Business

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Als u deze video nuttig vond, raadpleegt u dan de [complete training voor kleine bedrijven en degene die nieuw zijn bij Microsoft 365](../business-video/index.yml).

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: Een Microsoft 365 voor bedrijven instellen (beheerder)

Meld u aan [bij Microsoft 365-beheercentrum](https://admin.microsoft.com/adminportal/home) globale beheerdersreferenties en volg de volgende stappen om Microsoft 365 voor bedrijven. 
  
1. [Vereisten voor het beveiligen van gegevens op apparaten met Microsoft 365 voor bedrijven](pre-requisites-for-data-protection.md)
    
    Lees eerst de vereisten om ervoor te zorgen dat uw apparaten klaar zijn voor Microsoft 365 voor bedrijven.
    
2. [De installatiewizard gebruiken om een Microsoft 365 voor bedrijven in te stellen](set-up.md)
    
    Als u permanent van een lokale **Active Directory** naar de cloud gaat, kunt u naar de Microsoft 365-beheercentrum gaan en de installatiewizard gebruiken om uw gebruikers handmatig toe te voegen, of u kunt een een-tijdssynchronisatie uitvoeren met Azure AD-Verbinding maken. U kunt dit op twee manieren doen: 
    
    - Als u ook een Exchange 2010- Exchange 2013- of Exchange 2016-server hebt, kunt u Minimale hybride gebruiken om snel Exchange postvakken te migreren naar [Microsoft 365.](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate) De minimale hybride stappen omvatten een een time sync van gebruikers met Azure AD en e-mailmigratie van on-premises naar de cloud. Nadat de e-mailmigratie is voltooid, wordt de adreslijstsynchronisatie automatisch uitgeschakeld wanneer u deze methode gebruikt.
    
    - Gebruik de wizard Adreslijstsynchronisatie om uw gebruikers te synchroniseren met de cloud. Volg de stappen in [Adreslijstsynchronisatie](../enterprise/set-up-directory-synchronization.md) instellen voor Microsoft 365 dit proces te voltooien. Nadat u uw gebruikers hebt gesynchroniseerd met de cloud, moet u [adreslijstsynchronisatie](../enterprise/turn-off-directory-synchronization.md)uitschakelen voor Microsoft 365.
    
    U moet ook elke gebruiker die op deze manier is toegevoegd, een licentie geven Microsoft 365 voor bedrijven. U kunt dit doen in de [installatiewizard](set-up.md) of u kunt [licenties toewijzen aan gebruikers.](../admin/manage/assign-licenses-to-users.md)
    
### <a name="2-prepare-mobile-devices"></a>2: Mobiele apparaten voorbereiden

Volg de stappen in Mobiele apparaten instellen voor [Microsoft 365](set-up-mobile-devices.md) voor zakelijke gebruikers om Office-apps op apparaten te installeren en ervoor te zorgen dat ze zijn beveiligd door Microsoft 365 voor bedrijven. 
  
### <a name="3-prepare-pcs"></a>3: Pc's voorbereiden

Beheerders kunnen instellingen voor nieuwe Windows 10 pc's vooraf selecteren met Windows [AutoPilot.](add-autopilot-devices-and-profile.md) Gebruikers kunnen hun bestaande of nieuwe Windows 10 instellen door de stappen in dit onderwerp te volgen: Windows pc's instellen voor Microsoft 365 voor [zakelijke gebruikers.](set-up-windows-devices.md) Voor bestaande apparaten kunnen gebruikers desgewenst **bestanden** verplaatsen [naar OneDrive voor Bedrijven.](move-files-to-onedrive.md) Ze kunnen ook hulpprogramma's van derden gebruiken om bestanden die zijn gekoppeld aan Windows profiel te verplaatsen naar OneDrive.
  
Als uw organisatie Windows Server Active Directory on-premises gebruikt, kunt u Microsoft 365 voor bedrijven instellen om uw Windows 10-apparaten te beveiligen, met behoud van toegang tot lokale resources waarvoor lokale verificatie vereist is. Volg de stappen in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 for business](manage-windows-devices.md) to set this up. Deze methode heeft de voorkeur en apparaten in deze status worden **verbonden met hybride Azure AD-apparaten genoemd.** 
  
Als u een lokale Active Directory met enkele on-premises bronnen (zoals bestandsaandelen en printers) behoudt, kunt u uw apparaten met **Azure AD toegang** geven tot deze bronnen door de volgende stappen uit te voeren: On-premises resources openen vanaf een apparaat met Azure [AD-apparaten in Microsoft 365 voor](access-resources.md)bedrijven.
  
  
## <a name="contact-support"></a>Contact opnemen met de ondersteuning

 **Ga als volgt te werk als u contact wilt opnemen met Ondersteuning:**
  
- Neem contact op met uw partner.
    
- Als beheerder Microsoft 365 voor bedrijven hebt u toegang tot ons klantenserviceteam: Contact opnemen met ondersteuning voor **[zakelijke producten - Help voor beheerders](../business-video/get-help-support.md)**
    
## <a name="related-content"></a>Verwante onderwerpen

[Microsoft 365 voor zakelijke documentatie en resources](./index.yml) (koppelingspagina)\
[Beheer Microsoft 365 voor bedrijven](manage.md) (artikel)\
[Migreren naar Microsoft 365 voor bedrijven](migrate-to-microsoft-365-business.md) (artikel)\
[Trainingsvideo's voor Microsoft 365 voor bedrijven](../business-video/index.yml) (koppelingspagina)