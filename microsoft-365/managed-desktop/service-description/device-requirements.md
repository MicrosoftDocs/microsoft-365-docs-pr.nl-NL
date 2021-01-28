---
title: Apparaatvereisten
description: Overzicht van de minimale hardware-en softwarevereisten voor apparaten die werken met Microsoft beheerde bureaublad
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 88b1ba657b4823d90a41b28b01362760676410ba
ms.sourcegitcommit: b3bb5bf5efa197ef8b16a33401b0b4f5663d3aa0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/28/2021
ms.locfileid: "50032683"
---
# <a name="device-requirements"></a>Apparaatvereisten

Microsoft Managed Desktop evalueert regelmatig de hardwarevereisten voor het opnemen van de service. In dit artikel worden de hardware-en softwarevereisten beschreven waarmee een apparaat moet vergaderen om te kunnen werken met Microsoft beheerde bureaublad. U kunt een lijst met specifieke apparaten bekijken die [al zijn goedgekeurd](device-list.md) voor gebruik met de service op basis van deze vereisten.

> [!NOTE]
> Deze vereisten kunnen op elk moment worden gewijzigd, maar we leveren 90 dagen kennisgeving van dergelijke wijzigingen. De vereisten die het laatst zijn gewijzigd, zijn gemarkeerd met **\*** . 

## <a name="check-hardware-requirements"></a>De hardwarevereisten controleren

U kunt ook de specificaties van apparatuur reviseren, maar ook de downloadbare [gereedheids beoordelings controle](../get-ready/readiness-assessment-downloadable.md) gebruiken om te controleren of een bepaald apparaat aan de vereisten voldoet. Met dit hulpprogramma worden ook de netwerkinstellingen en eindpunten gecontroleerd die ook voor de service werken.

## <a name="minimum-requirements"></a>Minimum vereisten

Als u zich wilt aanmelden bij Microsoft Managed Desktop, moet een apparaat voldoen aan of groter zijn met deze vereisten.

### <a name="manufacturer"></a>Beste

Het apparaat moet zijn gemaakt door een van de volgende fabrikanten:

- Dell
- HP
- Lenovo
- Microsoft


### <a name="installed-software"></a>Geïnstalleerde software

Op het apparaat moet deze software vooraf zijn geïnstalleerd:

- Windows 10 Enterprise, Pro of Pro Workstation Edition
- {de 64-bits versie van Office klik-en-klaar {I controleert de naam van de Office-collega's]}
- Alle toepasselijke apparaatstuurprogramma's


### <a name="physical-features"></a>Fysieke functies

Apparaten moeten beschikken over de volgende mogelijkheden:

- Geschikt voor UEFI Secure boot 
- Trusted Platform Module 2,0 
- Geschikt voor op virtualisatie gebaseerde beveiliging 
- Ondersteuning voor de integriteit van hypervisor-beveiligde code 

Ga voor meer informatie over deze mogelijkheden en de technologieën die bij deze service worden gebruikt, naar [Microsoft Managed Desktop Technologies](../intro/technologies.md).

> [!NOTE]
> ARM-processors worden niet ondersteund.

Apparaten moeten voldoen aan of hoger zijn dan de limieten voor opslagruimte en geheugen:

- Het opstartstation moet elk type zijn dat geen harde schijf is. Zo zijn SSD, NVMe en eMMC drives allemaal geldige keuzes.
- Het opstartstation moet een capaciteit van minimaal 128 GB hebben.

Als het apparaat is gemaakt na 1 juli 2020, moet het ook een IR-camera, vingerafdruklezer of beide hebben om [Windows hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)te kunnen ondersteunen.

## <a name="recommended-requirements"></a>Aanbevolen vereisten

Hoewel ze geen absolute vereisten zijn, hebben uw gebruikers een veel betere ervaring wanneer u apparaten kiest met deze functies:

- Een Intel vPro-platform processor of een AMD Ryzen Pro-processor
- Opstartstation van het type SSD met een capaciteit van minimaal 256 GB
- Ondersteuning voor moderne standby
- Apparaat is van een beveiligd core-PC-type
- Ondersteuning voor DMA-beveiliging van kernel