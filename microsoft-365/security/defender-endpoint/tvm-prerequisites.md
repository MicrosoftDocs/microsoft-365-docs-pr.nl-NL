---
title: Vereisten & machtigingen - bedreigings- en kwetsbaarheidsbeheer
description: Voordat u bedreigings- en kwetsbaarheidsbeheer gaat gebruiken, moet u de relevante configuraties en machtigingen hebben.
keywords: vereisten & vereisten voor beveiligingsprobleembeheer, vereisten voor bedreigings- en kwetsbaarheidsbeheer, MDATP TVM-machtigingen, kwetsbaarheidsbeheer
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ca095a7a65a114182d736176840fdd4e651a8646
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059665"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a>Vereisten & machtigingen - bedreigings- en kwetsbaarheidsbeheer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedreigings- en kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Zorg ervoor dat uw apparaten:

- Zijn onboarded to Microsoft Defender for Endpoint
- Ondersteunde [besturingssystemen en platforms uitvoeren](tvm-supported-os.md)
- De volgende verplichte updates hebben geïnstalleerd en geïmplementeerd in uw netwerk om de detectiepercentages voor kwetsbaarheidsbeoordeling te verhogen:

> Release | KB-nummer en koppeling voor beveiligingsupdate
> :---|:---
> Windows 10 versie 1709 | [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) en [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
> Windows 10 versie 1803 | [KB4493464](https://support.microsoft.com/help/4493464) en [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
> Windows 10 versie 1809 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> Windows 10 versie 1903 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- Zijn onboarded to [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) and Microsoft Endpoint Configuration Manager to  [help remediate](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) threats found by threat and vulnerability management. Als u Configuration Manager gebruikt, moet u de console bijwerken naar de nieuwste versie.
    - **Opmerking:** Als de Intune-verbinding is ingeschakeld, krijgt u een optie om een Intune-beveiligingstaak te maken wanneer u een herstelaanvraag maakt. Deze optie wordt niet weergegeven als de verbinding niet is ingesteld.
- Minimaal één beveiligingsaanbeveling hebben die kan worden bekeken op de apparaatpagina
- Zijn gelabeld of gemarkeerd als co-beheerd

## <a name="relevant-permission-options"></a>Relevante machtigingsopties

1. Meld u aan bij het Microsoft Defender-beveiligingscentrum met behulp van een account met een beveiligingsbeheerder of globale beheerdersrol toegewezen.
2. Selecteer in het navigatiedeelvenster **Instellingen > Rollen.**

Zie Rollen maken en beheren voor op rollen [gebaseerd toegangsbeheer](user-roles.md) voor meer informatie.

### <a name="view-data"></a>Gegevens weergeven

- **Beveiligingsbewerkingen:** alle gegevens over beveiligingsbewerkingen weergeven in de portal
- **Bedreigings- en kwetsbaarheidsbeheer** : gegevens over bedreigings- en kwetsbaarheidsbeheer weergeven in de portal

### <a name="active-remediation-actions"></a>Actieve herstelacties

- **Beveiligingsbewerkingen:** actie ondernemen, in behandeling zijnde herstelacties goedkeuren of afwijzen, toegestane/geblokkeerde lijsten voor automatisering en indicatoren beheren
- **Bedreigings- en kwetsbaarheidsbeheer - Afhandeling van uitzonderingen** - Nieuwe uitzonderingen maken en actieve uitzonderingen beheren
- **Bedreigings- en kwetsbaarheidsbeheer - Herstelafhandeling** - Nieuwe herstelaanvragen indienen, tickets maken en bestaande herstelactiviteiten beheren

Zie [RBAC-machtigingsopties voor meer informatie](user-roles.md#permission-options)

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van bedreigings- en kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md)
- [Ondersteunde besturingssystemen en platforms](tvm-supported-os.md)
- [Apparaatwaarde toewijzen](tvm-assign-device-value.md)
- [Dashboard Bedreigings- en kwetsbaarheidsbeheer](tvm-dashboard-insights.md)

