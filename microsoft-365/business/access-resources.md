---
title: On-premises resources openen vanaf een apparaat dat is verbonden met Azure AD in Microsoft 365 Business
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
description: Meer informatie over hoe u toegang krijgt tot on-premises bronnen zoals bedrijfsapps, bestandsshares en printers van een Azure Active Directory dat is toegetreden tot Windows 10-apparaat.
ms.openlocfilehash: c1e04e5ca0d36c32a55a9819140356db5093e3a1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627449"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>On-premises resources openen vanaf een apparaat dat is verbonden met Azure AD in Microsoft 365 Business Premium

Elk Windows 10-apparaat dat Azure Active Directory heeft samengevoegd, heeft toegang tot alle cloudbronnen, zoals uw Microsoft 365-apps, en kan worden beschermd door Microsoft 365 Business Premium. U ook toegang verlenen tot on-premises bronnen zoals LOB-apps (Line of Business), bestandsshares en printers. Als u toegang wilt verlenen, gebruikt u [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) om uw on-premises Active Directory te synchroniseren met Azure Active Directory. 

Zie [Inleiding tot apparaatbeheer in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction)voor meer informatie.
De stappen worden ook samengevat in de volgende secties.

> [!IMPORTANT]
> Deze procedure is alleen van toepassing op OAuth en NTLM. Kerberos wordt niet ondersteund.
 
## <a name="run-azure-ad-connect"></a>Azure AD Connect uitvoeren

Voer de volgende stappen uit om de Azure AD-apparaten van uw organisatie toegang te geven tot on-premises resources.
  
1. Als u uw gebruikers, groepen en contactpersonen uit de lokale Active Directory wilt synchroniseren met Azure Active Directory, voert u de wizard Adressynchronisatie en Azure AD Connect uit zoals beschreven in [Adreslijstsynchronisatie instellen voor Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
2. Nadat de adreslijstsynchronisatie is voltooid, controleert u of de Windows 10-apparaten van uw organisatie zijn aangesloten bij Azure AD. Deze stap wordt individueel gedaan op elk Windows 10-apparaat. Zie [Windows-apparaten instellen voor Microsoft 365 Business Premium-gebruikers](set-up-windows-devices.md) voor meer informatie. 
    
3. Zodra de Windows 10-apparaten zijn aangesloten op Azure AD, moet elke gebruiker zijn apparaten opnieuw opstarten en zich aanmelden met hun Microsoft 365 Business Premium-referenties. Alle apparaten hebben nu ook toegang tot on-premises bronnen.
    
Er zijn geen extra stappen vereist om toegang te krijgen tot on-premises bronnen voor Azure AD-apparaten. Deze functionaliteit is ingebouwd in Windows 10. 

Als u plannen hebt om in te loggen op het AADJ-apparaat, andere dan wachtwoordmethode Zoals PIN / Bio-metric via WHFB-inloggegevens en vervolgens toegang hebt tot on-premise bronnen (shares,printers.. etc), volghttps://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Als uw organisatie nog niet klaar is om te worden geïmplementeerd in de hierboven beschreven Azure AD-apparaatconfiguratie, u overwegen [de configuratie van hybride Azure AD Joined-apparaat](manage-windows-devices.md)in te stellen.
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Overwegingen wanneer u Windows-apparaten aansluit bij Azure AD

Als het Windows-apparaat waarvan u Azure-AD lid van het Bureaublad bent geworden, eerder is verbonden aan het domein of in een werkgroep, moet u rekening houden met de volgende beperkingen:
  
- Wanneer een apparaat azure AD lid wordt, wordt een nieuwe gebruiker gemaakt zonder te verwijzen naar een bestaand profiel. Profielen moeten handmatig worden gemigreerd. Een gebruikersprofiel bevat informatie zoals favorieten, lokale bestanden, browserinstellingen en menu-instellingen voor het starten. Een beste aanpak is het vinden van een tool van derden om bestaande bestanden en instellingen in kaart te brengen naar het nieuwe profiel.

- Als het apparaat Groepsbeleidsobjecten (GPO) gebruikt, hebben sommige GPO's mogelijk geen vergelijkbare [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune. Voer de [MMAT-tool](https://www.microsoft.com/download/details.aspx?id=45520) uit om vergelijkbare CSP's voor bestaande GPO's te vinden.

- Gebruikers kunnen zich niet verifiëren voor toepassingen die afhankelijk zijn van Active Directory-verificatie. Evalueer de verouderde app en overweeg te updaten naar een app die gebruik maakt van moderne Auth, indien mogelijk.

- Detectie van Active Directory-printers werkt niet. U directe printerpaden voor alle gebruikers bieden of [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)gebruiken.
