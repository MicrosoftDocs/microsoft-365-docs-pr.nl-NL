---
title: Instellingen aanpassen na inschrijving
description: Bepaalde Microsoft-accounts uitsluiten
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 760fcb94ec6d84a55fe4b8c3cb3540ae29994ae3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918440"
---
# <a name="adjust-settings-after-enrollment"></a>Instellingen aanpassen na inschrijving

Nadat u zich hebt ingeschreven bij Microsoft Managed Desktop, moeten sommige beheerinstellingen mogelijk worden aangepast. Als u indien nodig wilt controleren en aanpassen, volgt u de volgende stappen:

1. Bekijk de instellingen van Microsoft Intune en Azure Active Directory die in de volgende sectie worden beschreven.
2. Als een van de items van toepassing is op uw omgeving, moet u de beschreven aanpassingen aanbrengen.
3. Als u wilt controleren of alle instellingen correct zijn, [](https://aka.ms/mmdart) kunt u het hulpprogramma voor gereedheidsbeoordeling opnieuw uitvoeren om ervoor te zorgen dat er geen conflicten zijn met beheerd bureaublad van Microsoft.

> [!NOTE]
> Als uw bewerkingen in de volgende maanden worden voortgezet, is het mogelijk dat Microsoft Managed Desktop niet meer goed werkt als u na de inschrijving wijzigingen aantekent in beleidsregels in Microsoft Intune, Azure Active Directory of Microsoft 365 die van invloed zijn op Microsoft Managed Desktop. Als u problemen met de service wilt voorkomen, controleert u de specifieke instellingen die worden beschreven in [Problemen](../get-ready/readiness-assessment-fix.md) oplossen die zijn gevonden door het hulpprogramma voor gereedheidsbeoordeling voordat u het beleid wijzigt dat daar wordt vermeld. U kunt het hulpprogramma voor gereedheidsbeoordeling ook op elk moment opnieuw uitvoeren.


## <a name="microsoft-intune-settings"></a>Microsoft Intune-instellingen

- Autopilot-implementatieprofiel: als u een Autopilot-beleid gebruikt, moet u elk beleid bijwerken om de groep Moderne werkplekapparaten **-Alle** Azure AD-apparaten uit te sluiten. Als u deze  wilt bijwerken, selecteert u in de sectie Uitgesloten groepen onder Toewijzingen de groep Moderne werkplekapparaten **-Alle** Azure AD-groep die is gemaakt tijdens microsoft Managed Desktop-registratie. Microsoft Managed Desktop heeft ook een Autopilot-profiel gemaakt, met 'Moderne werkplek' in de naam (het **Autopilot-profiel** voor moderne werkplek). Wanneer u uw eigen Autopilot-profielen  bijwerkt, moet u ervoor zorgen dat u de groep Moderne werkplekapparaten **-Alle** Azure AD-groep niet uitsluit van het **Autopilot-profiel** moderne werkplek dat is gemaakt door Microsoft Managed Desktop.

- Beleid voor voorwaardelijke toegang: Als u nieuwe beleidsregels voor voorwaardelijke toegang maakt met betrekking tot Azure AD,  Microsoft Intune of Microsoft Defender voor Eindpunt na microsoft Managed Desktop-registratie, sluit u de Azure AD-groep Moderne werkplekserviceaccounts uit. Zie Voorwaardelijke [toegang: Gebruikers en groepen voor stappen.](/azure/active-directory/conditional-access/concept-conditional-access-users-groups) Microsoft Managed Desktop onderhoudt afzonderlijke beleidsregels voor voorwaardelijke toegang om de toegang tot deze accounts te beperken. Als u het beleid voor voorwaardelijke toegang van Microsoft Managed Desktop **(Modern Workplace – Secure Workstation)** wilt bekijken, gaat u naar Microsoft Endpoint Manager en gaat u naar **Voorwaardelijke** toegang in **Endpoint Security.** Wijzig geen beleid voor voorwaardelijke toegang van Azure AD dat is gemaakt door Microsoft Managed Desktop met 'Moderne werkplek' in de naam.

- Meervoudige verificatie: Als u nieuwe meervoudige verificatievereisten maakt in beleidsregels voor voorwaardelijke toegang met betrekking tot Azure AD,  Intune of Microsoft Defender voor Eindpunt na de registratie van Microsoft Managed Desktop, sluit u de Azure AD-groep Moderne werkplekserviceaccounts van deze groep uit. Zie Voorwaardelijke [toegang: Gebruikers en groepen voor stappen.](/azure/active-directory/conditional-access/concept-conditional-access-users-groups) Microsoft Managed Desktop onderhoudt afzonderlijke beleidsregels voor voorwaardelijke toegang om de toegang tot leden van deze groep te beperken. Als u het beleid voor voorwaardelijke toegang van Microsoft Managed Desktop **(Modern Workplace -)** wilt bekijken, gaat u naar Microsoft Endpoint Manager en gaat u naar **Voorwaardelijke** toegang in **Endpoint Security.** 

- Updatering van Windows 10: voor elk windows 10-updateringsbeleid dat u hebt gemaakt, sluit u de groep Moderne werkplekapparaten **-Alle** Azure AD-groep uit van elk beleid. Zie Updateringen maken [en toewijzen voor stappen.](/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings) Microsoft Managed Desktop heeft ook een aantal updateringsbeleidsregels gemaakt, die allemaal 'Modern Workplace' in de naam hebben (bijvoorbeeld **Modern Workplace Update Policy [Broad]**, Modern Workplace Update Policy **[Fast]**, **Modern Workplace Update Policy [First]**, and **Modern Workplace Update Policy [Test]**). Wanneer u uw eigen beleid bijwerkt, moet u ervoor zorgen dat u de groep Moderne werkplekapparaten **-Alle** Azure AD-groep niet uitsluit van de apparaten die Microsoft Managed Desktop heeft gemaakt. 


## <a name="azure-active-directory-settings"></a>Azure Active Directory-instellingen

Selfservice password reset: als u selfservice password reset voor alle gebruikers gebruikt, past u de opdracht aan om Microsoft Managed Desktop-serviceaccounts uit te sluiten. Als u deze toewijzing wilt aanpassen, maakt u een dynamische Azure AD-groep voor alle gebruikers, behalve *Microsoft* Managed Desktop-serviceaccounts, en gebruikt u die groep vervolgens voor toewijzing in plaats van 'alle gebruikers'.

Om u te helpen de serviceaccounts te vinden en uit te sluiten, is hier een voorbeeld van een dynamische query die u kunt gebruiken:

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

Vervang in deze query @TENANT door uw tenantdomeinnaam.



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Stappen om aan de slag te gaan met Microsoft Managed Desktop

1. [Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal](add-admin-contacts.md)
2. Instellingen aanpassen na inschrijving (dit artikel)
3. [Licenties toewijzen](assign-licenses.md)
4. [Intune Company Portal implementeren](company-portal.md)
5. [Enterprise State Roaming inschakelen](enterprise-state-roaming.md)
6. [Apparaten instellen](set-up-devices.md)
7. [Uw gebruikers voorbereiden om apparaten te gebruiken](get-started-devices.md)
8. [Apps implementeren](deploy-apps.md)