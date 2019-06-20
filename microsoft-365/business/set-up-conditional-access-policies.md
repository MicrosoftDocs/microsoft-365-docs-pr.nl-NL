---
title: Instellen van het beleid voor Microsoft 365 campagnes voorwaardelijke toegang
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
search.appverid:
- BCS160
- MET150
- MOE150
description: Informatie over het instellen van het beleid van voorwaardelijke toegang voor Microsoft 365 campagnes.
ms.openlocfilehash: 7d8e1f16019d151478aae57b1593b0e0758e5b19
ms.sourcegitcommit: 7e46db0b35c188ee6a7b40ab3eb2d76ff6c101c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2019
ms.locfileid: "35086307"
---
# <a name="set-up-conditional-access-policies"></a>Instellen van het beleid van voorwaardelijke toegang

[-Voorwaardelijke](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) beleidsregels toevoegen substancial extra beveiliging. Microsoft biedt een reeks basislijn voorwaardelijke toegang beleidsregels die worden aanbevolen voor alle klanten. Beleid van de basislijn zijn een reeks vooraf gedefinieerde beleidsinstellingen die organisaties tegen veel voorkomende aanvallen beschermen. Deze gemeenschappelijke aanvallen zijn wachtwoord spray, replay en phishing.

Dit beleid is vereist voor beheerders en gebruikers kunnen invoeren, een tweede vorm van verificatie (multifactor-verificatie of MVR gesloten genoemd) wanneer aan bepaalde voorwaarden wordt voldaan. Bijvoorbeeld als een gebruiker vanaf een ander land aanmeldt zich, moet het aanmelden kan worden beschouwd als riskant en de gebruiker een extra vorm van verificatie. 

Op dit moment omvatten basislijn beleid het volgende:
- **MVR gesloten nodig voor beheerders** — meerledige verificatie vereist is voor de meeste bevoegdheden beheerdersrollen, inclusief globale beheerder.
- **Bescherming van de eindgebruiker** — meerledige verificatie vereist is voor gebruikers alleen wanneer een aanmelden riskant is. 
- **Verouderde verificatie blok** , oudere clienttoepassingen en sommige nieuwe apps geen nieuwere, meer beveiligde verificatieprotocollen gebruiken. Deze oudere apps kunnen omzeilen van beleid voor voorwaardelijke toegang en onbevoegde toegang krijgen tot uw omgeving. Dit beleid blokkeert de toegang van clients die geen ondersteuning voor voorwaardelijke toegang bieden. 
- **MVR gesloten vereist voor servicebeheer** , meerledige verificatie vereist is voor toegang tot de beheerprogramma's, waaronder Azure portal (waar u basislijn beleidsregels configureren). 

Microsoft adviseert dat u deze basislijn beleid inschakelen. Nadat u dit beleid hebt ingeschakeld, worden beheerders en gebruikers te registreren voor Azure Multii-Factor verificatie gevraagd.

Zie [Wat zijn volgens de basislijn beleid](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)voor meer informatie over deze beleidsregels?


## <a name="set-up-baseline-policies"></a>Beleid basislijn instellen

1. Ga naar [Azure portal](https://portal.azure.com)en navigeer vervolgens naar **Azure Active Directory** \> **Voorwaardelijke toegang**.
    
    Het beleid van de basislijn worden vermeld op de pagina. <br/> <br/>
    ![Pagina met basislijn beleid voor voorwaardelijke toegang.](media/baslinepolicies.png)
1. Zie de volgende specifieke instructies voor elk beleid:

  - [MVR gesloten voor beheerders vereisen](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [MFA Reequire voor gebruikers](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [Verouderde verificatie blokkeren](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [MVR gesloten vereist voor servicebeheer](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

U kunt veel aanvullend beleid, zoals het verplicht stellen van goedgekeurde clienttoepassingen instellen. Raadpleeg de [Documentatie van voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/) voor meer informatie.