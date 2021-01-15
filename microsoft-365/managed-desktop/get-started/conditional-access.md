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
ms.openlocfilehash: ca919798480698f92bba094c3755b3eccce30888
ms.sourcegitcommit: c1f9a1b2a34146c51c9e33c4119a388b249ce7a9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/14/2021
ms.locfileid: "49867968"
---
# <a name="adjust-settings-after-enrollment"></a>Instellingen aanpassen na inschrijving

Wanneer u klaar bent met de inschrijving in Microsoft Managed Desktop, moeten sommige beheerinstellingen worden aangepast. Ga als volgt te werk om te controleren en zo nodig te wijzigen:

1. Controleer de Microsoft intune-en Azure Active Directory-instellingen die worden beschreven in het volgende gedeelte.
2. Als een van de items op uw omgeving van toepassing is, kunt u de wijzigingen aanbrengen.
3. Als u wilt controleren of alle instellingen correct zijn, kunt u het hulpprogramma voor de [gereedheids beoordeling](https://aka.ms/mmdart) opnieuw uitvoeren om ervoor te zorgen dat er geen conflicten met Microsoft beheerde desktop.

> [!NOTE]
> Als uw bewerkingen worden doorgevoerd in de volgende maanden, is het mogelijk dat Microsoft de beheerde bureaubladversie van Microsoft niet goed werkt als u wijzigingen aanbrengt nadat u het beleid hebt gewijzigd in Microsoft intune, Azure Active Directory of Microsoft 365 die van invloed zijn op Microsoft Managed Desktop. Als u problemen met de service wilt voorkomen, schakelt u de selectievakjes in voor het oplossen van problemen die zijn [gevonden in het hulpprogramma voor de gereedheids beoordeling](../get-ready/readiness-assessment-fix.md) voordat u de hier vermelde beleidsregels wijzigen. U kunt ook het hulpprogramma voor de gereedheids beoordeling op elk moment opnieuw uitvoeren.


## <a name="microsoft-intune-settings"></a>Microsoft intune-instellingen

- Auto Pilot-implementatie profiel: als u auto pilot-beleidsregels gebruikt, moet u deze bijwerken om de **moderne werkplekken te uitsluiten: alle** Azure AD-groep. Als u deze wilt bijwerken, klikt u in de sectie **uitzonderingen** onder **toewijzingen** op de **moderne werkplaatsings apparaten – alle** Azure AD-groep die is gemaakt tijdens de registratie van Microsoft Managed Desktop. Microsoft Managed Desktop heeft ook een auto pilot-profiel gemaakt, dat de ' moderne werkplek ' bevat, in de naam (het auto pilot-Profiel van de **modern Workplace**). Als u uw eigen auto pilot-profielen bijwerkt, moet u ervoor zorgen dat u de **moderne Werkplaatsings apparaten** *niet* uitschakelt: alle Azure AD-groep uit het **modern Workplace auto pilot-profiel** dat is gemaakt door Microsoft Managed Desktop.

- Beleidsregels voor voorwaardelijke toegang: als u een nieuw beleid voor voorwaardelijke toegang in verband met Azure AD, Microsoft intune of Microsoft Defender voor eindpunten maakt na de Microsoft-bureaublad registratie, moet u de Azure AD-groep **service accounts van de moderne werk** stroom uitsluiten Zie voor de stappen [voorwaardelijke toegang: gebruikers en groepen](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Microsoft Managed Desktop onderhoudt afzonderlijke beleidsregels voor voorwaardelijke toegang voor het beperken van de toegang tot deze accounts. Als u het Microsoft-beheerbeleid voor voorwaardelijke toegang (**modern werkstation**) wilt controleren, gaat u naar Microsoft-eindpunttoewijzer en gaat u naar **voorwaardelijke toegang** in de **Endpoint-beveiliging**. Wijzig geen beleid voor voorwaardelijke toegang van Azure AD dat is gemaakt door Microsoft Managed Desktop met de naam modern Workplace.

- Meervoudige verificatie: als u nieuwe meervoudige authenticatie vereisten maakt in beleidsregels voor voorwaardelijke toegang in verband met Azure AD, intune of Microsoft Defender voor eindpunten na de registratie van Microsoft-Bureaubladverificatie, moet u de Azure AD-groep **service accounts voor de moderne werkplek** uitsluiten. Zie voor de stappen [voorwaardelijke toegang: gebruikers en groepen](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Microsoft Managed Desktop onderhoudt afzonderlijke beleidsregels voor voorwaardelijke toegang voor het beperken van de toegang tot leden van deze groep. Als u het Microsoft beheerde bureaublad met voorwaardelijke toegang (**modern Workplace-**) wilt controleren, gaat u naar Microsoft-eindpunt Manager en gaat u naar **voorwaardelijke toegang** in **Endpoint-beveiliging**. 

- Update van Windows 10-update: voor een Windows 10-update ring beleid dat u hebt gemaakt, sluit u de **moderne werkplekken-alle** Azure AD-groep uit van elk beleid. Zie [belsignalen voor updates maken en toewijzen](https://docs.microsoft.com/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings)voor instructies. Microsoft Managed Desktop heeft ook een update ring beleid gemaakt, alles met de naam modern Workplace in de naam (bijvoorbeeld modern werkings **beleid voor updates [algemeen]**, updatebeleid voor de moderne werkplek [ **Fast**], updatebeleid voor de modern Workplace update [ **First**] en modern Workplace **updatebeleid [Test]**). Wanneer u uw eigen beleidsregels bijwerkt, moet u ervoor zorgen dat u de **moderne Werkplaatsings apparaten** niet uitsluiten, *namelijk* alle Azure AD-groep, van degenen die door Microsoft beheerde bureaublad zijn gemaakt.


## <a name="azure-active-directory-settings"></a>Azure Active Directory-instellingen

Selfservice voor wachtwoord opnieuw instellen: als u selfservice voor wachtwoordherstel voor alle gebruikers gebruikt, kunt u de opdracht aanpassen om de beheerde bureaublad serviceaccounts van Microsoft uit te sluiten. Als u deze opdracht wilt aanpassen, maakt u een dynamische Azure AD-groep voor alle gebruikers, *met uitzondering* van Microsoft beheerde bureaublad serviceaccounts en gebruikt u die groep vervolgens voor de toewijzing in plaats van ' alle gebruikers '.

Hier ziet u een voorbeeld van een dynamische query die u kunt gebruiken om de serviceaccounts te zoeken en uit te sluiten:

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

In deze query vervangt u @TENANT door de domeinnaam van de TENANT.



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Stappen om aan de slag te gaan met Microsoft Managed Desktop

1. [Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal](add-admin-contacts.md)
2. Instellingen aanpassen na inschrijving (dit artikel)
3. [Licenties toewijzen](assign-licenses.md)
4. [Intune Company Portal implementeren](company-portal.md)
5. [Enterprise State Roaming inschakelen](enterprise-state-roaming.md)
6. [Apparaten instellen](set-up-devices.md)
7. [Uw gebruikers voorbereiden om apparaten te gebruiken](get-started-devices.md)
8. [Apps implementeren](deploy-apps.md)
