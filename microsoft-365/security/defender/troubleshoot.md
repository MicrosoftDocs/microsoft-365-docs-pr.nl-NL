---
title: Problemen met de Microsoft 365 Defender-service oplossen
description: Oplossingen en tijdelijke oplossingen zoeken voor bekende Problemen met Microsoft 365 Defender
keywords: problemen met Microsoft 365 Defender oplossen, problemen oplossen, Microsoft Defender voor identiteit, problemen, invoeg-aan- en instellingenpagina
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0c933edfe80275dbfa60464ff862a7609b269332
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933395"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Problemen met de Microsoft 365 Defender-service oplossen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

In deze sectie worden problemen opgelost die zich kunnen voordoen wanneer u de Microsoft 365 Defender-service gebruikt.

## <a name="i-dont-see-microsoft-365-defender-content"></a>Ik zie geen Microsoft 365 Defender-inhoud

Als u geen mogelijkheden ziet in het navigatiedeelvenster, zoals incidenten, actiecentrum of Jagen in uw portal, moet u controleren of uw tenant over de juiste licenties beschikt.

Zie Vereisten voor [meer informatie.](prerequisites.md)

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft Defender voor identiteitswaarschuwingen worden niet weergegeven in de Microsoft 365 Defender-incidenten

Als Microsoft Defender voor identiteit is geïmplementeerd in uw omgeving, maar u geen defender voor identiteitswaarschuwingen ziet als onderdeel van Microsoft 365 Defender-incidenten, moet u ervoor zorgen dat de Microsoft Cloud App Security en Defender voor identiteitsintegratie is ingeschakeld.

Zie Microsoft [Defender voor identiteitsintegratie](/cloud-app-security/mdi-integration)voor meer informatie.

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a>Waar is de pagina met instellingen voor het in- en uitschakelen van de service?

Als u Microsoft 365 Defender wilt in- of uitschakelen, hebt u toegang tot Instellingen **vanuit** het navigatiedeelvenster in het Microsoft 365-beveiligingscentrum. Dit navigatie-item is alleen zichtbaar als u de vereiste [machtigingen en licenties hebt.](m365d-enable.md#check-license-eligibility-and-required-permissions)

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a>Hoe maak ik een uitzondering voor mijn bestand/URL?

Een fout-positief is een bestand of URL dat wordt gedetecteerd als schadelijk, maar geen bedreiging is. U kunt indicatoren maken en uitsluitingen definiëren om bepaalde bestanden/URL's te deblokkeren en toe te staan. Zie [Fout-positieve/negatieven adresseert in Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).


