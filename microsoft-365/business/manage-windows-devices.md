---
title: Toestaan dat aan een domein toegevoegde Windows 10-apparaten door Microsoft 365 Business worden beheerd
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Informatie over het inschakelen van Microsoft 365 voor het beveiligen van lokale AD gekoppelde Windows 10-apparaten.
ms.openlocfilehash: 5cce4bc53f118560e31ad7e6048e4efcb49d662e
ms.sourcegitcommit: c0f769244d05ad019ea2307c38d5543d7b1e5afd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/16/2019
ms.locfileid: "36992224"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Toestaan dat aan een domein toegevoegde Windows 10-apparaten door Microsoft 365 Business worden beheerd

Als uw organisatie gebruikmaakt van on-premises Windows Server Active Directory, u Microsoft 365 Business instellen om uw Windows 10-apparaten te beveiligen, terwijl u nog steeds toegang hebt tot on-premises bronnen waarvoor lokale verificatie is vereist. U dit instellen door eerst uw Active Directory synchroniseren met Azure Active Directory, gevolgd door het registreren van de Windows 10-apparaten met Azure AD en ze inschrijven voor Mobile Device Management door Microsoft 365 Business.
De volgende Videodetails de stappen voor het instellen van dit voor de meest voorkomende scenario.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a>Domein apparaten instellen die moeten worden beheerd door Microsoft 365 Business

Als u wilt instellen van uw organisatie domein apparaten om te profiteren van de mogelijkheden die worden geleverd door Azure Active Directory naast on-premises Active Directory, u **hybride Azure AD gekoppelde apparaten**implementeren. Dit zijn apparaten die zijn gekoppeld aan uw on-premises Active Directory en uw Azure Active Directory. Hybride Azure AD gekoppelde apparaten kunnen worden beveiligd en beheerd door Microsoft 365 Business. 
  
Voltooi de onderstaande stappen om uw Windows 10-apparaten hybride Azure AD toegevoegd en beheerd door Microsoft 365 Business.
  
1. Voor het synchroniseren van uw gebruikers, groepen en contactpersonen van lokale Active Directory in azure Active Directory, voert u de wizard Directory-synchronisatie en Azure Active Directory Connect zoals beschreven in [Directory-synchronisatie voor Office 365 instellen](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
    > [!NOTE]
    > De stappen zijn precies hetzelfde voor Microsoft 365 Business. 
  
2. Voordat u stap 3 om in te schakelen van Windows 10-apparaten hybride Azure AD toegevoegd, moet u om ervoor te zorgen dat u aan de volgende vereisten voldoen:

   - U gebruikt de nieuwste versie van Azure AD Connect.

   - Azure AD Connect is gesynchroniseerd met alle computer objecten van de apparaten die u wilt worden hybride Azure AD toegevoegd. Als de computer objecten deel uitmaken van specifieke organisatie-eenheden (OE), zorg ervoor dat deze organisatie-eenheid zijn ingesteld voor synchronisatie in azure AD Connect ook.
    
3. Registreer bestaande domein Windows 10-apparaten als hybride Azure AD toegevoegd en Registreer deze voor beheer van mobiele apparaten door intune (Microsoft 365 Business):
    
4. Volg de stap voor stap instructies in het [configureren van hybride Azure Active Directory gekoppelde apparaten](https://go.microsoft.com/fwlink/p/?linkid=872870). Hiermee schakelt u de synchronisatie van uw on-premises Active Directory is aangesloten op Windows 10-computers en maken ze klaar voor de Cloud.
    
5. Als u een Windows 10-apparaat wilt inschrijven voor beheer van mobiele apparaten, raadpleegt u een [Windows 10-apparaat inschrijven bij intune met behulp van een Groepsbeleid](https://go.microsoft.com/fwlink/p/?linkid=872871) voor instructies. U het Groepsbeleid instellen op lokaal computerniveau of voor bulkbewerkingen, u deze instelling voor Groepsbeleid op de server van uw domeincontroller maken.