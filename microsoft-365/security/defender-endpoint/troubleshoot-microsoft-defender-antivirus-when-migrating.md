---
title: Problemen met Microsoft Defender Antivirus oplossen terwijl u migreert vanuit een oplossing van derden
description: Veelvoorkomende fouten oplossen bij het migreren naar Microsoft Defender Antivirus
keywords: gebeurtenis, foutcode, logboekregistratie, probleemoplossing, microsoft defender antivirus, Windows Defender antivirus, migratie
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 2ca486b86c24e18ae08753b5e88f2eb42986dddf
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690659"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a>Problemen met Microsoft Defender Antivirus oplossen terwijl u migreert vanuit een oplossing van derden

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)


U kunt hier hulp vinden als u problemen ondervindt tijdens het migreren van een beveiligingsoplossing van derden naar Microsoft Defender Antivirus.

## <a name="review-event-logs"></a>Gebeurtenislogboeken controleren

Open de app Gebeurtenisviewer door het pictogram **Zoeken** op de taakbalk te selecteren en te zoeken naar *gebeurtenisviewer.*

Informatie over Microsoft Defender Antivirus vindt u onder **Applications and Services Logs**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**. 

Selecteer vervolgens **Openen** onder **Operationeel.**

Als u een gebeurtenis selecteert in het detailvenster, ziet u meer  informatie over een gebeurtenis in het onderste deelvenster, onder de tabbladen Algemeen **en** Details.

## <a name="microsoft-defender-antivirus-wont-start"></a>Microsoft Defender Antivirus start niet

Dit probleem kan zich manifesteert in de vorm van verschillende gebeurtenis-ID's, die allemaal dezelfde onderliggende oorzaak hebben.

### <a name="associated-event-ids"></a>Gekoppelde gebeurtenis-IDs

 Gebeurtenis-id | Naam van logboek | Omschrijving | Source
-|-|-|-
15 | Toepassing | De Windows Defender-status is bijgewerkt om SECURITY_PRODUCT_STATE_OFF. | Beveiligingscentrum
5007 | Microsoft-Windows-Windows Defender/Operational | Windows Defender Antivirus Configuration is gewijzigd.  Als dit een onverwachte gebeurtenis is, moet u de instellingen controleren, omdat dit mogelijk het gevolg is van malware.<br /><br />**Oude waarde:** Standaard\IsServiceRunning = 0x0<br />**Nieuwe waarde:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1 | Windows Defender
5010 | Microsoft-Windows-Windows Defender/Operational | Windows Defender Antivirus scanning for spyware and other potentially unwanted software is disabled. | Windows Defender

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a>Hoe kunt u zien of Microsoft Defender Antivirus niet start omdat er een antivirusprogramma van derden is geïnstalleerd

Als u op een Windows 10-apparaat geen Microsoft Defender voor Eindpunt gebruikt en u een antivirusprogramma van derden hebt geïnstalleerd, wordt Microsoft Defender Antivirus automatisch uitgeschakeld. Als u Microsoft Defender voor Eindpunt gebruikt met een antivirusprogramma van derden, wordt Microsoft Defender Antivirus in de passieve modus met beperkte functionaliteit gebruikt.

> [!TIP]
> Het scenario dat zojuist is beschreven, is alleen van toepassing op Windows 10. Andere versies van Windows hebben [verschillende antwoorden op](microsoft-defender-antivirus-compatibility.md) Microsoft Defender Antivirus die wordt uitgevoerd naast beveiligingssoftware van derden.

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a>Services-app gebruiken om te controleren of Microsoft Defender Antivirus is uitgeschakeld

Als u de Services-app wilt openen, **selecteert** u het pictogram Zoeken op de taakbalk en zoekt u naar *services.* U kunt de app ook openen vanaf de opdrachtregel door *services.msc te typen.*

Informatie over Microsoft Defender Antivirus wordt weergegeven in de Services-app onder **Windows Defender**  >  **Operationeel.** De naam van de antivirusservice is *Windows Defender Antivirus Service.*

Tijdens het controleren van de app ziet u mogelijk dat *Windows Defender Antivirus Service* is ingesteld op handmatig, maar wanneer u deze service handmatig probeert te starten, krijgt u een waarschuwing met de melding: De Windows Defender Antivirus Service service op lokale computer is gestart en vervolgens *gestopt. Sommige services worden automatisch gestopt als ze niet worden gebruikt door andere services of programma's.*

Dit geeft aan dat Microsoft Defender Antivirus automatisch is uitgeschakeld om de compatibiliteit met een antivirusprogramma van derden te behouden.

#### <a name="generate-a-detailed-report"></a>Een gedetailleerd rapport genereren

U kunt een gedetailleerd rapport genereren over momenteel actief groepsbeleid door een opdrachtprompt te openen in de modus Uitvoeren als **beheerder** en vervolgens de volgende opdracht in te voeren:

```powershell
GPresult.exe /h gpresult.html
```

Hiermee wordt een rapport gegenereerd dat zich op *./gpresult.html bevindt.* Open dit bestand en u ziet mogelijk de volgende resultaten, afhankelijk van hoe Microsoft Defender Antivirus is uitgeschakeld.

##### <a name="group-policy-results"></a>Groepsbeleidsresultaten

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a>Als beveiligingsinstellingen worden geïmplementeerd via groepsbeleid (GPO) op het domein of lokaal niveau, of als System Center Configuration Manager (SCCM)

In het rapport GPResults, onder de kop *Windows Components/Windows Defender Antivirus,* ziet u mogelijk iets als de volgende vermelding, waarmee wordt aangegeven dat Microsoft Defender Antivirus is uitgeschakeld.

Beleid | Instelling | GPO winnen
-|-|-
Windows Defender Antivirus uitschakelen | Ingeschakeld | Win10-Workstations

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a>Als beveiligingsinstellingen worden geïmplementeerd via groepsbeleidsvoorkeuren (GPP)

Onder de kop *Registeritem (Sleutelpad: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Waardenaam: DisableAntiSpyware)* ziet u mogelijk zoiets als het volgende item, wat aangeeft dat Microsoft Defender Antivirus is uitgeschakeld.

DisableAntiSpyware | -
-|-
GPO winnen | Win10-Workstations
Resultaat: Succes | 
**Algemeen** | 
Actie | Update
**Eigenschappen** | 
Bijenkorf | HKEY_LOCAL_MACHINE
Sleutelpad | SOFTWARE\Policies\Microsoft\Windows Defender
Waardenaam | DisableAntiSpyware
Waardetype | REG_DWORD
Waardegegevens | 0x1 (1)

###### <a name="if-security-settings-are-implemented-via-registry-key"></a>Als beveiligingsinstellingen worden geïmplementeerd via de registersleutel

Het rapport kan de volgende tekst bevatten, waarmee wordt aangegeven dat Microsoft Defender Antivirus is uitgeschakeld:
 
> Register (regedit.exe)
>
> HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hex)

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a>Als beveiligingsinstellingen zijn ingesteld in Windows of uw Windows Server-afbeelding

Uw fanatiek beheerder heeft mogelijk het **[beveiligingsbeleid, DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**, lokaal via *GPEdit.exe*, *LGPO.exe* ingesteld of door het register in hun taakvolgorde te wijzigen. U kunt [een vertrouwde afbeeldingsaanduiding configureren](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) voor Microsoft Defender Antivirus.

### <a name="turn-microsoft-defender-antivirus-back-on"></a>Microsoft Defender Antivirus weer in- en uit-

Microsoft Defender Antivirus wordt automatisch in gebruik als er geen andere antivirusprogramma's actief zijn. U moet de antivirussoftware van derden volledig uitschakelen om ervoor te zorgen dat Microsoft Defender Antivirus met volledige functionaliteit kan worden uitgevoerd.

> [!WARNING]
> Oplossingen die suggereren dat u de *beginwaarden* van Windows Defender voor *wdboot,* *wdfilter,* *wdnisdrv,* *wdnissvc* en *windefend* in HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services bewerkt, worden niet ondersteund en kunnen u dwingen uw systeem opnieuw te imagen.

De passieve modus is beschikbaar als u Microsoft Defender voor Eindpunt en een antivirusprogramma van derden gaat gebruiken samen met Microsoft Defender Antivirus. Met de passieve modus kan Microsoft Defender bestanden scannen en zichzelf bijwerken, maar worden bedreigingen niet verwijderd. Daarnaast is gedragscontrole via [realtimebeveiliging](configure-real-time-protection-microsoft-defender-antivirus.md) niet beschikbaar in de passieve modus, tenzij preventie van gegevensverlies in eindpunten [(DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) wordt geïmplementeerd.

Een andere functie, ook [wel beperkt periodiek](limited-periodic-scanning-microsoft-defender-antivirus.md)scannen genoemd, is beschikbaar voor eindgebruikers wanneer Microsoft Defender Antivirus is ingesteld om automatisch uit te schakelen. Met deze functie kan Microsoft Defender Antivirus regelmatig bestanden scannen samen met een antivirusprogramma van derden, waarbij een beperkt aantal detecties wordt gebruikt.

> [!IMPORTANT]
> Beperkt periodiek scannen wordt niet aanbevolen in bedrijfsomgevingen. De detectie-, beheer- en rapportagemogelijkheden die beschikbaar zijn bij het uitvoeren van Microsoft Defender Antivirus in deze modus, worden verminderd ten opzichte van de actieve modus.

### <a name="see-also"></a>Zie ook

* [Microsoft Defender Antiviruscompatibiliteit](microsoft-defender-antivirus-compatibility.md)
* [Microsoft Defender Antivirus in de Windows Security-app](microsoft-defender-security-center-antivirus.md)