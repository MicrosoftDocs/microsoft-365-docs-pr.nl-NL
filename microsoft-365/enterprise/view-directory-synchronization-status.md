---
title: Adreslijstsynchronisatiestatus weergeven in Microsoft 365
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
description: In dit artikel leert u hoe u de status van uw adreslijstsynchronisatie kunt controleren in Office 365.
ms.openlocfilehash: cbaae8bbd31f6124c2b0f4984b9a625ffbde538f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924658"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>Adreslijstsynchronisatiestatus weergeven in Microsoft 365

Als u uw on-premises Active Directory Domain Services (AD DS) hebt geïntegreerd met Azure Active Directory (Azure AD) door uw on-premises omgeving te synchroniseren met Microsoft 365, kunt u ook de status van uw synchronisatie controleren.
  
## <a name="view-directory-synchronization-status"></a>De status van de adreslijstsynchronisatie bekijken

- Meld u aan bij [het Microsoft 365-beheercentrum](https://admin.microsoft.com) en kies **DirSync-status** op de startpagina.
- U kunt ook naar  Gebruikers Actieve gebruikers gaan en op de pagina Actieve gebruikers de optie \>  **Meer**  \> **adreslijstsynchronisatie kiezen.** Kies in **het deelvenster Adreslijstsynchronisatie** **de optie Ga naar DirSync-beheer.**

## <a name="information-on-the-manage-directory-synchronization-page"></a>Informatie op de pagina Adreslijstsynchronisatie beheren

De volgende tabel bevat de functies waar u informatie over kunt krijgen op de pagina.
  
Als er een probleem is met de adreslijstsynchronisatie, worden de fouten ook op deze pagina weergegeven. Zie Adreslijstsynchronisatiefouten identificeren [in Microsoft 365](identify-directory-synchronization-errors.md)voor meer informatie over verschillende fouten die u mogelijk ondervindt.
  
|Item|Doel|
|:-----|:-----|
|**Geverifieerde domeinen** | Het aantal domeinen in uw Microsoft 365-tenant dat u hebt geverifieerd. |
|**Domeinen die niet zijn geverifieerd** | Domeinen die u hebt toegevoegd, maar die niet zijn geverifieerd. |
|**Adreslijstsynchronisatie ingeschakeld** |Waar of Onwaar. Hiermee geeft u aan of u adreslijstsynchronisatie hebt ingeschakeld. |
|**Meest recente adreslijstsynchronisatie** | De laatste keer dat adreslijstsynchronisatie is afgelopen. Er wordt een waarschuwing en een koppeling naar een hulpprogramma voor probleemoplossing weergegeven als de laatste synchronisatie meer dan drie dagen geleden was. |
|**Wachtwoordsynchronisatie ingeschakeld** | Waar of Onwaar. Hiermee geeft u aan of u een wachtwoordhashsynchronisatie hebt tussen onze on-premises en uw Microsoft 365-tenant. |
|**Laatste wachtwoordsynchronisatie** | De laatste keer dat wachtwoordhashsynchronisatie werd gebruikt. Er wordt een waarschuwing en een koppeling naar een hulpprogramma voor probleemoplossing weergegeven als de laatste synchronisatie meer dan drie dagen geleden was. |
|**Clientversie adreslijstsynchronisatie** | Bevat een downloadkoppeling als er een nieuwe versie van Azure AD Connect is uitgebracht. |
|**Adreslijstsynchronisatieserviceaccount** | Hiermee wordt de naam van uw Microsoft 365-adreslijstsynchronisatieserviceaccount weergegeven. |
|||

## <a name="monitor-synchronization-health"></a>Synchronisatiestatus bewaken

In deze sectie installeert u een Azure AD Connect Health-agent op elk van uw on-premises AD DS-domeincontrollers om uw identiteitsinfrastructuur en de synchronisatieservices van Azure AD Connect te bewaken. De bewakingsinformatie wordt beschikbaar gesteld in een Azure AD Connect Health-portal waar u waarschuwingen, prestatiebewaking, gebruiksanalyses en andere informatie kunt bekijken.

De belangrijkste ontwerpbeslissing over hoe u Azure AD Connect Health gaat gebruiken, is gebaseerd op hoe u Azure AD Connect gebruikt:

- Als u de optie **beheerde verificatie** gebruikt, begint u met [Azure AD Connect Health gebruiken met synchronisatie](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync), om Azure AD Connect Health te begrijpen en te configureren.
- Als u alleen de namen synchroniseert van de accounts en groepen met **federatieve verificatie** met Active Directory Federation Services (AD FS), begint u met [Azure AD Connect Health gebruiken met AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) om Azure AD Connect Health te begrijpen en te configureren.

Wanneer u klaar bent, hebt u het volgende:

- De Azure AD Connect Health-agent die is geïnstalleerd op uw on-premises servers van de identiteitsprovider.
- De Azure AD Connect Health-portal met de huidige status van uw on-premises infrastructuur en synchronisatieactiviteiten met de Azure AD-tenant voor uw Microsoft 365- en EMS-abonnementen.