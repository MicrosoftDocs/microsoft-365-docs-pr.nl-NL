---
title: 'Stap 6: bescherming tegen inbreuk op referenties'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Lees meer over en configureer Azure AD Identity Protection.
ms.openlocfilehash: b1dea9d2917c45bf87bd972f56c9eac2b074c252
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "42810922"
---
# <a name="step-6-protect-against-credential-compromise"></a>Stap 6: bescherming tegen inbreuk op referenties

*Deze stap is optioneel en geldt voor alleen voor de E5-versie van Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In deze stap leert u hoe u beleidsregels configureert die bescherming bieden tegen inbreuken op referenties, waarbij een kwaadwillende gebruiker een aanval uitvoert op de accountnaam en wachtwoord van een gebruiker om toegang te krijgen tot de cloudservices en gegevens van een organisatie. Azure AD Identity Protection biedt verschillende manieren om te voorkomen dat een kwaadwillende gebruiker uw accounts en groepen doorzoekt en vervolgens terecht komt bij uw meest waardevolle gegevens.

Met Azure AD Identity Protection kunt u:

|||
|:---------|:---------|
|Mogelijke beveiligingslekken in de identiteiten van uw organisatie vaststellen en verhelpen|Azure AD maakt gebruik van machine learning om afwijkingen en verdachte activiteiten te ontdekken, zoals aanmeldingen en activiteiten na aanmelding. Met deze gegevens genereert identiteitsbescherming rapporten en waarschuwingen om u te helpen bij het evalueren van problemen en het ondernemen van actie. |
|Verdachte acties opsporen die zijn gerelateerd aan de identiteiten van uw organisatie en automatisch op deze acties te reageren|U kunt beleidsregels met betrekking tot risicobeheer zodanig configureren dat deze automatisch reageren op opgespoorde problemen als een bepaald risiconiveau is bereikt. Met deze beleidsregels kunt u naast andere besturingselementen voor voorwaardelijke toegang die worden geboden door Azure Active Directory en Enterprise Mobility + Security (EMS), de toegang automatisch blokkeren of corrigerende acties ondernemen, waaronder wachtwoordherstel en vereiste meervoudige verificatie voor volgende aanmeldingen.|
|Verdachte incidenten onderzoeken en deze oplossen met beheertaken|U kunt risico gebeurtenissen onderzoeken door informatie over het beveiligingsincident te gebruiken. Er zijn eenvoudige werkstromen beschikbaar om onderzoek bij te houden en herstelbewerkingen uit te voeren, zoals het opnieuw instellen van wachtwoorden.|

Zie [meer informatie over Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).

Zie de [stappen voor het inschakelen van de Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).

Het resultaat van deze stap is dat de Azure AD Identity Protection is ingeschakeld en u deze gebruikt voor het volgende:

- Mogelijke beveiligingslekken met een identiteit oplossen.
- Mogelijke inbreuk op referenties opsporen.
- Het onderzoeken en adresseren van voortdurende verdachte identiteitsincidenten.

|||
|:-------|:-----|
|![Labrichtlijnen testen voor de Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Labrichtlijnen testen: Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

Als tussentijds controlepunt kunt u het [afsluitcriterium](identity-exit-criteria.md#crit-identity-ident-prot) voor deze stap bekijken.

## <a name="next-step"></a>Volgende stap

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [Mappen synchroniseren](identity-azure-ad-connect.md) |


