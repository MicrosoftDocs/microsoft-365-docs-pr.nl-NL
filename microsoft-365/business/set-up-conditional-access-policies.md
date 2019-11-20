---
title: Beleid voor voorwaardelijke toegang instellen voor Microsoft 365-campagnes
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
description: Informatie over het instellen van beleid voor voorwaardelijke toegang voor Microsoft 365-campagnes.
ms.openlocfilehash: aebdb733c2dd9a05947335ad4f151104d801568e
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/19/2019
ms.locfileid: "38718824"
---
# <a name="set-up-conditional-access-policies"></a>Beleid voor voorwaardelijke toegang instellen

Beleid voor [voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) toevoegen aanzienlijke extra beveiliging. Microsoft biedt een set basislijn beleid voor voorwaardelijke toegang die worden aanbevolen voor alle klanten. Basislijn beleid is een set vooraf gedefinieerde beleidsregels die organisaties helpen beschermen tegen veel veelvoorkomende aanvallen. Deze veelvoorkomende aanvallen kunnen bestaan uit het wachtwoord spray, replay en phishing.

Deze beleidsregels vereisen dat beheerders en gebruikers een tweede vorm van verificatie (multi factor Authentication, of MFA) invoeren wanneer aan bepaalde voorwaarden wordt voldaan. Als een gebruiker zich bijvoorbeeld aanmeldt vanuit een ander land, kan de aanmelding als riskant worden beschouwd en moet de gebruiker een extra verificatie vorm opgeven. 

Op dit moment basislijn beleid omvatten de volgende:
- **MFA vereisen voor beheerders** &ndash; vereist meervoudige verificatie voor de meest bevoorrechte beheerdersrollen, met inbegrip van de globale beheerder.
- **Bescherming** &ndash; van eindgebruikers vereist meervoudige verificatie voor gebruikers alleen wanneer een aanmelding riskant is. 
- **Verouderde verificatie** &ndash; voor oudere client-apps blokkeren en sommige nieuwe apps gebruiken geen nieuwere, veiligere verificatieprotocollen. Deze oudere apps kunnen beleid voor voorwaardelijke toegang omzeilen en onbevoegde toegang tot uw omgeving te krijgen. Dit beleid blokkeert de toegang van clients die geen ondersteuning bieden voor voorwaardelijke toegang. 
- **MFA vereisen voor Service beheer** &ndash; vereist meervoudige verificatie voor toegang tot beheerhulpprogramma's, met inbegrip van Azure Portal (waar u Basisbeleid configureren). 

Microsoft raadt aan dat u al deze basislijn beleid inschakelen. Nadat dit beleid is ingeschakeld, worden beheerders en gebruikers gevraagd om zich te registreren voor Azure Multii-Factor Authentication.

Zie voor meer informatie over dit beleid, [Wat zijn Basisbeleid](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?


## <a name="set-up-baseline-policies"></a>Basislijn beleid instellen

1. Ga naar [Azure Portal](https://portal.azure.com), en navigeer vervolgens naar **Azure Active Directory** \> **voorwaardelijke toegang**.
    
    Het basislijn beleid wordt weergegeven op de pagina. <br/> <br/>
    ![Pagina waarop het basisbeleid voor voorwaardelijke toegang wordt vermeld.](media/baslinepolicies.png)
1. Zie de volgende specifieke instructies voor elk beleid:

  - [MFA vereisen voor beheerders](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [MFA vereisen voor gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [Verouderde verificatie blokkeren](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [MFA vereisen voor servicebeheer](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

U veel extra beleidsregels instellen, zoals het vereisen van goedgekeurde client-apps. Zie de [documentatie voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/)voor meer informatie.
