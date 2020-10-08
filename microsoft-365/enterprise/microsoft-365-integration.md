---
title: Microsoft 365-integratie met on-premises omgevingen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: In dit artikel leest u hoe u Microsoft 365 kunt integreren met uw bestaande adreslijstservices en on-premises omgevingen.
ms.openlocfilehash: 9c5e287ed4a440d1f62081a4c94e39f0f162b4dc
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384882"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a>Microsoft 365-integratie met on-premises omgevingen

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

U kunt Microsoft 365 integreren met uw bestaande on-premises Active Directory Domain Services (AD DS) en met on-premises installaties van Exchange Server, Skype voor bedrijven server 2015 of SharePoint Server.
  
 - Wanneer u ACTIVEert, kunt u gebruikersaccounts voor beide omgevingen synchroniseren en beheren. U kunt ook wachtwoord hash-synchronisatie (PHS) of eenmalige aanmelding (SSO) toevoegen, zodat gebruikers zich kunnen aanmelden bij beide omgevingen met hun on-premises referenties.
 - Als u integratie met lokale server producten uitvoert, maakt u een hybride omgeving. Een hybride omgeving kan u helpen bij het migreren van gebruikers of gegevens naar Microsoft 365, of u kunt in de Cloud bepaalde gebruikers of bepaalde informatie on-premises blijven hebben. Zie voor meer informatie over hybride omgevingen [hybride Cloud](../solutions/cloud-architecture-models.md#hybrid).

U kunt ook de Azure Active Directory (Azure AD) adviseurs voor aangepaste instellingsrichtlijnen gebruiken in het Microsoft 365-Beheercentrum (u moet zijn aangemeld bij Microsoft 365):

- [Installatiehandleiding voor Azure AD](https://aka.ms/aadpguidance)
- [Gebruikers synchroniseren vanuit de adreslijst van uw organisatie](https://aka.ms/aadconnectpwsync)
- [Active Directory Federation Services (AD FS) Deployment adviseur](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a>Voordat u begint

Voordat u Microsoft 365 en een lokale omgeving integreert, moet u ook [netwerk planning en prestaties optimaliseren](network-planning-and-performance.md). U kunt ook inzicht krijgen in de beschikbare [identiteits modellen](about-microsoft-365-identity.md). 

Zie [Microsoft 365-accounts beheren](manage-microsoft-365-accounts.md) voor een lijst met hulpmiddelen die u kunt gebruiken voor het beheren van gebruikersaccounts van microsoft 365. 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a>Microsoft 365 integreren met Active Directory

Als u beschikt over bestaande gebruikersaccounts in AD DS, wilt u niet al deze accounts opnieuw maken in Microsoft 365 en risico, waarbij de verschillen of fouten tussen de omgevingen worden geïntroduceerd. Met adreslijstsynchronisatie kunt u de accounts in uw on-premises en online omgevingen spiegelen. Met adreslijstsynchronisatie hoeven gebruikers geen nieuwe informatie voor elke omgeving te onthouden en hoeft u niet twee keer accounts te maken of bij te werken. U moet [uw on-premises adreslijst voorbereiden](prepare-for-directory-synchronization.md) op adreslijstsynchronisatie.
  
![Adreslijstsynchronisatie gebruiken om on-premises en online gegevens van gebruikersaccounts gesynchroniseerd te houden](../media/microsoft-365-integration/directory-synchronization.png)
  
Als u wilt dat gebruikers zich kunnen aanmelden bij Microsoft 365 met hun on-premises referenties, kunt u ook eenmalige aanmelding configureren. Met eenmalige aanmelding is Microsoft 365 geconfigureerd voor het vertrouwen van de on-premises omgeving voor gebruikersauthenticatie.
  
![Met eenmalige aanmelding is hetzelfde account beschikbaar in de on-premises omgeving en de online omgeving](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a>Adreslijstsynchronisatie met of zonder wachtwoord-hash-synchronisatie of Pass Through-verificatie (PTA)

Een gebruiker meldt zich aan bij hun on-premises omgeving met hun gebruikersaccount (DOMEIN\gebruikersnaam). Wanneer ze naar Microsoft 365 gaan, moeten ze zich opnieuw aanmelden met hun werk-of schoolaccount (user@domain.com). De gebruikersnaam is hetzelfde in beide omgevingen. Wanneer u PHS of PTA toevoegt, heeft de gebruiker hetzelfde wachtwoord voor beide omgevingen, maar deze referenties moeten opnieuw worden opgegeven bij het aanmelden bij Microsoft 365. Adreslijstsynchronisatie met PHS is de meestgebruikte adreslijstsynchronisatie.

Als u adreslijstsynchronisatie wilt instellen, gebruikt u Azure AD Connect. Zie [adreslijstsynchronisatie instellen voor Microsoft 365](set-up-directory-synchronization.md) en [Azure AD Connect met expres instellingen](https://go.microsoft.com/fwlink/p/?LinkId=698537)voor instructies.

Meer informatie over [het voorbereiden van adreslijstsynchronisatie met Microsoft 365](prepare-for-directory-synchronization.md).

### <a name="directory-synchronization-with-sso"></a>Adreslijstsynchronisatie met SSO

Een gebruiker meldt zich aan bij hun on-premises omgeving met hun gebruikersaccount. Wanneer de persoon naar Microsoft 365 gaat, meldt u zich automatisch aan of worden ze aangemeld met de referenties die ze voor hun on-premises omgeving gebruiken.

Voor het instellen van eenmalige aanmelding gebruikt u ook Azure AD Connect. Voor instructies raadpleegt u [aangepaste installatie van Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).

Zie voor meer informatie [eenmalige aanmelding](https://go.microsoft.com/fwlink/p/?LinkId=698604).

## <a name="azure-ad-connect"></a>Azure AD Connect

Azure AD Connect vervangt oudere versies van hulpmiddelen voor identiteits integratie, zoals DirSync en Azure AD-synchronisatie. Als u wilt bijwerken van Azure Active Directory-synchronisatie met Azure AD Connect, raadpleegt u [de upgrade-instructies](https://go.microsoft.com/fwlink/p/?LinkId=733240). 

## <a name="see-also"></a>Zie ook

[Overzicht van Microsoft 365 Enterprise](microsoft-365-overview.md)
