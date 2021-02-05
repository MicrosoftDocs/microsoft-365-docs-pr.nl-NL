---
title: Apparaatvereisten
description: Overzicht van de minimale hardware- en softwarevereisten voor apparaten om met het beheerde bureaublad van Microsoft te werken
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a6b5cbbcb2f48797130b080d9d1dd1e6427d4fb8
ms.sourcegitcommit: fa5659cb66d84dcfeebc03b47bd9d38017d8934d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110049"
---
# <a name="device-requirements"></a>Apparaatvereisten

Microsoft Managed Desktop evalueert regelmatig de apparaatvereisten die moeten worden opgenomen in de service. In dit artikel worden de hardware- en softwarevereisten beschreven waar een apparaat aan moet voldoen om met het beheerde bureaublad van Microsoft te kunnen werken. U kunt een lijst bekijken met specifieke [apparaten die al zijn goedgekeurd voor](device-list.md) gebruik met de service op basis van deze vereisten.

> [!NOTE]
> Deze vereisten kunnen op elk moment worden gewijzigd, maar we zullen u 30 dagen van eventuele wijzigingen aan de hardwarevereisten op de kennisgeving laten zien. De vereisten die het meest recent zijn gewijzigd, zijn gemarkeerd met **\*** . 

## <a name="check-hardware-requirements"></a>Hardwarevereisten controleren

U kunt niet alleen de apparaatspecificaties [](../get-ready/readiness-assessment-downloadable.md) bekijken, maar ook de evaluatie van downloadbare gereedheid gebruiken om te controleren of een bepaald apparaat aan de vereiste vereisten voldoet. Dit hulpprogramma controleert ook de netwerkinstellingen en eindpunten die ook nodig zijn om de service te laten werken.

## <a name="minimum-requirements"></a>Minimumvereisten

Als u wilt worden geregistreerd in Microsoft Managed Desktop, moet een apparaat aan al deze vereisten voldoen of voldoen.

### <a name="manufacturer"></a>Fabrikant

Het apparaat moet zijn gemaakt door een van deze fabrikanten:

- Dell
- HP
- Lenovo
- Microsoft


### <a name="installed-software"></a>Geïnstalleerde software

Op het apparaat moet deze software vooraf zijn geïnstalleerd:

- Windows 10 Enterprise, Pro of Pro Workstation edition
- de 64-bits versie van Microsoft Office Klik-en-Start 
- Alle toepasselijke apparaatt stuurprogramma's


### <a name="physical-features"></a>Fysieke functies

Apparaten moeten de volgende mogelijkheden hebben:

- Beveiligde start van UEFI ingeschakeld 
- Vertrouwde platformmodule 2.0 
- Geschikt voor beveiliging op basis van virtualisatie 
- Ondersteunt met Hypervisor beveiligde codeintegriteit 

Zie Microsoft [Managed Desktop-technologieën](../intro/technologies.md)voor meer informatie over deze mogelijkheden en de technologieën die daaraan zijn gerelateerd door de service.

> [!NOTE]
> ARM-processors worden niet ondersteund.

Apparaten moeten voldoen aan de volgende limieten voor opslag en geheugen of deze overschrijden:

- De opstartstation moet een ander type dan een harde schijf zijn. SSD-, NVMe- en eMMC-stations zijn bijvoorbeeld allemaal geldige keuzen.
- Het opstartstation moet een capaciteit hebben van ten minste 128 GB.

Als het apparaat is gemaakt na 1 juli 2020, moet het ook een IR-camera, vingerafdruklezer of beide hebben om [Windows Hello te ondersteunen.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)

## <a name="recommended-requirements"></a>Aanbevolen vereisten

Hoewel dit geen absolute vereisten zijn, hebben uw gebruikers een betere ervaring als u apparaten kiest die deze functies hebben:

- Een Intel vPro-platform processor of een AMD Ryzen Pro-processor
- Opstartstation van het type SSD met een capaciteit van ten minste 256 GB
- Ondersteuning voor moderne stand-by
- Apparaat is van het type Secured-core-pc
- Ondersteunt Kernel DMA-beveiliging
