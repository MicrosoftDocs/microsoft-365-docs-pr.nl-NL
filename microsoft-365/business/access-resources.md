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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Informatie over hoe u toegang krijgt tot on-premises resources, zoals zakelijke apps, bestandsshares en printers, vanuit een Azure Active Directory dat is gekoppeld aan een Windows 10-apparaat.
ms.openlocfilehash: 26ba0ffb64ddce32369002120657456e47ac0c7f
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287350"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Toegang tot on-premises bronnen van een Azure AD-apparaat in Microsoft 365 Business

Elk Windows 10-apparaat dat is gekoppeld aan Azure Active Directory, heeft toegang tot alle cloudgebaseerde bronnen, zoals uw Office 365-apps en kan worden beveiligd door Microsoft 365 Business. Om ook toegang tot on-premises resources zoals LOB-apps (line of Business), bestandsshares en printers toe te staan, moet u uw on-premises Active Directory synchroniseren met Azure Active Directory met behulp van [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). 

Zie [Inleiding tot Apparaatbeheer in azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) voor meer informatie.
De stappen worden ook samengevat in de volgende secties.

## <a name="run-azure-ad-connect"></a>Azure AD Connect uitvoeren

Voltooi de volgende stappen om in te schakelen van uw organisatie Azure AD gekoppelde apparaten voor toegang tot on-premises resources.
  
1. Voor het synchroniseren van uw gebruikers, groepen en contactpersonen van lokale Active Directory in azure Active Directory, voert u de wizard Directory-synchronisatie en Azure AD Connect zoals beschreven in [Directory-synchronisatie voor Office 365 instellen](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
2. Nadat de adreslijstsynchronisatie is voltooid, zorg ervoor dat de Windows 10-apparaten van uw organisatie zijn gekoppeld aan Azure AD. Deze stap wordt afzonderlijk uitgevoerd op elk apparaat met Windows 10. Zie [Windows-apparaten instellen voor Microsoft 365 zakelijke gebruikers](set-up-windows-devices.md) voor meer informatie. 
    
3. Zodra de Windows 10-apparaten zijn gekoppeld aan Azure AD, moet elke gebruiker hun apparaten opnieuw opstarten en aanmelden met hun Microsoft 365 zakelijke referenties. Alle apparaten hebben nu ook toegang tot on-premises resources.
    
Er zijn geen extra stappen nodig om toegang te krijgen tot on-premises bronnen voor Azure AD gekoppelde apparaten. Dit is ingebouwde functionaliteit beschikbaar in Windows 10. 
  
Als uw organisatie is niet gereed voor implementatie in de Azure AD gekoppelde apparaatconfiguratie hierboven beschreven, overweeg het instellen van [hybride Azure AD gekoppelde apparaatconfiguratie](manage-windows-devices.md).
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a>Overwegingen bij het verbinden van uw Windows-apparaten met Azure AD

Als u Azure AD lid worden van een Windows-apparaat dat eerder lid van een domein of in een werkgroep is, moet u rekening houden met de volgende beperkingen:
  
- Wanneer een apparaat Azure AD wordt toegevoegd, wordt een nieuwe gebruiker gemaakt zonder te verwijzen naar een bestaand profiel. Om dit op te lossen, moeten profielen handmatig worden gemigreerd. Een gebruikersprofiel bevat informatie zoals Favorieten, lokale bestanden, browserinstellingen, instellingen in het menu Start, enz. De beste manier is om een hulpprogramma van derden te vinden voor het toewijzen van bestaande bestanden en instellingen aan het nieuwe profiel

- Als het apparaat gebruikmaakt van groepsbeleidsobjecten (GPO), hebben sommige groepsbeleidobjecten mogelijk geen vergelijkbare [configuratie service provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in intune. Voer het [hulpprogramma Mmat](https://www.microsoft.com/download/details.aspx?id=45520) uit om vergelijkbare csp's voor bestaande groepsbeleidobjecten te vinden.

- Gebruikers kunnen niet worden geverifieerd bij toepassingen die afhankelijk van Active Directory-verificatie zijn. Om te gaan met deze evaluatie met behulp van een verouderde app en overweeg het bijwerken naar een app die gebruikmaakt van moderne auth indien mogelijk.

- Detectie van Active Directory-printers werkt niet. U dit oplossen door directe printer paden voor alle gebruikers te bieden of gebruik te maken van [Hybrid Cloud print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
