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
ms.openlocfilehash: e78f0123c909c90ff90be913e8775cc1e5b30313
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777097"
---
# <a name="adjust-settings-after-enrollment"></a>Instellingen aanpassen na inschrijving

Nadat u de registratie hebt voltooid van Microsoft Managed Desktop, moet u de instellingen voor Microsoft intune en Azure Active Directory (Azure AD) die in dit artikel worden beschreven, aanpassen om beheer te kunnen bieden en beveiliging te waarborgen. Stel de volgende instellingen in om specifieke Azure AD-groepen uit te sluiten die Microsoft beheerde bureaublad apparaten en-gebruikers bevatten. Zie [voorwaardelijke toegang: gebruikers en groepen](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users)voor de stappen om groepen uit te sluiten.

> [!NOTE]
> Als u wijzigingen aanbrengt na de inschrijving op beleidsregels in Microsoft intune, Azure Active Directory of Microsoft 365, is het mogelijk dat Microsoft de beheerde bureaubladversie van Microsoft niet goed werkt. Als u problemen met door Microsoft beheerde bureaublad bewerkingen wilt voorkomen, schakelt u de selectievakjes in voor het oplossen van problemen die zijn [gevonden in het hulpprogramma voor de gereedheids beoordeling](../get-ready/readiness-assessment-fix.md) voordat u beleidsregels wijzigt.


## <a name="microsoft-intune-settings"></a>Microsoft intune-instellingen

- Auto Pilot-implementatie profiel: voor auto pilot-profielen die zijn gemaakt door beheerders in uw bedrijf, sluit u de **moderne Werkplaatsings apparaten-alle** Azure AD-groep uit. Zie [Windows-apparaten in intune registreren met behulp van Windows auto pilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)voor stapsgewijze instructies. Sluit niet de **moderne Werkplaatsings apparaten-alle** Azure AD-groep uit op basis van een implementatie beleid dat is gemaakt door het Microsoft-beheer bureaublad met de naam **modern Workplace.** 
- Beleid voor voorwaardelijke toegang: voor regels voor voorwaardelijke toegang die door beheerders in uw bedrijf zijn gemaakt, sluit u de **service accounts voor de modern Workplace service accounts** uit. Zie voor de stappen [voorwaardelijke toegang: gebruikers en groepen](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Sluit niet de **moderne Werkplaatsings apparaten-alle** Azure AD-groep uit op basis van beleidsregels die door Microsoft worden beheerd bureaublad met ' moderne werkplek ' in de naam (bijvoorbeeld **modern Workstation**).
- Meervoudige verificatie: Zorg ervoor dat u beleidsregels voor voorwaardelijke toegang die zijn gemaakt door beheerders in uw bedrijf waarvoor meervoudige verificatie is vereist, geen **service accounts van de moderne werkplek** moeten opnemen. Zie voor meer informatie [beleidsregels voor voorwaardelijke toegang](../get-ready/readiness-assessment-fix.md#conditional-access-policies) en [voorwaardelijke toegang: MFA vereisen voor alle gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).
- Beveiligings basis: voor beleidsregels voor beveiliging op basis van basisregels van beheerders in uw bedrijf, sluit u de **moderne werkplekken uit: alle**  Azure AD-groep. Zie [beveiligings basislijnen gebruiken om Windows 10-apparaten te configureren in intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)voor instructies. Sluit niet de **moderne werkplekken** af van de beleidsregels die door Microsoft worden beheerd, met de naam modern Workplace in de naam (bijvoorbeeld de **basis beveiligings basislijn**.
- Windows 10 update ring: voor Windows 10-update ring beleid dat is gemaakt door beheerders in uw bedrijf, sluit u de **moderne werkplekken uit: alle**  Azure AD-groep. Zie [updates voor Windows 10-software beheren in intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)voor instructies. Sluit niet de **moderne Werkplaatsings apparaten-alle** Azure AD-groep uit op beleidsregels die door Microsoft worden beheerd bureaublad met ' moderne werkplek ' in de naam (bijvoorbeeld het update beleid voor de **modern Workplace update** ).


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
