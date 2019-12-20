---
title: Toegang tot on-premises bronnen van een Azure AD-apparaat in Microsoft 365 Business
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
description: Informatie over hoe u toegang krijgt tot on-premises resources, zoals zakelijke apps, bestandsshares en printers, vanuit een Azure Active Directory dat is gekoppeld aan een Windows 10-apparaat.
ms.openlocfilehash: 89ac38f3da9cbdd3ff1a5eb33dc129d2e83521c7
ms.sourcegitcommit: 8c244b38c43dd00c4ef0102f8bed02ab36639a6b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2019
ms.locfileid: "39967158"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Toegang tot on-premises bronnen van een Azure AD-apparaat in Microsoft 365 Business

Elk Windows 10-apparaat dat is Azure Active Directory toegevoegd heeft toegang tot alle cloud-gebaseerde resources, zoals uw Office 365-apps en kan worden beveiligd door Microsoft 365 Business. U ook toegang verlenen tot on-premises resources, zoals LOB-apps (line of Business), bestandsshares en printers. Als u toegang wilt toestaan, gebruikt u [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) om uw on-premises Active Directory te synchroniseren met Azure Active Directory. 

Zie voor meer informatie, [Inleiding tot Apparaatbeheer in azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
De stappen worden ook samengevat in de volgende secties.

> [!IMPORTANT]
> Deze procedure is alleen van toepassing op OAuth en NTLM. Kerberos wordt niet ondersteund.
 
## <a name="run-azure-ad-connect"></a>Azure AD Connect uitvoeren

Voltooi de volgende stappen om in te schakelen van uw organisatie Azure AD gekoppelde apparaten voor toegang tot on-premises resources.
  
1. Voor het synchroniseren van uw gebruikers, groepen en contactpersonen van lokale Active Directory in azure Active Directory, voert u de wizard Directory-synchronisatie en Azure AD Connect zoals beschreven in [Directory-synchronisatie voor Office 365 instellen](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
2. Nadat de adreslijstsynchronisatie voltooid is, zorg ervoor dat de Windows 10-apparaten van uw organisatie zijn gekoppeld aan Azure AD. Deze stap wordt afzonderlijk uitgevoerd op elk apparaat met Windows 10. Zie [Windows-apparaten instellen voor Microsoft 365 zakelijke gebruikers](set-up-windows-devices.md) voor meer informatie. 
    
3. Zodra de Windows 10-apparaten Azure AD zijn gekoppeld, moet elke gebruiker hun apparaten opnieuw opstarten en meld u aan met hun Microsoft 365 zakelijke referenties. Alle apparaten hebben nu ook toegang tot on-premises bronnen.
    
Er zijn geen extra stappen nodig om toegang te krijgen tot on-premises bronnen voor Azure AD gekoppelde apparaten. Deze functionaliteit is ingebouwd in Windows 10. 

Als u van plan bent om in te loggen op het AADJ-apparaat anders dan de wachtwoord methode zoals PIN/bio-metric via WHFB-inloggegevens en vervolgens toegang tot on-premise bronnen (shares, printers.. etc), volg danhttps://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Als uw organisatie niet gereed is voor implementatie in de Azure AD gekoppelde apparaatconfiguratie die hierboven wordt beschreven, u overwegen [hybride Azure AD gekoppelde apparaatconfiguratie](manage-windows-devices.md)in te stellen.
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Overwegingen bij het toevoegen van Windows-apparaten aan Azure AD

Houd rekening met de volgende beperkingen als het Windows-apparaat waaraan u Azure-AD is toegevoegd, eerder lid was van een domein of in een werkgroep:
  
- Wanneer een apparaat Azure AD wordt toegevoegd, wordt een nieuwe gebruiker gemaakt zonder te verwijzen naar een bestaand profiel. Profielen moeten handmatig worden gemigreerd. Een gebruikersprofiel bevat informatie zoals Favorieten, lokale bestanden, browserinstellingen en instellingen van het menu Start. De beste manier is om een hulpprogramma van derden te vinden voor het toewijzen van bestaande bestanden en instellingen aan het nieuwe profiel.

- Als het apparaat gebruikmaakt van groepsbeleidsobjecten (GPO), hebben sommige groepsbeleidobjecten mogelijk geen vergelijkbare [configuratie service provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in intune. Voer het [hulpprogramma Mmat](https://www.microsoft.com/download/details.aspx?id=45520) uit om vergelijkbare csp's voor bestaande groepsbeleidobjecten te vinden.

- Gebruikers kunnen niet worden geverifieerd bij toepassingen die afhankelijk van Active Directory-verificatie zijn. Evalueer de oude app en overweeg een update naar een app die gebruikmaakt van moderne auth, indien mogelijk.

- Detectie van Active Directory-printer werkt niet. U directe printer paden bieden voor alle gebruikers of [hybride Cloud print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)gebruiken.
