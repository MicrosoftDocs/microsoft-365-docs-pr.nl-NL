---
title: On-premises bronnen openen vanaf een apparaat dat lid is van Azure AD in Microsoft 365 Business
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
description: Lees hoe u toegang krijgt tot on-premises bronnen, zoals line-of-business-apps, bestands shares en printers vanaf een Windows 10-apparaat dat is aangesloten op Azure Active Directory.
ms.openlocfilehash: fc02fd30f41f25f52e653e750a6bdfd1bd7f800e
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233835"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>On-premises bronnen openen vanaf een azure AD-apparaat in Microsoft 365 Business Premium

Dit artikel is van toepassing op Microsoft 365 Business Premium.

Elk Windows 10-apparaat dat is aangesloten op Azure Active Directory, heeft toegang tot alle cloudresources, zoals uw Microsoft 365-apps, en kan worden beveiligd door Microsoft 365 Business Premium. U kunt ook toegang verlenen tot on-premises resources, zoals LOB-apps (Line Of Business), bestands shares en printers. Gebruik Azure [AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) om uw on-premises Active Directory te synchroniseren met Azure Active Directory om toegang toe te staan. 

Zie Inleiding tot apparaatbeheer [in Azure Active Directory voor meer informatie.](https://docs.microsoft.com/azure/active-directory/device-management-introduction)
De stappen worden ook samengevat in de volgende secties.
 
## <a name="run-azure-ad-connect"></a>Azure AD Connect uitvoeren

Volg de volgende stappen om de apparaten die lid zijn van Azure AD van uw organisatie toegang te geven tot on-premises bronnen.
  
1. Als u uw gebruikers, groepen en contactpersonen vanuit de lokale Active Directory wilt synchroniseren met Azure Active Directory, moet u de wizard Adreslijstsynchronisatie en Azure AD Connect uitvoeren, zoals is beschreven in Adreslijstsynchronisatie voor [Office 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)instellen.
    
2. Nadat de adreslijstsynchronisatie is voltooid, zorgt u ervoor dat de Windows 10-apparaten van uw organisatie zijn samengevoegd met Azure AD. Deze stap wordt afzonderlijk uitgevoerd op elk Windows 10-apparaat. Zie [Windows-apparaten instellen voor gebruikers van Microsoft 365 Business Premium](set-up-windows-devices.md) voor meer informatie. 
    
3. Wanneer de Windows 10-apparaten zijn samengevoegd met Azure AD, moet elke gebruiker zijn of haar apparaten opnieuw opstarten en zich aanmelden met de Microsoft 365 Business Premium-referenties. Alle apparaten hebben nu ook toegang tot on-premises bronnen.
    
Er zijn geen extra stappen nodig om toegang te krijgen tot on-premises bronnen voor apparaten die lid zijn van Azure AD. Deze functionaliteit is ingebouwd in Windows 10. 

Als u zich wilt aanmelden bij het AADJ-apparaat met een andere wachtwoordmethode dan bijvoorbeeld pincode/bio-meetwaarde via aanmelding bij WHFB-referenties en vervolgens toegang wilt krijgen tot lokale bronnen (shares,printers.). enzovoort) volgt u https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Als uw organisatie nog niet gereed is om te implementeren in de apparaatconfiguratie die is lid van Azure AD, zoals hierboven is beschreven, kunt u overwegen om een hybride configuratie van een [Azure AD-apparaat](manage-windows-devices.md)in te stellen.
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Overwegingen bij het deelnemen van Windows-apparaten aan Azure AD

Als het Windows-apparaat waar u azure-AD eerder lid van was, lid was van een domein of een werkgroep, moet u rekening houden met de volgende beperkingen:
  
- Wanneer een apparaat wordt lid van Azure AD, wordt er een nieuwe gebruiker gemaakt zonder dat wordt verwezen naar een bestaand profiel. Profielen moeten handmatig worden gemigreerd. Een gebruikersprofiel bevat informatie zoals favorieten, lokale bestanden, browserinstellingen en instellingen van het Startmenu. U kunt het beste een hulpprogramma van derden zoeken om bestaande bestanden en instellingen toe te passen op het nieuwe profiel.

- Als het apparaat groepsbeleidsobjecten gebruikt, hebben sommige GPOs mogelijk niet een vergelijkbaar [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune. Voer het [hulpprogramma MMAT uit om](https://www.microsoft.com/download/details.aspx?id=45520) vergelijkbare CSP's te zoeken voor bestaande GPOs's.

- Gebruikers kunnen zich mogelijk niet verifiëren bij toepassingen die afhankelijk zijn van Active Directory-verificatie. Evalueer de oudere app en overweeg indien mogelijk een update uit te brengen naar een app die gebruikmaakt van de moderne auth.

- Active Directory Printer Discovery werkt niet. U kunt directe printerpaden bieden voor alle gebruikers of universeel [afdrukken gebruiken.](https://aka.ms/UPDocs)
