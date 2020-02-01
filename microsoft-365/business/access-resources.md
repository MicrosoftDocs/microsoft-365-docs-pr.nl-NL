---
title: On-premises bronnen openen vanaf een Azure AD-verbonden apparaat in Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Meer informatie over het krijgen van toegang tot on-premises bronnen, zoals bedrijfsapps, bestandsshares en printers vanaf een Azure Active Directory-apparaat.
ms.openlocfilehash: 653b53d29e84bbdc91273cb78b9b8407c0f6a209
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593228"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>On-premises bronnen openen vanaf een Azure AD-verbonden apparaat in Microsoft 365 Business

Elk Windows 10-apparaat met Azure Active Directory is aangesloten, heeft toegang tot alle cloudbronnen, zoals uw Office 365-apps, en kan worden beschermd door Microsoft 365 Business. U ook toegang verlenen tot on-premises resources zoals LOB-apps, bestandsshares en printers van bedrijfsactiviteiten. Gebruik [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) om uw on-premises Active Directory te synchroniseren met Azure Active Directory om toegang toe te staan. 

Zie [Inleiding tot apparaatbeheer in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction)voor meer informatie.
De stappen worden ook samengevat in de volgende secties.

> [!IMPORTANT]
> Deze procedure is alleen van toepassing op OAuth en NTLM. Kerberos wordt niet ondersteund.
 
## <a name="run-azure-ad-connect"></a>Azure AD Connect uitvoeren

Voer de volgende stappen uit om de Azure AD-verbonden apparaten van uw organisatie toegang te geven tot on-premises bronnen.
  
1. Voer de wizard Adreslijstsynchronisatie en Azure AD Connect uit zoals beschreven in [Adreslijstsynchronisatie voor Office 365,](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)als u uw gebruikers, groepen en contactpersonen van lokale Active Directory wilt synchroniseren in Azure Active Directory.
    
2. Nadat de adreslijstsynchronisatie is voltooid, moet u ervoor zorgen dat de Windows 10-apparaten van uw organisatie Azure AD zijn aangesloten. Deze stap wordt afzonderlijk gedaan op elk Windows 10-apparaat. Zie [Windows-apparaten instellen voor Microsoft 365 Business-gebruikers](set-up-windows-devices.md) voor meer informatie. 
    
3. Zodra de Windows 10-apparaten zijn samengevoegd met Azure AD, moet elke gebruiker zijn apparaten opnieuw opstarten en zich aanmelden met zijn Microsoft 365 Business-referenties. Alle apparaten hebben nu ook toegang tot on-premises bronnen.
    
Er zijn geen extra stappen nodig om toegang te krijgen tot on-premises bronnen voor azure AD-verbonden apparaten. Deze functionaliteit is ingebouwd in Windows 10. 

Als u plannen hebt om in te loggen op het AADJ-apparaat, andere dan wachtwoordmethode Zoals PIN / Bio-metric via WHFB referentie login en vervolgens toegang on-premise bronnen (aandelen, printers.. etc), volghttps://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Als uw organisatie nog niet klaar is om te implementeren in de hierboven beschreven Azure AD-apparaatconfiguratie, u overwegen de configuratie van [hybride Azure AD-verbonden apparaat](manage-windows-devices.md)in te stellen.
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Overwegingen wanneer u lid wordt van Windows-apparaten op Azure AD

Houd rekening met de volgende beperkingen als het Windows-apparaat waarvan u lid is geworden van Azure-AD eerder is verbonden met domeinof in een werkgroep:
  
- Wanneer een apparaat Azure AD wordt lid, maakt het een nieuwe gebruiker zonder te verwijzen naar een bestaand profiel. Profielen moeten handmatig worden gemigreerd. Een gebruikersprofiel bevat informatie zoals favorieten, lokale bestanden, browserinstellingen en menu-instellingen starten. Een beste aanpak is het vinden van een tool van derden om bestaande bestanden en instellingen in kaart te brengen naar het nieuwe profiel.

- Als het apparaat groepsbeleidsobjecten (GPO) gebruikt, hebben sommige GPO's mogelijk geen vergelijkbare [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune. Voer de [MMAT-tool](https://www.microsoft.com/download/details.aspx?id=45520) uit om vergelijkbare CSP's te vinden voor bestaande GPO's.

- Gebruikers kunnen zich niet verifiëren voor toepassingen die afhankelijk zijn van Active Directory-verificatie. Evalueer de verouderde app en overweeg om zo mogelijk te updaten naar een app die gebruik maakt van het moderne Auth.

- Active Directory-printerdetectie werkt niet. U directe printerpaden voor alle gebruikers bieden of [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)gebruiken.
