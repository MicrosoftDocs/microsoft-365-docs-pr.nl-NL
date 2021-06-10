---
title: Waarschuwingsmeldingen configureren die naar MSSP's worden verzonden
description: Waarschuwingsmeldingen configureren die naar MSSP's worden verzonden
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
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166051"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a>Waarschuwingsmeldingen configureren die naar MSSP's worden verzonden 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
>Deze stap kan worden uitgevoerd door de MSSP-klant of MSSP. MsSP's moeten de juiste machtigingen krijgen om dit namens de MSSP-klant te configureren.

Nadat toegang tot de portal is verleend, kunnen waarschuwingsmeldingen worden gemaakt, zodat e-mailberichten worden verzonden naar MSSP's wanneer waarschuwingen aan de tenant worden gemaakt en voorwaarden worden ingesteld.

 
Zie Regels maken [voor waarschuwingsmeldingen voor meer informatie.](configure-email-notifications.md#create-rules-for-alert-notifications)
 

Deze selectievakjes moeten zijn ingeschakeld:
- **Naam van organisatie opnemen:** de klantnaam wordt toegevoegd aan e-mailmeldingen
- **Tenantspecifieke portalkoppeling opnemen:** url van waarschuwingskoppeling heeft tenantspecifieke parameter (tid=target_tenant_id) waarmee directe toegang tot de doel tenantportal wordt mogelijk


## <a name="related-topics"></a>Verwante onderwerpen
- [MSSP-toegang verlenen tot de portal](grant-mssp-access.md)
- [Toegang tot de MSSP-klantportal](access-mssp-portal.md)
- [Waarschuwingen ophalen van de klant-tenant](fetch-alerts-mssp.md)
