---
title: De status van de adreslijstsynchronisatie bekijken in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: In dit artikel leest u hoe u de status van de adreslijstsynchronisatie in Office 365 kunt controleren.
ms.openlocfilehash: 7577ed358a262d5b0ef2932bc73cf61941bec31b
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326947"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>De status van de adreslijstsynchronisatie bekijken in Microsoft 365

Als u uw on-premises Active Directory Domain Services (AD DS) met Azure Active Directory (Azure AD) hebt geïntegreerd met de synchronisatie van uw on-premises omgeving met Microsoft 365, kunt u ook de status van uw synchronisatie controleren.
  
## <a name="view-directory-synchronization-status"></a>De status van de adreslijstsynchronisatie bekijken

- Meld u aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) en kies **DirSync-status** op de startpagina.
- U kunt **ook op** \> de pagina **actieve** gebruikers op de pagina actieve **gebruikers klikken**en **meer** \> **adreslijstsynchronisatie**kiezen. In het deelvenster **adreslijstsynchronisatie** kiest **u Ga naar DirSync-beheer**.

## <a name="information-on-the-manage-directory-synchronization-page"></a>Gegevens op de pagina Adreslijstsynchronisatie beheren

De volgende tabel bevat een overzicht van de functies waarop u informatie kunt vinden over de pagina.
  
Als er een probleem is met uw adreslijstsynchronisatie, worden de fouten ook op deze pagina weergegeven. Zie [fouten met adreslijstsynchronisatie identificeren in Microsoft 365](identify-directory-synchronization-errors.md)voor meer informatie over de verschillende fouten die kunnen optreden.
  
|Item|Doel|
|:-----|:-----|
|**Geverifieerde domeinen** | Het aantal domeinen in uw Microsoft 365-Tenant waarvoor u hebt gecontroleerd of u de eigenaar bent. |
|**Domeinen niet gecontroleerd** | Domeinen die u hebt toegevoegd, maar die niet zijn geverifieerd. |
|**Directory-synchronisatie ingeschakeld** |Waar of onwaar. Hiermee geeft u op of u adreslijstsynchronisatie hebt ingeschakeld. |
|**Laatste adreslijstsynchronisatie** | Laatste keer dat de adreslijstsynchronisatie is uitgevoerd. Geeft een waarschuwing weer en een koppeling naar het hulpprogramma voor probleemoplossing als de laatste synchronisatie langer dan drie dagen geleden was. |
|**Wachtwoordsynchronisatie ingeschakeld** | Waar of onwaar. Hiermee geeft u op of u een hash-synchronisatie tussen onze on-premises en uw Microsoft 365-Tenant hebt. |
|**Laatste Wachtwoordsynchronisatie** | Laatste keer dat de hash-synchronisatie voor het wachtwoord is uitgevoerd. Geeft een waarschuwing weer en een koppeling naar het hulpprogramma voor probleemoplossing als de laatste synchronisatie langer dan drie dagen geleden was. |
|**Versie van adreslijstsynchronisatie client** | Bevat een downloadkoppeling als er een nieuwe versie van Azure AD Connect is uitgebracht. |
|**Serviceaccount adreslijstsynchronisatie** | Toont de naam van uw Microsoft 365 Directory-synchronisatieserviceaccount. |
|||

## <a name="monitor-synchronization-health"></a>Synchronisatiestatus bewaken

In deze sectie installeert u een Azure AD Connect Health-agent op elk van uw on-premises AD DS-domeincontrollers om uw identiteitsinfrastructuur en de synchronisatieservices van Azure AD Connect te bewaken. De bewakingsinformatie wordt beschikbaar gesteld in een Azure AD Connect Health-portal waar u waarschuwingen, prestatiebewaking, gebruiksanalyses en andere informatie kunt bekijken.

De belangrijkste ontwerpbeslissing over hoe u Azure AD Connect Health gaat gebruiken, is gebaseerd op hoe u Azure AD Connect gebruikt:

- Als u de optie **beheerde verificatie** gebruikt, begint u met [Azure AD Connect Health gebruiken met synchronisatie](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync), om Azure AD Connect Health te begrijpen en te configureren.
- Als u alleen de namen synchroniseert van de accounts en groepen met **federatieve verificatie** met Active Directory Federation Services (AD FS), begint u met [Azure AD Connect Health gebruiken met AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) om Azure AD Connect Health te begrijpen en te configureren.

Wanneer u klaar bent, hebt u het volgende:

- De Azure AD Connect Health-agent die is geïnstalleerd op uw on-premises servers van de identiteitsprovider.
- De Azure AD Connect Health-portal met de huidige status van uw on-premises infrastructuur en synchronisatieactiviteiten met de Azure AD-tenant voor uw Microsoft 365- en EMS-abonnementen.

