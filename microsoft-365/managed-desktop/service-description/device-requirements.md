---
title: Apparaatvereisten
description: Overzicht van de minimale hardware- en softwarevereisten voor apparaten die met Microsoft Managed Desktop kunnen werken
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 18422f74d87bbadf014de24849235ce5c25bd614
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920466"
---
# <a name="device-requirements"></a>Apparaatvereisten

Microsoft Managed Desktop evalueert regelmatig apparaatvereisten die moeten worden opgenomen in de service. In dit artikel wordt beschreven aan welke hardware- en softwarevereisten een apparaat moet voldoen om met Microsoft Managed Desktop te kunnen werken. U kunt een lijst bekijken met specifieke [apparaten die al zijn](device-list.md) goedgekeurd voor gebruik met de service op basis van deze vereisten.

> [!NOTE]
> Deze vereisten kunnen op elk moment worden gewijzigd, maar we zullen u 30 dagen van de kennisgeving voorzien van wijzigingen in de hardwarevereisten. De vereisten die het laatst zijn gewijzigd, worden gemarkeerd met **\*** . 

## <a name="check-hardware-requirements"></a>Hardwarevereisten controleren

Naast het controleren van apparaatspecificaties, [](../get-ready/readiness-assessment-downloadable.md) kunt u ook de evaluatiecontrole voor downloadbare gereedheid gebruiken om te controleren of een bepaald apparaat aan de vereiste vereisten voldoet. Met dit hulpprogramma worden ook netwerkinstellingen en eindpunten gecontroleerd die ook nodig zijn om de service te laten werken.

## <a name="minimum-requirements"></a>Minimumvereisten

Als u zich wilt inschrijven voor Microsoft Managed Desktop, moet een apparaat aan al deze vereisten voldoen of deze overschrijden.

### <a name="manufacturer"></a>Fabrikant

Het apparaat moet zijn gemaakt door een van deze fabrikanten:

- Dell
- HP
- Lenovo
- Microsoft


### <a name="installed-software"></a>Geïnstalleerde software

Op het apparaat moet deze software vooraf zijn geïnstalleerd:

- Windows 10 Enterprise, Pro of Pro Workstation edition
- de 64-bits versie van Microsoft Office click-to-run 
- Alle toepasselijke apparaat stuurprogramma's


### <a name="physical-features"></a>Fysieke functies

Apparaten moeten de volgende mogelijkheden hebben:

- Ingeschakeld voor UEFI secure boot 
- Vertrouwde platformmodule 2.0 
- Beveiliging op basis van virtualisatie 
- Ondersteunt met Hypervisor beveiligde codeintegriteit 

Zie [Microsoft Managed Desktop-technologieën](../intro/technologies.md)voor meer informatie over deze mogelijkheden en de technologieën die hiermee verband houden.

> [!NOTE]
> ARM processors worden niet ondersteund.

Apparaten moeten voldoen aan of de volgende limieten voor opslag en geheugen overschrijden:

- Opstartstation moet elk ander type dan een harde schijf zijn. Ssd-, NVMe- en eMMC-stations zijn bijvoorbeeld allemaal geldige opties.
- Opstartstation moet een capaciteit van ten minste 128 GB hebben.
- Intern geheugen (RAM) moet gelijk zijn aan of groter zijn dan 8 GB.

Als het apparaat na 1 juli 2020 is gemaakt, moet het ook een IR-camera, vingerafdruklezer of beide hebben om [Windows Hello te ondersteunen.](/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)

## <a name="recommended-requirements"></a>Aanbevolen vereisten

Hoewel het geen absolute vereisten zijn, hebben uw gebruikers een veel betere ervaring als u apparaten kiest die deze functies hebben:

- Een Intel vPro-platformprocessor of een AMD Ryzen Pro-processor
- Opstartstation van het type SSD met een capaciteit van ten minste 256 GB
- Ondersteuning voor moderne stand-by
- Apparaat is van pc-type Secured-core
- Ondersteunt Kernel DMA Protection