---
title: Een aangepast geleidelijk implementatieproces maken voor Microsoft Defender-updates
description: Meer informatie over het gebruik van ondersteunde hulpprogramma's om een aangepast geleidelijk implementatieproces voor updates te maken
keywords: updateprogramma's, gpo, intune, mdm, microsoft endpoint manager, beleid, powershell
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
ms.openlocfilehash: a7a560cb33190105f8df5922e04aeada4d75f398
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290037"
---
# <a name="create-a-custom-gradual-rollout-process-for-microsoft-defender-updates"></a>Een aangepast geleidelijk implementatieproces maken voor Microsoft Defender-updates

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> Voor deze functionaliteit Microsoft Defender Antivirus versie 4.18.2106.X of hoger vereist.

Als u uw eigen aangepaste, geleidelijke implementatieprocedure voor Defender-updates wilt maken, kunt u Groepsbeleid, Microsoft Endpoint Manager en PowerShell gebruiken.

In de volgende tabel vindt u de beschikbare instellingen voor groepsbeleid voor het configureren van updatekanalen:

| Titel instellen  | Omschrijving  | Locatie  |
|:---|:---|:---|
| Selecteer geleidelijk het update-kanaal voor het maandelijkse Microsoft Defender-platform  | Schakel dit beleid in om op te geven wanneer apparaten microsoft Defender-platformupdates ontvangen tijdens de maandelijkse geleidelijke implementatie. Bètakanaal: Apparaten die zijn ingesteld op dit kanaal, ontvangen als eerste nieuwe updates. Selecteer Beta-kanaal om deel te nemen aan het identificeren en rapporteren van problemen met Microsoft. Apparaten in het Windows Insider-programma zijn standaard geabonneerd op dit kanaal. Alleen voor gebruik in (handmatige) testomgevingen en een beperkt aantal apparaten.  <br><br>  Current Channel (Preview): Apparaten die zijn ingesteld op dit kanaal, worden het vroegst tijdens de maandelijkse, geleidelijke releasecyclus bijgewerkt. Voorgesteld voor pre-productie-/validatieomgevingen.  <br><br>  Huidig kanaal (gefaseerd): Apparaten worden updates aangeboden na de maandelijkse, geleidelijke releasecyclus. Voorgesteld om toe te passen op een klein, representatief deel van uw productiepopulatie (~10%).  <br><br>  Huidig kanaal (breed): Apparaten worden alleen updates aangeboden nadat de geleidelijke releasecyclus is voltooid. Voorgesteld om toe te passen op een breed scala aan apparaten in uw productiepopulatie (~10-100%).  <br><br>   Als u dit beleid uit- of niet configureert, blijft het apparaat automatisch up-to-date tijdens de geleidelijke releasecyclus. Geschikt voor de meeste apparaten.  | Windows Onderdelen\Microsoft Defender Antivirus  |
| Selecteer een geleidelijk updatekanaal voor de maandelijkse Engine Update van Microsoft Defender  | Schakel dit beleid in om op te geven wanneer apparaten microsoft Defender-motorupdates ontvangen tijdens de maandelijkse geleidelijke implementatie.  <br><br>  Bètakanaal: Apparaten die zijn ingesteld op dit kanaal, ontvangen als eerste nieuwe updates. Selecteer Beta-kanaal om deel te nemen aan het identificeren en rapporteren van problemen met Microsoft. Apparaten in het Windows Insider-programma zijn standaard geabonneerd op dit kanaal. Alleen voor gebruik in (handmatige) testomgevingen en een beperkt aantal apparaten.  <br><br>  Current Channel (Preview): Apparaten die zijn ingesteld op dit kanaal, worden het vroegst tijdens de maandelijkse, geleidelijke releasecyclus bijgewerkt. Voorgesteld voor pre-productie-/validatieomgevingen.  <br><br>  Huidig kanaal (gefaseerd): Apparaten worden updates aangeboden na de maandelijkse, geleidelijke releasecyclus. Voorgesteld om toe te passen op een klein, representatief deel van uw productiepopulatie (~10%).  <br><br>  Huidig kanaal (breed): Apparaten worden alleen updates aangeboden nadat de geleidelijke releasecyclus is voltooid. Voorgesteld om toe te passen op een breed scala aan apparaten in uw productiepopulatie (~10-100%).  <br><br>  Als u dit beleid uit- of niet configureert, blijft het apparaat automatisch up-to-date tijdens de geleidelijke releasecyclus. Geschikt voor de meeste apparaten.  | Windows Onderdelen\Microsoft Defender Antivirus  |
| Het geleidelijk uitrolkanaal voor dagelijkse definitieupdates van Microsoft Defender selecteren  | Schakel dit beleid in om op te geven wanneer apparaten Definitie-updates van Microsoft Defender ontvangen tijdens de dagelijkse geleidelijke implementatie. <br><br> Current Channel (Gefaseerd): Apparaten worden na de releasecyclus updates aangeboden. Voorgesteld om toe te passen op een klein, representatief deel van de productiepopulatie (~10%). <br><br>   Huidig kanaal (breed): Apparaten worden alleen updates aangeboden nadat de geleidelijke releasecyclus is voltooid. Voorgesteld om toe te passen op een breed scala aan apparaten in uw productiepopulatie (~10-100%). <br><br>   Als u dit beleid uit- of niet configureert, blijft het apparaat automatisch up-to-date tijdens de dagelijkse releasecyclus. Geschikt voor de meeste apparaten.  | Windows Onderdelen\Microsoft Defender Antivirus  |
| Geleidelijke implementatie van Microsoft Defender-updates uitschakelen  | Schakel dit beleid in om de geleidelijke implementatie van Defender-updates uit te schakelen. <br><br> Huidig kanaal (breed): Apparaten die zijn ingesteld op dit kanaal, worden gedurende de geleidelijke releasecyclus als laatste bijgewerkt. Het beste voor datacenterapparaten die slechts beperkte updates ontvangen. <br><br> Opmerking: Deze instelling is van toepassing op zowel maandelijkse als dagelijkse Defender-updates en overteert alle eerder geconfigureerde kanaalselecties voor platform- en motorupdates. <br><br> Als u dit beleid uit- of niet configureert, blijft het apparaat in huidig kanaal (standaard), tenzij anders is opgegeven in specifieke kanalen voor platform- en motorupdates. Blijf automatisch up-to-date tijdens de geleidelijke releasecyclus. Geschikt voor de meeste apparaten.  | Windows Onderdelen\Microsoft Defender Antivirus  |

## <a name="group-policy"></a>Groepsbeleid

> [!NOTE]
> Een bijgewerkte Defender ADMX-sjabloon wordt samen met de 21H2-release van de Windows 10. Er is een niet-gelokaliseerde versie beschikbaar om te downloaden op https://github.com/microsoft/defender-updatecontrols .

U kunt [Groepsbeleid gebruiken om](/windows/win32/srvnodes/group-policy?redirectedfrom=MSDN)uw Microsoft Defender Antivirus   eindpunten te configureren en te beheren.

In het algemeen kunt u de volgende procedure gebruiken voor het configureren of wijzigen van Microsoft Defender Antivirus groepsbeleidsinstellingen:

1. Open op uw groepsbeleidsbeheercomputer de console Groepsbeleidsbeheer  **,** klik met de rechtermuisknop op het groepsbeleidsobject **dat** u wilt configureren en klik op  **Bewerken.**

2. Ga met de Editor voor groepsbeleidsbeheer naar **Computerconfiguratie.**

3. Klik **op Beheersjablonen.**

4. Vouw de boom uit Windows **onderdelen > Microsoft Defender Antivirus.**

5. Vouw de sectie uit ****(ook wel locatie genoemd in de tabel in dit onderwerp) met de instelling die u wilt configureren, dubbelklik op de instelling om deze te openen en wijzig de   configuratie.

6. [Implementeer het bijgewerkte GPO zoals u dat normaal doet.](https://msdn.microsoft.com/library/ee663280(v=vs.85).aspx)

## <a name="intune"></a>Intune

Volg de instructies in onderstaande koppeling om een aangepast beleid te maken in Intune:

[Aangepaste instellingen toevoegen voor Windows 10 apparaten in Microsoft Intune - Azure \| Microsoft Docs](/mem/intune/configuration/custom-settings-windows-10)

Zie Defender CSP voor meer informatie over de Defender [CSP's](/windows/client-management/mdm/defender-csp)die worden gebruikt voor de geleidelijke uitrol.

## <a name="powershell"></a>PowerShell

Gebruik de `Set-MpPreference` cmdlet om de implementatie van de geleidelijke updates te configureren.

Gebruik de volgende parameters:

```powershell
Set-MpPreference
-PlatformUpdatesChannel Beta|Preview|Staged|Broad|NotConfigured
-EngineUpdatesChannel Beta|Preview|Staged|Broad|NotConfigured
-DisableGradualRelease True|False
-SignaturesUpdatesChannel Staged|Broad|NotConfigured
```

Voorbeeld:

Gebruik `Set-MpPreference -PlatformUpdatesChannel Beta` dit programma om platformupdates te configureren om vanuit het bètakanaal te komen.

Zie Set-MpPreference (Defender) voor meer informatie over de parameters en hoe u [deze configureert | Microsoft Docs](/powershell/module/defender/set-mppreference).
