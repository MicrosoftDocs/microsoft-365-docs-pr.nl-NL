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
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Meer informatie over Microsoft 365 voor bedrijven, het instellen ervan en hoe u de apparaten en pc's van uw gebruikers voorbereidt om te controleren of ze worden beschermd door Microsoft 365 voor bedrijven.
ms.openlocfilehash: 8754c470cb6369f0814f953288be130fa49cea86
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048080"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Aan de slag met Microsoft 365 voor bedrijven

## <a name="what-is-microsoft-365-for-business"></a>Wat is Microsoft 365 voor bedrijven

Microsoft 365 voor bedrijven is een uitgebreide reeks tools voor bedrijfsproductiviteit en samenwerking, zoals Outlook, Word, Excel en andere Office-producten, die altijd up-to-date zijn. U uw werkbestanden beveiligen op al uw iOS-, Android- en Windows 10-apparaten met beveiliging op bedrijfsniveau die eenvoudig te beheren is.

Bekijk deze video voor een snel overzicht van Microsoft 365 voor bedrijven.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 voor bedrijven is bedoeld voor maximaal 300 licenties. Als u meer licenties nodig hebt, raadpleegt u de documentatie bij [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) voor meer informatie. 
  
## <a name="get-microsoft-365-for-business"></a>Microsoft 365 voor bedrijven inde uhalen

- Als u een partner hebt, krijgt deze Microsoft 365 voor bedrijven: [Microsoft 365 voor bedrijven ophalen vanuit Microsoft Partner Center.](get-microsoft-365-business.md)
    
- Als u geen partner hebt en Microsoft 365 voor bedrijven wilt kopen, u [deze hier kopen.](https://www.microsoft.com/microsoft-365/business)
    
## <a name="set-up-microsoft-365-for-business"></a>Microsoft 365 voor bedrijven instellen

 **Overzicht van Microsoft 365 for business Suite set-up**
  
In het volgende diagram wordt beschreven hoe beheerders Microsoft 365 voor bedrijven instellen. Het beschrijft ook de stappen om Windows-pc's voor te bereiden op Microsoft 365 voor bedrijven. U ook nieuwe apparaten toevoegen in het Microsoft 365-beheercentrum met [Windows AutoPilot](add-autopilot-devices-and-profile.md). U AutoPilot gebruiken om nieuwe apparaten zo in te stellen en vooraf te configureren, zodat ze klaar zijn voor productief gebruik zodra een gebruiker zich aanmeldt met zijn Microsoft 365 voor zakelijke referenties.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Bekijk deze video voor een overzicht van Microsoft 365 voor zakelijke installatie.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Als u deze video nuttig vond, raadpleegt u dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: Microsoft 365 voor bedrijven instellen (beheerder)

Meld u aan bij [het Microsoft 365-beheercentrum](https://portal.office.com/adminportal/home) met uw globale beheerdersreferenties en voer de volgende stappen uit om Microsoft 365 voor bedrijven in te stellen. 
  
1. [Voorwaarden voor het beveiligen van gegevens op apparaten met Microsoft 365 voor bedrijven](pre-requisites-for-data-protection.md)
    
    Lees eerst de vereisten om ervoor te zorgen dat uw apparaten klaar zijn voor Microsoft 365 voor bedrijven.
    
2. [De wizard Setup gebruiken om Microsoft 365 voor bedrijven in te stellen](set-up.md)
    
    Als u **permanent van een lokale Active Directory naar de cloud gaat,** u naar het Microsoft 365-beheercentrum gaan en de wizard Setup gebruiken om uw gebruikers handmatig toe te voegen, of u een eenmalige synchronisatie uitvoeren met Azure AD Connect. U kunt dit op twee manieren doen: 
    
    - Als u ook een Exchange 2010-, Exchange 2013- of Exchange 2016-server hebt, u [Minimal Hybrid gebruiken om Exchange-postvakken snel te migreren naar Office 365.](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef) De minimale hybride stappen omvatten een eenmalige synchronisatie van gebruikers met Azure AD en e-mailmigratie van on-premises naar de cloud. Nadat de e-mailmigratie is voltooid, wordt de adreslijstsynchronisatie automatisch uitgeschakeld wanneer u deze methode gebruikt.
    
    - Gebruik de wizard Directorysynchronisatie om uw gebruikers te synchroniseren met de cloud. Volg de stappen in [Adreslijstsynchronisatie instellen voor Microsoft 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) om dit proces te voltooien. Nadat u uw gebruikers hebt gesynchroniseerd met de cloud, moet u [adreslijstsynchronisatie uitschakelen voor Office 365.](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d)
    
    U moet ook elke gebruiker die op deze manier is toegevoegd, een licentie aan Microsoft 365 voor bedrijven geven. U dit doen in de [wizard Setup](set-up.md) of u licenties toewijzen aan gebruikers in [Microsoft 365 voor Bedrijven.](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users)
    
### <a name="2-prepare-mobile-devices"></a>2: Mobiele apparaten voorbereiden

Volg de stappen in [Mobiele apparaten instellen voor Microsoft 365 voor zakelijke gebruikers](set-up-mobile-devices.md) om Office-apps op apparaten te installeren en ervoor te zorgen dat ze worden beschermd door Microsoft 365 voor Bedrijven. 
  
### <a name="3-prepare-pcs"></a>3: Pc's voorbereiden

Beheerders kunnen vooraf instellingen voor nieuwe Windows 10-pc's selecteren met [Windows AutoPilot](add-autopilot-devices-and-profile.md). Gebruikers kunnen hun bestaande of nieuwe Windows 10-apparaten instellen door de stappen in dit onderwerp te volgen: [Windows-pc's instellen voor Microsoft 365 voor zakelijke gebruikers.](set-up-windows-devices.md) Voor bestaande apparaten kunnen gebruikers **bestanden optioneel** verplaatsen [naar OneDrive voor Bedrijven.](move-files-to-onedrive.md) Ze kunnen ook hulpprogramma's van derden gebruiken om bestanden die zijn gekoppeld aan Windows-profiel naar OneDrive te verplaatsen.
  
Als uw organisatie on-premises Windows Server Active Directory gebruikt, u Microsoft 365 voor bedrijven instellen om uw Windows 10-apparaten te beschermen, terwijl u toch toegang behoudt tot on-premises bronnen waarvoor lokale verificatie vereist is. Volg de stappen in [Windows 10-apparaten met domein ingeschakeld die door Microsoft 365 voor bedrijven moeten worden beheerd](manage-windows-devices.md) om dit in te stellen. Deze methode heeft de voorkeur en apparaten in deze status worden **hybride Azure AD-samengevoegde apparaten**genoemd. 
  
Als u een lokale Active Directory behoudt die een aantal on-premises bronnen bevat (zoals bestandsshares en printers), u uw **Azure AD-apparaten** toegang geven tot deze bronnen door de volgende stappen te volgen: [Toegang tot on-premises bronnen vanaf een apparaat dat is verbonden met Azure AD in Microsoft 365 voor Bedrijven.](access-resources.md)
  
  
## <a name="contact-support"></a>Contact opnemen met de ondersteuning

 **Ga als volgt te werk als u contact wilt opnemen met Ondersteuning:**
  
- Neem contact op met uw partner.
    
- Als Microsoft 365 voor zakelijke beheerder heeft u toegang tot ons klantenserviceteam: ** [neem contact op met ondersteuning voor zakelijke producten - Help voor beheerders](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="see-also"></a>Zie ook

[Microsoft 365 voor bedrijfsdocumentatie en -bronnen](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Microsoft 365 voor bedrijven beheren](manage.md)[Migreren naar Microsoft 365 voor bedrijven](migrate-to-microsoft-365-business.md)

[Trainingsvideo's voor Microsoft 365 voor bedrijven](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) 
