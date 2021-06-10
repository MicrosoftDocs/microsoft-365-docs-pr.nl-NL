---
title: Lokale overschrijvingen configureren voor AV-instellingen voor Microsoft Defender
description: Gebruikers in- of uitschakelen van lokaal wijzigende instellingen in Microsoft Defender AV.
keywords: lokaal overschrijven, lokaal beleid, groepsbeleid, gpo, lockdown, samenvoegen, lijsten
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 02/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4a35c6717fd7a1834364df32cf5570c83a5b776e
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274518"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a>Voorkomen of toestaan dat gebruikers lokaal de beleidsinstellingen Microsoft Defender Antivirus wijzigen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Standaard worden Microsoft Defender Antivirus instellingen die via een groepsbeleidsobject worden geïmplementeerd naar de eindpunten in uw netwerk, voorkomen dat gebruikers de instellingen lokaal kunnen wijzigen. U kunt dit in sommige gevallen wijzigen.

Het kan bijvoorbeeld nodig zijn om bepaalde gebruikersgroepen (zoals beveiligingsonderzoekers en bedreigingsonderzoekers) meer controle te geven over afzonderlijke instellingen op de eindpunten die ze gebruiken.

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a>Lokale overschrijvingen configureren voor Microsoft Defender Antivirus instellingen

De standaardinstelling voor dit beleid is **Uitgeschakeld.**

Als ze zijn ingesteld op **Ingeschakeld,** kunnen gebruikers op eindpunten wijzigingen aanbrengen in de bijbehorende instelling met de [Windows-beveiliging-app,](microsoft-defender-security-center-antivirus.md) lokale groepsbeleidsinstellingen en PowerShell-cmdlets (indien van toepassing).

In de volgende tabel vindt u een overzicht van de beleidsinstelling en de configuratie-instructies voor de bijbehorende functie of instelling.

U configureert de volgende instellingen:

1. Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

2. Ga in **groepsbeleidseditor** naar **Computerconfiguratie** en klik op **Beheersjablonen.**

3. Vouw de boom uit **Windows onderdelen > Microsoft Defender Antivirus** en  vervolgens de locatie die is opgegeven in de onderstaande tabel.

4. Dubbelklik op de **beleidsinstelling** zoals aangegeven in de onderstaande tabel en stel de optie in op de gewenste configuratie. Klik **op OK** en herhaal dit voor andere instellingen.

5. Implementeer het groepsbeleidsobject zoals gewoonlijk.

Locatie | Instelling | Artikel
---|---|---|---
KAARTEN | Lokale instelling overschrijven voor rapportage naar Microsoft MAPS configureren | [Cloudbeveiliging inschakelen](enable-cloud-protection-microsoft-defender-antivirus.md)
Quarantaine | Lokale instelling overschrijven configureren voor het verwijderen van items uit de map Quarantaine | [Herstel configureren voor scans](configure-remediation-microsoft-defender-antivirus.md)
Realtime beveiliging | Lokale instelling overschrijven configureren voor het controleren van bestands- en programmaactiviteit op uw computer | [Beveiliging en Microsoft Defender Antivirus altijd ingeschakeld inschakelen en configureren](configure-real-time-protection-microsoft-defender-antivirus.md)
Realtime beveiliging | Lokale instelling overschrijven configureren voor het controleren op activiteiten inkomende en uitgaande bestanden | [Beveiliging en Microsoft Defender Antivirus altijd ingeschakeld inschakelen en configureren](configure-real-time-protection-microsoft-defender-antivirus.md)
Realtime beveiliging | Lokale instelling overschrijven configureren voor het scannen van alle gedownloade bestanden en bijlagen | [Beveiliging en Microsoft Defender Antivirus altijd ingeschakeld inschakelen en configureren](configure-real-time-protection-microsoft-defender-antivirus.md)
Realtime beveiliging | Lokale instelling overschrijven configureren om gedragscontrole in te stellen | [Beveiliging en Microsoft Defender Antivirus altijd ingeschakeld inschakelen en configureren](configure-real-time-protection-microsoft-defender-antivirus.md)
Realtime beveiliging | Lokale instelling overschrijven configureren om realtimebeveiliging in te stellen | [Beveiliging en Microsoft Defender Antivirus altijd ingeschakeld inschakelen en configureren](configure-real-time-protection-microsoft-defender-antivirus.md)
Herstellen | Lokale instelling overschrijven voor het tijdstip van de dag configureren om een geplande volledige scan uit te voeren om herstel te voltooien | [Herstel configureren voor scans](configure-remediation-microsoft-defender-antivirus.md)
Scannen | Lokale instelling overschrijven configureren voor maximumpercentage cpu-gebruik | [Scans configureren en uitvoeren](run-scan-microsoft-defender-antivirus.md)
Scannen | Lokale instelling overschrijven voor planningsscandag configureren | [Geplande scans configureren](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Scannen | Lokale instelling overschrijven configureren voor geplande snelle scantijd | [Geplande scans configureren](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Scannen | Lokale instelling overschrijven configureren voor geplande scantijd | [Geplande scans configureren](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Scannen | Lokale instelling overschrijven configureren voor het scantype dat wordt gebruikt voor een geplande scan | [Geplande scans configureren](scheduled-catch-up-scans-microsoft-defender-antivirus.md)

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a>Configureren hoe lokaal en globaal gedefinieerde lijsten voor het herstellen van bedreigingen en uitsluitingen worden samengevoegd

U kunt ook configureren hoe lokaal gedefinieerde lijsten worden gecombineerd of samengevoegd met globaal gedefinieerde lijsten. Deze instelling is van toepassing [op uitsluitingslijsten](configure-exclusions-microsoft-defender-antivirus.md), [opgegeven herstellijsten](configure-remediation-microsoft-defender-antivirus.md)en [beperking van het oppervlak van de aanval](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction).

Lijsten die zijn geconfigureerd in lokaal groepsbeleid en de Windows-beveiliging-app, worden standaard samengevoegd met lijsten die zijn gedefinieerd door het juiste groepsbeleidsobject dat u in uw netwerk hebt geïmplementeerd. Als er conflicten zijn, heeft de globaal gedefinieerde lijst voorrang.

U kunt deze instelling uitschakelen om ervoor te zorgen dat alleen globaal gedefinieerde lijsten (zoals lijsten van geïmplementeerde GPOs) worden gebruikt.

### <a name="use-group-policy-to-disable-local-list-merging"></a>Groepsbeleid gebruiken om het samenvoegen van lokale lijst uit te schakelen

1. Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

2. Ga in **groepsbeleidseditor** naar **Computerconfiguratie** en klik op **Beheersjablonen.**

3. Vouw de boom uit Windows **onderdelen > Microsoft Defender Antivirus.**

4. Dubbelklik op **Gedrag van lokale beheerders samenvoegen configureren voor lijsten** en stel de optie in op **Uitgeschakeld.** Klik op **OK**.

> [!NOTE]
> Als u het samenvoegen van lokale lijst uit schakelt, worden de instellingen voor beheerde maptoegang overgeslagen. Ook worden beveiligde mappen of toegestane apps die door de lokale beheerder zijn ingesteld, overgeslagen. Zie Een geblokkeerde app toestaan in Windows-beveiliging voor meer informatie over instellingen [voor beheerde maptoegang.](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security)

## <a name="related-topics"></a>Verwante onderwerpen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Interactie tussen eindgebruikers configureren met Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)