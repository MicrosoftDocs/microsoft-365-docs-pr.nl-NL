---
title: Het geleidelijke implementatieproces voor Microsoft Defender-updates beheren
description: Meer informatie over het geleidelijke updateproces en besturingselementen
keywords: update, updateproces, besturingselementen, release
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f5db08e4eb98dd3fe6f7e8a84fb0c49e889fb73f
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809248"
---
#  <a name="manage-the-gradual-rollout-process-for-microsoft-defender-updates"></a>Het geleidelijke implementatieproces voor Microsoft Defender-updates beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)


Het is belangrijk om ervoor te zorgen dat clientonderdelen up-to-date zijn om essentiële beveiligingsfuncties te bieden en aanvallen te voorkomen.

De mogelijkheden worden geleverd via verschillende onderdelen: 

- [Endpoint Detection & Response](overview-endpoint-detection-response.md) 
- [Beveiliging van de volgende generatie](microsoft-defender-antivirus-in-windows-10.md#microsoft-defender-antivirus-your-next-generation-protection) met door de cloud [geleverde beveiliging](cloud-protection-microsoft-defender-antivirus.md) 
- [Surface Reduction aanvallen](overview-attack-surface-reduction.md)

Updates worden maandelijks uitgebracht via een geleidelijk releaseproces. Met dit proces kunt u vroegtijdige foutdetectie inschakelen om de impact te vangen terwijl deze optreedt en deze snel aan te pakken vóór een grotere implementatie. 

> [!NOTE]
> Zie Updates voor definities plannen Microsoft Defender Antivirus definities - Windows beveiligingsupdates | voor meer informatie over het beheer van dagelijkse [definitie-updates | Microsoft Docs](manage-protection-update-schedule-microsoft-defender-antivirus.md). Definitie-updates zorgen ervoor dat de beveiliging van de volgende generatie kan worden beschermd tegen nieuwe bedreigingen, zelfs als beveiliging in de cloud niet beschikbaar is voor het eindpunt.

## <a name="microsoft-gradual-rollout-model"></a>Geleidelijk uitrolmodel van Microsoft

Het volgende geleidelijke uitrolmodel wordt gevolgd:

1. De eerste release gaat uit naar beta-kanaalabonnees.
2. Na validatie, feedback en oplossingen starten we het geleidelijke implementatieproces op een beperkter manier en gaan we eerst naar Preview-kanaalabonnees.
3. Vervolgens gaan we verder met het vrijgeven van de update voor de rest van de wereldbevolking, met een schaal van 10-100%.

Onze technici houden de impact voortdurend in de gaten en escaleren eventuele problemen om zo nodig een oplossing te maken.

## <a name="how-to-customize-your-internal-deployment-process"></a>Uw interne implementatieproces aanpassen

Als uw machines Defender-updates ontvangen van Windows Update, kan de geleidelijke uitrol ertoe leiden dat sommige van uw machines sneller Defender-updates ontvangen dan andere. In de volgende sectie wordt uitgelegd hoe u een strategie kunt definiëren waarmee automatische updates anders kunnen worden gestroomd naar specifieke groepen apparaten door gebruik te maken van de configuratie van het updatekanaal.

> [!NOTE]
> Wanneer u een geleidelijke release plant, moet u altijd een selectie van apparaten hebben die zijn geabonneerd op de preview- en gefaseerd kanalen. Dit biedt uw organisatie en Microsoft de mogelijkheid om specifieke problemen met uw omgeving te voorkomen of op te lossen.

Voor machines die updates ontvangen via bijvoorbeeld Windows Server Update Services (WSUS) of Microsoft Endpoint Configuration Manager (MECM), zijn er meer opties beschikbaar voor alle Windows-updates, inclusief opties voor Microsoft Defender voor Eindpunt.

- Lees meer over het gebruik van een oplossing zoals WSUS, MECM voor het beheren van de distributie en toepassing van updates bij Updates van Microsoft Defender Antivirus beheren en basislijnen toepassen - Windows [beveiligings | Microsoft Docs](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates).

## <a name="update-channels-for-monthly-updates"></a>Kanalen bijwerken voor maandelijkse updates

U kunt een computer toewijzen aan een updatekanaal om de cadans te definiëren waarin een computer maandelijkse engine- en platformupdates ontvangt.

Zie Een aangepast geleidelijk implementatieproces maken voor [Microsoft Defender-updates](configure-updates.md)voor meer informatie over het configureren van updates.

De volgende updatekanalen zijn beschikbaar:

| Kanaalnaam  | Beschrijving  | Toepassing  |
|-|-|-|
| Beta-kanaal - Prerelease  | Updates testen vóór anderen  | Apparaten die zijn ingesteld op dit kanaal, ontvangen als eerste nieuwe maandelijkse updates. Selecteer Beta-kanaal om deel te nemen aan het identificeren en rapporteren van problemen met Microsoft. Apparaten in het Windows Insider-programma zijn standaard geabonneerd op dit kanaal. Alleen voor gebruik in testomgevingen.  |
| Huidig kanaal (voorbeeld)  | Huidige kanaalupdates **eerder downloaden tijdens** de geleidelijke release  | Apparaten die zijn ingesteld op dit kanaal, worden het vroegst tijdens de geleidelijke releasecyclus bijgewerkt. Voorgesteld voor pre-productie-/validatieomgevingen.  |
| Huidig kanaal (gefaseerd)  | Updates voor huidig kanaal later downloaden tijdens de geleidelijke release  | Apparaten worden later tijdens de geleidelijke releasecyclus updates aangeboden. Voorgesteld om toe te passen op een klein, representatief deel van de apparaatpopulatie (~10%).  |
| Huidig kanaal (breed) | Updates ontvangen aan het einde van de geleidelijke release  | Apparaten worden alleen updates aangeboden nadat de geleidelijke releasecyclus is voltooid. Voorgesteld om toe te passen op een breed scala aan apparaten in uw productiepopulatie (~10-100%).  |
| (standaard)  |   | Als u dit beleid uit- of niet configureert, blijft het apparaat in huidig kanaal (standaard): Blijf automatisch up-to-date tijdens de geleidelijke releasecyclus. Geschikt voor de meeste apparaten.  |

### <a name="update-channels-for-daily-definition-updates"></a>Kanalen bijwerken voor dagelijkse definitie-updates

U kunt een computer toewijzen aan een updatekanaal om de cadans te definiëren waarin een computer dagelijkse definitie-updates ontvangt.
  
| Kanaalnaam  | Beschrijving  | Toepassing  |
|-|-|-|
| Huidig kanaal (gefaseerd)  | Updates voor huidig kanaal later downloaden tijdens de geleidelijke release  | Apparaten worden later tijdens de geleidelijke releasecyclus updates aangeboden. Voorgesteld om toe te passen op een klein, representatief deel van de apparaatpopulatie (~10%).  |
| Huidig kanaal (breed) | Updates ontvangen aan het einde van de geleidelijke release  | Apparaten worden na de geleidelijke releasecyclus updates aangeboden. Het beste voor datacenterapparaten die slechts beperkte updates ontvangen. Opmerking: deze instelling is van toepassing op alle Defender-updates.  |
| (standaard)  |   | Als u dit beleid uit- of niet configureert, blijft het apparaat in huidig kanaal (standaard): Blijf automatisch up-to-date tijdens de geleidelijke releasecyclus. Geschikt voor de meeste apparaten  |

> [!NOTE]
> Als u een update naar de nieuwste handtekening wilt forcen in plaats van gebruik te maken van de vertraging, moet u dit beleid eerst verwijderen.

## <a name="update-guidance"></a>Richtlijnen bijwerken

In de meeste gevallen is de aanbevolen configuratie bij het Windows update om eindpunten toe te staan om maandelijkse Defender-updates te ontvangen en toe te passen wanneer ze binnenkomen. Dit biedt de beste balans tussen beveiliging en mogelijke gevolgen die samenhangen met de wijzigingen die ze kunnen introduceren.

Voor omgevingen waarin een meer gecontroleerde geleidelijke uitrol van automatische Defender-updates nodig is, kunt u een benadering overwegen met implementatiegroepen:

1. Neem deel aan het Windows Insider-programma of wijs een groep apparaten toe aan het bètakanaal.
2. Wijs een testgroep aan die zich opteert voor Preview-kanaal, meestal validatieomgevingen, om nieuwe updates eerder te ontvangen.
3. Wijs een groep machines aan die updates later ontvangen tijdens de geleidelijke implementatie van gefaseerd kanaal. Meestal is dit een representatieve ~10% van de populatie.
4. Wijs een groep machines aan die updates ontvangen nadat de geleidelijke releasecyclus is voltooid. Dit zijn meestal belangrijke productiesystemen.

Voor de rest van de apparaten is de standaardinstelling om nieuwe updates te ontvangen wanneer deze tijdens de geleidelijke implementatie van Microsoft binnenkomen en er is geen verdere configuratie vereist. 

Dit model gebruiken:
- Hiermee kunt u vroege versies testen voordat ze een productieomgeving bereiken 
- Zorg ervoor dat de productieomgeving nog steeds regelmatig updates ontvangt en dat de beveiliging tegen kritieke bedreigingen wordt gegarandeerd.

## <a name="management-tools"></a>Beheerprogramma's
Als u uw eigen aangepaste, geleidelijke implementatieprocedure voor maandelijkse updates wilt maken, kunt u de volgende hulpprogramma's gebruiken:

- Groepsbeleid
- Microsoft Endpoint Manager
- PowerShell

Zie Een aangepast geleidelijk implementatieproces maken voor [Microsoft Defender-updates](configure-updates.md)voor meer informatie over het gebruik van deze hulpmiddelen.
