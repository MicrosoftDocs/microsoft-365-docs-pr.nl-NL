---
title: On-premises resources openen vanuit een Azure AD-apparaat in Microsoft 365 Business
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
description: Meer informatie over hoe u toegang krijgt tot on-premises bronnen, zoals line-of-Business-Apps, bestandsshares en printers van een Azure Active Directory-apparaat met Windows 10.
ms.openlocfilehash: 2144268f5cbab67c39d5902622c61c0c35e6481c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295305"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>On-premises resources openen vanuit een Azure AD-domein dat is gekoppeld aan Microsoft 365 Business Premium

Dit artikel is van toepassing op Microsoft 365 Business Premium.

Een Windows 10-apparaat dat Azure Active Directory is aangemeld, heeft toegang tot alle bronnen op basis van de Cloud, zoals uw Microsoft 365-apps, en kan worden beveiligd door Microsoft 365 Business Premium. U kunt ook toegang verlenen tot on-premises bronnen, zoals LOB-apps (line of Business), bestandsshares en printers. Als u toegang wilt toestaan, gebruikt u [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) om uw on-premises Active Directory te synchroniseren met Azure Active Directory. 

Zie [Inleiding tot Apparaatbeheer in azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction)voor meer informatie.
De stappen worden ook samengevat in de volgende secties.
 
## <a name="run-azure-ad-connect"></a>Azure AD Connect uitvoeren

Voer de volgende stappen uit om in te stellen dat de Azure Active Directory-apparaten van uw organisatie toegang hebben tot on-premises resources.
  
1. Als u uw gebruikers, groepen en contactpersonen wilt synchroniseren van lokale Active Directory naar Azure Active Directory, voert u de wizard adreslijstsynchronisatie en Azure AD Connect uit, zoals wordt beschreven in [adreslijstsynchronisatie instellen voor Office 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization).
    
2. Wanneer de adreslijstsynchronisatie is voltooid, controleert u of de Windows 10-apparaten van uw organisatie aan Azure AD zijn toegevoegd. Deze stap gaat afzonderlijk op elk Windows 10-apparaat. Zie [Windows-apparaten instellen voor gebruikers van Microsoft 365 Business Premium](set-up-windows-devices.md) voor meer informatie. 
    
3. Wanneer de Windows 10-apparaten Azure AD zijn toegevoegd, moet elke gebruiker zijn of haar apparaten opnieuw opstarten en zich aanmelden met de referenties van Microsoft 365 Business Premium. Alle apparaten hebben nu ook toegang tot on-premises resources.
    
Er zijn geen extra stappen nodig om toegang te krijgen tot on-premises bronnen voor gekoppelde apparaten in azure AD. Deze functionaliteit is ingebouwd in Windows 10. 

Als u een abonnement hebt om u aan te melden bij het AADJ-apparaat, zoals pincode/bio-metric via WHFB Credential login en vervolgens toegang tot on-premises resources (shares, printers. etc), kunt u het volgende doen https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Als uw organisatie niet klaar is om te implementeren in de hierboven beschreven configuratie van Azure AD, kunt u overwegen om de configuratie van de [hybride Azure AD-apparaat](manage-windows-devices.md)in te stellen.
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Aandachtspunten wanneer u deelneemt aan Windows-apparaten aan Azure AD

Als het Windows-apparaat waarvan u Azure-AD lid bent geworden, eerder domein of een werkgroep is, kunt u de volgende beperkingen overwegen:
  
- Wanneer een apparaat van Azure AD wordt samengevoegd, wordt er een nieuwe gebruiker gemaakt zonder op een bestaand profiel te verwijzen. Profielen moeten handmatig worden gemigreerd. Een gebruikersprofiel bevat informatie, zoals Favorieten, lokale bestanden, browserinstellingen en menu Start-menu instellingen. Een beste manier is om een hulpmiddel van een derde partij te zoeken waarmee u bestaande bestanden en instellingen kunt toewijzen aan het nieuwe profiel.

- Als het apparaat gebruikmaakt van groepsbeleidsobjecten (groepsbeleidsobjecten), hebben sommige Gpo's mogelijk geen vergelijkbaar [Configuration service provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in intune. Voer het [hulpprogramma MMAT](https://www.microsoft.com/download/details.aspx?id=45520) uit om vergelijkbare csp's voor bestaande gpo's te zoeken.

- Gebruikers kunnen zich niet verifiëren met toepassingen die afhankelijk zijn van Active Directory-verificatie. Evalueer de oudere app en overweeg, indien mogelijk, bij te werken naar een app die gebruikmaakt van moderne auth.

- Active Directory-Printer detectie werkt niet. U kunt voor alle gebruikers direct printer paden maken of [hybride Cloud afdrukken](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)gebruiken.
