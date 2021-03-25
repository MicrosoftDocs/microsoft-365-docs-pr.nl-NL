---
title: Ondersteunde API's van Microsoft Defender Advanced Threat Protection
description: Meer informatie over de specifieke responsgerelateerde Microsoft Defender Advanced Threat Protection API-oproepen.
keywords: antwoord-api's, graph api, ondersteunde api's, actor, waarschuwingen, apparaat, gebruiker, domein, ip, bestand
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: a290c431f6d81b23896ddf77e7c7a47de378de22
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185549"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a>Ondersteunde API's voor Microsoft Defender voor eindpuntquery's 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

Meer informatie over de ondersteunde API-oproepen die u kunt uitvoeren en details, zoals de vereiste aanvraagkoppen en de verwachte reactie van de oproepen.

## <a name="in-this-section"></a>In deze sectie
Onderwerp | Beschrijving
:---|:---
Onderzoekspakket verzamelen | Voer deze API uit om een onderzoekspakket van een apparaat te verzamelen.
Apparaat isoleren | Voer deze API uit om een apparaat van het netwerk te isoleren.
Unisolate-apparaat | Een apparaat uit isolatie verwijderen. 
De uitvoering van code beperken | Voer deze API uit om een aanval te bevatten door schadelijke processen te stoppen. U kunt ook een apparaat vergrendelen en voorkomen dat volgende pogingen van potentieel schadelijke programma's worden uitgevoerd.
Unrestrict code execution | Voer dit uit om de beperking van het toepassingsbeleid terug te draaien nadat u hebt geverifieerd dat het gecompromitteerde apparaat is opgelost.
Antivirusscan uitvoeren | Start op afstand een antivirusscan om malware te identificeren en te herstellen die mogelijk aanwezig is op een gecompromitteerd apparaat.
Bestand stoppen en in quarantaine plaatsen |  Voer deze oproep uit om het uitvoeren van processen, quarantainebestanden en het verwijderen van de persistentie, zoals registersleutels, te stoppen.
Voorbeeld aanvragen | Voer deze oproep uit om een voorbeeld van een bestand op te vragen vanaf een bepaald apparaat. Het bestand wordt verzameld vanaf het apparaat en geüpload naar een veilige opslag.
Bestand blokkeren | Voer deze API uit om verdere verspreiding van een aanval in uw organisatie te voorkomen door potentieel schadelijke bestanden of vermoedelijke malware te verbieden. 
Bestand deblokkeren | Een bestand toestaan dat in de organisatie wordt uitgevoerd met Microsoft Defender Antivirus.
Sas URI-pakket krijgen | Voer deze API uit om een URI te downloaden waarmee u een onderzoekspakket kunt downloaden.
MachineAction-object krijgen | Voer deze API uit om MachineAction-object op te halen.
MachineActions-verzameling ophalen | Voer dit uit om MachineAction-verzameling op te halen.
FileActions-verzameling ophalen | Voer deze API uit om FileActions-verzameling op te halen.
Object FileMachineAction downloaden | Voer deze API uit om FileMachineAction-object op te halen.
FileMachineActions-verzameling ophalen | Voer deze API uit om FileMachineAction-verzameling op te halen.
