---
title: Vereisten & machtigingen - Threat and Vulnerability Management
description: Voordat u begint met Threat and Vulnerability Management, moet u de relevante configuraties en machtigingen hebben.
keywords: vereisten & vulnerability management voor bedreigingen Threat and Vulnerability Management machtigingen, vereisten voor Microsoft Defender voor endpoint-tvm-machtigingen, vulnerability management
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c0544665ea4e9b1ceafa645a2dcc96a224b0c242
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843948"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a>Vereisten & machtigingen - Threat and Vulnerability Management

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedreiging en vulnerability management](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Zorg ervoor dat uw apparaten:

- Zijn onboarded to Microsoft Defender for Endpoint
- Ondersteunde [besturingssystemen en platforms uitvoeren](tvm-supported-os.md)
- De volgende verplichte updates hebben geïnstalleerd en geïmplementeerd in uw netwerk om de detectiepercentages voor kwetsbaarheidsbeoordeling te verhogen:

> Release | KB-nummer en koppeling voor beveiligingsupdate
> :---|:---
> Windows 10 Versie 1709 | [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) en [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
> Windows 10 Versie 1803 | [KB4493464](https://support.microsoft.com/help/4493464) en [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
> Windows 10 Versie 1809 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> Windows 10 Versie 1903 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- Zijn onboarded [voor](/mem/intune/fundamentals/what-is-intune) Microsoft Intune en [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) om te helpen bij het herstellen van bedreigingen die door Threat and Vulnerability Management. Als u Configuration Manager gebruikt, moet u de console bijwerken naar de nieuwste versie.
    - **Opmerking:** Als de Intune-verbinding is ingeschakeld, krijgt u een optie om een Intune-beveiligingstaak te maken wanneer u een herstelaanvraag maakt. Deze optie wordt niet weergegeven als de verbinding niet is ingesteld.
- Minimaal één beveiligingsaanbeveling hebben die kan worden bekeken op de apparaatpagina
- Zijn gelabeld of gemarkeerd als co-beheerd

## <a name="relevant-permission-options"></a>Relevante machtigingsopties

1. Meld u aan bij Microsoft Defender-beveiligingscentrum account met een beveiligingsbeheerder of globale beheerdersrol toegewezen.
2. Selecteer in het navigatiedeelvenster **Instellingen > Rollen.**

Zie Rollen maken en beheren voor op rollen [gebaseerd toegangsbeheer](user-roles.md) voor meer informatie.

### <a name="view-data"></a>Gegevens weergeven

- **Beveiligingsbewerkingen:** alle gegevens over beveiligingsbewerkingen weergeven in de portal
- **Bedreiging en vulnerability management** - Bekijk Threat and Vulnerability Management gegevens in de portal

### <a name="active-remediation-actions"></a>Actieve herstelacties

- **Beveiligingsbewerkingen:** actie ondernemen, in behandeling zijnde herstelacties goedkeuren of afwijzen, toegestane/geblokkeerde lijsten voor automatisering en indicatoren beheren
- **Bedreiging en vulnerability management - Afhandeling van uitzonderingen** - Nieuwe uitzonderingen maken en actieve uitzonderingen beheren
- **Bedreiging en vulnerability management -** Herstelafhandeling - Nieuwe herstelaanvragen indienen, tickets maken en bestaande herstelactiviteiten beheren

Zie [RBAC-machtigingsopties voor meer informatie](user-roles.md#permission-options)

## <a name="related-articles"></a>Aanverwante artikelen

- [Overzicht van bedreigingen en vulnerability management](next-gen-threat-and-vuln-mgt.md)
- [Ondersteunde besturingssystemen en -platforms](tvm-supported-os.md)
- [Apparaatwaarde toewijzen](tvm-assign-device-value.md)
- [Bedreiging en vulnerability management dashboard](tvm-dashboard-insights.md)

