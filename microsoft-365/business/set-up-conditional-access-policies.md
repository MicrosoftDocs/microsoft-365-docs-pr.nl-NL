---
title: Beleid voor voorwaardelijke toegang instellen voor Microsoft 365-campagnes
f1.keywords:
- NOCSH
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
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
description: Meer informatie over het instellen van beleid voor voorwaardelijke toegang voor Microsoft 365-campagnes om aanzienlijke extra beveiliging toe te voegen.
ms.openlocfilehash: 26fadecc69486d7931dac069d8f53061592f397f
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153761"
---
# <a name="set-up-conditional-access-policies"></a>Beleid voor voorwaardelijke toegang instellen

[Het](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) beleid voor voorwaardelijke toegang voegt aanzienlijke extra beveiliging toe. Microsoft biedt een set voorwaardelijke toegangsbeleid basislijn dat wordt aanbevolen voor alle klanten. Basislijnbeleid is een set vooraf gedefinieerde beleidsregels die organisaties helpen beschermen tegen veelvoorkomende aanvallen. Deze veelvoorkomende aanvallen kunnen wachtwoordspray, replay en phishing omvatten.

Voor dit beleid moeten beheerders en gebruikers een tweede vorm van verificatie (multifactorauthenticatie of MFA) invoeren wanneer aan bepaalde voorwaarden is voldaan. Als een gebruiker zich bijvoorbeeld aanmeldt vanuit een ander land, kan de aanmelding als riskant worden beschouwd en moet de gebruiker een extra vorm van verificatie opgeven. 

Momenteel omvat het basislijnbeleid het volgende:
- **Mfa vereisen voor beheerders** &ndash; Vereist multi-factor authenticatie voor de meest bevoorrechte beheerdersrollen, inclusief globale beheerder.
- **Bescherming van eindgebruikers** &ndash; Vereist multi-factor authenticatie voor gebruikers alleen wanneer een aanmelding riskant is. 
- **Verouderde verificatie** &ndash; blokkeren Oudere client-apps en sommige nieuwe apps maken geen gebruik van nieuwere, veiligere verificatieprotocollen. Deze oudere apps kunnen het beleid voor voorwaardelijke toegang omzeilen en ongeautoriseerde toegang tot uw omgeving krijgen. Dit beleid blokkeert de toegang van clients die voorwaardelijke toegang niet ondersteunen. 
- **Mfa vereisen voor servicebeheer** &ndash; Vereist multi-factor authenticatie voor toegang tot beheertools, waaronder Azure portal (waar u basislijnbeleid configureert). 

Microsoft raadt u aan al deze basislijnbeleidsregels in te schakelen. Nadat dit beleid is ingeschakeld, worden beheerders en gebruikers gevraagd zich te registreren voor Azure Multii-Factor-verificatie.

Zie [Wat zijn basislijnbeleid](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)voor meer informatie over dit beleid?


## <a name="set-up-baseline-policies"></a>Basislijnbeleid instellen

1. Ga naar [Azure-portal](https://portal.azure.com)en navigeer naar Voorwaardelijke **toegang** **voor Azure Active Directory** \> .
    
    Het basislijnbeleid wordt op de pagina weergegeven. <br/> <br/>
    ![Pagina met basislijnbeleid voor voorwaardelijke toegang.](../media/baslinepolicies.png)
1. Zie de volgende specifieke instructies voor elk beleid:

  - [MFA vereisen voor beheerders](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [MFA vereisen voor gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [Verouderde verificatie blokkeren](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [MFA vereisen voor servicebeheer](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

U veel aanvullende beleidsregels instellen, zoals het vereisen van goedgekeurde client-apps. Zie de documentatie [voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/)voor meer informatie .
