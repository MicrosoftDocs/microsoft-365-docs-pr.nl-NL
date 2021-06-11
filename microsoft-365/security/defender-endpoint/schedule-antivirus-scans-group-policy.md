---
title: Antivirusscans plannen met groepsbeleid
description: Groepsbeleid gebruiken om antivirusscans in te stellen
keywords: quick scan, full scan, schedule, group policy, antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 6f6018ec8b514234ab4f98e3d5416b472ff88739
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879692"
---
# <a name="schedule-antivirus-scans-using-group-policy"></a>Antivirusscans plannen met groepsbeleid

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

In dit artikel wordt beschreven hoe u geplande scans configureert met groepsbeleid. Zie Geplande snelle of volledige Microsoft Defender Antivirus configureren voor meer informatie over planningsscans [en scantypen.](schedule-antivirus-scans.md) 

## <a name="configure-antivirus-scans-using-group-policy"></a>Antivirusscans configureren met groepsbeleid

1. Ga op uw groepsbeleidsbeheercomputer in de groepsbeleidseditor naar **Beheersjablonen** voor computerconfiguratie Windows  >    >  **Onderdelen**  >  **Microsoft Defender Antivirus**  >  **scannen.**

2. Klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **bewerken.**

3. Geef instellingen op voor het groepsbeleidsobject en selecteer **OK.** 

4. Herhaal stap 1-4 voor elke instelling die u wilt configureren.

5. Implementeer het groepsbeleidsobject zoals u dat normaal doet. Zie Een groepsbeleidsobject maken als u hulp nodig hebt bij [groepsbeleidsobjecten.](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)

> [!TIP]
> Zie Beheren [wanneer beveiligingsupdates](manage-protection-update-schedule-microsoft-defender-antivirus.md) moeten worden gedownload en toegepast en Voorkomen of toestaan dat gebruikers beleidsinstellingen lokaal [kunnen](configure-local-policy-overrides-microsoft-defender-antivirus.md) wijzigen.

## <a name="group-policy-settings-for-scheduling-scans"></a>Groepsbeleidsinstellingen voor planningsscans

| Locatie | Instelling | Beschrijving | Standaardinstelling (indien niet geconfigureerd) |
|:---|:---|:---|:---|
| Scannen | Het scantype opgeven dat moet worden gebruikt voor een geplande scan | Snelle scan |
| Scannen | De dag van de week opgeven om een geplande scan uit te voeren | Geef de dag (of nooit) op om een scan uit te voeren. | Nooit |
| Scannen | De tijd van de dag opgeven om een geplande scan uit te voeren | Geef het aantal minuten na middernacht op (bijvoorbeeld **60** voor 01.00 uur). | 02:00 uur |
| Hoofdmap | Geplande taaktijden willekeurig maken |In Microsoft Defender Antivirus de begintijd van de scan willekeurig instellen op een interval van 0 tot 4 uur. <p>In [SCEP](/mem/intune/protect/certificates-scep-configure)kunt u een willekeurige scan instellen op een interval plus of min 30 minuten. Dit kan handig zijn in virtuele machines of VDI-implementaties. | Ingeschakeld |

## <a name="group-policy-settings-for-scheduling-scans-for-when-an-endpoint-is-not-in-use"></a>Groepsbeleidsinstellingen voor het plannen van scans voor wanneer een eindpunt niet wordt gebruikt

| Locatie | Instelling | Beschrijving | Standaardinstelling (indien niet geconfigureerd) |
|:---|:---|:---|:---|
| Scannen | De geplande scan alleen starten wanneer de computer is aan, maar niet in gebruik is | Geplande scans worden niet uitgevoerd, tenzij de computer is aan maar niet in gebruik is | Ingeschakeld |

> [!NOTE]
> Wanneer u scans inplant voor tijden waarin eindpunten niet worden gebruikt, wordt de configuratie voor het beperken van cpu's niet door scans uitgevoerd en wordt optimaal gebruik gemaakt van de bronnen die beschikbaar zijn om de scan zo snel mogelijk te voltooien.

## <a name="group-policy-settings-for-scheduling-remediation-required-scans"></a>Groepsbeleidsinstellingen voor het plannen van herstel-vereiste scans

| Locatie | Instelling | Beschrijving | Standaardinstelling (indien niet geconfigureerd) |
|---|---|---|---|
| Herstellen | Geef de dag van de week op om een geplande volledige scan uit te voeren om herstel te voltooien | Geef de dag (of nooit) op om een scan uit te voeren. | Nooit |
| Herstellen | Geef de tijd van de dag op om een geplande volledige scan uit te voeren om de hersteltijd te voltooien | Geef het aantal minuten na middernacht op (bijvoorbeeld **60** voor 01.00 uur) | 02:00 uur |

## <a name="group-policy-settings-for-scheduling-daily-scans"></a>Groepsbeleidsinstellingen voor het plannen van dagelijkse scans

| Locatie | Instelling | Beschrijving | Standaardinstelling (indien niet geconfigureerd) |
|:---|:---|:---|:---|
| Scannen | Geef het interval op om snelle scans per dag uit te voeren | Geef op hoeveel uren moeten worden verstreken vóór de volgende snelle scan. Als u bijvoorbeeld elke twee uur wilt uitvoeren, typt u **2**, voor één keer per dag, voert u **24 in.** Voer **0 in** om nooit een dagelijkse quick scan uit te voeren. | Nooit |
| Scannen | De tijd voor een dagelijkse snelle scan opgeven | Geef het aantal minuten na middernacht op (bijvoorbeeld **60** voor 01.00 uur) | 02:00 uur |

## <a name="group-policy-settings-for-scheduling-scans-after-protection-updates"></a>Groepsbeleidsinstellingen voor het plannen van scans na beveiligingsupdates

| Locatie | Instelling | Beschrijving | Standaardinstelling (indien niet geconfigureerd)|
|:---|:---|:---|:---|
| Handtekeningupdates | Scannen in-/uit-/uit-2014 in- en | Er wordt direct na het downloaden van een nieuwe beveiligingsupdate een scan uitgevoerd | Ingeschakeld |

