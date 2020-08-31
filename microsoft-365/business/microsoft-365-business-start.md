---
title: Aan de slag met Microsoft 365 voor bedrijven
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
description: Meer informatie over Microsoft 365 voor bedrijven, hoe u dit kunt instellen en hoe u de apparaten en Pc's van de gebruikers kunt voorbereiden, zodat u zeker weet dat ze zijn beveiligd met Microsoft 365 voor bedrijven.
ms.openlocfilehash: ec50036f589cfd8497b0e7e9af6519b30d25dcd3
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306484"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Aan de slag met Microsoft 365 voor bedrijven

## <a name="what-is-microsoft-365-for-business"></a>Wat is Microsoft 365 voor bedrijven

Microsoft 365 voor bedrijven is een uitgebreide set zakelijke productiviteit en samenwerkingshulpmiddelen, zoals Outlook, Word, Excel en andere Office-producten, die altijd up-to-date zijn. U kunt uw werkbestanden op al uw iOS-, Android-en Windows 10-apparaten beveiligen met een eenvoudige beveiliging van de organisatie.

Bekijk deze video voor een kort overzicht van Microsoft 365 voor bedrijven.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 voor bedrijven is bedoeld voor maximaal 300 licenties. Als u meer licenties nodig hebt, raadpleegt u de documentatie bij [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) voor meer informatie. 
  
## <a name="get-microsoft-365-for-business"></a>Microsoft 365 voor bedrijven kopen

- Als u een partner hebt, krijgen ze Microsoft 365 voor bedrijven: [Microsoft 365 voor bedrijven kopen bij Microsoft Partner Center](get-microsoft-365-business.md).
    
- Als u geen partner hebt en Microsoft 365 for Business wilt kopen, kunt u [het hier kopen](https://www.microsoft.com/microsoft-365/business).
    
## <a name="set-up-microsoft-365-for-business"></a>Microsoft 365 voor bedrijven instellen

 **Overzicht van de instelling van Microsoft 365 for Business Suite**
  
In het volgende diagram wordt beschreven hoe beheerders Microsoft 365 voor bedrijven instellen. Ook worden de stappen beschreven voor het voorbereiden van Windows-Pc's voor Microsoft 365 voor bedrijven. U kunt ook nieuwe apparaten toevoegen in het Microsoft 365-Beheercentrum met de [Windows auto pilot](add-autopilot-devices-and-profile.md). Met auto pilot kunt u nieuwe apparaten instellen en vooraf configureren, zodat deze klaar zijn voor gebruik zodra een gebruiker zich aanmeldt met hun Microsoft 365 for Business-referenties.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Bekijk deze video voor een overzicht van de configuratie van Microsoft 365 voor bedrijven.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Als u deze video nuttig vond, raadpleegt u dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: Microsoft 365 voor bedrijven instellen (beheerder)

Meld u aan bij het [Beheercentrum van Microsoft 365](https://portal.office.com/adminportal/home) met uw globale-beheerdersreferenties en voer de volgende stappen uit om microsoft 365 voor bedrijven in te stellen. 
  
1. [Vereisten voor het beschermen van gegevens op apparaten met Microsoft 365 voor bedrijven](pre-requisites-for-data-protection.md)
    
    Lees eerst de vereisten om te controleren of uw apparaten gereed zijn voor Microsoft 365 voor bedrijven.
    
2. [De installatiewizard gebruiken om Microsoft 365 voor bedrijven in te stellen](set-up.md)
    
    Als u **permanent van een lokale Active Directory naar de Cloud overstapt**, gaat u naar het microsoft 365-Beheercentrum en gebruikt u de installatiewizard om uw gebruikers handmatig toe te voegen, of u kunt een eenmalige synchronisatie uitvoeren met Azure AD Connect. U kunt dit op twee manieren doen: 
    
    - Als u ook een Exchange 2010, Exchange 2013 of Exchange 2016-server hebt, kunt u [minimale Hybrid gebruiken om snel Exchange-postvakken te migreren naar Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate). De minimale hybride stappen zijn een eenmalige synchronisatie van gebruikers naar Azure AD en e-mail migratie van on-premises naar de Cloud. Wanneer de e-mail migratie is voltooid, wordt adreslijstsynchronisatie automatisch uitgeschakeld wanneer u deze methode gebruikt.
    
    - Met de wizard adreslijstsynchronisatie kunt u gebruikers synchroniseren met de Cloud. Volg de stappen in [adreslijstsynchronisatie instellen voor Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) om dit proces te voltooien. Nadat u uw gebruikers hebt gesynchroniseerd met de Cloud, moet u [adreslijstsynchronisatie uitschakelen voor Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/turn-off-directory-synchronization).
    
    U dient ook elke gebruiker uit te geven die op deze manier is toegevoegd als een licentie voor Microsoft 365 voor bedrijven. U kunt dit doen in de [installatiewizard](set-up.md) of u kunt [licenties toewijzen aan gebruikers](../admin/manage/assign-licenses-to-users.md).
    
### <a name="2-prepare-mobile-devices"></a>2: mobiele apparaten voorbereiden

Voer de stappen uit in [mobiele apparaten instellen voor Microsoft 365 voor bedrijven-gebruikers](set-up-mobile-devices.md) om Office-apps op apparaten te installeren en zorg ervoor dat deze zijn beveiligd met microsoft 365 voor bedrijven. 
  
### <a name="3-prepare-pcs"></a>3: Pc's voorbereiden

Beheerders kunnen instellingen voor nieuwe Windows 10-Pc's vooraf selecteren met behulp van [Windows auto pilot](add-autopilot-devices-and-profile.md). Gebruikers kunnen hun bestaande of nieuwe Windows 10-apparaten instellen door de stappen te volgen in dit onderwerp: [Windows-Pc's instellen voor gebruikers van Microsoft 365 voor bedrijven](set-up-windows-devices.md). Voor bestaande apparaten kunnen gebruikers **optioneel** [bestanden verplaatsen naar OneDrive voor bedrijven](move-files-to-onedrive.md). Ze kunnen ook gebruikmaken van Programma's van derden voor het verplaatsen van bestanden die zijn gekoppeld aan Windows-profielen naar OneDrive.
  
Als uw organisatie Windows Server Active Directory on-premises gebruikt, kunt u Microsoft 365 voor bedrijven instellen voor het beschermen van uw Windows 10-apparaten, terwijl u nog steeds toegang hebt tot on-premises bronnen waarvoor lokale verificatie is vereist. Voer de stappen uit in [Windows 10-apparaten die aan het domein zijn toegevoegd om te worden beheerd door Microsoft 365 voor bedrijven](manage-windows-devices.md) om dit in te stellen. Deze methode is voorkeur, en apparaten in deze status worden aan de slag met een **hybride Azure AD-apparaat**. 
  
Als u een lokale Active Directory behoudt met bepaalde on-premises resources (zoals bestanden en printers), kunt u uw Azure Active Directory **-apparaten** toegang verlenen tot deze bronnen door deze stappen te volgen: [on-premises resources openen vanuit een Azure AD-domein dat is gekoppeld aan Microsoft 365 voor bedrijven](access-resources.md).
  
  
## <a name="contact-support"></a>Contact opnemen met de ondersteuning

 **Ga als volgt te werk als u contact wilt opnemen met Ondersteuning:**
  
- Neem contact op met uw partner.
    
- Als Microsoft 365 voor bedrijven-beheerder hebt u toegang tot ons klant ondersteuningsteam: ** [contact opnemen met ondersteuning voor bedrijfsproducten-Help voor beheerders](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)**
    
## <a name="see-also"></a>Zie ook

[Documentatie en bronnen voor Microsoft 365 voor bedrijven](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
Migratie van [Microsoft 365 voor bedrijven beheren](manage.md)[naar Microsoft 365 voor bedrijven](migrate-to-microsoft-365-business.md)

[Trainingsvideo's voor Microsoft 365 voor bedrijven](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) 
