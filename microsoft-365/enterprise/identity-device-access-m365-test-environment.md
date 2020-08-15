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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Maak een Microsoft 365-omgeving om de toegang tot identiteiten en apparaten te testen.
ms.openlocfilehash: c5bc0fbbb3ae3839cb7aa71e8c840784ae4a4cad
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685852"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Identiteit en apparaattoegang voor uw Microsoft 365-testomgeving

*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*

[Configuraties voor identiteits-en Apparaattoegang](microsoft-365-policies-configurations.md) zijn een set functies en regels voor voorwaardelijke toegang om de toegang te beschermen tot alle services die zijn geïntegreerd in azure Active Directory (Azure AD).

U kunt als volgt een testomgeving met deze beleidsregels maken:

1. Configureer uw testomgeving met de vereiste identiteits- en beveiligingsfuncties op basis van uw keuze van identiteitsmodel en verificatiemethode:

  - [Alleen cloud](cloud-only-prereqs-m365-test-environment.md)
  - [Wachtwoord-hash-synchronisatie (PHS)](phs-prereqs-m365-test-environment.md)
  - [Pass Through-verificatie (PTA)](pta-prereqs-m365-test-environment.md)

2. Gebruik [gemeenschappelijk beleid voor identiteits- en apparaattoegang](identity-access-policies.md) om het beleid te configureren dat is gebaseerd op de vereisten en test bescherming voor identiteiten en apparaten.

## <a name="see-also"></a>Zie ook

[Aanvullende testlabrichtlijnen voor identiteit](m365-enterprise-test-lab-guides.md#identity)

[Identiteitskaart](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
