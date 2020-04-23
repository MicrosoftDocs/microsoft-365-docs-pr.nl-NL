---
title: 'Stap 1: Uw globale beheerdersaccounts maken en beveiligen'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Uw globale beheerdersaccounts hebben een speciale behandeling nodig om ze te beschermen tegen inbreuk van referenties.
ms.openlocfilehash: c23a5730bc4c6af1f7fd829a40b63cc7ccc89184
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43621304"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a>Stap 1: Uw globale beheerdersaccounts maken en beveiligen

![Fase 2: Identiteit](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a>Wereldwijde beheerdersaccounts beveiligen

*Dit is vereist en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*

In deze sectie helpt u digitale aanvallen voorkomen op uw organisatie door ervoor te zorgen dat uw beheerdersaccounts zo veilig mogelijk zijn. Om dit te doen, moet u:

- Meer dan één specifieke globale beheerdersaccount maken met [sterke wachtwoorden](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) en ze alleen gebruiken wanneer dat nodig is.
- Dagelijks beheer uitvoeren door specifieke beheerdersrollen (zoals Exchange-beheerder of Wachtwoordbeheerder) toe te wijzen aan andere specifieke accounts voor die rollen of gebruikersaccounts van IT-medewerkers.

Voor uw specifieke globale beheerdersaccounts moet u ook:

1. Per gebruikersaccount testen of de Azure MFA-instellingen (Multi-Factor Authentication) voor voorwaardelijke toegang op een testgebruikersaccount testen om u ervan te verzekeren dat MFA correct en voorspelbaar werkt. MFA vereist een tweede vorm van verificatie, zoals een verificatiecode die naar een smartphone wordt gestuurd.
2. Maak beleid voor voorwaardelijke toegang voor uw globale beheerdersaccounts dat MFA vereist, schakel dat in en gebruik de sterkste vorm van secundaire verificatie die beschikbaar is binnen uw organisatie. Zie [Azure meervoudige verificatie](identity-access-prerequisites.md#protecting-administrator-accounts)voor meer informatie.

Zie [Uw globale beheerdersaccount beveiligen](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations) voor aanvullende bescherming.

> [!Note]
> Noodtoegangsaccounts voor ‘break glass’-scenario’s, zoals een cyberaanval moeten cloudaccounts zijn. U kunt ook globale beheerdersaccounts (geschikt als of permanent) hebben die niet alleen in de cloud worden gebruikt. Zie [Noodtoegangsaccounts beheren in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access) voor meer informatie.

De resultaten van deze sectie zijn:

- De enige gebruikersaccounts in uw abonnement met de globale beheerdersrol, zijn de toegewezen globale beheerdersaccounts. Verifieer dit met de volgende Azure Active Directory PowerShell voor Graph-opdracht: 
  ```powershell
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- Aan alle andere gebruikersaccounts waarmee uw abonnementservices worden beheerd, zijn beheerdersrollen toegewezen die zijn gekoppeld aan de bijbehorende taakverantwoordelijkheden.

> [!Note]
> Zie [Verbinding maken met Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) voor instructies over het installeren van de Azure Active Directory PowerShell for Graph-module en het aanmelden.

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Zie de [Testlabrichtlijn globale beheerdersaccounts beschermen](protect-global-administrator-accounts-microsoft-365-test-environment.md) om deze configuratie in een testlab-omgeving te oefenen. |
|||

Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-global-admin) voor deze stap bekijken.


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a>Beheerders-op-aanvraag instellen

*Dit is optioneel en geldt alleen voor de E5-versie van Microsoft 365 Enterprise*

In deze sectie stelt u de Azure Active Directory Privileged Identity Management (PIM) in om de tijd te verminderen dat uw beheerdersaccounts kwetsbaar zijn voor aanvallen door kwaadwillende gebruikers. Met PIM kunt u op aanvraag een just-in-time-instructie van de beheerdersrollen inschakelen wanneer dat nodig is.  

In plaats van dat uw beheerdersaccounts permanente beheerders zijn, worden ze in aanmerking komende beheerders. De beheerdersrol is inactief totdat iemand deze nodig heeft. Vervolgens voert u een activeringsprocedure uit om de beheerdersrol gedurende een bepaalde tijd toe te voegen aan het beheerdersaccount. Als de tijd is verstreken, verwijdert PIM de beheerdersrol uit het beheerdersaccount.

PIM is beschikbaar met Azure Active Directory Premium P2, dat inbegrepen is bij Microsoft 365 E5. U kunt ook afzonderlijke Azure Active Directory Premium P2-licenties aanschaffen voor uw beheerdersaccounts.

Als u Azure PIM wilt inschakelen voor uw Azure Active Directory tenant -en beheerdersaccounts, raadpleegt u de [stappen voor het configureren van PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

U kunt een uitgebreide roadmap ontwikkelen om bevoegde toegang te beveiligen tegen cyberaanvallers, zie [Bevoegde toegang voor hybride en cloudimplementaties in Azure Active Directory beveiligen](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-pim) voor deze stap bekijken.


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a>Privileged Access Management

Geprivilegieerd toegangsbeheer wordt ingeschakeld door beleid te configureren dat just-in-time-toegang specificeert voor taakactiviteiten in uw tenant. Deze functie kan helpen uw organisatie te beschermen tegen inbreuken die mogelijk bestaande geprivilegieerde beheerdersaccounts gebruiken met permanente toegang tot gevoelige gegevens of toegang tot belangrijker configuratie-instellingen. U kunt bijvoorbeeld geprivilegieerd toegangsbeheerbeleid configureren dat expliciete goedkeuring vereist voor toegang tot en het wijzigen van postvakinstellingen van de organisatie in uw tenant.

In deze stap schakelt u geprivilegieerd toegangsbeheer in uw tenant in en configureert u geprivilegieerd toegangsbeleid dat aanvullende bescherming biedt voor taaktoegang tot gegevens en configuratie-instellingen voor uw organisatie. Er zijn drie basisstappen om aan de slag te gaan met geprivilegieerde toegang in uw organisatie:

- Een groep met fiatteurs maken
- Geprivilegieerde toegang inschakelen
- Goedkeuringsbeleid maken

Als geprivilegieerd toegangsbeheer is geconfigureerd, kan uw organisatie opereren zonder permanente bevoegdheden en een verdedigingslaag bieden tegen kwetsbaarheden die voortkomen uit dergelijke permanente beheerderstoegang. Geprivilegieerde toegang vereist goedkeuring voor het uitvoeren van taken met een bijbehorend goedkeuringsbeleid. Gebruikers die taken moeten uitvoeren die zijn opgenomen in het goedkeuringsbeleid, moeten toestemming voor toegang aanvragen en krijgen om de machtigingen te krijgen die nodig zijn om de taken, die zijn gedefinieerd in het beleid, uit te voeren.

Zie het onderwerp [Geprivilegieerd toegangsbeheer configureren](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) om Privileged Access Management in te schakelen.

Zie het onderwerp [Geprivilegieerd toegangsbeheer](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) voor meer informatie.


|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Zie de [Testlabrichtlijn geprivilegieerd toegangsbeheer](privileged-access-microsoft-365-enterprise-dev-test-environment.md) om deze configuratie in een testlab-omgeving te oefenen. |
|||

Zie de [afsluitcriteria](identity-exit-criteria.md#crit-identity-pam) voor deze stap als tussentijds controlepunt.

## <a name="next-step"></a>Volgende stap

|||
|:-------|:-----|
|![Stap 2](../media/stepnumbers/Step2.png)| [Wachtwoorden beveiligen](identity-secure-your-passwords.md) |

