---
title: Toegang tot Microsoft Defender-beveiligingscentrum MSSP-klantportal
description: Toegang tot Microsoft Defender-beveiligingscentrum MSSP-klantportal
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
ms.openlocfilehash: 97122decede91e8b4f059b3b66999ac12b300172
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164855"
---
# <a name="access-the-microsoft-defender-security-center-mssp-customer-portal"></a>Toegang tot Microsoft Defender-beveiligingscentrum MSSP-klantportal

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
>Deze reeks stappen zijn gericht op de MSSP. 

MsSP-klanten hebben standaard toegang tot hun Microsoft Defender-beveiligingscentrum tenant via de volgende URL: `https://securitycenter.windows.com` .
 

MSSP's moeten echter een tenantspecifieke URL gebruiken in de volgende indeling: om toegang te krijgen  `https://securitycenter.windows.com?tid=customer_tenant_id` tot de MSSP-klantportal. 

In het algemeen moeten MSSP's worden toegevoegd aan de Azure AD van de MSSP-klant die ze willen beheren.


Gebruik de volgende stappen om de MSSP-klant tenant-id te verkrijgen en vervolgens de id te gebruiken om toegang te krijgen tot de tenantspecifieke URL:

1. Meld u als MSSP aan bij Azure AD met uw referenties. 

2. Schakel adreslijst over naar de tenant van de MSSP-klant.

3.  Selecteer **Azure Active Directory > Eigenschappen**. U vindt de tenant-id in het veld Adreslijst-id. 

4. Open de MSSP-klantportal door de waarde in de `customer_tenant_id` volgende URL te vervangen: `https://securitycenter.windows.com?tid=customer_tenant_id` .


## <a name="related-topics"></a>Verwante onderwerpen
- [MSSP-toegang verlenen tot de portal](grant-mssp-access.md)
- [Waarschuwingsmeldingen configureren](configure-mssp-notifications.md)
- [Waarschuwingen ophalen van de klant-tenant](fetch-alerts-mssp.md)
