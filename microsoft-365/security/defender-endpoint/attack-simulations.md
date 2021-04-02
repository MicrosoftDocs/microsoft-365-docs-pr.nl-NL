---
title: Microsoft Defender ATP ervaren via gesimuleerde aanvallen
description: Voer de meegeleverde scenariosimulaties uit om te ervaren hoe Microsoft Defender ATP inbreuken kan detecteren, onderzoeken en beantwoorden.
keywords: wdatp, test, scenario, aanval, simulatie, gesimuleerd, doe-het-zelf, Microsoft Defender voor eindpunt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: b3fb862ac6e845ed4a3f5b72bae902f00c125b53
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498306"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a>Microsoft Defender voor eindpunt ervaren via gesimuleerde aanvallen 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- Meer informatie over de nieuwste verbeteringen in Microsoft Defender ATP: [Wat is er nieuw in Defender voor Eindpunt?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).
>- Defender for Endpoint heeft in de recente MITRE-evaluatie de toonaangevende mogelijkheden voor optica en detectie gedemonstreerd. Lees: [Inzichten uit de MITRE-ATT-&op CK gebaseerde evaluatie](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

Mogelijk wilt u Defender voor Eindpunt ervaren voordat u meer dan een paar apparaten aan boord van de service aan boord gaat. Hiervoor kunt u gecontroleerde aanvalssimulaties uitvoeren op een paar testapparaten. Nadat u de gesimuleerde aanvallen hebt uitgevoerd, kunt u bekijken hoe in Defender voor Eindpunt schadelijke activiteiten worden aan het licht gekomen en kunt u bekijken hoe dit een efficiënte reactie mogelijk maakt.

## <a name="before-you-begin"></a>Voordat u begint

Als u een van de meegeleverde simulaties wilt uitvoeren, hebt u ten minste [één apparaat met onboarding nodig.](onboard-configure.md) 

Lees het walkthrough-document dat bij elk aanvalsscenario wordt geleverd. Elk document bevat besturingssysteem- en toepassingsvereisten, evenals gedetailleerde instructies die specifiek zijn voor een aanvalsscenario.

## <a name="run-a-simulation"></a>Een simulatie uitvoeren

1. Selecteer **in**  >  **Help-& zelfstudies** welke van de beschikbare aanvalsscenario's u wilt simuleren:

   - **Scenario 1: Document dropt backdoor-** simuleert de bezorging van een sociaal ontworpen lokmiddeldocument. Het document start een speciaal ontworpen backdoor die aanvallers controle geeft.

   - **Scenario 2: PowerShell-script in bestandsloze** aanval : simuleert een bestandsloze aanval die afhankelijk is van PowerShell, waarbij de surface reduction van de aanval wordt belicht en de detectie van schadelijke geheugenactiviteit op apparaten wordt gedetecteerd.
    
   - **Scenario 3: Geautomatiseerde reactie** op incidenten : activeert automatisch onderzoek, waarmee automatisch wordt gejaagd naar en herstelt van inbreukartefacten om de reactiecapaciteit voor incidenten te vergroten.

2. Download en lees het bijbehorende doorloopdocument dat bij het geselecteerde scenario is geleverd.

3. Download het simulatiebestand of kopieer het simulatiescript door naar  >  **Help-& navigeren.** U kunt ervoor kiezen om het bestand of script te downloaden op het testapparaat, maar dit is niet verplicht.

4. Voer het simulatiebestand of script uit op het testapparaat, zoals wordt geïnstrueerd in het doorloopdocument.

> [!NOTE]
> Simulatiebestanden of scripts bootsen aanvalsactiviteit na, maar zijn in feite goedaardig en kunnen het testapparaat niet schaden of in gevaar brengen.
> 
> 
> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a>Verwante onderwerpen

- [Onboard-apparaten](onboard-configure.md)
- [Onboarden Windows 10-apparaten](configure-endpoints.md)
