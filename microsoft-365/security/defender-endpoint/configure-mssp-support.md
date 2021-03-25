---
title: Ondersteuning voor beheerde beveiligingsservice configureren
description: De benodigde stappen ondernemen om de MSSP-integratie met microsoft Defender voor eindpunt te configureren
keywords: managed security service provider, mssp, configure, integration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6786d423d20ec90c12d2ea712003acc787ed599d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165247"
---
# <a name="configure-managed-security-service-provider-integration"></a>Integratie van beheerde beveiligingsproviders configureren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

U moet de volgende configuratiestappen nemen om de MSSP-integratie (Managed Security Service Provider) in te stellen.

>[!NOTE]
>In dit artikel worden de volgende termen gebruikt om onderscheid te maken tussen de serviceprovider en de service-consument:
> - MSSP's: beveiligingsorganisaties die bieden om beveiligingsapparaten voor een organisatie te bewaken en te beheren.
> - MSSP-klanten: organisaties die zich bezighouden met de services van MSSP's.

Met de integratie kunnen MSSP's de volgende acties uitvoeren:

- Toegang krijgen tot de Microsoft Defender-beveiligingscentrumportal van MSSP-klanten
- E-mailmeldingen ontvangen en 
- Waarschuwingen ophalen via hulpprogramma's voor beveiligingsgegevens en gebeurtenisbeheer (SIEM)

Voordat MSSP's deze acties kunnen uitvoeren, moet de MSSP-klant toegang verlenen tot de Defender for Endpoint-tenant, zodat de MSSP toegang heeft tot de portal. 
 

MsSP-klanten nemen meestal de eerste configuratiestappen om MSSP's toegang te verlenen tot hun Windows Defender Security Central-tenant. Nadat toegang is verleend, kunnen andere configuratiestappen worden uitgevoerd door de MSSP-klant of de MSSP.


In het algemeen moeten de volgende configuratiestappen worden ondernomen:


- **MsSP-toegang verlenen tot Microsoft Defender-beveiligingscentrum** <br>
Deze actie moet worden uitgevoerd door de MSSP-klant. Het verleent de MSSP-toegang tot de Defender for Endpoint-tenant van de MSSP-klant.
 

- **Waarschuwingsmeldingen configureren die zijn verzonden naar MSSP's** <br>
Deze actie kan worden ondernomen door de MSSP-klant of MSSP. Op deze manier weten de MSSP's welke waarschuwingen ze moeten adresseringen voor de MSSP-klant.

- **Waarschuwingen ophalen van de tenant van MSSP-klant in het SIEM-systeem** <br> Deze actie wordt ondernomen door de MSSP. Hiermee kunnen MSSP's waarschuwingen ophalen in SIEM-hulpprogramma's.

- **Waarschuwingen ophalen bij de tenant van MSSP-klanten met API's** <br>
Deze actie wordt ondernomen door de MSSP. Hiermee kunnen MSSP's waarschuwingen ophalen met API's.

## <a name="multi-tenant-access-for-mssps"></a>Multiten tenanttoegang voor MSSP's
Zie [Multi-tenant access for Managed Security Service Providers (Multi-tenant access for Managed Security Service Providers)](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440)voor informatie over het implementeren van een gedelegeerde toegang met meerdere tenants.



## <a name="related-topics"></a>Verwante onderwerpen
- [MSSP-toegang verlenen tot de portal](grant-mssp-access.md)
- [Toegang tot de MSSP-klantportal](access-mssp-portal.md)
- [Waarschuwingsmeldingen configureren](configure-mssp-notifications.md)
- [Waarschuwingen ophalen van klant tenant](fetch-alerts-mssp.md)

