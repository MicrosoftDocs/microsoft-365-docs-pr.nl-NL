---
title: Aan de slag met Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Informatie over Microsoft 365 Business instellen.
ms.openlocfilehash: 80c6590a682af5fadeceac7a75e409adac897f6f
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276717"
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
  
In het volgende diagram wordt beschreven hoe Microsoft 365 Business beheerders instellen. Ook worden de stappen beschreven voor de voorbereiding van Windows-pc's voor Microsoft 365 Business. U kunt ook nieuwe apparaten toevoegen in het Microsoft 365 Business-beheercentrum met de [Windows AutoPilot](add-autopilot-devices-and-profile.md). U kunt AutoPilot gebruiken voor het instellen en vooraf configureren van nieuwe apparaten, zodat deze klaar zijn voor productief gebruik wanneer een gebruiker zich aanmeldt met de Microsoft 365 Business-referenties.
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: instellen van Microsoft 365 Business (Admin)

Meld u aan bij het [Microsoft 365 Business-beheercentrum](https://portal.office.com/adminportal/home) met uw globale-beheerdersreferenties en voltooi de onderstaande stappen om Microsoft 365 Business in te stellen. 
  
1. [Vereisten voor het beschermen van gegevens op apparaten met Microsoft 365 Business](pre-requisites-for-data-protection.md)
    
    Lees eerst de vereisten om te controleren of uw apparaten gereed zijn voor Microsoft 365 Business.
    
2. [Microsoft 365 Business instellen met de wizard Setup](set-up.md)
    
    Als u **permanent verplaatsen van een lokale Active Directory naar de cloud**, kunt u ofwel uw gebruikers handmatig toevoegen in het beheercentrum voor Microsoft 365 Business met behulp van de wizard setup of u kunt een eenmalige synchronisatie met Azure AD verbinden doen. U kunt dit op twee manieren doen: 
    
  - Hebt u ook een Exchange 2010, Exchange 2013 of 2016 van Exchange server, kunt u de [Minimale hybride gebruik snel migreren naar Office 365 Exchange-postbussen](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef). De minimale hybride stappen omvatten een eenmalige synchronisatie van gebruikers met Azure AD en de e-mailmigratie van on-premises naar de cloud. Wanneer de e-mailmigratie is voltooid, wordt de adreslijstsynchronisatie automatisch uitgeschakeld bij gebruik van deze methode.
    
  - Gebruik de Office 365-wizard voor adreslijstsynchronisatie om uw gebruikers te synchroniseren met de cloud. Volg de stappen in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) om dit proces te voltooien. Nadat u uw gebruikers hebt gesynchroniseerd met de cloud, moet u [Turn off directory synchronization for Office 365](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d).
    
    U moet ook aan elke gebruiker die op deze manier is toegevoegd, een licentie voor Microsoft 365 Business verlenen. U kunt dit doen in de [wizard setup](set-up.md)of in het [toewijzen van licenties aan gebruikers in Office 365 voor bedrijven](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC).
    
### <a name="2-prepare-mobile-devices"></a>2: voorbereiden van mobiele apparaten

Volg de stappen in het[instellen van mobiele apparaten voor gebruikers van Microsoft 365 Business](set-up-mobile-devices.md) Office apps installeren op apparaten en ervoor te zorgen dat ze beschermd worden door Microsoft 365 Business. 
  
### <a name="3-prepare-pcs"></a>3: pc's voorbereiden

Beheerders kunnen vooraf selecteren instellingen voor nieuwe apparaten Windows 10 pc's met [Windows Automatische piloot](add-autopilot-devices-and-profile.md). Gebruikers kunnen hun bestaande of nieuwe Windows 10-apparaten instellen met behulp van de stappen in dit onderwerp: [instellen voor Microsoft 365 zakelijke gebruikers die Windows-pc's](set-up-windows-devices.md). Voor bestaande apparaten kunnen ook **eventueel**[verplaatsen van bestanden met OneDrive voor bedrijven](move-files-to-onedrive.md). Ze kunnen ook hulpprogramma's van derden gebruiken om bestanden die zijn gekoppeld aan Windows-profiel om OneDrive te verplaatsen.
  
Als uw organisatie gebruikmaakt van Windows Server Active Directory op lokalen, kunt u Microsoft 365 Business instellen ter bescherming van uw Windows 10-apparaten, terwijl zij toch toegang tot bronnen voor ruimten die lokale verificatie vereisen. Volg de stappen in [Windows 10-apparaten worden beheerd door Microsoft 365 Business domein behoren](manage-windows-devices.md) tot dit instellen. Dit is de aanbevolen methode en apparaten in deze toestand **hybride Azure AD verbonden apparaten**worden genoemd. 
  
Als u bewaren op een lokale Active Directory met sommige op-ruimten (zoals bestandsshares en printers), u kunt uw **Azure AD verbonden apparaten** toegang geven tot deze bronnen door de stappen hier: [toegang op-premises resources uit een Azure AD verbonden apparaat in Microsoft 365 Business](access-resources.md).
  
Nadat u een Windows 10 pc's hebt ingesteld, kunt u de [installatie van Office automatisch](auto-install-or-uninstall-office.md) aan de apparaten. 
  
## <a name="contact-support"></a>Neem contact op met ondersteuning.

 **Ga als volgt te werk als u contact wilt opnemen met Ondersteuning:**
  
- Neem contact op met uw partner.
    
- Als een beheerder Microsoft 365 Business hebt u toegang tot onze customer support team ** [contact met ondersteuning voor zakelijke producten - Help voor Admin](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    

