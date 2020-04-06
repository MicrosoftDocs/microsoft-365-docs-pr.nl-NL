---
title: 'Stap 5: Groepen gebruiken voor beheer'
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
description: U kunt groepen gebruiken om het beheer van sommige administratieve taken te automatiseren.
ms.openlocfilehash: 215bb84cbb0cedc2f1320372ba8239cd51d07c98
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806105"
---
# <a name="step-5-use-groups-for-management"></a>Stap 5: Groepen gebruiken voor beheer

![Fase 2-Identiteit](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a>Bied gebruikers de mogelijkheid om hun eigen groepen te maken en beheren

*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365*

In deze sectie vindt u de Azure AD-groepen (Azure Active Directory) die kunnen worden beheerd door groepseigenaren in plaats van IT-beheerders. Met deze functie, die *selfservice-groepsbeheer* wordt genoemd, kunnen groepseigenaren waaraan geen beheerdersrol is toegewezen, beveiligingsgroepen maken en beheren. 

Gebruikers kunnen lidmaatschap van een beveiligingsgroep aanvragen en dit verzoek wordt vervolgens naar de eigenaar van de groep gestuurd, in plaats van een IT-beheerder. Dit maakt het mogelijk om het groepslidmaatschap te laten beheren door team-, project- of bedrijfseigenaren die het zakelijke doel van de groep begrijpen en het lidmaatschap ervan kunnen beheren.

>[!Note]
>Selfservice-groepsbeheer is alleen beschikbaar voor Azure AD-beveiligingsgroepen en Office 365-groepen. Het is niet beschikbaar voor groepen die met e-mail worden beheerd, distributielijsten of een groep die is gesynchroniseerd vanuit uw Active Directory Domain Services (AD DS) op locatie.
>

Zie de [instructies voor het configureren van een Azure AD-groep voor selfservice-beheer](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) voor meer informatie.

Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-self-service-groups) voor deze sectie bekijken.

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a>Dynamisch groepslidmaatschap instellen

*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365*

In deze sectie maakt u een reeks regels om gebruikersaccounts automatisch toe te voegen of te verwijderen als leden van een Azure AD-groep. Dit wordt *dynamisch groepslidmaatschap* genoemd. De regels zijn gebaseerd op kenmerken van gebruikersaccounts, zoals Afdeling of Land.

De regels worden als volgt toegepast:

- Als een nieuw gebruikersaccount aan alle regels voor de groep voldoet, wordt het lid.
- Als een gebruikersaccount geen lid is van de groep, maar de bijbehorende kenmerken zodanig worden gewijzigd dat deze voldoen aan alle regels voor de groep, wordt het account lid van die groep.
- Als een gebruikersaccount niet voldoet aan alle regels voor de groep, wordt het niet toegevoegd aan de groep.
- Als een gebruikersaccount lid is van de groep, maar de bijbehorende kenmerken zodanig worden gewijzigd dat het niet meer voldoet aan alle regels voor de groep, wordt het account als lid van de groep verwijderd.

Als u dynamisch lidmaatschap wilt gebruiken, moet u eerst bepalen welke sets groepen een gemeenschappelijke set gebruikersaccountkenmerken hebben. Zo moeten bijvoorbeeld alle leden van de afdeling Verkoop zich bevinden in de Azure AD-groep Verkoop op basis van het gebruikersaccountkenmerk Afdeling met de waarde Verkoop.

Zie de [instructies voor het maken en configureren van de regels voor een dynamische Azure AD-groep](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

De resultaten van deze sectie zijn:

- Een set Azure AD-groepen die kan worden geconfigureerd voor dynamisch lidmaatschap
- Een set regels voor elke dynamische groep

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabrichtlijn: licenties en groepslidmaatschap automatiseren](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-dyn-groups) voor deze sectie bekijken.

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a>Automatische licentie instellen

*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365*

In deze stap worden beveiligingsgroepen in Azure AD geconfigureerd om automatisch licenties van een verzameling abonnementen toe te wijzen aan alle leden van de groep. Dit wordt *licenties op groepsbasis* genoemd. Als een gebruikersaccount wordt toegevoegd aan of verwijderd uit de groep, worden de licenties voor de groepsabonnementen automatisch toegewezen aan of verwijderd van het gebruikersaccount. 

Voor Microsoft 365 Enterprise worden Azure AD-beveiligingsgroepen geconfigureerd om de juiste Microsoft 365 Enterprise-licentie toe te wijzen.

Zorg ervoor dat u genoeg licenties hebt voor alle groepsleden. Als u niet genoeg licenties hebt, krijgen nieuwe gebruikers geen licenties totdat er weer licenties beschikbaar zijn.

>[!Note]
>Voor groepen die Azure B2B-accounts (business-to-business) bevatten, dient u *licenties op groepsbasis* niet te configureren.
>

Zie [Beginselen van licenties op groepsbasis in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal) voor meer informatie.

Zie de [stappen om licenties op groepsbasis te configureren voor een Azure-beveiligingsgroep](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).

De resultaten van deze sectie zijn:

- U hebt vastgesteld welke beveiligingsgroepen geschikt zijn voor licenties op groepsbasis.
- U hebt deze groepen geconfigureerd voor licenties op groepsbasis.

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabrichtlijn: licenties en groepslidmaatschap automatiseren](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-group-license) voor deze sectie bekijken.

|||
|:-------|:-----|
|![Stap 6](../media/stepnumbers/Step6.png)| [Identiteitsbeheer configureren](identity-configure-identity-governance.md) |
