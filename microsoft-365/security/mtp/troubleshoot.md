---
title: Problemen met de service voor bedreigingsbeveiliging van Microsoft oplossen
description: Oplossingen en oplossingen vinden voor bekende problemen met microsoft-bedreigingenbescherming
keywords: problemen met Microsoft Threat Protection, problemen oplossen, Azure ATP, problemen, add-on, instellingenpagina
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bbc7d5d434765b94b0b2707605be2edfbbc8e423
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/01/2020
ms.locfileid: "42809535"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a>Problemen met de service voor bedreigingsbeveiliging van Microsoft oplossen

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging

In deze sectie worden problemen opgelost die zich kunnen voordoen wanneer u de Microsoft Threat Protection-service gebruikt.


## <a name="i-dont-see-microsoft-threat-protection-content"></a>Ik zie geen inhoud voor Microsoft Threat Protection
Als u geen mogelijkheden ziet in het navigatiedeelvenster, zoals het incidenten, actiecentrum of jagen in uw portal, moet u controleren of uw tenant over de juiste licenties beschikt. 

Zie [Vereisten](prerequisites.md)voor meer informatie .

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a>Azure ATP-waarschuwingen worden niet weergegeven in de microsoft-incidenten voor bedreigingsbeveiliging
Als Azure ATP is geïmplementeerd in uw omgeving, maar u Azure ATP-waarschuwingen niet ziet als onderdeel van microsoft-incidenten voor bedreigingsbeveiliging, moet u ervoor zorgen dat de Microsoft Cloud App Security en Azure ATP-integratie is ingeschakeld. 

Zie [Azure ATP-integratie](https://docs.microsoft.com/cloud-app-security/aatp-integration)voor meer informatie.

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Is Microsoft Threat Protection beschikbaar voor GCC (Us Government Community Cloud) of GCC High?
Op dit moment is het niet beschikbaar.

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Waar is de instellingenpagina voor het inschakelen van de service?
Als u Microsoft Threat Protection wilt inschakelen, krijgt u toegang tot **instellingen** via het navigatiedeelvenster in het Microsoft 365-beveiligingscentrum. Dit navigatie-item is alleen zichtbaar als u de [vereiste machtigingen en licenties](mtp-enable.md#check-license-eligibility-and-required-permissions)hebt.

## <a name="can-i-use-an-add-on-instead-of-the-required-e5-licenses"></a>Kan ik een add-on gebruiken in plaats van de vereiste E5-licenties?
Er zijn momenteel geen add-ons voor Microsoft Threat Protection. [Zie licentievereisten](prerequisites.md) 

