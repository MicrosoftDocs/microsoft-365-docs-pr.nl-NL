---
title: Detecties naar uw SIEM-hulpprogramma's halen vanuit Microsoft Defender voor Eindpunt
description: Meer informatie over het gebruik van REST API en het configureren van ondersteunde hulpprogramma's voor beveiligingsgegevens en gebeurtenissenbeheer voor het ontvangen en trekken van detecties.
keywords: siem- en beveiligingsinformatie- en evenementenbeheerhulpmiddelen configureren, splunk, boogsight, aangepaste indicatoren, rest-api, waarschuwingsdefinities, indicatoren van compromissen
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
ms.openlocfilehash: 0b9ce376736e5f00ee0f6a4f308d783e75052357
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163293"
---
# <a name="pull-detections-to-your-siem-tools"></a>Detecties naar uw SIEM-hulpprogramma's trekken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a>Detecties trekken met behulp van siem-hulpprogramma's (Security Information and Events Management)

>[!NOTE]
>- [Microsoft Defender for Endpoint Alert](alerts.md) is samengesteld uit een of meer detecties.
>- [Microsoft Defender voor eindpuntdetectie](api-portal-mapping.md) is samengesteld uit de verdachte gebeurtenis op het apparaat en de bijbehorende waarschuwingsgegevens.
>-De Microsoft Defender for Endpoint Alert API is de nieuwste API voor waarschuwingsverbruik en bevat een gedetailleerde lijst met verwante gegevens voor elke waarschuwing. Zie Waarschuwingsmethoden en [-eigenschappen](alerts.md) en [Lijstwaarschuwingen](get-alerts.md)voor meer informatie.

Defender for Endpoint ondersteunt hulpprogramma's voor beveiligingsgegevens en gebeurtenisbeheer (SIEM) om detecties op te halen. In Defender for Endpoint worden waarschuwingen via een HTTPS-eindpunt dat wordt gehost in Azure, beschikbaar. Het eindpunt kan worden geconfigureerd om detecties op te halen van uw enterprise tenant in Azure Active Directory (AAD) met behulp van het OAuth 2.0-verificatieprotocol voor een AAD-toepassing die de specifieke SIEM-connector vertegenwoordigt die in uw omgeving is geïnstalleerd.

Defender voor Eindpunt ondersteunt momenteel de volgende specifieke SIEM-oplossingshulpmiddelen via een speciaal SIEM-integratiemodel:

- IBM QRadar
- MicroFocus ArcSight

Andere SIEM-oplossingen (zoals Splunk, RSA NetWitness) worden ondersteund via een ander integratiemodel op basis van de nieuwe Alert API. Zie de pagina [Partnertoepassing](https://securitycenter.microsoft.com/interoperability/partners) voor meer informatie en selecteer de sectie Beveiligingsgegevens en analyse voor meer informatie.

Als u een van deze ondersteunde SIEM-hulpprogramma's wilt gebruiken, moet u het volgende doen:

- [SIEM-integratie inschakelen in Defender voor Eindpunt](enable-siem-integration.md)
- Het ondersteunde SIEM-hulpprogramma configureren:
     - [HP ArcSight configureren om Defender te gebruiken voor eindpuntdetecties](configure-arcsight.md)
     - CONFIGURE IBM QRadar to pull Defender for Endpoint detections (IBM [Knowledge Center)](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)voor meer informatie.

Zie Defender [voor eindpuntdetectievelden](api-portal-mapping.md)voor meer informatie over de lijst met velden die worden weergegeven in de Detectie-API.
