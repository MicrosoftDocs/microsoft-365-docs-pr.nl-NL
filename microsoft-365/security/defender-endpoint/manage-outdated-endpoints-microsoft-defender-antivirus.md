---
title: Microsoft Defender AV-beveiligingsupdates toepassen op verouderd eindpunten
description: Bepaal wanneer en hoe updates moeten worden toegepast voor eindpunten die al een tijdje niet zijn bijgewerkt.
keywords: updates, beveiliging, verouderd, verouderd, oud, catch-up
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b141c9b745e560b3c2236a9d073a7b2f3500623c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926041"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a>Microsoft Defender Antivirus-updates en scans beheren voor verouderde eindpunten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus kunt u bepalen hoe lang een eindpunt een update kan voorkomen of hoeveel scans het kan missen voordat het moet worden bijgewerkt en gescand. Dit is vooral handig in omgevingen waarin apparaten niet vaak zijn verbonden met een bedrijfs- of extern netwerk of apparaten die niet dagelijks worden gebruikt.

Een werknemer die bijvoorbeeld een bepaalde pc gebruikt, heeft drie dagen pauze en kan zich in die periode niet aanmelden bij zijn of haar pc.

Wanneer de gebruiker weer aan het werk gaat en zich aanmeldt bij zijn of haar pc, Microsoft Defender Antivirus de meest recente beveiligingsupdates direct controleren en downloaden en een scan uitvoeren.

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a>Inhaalbeveiligingsupdates instellen voor eindpunten die al een tijdje niet zijn bijgewerkt

Als Microsoft Defender Antivirus beveiligingsupdates voor een bepaalde periode niet hebt gedownload, kunt u deze instellen om de nieuwste update automatisch te controleren en te downloaden bij de volgende keer dat u zich aanmeldt. Dit is handig als u automatische updatedownloads bij het opstarten globaal [hebt uitgeschakeld.](manage-event-based-updates-microsoft-defender-antivirus.md)

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a>Configuration Manager gebruiken om inhaalbeveiligingsupdates te configureren

1.  Open op Microsoft Endpoint Manager console het antimalwarebeleid dat u wilt wijzigen (klik **op** Activa en naleving in het navigatiedeelvenster aan de linkerkant en vouw de structuur uit naar Overzicht  >  **Endpoint Protection**  >  **Antimalware-beleid**)

2.  Ga naar de **sectie Beveiligingsinformatie-updates** en configureer de volgende instellingen:

    1. Stel **Een beveiligingsintelligentie-update in als de clientcomputer offline is voor** meer dan twee opeenvolgende geplande updates voor **Ja.**
    2. Geef voor  **If Configuration Manager** als bron voor beveiligingsinformatieupdates... de uren op waarvoor de beveiligingsupdates die door Configuration Manager worden geleverd, als verouderd moeten worden beschouwd. Hierdoor wordt de volgende updatelocatie gebruikt op basis van de gedefinieerde [fallbackbronorder.](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)

3. Klik op **OK**.

4.  [Implementeer het bijgewerkte beleid zoals gewoonlijk.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a>Groepsbeleid gebruiken om de functie voor het bijwerken van bijvangst in te stellen en te configureren

1. Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

2. Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**

3. Klik **op Beleid** en vervolgens op **Beheersjablonen.**

4. Vouw de structuur uit Windows **onderdelen > Microsoft Defender Antivirus > Handtekeningupdates.**

5. Dubbelklik op **de instelling Het aantal** dagen definiëren waarna een inhaalupdate voor beveiligingsinformatie vereist is en stel de optie in op **Ingeschakeld.** Voer het aantal dagen in waarop u wilt dat Microsoft Defender AV de meest recente beveiligingsupdate controleert en downloadt.

6. Klik op **OK**.

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a>PowerShell-cmdlets gebruiken om inhaalbeveiligingsupdates te configureren

Gebruik de volgende cmdlets:

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a>Gebruik Windows Management Instruction (WMI) om inhaalbeveiligingsupdates te configureren

Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:

```WMI
SignatureUpdateCatchupInterval
```

Zie het volgende voor meer informatie en toegestane parameters:
- [Windows Defender WMIv2-API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a>Het aantal dagen instellen voordat de beveiliging als verouderd wordt gerapporteerd

U kunt ook het aantal dagen opgeven waarna Microsoft Defender Antivirus wordt beschouwd als oud of verouderd. Na het opgegeven aantal dagen meldt de client zich als verouderd en wordt er een fout weergegeven aan de gebruiker van de pc. Het kan er ook toe leiden dat Microsoft Defender Antivirus probeert een update te downloaden van andere bronnen (op basis van de gedefinieerde [fallbackbronorder),](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)bijvoorbeeld wanneer u MMPC als secundaire bron gebruikt nadat U WSUS of Microsoft Update als eerste bron hebt opgegeven.

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a>Groepsbeleid gebruiken om het aantal dagen op te geven voordat beveiliging als verouderd wordt beschouwd

1.  Open op uw groepsbeleidsbeheercomputer de [console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

3.  Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**

4.  Klik **op Beleid** en vervolgens op **Beheersjablonen.**

5.  Vouw de structuur uit Windows **onderdelen > Microsoft Defender Antivirus > handtekeningupdates** en configureer de volgende instellingen:

    1.  Dubbelklik op **Het aantal dagen definiëren voordat spywaredefinities** als verouderd worden beschouwd en stel de optie in op **Ingeschakeld.** Voer het aantal dagen in waarvoor u wilt dat Microsoft Defender AV spyware beveiligingsinformatie als verouderd beschouwt.

    2. Klik op **OK**.

    3.  Dubbelklik op **Het aantal dagen definiëren voordat virusdefinities** als verouderd worden beschouwd en stel de optie in op **Ingeschakeld.** Voer het aantal dagen in waarvan u wilt dat Microsoft Defender AV virusbeveiligingsinformatie verouderd acht.

    4. Klik op **OK**.


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a>Inhaalscans instellen voor eindpunten die al een tijdje niet zijn gescand

U kunt het aantal opeenvolgende geplande scans instellen dat kan worden gemist voordat Microsoft Defender Antivirus scan wordt uitgevoerd.

Het proces voor het inschakelen van deze functie is:

1. Ten minste één geplande scan instellen (zie het [onderwerp Scans plannen).](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
2. Schakel de functie voor inhaalscans in.
3. Definieer het aantal scans dat kan worden overgeslagen voordat een inhaalscan wordt uitgevoerd.

Deze functie kan worden ingeschakeld voor zowel volledige als snelle scans.

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a>Groepsbeleid gebruiken om de functie voor het inhalen van de scan in te stellen en te configureren

1.  Zorg ervoor dat u ten minste één geplande scan hebt ingesteld.

2.  Open op uw groepsbeleidsbeheercomputer de [console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

3.  Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**

4.  Klik **op Beleid** en vervolgens op **Beheersjablonen.**

5.  Vouw de structuur uit Windows **onderdelen > Microsoft Defender Antivirus > De** volgende instellingen scannen en configureren:

    1.  Als u geplande snelle scans hebt ingesteld,  dubbelklikt u op de instelling Snelscan inhalen inschakelen en stelt u de optie **in op Ingeschakeld.** 
    2. Als u geplande volledige scans hebt ingesteld,  dubbelklikt u op de instelling Volledige inhaaloptie inschakelen en stelt u de optie **in op Ingeschakeld.** Klik op **OK**.
    3. Dubbelklik op het aantal dagen definiëren waarna een **inhaalscan wordt** geforceerd en stel de optie in op **Ingeschakeld.** 
    4. Voer het aantal scans in dat kan worden gemist voordat een scan automatisch wordt uitgevoerd wanneer de gebruiker zich volgende keer aanmeldt bij de pc. Het type scan dat wordt uitgevoerd, wordt bepaald door het scantype Opgeven dat moet worden gebruikt voor een **geplande scan** (zie het onderwerp [Planningsscans).](scheduled-catch-up-scans-microsoft-defender-antivirus.md) Klik op **OK**.

> [!NOTE]
> De instellingstitel Groepsbeleid verwijst naar het aantal dagen. De instelling wordt echter toegepast op het aantal scans (niet dagen) voordat de inhaalscan wordt uitgevoerd.

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a>PowerShell-cmdlets gebruiken om inhaalscans te configureren

Gebruik de volgende cmdlets:

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus [en Defender-cmdlets](/powershell/module/defender/) te beheren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a>Gebruik Windows Management Instruction (WMI) om inhaalscans te configureren

Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

Zie het volgende voor meer informatie en toegestane parameters:
- [Windows Defender WMIv2-API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a>Configuratiebeheer gebruiken om inhaalscans te configureren

1.  Open op Microsoft Endpoint Manager console het antimalwarebeleid dat u wilt wijzigen (klik **op** Activa en naleving in het navigatiedeelvenster aan de linkerkant en vouw de structuur uit naar Overzicht  >  **Endpoint Protection**  >  **Antimalware-beleid**)

2.  Ga naar de **sectie Geplande scans** en forceer een scan van het geselecteerde scantype als de **clientcomputer offline is...** naar **Ja.** 

3. Klik op **OK**.

4.  [Implementeer het bijgewerkte beleid zoals gewoonlijk.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

## <a name="related-articles"></a>Aanverwante artikelen

- [Implementatie van Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Updates Microsoft Defender Antivirus en basislijnen toepassen](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Beheren wanneer beveiligingsupdates moeten worden gedownload en toegepast](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [Op basis van gebeurtenissen afgedwongen updates beheren](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Updates beheren voor mobiele apparaten en virtuele machines (VM's)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)