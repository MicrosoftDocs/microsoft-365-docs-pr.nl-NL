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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Meer informatie over het instellen van Microsoft 365 Business.
ms.openlocfilehash: 52e3167986bb7ed835762540e8076a3b9b2a0b56
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287630"
---
# <a name="get-started-with-microsoft-365-business"></a>Aan de slag met Microsoft 365 Business

## <a name="what-is-microsoft-365-business"></a>Wat is Microsoft 365 Business

Microsoft 365 Business is een uitgebreide reeks zakelijke hulpmiddelen voor productiviteit en samenwerking, zoals Outlook, Word, Excel en andere Office-producten, die altijd up-to-date zijn. U kunt uw werkbestanden op al uw iOS-, Android- en Windows 10-apparaten beveiligen met geavanceerde beveiliging die eenvoudig is te beheren.
  
Microsoft 365 Business is bedoeld voor maximaal 300 licenties. Als u meer licenties nodig hebt, raadpleegt u de documentatie voor [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) voor meer informatie. 
  
## <a name="get-microsoft-365-business"></a>Microsoft 365 Business kopen

- Als u een partner hebt, ontvangt deze Microsoft 365 Business: [Microsoft 365 Business verkrijgen via Microsoft Partner Center](get-microsoft-365-business.md).
    
- Als u niet met een partner werkt en Microsoft 365 Business wilt kopen, kunt u [contact opnemen met ](https://www.microsoft.com/en-us/microsoft-365/business).
    
## <a name="set-up-microsoft-365-business"></a>Microsoft 365 Business instellen

 **Overzicht van Microsoft 365 Business Suite instellen**
  
In het volgende diagram wordt beschreven hoe beheerders Microsoft 365 Business hebben ingesteld. Ook worden de stappen beschreven voor de voorbereiding van Windows-pc's voor Microsoft 365 Business. U kunt ook nieuwe apparaten toevoegen in het Microsoft 365 Business-beheercentrum met de [Windows AutoPilot](add-autopilot-devices-and-profile.md). U kunt AutoPilot gebruiken voor het instellen en vooraf configureren van nieuwe apparaten, zodat deze klaar zijn voor productief gebruik wanneer een gebruiker zich aanmeldt met de Microsoft 365 Business-referenties.
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: Microsoft 365 Business (admin) instellen

Meld u aan bij het [Microsoft 365 Business-beheercentrum](https://portal.office.com/adminportal/home) met uw globale-beheerdersreferenties en voltooi de onderstaande stappen om Microsoft 365 Business in te stellen. 
  
1. [Vereisten voor het beschermen van gegevens op apparaten met Microsoft 365 Business](pre-requisites-for-data-protection.md)
    
    Lees eerst de vereisten om te controleren of uw apparaten gereed zijn voor Microsoft 365 Business.
    
2. [Microsoft 365 Business instellen met de wizard Setup](set-up.md)
    
    Als u **permanent van een lokale Active Directory naar de Cloud verhuist**, u uw gebruikers handmatig toevoegen in het Beheercentrum van microsoft 365 Business met behulp van de wizard Setup of u een eenmalige synchronisatie met Azure AD Connect doen. U kunt dit op twee manieren doen: 
    
  - Als u ook een Exchange 2010, Exchange 2013 of Exchange 2016 server hebt, u [minimaal hybride gebruiken om snel Exchange-postvakken naar Office 365 te migreren](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef). De minimale hybride stappen omvatten een eenmalige synchronisatie van gebruikers met Azure AD en de e-mailmigratie van on-premises naar de cloud. Wanneer de e-mailmigratie is voltooid, wordt de adreslijstsynchronisatie automatisch uitgeschakeld bij gebruik van deze methode.
    
  - Gebruik de Office 365-wizard voor adreslijstsynchronisatie om uw gebruikers te synchroniseren met de cloud. Volg de stappen in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) om dit proces te voltooien. Nadat u uw gebruikers hebt gesynchroniseerd met de cloud, moet u [Turn off directory synchronization for Office 365](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d).
    
    U moet ook aan elke gebruiker die op deze manier is toegevoegd, een licentie voor Microsoft 365 Business verlenen. U dit doen in de [installatiewizard](set-up.md)of in de [licenties toewijzen aan gebruikers in Office 365 voor bedrijven](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC).
    
### <a name="2-prepare-mobile-devices"></a>2: mobiele apparaten voorbereiden

Volg de stappen in[mobiele apparaten instellen voor Microsoft 365 zakelijke gebruikers](set-up-mobile-devices.md) om Office-apps op apparaten te installeren en ervoor te zorgen dat ze worden beschermd door microsoft 365 Business. 
  
### <a name="3-prepare-pcs"></a>3: Pc's voorbereiden

Beheerders kunnen vooraf selecteren instellingen voor nieuwe apparaten Windows 10 Pc's met behulp van [Windows Autopilot](add-autopilot-devices-and-profile.md). Gebruikers kunnen hun bestaande of nieuwe Windows 10-apparaten instellen door de stappen in dit onderwerp te volgen: [Windows-Pc's instellen voor Microsoft 365 zakelijke gebruikers](set-up-windows-devices.md). Voor bestaande apparaten kunnen gebruikers **desgewenst**ook[bestanden verplaatsen naar OneDrive voor bedrijven](move-files-to-onedrive.md). Ze kunnen ook hulpprogramma's van derden gebruiken om bestanden te verplaatsen die zijn gekoppeld aan Windows-profiel naar OneDrive.
  
Als uw organisatie gebruikmaakt van on-premises Windows Server Active Directory, u Microsoft 365 Business instellen om uw Windows 10-apparaten te beveiligen, terwijl u nog steeds toegang hebt tot on-premises bronnen waarvoor lokale verificatie is vereist. Volg de stappen in [Windows 10-apparaten met een domein verbinding inschakelen die door Microsoft 365 Business worden beheerd](manage-windows-devices.md) om dit in te stellen. Dit is de voorkeursmethode en apparaten in deze status worden **hybride Azure AD gekoppelde apparaten**genoemd. 
  
Als u een lokale Active Directory met bepaalde on-premises bronnen (zoals bestandsshares en printers) bewaart, u uw **Azure ad-apparaten** toegang tot deze resources geven door de stappen hier: [toegang tot on-premises resources van een Azure AD gekoppelde apparaat in Microsoft 365 Business](access-resources.md).
  
Nadat u Windows 10-Pc's hebt ingesteld, u [Office automatisch](auto-install-or-uninstall-office.md) op de apparaten installeren. 
  
## <a name="contact-support"></a>Neem contact op met ondersteuning.

 **Ga als volgt te werk als u contact wilt opnemen met Ondersteuning:**
  
- Neem contact op met uw partner.
    
- Als Microsoft 365 Business admin hebt u toegang tot ons klantenservice team, neem dan ** [contact op met ondersteuning voor zakelijke producten-admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="related-topics"></a>Verwante onderwerpen
[Microsoft 365 Business-documentatie en -informatiebronnen](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Microsoft 365 Business beheren](manage.md)[Migreren naar Microsoft 365 Business](migrate-to-microsoft-365-business.md)
  

