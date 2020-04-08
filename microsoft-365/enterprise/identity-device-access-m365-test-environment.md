---
title: Identiteit en apparaattoegang voor uw Microsoft 365-testomgeving
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Maak een Microsoft 365-omgeving om de toegang tot identiteiten en apparaten te testen.
ms.openlocfilehash: 45749140698553a75df50ed1111cdbfc8eb15684
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153736"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Identiteit en apparaattoegang voor uw Microsoft 365-testomgeving

*Deze testlabrichtlijn kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*

[Configuraties voor identiteit en apparaattoegang](microsoft-365-policies-configurations.md) bestaan uit een set van configuraties en beleidsregels voor voorwaardelijke toegang om de toegang te beveiligen tot alle services die zijn geïntegreerd met Azure Active Directory (Azure AD), met inbegrip van Office 365 en Microsoft Intune in Microsoft 365 Enterprise.

U kunt als volgt een testomgeving met deze beleidsregels maken:

1. Configureer uw testomgeving met de vereiste identiteits- en beveiligingsfuncties op basis van uw keuze van identiteitsmodel en verificatiemethode:

  - [Alleen cloud](cloud-only-prereqs-m365-test-environment.md)
  - [Wachtwoord-hash-synchronisatie (PHS)](phs-prereqs-m365-test-environment.md)
  - [Pass Through-verificatie (PTA)](pta-prereqs-m365-test-environment.md)

2. Gebruik [gemeenschappelijk beleid voor identiteits- en apparaattoegang](identity-access-policies.md) om het beleid te configureren dat is gebaseerd op de vereisten en test bescherming voor identiteiten en apparaten.

## <a name="see-also"></a>Zie ook

[Aanvullende testlabrichtlijnen voor identiteit](m365-enterprise-test-lab-guides.md#identity)

[Fase 2: Identiteit](identity-infrastructure.md)

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise-implementatie](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-documentatie](https://docs.microsoft.com/microsoft-365-enterprise/)
