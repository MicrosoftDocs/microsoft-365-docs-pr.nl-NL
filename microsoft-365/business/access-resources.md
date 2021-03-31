---
title: On-premises resources openen vanaf een azure AD-apparaat in Microsoft 365 Business
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
description: Lees hoe u toegang krijgt tot on-premises resources, zoals zakelijke apps, bestandsaandelen en printers vanaf een Azure Active Directory-apparaat dat is aangesloten bij Windows 10.
ms.openlocfilehash: 1bca0beb3ccc78e670ad33ce446b9b3f7c372ba7
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445343"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>On-premises resources openen vanaf een azure AD-apparaat in Microsoft 365 Business Premium

Dit artikel is van toepassing op Microsoft 365 Business Premium.

Elk Windows 10-apparaat dat is verbonden met Azure Active Directory, heeft toegang tot alle cloudbronnen, zoals uw Microsoft 365-apps, en kan worden beschermd door Microsoft 365 Business Premium. U kunt ook toegang verlenen tot on-premises resources, zoals LOB-apps (Line of Business), bestandsaandelen en printers. Als u toegang wilt toestaan, gebruikt [u Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) om uw on-premises Active Directory te synchroniseren met Azure Active Directory. 

Zie Inleiding tot [apparaatbeheer in Azure Active Directory](/azure/active-directory/device-management-introduction)voor meer informatie.
De stappen worden ook samengevat in de volgende secties.
 
## <a name="run-azure-ad-connect"></a>Azure AD Connect uitvoeren

Volg de volgende stappen om de aan Azure AD-apparaten van uw organisatie verbonden apparaten toegang te geven tot on-premises resources.
  
1. Als u uw gebruikers, groepen en contactpersonen van lokale Active Directory wilt synchroniseren met Azure Active Directory, kunt u de wizard Adreslijstsynchronisatie en Azure AD Connect uitvoeren, zoals beschreven in Adreslijstsynchronisatie instellen voor [Office 365.](../enterprise/set-up-directory-synchronization.md)
    
2. Nadat de adreslijstsynchronisatie is voltooid, moet u ervoor zorgen dat de Windows 10-apparaten van uw organisatie zijn verbonden met Azure AD. Deze stap wordt afzonderlijk uitgevoerd op elk Windows 10-apparaat. Zie [Windows-apparaten instellen voor Gebruikers van Microsoft 365 Business Premium](set-up-windows-devices.md) voor meer informatie. 
    
3. Wanneer de Windows 10-apparaten zijn samengevoegd met Azure AD, moet elke gebruiker zijn of haar apparaten opnieuw opstarten en zich aanmelden met de referenties van Microsoft 365 Business Premium. Alle apparaten hebben nu ook toegang tot on-premises resources.
    
Er zijn geen extra stappen vereist om toegang te krijgen tot on-premises resources voor aan Azure AD verbonden apparaten. Deze functionaliteit is ingebouwd in Windows 10. 

Als u plannen hebt om u aan te melden bij het AADJ-apparaat anders dan wachtwoordmethode Like PIN/Bio-metrische via WHFB credential login en vervolgens toegang te krijgen tot on-premises resources (shares,printers.). etc), volgt u https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Als uw organisatie nog niet klaar is om te implementeren in de configuratie van azure AD-apparaten die hierboven zijn samengevoegd, kunt u de configuratie van hybride [Azure AD-apparaten instellen.](manage-windows-devices.md)
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Aandachtspunten bij het deelnemen van Windows-apparaten aan Azure AD

Als het Windows-apparaat waar u Azure-AD deel van hebt gemaakt eerder is verbonden aan een domein of in een werkgroep, moet u rekening houden met de volgende beperkingen:
  
- Wanneer een apparaat azure AD wordt joins, wordt er een nieuwe gebruiker gemaakt zonder te verwijzen naar een bestaand profiel. Profielen moeten handmatig worden gemigreerd. Een gebruikersprofiel bevat informatie zoals favorieten, lokale bestanden, browserinstellingen en Menu-instellingen starten. U kunt het beste een hulpprogramma van derden vinden om bestaande bestanden en instellingen toe te passen op het nieuwe profiel.

- Als het apparaat groepsbeleidsobjecten (GPO) gebruikt, hebben sommige GPOs mogelijk geen vergelijkbare [Configuratieserviceprovider](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune. Voer het [hulpprogramma MMAT uit om](https://www.microsoft.com/download/details.aspx?id=45520) vergelijkbare CSP's voor bestaande GPOs te zoeken.

- Gebruikers kunnen zich mogelijk niet verifiëren voor toepassingen die afhankelijk zijn van Active Directory-verificatie. Evalueer de oudere app en overweeg indien mogelijk bij te werken naar een app die gebruikmaakt van het moderne Auth.

- Active Directory-printerdetectie werkt niet. U kunt directe printerpaden voor alle gebruikers bieden of Universeel [afdrukken gebruiken.](/universal-print/)

### <a name="related-articles"></a>Verwante artikelen

[Vereisten voor Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)
