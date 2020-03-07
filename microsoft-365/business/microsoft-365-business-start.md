---
title: Aan de slag met Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Meer informatie over Microsoft 365 Business, hoe u deze instellen en hoe u de apparaten en pc's van uw gebruikers voorbereidt om ervoor te zorgen dat ze worden beschermd door Microsoft 365 Business.
ms.openlocfilehash: 220fb747e2bc501f3f6d46d967b30d2e5fd79a4a
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561435"
---
# <a name="get-started-with-microsoft-365-business"></a>Aan de slag met Microsoft 365 Business

## <a name="what-is-microsoft-365-business"></a>Wat is Microsoft 365 Business

Microsoft 365 Business is een uitgebreide set hulpprogramma's voor bedrijfsproductiviteit en samenwerking, zoals Outlook, Word, Excel en andere Office-producten, die altijd up-to-date zijn. U uw werkbestanden op al uw iOS-, Android- en Windows 10-apparaten beveiligen met beveiliging van bedrijfsniveau die eenvoudig te beheren is.

Bekijk deze video voor een snel overzicht van Microsoft 365 Business.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 Business is bedoeld voor maximaal 300 licenties. Zie [Microsoft 365 Enterprise-documentatie](https://go.microsoft.com/fwlink/p/?linkid=860986) voor meer informatie als u meer licenties nodig hebt. 
  
## <a name="get-microsoft-365-business"></a>Microsoft 365 Business kopen

- Als u een partner hebt, krijgt deze Microsoft 365 Business: [Download Microsoft 365 Business van Microsoft Partner Center.](get-microsoft-365-business.md)
    
- Als u niet met een partner werkt en Microsoft 365 Business wilt kopen, kunt u [contact opnemen met ](https://www.microsoft.com/microsoft-365/business).
    
## <a name="set-up-microsoft-365-business"></a>Microsoft 365 Business instellen

 **Overzicht van microsoft 365 Business Suite ingesteld**
  
In het volgende diagram wordt beschreven hoe beheerders Microsoft 365 Business instellen. Ook worden de stappen beschreven voor de voorbereiding van Windows-pc's voor Microsoft 365 Business. U ook nieuwe apparaten toevoegen in het Microsoft 365 Business-beheercentrum met [Windows AutoPilot.](add-autopilot-devices-and-profile.md) U AutoPilot gebruiken om nieuwe apparaten in te stellen en vooraf te configureren, zodat ze klaar zijn voor productief gebruik zodra een gebruiker zich aanmeldt met zijn Microsoft 365 Business-referenties.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Bekijk deze video voor een overzicht van microsoft 365 Business setup.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Als u deze video nuttig vond, raadpleegt u dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: Microsoft 365 Business instellen (beheerder)

Meld u aan bij het [Microsoft 365 Business-beheercentrum](https://portal.office.com/adminportal/home) met uw globale beheerdersreferenties en voer de volgende stappen uit om Microsoft 365 Business in te stellen. 
  
1. [Voorwaarden voor het beveiligen van gegevens op apparaten met Microsoft 365 Business](pre-requisites-for-data-protection.md)
    
    Lees eerst de vereisten om ervoor te zorgen dat uw apparaten klaar zijn voor Microsoft 365 Business.
    
2. [De wizard Setup gebruiken om Microsoft 365 Business in te stellen](set-up.md)
    
    Als u **permanent overstapt van een lokale Active Directory naar de cloud,** u naar het Microsoft 365 Business-beheercentrum gaan en de wizard Setup gebruiken om uw gebruikers handmatig toe te voegen of u een eenmalige synchronisatie uitvoeren met Azure AD Connect. U kunt dit op twee manieren doen: 
    
    - Als u ook een Exchange 2010-, Exchange 2013- of Exchange 2016-server hebt, u [Minimal Hybrid gebruiken om Exchange-postvakken snel te migreren naar Office 365.](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef) De minimale hybride stappen omvatten een eenmalige synchronisatie van gebruikers naar Azure AD en e-mailmigratie van on-premises naar de cloud. Nadat de e-mailmigratie is voltooid, wordt de adreslijstsynchronisatie automatisch uitgeschakeld wanneer u deze methode gebruikt.
    
    - Gebruik de wizard Office 365-mapsynchronisatie om uw gebruikers te synchroniseren met de cloud. Volg de stappen in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) om dit proces te voltooien. Nadat u uw gebruikers hebt gesynchroniseerd met de cloud, moet u [adreslijstsynchronisatie uitschakelen voor Office 365.](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d)
    
    U moet ook elke gebruiker die op deze manier is toegevoegd, een licentie geven aan Microsoft 365 Business. U dit doen in de [wizard Setup](set-up.md) of u licenties toewijzen aan gebruikers in [Office 365 voor Bedrijven.](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC)
    
### <a name="2-prepare-mobile-devices"></a>2: Mobiele apparaten voorbereiden

Volg de stappen in [Mobiele apparaten instellen voor Microsoft 365 Business-gebruikers](set-up-mobile-devices.md) om Office-apps op apparaten te installeren en ervoor te zorgen dat ze worden beschermd door Microsoft 365 Business. 
  
### <a name="3-prepare-pcs"></a>3: Pc's voorbereiden

Beheerders kunnen instellingen voor nieuwe Windows 10-pc's vooraf selecteren met [Windows AutoPilot.](add-autopilot-devices-and-profile.md) Gebruikers kunnen hun bestaande of nieuwe Windows 10-apparaten instellen door de stappen in dit onderwerp te volgen: [Windows-pc's instellen voor Microsoft 365 Business-gebruikers](set-up-windows-devices.md). Voor bestaande apparaten kunnen gebruikers **bestanden optioneel** verplaatsen [naar OneDrive voor Bedrijven.](move-files-to-onedrive.md) Ze kunnen ook hulpprogramma's van derden gebruiken om bestanden die zijn gekoppeld aan Windows-profiel naar OneDrive te verplaatsen.
  
Als uw organisatie On-premises gebruik maakt van Windows Server Active Directory, u Microsoft 365 Business instellen om uw Windows 10-apparaten te beschermen, terwijl u nog steeds toegang behoudt tot on-premises bronnen waarvoor lokale verificatie vereist is. Volg de stappen in [Windows 10-apparaten inschakelen die door Microsoft 365 Business moeten worden beheerd](manage-windows-devices.md) om dit in te stellen. Deze methode heeft de voorkeur en apparaten in deze status worden **hybride Azure AD-verbonden apparaten**genoemd. 
  
Als u een lokale Active Directory behoudt die een aantal on-premises bronnen (zoals bestandsshares en printers) bevat, u uw **azure AD-verbonden apparaten** toegang geven tot deze bronnen door de stappen hier te volgen: [On-premises bronnen openen vanaf een Azure AD-verbonden apparaat in Microsoft 365 Business](access-resources.md).
  
  
## <a name="contact-support"></a>Contact opnemen met de ondersteuning

 **Ga als volgt te werk als u contact wilt opnemen met Ondersteuning:**
  
- Neem contact op met uw partner.
    
- Als Beheerder van Microsoft 365 Business heeft u toegang tot ons klantenserviceteam: ** [neem contact op met ondersteuning voor zakelijke producten - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="see-also"></a>Zie ook

[Microsoft 365 Business-documentatie en -informatiebronnen](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Microsoft 365 Business beheren](manage.md)[Migreren naar Microsoft 365 Business](migrate-to-microsoft-365-business.md)

[Trainingsvideo's voor Microsoft 365 Business](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) 
