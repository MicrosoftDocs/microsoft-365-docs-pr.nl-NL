---
title: Aan de slag met Microsoft 365 Business
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Meer informatie over het instellen van Microsoft 365 Business.
ms.openlocfilehash: f269e970cc1ee5ba7455ea799b238db577116f09
ms.sourcegitcommit: 38934a2115d5cdeb44c7484d57be07686c6f7720
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/19/2019
ms.locfileid: "38704110"
---
# <a name="get-started-with-microsoft-365-business"></a>Aan de slag met Microsoft 365 Business

## <a name="what-is-microsoft-365-business"></a>Wat is Microsoft 365 Business

Microsoft 365 Business is een uitgebreide set zakelijke productiviteits-en samenwerkingshulpmiddelen, zoals Outlook, Word, Excel en andere Office-producten, die altijd up-to-date zijn. U uw werkbestanden op al uw iOS-, Android-en Windows 10-apparaten beschermen met hoogwaardige beveiliging die eenvoudig te beheren is.
  
Microsoft 365 Business is bedoeld voor maximaal 300 licenties. Als u meer licenties nodig hebt, raadpleegt u de documentatie bij [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) voor meer informatie. 
  
## <a name="get-microsoft-365-business"></a>Microsoft 365 Business kopen

- Als u een partner hebt, krijgen ze Microsoft 365 Business: [Microsoft 365 Business ophalen bij Microsoft Partner Center](get-microsoft-365-business.md).
    
- Als u niet met een partner werkt en Microsoft 365 Business wilt kopen, kunt u [contact opnemen met ](https://www.microsoft.com/microsoft-365/business).
    
## <a name="set-up-microsoft-365-business"></a>Microsoft 365 Business instellen

 **Overzicht van Microsoft 365 Business Suite instellen**
  
In het volgende diagram wordt beschreven hoe beheerders Microsoft 365 Business hebben ingesteld. Ook worden de stappen beschreven voor de voorbereiding van Windows-pc's voor Microsoft 365 Business. U ook nieuwe apparaten toevoegen in het Microsoft 365 Business Admin Center met [Windows Autopilot](add-autopilot-devices-and-profile.md). U AutoPilot gebruiken om nieuwe apparaten in te stellen en vooraf te configureren, zodat ze klaar zijn voor productief gebruik zodra een gebruiker zich aanmeldt met de referenties van hun Microsoft 365 Business.
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: Microsoft 365 Business (admin) instellen

Meld u aan bij [Microsoft 365 Business Admin Center](https://portal.office.com/adminportal/home) met uw globale beheerdersreferenties en voer de volgende stappen uit om microsoft 365 Business in te stellen. 
  
1. [Vereisten voor het beveiligen van gegevens op apparaten met Microsoft 365 Business](pre-requisites-for-data-protection.md)
    
    Lees de vereisten eerst om ervoor te zorgen dat uw apparaten gereed voor Microsoft 365 Business zijn.
    
2. [De installatiewizard gebruiken voor het instellen van Microsoft 365 Business](set-up.md)
    
    Als u **permanent van een lokale Active Directory naar de Cloud verhuist**, u naar het microsoft 365 Business Admin Center gaan en de installatiewizard gebruiken om uw gebruikers handmatig toe te voegen, of u een eenmalige synchronisatie uitvoeren met Azure AD Connect. U kunt dit op twee manieren doen: 
    
    - Als u ook een Exchange 2010, Exchange 2013 of Exchange 2016 server hebt, u [minimaal hybride gebruiken om snel Exchange-postvakken naar Office 365 te migreren](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef). De minimale hybride stappen omvatten een eenmalige synchronisatie van gebruikers naar Azure AD en e-mail migratie van on-premises naar de Cloud. Nadat de e-mail migratie is voltooid, wordt de adreslijstsynchronisatie automatisch uitgeschakeld wanneer u deze methode gebruikt.
    
    - Gebruik de Office 365 Directory Sync wizard om uw gebruikers te synchroniseren met de Cloud. Volg de stappen in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) om dit proces te voltooien. Nadat u uw gebruikers hebt gesynchroniseerd met de Cloud, moet u [adreslijstsynchronisatie voor Office 365 uitschakelen](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d).
    
    U moet ook elke gebruiker die op deze manier is toegevoegd, een licentie voor Microsoft 365 Business geven. U dit doen in de [installatiewizard](set-up.md) of u [licenties toewijzen aan gebruikers in Office 365 voor bedrijven](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC).
    
### <a name="2-prepare-mobile-devices"></a>2: mobiele apparaten voorbereiden

Volg de stappen in [mobiele apparaten instellen voor Microsoft 365 zakelijke gebruikers](set-up-mobile-devices.md) Office-apps installeren op apparaten en zorg ervoor dat ze zijn beveiligd door microsoft 365 Business. 
  
### <a name="3-prepare-pcs"></a>3: Pc's voorbereiden

Beheerders kunnen instellingen voor nieuwe Windows 10-Pc's vooraf selecteren met behulp van [Windows Autopilot](add-autopilot-devices-and-profile.md). Gebruikers kunnen hun bestaande of nieuwe Windows 10-apparaten instellen door de stappen in dit onderwerp te volgen: [Windows-Pc's instellen voor Microsoft 365 zakelijke gebruikers](set-up-windows-devices.md). Voor bestaande apparaten kunnen gebruikers **desgewenst** [bestanden verplaatsen naar OneDrive voor bedrijven](move-files-to-onedrive.md). Ze kunnen ook hulpprogramma's van derden gebruiken om bestanden te verplaatsen die zijn gekoppeld aan Windows-profiel naar OneDrive.
  
Als uw organisatie gebruikmaakt van on-premises Windows Server Active Directory, u Microsoft 365 Business instellen om uw Windows 10-apparaten te beveiligen, terwijl u nog steeds toegang hebt tot on-premises bronnen waarvoor lokale verificatie is vereist. Volg de stappen in [Windows 10-apparaten met een domein verbinding inschakelen die door Microsoft 365 Business worden beheerd](manage-windows-devices.md) om dit in te stellen. Deze methode heeft de voorkeur en apparaten in deze status worden **hybride Azure AD gekoppelde apparaten**genoemd. 
  
Als u een lokale Active Directory met bepaalde on-premises resources (zoals bestandsshares en printers) bewaart, u uw **Azure AD-gekoppelde apparaten** toegang geven tot deze resources door de stappen hier: [toegang tot on-premises resources van een Azure AD gekoppelde apparaat in Microsoft 365 Business](access-resources.md).
  
  
## <a name="contact-support"></a>Neem contact op met ondersteuning.

 **Ga als volgt te werk als u contact wilt opnemen met Ondersteuning:**
  
- Neem contact op met uw partner.
    
- Als Microsoft 365 Business admin heb je toegang tot ons Customer Support team: ** [contact opnemen met ondersteuning voor zakelijke producten-admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="related-topics"></a>Verwante onderwerpen
[Microsoft 365 Business-documentatie en -informatiebronnen](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Microsoft 365 Business beheren](manage.md)[Migreren naar Microsoft 365 Business](migrate-to-microsoft-365-business.md)
  

