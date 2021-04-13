---
title: Herstel configureren voor antivirusdetecties van Microsoft Defender
description: Configureren wat Microsoft Defender Antivirus moet doen wanneer een bedreiging wordt gedetecteerd en hoe lang in quarantaine geplaatste bestanden moeten worden bewaard in de quarantainemap
keywords: herstel, oplossing, verwijderen, bedreigingen, quarantaine, scannen, herstellen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7f41e9c5b38e93ce84fbd971e02ebc2d77432c3f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690050"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a>Herstel configureren voor antivirusdetecties van Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Wanneer Microsoft Defender Antivirus een scan uit voert, wordt geprobeerd om gedetecteerde bedreigingen te corrigeren of te verwijderen. U kunt configureren hoe Microsoft Defender Antivirus bepaalde bedreigingen moet aanpakken, of er een herstelpunt moet worden gemaakt voordat u herstelt en wanneer bedreigingen moeten worden verwijderd.

In dit artikel wordt beschreven hoe u deze instellingen configureert met groepsbeleid, maar u kunt ook [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) en Microsoft [Intune gebruiken.](/intune/device-restrictions-configure) 

U kunt ook de [ `Set-MpPreference` PowerShell-cmdlet](/powershell/module/defender/set-mppreference) of [ `MSFT_MpPreference` WMI-klasse](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) gebruiken om deze instellingen te configureren.

## <a name="configure-remediation-options"></a>Herstelopties configureren

1. Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

2. Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie** en selecteer **Beheersjablonen.**

3. Vouw de boom uit naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus.** 

4. Selecteer een locatie in de onderstaande tabel en bewerk het beleid zo nodig. 

5. Kies **OK**.

|Locatie | Instelling | Beschrijving | Standaardinstelling (indien niet geconfigureerd) |
|:---|:---|:---|:---|
|Scannen | Een systeemherstelpunt maken | Er wordt elke dag een systeemherstelpunt gemaakt voordat wordt geprobeerd het te reinigen of te scannen | Uitgeschakeld|
|Scannen | Het verwijderen van items uit de map scangeschiedenis in- | Opgeven hoeveel dagen items moeten worden bewaard in de scangeschiedenis | 30 dagen |
|Hoofdmap | Routine-herstel uitschakelen | U kunt opgeven of Microsoft Defender Antivirus automatisch bedreigingen herstelt of dat de eindgebruiker moet vragen wat hij of zij moet doen. | Uitgeschakeld (bedreigingen worden automatisch gesaneerd) |
|Quarantaine | Het verwijderen van items configureren uit de map Quarantaine | Opgeven hoeveel dagen items in quarantaine moeten worden bewaard voordat ze worden verwijderd | 90 dagen |
|Bedreigingen | Waarschuwingsniveaus opgeven waarop standaardactie niet moet worden ondernomen wanneer deze wordt gedetecteerd | Aan elke bedreiging die door Microsoft Defender Antivirus wordt gedetecteerd, wordt een bedreigingsniveau toegewezen (laag, gemiddeld, hoog of ernstig). U kunt deze instelling gebruiken om te definiëren hoe alle bedreigingen voor elk van de bedreigingsniveaus moeten worden verwijderd (in quarantaine geplaatst, verwijderd of genegeerd) | Niet van toepassing |
|Bedreigingen | Geef bedreigingen op waarop standaardactie niet moet worden ondernomen wanneer deze worden gedetecteerd | Geef op hoe specifieke bedreigingen (met hun bedreigings-id) moeten worden gesaneerd. U kunt opgeven of de specifieke bedreiging in quarantaine moet worden geplaatst, verwijderd of genegeerd | Niet van toepassing |

> [!IMPORTANT]
> Microsoft Defender Antivirus detecteert en herstelt bestanden op basis van vele factoren. Soms is het voltooien van een herstel vereist een herstart. Zelfs als later wordt vastgesteld dat de detectie onwaar positief is, moet het opnieuw opstarten zijn voltooid om ervoor te zorgen dat alle aanvullende herstelstappen zijn voltooid.
>
> Als u zeker weet dat Microsoft Defender Antivirus een bestand in quarantaine heeft geplaatst op basis van een false positive, kunt u het bestand herstellen uit quarantaine nadat het apparaat opnieuw is opgestart. Zie [Bestanden in quarantaine herstellen in Microsoft Defender Antivirus](restore-quarantined-files-microsoft-defender-antivirus.md).
> 
> Als u dit probleem in de toekomst wilt voorkomen, kunt u bestanden uitsluiten van de scans. Zie [Uitsluitingen configureren en valideren voor Microsoft Defender Antivirus scans.](configure-exclusions-microsoft-defender-antivirus.md)

Zie Ook [Herstel-vereiste geplande volledige Microsoft Defender Antivirus-scans configureren](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) voor meer instellingen voor herstel.

## <a name="see-also"></a>Zie ook

- [Scanopties voor Microsoft Defender Antivirus configureren](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Geplande Microsoft Defender Antivirus-scans configureren](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [On-demand Microsoft Defender Antivirus scans configureren en uitvoeren](run-scan-microsoft-defender-antivirus.md)
- [De meldingen configureren die op eindpunten worden weergegeven](configure-notifications-microsoft-defender-antivirus.md)
- [Interactie met Microsoft Defender Antivirus voor eindgebruikers configureren](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [De resultaten van Microsoft Defender Antivirus scans en herstel aanpassen, starten en controleren](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)