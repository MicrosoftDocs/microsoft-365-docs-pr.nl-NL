---
title: Belangrijke mappen beschermen tegen ransomware tegen het versleutelen van uw bestanden met gecontroleerde maptoegang
description: Bestanden in standaardmappen kunnen worden beveiligd tegen het wijzigen van schadelijke apps. Voorkom dat ransomware uw bestanden versleutelt.
keywords: gecontroleerde maptoegang, windows 10, Windows Defender, ransomware, beveiligen, bestanden, mappen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 06/10/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: c60620d2a589c8473764b810d1fcb0e24f674451
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904054"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a>Belangrijke mappen beveiligen met gecontroleerde maptoegang

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a>Wat is beheerde maptoegang?

Gecontroleerde maptoegang helpt uw waardevolle gegevens te beschermen tegen schadelijke apps en bedreigingen, zoals ransomware. Gecontroleerde maptoegang beschermt uw gegevens door apps te controleren op een lijst met bekende, vertrouwde apps. Ondersteund op Windows Server 2019- en Windows 10-clients, kan gecontroleerde maptoegang worden ingeschakeld met de Windows-beveiliging-app, Microsoft Endpoint Configuration Manager of Intune (voor beheerde apparaten). 

> [!NOTE]
> Scripting-engines worden niet vertrouwd en u kunt ze geen toegang verlenen tot gecontroleerde beveiligde mappen.  PowerShell wordt bijvoorbeeld niet vertrouwd door gecontroleerde maptoegang, zelfs niet als u dit toestaat met [certificaat- en bestandsindicatoren.](/microsoft-365/security/defender-endpoint/indicator-certificates) 

Gecontroleerde toegang tot mappen werkt het beste met [Microsoft Defender voor](microsoft-defender-endpoint.md)Eindpunt, waarmee u gedetailleerde rapportage krijgt over gebeurtenissen en blokken voor gecontroleerde mappentoegang als onderdeel van de gebruikelijke scenario's voor [waarschuwingsonderzoek.](investigate-alerts.md)

> [!TIP]
> Met gecontroleerde mappentoegangsblokken worden geen waarschuwingen gegenereerd in de [wachtrij Waarschuwingen.](alerts-queue.md) U kunt echter informatie over beheerde maptoegangsblokken weergeven in de tijdlijnweergave van het [apparaat,](investigate-machines.md)tijdens het gebruik van geavanceerd zoeken [of](advanced-hunting-overview.md)met [aangepaste detectieregels.](custom-detection-rules.md)

## <a name="how-does-controlled-folder-access-work"></a>Hoe werkt beheerde maptoegang?

Gecontroleerde maptoegang werkt door alleen vertrouwde apps toegang te geven tot beveiligde mappen. Beveiligde mappen worden opgegeven wanneer beheerde maptoegang is geconfigureerd. Meestal worden veelgebruikte mappen, zoals mappen die worden gebruikt voor documenten, afbeeldingen, downloads, en dergelijke, opgenomen in de lijst met beheerde mappen. 

Gecontroleerde maptoegang werkt met een lijst met vertrouwde apps. Apps die zijn opgenomen in de lijst met vertrouwde software werken zoals verwacht. Apps die niet in de lijst zijn opgenomen, kunnen geen wijzigingen aanbrengen in bestanden in beveiligde mappen. 

Apps worden toegevoegd aan de lijst op basis van hun aanwezigheid en reputatie. Apps die veel voorkomen in uw organisatie en die nooit gedrag hebben weergegeven dat als schadelijk wordt beschouwd, worden als betrouwbaar beschouwd. Deze apps worden automatisch aan de lijst toegevoegd.

Apps kunnen ook handmatig worden toegevoegd aan de vertrouwde lijst met Behulp van Configuration Manager of Intune. Extra acties, zoals het [toevoegen van een bestandsindicator](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) voor een app, kunnen worden uitgevoerd vanuit de console van het beveiligingscentrum.

## <a name="why-controlled-folder-access-is-important"></a>Waarom gecontroleerde maptoegang belangrijk is

Gecontroleerde toegang tot mappen is vooral handig om uw documenten en informatie te beschermen tegen [ransomware.](https://www.microsoft.com/wdsi/threats/ransomware) Bij een ransomware-aanval kunnen uw bestanden worden versleuteld en gegijzeld. Er wordt een melding weergegeven op de computer waarop een app heeft geprobeerd wijzigingen aan te brengen in een bestand in een beveiligde map. U kunt [de melding aanpassen met](customize-attack-surface-reduction.md#customize-the-notification) uw bedrijfsgegevens en contactgegevens. U kunt de regels ook afzonderlijk inschakelen om aan te passen welke technieken de functiemonitors heeft.

De [beveiligde mappen bevatten](#review-controlled-folder-access-events-in-windows-event-viewer) veelgebruikte systeemmappen (inclusief opstartsectoren) en u kunt meer mappen [toevoegen.](customize-controlled-folders.md#protect-additional-folders) U kunt ook [toestaan dat apps](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) hen toegang geven tot de beveiligde mappen.

U kunt de [auditmodus gebruiken om](audit-windows-defender.md) te evalueren hoe gecontroleerde maptoegang van invloed is op uw organisatie als deze is ingeschakeld. U kunt ook naar de website [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Windows Defender Test ground demo.wd.microsoft.com om te bevestigen dat de functie werkt en te zien hoe deze werkt.

Gecontroleerde maptoegang wordt ondersteund in de volgende versies van Windows:
- [Windows 10, versie 1709](/windows/whats-new/whats-new-windows-10-version-1709) en hoger
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a>Windows systeemmappen zijn standaard beveiligd

Windows systeemmappen zijn standaard beveiligd, samen met verschillende andere mappen: 

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

> [!NOTE]
> U kunt extra mappen als beveiligd configureren, maar u kunt de Windows systeemmappen die standaard zijn beveiligd, niet verwijderen.

## <a name="requirements-for-controlled-folder-access"></a>Vereisten voor gecontroleerde maptoegang

Voor gecontroleerde maptoegang is het [inschakelen Microsoft Defender Antivirus realtime-beveiliging vereist.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)

## <a name="review-controlled-folder-access-events-in-the-microsoft-365-defender-portal"></a>Gecontroleerde maptoegangsgebeurtenissen bekijken in Microsoft 365 Defender-portal

Defender voor Eindpunt biedt gedetailleerde rapportage over gebeurtenissen en blokken als onderdeel van de [scenario's](investigate-alerts.md) voor waarschuwingsonderzoek in Microsoft 365 Defender-portal. (Zie [Microsoft Defender voor Eindpunt in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).)

U kunt Microsoft Defender opvragen voor eindpuntgegevens met behulp van [Geavanceerd zoeken.](/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection) Als u de [auditmodus gebruikt,](audit-windows-defender.md)kunt u geavanceerd zoeken gebruiken om te zien hoe de instellingen voor gecontroleerde maptoegang van invloed zijn op uw omgeving als deze zijn ingeschakeld. [](advanced-hunting-overview.md)

Voorbeeldquery:

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Gecontroleerde maptoegangsgebeurtenissen controleren in Windows Gebeurtenisviewer

U kunt het Windows gebeurtenislogboek bekijken om gebeurtenissen te zien die worden gemaakt wanneer gecontroleerde maptoegangsblokken (of audits) een app maken:

1. Download het [evaluatiepakket en](https://aka.ms/mp7z2w) haal het *bestand* cfa-events.xmlnaar een gemakkelijk toegankelijke locatie op het apparaat.
2. Typ **Gebeurtenisviewer** in het menu Start om de Windows gebeurtenisviewer te openen.
3. Selecteer in het linkervenster onder **Acties** de optie **Aangepaste weergave importeren...**.
4. Ga naar de plaats waar u *cfa-events.xml* en selecteer deze. U kunt ook [de XML rechtstreeks kopiëren.](event-views.md)
5. Selecteer **OK**.

In de volgende tabel ziet u gebeurtenissen met betrekking tot gecontroleerde maptoegang:

|Gebeurtenis-id | Omschrijving |
|:---|:---|
|5007 | Gebeurtenis wanneer instellingen worden gewijzigd |
|1124 | Gecontroleerde gecontroleerde maptoegangsgebeurtenis | 
|1123 | Gebeurtenis Geblokkeerde gecontroleerde maptoegang |

## <a name="view-or-change-the-list-of-protected-folders"></a>De lijst met beveiligde mappen weergeven of wijzigen

U kunt de app Windows-beveiliging gebruiken om de lijst met mappen weer te geven die zijn beveiligd met beheerde maptoegang. 

1. Open op Windows 10 apparaat de Windows-beveiliging app.
2. Selecteer **Virus- & bedreigingsbeveiliging**.
3. Selecteer **onder Ransomware-beveiliging** de optie **Ransomware-beveiliging beheren.**
4. Als beheerde maptoegang is uitgeschakeld, moet u deze in- en uitschakelen. Selecteer **beveiligde mappen.**
5. Ga op een van de volgende stappen te werk:
   - Als u een map wilt toevoegen, **selecteert u + Een beveiligde map toevoegen.**
   - Als u een map wilt verwijderen, selecteert u deze en selecteert u **Vervolgens Verwijderen.** 

> [!NOTE]
> [Windows systeemmappen](#windows-system-folders-are-protected-by-default) zijn standaard beveiligd en u kunt ze niet uit de lijst verwijderen.


