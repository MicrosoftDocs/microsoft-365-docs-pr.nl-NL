---
title: Microsoft 365-integratie met on-premises omgevingen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/08/2019
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
ms.openlocfilehash: 46f0fab6396dd1db82524ea1aeedc6894ce7ab70
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689512"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a>Microsoft 365-integratie met on-premises omgevingen

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

U kunt Microsoft 365 integreren met uw bestaande adreslijstservices en met een lokale installatie van Exchange Server, Skype voor bedrijven server 2015 of SharePoint Server.
  
 - Als u integratie met adreslijstservices, kunt u gebruikersaccounts synchroniseren en beheren voor beide omgevingen. U kunt ook hash-synchronisatie voor wachtwoord of eenmalige aanmelding (SSO) toevoegen, zodat gebruikers zich kunnen aanmelden bij beide omgevingen met hun on-premises referenties.
 - Als u integratie met lokale server producten uitvoert, maakt u een hybride omgeving. Een hybride omgeving kan u helpen bij het migreren van gebruikers of gegevens naar Microsoft 365, of u kunt in de Cloud bepaalde gebruikers of bepaalde informatie on-premises blijven hebben. Zie voor meer informatie over hybride omgevingen [hybride Cloud Overview](https://docs.microsoft.com/Office365/Enterprise/hybrid-cloud-overview).

U kunt ook de Azure Active Directory (Azure AD) adviseurs gebruiken voor aangepaste instel richtlijnen (u moet zijn aangemeld bij Microsoft 365):

- [Gebruikers synchroniseren vanuit de adreslijst van uw organisatie](https://aka.ms/aadconnectpwsync)
- [AD FS-implementatie adviseur](https://aka.ms/adfsguidance)
- [Installatiehandleiding voor Azure AD](https://aka.ms/aadpguidance)
   
## <a name="before-you-begin"></a>Voordat u begint

Voordat u Microsoft 365 en een lokale omgeving integreert, moet u ook een [netwerk planning en prestaties afstemmen](network-planning-and-performance.md). U kunt ook inzicht krijgen in de beschikbare [identiteits modellen](about-microsoft-365-identity.md). 

Zie [waar kunt u Microsoft 365-accounts beheren](manage-microsoft-365-accounts.md) voor een lijst met hulpmiddelen die u kunt gebruiken voor het beheren van gebruikers en accounts van microsoft 365. 
  
## <a name="integrate-microsoft-365-with-directory-services"></a>Microsoft 365 integreren met adreslijstservices
Als u bestaande gebruikersaccounts hebt in een on-premises adreslijst, kunt u niet al deze accounts opnieuw maken in Microsoft 365 en risico, waarbij de verschillen of fouten tussen de omgevingen worden geïntroduceerd. Met adreslijstsynchronisatie kunt u de accounts van uw online en on-premises omgevingen spiegelen. Met adreslijstsynchronisatie hoeven gebruikers geen nieuwe informatie voor elke omgeving te onthouden en hoeft u niet twee keer accounts te maken of bij te werken. U moet [uw on-premises adreslijst voorbereiden](prepare-for-directory-synchronization.md) op adreslijstsynchronisatie.
  
![Adreslijstsynchronisatie gebruiken om on-premises en online gegevens van gebruikersaccounts gesynchroniseerd te houden](../media/a64af0d0-9be6-46b1-8727-277e683abf5e.png)
  
Als u wilt dat gebruikers zich kunnen aanmelden bij Microsoft 365 met hun on-premises referenties, kunt u ook eenmalige aanmelding configureren. Met eenmalige aanmelding is Microsoft 365 geconfigureerd voor het vertrouwen van de on-premises omgeving voor gebruikersauthenticatie.
  
![Met eenmalige aanmelding is hetzelfde account beschikbaar in de on-premises omgeving en de online omgeving](../media/d76235f2-8a53-405e-b8ef-dfa4cfc208b8.png)
  
Verschillende technieken voor Gebruikersaccountbeheer maken een afwijkende ervaring voor uw gebruikers, zoals wordt weergegeven in de volgende tabel.
 
### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication"></a>Adreslijstsynchronisatie met of zonder wachtwoord-hash synchronisatie of Pass Through-verificatie

Een gebruiker meldt zich aan bij hun on-premises omgeving met hun gebruikersaccount (DOMEIN\gebruikersnaam). Wanneer ze naar Microsoft 365 gaan, moeten ze zich opnieuw aanmelden met hun werk-of schoolaccount (user@domain.com). De gebruikersnaam is hetzelfde in beide omgevingen. Wanneer u een hash-synchronisatie via een wachtwoord toevoegt of een Pass-Through-verificatie toevoegt, heeft de gebruiker hetzelfde wachtwoord voor beide omgevingen, maar deze referenties moeten opnieuw worden opgegeven bij het aanmelden bij Microsoft 365. Adreslijstsynchronisatie met wachtwoord hash is het meestgebruikte scenario voor Directory synchronisatie.

Als u adreslijstsynchronisatie wilt instellen, maakt u gebruik van Azure Active Directory Connect. Zie [adreslijstsynchronisatie instellen voor Microsoft 365](set-up-directory-synchronization.md)en [Azure AD Connect met expres instellingen](https://go.microsoft.com/fwlink/p/?LinkId=698537)voor instructies.

Meer informatie over het [voorbereiden van adreslijstsynchronisatie met Microsoft 365](prepare-for-directory-synchronization.md) en [het integreren van uw on-premises identificaties met Azure Active Directory](https://go.microsoft.com/fwlink/?LinkId=518101).

### <a name="directory-synchronization-with-sso"></a>Adreslijstsynchronisatie met SSO

Een gebruiker meldt zich aan bij hun on-premises omgeving met hun gebruikersaccount. Wanneer de persoon naar Microsoft 365 gaat, meldt u zich automatisch aan of worden ze aangemeld met de referenties die ze voor hun on-premises omgeving gebruiken.

Voor het instellen van eenmalige aanmelding gebruikt u ook Azure AD Connect. Voor instructies raadpleegt u [aangepaste installatie van Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).

Meer informatie over [eenmalige aanmelding bij toepassingen in azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=698604).

## <a name="azure-ad-connect"></a>Azure AD Connect

Azure AD Connect vervangt oudere versies van hulpmiddelen voor identiteits integratie, zoals DirSync en Azure AD-synchronisatie. Zie [Wat is hybride identiteit met Azure Active Directory?](https://go.microsoft.com/fwlink/p/?LinkId=527969)voor meer informatie. Als u wilt bijwerken van Azure Active Directory-synchronisatie met Azure AD Connect, raadpleegt u [de upgrade-instructies](https://go.microsoft.com/fwlink/p/?LinkId=733240). 

Zie ook [Microsoft 365 Directory-synchronisatie implementeren in Microsoft Azure](https://go.microsoft.com/fwlink/?LinkId=517887).

## <a name="see-also"></a>Zie ook

[Overzicht van Microsoft 365 Enterprise](microsoft-365-overview.md)
