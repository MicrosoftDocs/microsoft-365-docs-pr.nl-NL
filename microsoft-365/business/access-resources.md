---
title: On-premises bronnen openen vanaf een azure ad-apparaat in Microsoft 365 Business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Meer informatie over het openen van on-premises bronnen, zoals branche-apps, bestandsshares en printers vanaf een azure Active Directory-apparaat dat is aangesloten bij Windows 10.
ms.openlocfilehash: 9615ecc9469992d3e5a7479f4799c610db11fb41
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471246"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>On-premises bronnen openen vanaf een azure ad-apparaat in Microsoft 365 Business Premium

Dit artikel is van toepassing op Microsoft 365 Business Premium.

Elk Windows 10-apparaat dat azure Active Directory is aangesloten, heeft toegang tot alle cloudbronnen, zoals uw Microsoft 365-apps, en kan worden beschermd door Microsoft 365 Business Premium. U ook toegang verlenen tot on-premises bronnen, zoals LOB-apps, bestandsshares en printers. Als u toegang wilt toestaan, gebruikt [u Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) om uw on-premises Active Directory te synchroniseren met Azure Active Directory. 

Zie [Inleiding tot apparaatbeheer in Azure Active Directory voor](https://docs.microsoft.com/azure/active-directory/device-management-introduction)meer informatie.
De stappen worden ook samengevat in de volgende secties.

> [!IMPORTANT]
> Deze procedure is alleen van toepassing op OAuth en NTLM. Kerberos wordt niet ondersteund.
 
## <a name="run-azure-ad-connect"></a>Azure AD Connect uitvoeren

Voer de volgende stappen uit om de azure ad-apparaten van uw organisatie toegang te geven tot on-premises bronnen.
  
1. Als u uw gebruikers, groepen en contactpersonen van lokale Active Directory wilt synchroniseren met Azure Active Directory, voert u de wizard Mapsynchronisatie en Azure AD Connect uit zoals beschreven in [Mapsynchronisatie instellen voor Office 365.](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)
    
2. Nadat de mapsynchronisatie is voltooid, controleert u of de Windows 10-apparaten van uw organisatie Azure AD zijn aangesloten. Deze stap wordt individueel uitgevoerd op elk Windows 10-apparaat. Zie [Windows-apparaten instellen voor Microsoft 365 Business Premium-gebruikers](set-up-windows-devices.md) voor meer informatie. 
    
3. Zodra de Windows 10-apparaten azure ad zijn aangesloten, moet elke gebruiker zijn apparaten opnieuw opstarten en zich aanmelden met zijn Microsoft 365 Business Premium-referenties. Alle apparaten hebben nu ook toegang tot on-premises bronnen.
    
Er zijn geen extra stappen vereist om toegang te krijgen tot on-premises bronnen voor azure AD-apparaten. Deze functionaliteit is ingebouwd in Windows 10. 

Als u van plan bent om in te loggen op het AADJ-apparaat, met uitzondering van wachtwoordmethode Zoals pin/bio-metric via het inloggen op whfb-referentiegegevens en vervolgens toegang te krijgen tot on-premise bronnen (shares,printers.. etc), volg danhttps://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Als uw organisatie niet klaar is om te implementeren in de hierboven beschreven azure AD joined-apparaatconfiguratie, u overwegen de configuratie van [hybride Azure AD Joined in](manage-windows-devices.md)te stellen.
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Overwegingen wanneer u Windows-apparaten aansluit bij Azure AD

Als het Windows-apparaat waarmee Azure-AD is lid geworden, eerder is aangesloten bij het domein of in een werkgroep, moet u de volgende beperkingen overwegen:
  
- Wanneer een apparaat azure AD wordt samengevoegd, maakt het een nieuwe gebruiker zonder te verwijzen naar een bestaand profiel. Profielen moeten handmatig worden gemigreerd. Een gebruikersprofiel bevat informatie zoals favorieten, lokale bestanden, browserinstellingen en menu-instellingen starten. Een beste aanpak is het vinden van een tool van derden om bestaande bestanden en instellingen in kaart te brengen aan het nieuwe profiel.

- Als het apparaat Groepsbeleidsobjecten (GPO' s) gebruikt, hebben sommige GPO's mogelijk geen vergelijkbare [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune. Voer de [MMAT-tool](https://www.microsoft.com/download/details.aspx?id=45520) uit om vergelijkbare CSP's voor bestaande GPO's te vinden.

- Gebruikers kunnen zich niet verifiëren voor toepassingen die afhankelijk zijn van Active Directory-verificatie. Evalueer de verouderde app en overweeg om te updaten naar een app die gebruik maakt van de moderne Auth, indien mogelijk.

- Active Directory-printerdetectie werkt niet. U directe printerpaden bieden voor alle gebruikers of [Hybride cloudprint](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)gebruiken.
