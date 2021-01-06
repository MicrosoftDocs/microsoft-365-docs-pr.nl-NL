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
ms.openlocfilehash: d7fe410f114d43d4f6c983aaf23d949298635318
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760101"
---
# <a name="adjust-settings-after-enrollment"></a>Instellingen aanpassen na inschrijving

Nadat u de registratie hebt voltooid van Microsoft Managed Desktop, moet u bepaalde instellingen voor Microsoft intune en Azure Active Directory (Azure AD) aanpassen zodat u deze kunt beheren en beveiligen. Stel de volgende instellingen in om Azure AD-groepen uit te sluiten die beheerde bureaublad apparaten en gebruikers van Microsoft bevatten. Zie [voorwaardelijke toegang: gebruikers en groepen](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users)voor de stappen om groepen uit te sluiten.

> [!NOTE]
> Als u wijzigingen aanbrengt na de inschrijving op beleidsregels in Microsoft intune, Azure Active Directory of Microsoft 365, is het mogelijk dat Microsoft de beheerde bureaubladversie van Microsoft niet goed werkt. Als u problemen met door Microsoft beheerde bureaublad bewerkingen wilt voorkomen, schakelt u de selectievakjes in voor het oplossen van problemen die zijn [gevonden in het hulpprogramma voor de gereedheids beoordeling](../get-ready/readiness-assessment-fix.md) voordat u beleidsregels wijzigt.


## <a name="microsoft-intune-settings"></a>Microsoft intune-instellingen

- Auto Pilot-implementatie profiel: Sluit de **moderne werkplekken**  voor de groep Azure AD. Zie [Windows-apparaten in intune registreren met behulp van Windows auto pilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)voor stapsgewijze instructies.
- Beleidsregels voor voorwaardelijke toegang: Sluit de **moderne service accounts van de moderne werk** stroom uit. Zie voor de stappen [voorwaardelijke toegang: gebruikers en groepen](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).
- Meervoudige verificatie: Zorg ervoor dat u een beleid voor voorwaardelijke toegang waarvoor meervoudige verificatie is vereist, geen **service accounts van de moderne werkruimte** moet bieden. Zie voor meer informatie [beleidsregels voor voorwaardelijke toegang](../get-ready/readiness-assessment-fix.md#conditional-access-policies) en [voorwaardelijke toegang: MFA vereisen voor alle gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).
- Beveiligings basislijn: Sluit de **moderne werkplekken en**  de groep Azure AD uit. Zie [beveiligings basislijnen gebruiken om Windows 10-apparaten te configureren in intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)voor instructies.
- Windows 10 update-ring: Sluit de **moderne Werkplaatsings apparaten-alle**  Azure AD-groep uit. Zie [updates voor Windows 10-software beheren in intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)voor instructies.


## <a name="azure-active-directory-settings"></a>Azure Active Directory-instellingen

Selfservice voor wachtwoordherstel: Kies **geselecteerde** instelling en selecteer vervolgens **moderne werkapparatuurs-alle** Azure AD-groep. Zie [Zelfstudie: gebruikers toestaan hun account te ontgrendelen of wachtwoorden opnieuw in te stellen met behulp van Azure Active Directory-wachtwoordherstel](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Stappen om aan de slag te gaan met Microsoft Managed Desktop

1. [Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal](add-admin-contacts.md)
2. Instellingen aanpassen na inschrijving (dit artikel)
3. [Licenties toewijzen](assign-licenses.md)
4. [Intune Company Portal implementeren](company-portal.md)
5. [Enterprise State Roaming inschakelen](enterprise-state-roaming.md)
6. [Apparaten instellen](set-up-devices.md)
7. [Uw gebruikers voorbereiden om apparaten te gebruiken](get-started-devices.md)
8. [Apps implementeren](deploy-apps.md)
