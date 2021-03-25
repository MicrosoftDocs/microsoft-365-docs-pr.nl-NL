---
title: Identiteit en apparaattoegang voor uw Microsoft 365-testomgeving
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Maak een Microsoft 365-omgeving om de toegang tot identiteiten en apparaten te testen.
ms.openlocfilehash: 5a9e9ef9ea6b8f6dc80aa7fea225f3573b8fcadc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197873"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Identiteit en apparaattoegang voor uw Microsoft 365-testomgeving

*Deze testlaborator kan alleen worden gebruikt voor Microsoft 365 voor testomgevingen voor ondernemingen.*

[Configuraties voor identiteits-](../security/office-365-security/microsoft-365-policies-configurations.md) en apparaattoegang zijn een reeks aanbevolen configuraties en beleid voor voorwaardelijke toegang om de toegang tot alle services te beschermen die zijn geïntegreerd met Azure Active Directory (Azure AD).

Een testomgeving maken met de algemene configuraties voor identiteits- en apparaattoegang:

1. Configureer uw testomgeving met de vereiste identiteits- en beveiligingsfuncties op basis van uw keuze van identiteitsmodel en verificatiemethode:

  - [Alleen cloud](cloud-only-prereqs-m365-test-environment.md)
  - [Wachtwoordhashsynchronisatie (PHS)](phs-prereqs-m365-test-environment.md)
  - [Pass Through-verificatie (PTA)](pta-prereqs-m365-test-environment.md)

2. Gebruik [gemeenschappelijk beleid](../security/office-365-security/identity-access-policies.md) voor identiteits- en apparaattoegang om het beleid te configureren dat is gebaseerd op de vereisten die zijn geconfigureerd voor uw testomgeving en om de beveiliging voor identiteiten en apparaten te verkennen en te controleren.

## <a name="see-also"></a>Zie ook

[Aanvullende testlabrichtlijnen voor identiteit](m365-enterprise-test-lab-guides.md#identity)

[Routekaart voor identiteit](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Microsoft 365 enterprise-documentatie](/microsoft-365-enterprise/)
