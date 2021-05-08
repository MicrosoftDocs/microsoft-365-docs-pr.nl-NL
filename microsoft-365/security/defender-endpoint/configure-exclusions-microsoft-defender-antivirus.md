---
title: Uitsluitingen instellen voor Antivirusscans van Microsoft Defender
description: U kunt uitsluiten dat bestanden (inclusief bestanden die zijn gewijzigd door bepaalde processen) en mappen worden gescand door Microsoft Defender Antivirus. Valideer uw uitsluitingen met PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 7065aa7cd1975b2f5a38e79da8618ba3efdcdac5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275118"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>Uitsluitingen configureren en valideren voor Antivirusscans van Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

U kunt bepaalde bestanden, mappen, processen en proces geopende bestanden uitsluiten van Microsoft Defender Antivirus-scans. Dergelijke uitsluitingen zijn van toepassing [op geplande scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [scans](run-scan-microsoft-defender-antivirus.md)op aanvraag en altijd realtime bescherming [en monitoring](configure-real-time-protection-microsoft-defender-antivirus.md). Uitsluitingen voor proces geopende bestanden zijn alleen van toepassing op realtime beveiliging.

## <a name="configure-and-validate-exclusions"></a>Uitsluitingen configureren en valideren

Zie het volgende om uitsluitingen te configureren en te valideren:

- [Uitsluitingen configureren en valideren op basis van bestandsnaam, extensie en maplocatie.](configure-extension-file-exclusions-microsoft-defender-antivirus.md) U kunt bestanden uitsluiten van Microsoft Defender Antivirus-scans op basis van de bestandsextensie, bestandsnaam of locatie.

- [Uitsluitingen configureren en valideren voor bestanden die door processen zijn geopend.](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md) U kunt bestanden uitsluiten van scans die door een bepaald proces zijn geopend.

## <a name="recommendations-for-defining-exclusions"></a>Aanbevelingen voor het definiëren van uitsluitingen

> [!IMPORTANT]
> Microsoft Defender Antivirus bevat veel automatische uitsluitingen op basis van bekende gedragingen van het besturingssysteem en normale beheerbestanden, zoals bestanden die worden gebruikt in ondernemingsbeheer, databasebeheer en andere ondernemingsscenario's en -situaties.  
> 
> Als u uitsluitingen definieert, wordt de beveiliging van Microsoft Defender Antivirus verlaagd. U moet altijd de risico's evalueren die zijn gekoppeld aan het implementeren van uitsluitingen en u moet alleen bestanden uitsluiten die u zeker weet dat ze niet schadelijk zijn.

Houd rekening met de volgende punten wanneer u uitsluitingen definieert:  

- Uitsluitingen zijn technisch gezien een beschermingsgat. Houd altijd rekening met risico's bij het definiëren van uitsluitingen. Andere risicobeperking kan net zo eenvoudig zijn als ervoor zorgen dat de uitgesloten locatie beschikt over de juiste toegangscontrolelijsten (ACL's), auditbeleid, wordt verwerkt door een up-to-date software, enzovoort.

- Controleer de uitsluitingen regelmatig. Controleer de risico's opnieuw en dwing deze opnieuw af als onderdeel van het controleproces.

- Vermijd het definiëren van uitsluitingen die proactief willen zijn. Sluit bijvoorbeeld iets niet uit omdat u denkt dat het in de toekomst een probleem kan zijn. Gebruik uitsluitingen alleen voor specifieke problemen, zoals die met betrekking tot prestaties of toepassingscompatibiliteit die uitsluitingen kunnen beperken.

- Controleer de wijzigingen in de uitsluitingslijst. De beveiligingsbeheerder moet voldoende context behouden waarom een bepaalde uitsluiting is toegevoegd. U moet een antwoord kunnen geven met specifieke redenering waarom een bepaald pad is uitgesloten.

## <a name="related-articles"></a>Verwante artikelen

- [Microsoft Defender Antivirus-uitsluitingen op Windows Server 2016](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Veelvoorkomende fouten bij het definiëren van uitsluitingen voorkomen](common-exclusion-mistakes-microsoft-defender-antivirus.md)
