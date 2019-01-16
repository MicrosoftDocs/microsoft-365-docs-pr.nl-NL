---
title: Toegang op-premises resources uit een Azure AD verbonden apparaat in Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Informatie over het verkrijgen van toegang tot bronnen voor bedrijfsruimten zoals Line Of Business apps, bestandsshares en printers uit een Azure Active Directory Windows 10-apparaat gekoppeld.
ms.openlocfilehash: 0a5d4b0828888fcb99676223000c446479f84ddc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "26982252"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Toegang op-premises resources uit een Azure AD verbonden apparaat in Microsoft 365 Business

Elk Windows 10-apparaat dat is Azure Active Directory toegevoegd toegang hebben tot alle cloud-gebaseerde bronnen zoals uw apps Office 365 en kan worden beveiligd door Microsoft 365 Business. Als u ook toegang tot bronnen voor bedrijfsruimten zoals apps, bestandsshares en printers lijn van Business (LOB), moet u Active Directory op ruimten synchroniseren met Azure Active Directory met [Azure AD verbinding](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). Zie [Inleiding tot device management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) voor meer informatie. 
  
## <a name="run-azure-ad-connect"></a>Verbinding Azure AD uitvoeren

Voer de volgende stappen voor het inschakelen van uw organisatie Azure AD verbonden apparaten toegang krijgen tot bronnen op gebouwen.
  
1. Als u uw gebruikers, groepen en contactpersonen uit de lokale Active Directory naar Azure Active Directory, de Directory synchronisatie-wizard uitvoeren en Azure AD verbinden als beschreven in de [directory-synchronisatie voor Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
2. Nadat de adreslijstsynchronisatie is voltooid, moet u ervoor zorgen van uw organisatie Windows 10-apparaten zijn Azure advertentie toegevoegd. Deze stap gebeurt afzonderlijk op elk apparaat met Windows 10. Zie [Windows-apparaten voor Microsoft 365 zakelijke gebruikers instellen](set-up-windows-devices.md) voor meer informatie. 
    
3. Nadat de Windows 10-apparaten Azure AD toegevoegd zijn, moet elke gebruiker opnieuw hun apparaten en meld u aan met de referenties van Microsoft 365 Business. Alle apparaten hebben nu toegang tot ook bronnen voor gebouwen.
    
Er zijn geen extra stappen vereist voor toegang tot lokale bronnen voor AD Azure verbonden apparaten. Dit is de ingebouwde functionaliteit die beschikbaar is in Windows 10. 
  
Als uw organisatie niet implementeren in Azure AD verbonden configuratie van het apparaat beschreven, kunt u [configuratie van hybride Azure AD verbonden apparaat](manage-windows-devices.md).
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a>Overwegingen wanneer u uw Windows-apparaten met Azure AD

Als u Azure AD lid worden van een Windows-apparaat dat eerder deel uitmaakt van een domein is of een werkgroep, moet u rekening houden met de volgende beperkingen:
  
- Wanneer een apparaat Azure AD lid, wordt een nieuwe gebruiker zonder te verwijzen naar een bestaand profiel gemaakt. U kunt dit oplossen moeten profielen handmatig worden gemigreerd. Een gebruikersprofiel bevat informatie zoals Favorieten, lokale bestanden, instellingen, instellingen van het menu Start, enz. Een beste benadering is een hulpprogramma van derden voor het toewijzen van bestanden en instellingen naar het nieuwe profiel vinden
    
- Als het apparaat wordt met behulp van Group Policy objecten (GPO), sommige groepsbeleidsobjecten niet mogelijk een vergelijkbare [Configuratie Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune. Het [hulpprogramma MMAT](https://www.microsoft.com/download/details.aspx?id=45520) om te zoeken naar vergelijkbare CSP's voor bestaande groepsbeleidsobjecten uitvoeren. 
    
- Gebruikers worden niet geverifieerd aan toepassingen die afhankelijk van de verificatie van Active Directory zijn. Omgaan met met behulp van een oude toepassingen evalueren en bij te werken naar een toepassing die gebruikmaakt van moderne Auth indien mogelijk.
    
- Detectie van Active Directory printer werkt niet. U kunt dit oplossen direct printerpaden bieden voor alle gebruikers of maak gebruik van [Hybride Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
    

